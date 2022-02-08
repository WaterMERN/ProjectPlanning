 # Backend Plan

 ## Controllers
 ### tripController.js
 - require express
 - get route for all trips (this is for the past trips page)
 - get route by id ( this is for current trip and when wanting to look at a specific past trip)
 - post route (this is for creating a trip)
 - put route (this is for adding expenses to the trip, editing total budget or editing number of days)
 - patch route by id (this is for updating individual expenses)
 - delete route (this is for deleting a trip entirely)
 - get route by id and day number (for showing individual day data)
 - export controller

 ### userController.js
- require express
- get route (dev purposes only to see how many users there are for testing purposes. Comment out before deployment?)
- post route for /signup includes bcrypt and password hashing  (see express auth api for reference on how to do)
- post route for /signin finds by User email with User.findOne(req.body.email) and uses token creation  (see express auth api for reference on how to do)
- export controller
## Middleware
- auth.js 
    - require (passport, bcrypt, jwt(jsonwebtokens) is all here)
        - define secret 
        - destructure strategy and extract JWT
        - define minimum options for  passport
        - require User model
        - define strategy with options and jwt payload
        - pass user onto route 
        - passport uses strategy then intializes
        - require passport to require token
        - create user token for authorization
        -  export require token and create user token
- request-logger.js (for testing purposes and logging requests made)
    - series of console logs to show what we are looking at
    -export request logger
- customErrors.js (for showing users specific messages when login info is incorrect)
    - ownership error
    - document not found error
    - authorization credentials error
    - bad params error
    - create arrow functions with conditional statements for each error type
    - export each idividual arrow  function 
## index.js 
- express
- cors
- redirect app.get for main page
- app.use 
    - tripController
    - userController
    - request-logger
    - cutomErrors
- app.listen

## Models Pseudo Code
- Trip Schema
    - require mongoose at the top
    - create schema that will include:
        - budget: number
        - cost: number
        - date: number
        - Totals for lodging, food, transport, other all with
            - title: string
            - cost: number
    - declare Trip SChema as a variable and export at the bottom

- Day Schema
    - require mongoose at the top
    - create schema that will include
        - date: number || string
        - Expenses (lodging, food, transport, other) all with
            - title: string
            - cost: number
        - will have to link to trip schema for a specific trip
    - declare Day Schema as a variable and export at the bottom

- User Schema
    - require mongoose at the top
    - create schema that will include
        - name: string
        - email: {type: string, required: true, unique: true}
        - password: {type: string, required: true}
        - timestamp: true
    - declare User Schema as a variable and export at the bottom
