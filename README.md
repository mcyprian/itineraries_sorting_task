# Itineraries sorting

## Task
Create a REST API that can sort a given list of travel itineraries using various sorting criteria.

### Itinerary definition
An itinerary is a JSON object with the following structure:
```
{
  "id": "awesome_adventure", // identifier of the travel itinerary
  "duration_minutes": 330, // total duration including all flights and layovers in minutes
  "price": {  // total price of the itinerary
    "amount": "90",
    "currency": "EUR"
  }
}
```

### Sorting options
Your application supports three ways to sort itineraries:
  - **cheapest**: Sort based on price, with the most affordable ones coming first.
  - **fastest**: Sort by duration, with the shortest ones at the top of the list.
  - **best**: Design an algorithm to find the optimal balance between price and duration.

### Example
Request:
```
POST /sort_itineraries
{
 "sorting_type": "cheapest",
 "itineraries": [
   {
     "id": "sunny_beach_bliss",
     "duration_minutes": 330,
     "price": {
       "amount": "90",
       "currency": "EUR"
     }
   },
   {
     "id": "rocky_mountain_adventure",
     "duration_minutes": 140,
     "price": {
       "amount": "830",
       "currency": "EUR"
     }
   },
   {
     "id": "urban_heritage_odyssey",
     "duration_minutes": 275,
     "price": {
       "amount": "620",
       "currency": "CZK"
     }
   }
 ]
}
```

Response:
```
200 OK
{
 "sorting_type": "cheapest",
 "sorted_itineraries": [
   {
     "id": "urban_heritage_odyssey",
     "duration_minutes": 275,
     "price": {
       "amount": "620",
       "currency": "CZK"
     }
   },
   {
     "id": "sunny_beach_bliss",
     "duration_minutes": 330,
     "price": {
       "amount": "90",
       "currency": "EUR"
     }
   },
   {
     "id": "rocky_mountain_adventure",
     "duration_minutes": 140,
     "price": {
       "amount": "830",
       "currency": "EUR"
     }
   }
 ]
}
```

## Requirements
In this short task, we want you to demonstrate your best skills. Imagine you're creating code for an MVP that's ready for use on production, 
following the best coding practices. Write your solution in Python 3 or Go. You can use all the libraries and APIs that are publicly available. 
If you have any ideas to make it even better, feel free to include them, like:

### Mandatory:
  - Ensure proper test coverage.
  - Create API documentation, e.g. OpenAPI 3.0.
  - Include a README.md with a description and instructions on how to test and run the application.


### Optional:
 - Add container image definition (Dockerfile)
 - Include CI/CD (Continuous Integration/Continuous Deployment).
 - Consider adding data storage and caching.
 - Anything else you'd like to try.

Once you're done, create a private repository with your solution on GitHub and add https://github.com/mcyprian and https://github.com/rlapar as a contributors.
