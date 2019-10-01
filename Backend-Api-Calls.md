## Backend API Calls

- ### login
  - parameters: `username`, `password`
  - reponse: `token`, `session_id`
- ### logout
  - parameters: `token`, `session_id`
- ### planes
  - response: `data` [ `id`, `system`, `owner_system`, `reg`, `mark`, `type`, `beacon`, `logging` ]
- ### test
  - response: `working`
- ### waypoints
  - response: `data` [ `latitude`, `longitude`, `icao`, `name`, `altitude` ]
