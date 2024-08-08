# LightBnB 

## Overview

This project provides a Node.js API for interacting with a PostgreSQL database for a hypothetical booking system called LightBnB. The API includes functions for managing users, properties, and reservations.

## Setup

### Prerequisites

- [Node.js](https://nodejs.org/) (>= 14.x)
- [PostgreSQL](https://www.postgresql.org/) (>= 13.x)

### Installation

1. **Clone the repository:**

    ```bash
    git clone https://github.com/your-username/lightbnb-api.git
    cd lightbnb-api
    ```

2. **Install dependencies:**

    ```bash
    npm install
    ```

3. **Setup the database:**

    Ensure you have PostgreSQL running and create a database named `lightbnb`. You may need to adjust the database configuration in the code (e.g., `user`, `password`, `host`, `database`) according to your setup.

4. **Run migrations and seed data (if applicable):**

    This project assumes the database schema is already set up. If you have migration and seeding scripts, run them as necessary.

## API Functions

### `getUserWithEmail(email)`

Fetches a user from the database by their email address.

- **Parameters:**
  - `email` (String): The email of the user.
- **Returns:** A promise that resolves to the user object or `null` if no user is found.

### `getUserWithId(id)`

Fetches a user from the database by their ID.

- **Parameters:**
  - `id` (String): The ID of the user.
- **Returns:** A promise that resolves to the user object or `null` if no user is found.

### `addUser(user)`

Adds a new user to the database.

- **Parameters:**
  - `user` (Object): The user object containing `name`, `email`, and `password`.
- **Returns:** A promise that resolves to the inserted user object.

### `getAllReservations(guest_id, limit)`

Fetches all reservations for a specific user.

- **Parameters:**
  - `guest_id` (String): The ID of the user.
  - `limit` (Number, optional): The maximum number of reservations to return (default is 10).
- **Returns:** A promise that resolves to an array of reservation objects.

### `getAllProperties(options, limit)`

Fetches all properties from the database.

- **Parameters:**
  - `options` (Object, optional): An object containing query options.
  - `limit` (Number, optional): The maximum number of properties to return (default is 10).
- **Returns:** A promise that resolves to an array of property objects.

### `addProperty(property)`

Adds a new property to the database.

- **Parameters:**
  - `property` (Object): The property object containing details such as `title`, `description`, `owner_id`, and `price_per_night`.
- **Returns:** A promise that resolves to the inserted property object.
