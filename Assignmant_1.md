ASSIGNMENT 1 (DB & SYSTEM DESIGN)

SCHEMA DESIGN and NORMALISATION 

Initial identification of Columns from the given image 
Movie Attributes : Movie Name, Language, Type(2D/3D), Certification
Theatre Attributes : Theatre Name, Location, No of Screens, Timings 
Transaction Attributes: Date, Ticket Price 

NORMALIZATION 
Phase 1: 
Movies like AVATAR can be released in multiple languages like English and Hindi and formats like 2D and 3D. Storing these in a single cell violates 1NF
Phase 2: 
A theatre has multiple screens. Specific shows happen at specific time on specific screens. We only need to link shows to theatres 
Phase 3: 
Since there are multiple screens in a theatre and these can have different movies in it the screens and theatres tables are separated. 

FINAL SCHEMA 
MOVIES: Movie_ID (PK), Movie_Name, Certificate
THEATRES: Theatre_ID (PK), Theatre_Name, Location
SCREENS: Screen_ID (PK), Theatre_ID (FK), Screen_Name
SHOWS: Show_ID (PK), Movie_ID (FK), Screen_ID (FK), Date, Time, Price, Language, Format
PK => Primary Key,  FK=> Foreign KEY 


SAMPLE TABLES 

MOVIES 

| MOVIE_ID | MOVIE_NAME               |  CERTIFICATE|
| :--- 	   | :---   				  | :--- 		|
| 1        | Dasara                   | UA			|
| 2        | Avatar: The Way of Water | UA			|


THEATRES 

THEATRE_ID      THEATRE_NAME                    LOCATION
101             PVR: Nexus (Formerly Forum)     "Koramangala, Bangalore"
102             PVR: Vega City,                 "Bannerghatta Road, Bangalore"


SCREENS 

SCREEN_ID       THEATRE_ID      SCREEN_NAME
1               101             Audi 1
2               101             Playhouse 4K
3               102             Audi 1
4               102             Gold Class


SHOWS 

SHOW_ID     MOVIE_ID    SCREEN_ID   SHOW_DATE   START_TIME  PRICE   LANGUAGE    FORMAT
1001        1           1           2023-04-25  12:15:00    350.00  Telugu      2D
1002        2           2           2023-04-25  01:20:00    450.00  English     3D


QUERY to list down all the shows on a given date at a given theatre along with their respective show timings.

SELECT 
    MOVIES.MOVIE_NAME, 
    THEATRES.THEATRE_NAME, 
    SCREENS.SCREEN_NAME,
    SHOWS.START_TIME,
    SHOWS.LANGUAGE,
    SHOWS.FORMAT
FROM 
    SHOWS
JOIN MOVIES ON SHOWS.MOVIE_ID = MOVIES.MOVIE_ID
JOIN SCREENS ON SHOWS.SCREEN_ID = SCREENS.SCREEN_ID
JOIN THEATRES ON SCREENS.THEATRE_ID = THEATRES.THEATRE_ID
WHERE 
    SHOWS.SHOW_DATE = '2024-04-25' 
    AND THEATRES.THEATRE_NAME = 'PVR Nexus'
ORDER BY 
    SHOWS.START_TIME ASC;

	

		


