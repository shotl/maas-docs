We use standard JWT tokens described at [RFC 7519](https://tools.ietf.org/html/rfc7519) to protect our endpoints. 
You'll need credentials, that consist in a username and password, that we
will be happy to share with you ([contact us](mailto:support@shotl.com)). One you have your credentials, you'll need
to generate an access token trough our token endpoint adding 
a [basic authentication](https://en.wikipedia.org/wiki/Basic_access_authentication) in the headers.

## Context and limits
Shotl can work with its own mark or bring a white label to others. Work areas, drivers, service hours, passengers,
etc. are independent of each other, so you will need credentials for each of them that you have access to.

## Security
The generated access token opens our system to perform some actions on behalf of the passengers. Don't store it 
on the client side to avoid a security leak. On the other hand, these tokens have a short expiration
time for minimize the impact of a potential thief.

To reduce its complexity, you can call our token endpoint before starting each new flow with shotl and keep it on 
memory trough all the use case.

!!! api "Related endpoint"
    [POST /v1/token](https://app.swaggerhub.com/apis/Shotl-transportation/maas/1.0.0#/Authentication/generateToken)


