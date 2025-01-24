## Voting Application - Kubernetes Project

This repository contains a microservices application designed to demonstrate the use of Kubernetes for deploying and managing a multi-component solution. The application allows users to vote between two options (a cat or a dog) and see the results in real-time. It leverages various technologies to simulate a production-like environment.

## Application Architecture

1. vote-app (Frontend)
Web application developed in Python.
Provides a user-friendly interface for selecting a vote (cat or dog).
Sends votes to Redis, which acts as an in-memory database.
2. Redis
In-memory database used to temporarily store user votes.
Serves as a bridge between the frontend application and the vote processor.
3. worker
Application developed in .NET Core.
Processes votes stored in Redis and transfers them to the persistent database (PostgreSQL).
Ensures that votes are saved for future reference.
4. db (Database)
Persistent database using PostgreSQL.
Stores vote results in a durable manner.
5. result-app (Results Backend)
Web application developed in Node.js.
Reads vote results from the database and displays them to users in real-time.
Provides a dynamic and live view of the voting process.

## Kubernetes Resources

The project uses the following Kubernetes resources to deploy and manage the application components:

Deployments
redis: Deploys a pod for in-memory storage.
db: Deploys a pod with PostgreSQL for persistent storage.
vote-app: Deploys a pod for the frontend voting application.
worker: Deploys a pod for vote processing.
result-app: Deploys a pod for displaying vote results.
Services
redis: Exposes the Redis service for access by other components.
db: Exposes the PostgreSQL service for persistent data access.
vote-app: Exposes the frontend application for user access.
result-app: Exposes the results service for user access.

## Technologies Used

Kubernetes: Management and orchestration of microservices.
Python: Frontend development.
Redis: In-memory storage for temporary data.
.NET Core: Vote processor development.
PostgreSQL: Persistent database.
Node.js: Backend development for vote results.

## Project Goals

Demonstrate skills in microservices development and deployment.
Showcase efficient use of Kubernetes resources like Deployments and Services.
Integrate multiple technologies to create a fully functional solution.
