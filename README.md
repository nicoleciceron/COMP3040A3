## List of Endpoints with Parameters

1. **ticketFair(age)**<br>
This endpoint takes in age of the user as it's parameter and returns the cost of the ticket which applies to that age group.
1. **peggoPass()** <br>
This endpoint returns all the information about different kinds of bus passes available. 
1. **busInfo()** <br>
This endpoint returns information about all the busses, like their bus number, their start location and their destination

## Sample Request with Sample response

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

3) Sample request request and response to getAllBusRoutes()

https://api.wpg-transit.org/getAllBusRoutes/

Sample Response:


```
"results" : [
    {
        "id" : "1"
        "busNumber" : "74",
        "routeName" : ""
        "startLocation" : "", 
        "endLocation" : ""
    },
    {
        "id" : "2"
        "busNumber" : "75",
        "routeName" : ""
        "startLocation" : "", 
        "endLocation" : ""
    },
    {
        "id" : "3"
        "busNumber" : "76",
        "routeName" : ""
        "startLocation" : "", 
        "endLocation" : ""
    },
    {
        "id" : "4"
        "busNumber" : "78",
        "routeName" : "Pembina"
        "startLocation" : "", 
        "endLocation" : ""
    },
    {
        "id" : "5"
        "busNumber" : "160",
        "routeName" : "Pembina"
        "startLocation" : "", 
        "endLocation" : ""
    }
],
"status" : "success"
```
