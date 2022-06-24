## Cinema application
Application to manage cinema user account. You can register as a user, login, add tickets to certain movies at certain time to your shopping cart, 
complete your order(and enjoy a movie you picked, obviously:)). Application also has role based authorisation. It might be a great addition to some online or offline cinema business 

## Technologies used
- Java 11
- Hibernate
- Spring Framework
- REST
- MySQL
- Apache Tomcat 9.0.50

## Overview
Application stores information about users, tickets, movies, movie sessions in a database. It has basic authentication process as well as role based authorisation for two initial roles - USER and ADMIN.
You have different access for different roles. Mostly, ADMIN has access to POST, PUT, DELETE across entire app when USER has access to GET endpoints.
You can use Postman or any other tool to test functionality of the app
For simplicity, here is the list of all available endpoints with role access:
Type: /URL - role to access      
- POST: /register - always available
- POST: /cinema-halls - ADMIN
- GET: /cinema-halls - ADMIN, USER
- GET: /movies - ADMIN, USER
- POST: /movies - ADMIN
- GET: /movie-sessions/available - ADMIN, USER
- POST: /movie-sessions - ADMIN
- PUT: /movie-sessions/ - ADMIN
- DELETE: /movie-sessions/ - ADMIN
- GET: /orders - USER
- POST: /orders/complete - USER
- PUT: /shopping-carts/movie-sessions - USER
- GET: /shopping-carts/by-user - USER
- GET: /users/by-email - ADMIN

# Example
example of JSON for POST request for /register:
{"email" : "example@gmail.com", "password" : "Abc123123", "repeatPassword" : "Abc123123"}

## Installation
- Copy this project to your IDE
- Install MySQL
- Configure db.properties file with relevant data
- Configure Tomcat(9.0.50 would be the best choice) and run the app
- (Optional) You either need to log in with admintest@gmail.com login and Abc123123 password as admin, or create account with /register endpoint
