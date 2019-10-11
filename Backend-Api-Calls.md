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

- ### `aircrafts` (session-required)
  Get list of available aircrafts.

  - parameters: `token`, `session_id`
  - response: `aircrafts`, `data` [ `id`, `system`, `owner_system`, `reg`, `mark`, `type`, `beacon`, `logging` ], `datacount`

- ### `delay-types` (session-required)
  Get list of available Delay Types.

  - parameters: `token`, `session_id`
  - response: `data` [ `id`, `fi`, `en`, `owner` ], `datacount`
    
- ### `login` (public)
  Login to the Backend server with existing username and password.
  
  - parameters: `username`, `password`
  - reponse: `token`, `session_id`
  
- ### `logout` (session-required)
  Logout from the Backend server with existing session_id and token.
  
  - parameters: `token`, `session_id`

- ### `prog` (session-required)
  Get list of available PROG types for a flight.

  - parameters: `token`, `session_id`
  - response: `data` [ `id`, `fi`, `fin`, `en`, `eng`, `owner`], `datacount`

- ### `search-users` (session-required)
  Get list of available users. Limit count is optional value.

  - parameters: `token`, `session_id`, (`limit`)
  - response: `data` [ `id`, `first`, `sure` ], `datacount`
  
- ### `syllabus` (session-required)
  Get list of available syllabusses for flight logging.

  - parameters: `token`, `session_id`
  - response: `data` [ `id`, `list_id`, `list_name`, `ident`, `en`, `fi`, `type`, `owner_system` ], `datacount`  
  
- ### `systems-for-logging` (session-required)
  Get list of available systems for flight logging.

  - parameters: `token`, `session_id`
  - response: `data` [ `id`, `name` ], `datacount`    

- ### `test` (public)
  A Simple Test for Backend API -communication.
  
  - response: `working`

- ### `type` (session-required)
  Get list of available flight TYPE(s) for a flight.

  - parameters: `token`, `session_id`
  - response: `data` [ `id`, `fi`, `fin`, `en`, `eng`, `owner`], `datacount`

- ### `waypoints` (public)
  Get list of common Waypoints (airports, etc.).
  
  - response: `data` [ `latitude`, `longitude`, `icao`, `name`, `altitude` ]
