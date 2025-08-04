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

       ng serve

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
   
   <img width="1892" height="893" alt="Screenshot 2025-08-01 190246" src="https://github.com/user-attachments/assets/9d8495fb-bfa8-4e25-af52-376d94725a9b" />

 - Register Page:

   <img width="1888" height="892" alt="Screenshot 2025-08-01 190307" src="https://github.com/user-attachments/assets/cda588a1-aa8c-4bc8-8489-ba8b4ee15af2" />
   
- Home Page:

   <img width="1905" height="893" alt="Screenshot 2025-08-01 185847" src="https://github.com/user-attachments/assets/317b4ae4-1084-471c-be62-cf7555d1561b" />

 - Plagiarism Dashboard:

   <img width="1901" height="897" alt="Screenshot 2025-08-01 185925" src="https://github.com/user-attachments/assets/31ec7bdc-8bfe-4e22-9a7e-4df8b5a88222" />

  - Report Page:

   <img width="1897" height="890" alt="Screenshot 2025-08-01 190227" src="https://github.com/user-attachments/assets/2ef36990-8d16-4450-9291-49229ddcf2c8" />


## Future Enhancements
 - Integrate machine learning for advanced plagiarism detection.
 - Optimise performance for large datasets.
 - Implement full CI/CD pipelines with Jenkins.
 - Add support for multiple courses/institutions.

<!-- Team

Prajapati Akash Ashokkumar - Frontend, Authentication, Reporting
Patel Madhvesh Ajaybhai - Backend, Plagiarism Detection, File Management --> 

 Built with ❤️ by Team ClearGrade
