## Backend API

1. Gives all the responses in JSON-format.
2. Every response has parameter `success` (Boolean) value given the requester information did the request succeed. If it didn't also `error` (String) will be given
3. Every request **must have** parameter `oper` that gives the information what **operation** is requested
4. **Warning:** every API-call should be passed in **POST** -request and parameters should be encoded in `multipart/form-data`. In development state **GET**-requests are allowed - but this feature will be removed in the production version.

Api URL: https://www.aviatron.fi/_skyAPI.php

Demo (GET) REQUEST: https://www.aviatron.fi/_skyAPI.php?oper=test

## Backend API Calls

- ### login
  - parameters: `username`, `password`
  - reponse: `token`, `session_id`
- ### logout
  - parameters: `token`, `session_id`
- ### planes
  - parameters: `token`, `session_id`
  - response: `planes`, `data` [ `id`, `system`, `owner_system`, `reg`, `mark`, `type`, `beacon`, `logging` ]
- ### test
  - response: `working`
- ### waypoints
  - response: `data` [ `latitude`, `longitude`, `icao`, `name`, `altitude` ]
