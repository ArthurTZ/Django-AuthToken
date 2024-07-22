
# Django REST API Project with Poetry

This project is a simple Django REST API for user authentication, including signup, login, and token verification. It uses Django's built-in user model and Django REST Framework (DRF) for handling API endpoints. The project is managed using Poetry for dependency management.

## Features

- **User Signup:** Allows new users to create an account.
- **User Login:** Authenticates users and provides a token.
- **Token Verification:** Verifies if the provided token is valid.

## Setup

### Prerequisites

- Python 3.8 or higher
- Poetry


### Installation

1. Clone the repository:

    ```sh
    git clone <repository-url>
    cd <repository-name>
    ```

2. Install dependencies using Poetry:

    ```sh
    poetry install
    ```

    ```sh
    poetry add django djangorestframework taskipy
    ```

    #### Poetry Custom Tools
   ```sh
    [tools.taskipy.tasks]
     run = "python maange.py runserver"
     manage = "python manage.py"
     test = "python manage.py test ."
    ```

3. Apply migrations:

    ```sh
   task manage migrate
    ```

4. Run the server:

    ```sh
    task run
    ```

5. Run the Tests :

    ```sh
    task tests
    ```


## API Endpoints

### Signup

- **URL:** `/signup`
- **Method:** `POST`
- **Description:** Creates a new user and returns an authentication token.
- **Request Body:**
    ```json
    {
        "username": "your_username",
        "password": "your_password",
        "email": "your_email@example.com"
    }
    ```
- **Response:**
    ```json
    {
        "token": "your_token",
        "user": {
            "id": 1,
            "username": "your_username",
            "email": "your_email@example.com"
        }
    }
    ```

### Login

- **URL:** `/login`
- **Method:** `POST`
- **Description:** Authenticates a user and returns an authentication token.
- **Request Body:**
    ```json
    {
        "username": "your_username",
        "password": "your_password"
    }
    ```
- **Response:**
    ```json
    {
        "token": "your_token",
        "user": {
            "id": 1,
            "username": "your_username",
            "email": "your_email@example.com"
        }
    }
    ```

### Test Token

- **URL:** `/test_token`
- **Method:** `GET`
- **Description:** Verifies if the provided token is valid.
- **Headers:**
    ```
    Authorization: Token your_token
    ```
- **Response:**
    ```json
    {
        "message": "passed for the email : your_email@example.com"
    }
    ```

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
