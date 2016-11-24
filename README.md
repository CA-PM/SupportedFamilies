# SupportedFamilies
A basic table view stylized to match the default CAPC themes which provides the Metric Family and Vendor Certifications supported for a given device.

![](./screenShot.jpg?raw=true "Example Screenshot")

##Installation Instructions:

1. Copy app to user app directory on CAPC (/opt/CA/PerformanceCenter/PC/webapps/pc/apps/user)
2. Modify/Add Device (router/switch/server) context page tabs
3. Add browser view(s) with height of 600
4. Add URL to app location with key parameters defined (see below)

###CAPC Browser view sample URL:

/pc/apps/user/SupportedFamilies/index.html?id={ItemIdDA}

###Key URL parameters:

id : is the ID of the Device (router/switch/server)

##Application Modifications:

The app can easily be modified to run any OpenAPI query by modifying the "thisQuery" variable and then modify the Table attributes to include the columns provided by the query response.

For example, to modify the table do display a device's ID, Name, IP address, and number of polled items:

<pre><code>
var thisQuery  = "/odata/api/devices?$select=ID,Name,PrimaryIPAddress,PolledItemCount" +
				 "&$filter=((device/ID eq " + getQueryVariable("id") + "))" +
				 "&$format=json&$top=1000";

columns: [
    { data: 'ID', "title": 'Device ID' },
    { data: 'VName', "title": 'Device Name'},
    { data: 'PrimaryIPAddress', "title": 'Device IP Address' },
    { data: 'PolledItemCount', "title": 'Number of polled items' }
]
</code></pre>


===================================================================================

License (refer to license.txt in folder for 3rd party license details)

Copyright (c) 2016 CA Technologies
 
The MIT License

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:
 
The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.
 
THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.

===================================================================================