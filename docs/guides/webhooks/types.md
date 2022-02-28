Events are at the core of webhooks. These webhooks fire whenever a certain action is taken on the vehicle, 
which your server's payload URL intercepts and acts upon.

## Driver is here
The event is being triggered by the driver on arrive to the expected pick-up location. The passenger has a short
time to get on the vehicle.
```json
{
  "id": "string",
  "type": "IM_HERE",
  "created_at": "int64",
  "body": {
    "ride_id": "string",
    "user_id": "string"
  }
}
```

## Passenger no show
The event is being triggered by the driver on a passenger no show. 
```json
{
  "id": "string",
  "type": "NO_SHOW",
  "created_at": "int64",
  "body": {
    "ride_id": "string",
    "user_id": "string"
  }
}
```
