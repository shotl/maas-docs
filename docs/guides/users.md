## Obtain list of users

!!! api "Related endpoint"
[GET /v1/users](https://app.swaggerhub.com/apis-docs/Shotl-transportation/maas/1.0.0-draft#/User/getUsers)

Returns the list of users of a particular area

## Obtain user information

!!! api "Related endpoint"
[GET /v1/users/{id}](https://app.swaggerhub.com/apis-docs/Shotl-transportation/maas/1.0.0-draft#/User/getUser)

Returns the details of a particular user

## User creation

!!! api "Related endpoint"
[PUT /v1/users/{user_id}](https://app.swaggerhub.com/apis-docs/Shotl-transportation/maas/1.0.0-draft#/User/putUser)

Shotl is a passenger-oriented service, so we need to link each ride with a specific user. In this sense,
we don't require any personal data from your database, but we have to identify them in order to give service to
them when arrive to the vehicle. To accomplish with it, we have an idempotent endpoint that you can always call
you need. We advice you to use it each time you use our service.

![](../assets/images/user-registration.png)

!!! tip "Working on"
Some times you don't want to manage users, but rather act as a proxy between them and the different
mobility solutions. We are working to enable you to connect them without having to manage any data.
