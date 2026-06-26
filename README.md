CyberBot – Cybersecurity Awareness Chatbot
Programming POE Part 3
Developed by:

Sandile Siyo

Project Overview

CyberBot is a desktop application developed using C# WPF (.NET Framework) that helps users learn about cybersecurity in an interactive way. The application acts as an intelligent chatbot capable of answering cybersecurity questions, remembering user interests, managing reminder tasks using SQL Server, playing a voice greeting, and providing an educational cybersecurity quiz. The project also incorporates ML.NET to improve chatbot responses through machine learning.

Main Features
User Login

When the application starts, users are asked to enter a username. The username is stored inside a text file (user_names.txt). If the username already exists, the chatbot welcomes the user back; otherwise, it saves the new username and welcomes the new user.

Voice Greeting

When the application launches, the voice_greeting class uses SoundPlayer to play a prerecorded WAV greeting (sandi.wav). This provides a more interactive experience before the chatbot begins.

Cybersecurity Chatbot

The chatbot answers questions related to cybersecurity using a built-in knowledge base stored in the respond.cs class.

Topics include:

Cybersecurity
Phishing
Password Safety
Firewalls
VPNs
Fraud
Hacked Accounts
Safe Browsing
Emotional Responses

Example:

User: What is phishing?

CyberBot: Phishing is a scam where attackers pretend to be trusted sources to steal sensitive information.

Keyword Matching

The chatbot removes unnecessary words (stop words) such as:

the
is
and
of
to

This allows the chatbot to search only meaningful keywords before generating a response.

Machine Learning (ML.NET)

The project integrates ML.NET to make the chatbot smarter.

The training.cs class:

Loads training data
Trains a text classification model
Saves the trained model as nlp_model.zip
Loads the saved model
Predicts responses
Learns from unknown questions

Whenever the chatbot cannot answer a question, it stores the question inside unknown_questions.txt for future improvements.

User Interest Memory

Users can tell the chatbot what they are interested in.

Example:

I am interested in networking and cybersecurity.

The chatbot stores these interests inside interested_topic.txt.

After every few conversations, CyberBot reminds the user about their saved interests to make conversations more personal.

Reminder Task Management

Users can create reminder tasks directly through the chatbot.

Example:

Add task Study Cryptography

Then:

Yes remind me in 3 days

The application stores:

Task Name
Task Description
Due Date
Task Status

Tasks are saved inside a SQL Server database.

Users can:

Create tasks
View tasks
Mark tasks as completed
Delete completed tasks
SQL Database

The application uses SQL Server LocalDB.

Database Name:

tasks_prog

Table:

poe_tasks

Columns:

Column	Description
task_id	Primary Key
task_name	Task title
task_description	Task details
task_dueDate	Reminder date
task_status	Pending or Done

Supported database operations include:

INSERT
SELECT
UPDATE
DELETE

The program also checks whether the table exists and creates it automatically if necessary.

Cybersecurity Quiz

The chatbot includes an educational multiple-choice quiz.

The quiz features:

Randomized answer positions
Score tracking
Automatic quiz reset after completion
Multiple cybersecurity questions

Topics include:

Password Safety
VPN
Safe Browsing
Public Wi-Fi
Phishing

Each correct answer awards 5 marks.

Application Pages

The application is divided into multiple pages using WPF Grids:

Home Page
Username Page
Chat Page
Reminder Page
Activity Log
Quiz Game

The side menu allows users to navigate easily between these sections.

Technologies Used
Programming Language: C#
Framework: WPF (.NET Framework)
Machine Learning: ML.NET
Database: SQL Server LocalDB
IDE: Microsoft Visual Studio 2022
Database Language: SQL
Project Structure
MainWindow.xaml

Responsible for the graphical user interface.

Contains:

Home screen
Username page
Chat interface
Reminder page
Quiz page
Navigation menu
MainWindow.xaml.cs

Acts as the controller for the application.

Responsibilities include:

Switching between pages
Sending chatbot messages
Managing reminders
Running the cybersecurity quiz
Displaying conversations
Handling user interactions
respond.cs

Contains the chatbot's knowledge base.

Stores:

Cybersecurity responses
Emotional responses
Stop words used during keyword matching
training.cs

Implements machine learning functionality.

Functions include:

Training the ML model
Predicting responses
Learning unknown questions
Saving and loading the trained model
tasks.cs

Handles all SQL Server operations.

Responsible for:

Creating the database table
Inserting tasks
Loading tasks
Updating task status
Deleting completed tasks
user_name.cs

Handles user management.

Functions include:

Saving usernames
Checking returning users
Displaying welcome messages
voice_greeting.cs

Uses SoundPlayer to play the welcome audio when the application starts.

Quiz_Question_Load.cs

Automatically loads all cybersecurity quiz questions.

Question_in_quiz.cs

Represents a quiz question object.

Stores:

Question
Correct Answer
Wrong Answers
Files Created Automatically

During execution, the application creates and updates the following files:

File	Purpose
user_names.txt	Stores usernames
interested_topic.txt	Stores user interests
unknown_questions.txt	Stores unanswered questions
learned_questions.txt	Stores learned responses
nlp_model.zip	Saved ML.NET model
How to Run the Project
Open the solution in Visual Studio 2022.
Restore all required NuGet packages (including ML.NET if necessary).
Ensure SQL Server LocalDB is installed.
Run the SQL script (tasks_prog.sql) to create the database, or allow the application to create the table automatically.
Build and run the project.
Enter a username and begin chatting with CyberBot.
Learning Outcomes Demonstrated

This project demonstrates knowledge of:

Object-Oriented Programming (OOP)
Windows Presentation Foundation (WPF)
Event-Driven Programming
File Handling
SQL Database Integration
CRUD Operations
Machine Learning with ML.NET
Collections (Lists and ArrayLists)
Exception Handling
Input Validation
Modular Programming
Cybersecurity Awareness
Future Improvements

Possible future enhancements include:

Voice recognition
Online/cloud database integration
More advanced Natural Language Processing
User authentication and login system
Administrator dashboard
Dark and Light themes
Improved AI training with larger datasets
Cloud storage for user information
Additional cybersecurity learning modules
Conclusion

CyberBot is an educational cybersecurity assistant designed to help users improve their understanding of online safety through interactive conversations, intelligent responses, reminder management, and quiz-based learning. The project combines C# WPF, SQL Server, ML.NET, file handling, and object-oriented programming principles to create a complete desktop application that demonstrates both software development skills and cybersecurity awareness.
