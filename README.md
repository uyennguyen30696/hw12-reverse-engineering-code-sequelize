# Unit 14 Sequelize Homework: Reverse Engineering Code

## Purpose

This is a walk through tutorial for a starter coded provided. The purpose of this activity is to be familiar with the process of self inspecting code when first join a team or a project. 

## Tutorial

### Purpose

This app allows user to securely create an account, log in, and log back out. All user data is stored in MySQL database. 

### Dependencies

* bcryptjs
* express
* express-session
* mysql2
* passport
* passport-local
* sequelize
* sequelize-cli

### Installation

Follow these steps after cloning the repository to use the app: 

* Create a database in MySQL named `passport_demo`.
* Update the `config.json` file's development object with your own local MYSQL database settings.
* Open terminal in the current repository, then run `npm i` to install the node modules and install the dependencies needed. 
* Run `node server.js` to start the server. If successfully connected, the app will run in the browser at "http://localhost:8080".

### Files functionality 

#### The config folder

* The config folder contains the middleware isAuthenticated.js file which restricts routes that a user is not allowed to visit if not logged in. If the user is successfully logged in, the route to the restricted file is proceeded. If not, the page is redirected to the login page.

* The config.json file is the connection configuration to connect to the server.

* The passport.js is an authentication middleware which contains javascript logics to authenticate requests from user to login with email and password. 

#### The models folder

* The models/index.js file is generated with the sequelize CLI and collects all the models from the models directory and associates them if needed.

* The models.user.js file require bcrypt for password hashing. This file defines what will be in the database and makes the website secure.

#### The node_modules folder

This folder contains the modules needed for the application to run.

#### The public folder

This folder contains the HTML, CSS, and Javascript files for front end that will interact with the user by receiving requests and delivering information from the back end to the user through api.

#### The routes folder

* The api-routes.js contains routes for signing in, logging out, and retrieve data to be displayed to the user. 

* The html-routes.js checks whether or not the user is logged in. The user will be directed to the member page if already has an account. If not, the user is redirected to the signup page.

#### The package.json file

This file contains all the information of the used packages.

#### The server.js file

This file performs the functionalities, including: requires necessary npm packages, sets up port and require models for syncing, create express app and configuring middleware needed for authentication, require routes, syncing our database and logging a message to the user upon success.