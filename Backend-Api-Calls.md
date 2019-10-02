## Backend API

1. Gives all the responses in JSON-format.
2. Every response has parameter `success` (Boolean) value given the requester information did the request succeed. If it didn't also `error` (String) will be given
3. Every request **must have** parameter `oper` that gives the information what **operation** is requested
4. **Warning:** every API-call should be passed in **POST** -request and parameters should be encoded in `multipart/form-data`. In development state **GET**-requests are allowed - but this feature will be removed in the production version.
5. JSONRequest -class takes care of these requirements and passes the requests safely (in a POST-request and values encoded into prefferred format) to the Backend service
6. In development state you can also pass the variables in GET -request. **Warning: Do not pass urgent information in GET-request (login passwords, private info, etc...)**

Api URL: https://www.aviatron.fi/_skyAPI.php

Demo (GET) REQUEST: https://www.aviatron.fi/_skyAPI.php?oper=test

## Backend API Calls (operations)

- ### `login` (public)
  Login to the Backend server with existing username and password.
  
  - parameters: `username`, `password`
  - reponse: `token`, `session_id`
- ### `logout` (session-required)
  Logout from the Backend server with existing session_id and token.
  
  - parameters: `token`, `session_id`
- ### `planes` (session-required)
  Get list of available planes.

  - parameters: `token`, `session_id`
  - response: `planes`, `data` [ `id`, `system`, `owner_system`, `reg`, `mark`, `type`, `beacon`, `logging` ]
- ### `test` (public)
  A Simple Test for Backend API -communication.
  
  - response: `working`
- ### `waypoints` (public)
  Get list of common Waypoints (airports, etc.).
  
  - response: `data` [ `latitude`, `longitude`, `icao`, `name`, `altitude` ]
