
 Hospital Administration System (Console Version)


This project is a complete console-based Hospital Administration System developed in Python using SQLite as the backend database. It is designed to help manage patients, doctors, appointments, and billing operations in a small hospital or clinic setup. The system runs fully in the terminal and automatically creates the required database tables on first run.  

1. Project Overview
The application follows a menu-driven structure. Every section (patients, doctors, appointments, billing) has its own submenu. All user inputs are taken through the console. SQLite is used because it requires no installation and stores data in a single file: hospital.db.
  
2. How the Code Works
2.1 Database Initialization
When the program starts, init_db() creates tables if they don't already exist:  
•patients - stores patient details  
•doctors - stores doctor details  
•appointments - links patients and doctors with date/time  
•bills - stores bill summary (total, status, date)  
•bill_items - stores individual bill line items 
 
Every function uses get_connection() to open database access cleanly.  

2.2 Patient Management
The patient menu provides three functions:
•Add patient - Inserts a new record into the database.  
•List patients - Displays all patients with their IDs.  
•Search patient - Searches by ID or name using SQL LIKE.  

This section ensures patient details are always accessible for appointments and billing.

2.3 Doctor Management
The doctor section works similarly:  
Add doctor  
List doctors  
Doctors are linked to appointments, so every appointment must reference a valid doctor ID.
  
2.4 Appointment Scheduling
Appointments connect patients and doctors. Each appointment stores date, time, and notes. The system joins tables to display:  
Patient name  
Doctor name  
Appointment time and notes  
This is handled using SQL JOIN queries for readability. 
 
2.5 Billing System
The billing module is one of the most functional components. 
 
Creating a bill:
•User enters patient ID and optional appointment ID.  
•Multiple bill items can be added (service + amount).  
•The system calculates total amount automatically.  
•Bill is stored with status UNPAID.  

Viewing bills:
List all bills with patient names.  
View a detailed bill showing all items.  

Marking a bill as PAID:
The system updates status using an SQL UPDATE query.  

Revenue Report:
Shows:
Total PAID amount collected  
Total UNPAID amount still pending  

2.6 Menu System
The main_menu() function controls navigation. Every option leads to a submenu, and each submenu loops until the user returns back. 

The structure is clean and easy to extend if needed (e.g., add medicines, staff management, etc.).  

3. How to Run the Project
1)Install Python 3.  
2)Save script as hospital.py.  
3)Run using: python hospital.py.  

On first run, the database is created automatically.  

4. Improvements You Can Add

•Input validation (avoid wrong IDs or formats)  
•Update/delete options for all sections  
•Export bills to PDF  
•GUI version using Tkinter or PyQt  
•Login authentication system  

5. Conclusion

This project provides a complete beginner-friendly hospital management solution with a clear structure, working database integration, and modular functions. It is ideal for learning database operations, menu-driven programming, and real-world system design.  
Would you like me to summarize a specific section, like the billing system or database structure?
