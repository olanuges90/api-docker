# Deploying a Containerized Soccer Stats Tracker 

## This project implements the seamless deployment of a containerized soccer statistics tracker with FastAPI - a Lighting fast Python Framework, Docker and RapidAPI.

# Technical Diagram
![sportsapi drawio](https://github.com/user-attachments/assets/c035c5a3-b052-423c-ad8a-a431b852dca4)


# Project Structure
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

# Technology stack 
- Docker - Containerization.
- Python (FastAPI) -  API development
- Soccer API - external soccer data (api-football-v1.p.rapidapi.com)
- pytest for testing
- Web App/Postman - Client-side testing or UI


# Prerequisite
1. Create an account on RapidAPI. 
2. Search for Football API within the RapidAPI marketplace and select.
3. Click Subscribe to Test
4. Retrieve your RapidAPI key and save for future use.
   
# Setup Instructions
## 1. Clone the Repository

Clone your Github repository into your local machine
   
```sh
git clone https://github.com/olanuges90/api-docker
cd api-docker
```
## 2. Environmental Variable
   
   Create a .env file and Replace the variable with your RapidAPI Key. Echo the .env file into your .gitignore to secure your RapidAPI key
```sh
RAPID_API_KEY="your_api_key_here"
```
## 3.  Build and Run the Docker Image

Build the Docker image
```sh
docker build -t soccer-stats .
```
Run the Docker Container
```sh
docker run -p 8000:8000 --env-file .env soccer-stats
```
## 4. Test the API
Navigate to your web browser and paste the url below in your search bar
```sh
http://127.0.0.1:8000
```
- Alternatively, use Postman to interact with the API endpoints. 

## API endpoints
- / - Welcome message and available endpoints
- /health - Health check endpoint
- /player/{player_id} - Get player statistics
- /topscorers/{league_id} - Get top scorers for a league (default: Premier League)

## 5. Resources Clean up
Stop the container
```sh
docker stop $(docker ps -q --filter ancestor=soccer-stats)
```
Remove the container
```sh
docker rm $(docker ps -aq --filter ancestor=soccer-stats)
```
Remove the image
```sh
docker rmi soccer-stats
```
Remove all unused containers, networks, images (use with caution)
```sh
docker system prune
```
## What we Learnt
1. Learn how to containerize a Python application using Docker 
2. Build a RESTful API using FastAPI and Handle HTTP requests, process data, and return responses efficiently
3. Learn to handle API authentication, request formatting, and response parsing.
4. Process JSON data from an external API.
5. Format and structure data for better usability in front-end applications.

##  Future Enhancement
1. Frontend Dashboard to visualize team and player statistics
2. Multi-API Integration
