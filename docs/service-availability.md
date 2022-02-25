Our service depends on from multiple operators and their availability. In order to check if Shotl can give service to
the passenger, you can ask us given the specific coordinates for a specific pick-up and drop-off and it will respond 
with a single boolean (one request by type).

## Service availability

!!! api "Related endpoint"
    [GET /v1/availability](https://app.swaggerhub.com/apis-docs/Shotl-transportation/maas/1.0.0-draft#/Ride/getAvailability)


## Health status

!!! api "Related endpoint"
    [GET /v1/health](https://app.swaggerhub.com/apis-docs/Shotl-transportation/maas/1.0.0-draft#/Health/healthCheck)

You can also retrieve the health status of the whole service, in this request you can see the different services that 
compose the maas api and their status. 
The following table illustrates this

| Service    | Description                                                                                       |
|------------|---------------------------------------------------------------------------------------------------|
| Middleware | Handles permissions, legal documents and errors                                                   |                                           |
| Rides      | Contains all the functionality related to rides, like reserves, routes, vehicles & payments       |
| Users      | Microservice that performs user-related tasks like authentication & register and user-preferences |
