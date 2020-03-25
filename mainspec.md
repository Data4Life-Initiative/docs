# Covid-19 MapView Project



## Background
This is the first requirement spec to build an open source project towards citizens to view covid-19 infected areas. 

Selected data entry admins are able to input geo-data could be used to:
1. Sanitize the places continuously by authorities
2. People can view places based on color codes so they can avoid it
3. Find potential outbreak hotspots. If the route maps in the past 10 days for 5 community spread patients (where index patient is not known) intersects at a supermarket, it could potentially mean that say the cashier is an asymptomatic spreader or there is some place in that supermarket which has not been sanitized.

## User roles
The following user roles shall be supported:
1. Super admins 
2. Data entry admins: group of restricted volunteers who are allocated specific geo-areas. 
3. Users: Anyone who uses the map

## Use Cases
### Data Entry
Here, the Data entry admins are able to perform the following functions: 
1. Enter geo-data of an affected area(s) that can be used by Google Map APIs
2. Enter a sanitised area that can be marked as sanitised bringing the severity down to 1
3. Shall be able to correct any errors. 

### System 
The system shall be able to:

1. Mark color code severity in the range 1-5 based on the number of cases.
2. Mark an area as a potential outbreak hotspot. If the route maps in the past 10 days for 5 community spread patients (where index patient is not known) intersects at a supermarket, it could potentially mean that say the cashier is an asymptomatic spreader or there is some place in that supermarket which has not been sanitized

### Map View
Users are able to view google maps similar to traffic views. They are able to see streets marked in 5 different colors that shows how safe it is to use the area. 

## Requirements
All requirements are handled via [issues](https://github.com/covid-19-mapview/docs/issues).

