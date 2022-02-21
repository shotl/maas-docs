We use conventional HTTP status codes to indicate the success or failure of an API request. 
In general: 

- 2xx indicates success
- 4xx indicates a client error
- 5xx indicates an error from our servers (not normal)

Some 4xx errors that could be handled programmatically include an error code that briefly explains the error reported.

Attributes
-------------
**code** string <br>
For some errors that could be handled programmatically, a short string indicating the error code reported.
-------------
**tag** string <br>
The type of error returned. One of <code>server-error</code>, <code>invalid-request-error</code> or <code>domain-error</code>
-------------
**message** string <br>
A human-readable message providing more details about the error.
-------------
Error Types
-------------
| Type      | Description                                                                                             |
| ----------- | ------------------------------------------------------------------------------------------------------- |
| server-error       | Server errors cover any other type of problem (e.g., a temporary problem with Shotl's servers), and are extremely uncommon.                                             |
| invalid-request-error   | Invalid request errors arise when your request has invalid parameters.
| domain-error | Domain errors cover any type of problem that collides with established business rules (e.g. requesting ride which desired pickup time is out of service hours)

Error Codes
-------------
Some 4xx errors that could be handled programmatically include an error code that briefly explains the error reported. Below is a list of error codes that can be sent as a value for <code>code</code>, with additional information on how to resolve them.

<span class="check-circle-fill">:octicons-check-circle-fill-12:</span> <code>bad-request</code>
:   Invalid request errors arise when your request has invalid parameters.
-------------
<span class="check-circle-fill">:octicons-check-circle-fill-12:</span> <code>resource-not-found</code>
:   Resource not found in the system.
-------------
<span class="check-circle-fill">:octicons-check-circle-fill-12:</span> <code>forbidden-status-transaction</code>
:   The action required for a service generates an invalid status transaction (for example, a ride that is already confirmed, can't be confirmed twice).
-------------
<span class="check-circle-fill">:octicons-check-circle-fill-12:</span> <code>quoted-ride-out-of-hours</code>
:   Service hours will end soon and due to other already confirmed bookings we can't fit the request in.
-------------
<span class="check-circle-fill">:octicons-check-circle-fill-12:</span> <code>overbooking</code>
:   Service is overbooked. Please try again the request in a few minutes.
-------------
<span class="check-circle-fill">:octicons-check-circle-fill-12:</span> <code>area-not-providing-service</code>
:   There is no service configured for the desired pickup time at this area.
-------------
<span class="check-circle-fill">:octicons-check-circle-fill-12:</span> <code>desired-ride-out-of-hours</code>
:   Area is providing service, but the desired pickup time is out of service hours.
-------------
<span class="check-circle-fill">:octicons-check-circle-fill-12:</span> <code>no-online-vehicles-available</code>
:   All the vehicles that should be providing service, are not connected or are out of signal.
-------------
<span class="check-circle-fill">:octicons-check-circle-fill-12:</span> <code>no-show-penalty</code>
:   The passenger in the request didn't show up on their last service. He must wait few minutes for the next request.
-------------
<span class="check-circle-fill">:octicons-check-circle-fill-12:</span> <code>passenger-concurrent-rides</code>
:   The passenger in the request is already using the service.
-------------
<span class="check-circle-fill">:octicons-check-circle-fill-12:</span> <code>shotl-not-possible-same-stop</code>
:   Distance between desired pickup location and desired dropoff location are too short.
-------------
<span class="check-circle-fill">:octicons-check-circle-fill-12:</span> <code>subarea-movement-unavailable</code>
:   Service between the desired pickup location and desired dropoff location are not allowed. There are other bus lines that cover this route.
-------------
<span class="check-circle-fill">:octicons-check-circle-fill-12:</span> <code>confirmation-time-exceeded</code>
:   The maximum time that has been configured to expire an unconfirmed service has been exceeded. Please request the service again.
-------------

!!! tip "Working on"
    We are working to improve this section in order to inform you about the different codes included in our responses 
    to react more suitably to a possible error. 


