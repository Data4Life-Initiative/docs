# Data4Life Project



## Background
This is the first requirement spec to build an open source project towards citizens to:
> 1.	View covid-19 infected areas
> 2.	Perform risk analysis
> 3.	Receive alert notifications if health parameters change

Selected data entry admins are able to input geo-data could be used to:
> 1. 	Sanitize the places continuously by authorities
> 2.	People can view places based on color codes so they can avoid it.
> 3.	Find potential outbreak hotspots. If the route maps in the past 10 days for 5 community spread patients (where index patient is not known) intersects at a supermarket, it could potentially mean that say the cashier is an asymptomatic spreader or there is some place in that supermarket which has not been sanitized.

## User roles
The following user roles shall be supported:
> 1. Super admins 
> 2. Data admins: Group of restricted volunteers who are allocated specific geo-areas. 
> 3. Users: Anyone who uses the map

## Data Sources
There are few different data sources for historic location data:
> 1. Manual data entry
> 2. External data sources: External data sources can be 
> 	  1) Enabling your location data within the client app if you are corona virus quarantined. 2) It could be a telecom operator that shares location data based on user consents 3) Google, Facebook and other 3PP providers. 

Data sources for contact tracing is primarily from Apple and Google

## Use Cases
### Data Entry
Here, the Data entry admins are able to perform the following functions: 
1. Enter geo-data of an affected area(s) that can be used by Google Map APIs
2. Enter a sanitised area that can be marked as sanitised bringing the severity down to 1
3. Shall be able to correct any errors. 

### System 
The system shall be able to:
> 
> 1. Mark color code severity in the range 1-5 based on the number of cases.
> 2. Mark an area as a potential outbreak hotspot. If the route maps in the past 10 days for 5 community spread patients (where index patient is not known) intersects at a supermarket, it could potentially mean that say the cashier is an asymptomatic spreader or there is some place in that supermarket which has not been sanitized

### Map View
Users are able to view google maps similar to traffic views. They are able to see streets marked in 5 different colors that shows how safe it is to use the area. The area ranking algorithms and color coding, please refer to the project specs.

## Requirements

### Functional Requirements 
All requirements are handled via internel project doc in xls. Please check w/ lal@igrant.io.

### Privacy
The solution shall strictly follow the privacy rules where all personal information used and shared shall be done in a transparent manner. Users shall be able to opt out of any purpose (e.g. location tracking) other basic ones used for registration.

Please refer to project spec document for all data usage purposes and attributes etc. 
