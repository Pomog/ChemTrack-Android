# Technical Task Plan: Android Warehouse Chemical Monitoring Application

## Table of Contents

1. [Introduction](#1-introduction)
2. [Project Scope](#2-project-scope)
   - [Inclusions](#21-inclusions)
   - [Exclusions](#22-exclusions)
   - [Additional Considerations](#23-additional-considerations)
3. [Objectives](#3-objectives)
4. [Need for the Application](#4-need-for-the-application)
5. [User Stories and Use Cases](#5-user-stories-and-use-cases)
   - [Take from Storage](#51-take-from-storage)
   - [Return To Storage](#52-return-to-storage)
   - [Check My History](#53-check-my-history)
   - [View Logs for WH Manager](#54-view-logs-for-wh-manager)
   - [View Warehouse](#55-view-warehouse)
   - [Edit Chemical](#56-edit-chemical)
   - [Delete Chemical](#57-delete-chemical)
   - [View Taken Chemicals for WH manager](#58-view-taken-chemicals-for-wh-manager)
   - [Register chemicals to the Data Base for WH manager](#59-register-chemicals-to-the-data-base-for-wh-manager)
   - [Changing and assigning new roles for user](#510-changing-and-assigning-new-roles-for-user)
6. [Functional Requirements](#6-functional-requirements)
   - [Chemicals Logging](#61-chemicals-logging)
   - [Transaction Tracking](#62-transaction-tracking)
   - [User Authentication](#63-user-authentication)
   - [Code Scanning](#64-code-scanning)
   - [Reporting](#65-reporting)
   - [User Roles and Permissions](#66-user-roles-and-permissions)
7. [Non-Functional Requirements](#7-non-functional-requirements)
8. [Technical Stack](#8-technical-stack)
9. [Database Design](#9-database-design)
10. [UI/UX Design](#10-uiux-design)
11. [Security Considerations](#11-security-considerations)
12. [Integration](#12-integration)
13. [Testing Plan](#13-testing-plan)
14. [Timeline and Milestones](#14-timeline-and-milestones)
15. [Communication and Collaboration](#15-communication-and-collaboration)
16. [Documentation](#16-documentation)
17. [Legal and Compliance](#17-legal-and-compliance)
18. [Review and Approval](#18-review-and-approval)

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
4. **Presentation Link:**
   - [Figma Presentation](https://www.figma.com/proto/iMbZroTCQ2LXOcntrK7icS/Warehouse?type=design&node-id=0-1&t=nZjCDZjRCMFoUo6u-0&scaling=scale-down&page-id=0%3A1&starting-point-node-id=21%3A6)

## 2. Project Scope

The project scope outlines the functionalities that will and will not be included in the Android Warehouse Chemical Monitoring Application. The application is designed to cater to three distinct roles: Admin, User, and WH Manager.

### 2.1 Inclusions:

#### Admin:
- Administrative dashboard with access to all functionalities.
- User management, including the addition, modification, and removal of users.
- Chemical management, including the addition, modification, and removal of chemicals. Overview of all chemical transactions.
- Specifying chemical "storage conditions"

#### User:
- Ability to log the taking of chemicals, specifying the chemical, and quantity, and setting the "needed" period and timestamp. If a chemical has "special storage conditions e.g. "under argon" or "at -20deg," this warning will be shown on the screen.
- Ability to log the returning of chemicals, specifying the chemical, quantity, and timestamp
- Receive email notifications if chemicals are not returned by the set "needed" period.

#### WH Manager:
- Access to detailed reports, including information on who took chemicals, when they were taken, when they were returned, and the remaining quantity.
- Capability to request reports for specific time periods or chemical types.
- Chemical management, including the addition, modification, and removal of chemicals. Overview of all chemical transactions.
- Specifying chemical "storage conditions"

### 2.2 Exclusions:

- **Financial Transactions:**
  - The application will not handle financial transactions related to chemical usage.

- **Inventory Management:**
  - Beyond tracking quantities taken and returned, the application will not handle general inventory management tasks.

- **Real-time Monitoring:**
  - While the application provides real-time tracking of chemical transactions, it does not support continuous monitoring during the day.

- **Chemical Ordering:**
  - The application will not include features related to ordering new chemicals or managing chemical supply chains.

### 2.3 Additional Considerations:

- The application will prioritize simplicity and user-friendliness to ensure ease of use for all roles.
- Security measures will be implemented to safeguard sensitive information.
- Data privacy and compliance with relevant regulations will be integral to the application's design.

This scope sets clear boundaries for the features and functionalities of the Android Warehouse Chemical Monitoring Application, focusing on the essential tasks of tracking chemical transactions and generating relevant reports for effective warehouse management.

### 3. Objectives

- **Efficiency Improvement:**
  - Replace traditional paper logbooks with a digital solution to streamline and enhance the monitoring of chemicals in warehouses.

- **Real-time Data Access:**
  - Enable real-time access to critical information, reducing manual effort and improving decision-making processes.

- **User-Friendly Interface:**
  - Develop an intuitive Android application that simplifies the process of logging, tracking, and managing chemicals.

### 4. Need for the Application

The need for this application arises from the limitations of traditional paper-based logbooks, which are often time-consuming, prone to errors, and lack real-time accessibility. The Android Warehouse Chemical Monitoring Application aims to overcome these challenges by providing a digital platform that ensures efficient tracking, secure communication, and centralized data management.

This introduction sets the stage for the subsequent sections, outlining the scope, functionalities, and technical aspects of the Android warehouse chemical monitoring application.

### 5. User Stories and Use Cases

#### **5.1 Take from Storage:**

1. **Login:**
   - As a user, I want to launch the application, log in with my username (auto-completion available), and enter my password for secure access.

2. **Take from storage:**
   - As a user, after logging in, I want to click the "Take from Storage" button to initiate the process of acquiring chemicals.

3. **Enter Chemical Details:**
   - As a user, during the "Take from Storage" process, I want to enter (or scan, in the next updates) the internal code, CAS, or name of the chemical.

4. **Confirm withdrawal:**
   - As a user, after entering the chemical details, I want to click the "Confirm" button to request the specified chemical.

5. **Feedback:**
   - As a user, I expect to receive a success or failure message indicating the result of my request, amount of substance mass, or volume should be visible.

6. **Internal Code and CAS Linkage:**
   - As a system requirement, the internal code, name, and CAS should be interconnected to ensure accurate tracking and identification of chemicals.

#### **5.2 Return To Storage:**

1. **Login:**
   - As a user, I want to launch the application, log in with my username (auto-completion available), and enter my password for secure access.

2. **Initiate Return To Storage Process:**
   - As a user, after logging in, I want to click the "Return To Storage" button to initiate the process of returning chemicals.

3. **View Taken Chemicals:**
   - As a user, during the "Return To Storage" process, I want the application to display a list of chemicals previously taken by me.

4. **Return Chemicals:**
   - As a user, for each chemical displayed, I want to click on a specific chemical, enter the quantity in mL or g that I am returning, and click the "Proceed" button.

5. **Confirm**
   - As a user, I will be redirected to the page for final confirmation. On this page, I'll be able to see the substance, used amount, and other relevant information, and after checking I will click the "Confirm" button to finalize the return.
     
7. **Feedback:**
   - As a user, I expect to receive a success or failure message indicating the result of my return request.

#### **5.3 Check My History:**

1. **Login:**
   - As a user, I want to launch the application, login with my username (auto-completion available), and enter my password for secure access.

2. **View Taken Chemicals:**
   - As a user, during the "Check my history" process, I want the application to display a list of chemicals previously taken, not returned by default. This list should include chemicals taken by me. A list of all previously taken and returned chemicals is also should be visible. Sorting by date. 

3. **Sorting and Scrolling:**
   - As a user, I expect the displayed list to be ordered by taking date, from the earliest to the latest. Additionally, the list should support scrolling for ease of navigation through multiple entries.

#### **5.4 View Logs for WH Manager:**
1. **Login:**
   - As a WH manager, I want to launch the application, login with my username (auto-completion available), and enter my password for secure access. I will be redirected to the WH initial screen.
2. **View WH Logs**
   - I click WH Logs Button, and will be redirected to WH Logs page, where I can search by WH code, CAS, subname, and User name. I can see who took the substance, who returned it, the amount, and the date.
     
#### **5.5 View Warehouse:**
1. **Login:**
   - As a WH manager, I want to launch the application, login with my username (auto-completion available), and enter my password for secure access. I will be redirected to the WH initial screen.
2. **View WH** 
   - By clicking the button "warehouse" I will be redirected to the WH page. Here I have the list of all chemicals, I can search for a chemical by CAS, WH code or name, and I see how many chemicals remain and how much is taken.
3. **Info about chemical**
   - After clicking the "info" button I will be redirected to the Info page, where I can see all current information about the given chemical, who and when took it, how much was taken every time, and how much is remaining.

#### **5.6 Edit Chemical:**
1. **Login:**
   - As a WH manager, I want to launch the application, login with my username (auto-completion available), and enter my password for secure access. I will be redirected to the WH initial screen.
2. **View WH** 
   - By clicking the button "warehouse" I will be redirected to the WH page. Here I have the list of all chemicals, I can search for a chemical by CAS, WH code or name, and I see how many chemicals remain and how much is taken.
3. **Select a row with the Chemical**
   - By clicking the row with the chemical that needs to be edited, I can select it.
3. **Edit Chemical**
   - By clicking the "Edit" button, I will be redirected to the page, where I can edit or delete existing chemicals.
   - After Editing I will be redirected to the confirmation page, where I can see the changes done and after reviewing them I can confirm the change.
   - After pressing the "confirm" button I will be redirected to the feedback page, where I receive a message about successful editing.

#### **5.7 Delete Chemical:**
1. **Login:**
   - As a WH manager, I want to launch the application, login with my username (auto-completion available), and enter my password for secure access. I will be redirected to the WH initial screen.
2. **View WH** 
   - By clicking the button "warehouse" I will be redirected to the WH page. Here I have the list of all chemicals, I can search for a chemical by CAS, WH code, or name, and I see how many chemicals remain and how much is taken.
3. **Select a row with the Chemical**
   - By clicking the row with the chemical that needs to be edited, I can select it.
3. **Delete Chemical**
   - By clicking the "Edit" button, I will be redirected to the page, where I can edit or delete existing chemicals.
   - After Editing I will be redirected to the confirmation page, where I can see the changes that have been done and after reviewing them I can confirm the change.
   - After pressing the "delete" button I will be redirected to the feedback page, where I receive a message about successful deletion.

#### **5.8 View Taken Chemicals for WH manager:**
1. **Login:**
   - As a WH manager, I want to launch the application, login with my username (auto-completion available), and enter my password for secure access. I will be redirected to the WH initial screen.
2. **View Taken Chemicals for WH manager:** 
   - As a user, during the "View Taken Chemicals" process, I want the application to display, by default a list of all chemicals previously taken, and not returned, the list can be sorted by time or user. This list should include chemicals taken by all users, or a specific chemical searched by internal code, CAS, or name. A list of all previously taken chemicals is also should be visible, the list can be sorted by time or user.
   - To notify the User about the chemicals taken, press the "send notification" button and compose a message.  

#### **5.9 Register chemicals to the Data Base for WH manager:**
   - As a WH manager, I want to launch the application, login with my username (auto-completion available), and enter my password for secure access.
   - Next, I want to click the "Register" button and will be redirected to the register page.
   - There I see multiple input fields, I need to input CAS number, Mr Formula, Chemical name, Amount, and units. Next, I want to click the "Continue" button, and I will be redirected to the next registration page, where I can input additional data.
   - After clicking the "Continue" page, I will be redirected to the second registration page, where I can input storage conditions and other Special conditions. After it is done, I can press the "confirm" button and will get feedback upon successful or failed operation.

#### **5.10 Changing and assigning new roles for user:**
   - As an Admin, I want to launch the application, login with my username (auto-completion available, login and password will be pre-defined), and enter my password for secure access
   - I can click the button "Account Management" on the initial screen.
   - I will be redirected to the page "account management", where I see a search field and I can search users by name.
   - After finding a user, I can choose a new role for him and I can press the "confirm" button and get feedback upon successful or failed operation.

## 6. Functional Requirements
**Comprehensive Search:**
   - As a user, I want the ability to search for specific chemicals using internal code, CAS, or name, ensuring a comprehensive and efficient search functionality.
**User-Friendly Interface:**
   - As a user, I expect the user interface to be intuitive and user-friendly, facilitating easy navigation and understanding of the logged chemical transactions.
List and describe the essential features and functionalities of the application:

### 6.1 Chemicals Logging
- **Description:** Users should be able to log the taking and returning of chemicals, providing details such as CAS number, WH code, chemical name type, quantity, units, and timestamp.
- **User Roles:** User.

### 6.2 Transaction Tracking
- **Description:** The system must track all chemical transactions, including details on who took the chemicals, when they were taken, when they were returned, and the quantity involved.
- **User Roles:** User, WH Manager.

### 6.3 User Authentication
- **Description:** Secure authentication mechanisms should be implemented to ensure that only authorized users (Admin, User, WH manager) can access the application.
- **User Roles:** All roles (Admin, User, WH Manager)

### 6.4 Code Scanning
- **Description:** The application should support barcode scanning or QR code scanning to streamline the logging process.
- **User Roles:** All roles (Admin, User, WH Manager) /*Comment from DV - I have doubts about the above task, it is not so easy to implement and requires knowledge of some 3rd party applications*/ /*Comment from YP it is not obligatorily and we can scan only digital number like 0000-0/0-000*/
  /*Under consideration*/

### 6.5 Reporting
- **Description:** Users, especially WH Managers, should have access to detailed reports on chemical transactions, indicating who took chemicals, when they were taken, when they were returned, and the remaining quantity.
- **User Roles:** WH Manager

### 6.6 User Roles and Permissions
- **Description:** Different roles (Admin, User, WH Manager) will have distinct permissions to ensure appropriate access levels for each user type.
- **User Roles:** Admin, User, WH Manager

## 7. Non-Functional Requirements
Specify non-functional aspects such as:
- **Performance Expectations:**
  - The application should load within 3 seconds on average on standard internet connections.
  - Response times for critical operations (such as login, search, and data retrieval) should be less than 1 second.
  - The system should be able to handle concurrent requests from multiple users without significant degradation in performance.
  - Database queries should be optimized to ensure efficient data retrieval.
- **Security measures (encryption, secure authentication)**
- During registration, all users are assigned the role "guest" and only the admin can assign a new role for a new user (such as "user" or "WH manager").
- The "guest" role has no access to the platform.
- **Compatibility with Android Devices:**
  - The application's user interface should be responsive and optimized for various screen sizes commonly found in Android devices, including smartphones and tablets.
  - All core functionalities of the application should be fully accessible and functional on Android devices, ensuring a seamless user experience across different devices and screen resolutions.
  - Compatibility testing should be conducted on a range of Android devices and operating system versions to identify and address any compatibility issues.
  - The application should adhere to Android design guidelines and best practices to ensure consistency and familiarity for Android users.
___________ to be added soon ____________________
## 8. Technical Stack
Specify the technology stack:
- Programming Language: Kotlin
- Development Framework: Android SDK
- Database: SQLite or Room Database
- Third-party Libraries: If any (e.g., barcode scanning libraries)

## 9. Database Design
Outline the database structure, including tables and relationships:
- Chemicals Table
- Transactions Table
- Users Table

## 10. UI/UX Design
Describe the expected user interface and user experience, including:
- Screens and navigation flow
- Input forms
- Dashboard and reporting layouts
- Search bar with possibilities to search by Name, CAS, WH code.
- Filters (by project, storage condition, date)

## 11. Security Considerations
Identify potential security risks and outline measures to secure the application and its data.

## 12. Integration
Specify integration requirements, if any:
- A plugin to fetch all convenient names of chemicals by their CAS number (written in Python or another language). I will use JSON to communicate with the app.
- Barcode scanner integration /*Under consideration*/
- User authentication integration

## 13. Testing Plan
Define a comprehensive testing plan:
- Unit testing for individual components
- Integration testing for combined functionalities
- User acceptance testing

## 14. Timeline and Milestones
Establish a timeline for the development process:
- Milestone 1: Database design and setup
- Milestone 2: UI/UX design and basic functionality implementation
- Milestone 3: Integration and testing
- Milestone 4: Final testing and debugging
- Milestone 5: Deployment and post-launch support

## 15. Communication and Collaboration
Specify communication tools and channels for effective collaboration:
- Project management platform (e.g., Jira)
- Regular meetings (weekly or bi-weekly)

## 16. Documentation
Emphasize the importance of documentation:
- Code documentation
- User manuals
- Technical documentation for maintenance

## 17. Legal and Compliance
Ensure compliance with relevant laws and regulations.

## 18. Review and Approval
Define a process for regular reviews and approvals from stakeholders:
- Regular demo sessions
- Stakeholder feedback sessions
