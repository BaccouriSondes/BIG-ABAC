# Emergency Access POC

This project demonstrates an Emergency Access Proof of Concept using NestJS and various Docker services.

## Tech Stack

- NestJS
- Docker

## Prerequisites

- Docker and Docker Compose
- Node.js (version 22.4.1)
- ASDF (recommended for Node.js version management)

## Setup

### 1. ASDF Setup (Recommended)

ASDF is used for managing the Node.js version. To set it up:

1. Install ASDF by following the instructions at: https://asdf-vm.com/guide/getting-started.html
2. Add the Node.js plugin:
   ```
   asdf plugin add nodejs
   ```
3. Install Node.js 22.4.1:
   ```
   asdf install nodejs 22.4.1
   ```
4. Set the Node.js version for the project:
   ```
   asdf local nodejs 22.4.1
   ```

Alternatively, you can install Node.js 22.4.1 directly without ASDF.

### 2. Docker Setup

1. Ensure Docker and Docker Compose are installed on your system.
2. Start the Docker containers:
   ```
   docker-compose up
   ```

### 3. Project Setup

1. Install project dependencies:
   ```
   npm install
   ```

2. Seed the MongoDB with patients and doctors data:
   ```
   npm run seed
   ```

   Note: You can use MongoDB Compass to view the seeded data. Connect using the following URI:
   ```
   mongodb://root:examplepassword@localhost:27017/dpu-db?authSource=admin
   ```

3. Start the development server:
   ```
   npm run start:dev
   ```

   The server will start on port 8080. You can access the Swagger docs at `http://localhost:8080/docs`.

## Usage

- Interact with the system using APIs in the simulate and healthcare modules.
- Ensure all Docker services are running, especially Kafka and Ranger.
- Access the Ranger Admin UI at `http://localhost:6080/` using the following credentials:
  - Username: admin
  - Password: rangerR0cks!

## Docker Services

The project uses the following Docker services:

- Zookeeper
- Ranger Solr
- Ranger DB (PostgreSQL)
- Ranger Admin
- Kafka
- MongoDB

For detailed configuration of these services, refer to the `docker-compose.yml` file in the project root.

## Notes

- The MongoDB connection string is set in the Docker Compose file. Adjust if necessary.
- Make sure to check the status of all Docker services before running the application.
- For any issues or further customization, refer to the individual service documentation.
