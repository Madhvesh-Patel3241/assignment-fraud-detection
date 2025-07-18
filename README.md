# Fraud Detection in Local Classroom Assignments

## Overview
This project is a web-based system designed to detect and prevent fraudulent activities in classroom assignment submissions, ensuring academic integrity. Built with **AngularJS** for the frontend, **Flask API** and **Python** for the backend, and **MySQL** for data storage, it automates plagiarism detection, generates fraud reports, and provides secure user authentication.

## Features

 - **Plagiarism Detection**: Compares assignments to identify internal plagiarism using text similarity analysis.
 - **Fraud Reports**: Generates detailed reports highlighting plagiarized sections and fraud scores.
 - **File Upload Management**: Supports multiple file uploads with validation and organization by class.
 - **User Authentication**: Secure registration, login, and admin CRUD operations using JWT.
 - **Visual Dashboard**: Displays plagiarism results with graphs and charts.

## Tech Stack

 - **Frontend**: AngularJS, Bootstrap
 - **Backend**: Python, Flask, scikit-learn, numpy
 - **Database**: MySQL
 - **Tools**: JIRA (project management), Postman (API testing), SonarQube (static analysis, planned)
 - **Authentication**: JWT, bcrypt

## Installation

 1. **Clone the Repository:**

        git clone https://github.com/Madhvesh-Patel3241/assignment-fraud-detection.git
        cd fraud-detection-classroom

 2. **Backend Setup:**

 - Configure MySQL database (see Database Schema below).
 - Run the Flask server:

        python app.py

3. **Frontend Setup:**
 - Install npm dependencies:

       npm install

 - Start the AngularJS app:

       npm start

4. **Environment Variables:**

 - Create a .env file in the backend root with:

       MYSQL_HOST=localhost
       MYSQL_USER=root
       MYSQL_PASSWORD=your_password
       MYSQL_DB=plagiarism_checker
       JWT_SECRET_KEY=your_secret_key

 ## Database Schema

 The project uses a MySQL database with the following tables:

    -- Files Table
    CREATE TABLE files (
        id INT AUTO_INCREMENT PRIMARY KEY,
        filename VARCHAR(255) NOT NULL,
        filepath TEXT NOT NULL
    );

    -- Results Table
    CREATE TABLE results (
        id INT AUTO_INCREMENT PRIMARY KEY,
        file1 VARCHAR(255),
        file2 VARCHAR(255),
        similarity FLOAT
    );

    -- Users Table
    CREATE TABLE users (
        id INT AUTO_INCREMENT PRIMARY KEY,
        username VARCHAR(100) NOT NULL,
        email VARCHAR(100) NOT NULL UNIQUE,
        password VARCHAR(255) NOT NULL
    );


 ## Usage

 1. Register or log in as a user/admin.
 2. Upload assignment files via the frontend interface.
 3. View plagiarism detection results and fraud reports.
 4. Admins can manage users and configure similarity thresholds.


## Screenshots

 - Login Page:
   
 
 - Plagiarism Dashboard:
