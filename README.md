# Developing a Containerized Soccer Stats Application 

## This project implements a containerized soccer statistics application using Docker, Python (with FastAPI for efficient request handling) and the Football API

# Technical Diagram
![sportsapi drawio](https://github.com/user-attachments/assets/c035c5a3-b052-423c-ad8a-a431b852dca4)


## Project Structure
    soccer-stats-docker/
    ├── src/
    │   ├── __init__.py
    │   └── soccer_stats.py
    ├── tests/
    │   └── test_soccer_stats.py
    ├── Dockerfile
    ├── requirements.txt
    └── .env


# Workflow

- The Client sends an HTTP request to the FastAPI application hosted within a Docker container. 

- The FastAPI Application receives the request, processes it, and determines the necessary data to fetch from the external Football API.

- The application makes a request to the Football API to retrieve the relevant soccer statistics.

- Upon receiving the data, the FastAPI application processes it as needed and sends the response back to the Client.

#cTechnology stack 
- Docker
- Python/FastAPI
- Soccer API (api-football-v1.p.rapidapi.com)
- pytest for testing
  
# Setup Instructions
1. Clone the repository
   git clone 
