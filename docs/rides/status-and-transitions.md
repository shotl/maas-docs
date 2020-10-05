In order to know how the ride works, it's important to understand the different status that can take along
its life cycle.

| Status      | Description                                                                                             |
| ----------- | ------------------------------------------------------------------------------------------------------- |
| DRAFT       | The passenger has requested a ride but has not confirmed it                                             |
| SCHEDULED   | The passenger has confirmed a ride which is of type SCHEDULE_RIDE and its expected pickup time is more than 2h far from now. The trip does not appear neither in the DriverApp nor the PassengerApp.  
| DRIVER_LAUNCHED | The passenger has confirmed a ride which is of type SCHEDULE_RIDE and its expected pickup time is between 2h and 10 minutes far from now. The trip does appear only in the DriverApp, not in the PassengerApp. The following API endpoints are available |
| USER_LAUNCHED | The passenger has confirmed a ride which is of type RIDE_NOW or is of type SCHEDULE_RIDE and its expected pickup time less than 10 minutes far from now. The trip does appear both in the DriverApp and the PassengerApp |
| CANCELLED | The passenger has cancelled the trip |
| NOSHOW | The passenger did not show up at the pickup station and has not been picked up |
| ONBOARD | The passenger is on board of the vehicle |
| FINISHED | The passenger has finished the trip as expected |
| EARLYDROPOFF | The passenger has finished the trip, asking to leave earlier than expected using the functionality “EARLYDROPOFF” from the driver App |

## Transitions

And these are the transitions allowed for each status:


![](/assets/images/ride-status-map.png)
