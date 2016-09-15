# SupportedFamilies
A basic table view stylized to match the default CAPC themes which provides the Metric Family and Vendor Certifications supported for a given device.


Installation Instructions:

1. Copy app to user app directory on CAPC (/opt/CA/PerformanceCenter/PC/webapps/pc/apps/user)
2. Modify/Add Device (router/switch/server) context page tabs
3. Add browser view(s) with height of 600
4. Add URL to app location with key parameters defined (see below)

CAPC Browser view sample URL:

/pc/apps/user/SupportedFamilies/index.html?id={ItemIdDA}

Key URL parameters:

id : is the ID of the Device (router/switch/server)

Application Modifications:

The app can easily be modified to run any OpenAPI query by modifying the "thisQuery" variable and then modify the Table attributes to include the columns provided by the query response.
