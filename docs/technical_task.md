# Technical Task Plan: Android Warehouse Chemical Monitoring Application

## 1. Introduction

The Android Warehouse Chemical Monitoring Application is designed to address the need for a modern and efficient solution to replace traditional paper logbooks in warehouse environments. The application is divided into three interconnected components:

1. **Android Desktop Application:**
   - A mobile phone or tablet-based application for Android devices.
   - Provides a user-friendly interface for monitoring and managing chemicals in the warehouse.

2. **Communication Program:**
   - Facilitates communication between the Android Desktop Application and the SQL database.
   - Utilizes TCP/IP communication, exchanging data in JSON format.

3. **Database:**
   - Stores essential information related to chemicals, transactions, and user data.
   - Serves as a centralized repository for efficient data management.

## 2. Project Scope

The project scope outlines the functionalities that will and will not be included in the Android Warehouse Chemical Monitoring Application. The application is designed to cater to three distinct roles: Admin, User, and Storekeeper.

### Inclusions:

#### Admin:
- Administrative dashboard with access to all functionalities.
- User management, including the addition, modification, and removal of users.
- Chemical management, including the addittion, modification and removal of chemicals. Overview of all chemical transactions. 
- Specifying chemical "storage conditions"

#### User:
- Ability to log the taking of chemicals, specifying the chemical, quantity, setting the "needed" period and timestamp. If chemcical has "special storage conditions e.g. "under argon" or "at -20deg", this warning will be shown on the screen.
- Ability to log the returning of chemicals, specifying the chemical, quantity, and timestamp
- Receive email notifications if chemicals are not returned by the set "needed" period. 

#### Storekeeper:
- Access to detailed reports, including information on who took chemicals, when they were taken, when they were returned, and the remaining quantity.
- Capability to request reports for specific time periods or chemical types.
- Chemical management, including the addittion, modification and removal of chemicals. Overview of all chemical transactions. 
- Specifying chemical "storage conditions"

### Exclusions:

- **Financial Transactions:**
  - The application will not handle financial transactions related to chemical usage.
  
- **Inventory Management:**
  - Beyond tracking quantities taken and returned, the application will not handle general inventory management tasks.

- **Real-time Monitoring:**
  - While the application provides real-time tracking of chemical transactions, it does not support continuous monitoring during the day.

- **Chemical Ordering:**
  - The application will not include features related to ordering new chemicals or managing chemical supply chains.

### Additional Considerations:

- The application will prioritize simplicity and user-friendliness to ensure ease of use for all roles.
- Security measures will be implemented to safeguard sensitive information.
- Data privacy and compliance with relevant regulations will be integral to the application's design.

This scope sets clear boundaries for the features and functionalities of the Android Warehouse Chemical Monitoring Application, focusing on the essential tasks of tracking chemical transactions and generating relevant reports for effective warehouse management.


### Objectives

- **Efficiency Improvement:**
  - Replace traditional paper logbooks with a digital solution to streamline and enhance the monitoring of chemicals in warehouses.

- **Real-time Data Access:**
  - Enable real-time access to critical information, reducing manual effort and improving decision-making processes.

- **User-Friendly Interface:**
  - Develop an intuitive Android application that simplifies the process of logging, tracking, and managing chemicals.

### Need for the Application

The need for this application arises from the limitations of traditional paper-based logbooks, which are often time-consuming, prone to errors, and lack real-time accessibility. The Android Warehouse Chemical Monitoring Application aims to overcome these challenges by providing a digital platform that ensures efficient tracking, secure communication, and centralized data management.

This introduction sets the stage for the subsequent sections, outlining the scope, functionalities, and technical aspects of the Android warehouse chemical monitoring application.

## 3. User Stories and Use Cases
Define user stories and use cases to describe how different users will interact with the application.

## 4. Functional Requirements

List and describe the essential features and functionalities of the application:

### 4.1 Chemicals Logging
- **Description:** Users should be able to log the taking and returning of chemicals, providing details such as chemical type, quantity, and timestamp.
- **User Roles:** All roles (Admin, User, Storekeeper)

### 4.2 Transaction Tracking
- **Description:** The system must track all chemical transactions, including details on who took the chemicals, when they were taken, when they were returned, and the quantity involved.
- **User Roles:** All roles (Admin, User, Storekeeper)

### 4.3 User Authentication
- **Description:** Secure authentication mechanisms should be implemented to ensure that only authorized users (Admin, User, Storekeeper) can access the application.
- **User Roles:** All roles (Admin, User, Storekeeper)

### 4.4 Code Scanning
- **Description:** The application should support barcode scanning or QR code scanning to streamline the logging process.
- **User Roles:** All roles (Admin, User, Storekeeper)
/*Comment from DV - I have doubts about the above task, it is not so easy to implement and requires of knowlage of some 3rd party applicatons*/


### 4.5 Reporting
- **Description:** Users, especially Storekeepers, should have access to detailed reports on chemical transactions, indicating who took chemicals, when they were taken, when they were returned, and the remaining quantity.
- **User Roles:** Storekeeper

### 4.6 User Roles and Permissions
- **Description:** Different roles (Admin, User, Storekeeper) will have distinct permissions to ensure appropriate access levels for each user type.
- **User Roles:** Admin, User, Storekeeper


## 5. Non-Functional Requirements
Specify non-functional aspects such as:
- Performance expectations
- Security measures (encryption, secure authentication)
- Compatibility with Android devices (minimum Android version)

## 6. Technical Stack
Specify the technology stack:
- Programming Language: Kotlin
- Development Framework: Android SDK
- Database: SQLite or Room Database
- Third-party Libraries: If any (e.g., barcode scanning libraries)

## 7. Database Design
Outline the database structure, including tables and relationships:
- Chemicals Table
- Transactions Table
- Users Table

## 8. UI/UX Design
Describe the expected user interface and user experience, including:
- Screens and navigation flow
- Input forms
- Dashboard and reporting layouts
- Searchbar with possibilities to search by Name, CAS, WH code.
- Filters (by project, by storage condition, date)

## 9. Security Considerations
Identify potential security risks and outline measures to secure the application and its data.

## 10. Integration
Specify integration requirements, if any:
- A plagin to fetch all convenient names of chemical by its CAS number (written on python or other language). I will use Json to comunicate with the app.
- Barcode scanner integration /*Under the consideration*/
- User authentication integration

## 11. Testing Plan
Define a comprehensive testing plan:
- Unit testing for individual components
- Integration testing for combined functionalities
- User acceptance testing

## 12. Timeline and Milestones
Establish a timeline for the development process:
- Milestone 1: Database design and setup
- Milestone 2: UI/UX design and basic functionality implementation
- Milestone 3: Integration and testing
- Milestone 4: Final testing and debugging
- Milestone 5: Deployment and post-launch support

## 13. Communication and Collaboration
Specify communication tools and channels for effective collaboration:
- Project management platform (e.g., Jira)
- Regular meetings (weekly or bi-weekly)

## 14. Documentation
Emphasize the importance of documentation:
- Code documentation
- User manuals
- Technical documentation for maintenance

## 15. Legal and Compliance
Ensure compliance with relevant laws and regulations.

## 16. Review and Approval
Define a process for regular reviews and approvals from stakeholders:
- Regular demo sessions
- Stakeholder feedback sessions

