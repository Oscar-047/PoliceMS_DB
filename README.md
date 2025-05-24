# Project Overview
PoliceMS_DB is a centralized police management system designed to streamline law enforcement operations, including crime tracking, officer deployment, case monitoring, and resource management.

#  Group Member
Name:IRADUKUNDA Oscar
Student ID: 26281
Group:Monday

# Problem Statement
Police departments often struggle with fragmented and inefficient information systems. Our solution introduces a centralized Oracle PL/SQL-based database that enhances case tracking, officer management, and resource coordination.

# Objectives
Improve response time with real-time data access.
Automate case and resource management.
Enforce secure and structured workflows using PL/SQL.
Enable auditing, restriction controls, and reporting.


//BUsiness_process_Modeling

# Business Process Modeling – MIS

![BPMN image](https://github.com/user-attachments/assets/ff4bf02b-8085-4e00-9895-2432ef444b32)


# Scope

This business process represents the flow of crime reporting, case assignment, and investigation in a police department. It reflects how information systems can support decision-making and improve response coordination.

#  Key Entities and Actors

  Citizen: Reports a crime to the authorities.
  Dispatch Officer: Logs reports, assesses urgency, and dispatches the response team if needed.
  Case System: Automatically creates and tracks the case.
  Investigating Officer: Handles the case investigation process from start to end.

# Process Explanation (Based on Diagram)

1. Report Crime (Citizen)  
   Citizens initiate the process by reporting crimes.

2. Log the Report (Dispatch Officer)  
   The officer logs the case and checks if it’s an emergency.

3. **Emergency Check**  
   - If Yes, a response team is dispatched.
   - If No, the process continues for routine case handling.

4. Response Given 
   An appropriate initial response is delivered based on situation severity.

5. Create Case Record (Case System)  
   A new case is registered in the system.

6. Assign an Officer  
   An investigating officer is assigned to the case.

7. Review & Investigate (Investigating Officer)  
   The officer:
   - Reviews the case,
   - Investigates the crime,
   - Identifies suspects/victims,
   - Collects evidence,
   - Submits the final report.

8. Update Case Status (Case System)  
   Once complete, the case is marked as closed in the system.

# MIS Value

Improves Decision-Making: Prioritizes emergencies and allocates resources quickly.
Streamlines Operations: Automates assignment and documentation.
Enhances Transparency: Every actor’s role and data interaction is recorded and trackable.

# Tools Used

- Diagram created using BPMN tools (Lucidchart / draw.io).

  //LOGICA_MODEL_DESIGN

  # Phase 3: Logical Model Design

![logical model design](https://github.com/user-attachments/assets/bf4b15cc-836f-4661-a263-3135ad19690d)

## Objective
This phase presents the logical data model for the PoliceMS_DB system, aligning with the problem statement and business process from Phases 1 and 2. It defines all necessary entities, relationships, keys, and constraints based on real-world law enforcement operations.



## Entities and Attributes

### 1. Officers
- officer_id (PK, int)
- name (varchar)
- rank (varchar)
- phone (varchar)
- email (varchar)

### 2. Crimes
- crime_id (PK, int)
- crime_type (varchar)
- date_reported (date)
- location (varchar)
- description (text)

### 3. Cases
- case_id (PK, int)
- case_status (varchar)
- opened_on (date)
- closed_on (date)
- officer_id (FK → Officers.officer_id)

### 4. Suspects
- suspect_id (PK, int)
- name (varchar)
- dob (date)
- address (varchar)

### 5. Victims
- victim_id  (PK, int)
- name (varchar)
- dob (date)
- address  (varchar)

### 6. Resources
- resource_id (PK, int)
- resource_type (varchar)
- assigned_to (int)
- status (varchar)

---

## Relationship Tables

### Case_Crime
- case_id (FK)
- crime_id (FK)
- Composite PK: (case_id, crime_id)

### Case_Suspect
case_id (FK)
suspect_id (FK)
Composite PK: (case_id, suspect_id)

### Case_Victim
- case_id (FK)
- victim_id (FK)
- Composite PK: (case_id, victim_id)

---

## Relationships & Constraints

- **One-to-Many**: Officers → Cases
- **Many-to-Many**:
  - Cases ↔ Crimes (via Case_Crime)
  - Cases ↔ Suspects (via Case_Suspect)
  - Cases ↔ Victims (via Case_Victim)
- **Constraints**:
  - PKs defined on all main tables
  - Composite PKs on junction tables
  - FKs enforce referential integrity
  - Fields like email, phone, status expected to use constraints such as NOT NULL, CHECK, and/or UNIQUE where applicable (to be handled in physical design)



# Normalization

 All tables are in **3NF**:
 No repeating groups
 All non-key attributes are fully functionally dependent on the primary key
 No transitive dependencies

-

# Data Handling

The model supports:
Multiple suspects/victims per case
Shared crimes across cases
Assignment of officers and resources
Accurate tracking of case progress and entity relationships


// Phase_4_Database_Creation

# Phase 4: Database Creation and Naming

In this phase, a pluggable Oracle database was created and configured to support the PoliceMS_DB system. The database creation followed the project naming convention and included full user access privileges.


<img width="345" alt="Image" src="https://github.com/user-attachments/assets/a87278fe-e976-4739-94b0-f95a5d226f69" />


# Tasks Completed

#1. Pluggable Database Creation

A pluggable Oracle database was created using the naming format:

monday_26281_oscar_policeBD_db

- Admin User: iradukunda
- Password: Oscar
- Structure: File directories were specified via `FILE_NAME_CONVERT`.



# 2. Session Configuration and User Privileges

- The session container was set to the newly created pluggable database.
- A user `Oscar` was created and granted **all privileges**.


## 3. Table Creation Verification

After connecting to the database via Oracle SQL Developer, all necessary tables were created and verified.

**Created Tables:**
- CASE_CRIME
- CASE_SUSPECT
- CASE_VICTIM
- CASES
- CRIMES
- OFFICERS
- RESOURCES
- SUSPECTS
- VICTIMS

## Access & Management

All activities and data operations throughout the project were stored in this database. This setup ensures a centralized, secure, and manageable data environment.




