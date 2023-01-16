# crud-api

## Start
1. clone repo
2. go to the created folder
3. checkout to the development branch
4. install all dependencies

## Run app

1. Run the app in development mode
   npm run start:dev
2. Run the app in production mode
   npm run start:prod
3. Run app in cluster mode with one in-memory db for all processes
   npm run start:multi
4. Run tests
   npm test

   ## Server API

Implemented endpoint:  
`api/users` or `api/users/` (final slash is allowed)

Methods:

**GET** `api/users` is used to get all persons  
Server should answer with status code 200 and all users records
  
**GET** `api/users/${userId}`  
Server answers with status code **200** and record with `id === userId` if it exists  
Server answers with status code **400** and corresponding message if `userId` is invalid (not uuid)  
Server answers with status code **404** and corresponding message if record with `id === userId` doesn't exist  
   
**POST** `api/users is used` to create record about new user and store it in database  
Server answers with status code **201** and newly created record  
Server answers with status code **400** and corresponding message if request body does not contain required fields  
   
**PUT** `api/users/{userId}` is used to update existing user  
Server answers with status code **200** and updated record  
Server answers with status code **400** and corresponding message if `userId` is invalid (not uuid)  
Server answers with status code **404** and corresponding message if record with `id === userId` doesn't exist  
   
**DELETE** `api/users/${userId}` is used to delete existing user from database  
Server answers with status code **204** if the record is found and deleted  
Server answers with status code **400** and corresponding message if `userId` is invalid (not uuid)  
Server answers with status code **404** and corresponding message if record with `id === userId` doesn't exist  