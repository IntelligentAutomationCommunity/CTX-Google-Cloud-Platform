# CTX-Google-Cloud-Platform
Cortex subtasks to interact with the Google Cloud Platform APIs.
To use any of these subtasks, import the relevant Cortex Studio package into your Cortex environment, and set the Cortex Studio authorisations appropriately.

## CTX-GCP-Generate-Map
This subtask generates HTML to include a Google Map in a Cortex LivePortal GUI.

It takes the following input parameters:
Parameter | Description
---------------------------------|---------------------------------------------------------------------------|
**i_HTML** | (Optional) Any HTML to which the map HTML will be appended |
**i_map-name** | (Optional) The name of the map. Multiple maps may be displayed on the same LivePortal GUI, but each must have a unique name. |
**i_latitude** | The latitude coordinates on which the map will be centred, and where the location pin will be dropped
**i_longitude** | The longitude coordinates on which the map will be centred, and where the location pin will be dropped
**i_zoom-level** | The zoom level for the map
**i_GCP-API-key** | The API key provided by the Google Cloud Platform; for more information, see https://developers.google.com/maps/documentation/embed/get-api-key


The output parameter **o_HTML** should be included in a LivePortal Literal Function Block where the map will be displayed.
