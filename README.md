Name: Pranjal Parmar
ID: 117504225
Mail: pparmar25@myseneca.ca

# API for Note-Taking Application

## Overview
This application presents a RESTful API for managing notes. Users can utilize HTTP requests to perform CRUD operations on notes. The API is developed in Python using the `http.server` module from the standard library. Additionally, it integrates with a MySQL database for data persistence.

## Prerequisites
- Docker installed on the local machine.
- Fundamental understanding of Docker commands and operations.
- Familiarity with Git for version control.

## Setup and Installation
1. **Clone the Repository**
    ```bash
    git clone https://github.com/LuqmanDirie/BTP405
    cd directory-name
    ```

2. **Build and Run with Docker Compose**

    Deploy Docker Compose to construct and execute the application and database services:
    ```bash
    docker-compose up --build
    ```

    This command generates the API server image and initializes the services defined in docker-compose.yml.

3. **Stopping the Services**

    To halt the services and remove the containers, utilize the following command:
    ```bash
    docker-compose down
    ```

## API Endpoints

The API supports the subsequent operations:

### GET /notes - Retrieve All Notes
- **Objective**: Fetches all notes.
- **Method**: GET
- **URL**: `http://localhost:8080/notes`
- **Body**: None
- **Instructions**: Specify the request method as GET, input the URL, and send the request.

### POST /notes - Create a New Note
- **Objective**: Establishes a new note.
- **Method**: POST
- **URL**: `http://localhost:8080/notes`
- **Body**: (application/json)
    ```json
    {
      "title": "New Note",
      "content": "Content of the new note."
    }
    ```
– **Instructions**: **POST** – **URL** – **Body**: ‘raw’ – **Type**: JSON – **Send**:

### PUT /notes - Update an Existing Note
- **Objective**: Modifies an existing note by ID.
- **Method**: PUT
- **URL**: `http://localhost:8080/notes?id=1` (Replace `1` with the actual note ID)
- **Body**: (application/json)
    ```json
    {
      "title": "Updated Note",
      "content": "Updated content."
    }
    ```
- **Instructions**: Set the request method to PUT, input the URL, select Body from the tabs, set to 'raw', set the Type to 'JSON', paste the JSON to modify the note, and submit the request.

### DELETE /notes - Delete a Note
- **Objective**: Removes an existing note by ID.
- **Method**: DELETE
- **URL**: `http://localhost:8080/notes?id=1` (Replace `1` with the actual note ID)
- **Body**: None
- **Instructions**: Set the request method to DELETE, enter the URL, and send the request.

## Testing

Invoke the API endpoints using a graphical user interface (GUI) like [Postman](https://www.postman.com/) mimicking a browser client, or employ `curl` commands akin to those illustrated in the examples above.

## Additional Information

- The MySQL database initializes with a `notes` table encompassing columns for `id`, `title`, and `content`.
- The API server operates on port `8080`, while the MySQL service is accessible on the default port `3306`.
- Ensure possession of the `.env` file containing necessary environment variables if sensitive or environment-specific configurations exist.