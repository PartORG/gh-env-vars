# PartORG/gh-env-vars

**A simple backend application using Node.js, Express, and MongoDB to manage events.**

[![JavaScript](https://img.shields.io/badge/language-JavaScript-blue.svg)] [![Node.js](https://img.shields.io/badge/runtime-Node.js-green.svg)] [![License](https://img.shields.io/badge/license-ISC-red.svg)] [![npm](https://img.shields.io/badge/package%20manager-npm-yellow.svg)] [![Express](https://img.shields.io/badge/framework-Express-brightgreen.svg)] [![Playwright](https://img.shields.io/badge/testing-Playwright-purple.svg)]

## Introduction

Welcome to `gh-env-vars`, a backend application designed to manage events using Node.js, Express, and MongoDB. This project is perfect for developers looking to learn how to build a simple RESTful API with these technologies.

The primary workflow involves setting up the environment, installing dependencies, configuring the database, and running the server. The main advantages of this project include its simplicity, ease of use, and the ability to manage events efficiently.

## Table of Contents

1. [Features](#features)
2. [How It Works](#how-it-works)
3. [Technology Stack](#technology-stack)
4. [Requirements](#requirements)
5. [Installation](#installation)
6. [Configuration](#configuration)
7. [Quick Start](#quick-start)
8. [Usage](#usage)
9. [Project Structure](#project-structure)
10. [Development](#development)
11. [Testing](#testing)
12. [Limitations](#limitations)
13. [License](#license)

## Features

### Event Management
- **Create Events**: Easily add new events.
- **Retrieve Events**: Fetch existing events.
- **Update Events**: Modify event details.
- **Delete Events**: Remove unwanted events.

### Database Integration
- **MongoDB**: Store and manage events using MongoDB, a NoSQL database.

## How It Works

The application is built using Express.js as the web framework. The `app.js` file serves as the entry point for the server. The `routes/events.js` file defines the API endpoints for managing events. The `data/database.js` file handles the connection to MongoDB and CRUD operations.

Here's a simplified architecture diagram:

```
+-------------------+
|    app.js         |
+---------+---------+
          |
          v
+---------+---------+
| routes/ | data/   |
| events.js | database.js |
+---------+---------+
          |
          v
+---------+---------+
| body-parser | express | mongodb |
+---------+---------+
```

## Technology Stack

| Technology | Purpose |
|------------|---------|
| **Node.js** | Runtime environment for JavaScript applications. |
| **Express.js** | Web framework for building APIs. |
| **MongoDB** | NoSQL database for storing event data. |
| **body-parser** | Middleware to parse incoming request bodies. |
| **Playwright** | End-to-end testing tool for web applications. |

## Requirements

- Node.js (v14 or higher)
- MongoDB (v4.0 or higher)

## Installation

To install the dependencies, run:

```bash
npm install
```

## Configuration

The application uses environment variables to configure the database connection. You can set these variables in a `.env` file:

```plaintext
MONGO_URI=mongodb://localhost:27017/eventsdb
```

Alternatively, you can set them directly in your terminal before starting the server.

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

Here are some example commands and usage scenarios:

### Creating an Event

```bash
curl -X POST http://localhost:3000/events -H "Content-Type: application/json" -d '{"name": "Tech Talk", "date": "2023-10-05"}'
```

### Retrieving Events

```bash
curl http://localhost:3000/events
```

### Updating an Event

```bash
curl -X PUT http://localhost:3000/events/1 -H "Content-Type: application/json" -d '{"name": "Updated Tech Talk", "date": "2023-10-06"}'
```

### Deleting an Event

```bash
curl -X DELETE http://localhost:3000/events/1
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

- **app.js**: Entry point for the server.
- **data/database.js**: Handles database connection and CRUD operations.
- **routes/events.js**: Defines API endpoints for managing events.
- **tests/events-api.spec.js**: Contains test cases for the API.

## Development

The development workflow involves:

1. Cloning the repository.
2. Installing dependencies using `npm install`.
3. Setting up environment variables (optional).
4. Running the server with `npm run start`.
5. Writing tests in `tests/events-api.spec.js` and running them with `npm run test`.

## Testing

The application includes end-to-end tests using Playwright. To run the tests, execute:

```bash
npm run test
```

## Limitations

- The project is a simple example and does not include advanced features like authentication or authorization.
- Error handling could be improved for production use.

## License

This project is licensed under the ISC license. See the [LICENSE](LICENSE) file for details.