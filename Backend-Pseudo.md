 # Backend Plan

 ## Controllers
 ### tripController.js
 - get route for all trips (this is for the past trips page)
 - get route by id ( this is for current trip and when wanting to look at a specific past trip)
 - post route (this is for creating a trip)
 - put route (this is for adding expenses to the trip, editing total budget or editing number of days)
 - patch route by id (this is for updating individual expenses)
 - delete route (this is for deleting a trip entirely)
 - get route by id and day number (for showing individual day data)

 ### userController.js
- get route (dev purposes only to see how many users there are for testing purposes. Comment out before deployment?)
- post route for /signup includes bcrypt and password hashing  (see express auth api for reference on how to do)
- post route for /signin finds by User email with User.findOne(req.body.email) and uses token creation  (see express auth api for reference on how to do)

## Middleware
- auth.js (passport, bcrypt, jwt(jsonwebtokens) is all here)
- request-logger.js (for testing purposes and logging requests made)
- customErrors.js (for showing users specific messages when login info is incorrect)

## index.js 
- express
- cors
- redirect app.get for main page
- app.use 
    - tripController
    - userController
    - request-logger
    - cutomErrors

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
