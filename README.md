# Salon Appointment System
This project implements a simple salon appointment system with functionalities to manage customers, services, and appointments.

## Features Implemented
### Database Setup:
    - Created a PostgreSQL database named salon.
    - Established tables: customers, appointments, and services.
    - Each table includes a primary key (table_name_id) that auto-increments.

### Table Relationships:
    - `appointments` table includes:
    - `customer_id` foreign key referencing customers.customer_id.
    - `service_id` foreign key referencing services.service_id.

### Table Specifications:
    - `customers` table: phone (VARCHAR, unique) and name columns.
    - `services` table: name column to list different services.
    - `appointments` table: time column (VARCHAR) for appointment timing.
    - Predefined Data: services table populated with at least three rows for different services.

### Script Implementation (salon.sh):
Bash script with executable permissions (#!/bin/bash).
Does not use clear command.
Displays a numbered list of services offered before user input.
Prompts user for:
    service_id selection.
    phone number.
    name (if new customer).
    time for appointment.
Handles cases for existing and new customers based on phone number input.

Output: Upon successful appointment booking, outputs: "I have put you down for a <service> at <time>, <name>."

### Usage:
1. Give permissions to execute
```sh
chmod +x salon.sh
```
2. Run the script
```sh
./salon.sh
```
#### Example test:
Create a row in the appointments table by running your script and entering:
```sh
1
555-555-5555
10:30
``` 
At each request for input if that phone number isn’t in the customers table. 
The row should have the customer_id for that customer, and the service_id for the service entered

Create another row in the appointments table by running your script and input:
```sh
2
555-555-5555
11am 
```
At each request for input if that phone number is already in the customers table.
The row should have the customer_id for that customer, and the service_id for the service entered.