AIRTRIBE-BOOK-MY-SHOW
DB and system design Assingment 1
🎬 BookMyShow Database Design (Assignment 1)

This repository contains the database schema design and SQL implementation for a movie ticketing platform similar to BookMyShow. This project was completed as part of the **Airtribe** backend engineering course.

📄 Project Overview
The objective of this assignment was to design a robust, normalized database to handle:
* Theatres & Screens: Managing multiple screens within a theatre location.
* Movies: Storing static movie details.
* Shows: Handling time-specific screenings with variable attributes like Price, Language, and Format (2D/3D).

🛠 Features
* Normalization: All tables are normalized up to BCNF (Boyce-Codd Normal Form) to eliminate redundancy and update anomalies.
* Relational Integrity: Proper use of Primary and Foreign Keys to link Movies, Screens, and Theatres.
* Executable SQL: Includes scripts compatible with MySQL for creating tables and inserting sample data.
* Complex Queries: Includes solution for retrieving showtimes by joining multiple entities.

📂 Repository Structure

File - Description 

`Assignment1.md`: Main Submission Doc. Contains the full schema documentation, logical reasoning, table structures, and SQL code. 


 📊 Database Schema Snapshot
The design consists of 4 core tables:
* MOVIES: `(MOVIE_ID, MOVIE_NAME, CERTIFICATE)`
* THEATRES: `(THEATRE_ID, THEATRE_NAME, LOCATION)`
* SCREENS: `(SCREEN_ID, THEATRE_ID, SCREEN_NAME)`
* SHOWS: `(SHOW_ID, MOVIE_ID, SCREEN_ID, DATE, TIME, ...)`

---
Submitted by SWATHI M for Airtribe.
