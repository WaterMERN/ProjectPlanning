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
- redirect app.get
- app.use 
    - tripController
    - userController
    - request-logger
    - cutomErrors
