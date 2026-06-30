# Architecture
![System architecture](diagrams/system-architecture.png)
This diagram shows the planned high-level data flow between the ESP32, backend, database and frontend

## Purpose
The purpose of the system is to collect environment-/sensordata. This data can later be used as part of energy measurement system however this might require additional hardware or an external data source.

## System Context
User
- Home owner interacting with the system
Home environment
- Has sensors that measures data
Smart Home Energy System
- Handles, stores and communicates data

## Main Components
Frontend
- Shows dashboard
Backend
- Receives data and sends it forward
Database
- Stores data
ESP32-program
- Measures sensor data and sends it

## Data Flow
Measurement flow:
ESP32 -> Backend -> Database

Display flow:
Frontend -> Backend -> Database > Backend -> Frontend

ESP32 -> Backend:
measurements from sensors, device id, timestamp

Backend -> Database:
validated measurement data
 
Frontend -> Backend:
requests for values

Backend -> Frontend:
values for dashboard

## Key Design Decisions

## Assumptions
- The ESP32 will send sensor readings to the backend.
- The backend will be responsible for storing data.
- The frontend will not communicate directly with the database.
- Energy usage may require additional hardware or an external data source.

## Open Questions
- Should the ESP32 communicate with the backend using HTTP or MQTT?
- Should the backend run locally or in the cloud?
- Which database should be used?
- Should the frontend show live values or historical values?

## What i dont understand
I dont know fully what MQTT is and how it works.