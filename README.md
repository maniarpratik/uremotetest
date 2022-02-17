# uremotetest
# 1 ) Create Database in mysql named "uremotetest" (If you have different database name change to config.json )
# 2 ) Run node .\server.js
# 3 ) How to register a new user with Postman
	1 ) Open a new request tab by clicking the plus (+) button at the end of the tabs.
	2 ) Change the http request method to "POST" with the dropdown selector on the left of the URL input field.
	3 ) In the URL field enter the address to the register route of your local API - http://localhost:4000/users/register.
	4 ) Select the "Body" tab below the URL field, change the body type radio button to "raw", and change the format dropdown selector to "JSON".
	5 ) Enter a JSON object containing the required user properties in the "Body" textarea, e.g:
		{
			"firstName": "United",
			"lastName": "Remote",
			"username": "unitedremote",
			"password": "unitedremote#123#"
		}
	6 ) Click the "Send" button, you should receive a "200 OK" response with a success message in the response body.
# 4 ) How to authenticate a user with Postman (To authenticate a user with the api and get a JWT token follow these steps: )  
	1) Open a new request tab by clicking the plus (+) button at the end of the tabs.
	2) Change the http request method to "POST" with the dropdown selector on the left of the URL input field.
	3) In the URL field enter the address to the authenticate route of your local API - http://localhost:4000/users/authenticate.
	4) Select the "Body" tab below the URL field, change the body type radio button to "raw", and change the format dropdown selector to "JSON".
	5) Enter a JSON object containing the username and password in the "Body" textarea:
		{
			"username": "unitedremote",
			"password": "unitedremote#123#"
		}
	6) Click the "Send" button, you should receive a "200 OK" response with the user details including a JWT token in the response body, make a copy of the token value because we'll be using it in the next step to make an authenticated request.
# 5 ) How to make an authenticated request to retrieve all users (To make an authenticated request using the JWT token from the previous step, follow these steps:)
	1) Open a new request tab by clicking the plus (+) button at the end of the tabs.
	2) Change the http request method to "GET" with the dropdown selector on the left of the URL input field.
	3) In the URL field enter the address to the users route of your local API - http://localhost:4000/users.
	4) Select the "Authorization" tab below the URL field, change the type to "Bearer Token" in the type dropdown selector, and paste the JWT token from the previous authenticate step into the "Token" field.
	5) Click the "Send" button, you should receive a "200 OK" response containing a JSON array with all the user records in the system.
  
# 6 ) How to update a user with Postman (To update a user with the api follow these steps:)
	1) Open a new request tab by clicking the plus (+) button at the end of the tabs.
	2) Change the http request method to "PUT" with the dropdown selector on the left of the URL input field.
	3) In the URL field enter the address to the /users/{id} route with the id of the user you registered above, e.g - http://localhost:4000/users/1.
	4) Select the "Authorization" tab below the URL field, change the type to "Bearer Token" in the type dropdown selector, and paste the JWT token from the previous authenticate step into the "Token" field.
	5) Select the "Body" tab below the URL field, change the body type radio button to "raw", and change the format dropdown selector to "JSON".
	6) Enter a JSON object in the "Body" textarea containing the properties you want to update, for example to update the first and last names:
	{
		"firstName": "Test Lastname",
		"lastName": "Test Firstname"
	}
	7) Click the "Send" button, you should receive a "200 OK" response with the updated user details in the response body.
  
# 7 ) How to delete a user with Postman (To update a user with the api follow these steps:)
	1) Open a new request tab by clicking the plus (+) button at the end of the tabs.
	2) Change the http request method to "DELETE" with the dropdown selector on the left of the URL input field.
	3) In the URL field enter the address to the /users/{id} route with the id of the user you registered above, e.g - http://localhost:4000/users/1.
	4) Select the "Authorization" tab below the URL field, change the type to "Bearer Token" in the type dropdown selector, and paste the JWT token from the previous authenticate step into the "Token" field.
	5) Select the "Body" tab below the URL field, change the body type radio button to "raw", and change the format dropdown selector to "JSON".
	6) Click the "Send" button, you should receive a "200 OK" response with the updated user details in the response body.

# Important Information
How to install Nodejs : https://nodejs.org/en/download/
Installed NPM Command:\
npm i mysql2\
npm i express-jwt\
npm i jsonwebtoken\
npm i bcryptjs\
npm i rootpath\
npm i cors\
npm i body-parser\
npm i express\
npm i joi\
npm i sequelize
