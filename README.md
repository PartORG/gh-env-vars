# gh-env-vars

A simple backend application using Express.js and MongoDB to manage environment variables securely.

[![JavaScript](https://img.shields.io/badge/language-JavaScript-blue.svg)] [![Express](https://img.shields.io/badge/framework-Express-green.svg)] [![MongoDB](https://img.shields.io/badge/database-MongoDB-brown.svg)] [![License](https://img.shields.io/badge/license-ISC-red.svg)] [![Tests](https://img.shields.io/badge/tests-passing-brightgreen.svg)]

## Introduction

`gh-env-vars` is a lightweight backend application designed to manage environment variables securely. It leverages Express.js for routing and MongoDB for data storage, ensuring that sensitive information is handled with care.

The primary workflow of this project involves setting up an Express server, connecting it to a MongoDB database, and providing endpoints to create, read, update, and delete environment variables. This application is particularly useful for developers who need a simple way to manage their environment variables without exposing them in the codebase.

## Table of Contents

- [Features](#features)
- [How It Works](#how-it-works)
- [Technology Stack](#technology-stack)
- [Requirements](#requirements)
- [Installation](#installation)
- [Configuration](#configuration)
- [Quick Start](#quick-start)
- [Usage](#usage)
- [Project Structure](#project-structure)
- [Development](#development)
- [Testing](#testing)
- [Limitations](#limitations)
- [License](#license)

## Features

### Environment Variable Management

- **Create**: Add new environment variables.
- **Read**: Retrieve existing environment variables.
- **Update**: Modify the values of existing environment variables.
- **Delete**: Remove environment variables that are no longer needed.

### Secure Storage

- Data is stored in MongoDB, ensuring that sensitive information is protected from unauthorized access.

## How It Works

The application consists of an Express server that handles incoming requests and routes them to appropriate handlers. The main components are:

1. **app.js**: The entry point of the application where the Express server is initialized.
2. **routes/events.js**: Contains the API endpoints for managing environment variables.
3. **data/database.js**: Handles the connection to the MongoDB database.

## Technology Stack

| Technology | Purpose |
|------------|---------|
| **Express** | A minimal and flexible Node.js web application framework that provides a robust set of features to develop web and mobile applications. |
| **MongoDB** | A NoSQL database that stores data in JSON-like documents, making it highly scalable and flexible. |
| **body-parser** | Middleware for parsing incoming request bodies in a middleware before your handlers, available under the `req.body` property. |

## Requirements

- Node.js (>= 14.x)
- MongoDB (>= 4.0)

## Installation

To install the project dependencies, run:

```bash
npm install
```

## Configuration

The application does not require any environment variables or configuration files.

## Quick Start

To start the application, run:

```bash
npm run start
```

To run tests, use:

```bash
npm run test
```

## Usage

### Creating an Environment Variable

```bash
curl -X POST http://localhost:3000/env -H "Content-Type: application/json" -d '{"key": "API_KEY", "value": "123456789"}'
```

### Reading an Environment Variable

```bash
curl http://localhost:3000/env/API_KEY
```

### Updating an Environment Variable

```bash
curl -X PUT http://localhost:3000/env/API_KEY -H "Content-Type: application/json" -d '{"value": "987654321"}'
```

### Deleting an Environment Variable

```bash
curl -X DELETE http://localhost:3000/env/API_KEY
```

## Project Structure

```
.
├── .DS_Store
├── .github/workflows/deploy.yml
├── .gitignore
├── app.js
├── data/database.js
├── package-lock.json
├── package.json
├── playwright.config.js
└── routes/events.js
└── tests/events-api.spec.js
```

- **app.js**: Entry point of the application.
- **data/database.js**: Handles database connection and operations.
- **routes/events.js**: Contains API endpoints for managing environment variables.
- **tests/events-api.spec.js**: Test cases for the API endpoints.

## Development

To contribute to this project, follow these steps:

1. Fork the repository.
2. Create a new branch (`git checkout -b feature/AmazingFeature`).
3. Make your changes and commit them (`git commit -m 'Add some AmazingFeature'`).
4. Push to the branch (`git push origin feature/AmazingFeature`).
5. Open a pull request.

## Testing

To run tests, use:

```bash
npm run test
```

## Limitations

- This application does not handle authentication and authorization for accessing environment variables.
- It assumes that MongoDB is running locally on the default port.

## License

This project is licensed under the ISC License - see the [LICENSE](LICENSE) file for details.