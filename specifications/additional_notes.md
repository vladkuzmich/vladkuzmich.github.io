# Additional notes on implementation

The developer's main objective is the delivery of a RESTful web API that matches the OpenAPI specification given [here](open_api_spec.yml). Note that this will involve creating a data pipeline that will be transform the data so that it is in a suitable format to be delivered in by the API.

In addition to the information in the OpenAPI specification, BARB have the following requirements.


### Service
- Speed: The API should be to deliver the data in a reasonable amount of time. For example, each of the endpoints `advertising_spots`, `programme_ratings` and `impacts_over_time` should be able to deliver a day's worth of data within 2-3 seconds.
- Security and access: The webAPI should be secure (OAuth 2 access) and it should be possible to grant different levels of access to users.
- Notifications: It should be possible to send push notifications to users to alert them to the fact that the data available at an endpoint has been updated .

### Documentation

The OpenAPI specification contains various links to additional reference material (for example BARB station codes.) Web pages containing this information should be part of the API implementation


### Enhancements to the data (not for phase I)

The following data enhancements need to be reviewed by BARB and may form part of later phases.

- Sky asked whether there would be the need to calculate derived audiences from the
API in the same way that is currently the case for database 2 (e.g. Women = Adults-Men,
C2DE Adults = Adults-ABC1 Adults).
- BARB will soon be receiving a datafeed from MetaBroadcast. We have included a placeholder object called MetaBroadcastInformation within the ProgrammeContent. BARB and the developer will need to decide how the MetaBroadcast data is to be integrated with the current content metadata.
