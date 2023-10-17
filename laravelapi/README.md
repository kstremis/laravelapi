## Introduction

This is a RESTful API built with Laravel and authenticated using JWT (JSON Web Tokens). It provides endpoints for user registration, login, and logout. This README will guide you on how to run this application, including server requirements, generating Swagger documentation, and testing the login experience.

## Server Requirements

Before you begin, make sure your server meets the following requirements:
PHP >= 7.2
Composer (https://getcomposer.org/)
MySQL or another supported database

## Installation

1. Clone the repository:
bash
git clone https://github.com/your-username/your-repo.git
cd your-repo

2. Install project dependencies using Composer:
bash
composer install

3. Create a .env file by copying .env.example:
bash
cp .env.example .env

4. Generate an application key:
bash
php artisan key:generate

5. Configure your .env file with your database credentials.

6. Run database migrations to create necessary tables:
bash
php artisan migrate

7. Install the JWT secret key:
bash
php artisan jwt:secret

8. Start the development server:
bash
php artisan serve

## Generating Swagger Documentation

This application uses the darkaonline/l5-swagger package for generating Swagger documentation. Follow these steps to generate and access the documentation:

1. Install the Swagger package:
bash
composer require darkaonline/l5-swagger

2. Publish the Swagger configuration:
bash
php artisan vendor:publish --provider "L5Swagger\L5SwaggerServiceProvider"

3. After publishing, open the config/l5-swagger.php configuration file and make any necessary adjustments (e.g., setting the API title, version, etc.).

4. Generate the Swagger documentation by running the following command:
bash
php artisan l5-swagger:generate

5. Access the Swagger documentation via the following URL:
bash
http://localhost:8000/api/documentation

## Testing the Login Experience

You can use Swagger documentation to test the login experience easily. Here's how to do it:

1. Visit the Swagger documentation URL:
bash
http://localhost:8000/api/documentation

2. Find the POST /login endpoint and click on it.

3. Click the "Try it out" button.

4. Fill in the required parameters (e.g., email and password) with valid user credentials.

5. Click the "Execute" button to send the login request.

6. You will receive a JWT token in the response if the login is successful.

7. Copy the JWT token for future authenticated requests.

You have successfully set up, generated Swagger documentation, and tested the login experience for this Laravel JWT REST API.

## Endpoints

POST /register: Register a new user.
POST /login: Log in with a registered user and receive a JWT token.
POST /logout: Log out by invalidating the JWT token.

Make sure to secure your JWT tokens and implement additional security measures as needed for a production environment.