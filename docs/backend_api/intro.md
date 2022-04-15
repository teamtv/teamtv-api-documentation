# Backend API

All backend APIs of TeamTV can be found at `https://api.teamtvsport.com/api/`

# Authentication

Authentication with the TeamTV api can be done in two ways:
1. Using a header 
2. Using a query parameter

## Using a header

When using the header variable for authentication you should us the `Authorization` header. The value should be `Bearer <TOKEN>`.

## Using a query parameter

Add the query parameter to the request. The request should look like `/api/endpoint?Authorization=<TOKEN>`

## Get a token

When you would like to retrieve an API token please reach out to [koen@teamtv.nl](mailto:koen@teamtv.nl).



