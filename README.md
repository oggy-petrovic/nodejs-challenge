# Node.js Challenge

### Requirements & considerations:

● The Node.js version must be the newest current release (12.7.0 by now).

● All the services must be dockerized.

● Services must be added in docker-compose.

● The server must be able to be executed just running docker-compose up && npm start.

● The EcmaScript version to follow should be the newest one supported by that Node.js version.

● All the endpoints URLs and HTTP methods should be as standard as possible.

● The database models required are open to your considerations.

● Use any package that you may consider relevant (ORMs, utilities and so on).


### Nice to have:

● Using Typescript is a plus.

### Docker Services:

● MongoDB (current version is 4.0)

● Redis (current version is 5.0.5)

### External Services:

● Google Maps Geocoding API (https://developers.google.com/maps/documentation/geocoding/overview)

● Open Weather API (https://openweathermap.org/api)

## Base exercise:

Create a REST API Node.js project that can handle validations and retrieve the data only from the previously mentioned 
external services.

Setup a Node.js server (you can use any existent framework) with MongoDB and Redis services that handles authentication 
through access tokens (OAuth2-like). This authentication must validate the execution of any create, update and delete 
endpoints. The validation of the tokens must be done through Redis and without involving MongoDB. These access tokens
must expire after 10 hours.

Add an endpoint that receives an address and validate if its valid. This address must be in an object with the 
properties street, streetNumber, town, postalCode and country.

Add an endpoint that receives an address and check the weather at the latitude and longitude of that address.

Add an endpoint that receives an address, validate it and check the weather for the lat/lon of that address.

All the usages of external services must be cached for 12 hours. If an address has been checked in that timeframe, 
shouldn’t be validated again.

Setup a batch process that checks for the previously queried addresses and whenever there is any kind of precipitation 
(rain, snow, etc) in that place sends an email notification to the user who queried it.

Set an optional schedule option where the user can choose the notifications timeframe and only receive notifications if 
there is precipitation in the user selected schedules (i.e: only send an email when is raining in the range from 7AM to 
10AM). These schedules can be in the format of your preference, be as cool as you want.

Add as many complementary endpoints as you consider that are relevant and explain why these are relevant in terms of 
business logic. Document how can you deploy this architecture in AWS (note: you do not have to deploy this application).
