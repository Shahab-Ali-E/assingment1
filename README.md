# FastAPI with PostgreSQL Docker Setup

This project uses Docker Compose to set up a FastAPI CRUD application with a PostgreSQL database. This README outlines the steps to build the Docker images and run the services.

## Docker Compose File

The `docker-compose.yml` file defines two services: `db` for PostgreSQL and `app` for the FastAPI application. Below is a brief description of each service:

- **db**: 
  - Uses the official PostgreSQL image (`postgres:16.4`).
  - Configures the database with environment variables for the user, password, and database name.
  - Exposes port `5432`.

- **app**:
  - Builds the FastAPI application using the Dockerfile in the current directory (`build: .`).
  - Exposes port `8000`.
  - Depends on the `db` service to ensure the database is available before starting the application.

## Build and Run

Follow these steps to build the images and run both services:

1. **Open your terminal** and navigate to the root directory of your project (where your `docker-compose.yml` file is located).

2. **Build the Docker images** using the following command:

   ```bash
   docker-compose up --build
    ```
3. **To see the logs of fastapi server** using the following command:    

    ```bash
    docker logs <container_id>
    ```