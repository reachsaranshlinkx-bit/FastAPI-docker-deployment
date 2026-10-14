# FastAPI Docker Deployment

A backend application built with **FastAPI**, featuring REST API development, database integration, authentication, Docker containerization, and cloud deployment fundamentals.

This project is part of my journey toward building reliable, production-ready backend systems and AI-powered applications.

## Overview

This repository contains a Python backend application designed to demonstrate API development, application configuration, database management, and deployment workflows.

The project uses a modular structure to separate API routes, database models, validation schemas, authentication, and supporting utilities.

## Tech Stack

- **Python** — Backend development
- **FastAPI** — REST API framework
- **Pydantic** — Data validation and schemas
- **SQLAlchemy / Database Integration** — Database operations
- **Alembic** — Database migrations
- **uv** — Python dependency and project management
- **Docker** — Application containerization
- **AWS S3** — Cloud storage integration
- **HTML, CSS, and JavaScript** — Static assets and templates

## Features

- Modular API routing
- Authentication functionality
- Database models and schema validation
- Database migration management with Alembic
- Image-related utilities
- AWS S3 integration
- Email utility functions
- Static files and HTML templates
- Docker-based deployment setup
- Test directory for application testing

Some features may require additional environment configuration before they can be run locally.

## Project Structure

```text
FastAPI-docker-deployment/
├── alembic/             # Database migrations
├── populate_images/     # Image-related project assets
├── routers/             # API route modules
├── static/              # Static assets
├── templates/           # HTML templates
├── tests/               # Application tests
├── .dockerignore        # Files excluded from Docker builds
├── .gitignore           # Files excluded from Git
├── alembic.ini          # Alembic configuration
├── auth.py              # Authentication logic
├── check_s3.py          # S3 integration utilities
├── config.py            # Application configuration
├── database.py          # Database configuration
├── Dockerfile           # Docker image configuration
├── email_utils.py       # Email utilities
├── image_utils.py       # Image utilities
├── main.py              # Application entry point
├── models.py            # Database models
├── populate_db.py       # Database population utilities
├── pyproject.toml       # Project metadata and dependencies
├── schemas.py           # Data validation schemas
└── uv.lock              # Locked dependency versions
```

## Getting Started

### Prerequisites

Install the following tools before running the project:

- Python version supported by the project
- [uv](https://docs.astral.sh/uv/)
- [Docker](https://www.docker.com/) (for containerized execution)

### 1. Clone the repository

```bash
git clone https://github.com/reachsaranshlinkx-bit/FastAPI-docker-deployment.git
cd FastAPI-docker-deployment
```

### 2. Install dependencies

```bash
uv sync
```

### 3. Configure environment variables

Create a local `.env` file containing the environment variables required by `config.py` and the application.

Use your own credentials and local configuration. Never commit `.env` or expose API keys, passwords, or AWS credentials.

### 4. Run the application

```bash
uv run uvicorn main:app --reload
```

If the application starts successfully, open:

- API: http://127.0.0.1:8000
- Interactive API documentation: http://127.0.0.1:8000/docs
- Alternative API documentation: http://127.0.0.1:8000/redoc

These addresses assume the application uses the standard Uvicorn configuration and the default port.

### 5. Run database migrations

After configuring the database connection, apply migrations if required:

```bash
uv run alembic upgrade head
```

## Docker

Build a Docker image from the project directory:

```bash
docker build -t fastapi-docker-deployment .
```

Run the container:

```bash
docker run --env-file .env -p 8000:8000 fastapi-docker-deployment
```

The container command, port, and required environment variables must match the project's `Dockerfile` and configuration.

## Security

- Keep `.env` and all credentials out of version control.
- Never commit AWS access keys or secret keys.
- Do not upload local virtual environments or generated cache files.
- Review permissions before using AWS bucket or IAM policies.
- Configure production secrets through an appropriate secrets-management mechanism.

## Learning Objectives

This project provides practical experience with:

- Python backend engineering
- REST API development
- Database integration and migrations
- Dependency management
- Application configuration
- Docker containerization
- Cloud storage integration
- Deployment fundamentals

## Future Improvements

- Add and expand automated tests.
- Document API endpoints and example requests.
- Add continuous integration checks.
- Improve application logging and error handling.
- Deploy the containerized application to a cloud environment.
- Add health checks and production monitoring.

## License

This project is intended for learning and portfolio development. A license has not yet been specified.

---

**Author:** Saransh Soni

**GitHub:** [reachsaranshlinkx-bit](https://github.com/reachsaranshlinkx-bit)
