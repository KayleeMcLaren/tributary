# Ford Digital Advanced Job Simulation - Backend Provisioning

This repository contains a backend service created for the **Ford Digital Advanced Job Simulation**, an online exercise completed through Forage.com. This job simulation aimed to provide hands-on experience with building a backend system to bridge live vehicle data from car sensors with a mobile application. **This was not a real-world project but a simulated environment designed for learning purposes.**

## Project Overview

The goal of this simulation was to create a backend service as part of a fictional system for Ford, designed to enhance driver access to real-time vehicle data. This backend service was intended to act as the intermediary between:
- **Vehicle sensors**: Simulated data sources collecting information like engine temperature.
- **Mobile application**: Allowing drivers to monitor simulated real-time data from their vehicles.

### Simulation Objective

The task involved setting up a backend Flask-based service that connects to a Redis database to:
- **Store** simulated incoming sensor data (e.g., engine temperature).
- **Serve** stored data, including current and average values, to the simulated mobile app upon request.
  
---

## Project Files

### 1. Dockerfile

The `Dockerfile` defines the environment to build and run the backend application using Python 3.11, Flask, Redis, and other dependencies.

### 2. docker-compose.yml
The `docker-compose.yml` file is used to manage multi-container deployment, setting up the backend service (tributary) and a Redis instance.

### 3. entrypoint.py
`entrypoint.py` houses the core Flask application, containing two endpoints:

* `/record` - Records simulated engine temperature data from incoming POST requests.
* `/collect` - Returns the current and average simulated engine temperatures to the mobile app.

### 4. requirements.txt
Lists all necessary dependencies for the project.

---

## Setup and Installation

### 1. Clone the repository:
`git clone <repository-url>` <br/> 
`cd <repository-directory>`

### 2. Build and Run with Docker Compose:
`docker-compose up --build`
This command sets up the Flask server and the Redis instance.

### 3. Test the Endpoints:
* Record Endpoint: Send a `POST` request to `/record` with JSON data (e.g., `{"engine_temperature": 85}`).
* Collect Endpoint: Send a `POST` request to `/collect` to retrieve the current and average simulated engine temperatures.

---

## Usage
* `/record` - Accepts JSON payloads to record simulated engine temperature data.
* `/collect` - Provides current and average simulated temperature values, supporting real-time analysis in the mobile app.

---

## Conclusion
This backend provisioning project was part of a simulated job experience designed to provide hands-on practice with building a data streaming backend, managing Redis for in-memory storage, and deploying containerized services. This exercise provided a foundational understanding of backend integration, containerization, and data management for live vehicle telemetry.
