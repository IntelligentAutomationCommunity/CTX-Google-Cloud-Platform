# CTX-Google-Cloud-Platform
Cortex subtasks to interact with the Google Cloud Platform APIs.
To use any of these subtasks, import the relevant Cortex Studio package into your Cortex environment, and set the Cortex Studio authorisations appropriately.

## GCP Maps
There are two subtasks to support interacting with the GCP Maps Javascrip API:
1. CTX-GCP-Map-Init
1. CTX-GCP-Map-Add

You must call the first before calling the second. You may call the second as many times as you need. The parameter **o_CTX-GCP-Map-Init-HTML** returned by either subtask
must be passed to each call of the CTX-GCP-Map-Add subtask.

### CTX-GCP-Map-Init
This subtask generates HTML to include a Google Map in a Cortex LivePortal GUI.

It takes the following input parameters:
Parameter | Description
---------------------------------|---------------------------------------------------------------------------|
**i_GCP-API-key** | The API key provided by the Google Cloud Platform; for more information, see https://developers.google.com/maps/documentation/embed/get-api-key

The output parameter **o_CTX-GCP-Map-Init-HTML** should be passed to the first call of the CTX-GCP-Map-Add subtask.

### CTX-GCP-Map-Add
This subtask generates HTML to include a Google Map in a Cortex LivePortal GUI.

It takes the following input parameters:
Parameter | Description
---------------------------------|---------------------------------------------------------------------------|
**i_HTML** | (Optional) Any HTML to which the map HTML will be appended |
**i_map-name** | (Optional) The name of the map. Multiple maps may be displayed on the same LivePortal GUI, but each must have a unique name. |
**i_latitude** | The latitude coordinates on which the map will be centred, and where the location pin will be dropped
**i_longitude** | The longitude coordinates on which the map will be centred, and where the location pin will be dropped
**i_zoom-level** | The zoom level for the map
**_i_class** | (Optional) The class used for the div element containing the map; defaults to col-md-12
**i_style** | (Optional) The style applied to the div element containing the map; defaulst to height=200px;width=200px
**i_CTX-GCP-Map-Init-HTML** | The most receltly returned value of the **o_CTX-GCP-Map-Init-HTML** parameter from using either the CTX-GCP-Map-Init or CTX-GCP-Map-Add subtasks

The output parameters **o_HTML** and **o_CTX-GCP-Map-Init-HTML** should each be included in a LivePortal Literal Function Block where the map will be displayed.
