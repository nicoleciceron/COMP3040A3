## Winnipeg Transit
---
An API is an interface where the routines and features of a website or platform are provided. This document introduces the Winnipeg Transit which provides a way for you to retrieve live status and information according to your needs. It provides specifications for exchanging both static and real time public transit information, including information about stops, routes, schedule, service alerts, and other details. It documents resources, query parameters, response structures and data types. The Winnipeg Transit API has a number of endpoints shown below.

## List of Endpoints with Parameters

1. **ticketFair(age)**<br>
This endpoint takes in age of the user as it's parameter and returns the cost of the ticket which applies to that age group.
1. **peggoPass()** <br>
This endpoint returns all the information about different kinds of bus passes available.
1. **busInfo()** <br>
This endpoint returns information about all the busses, like their bus number, their start location and their destination

## Description of Resources

**1. Resources for ticketFare**
```
	"result":
	{
		"id",
		"type",
		"cash_price",
		ticket_price
		"monthly_pass_price"
	}
```
- Name: "id", Type: string, Example: "2"
<br>The unique identifier for the cost of riding the bus

- Name: "type", Type string, Example: "Senior Fare"
<br>The type of bus fare.

- Name: "cash_price", Type: string, Example: "2.50"
<br>Price of bus fare using cash.

- Name: "ticket_price", Type: string, Example: "1.33"
<br>Price of a bus ticket.

- Name: "monthly_pass_price", Type: string, Example: "41.05"
<br>Price of a monthly bus pass.


**2. Resources for peggoPass**
```
	"result": [
		{
			"id",
			"type",
			"colour",
			"passenger_type"
		}
	]
```
- Name: "id", Type: string, Example: "1"
<br>The unique identifier for the specific peggo pass.

- Name: "type", Type: string, Example: "Full Fare"
<br>The type of peggo pass.

- Name: "colour", Type: string, Example: "Orange"
<br>The colour representing which year the pass is valid for.

- Name: "passenger_type", Type: string array, Example: "["Seniors", "Youth"]"
<br>The types of passengers that are allowed to use this pass.


**3. Resources for getAllBusRoutes**
```
	"result" : [
		{
			"id",
			"busNumber",
			"routeName",
			"startLocation",
			"endLocation"
		}
	]
```
- Name: "id", Type: string, Example: "5"
<br>The unique identifier of the bus route.

- Name: "busNumber", Type: string, Example: "74"
<br>The number on the busses taking this route.

- Name: "routeName", Type string, Example: "Crosstown East"
<br>The name of the route.

- Name: "startLocation", Type: string, Example: "Polo Park"
<br>The location that the route starts at.

- Name: "endLocation", Type: string, Example: "Westdale"
<br>The location that the route ends at.

## Sample Request with Sample response

1) This is a sample request for ticketFair

https://api.wpg-transit.org/ticketFair/json?age=76

Sample Response: 
```
"result" : {
    "id" : "1",
    "type" : "Senior Fare",
    "cash_price" : "2.50",
    "ticket_price" : "1.33",
    "monthly_pass_price" : "51.05"
},
"status" : "success"
```
2) Sample request and response to peggoPass()

https://api.wpg-transit.org/peggoPass/

Sample Response:
```
"result" : [
    {
        "id" : "1",
        "type" : "Reduced Fare",
        "colour" : "Green",
        "passenger_type" : [
            "Seniors",
            "Youth",
            "Student"
        ]
    },
    {
        "id" : "2",
        "type" : "Full Fare",
        "colour" : "White",
        "passenger_type" : [
            "Full-fare"
        ]
    }
],
"status" : "success"
```

3) Sample request request and response to getAllBusRoutes()

https://api.wpg-transit.org/getAllBusRoutes/

Sample Response:
```
"results" : [
    {
        "id" : "1"
        "busNumber" : "74",
        "routeName" : "Kenaston"
        "startLocation" : "Polo Park", 
        "endLocation" : "University of Manitoba"
    },
    {
        "id" : "2"
        "busNumber" : "75",
        "routeName" : "Crosstown East"
        "startLocation" : "Kildonan Place", 
        "endLocation" : "university of Manitoba"
    },
    {
        "id" : "3"
        "busNumber" : "77",
        "routeName" : "Crosstown North"
        "startLocation" : "Polo Park", 
        "endLocation" : "Kildonan Place"
    },
    {
        "id" : "4"
        "busNumber" : "78",
        "routeName" : "Waverly"
        "startLocation" : "Polo Park", 
        "endLocation" : "Universty of Manitoba"
    },
    {
        "id" : "5"
        "busNumber" : "79",
        "routeName" : "Charleswood"
        "startLocation" : "Polo Park", 
        "endLocation" : "Westdale"
    }
],
"status" : "success"
```
