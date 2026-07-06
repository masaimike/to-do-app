# To-Do List App

A simple to-do list web application built with Flask and SQLite, containerized with Docker. This project was built as a hands-on learning exercise covering Linux, Git/GitHub, Docker, and Docker Compose.

## Features

- Add tasks to a to-do list
- View all tasks
- Delete tasks
- Data persists across container restarts using a Docker named volume

## Tech Stack

- **Backend**: Python, Flask
- **Database**: SQLite
- **Containerization**: Docker, Docker Compose

## Project Structure

```
todo-app/
├── app.py               # Flask application and routes
├── requirements.txt     # Python dependencies
├── templates/
│   └── index.html       # Main page template
├── Dockerfile           # Container build instructions
├── docker-compose.yml   # Multi-container orchestration
└── .gitignore
```

## Running Locally (without Docker)

1. Install dependencies:
   ```
   pip install -r requirements.txt
   ```
2. Run the app:
   ```
   python app.py
   ```
3. Open your browser to `http://localhost:5000`

## Running with Docker Compose (recommended)

1. Make sure Docker Desktop is installed and running.
2. Build and start the container:
   ```
   docker-compose up
   ```
3. Open your browser to `http://localhost:5000`
4. To stop the app:
   ```
   docker-compose down
   ```

Your tasks are stored in a Docker named volume (`todo-data`), so they'll still be there the next time you run `docker-compose up`, even if the container is removed and recreated.

## Running with Docker (manual, without Compose)

```
docker build -t todo-app .
docker run -p 5000:5000 -v todo-data:/app/data todo-app
```

## What I Learned Building This

- Setting up and running Flask applications
- Git basics: commits, branches, pull requests, and merging
- Writing a Dockerfile and understanding image layers
- Why containers are ephemeral, and how Docker volumes solve data persistence
- Using Docker Compose to manage multi-container setups from a single config file

## Roadmap

- [ ] Add a Postgres database service via Docker Compose
- [ ] Deploy to an AWS EC2 instance
- [ ] Add a basic CI pipeline with GitHub Actions
