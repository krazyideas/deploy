# deploy
[![License](http://img.shields.io/:license-apache-blue.svg?style=flat-square)](http://www.apache.org/licenses/LICENSE-2.0.html)

Deployment Instructions for Krazy Ideas

Contained here in is the docker compose file that can be utilized for testing and deployment purposes

## Data Initialization
Two steps need to be performed before starting to use the application:
* Create blank ideas
* Establish an admin user

### Creating Ideas
curl -i -X POST -H "Content-Type:application/json" -d '{"name":"idea1"}' http://localhost:8080/idea
Subsequently, an admin user can modify these initial ideas to any form using UI.

### Create an admin user
Below is an example curl script for converting a normal user to an admin user... assuming first registered user will be the admin.
curl -i -X PUT -H "Content-Type:application/json" -d '{"name": "adminuser", "authId": "1234@github", "adminFlag": true}' http://localhost:8080/people/1
