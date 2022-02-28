## Get service hours

!!! api "Related endpoint"
    [GET /v1/service-hours](https://app.swaggerhub.com/apis-docs/Shotl-transportation/maas/1.0.0-draft#/Service%20hours/getServiceHours)

Returns the service hours for general periods (regular days) and exceptional periods (holidays or other special days)

## Obtain settings of a specific area

!!! api "Related endpoint"
    [GET /v1/areas/{id}/settings](https://app.swaggerhub.com/apis-docs/Shotl-transportation/maas/1.0.0-draft#/Areas/getAreaSettings)

Returns the settings of a particular area, the information retrieved is grouped in `contact info`, `passenger settings`,
`ride settings`, `registering settings`

## Get list of areas

!!! api "Related endpoint"
    [GET /v1/areas](https://app.swaggerhub.com/apis-docs/Shotl-transportation/maas/1.0.0-draft#/Areas/getAreas)

Returns the list of areas, each area ise defined by a geo-json polygon

## Get information of a particular area

!!! api "Related endpoint"
    [GET /v1/areas/{id}](https://app.swaggerhub.com/apis-docs/Shotl-transportation/maas/1.0.0-draft#/Areas/getArea)

Returns the geo-json polygon of a particular area

