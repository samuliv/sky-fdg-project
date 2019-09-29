## Backend API Calls

- ### login
  - parameters: `username`, `password`
  - reponse: `token`, `session_id`
- ### logout
  - parameters: `token`, `session_id`
- ### test
  - response: `working`
- ### waypoints
  - response: `data` [ `latitude`, `longitude`, `icao`, `name`, `altitude` ]
