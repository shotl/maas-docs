## Detail

!!! api "Related endpoint"
    [GET /v1/rides/{id}](https://app.swaggerhub.com/apis-docs/Shotl-transportation/maas/1.0.0-draft#/Ride/getRide)
    
You can retrieve the detail from a ride once it's created. Please note that an unconfirmed ride (draft)
may take removed from our system if it hasn't been confirmed after a time (time specified by area configuration).

## Vehicle assigned

!!! api "Related endpoint"
    [GET /v1/rides/{id}/vehicle](https://app.swaggerhub.com/apis-docs/Shotl-transportation/maas/1.0.0-draft#/Ride/getRideVehicle)
    
Shotl algoritms may change the assigned vehicle at any moment if they consider it more efficient. 
It's recommended to check it periodically. On the other hand, it can be null if there is no vehicle assigned.

## Vehicle's location

!!! api "Related endpoint"
    [GET /v1/rides/{id}/vehicle-location](https://app.swaggerhub.com/apis-docs/Shotl-transportation/maas/1.0.0-draft#/Ride/getRideVehicleLocation)
    
Location is being reported by the vehicle once the ride's status is [DRIVER_LAUNCHED or ONBOARD](status-and-transitions.md). 
Any other status will result as a null as response.

## Predicted times

!!! api "Related endpoint"
    [GET /v1/rides/{id}/predictes-times](https://app.swaggerhub.com/apis-docs/Shotl-transportation/maas/1.0.0-draft#/Ride/getRidePredictedTimes)
    
Predicted times may differ from desired and scheduled times depending on traffic conditions or any other reason. 
It is recommended to let the user know this information for a better experience.

## Route

!!! api "Related endpoint"
    [GET /v1/rides/{id}/route](https://app.swaggerhub.com/apis-docs/Shotl-transportation/maas/1.0.0-draft#/Ride/getRideRoute)
    
This is the route since the user is being picked up by the vehicle until it has reached its destiny. 
It includes all stops during the journey.

## Status

!!! api "Related endpoint"
    [GET /v1/rides/{id}/status](https://app.swaggerhub.com/apis-docs/Shotl-transportation/maas/1.0.0-draft#/Ride/getRideStatus)
    
It's a simple shortcut to see the [current status](status-and-transitions.md) of the ride.
