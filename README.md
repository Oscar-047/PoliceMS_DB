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


