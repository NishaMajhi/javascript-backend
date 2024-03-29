# Notes----

## Important definition 
- JavaScript - 
- mongoDB - 
- mongoose - 
- Node - 
- express - 
  - cors - 
  - express.json - 
  - express.urlencoded - 
  - express.static - 
- controller - 
- middleware - 
- route - 
- ### Packages
    - express
    - mongoose
    - aggregation pipeline - 
    - bcrypt - 
    - jwt - 
    - nodemon - 
    - prettier - 


## Project Structure
- node_moules
- public
- src
  - controllers
    - xyz.controller.js
  - db
    - connect.js 
  - middlewares
    - xyz.middleware.js
  - models
    - xyz.model.js
  - routes
    - xyz.route.js
  - utils
  - app.js
  - constants.js
  - index.js
- .env
- .gitignore
- .prettierignore
- .prettierrc
- package-lock.json
- package.json


## Basic Set-Up
- set a empty file use `npm init`.
- install dev-dependencies
  - by `npm i -D [dependency name]`.
  - prettier - (for style configuration)
  - nodemon - (for auto-start our server after saving it)
- install dependencies 
  - by `npm i [dependency name]`
  - `express` - (for hadling route, make server)
  - cors - (express middleware for handling cross-origin-resourse-sharing errors)
  - dotenv - (for accessing .env variable)
  - mongoose - (for talking with mongoDB Database)
  - mongoose-aggregate-paginate-v2  - (for aggregation pipe and other mongoose features)
  - bcrypt - (for password encryption/decryption)
  - jsonwebtoken - (for token)
  - cookie-parser - (express middleware to store nd read client cookie by server only)
- make .env file for keeping environment variable. 
- make a public folder to keep images, file, svg etc.
- make src folder
  - make following files
    - index.js
    - app.js - (for express app creation and adding all express middlewares) 
    - constants.js - (for keeping constants only)
  - make sub-folders
    - controllers (response function defintion)
    - models - (for keeping all models)
    - middlewares (to check things)
    - routes (for defining routes)
    - db (for database connection)
    - utils (for keeping utility function)
- .gitignore file (use gitignore generator websites to find all things for this file).
- make .prettierrc file(for keeping style configuration) and .prettierignore file(for keeping file names where style configuration should not follow).
- In package.json file change scripts(dev, start)  and add "types":"module" for supporting import statement.


## Commands
- `npm init`
- `npm i -D nodemon prettier`
- `npm i mongoose express dotenv cors`
- `npm i bcrypt jsonwebtoken cookie-parser mongoose-aggregate-paginate-v2`


## Keep Things in mind
- use async/await in code.
- use try-catch block. 


## File Dtailed Description 

- ## public
    - make folders for storing different kind of data

- ## .env
    - keep all secret variable, urls and environmant variable.

- ## .gitignore
    - use gitignore generator websites to generate code(files, folders name) to keep in it [link](https://mrkandreev.name/snippets/gitignore-generator/).

- ## .prettierignore
    - keep (.env and others) files so that style wont apply there.

- ## .prettierrc
    - keep code style setting for particular project, use this link for reference [link](https://prettier.io/docs/en/configuration.html)

- ## .package.json 
    - all dependencies, dev-dependencies, scripts, description about projects present

- ## src/index.js
    - import all packages, that you want should be available for all files.
    - import connectDB function and express app object
    - call connectDB function, if successfully connect with DB then (.then) make express server use app.listen() otherwise (.catch) console the error.

- ## src/app.js
    - import express and all express related middlewares ( cors, cookie-parser (cookieParser) ).
    - make an app object of express
    - add all express middlewares by using app.use()
      - cors() - for sharing resource with other     
        - others can be - different port number, different urls
      - express.json() - for accepting json data from request body
      - express.urlencoded({extended:true}) - 
        - express.urlencoded() - is for accepting data from request params
        - extended:true - means accept Object of Object from request params
      - express.static('') - for kepping public assests ( images, svgs, files)
      - cookieParser() - to store and perform CURD operation on client cookie by server only

- ## src/constants.js
    - keep all constants

- ## src/db
    - make connectDB function 
    - we take mongo_url(.env) and db_name(constants) and  using mongoose.connect establish the connection with the database.
   - if any error occur then console it and exit the process.

- ## src/models
    - present all models , their aggregation pipeline, hooks(pre, post), custome methods
      - aggregation pipeline - aggregation pipeline means use advance feature of mongoDB (like using hooks, adding custom functions etc). 
        - use "mongoose-aggregate-paginate-v2" package for performing aggregation.
      - pre() hook - if we want to perform any action just before any operation (save, update etc.) we use pre hook.
      - post() hook - if we want to perform any action just after any operation (save,update etc.) we use post hook.

- ## src/routes
    - define routes related to each model.

- ## src/middlewares
    - define various middlewares like (authentication).

- ## src/utils
    - define utilities that we will required while code

- ## src/controllers
    - in controllers, write code for accepting request , perform operation and send response.