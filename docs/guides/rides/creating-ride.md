## List rides

!!! api "Related endpoint"
    [POST /v1/rides](https://app.swaggerhub.com/apis-docs/Shotl-transportation/maas/1.0.0-draft#/Ride/createRide)
    
A ride have to pass through a serie of steps to be confirm. The first one would be generate a draft in order to
quote it and inform to the passenger about pickup time, drop-off time, pricing, etc.


There are two types of rides:

| Type          | Description |
| ------------- | ----------- |
| RIDE_NOW      | Rides on demand that can be requested at any moment (within service hours) |
| SCHEDULE_RIDE | Rides within the next 15 natural days considering the day when the petition is made (petition_time) as day 1 |


This endpoint will respond with all the relevant data of the passenger's ride such as the place of the pick-up location
(remember bus stops / virtual stops), the expected times and information about the payment, if applicable.

## Confirmation

!!! api "Related endpoint"
    [POST /v1/rides/{ride-id}/confirm](https://app.swaggerhub.com/apis-docs/Shotl-transportation/maas/1.0.0-draft#/Ride/confirmRide)
    
Once the passenger receive a quote (draft), if it is ok with the conditions, it can be confirmed with a simple
request to our api endpoint. 

This action will generate a different action depending if it's a RIDE_NOW or a SCHEDULE_RIDE. If it's the first one 
or it's a schedule ride within the next 2 hours, it will appear on the driver roadmap immediately. Otherwise it will
be informed to our driver's roadmap no earlier before two hours for the pickup time. 
More information [here](/rides/status-and-transitions).

## Cancel a ride

!!! api "Related endpoint"
    [POST /v1/rides/{id}/cancel](https://app.swaggerhub.com/apis-docs/Shotl-transportation/maas/1.0.0-draft#/Ride/cancelRide)

Cancels a ride. A ride can be cancelled at any moment if the status is `scheduled`, `driver_launched` or `user_launched`. Otherwise, it won't be possible.
