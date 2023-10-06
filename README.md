# API PHP Functions for DITEL MICRA MAX Panel Meter.
# The package includes a file of functions and examples to test the features of the Micra Max panel meter made by DITEL.

**API REST MICRA MAX**

<a name="_6jynaot9cbnq"></a>Especificaciones
<a name="_xr1uctwau2qt"></a>29 de Junio del 2023 - Alex Rubio

---

1. **Introduction:**

**API Purpose:**
The purpose of this API is to provide a REST application programming interface (API) to facilitate communication and data exchange between different systems. This API has been developed with the objective of allowing developers to access and manipulate certain resources and specific functionalities of our system or application in an efficient and secure manner.

Using this API, developers will be able to integrate and use our functionalities in their own applications, thus taking advantage of the capacity and data of our system in a flexible and personalized way. Additionally, by following REST design principles, our API adheres to widely accepted standards, making it easy to adopt and deploy across diverse environments and platforms.

By providing a REST API, our goal is to encourage the creation of applications and services that can effectively interact with our system. This opens new opportunities for collaboration, innovation and the creation of solutions that improve the user experience and provide greater added value through the integration of our functionalities.

Throughout this documentation, you will find detailed information about available endpoints, request parameters, response formats, required authentication, and recommended best practices to use our API effectively. We hope this documentation is a useful guide so developers can take full advantage of the capabilities of our API and build powerful and innovative applications.

---

**Goals and use cases**

Provide developers with a standardized interface to access and use data generated by probes and sensors connected to Micra MAX.

Facilitate the integration of Micra MAX into existing applications and systems, allowing the exchange of information in real time.

Improve visualization efficiency in capturing, analyzing and displaying data collected by Micra MAX.

Drive innovation by enabling developers to create custom solutions based on information provided by Micra MAX.

---

**Use cases**

Process Monitoring and Control: The API allows developers to obtain real-time data from the probes and sensors connected to Micra MAX, which facilitates the monitoring and control of industrial processes, such as temperature, humidity, pressure, among other critical parameters. .

Integration into Asset Management Platforms: Data from Micra MAX can be used in asset management platforms, allowing users to monitor and manage equipment and systems in real time. For example, the API can be used to receive automatic alerts in case a sensor connected to Micra MAX indicates a problem or a value outside the established limits.

Data Analysis and Report Generation: The API makes it easy to extract data stored in Micra MAX, allowing developers to perform advanced analysis and generate custom reports. For example, sensor data can be used to identify patterns, trends and anomalies, which can be useful in predictive equipment maintenance or process optimization.

These are just a few examples of the goals and use cases that the Micra MAX Connection API can address. By providing an easy-to-use and flexible interface, our API allows developers to take full advantage of the data generated by Micra MAX, opening up a world of possibilities for creating customized solutions and improving efficiency across various sectors and applications.

---

**Authorization:**

Authorization to access the API is done through a Token, which must be included in the request header with the name "X-DTpanel".

The Token or password necessary for authorization is defined within the Micra MAX device.

Importantly, the user has the ability to modify this Token, providing flexibility and control over the security of requests made to the hardware.

To ensure effective and secure communication, it is recommended to generate and use a strong and unique Token.

---

**Communication:**

Communication with the Micra MAX API is done through JSON (JavaScript Object Notation) objects.

Both requests sent and responses received must be in JSON + UTF-8 format to ensure compatibility and ease of data processing.

---

**Application Methods:**

The main commands used in the Micra MAX API are:

1. GET: Used to obtain specific information or data from the probes and sensors connected to Micra MAX.
1. POST: Used to send information or perform specific actions on the Micra MAX hardware.
1. DELETE: Used to delete or deactivate resources or configurations in Micra MAX.

These prerequisites are essential to ensure proper communication with the Micra MAX API. Be sure to comply with authorization by using the Token provided by the computer, and to use the JSON format for requests and responses. Also, familiarize yourself with the main commands (GET, POST and DELETE) to effectively interact with the hardware and obtain the necessary data.

---

**Quick Start Guide:**

Examples with cURL:  
curl -vvv -H 'X-DTpanel: **token**' "192.168.1.208/v1/hello.json"  

curl -X GET "192.168.1.208/v1/hello.json" -H "X-DTpanel: **token**"    
  
**RESPONSE BODY:** *200*  
[{"id": 1,"status":"Hello World"}]

---

**Error Codes or Response Body**
200: Success  
201: Success Creation.  
400: Invalid request  
401: Unauthorized  
404: Resource not found  
  
---

**Endpoints:**

**Send a configuration to the device (POST)**

**/v1/post\_config**

curl -X POST "IP/v1/config"  
-H "X-DTpanel: token"  
-H "Content-type: application/json"  
-d @request\_body  
  
*Where @request\_body = json with the configuration parameters*  
**RESPONSE BODY:** *201

---

**Receive a configuration to the device (GET)**  
**/v1/get\_config**  
curl -X GET "IP/v1/config" -H "X-DTpanel: token"   

**RESPONSE BODY:** *200*  
{  
`  `"inputType": {  
`	`"processInputType": null,  
`	`"loadCellInputType": {  
`  	`"loadCellInputTypeValues": "150mv"  
`	`},  
`	`"thermometerInputType": null  
`  `},  
`  `"display": {  
`	`"optionsOfDisplayConfig": {  
`  	`"decimalsDisplay": 2,  
`  	`"linearisationPoints": 11,  
`  	`"roundingFilter": "01",  
`  	`"balancedFilter": 1  
`	`},  
`	`"values": [  
`  	`{  
`    	`"inputValue": 0,  
`    	`"displayValue": 0  
`  	`},  
`  	`{  
`    	`"inputValue": 0,  
`    	`"displayValue": 0  
`  	`},  
`  	`{  
`    	`"inputValue": 0,  
`    	`"displayValue": 0  
`  	`},  
`  	`{  
`    	`"inputValue": 0,  
`    	`"displayValue": 0  
`  	`},  
`  	`{  
`    	`"inputValue": 0,  
`    	`"displayValue": 0  
`  	`},  
`  	`{  
`    	`"inputValue": 0,  
`    	`"displayValue": 0  
`  	`},  
`  	`{  
`    	`"inputValue": 0,  
`    	`"displayValue": 0  
`  	`},  
`  	`{  
`    	`"inputValue": 0,  
`    	`"displayValue": 0  
`  	`},  
`  	`{  
`    	`"inputValue": 0,  
`    	`"displayValue": 0  
`  	`},  
`  	`{  
`    	`"inputValue": 0,  
`    	`"displayValue": 0  
`  	`},  
`  	`{  
`    	`"inputValue": 0,  
`    	`"displayValue": 0  
`  	`}  
`	`],  
`	`"displayInputError": "off",  
`	`"displayEco": {  
`  	`"ecoState": "off",  
`  	`"ecoValue": 0  
`	`},  
`	`"brightType": "high",  
`	`"tareValue": 1,  
`	`"runModeColor": "green",  
`	`"progModeColor": "orange"  
`  `},  
`  `"setPoints": [  
`	`{  
`  	`"onOffType": "off",  
`  	`"value": 0,  
`  	`"comparisonValue": "net",  
`  	`"actionMode": "high",  
`  	`"noNcType": "no",  
`  	`"colorAlarmType": "noChange",  
`  	`"activationType": "delay",  
`  	`"activationValue": 0  
`	`},  
`	`{  
`  	`"onOffType": "off",  
`  	`"value": 0,  
`  	`"comparisonValue": "net",  
`  	`"actionMode": "high",  
`  	`"noNcType": "no",  
`  	`"colorAlarmType": "noChange",  
`  	`"activationType": "delay",  
`  	`"activationValue": 0  
`	`},  
`	`{  
`  	`"onOffType": "off",  
`  	`"value": 0,  
`  	`"comparisonValue": "net",  
`  	`"actionMode": "high",  
`  	`"noNcType": "no",  
`  	`"colorAlarmType": "noChange",  
`  	`"activationType": "delay",  
`  	`"activationValue": 0  
`	`},  
`	`{  
`  	`"onOffType": "off",  
`  	`"value": 0,  
`  	`"comparisonValue": "net",  
`  	`"actionMode": "high",  
`  	`"noNcType": "no",  
`  	`"colorAlarmType": "noChange",  
`  	`"activationType": "delay",  
`  	`"activationValue": 0  
`	`}  
`  `],  
`  `"rssConfig": {  
`	`"bauds": 9600,  
`	`"id": 1,  
`	`"protocol": "ascii",  
`	`"replyDelay": "no\_delay"  
`  `},  
`  `"ipAddress": null,  
`  `"analogueConfig": {  
`	`"displayHigh": 0,  
`	`"displayLow": 0,  
`	`"overrange": "high"  
`  `},  
`  `"logicFunctionConfig": {  
`	`"pin2": 1,  
`	`"pin3": 2,  
`	`"pin4": 6  
`  `},  
`  `"programmingLockCodeConfig": {  
`	`"code": 0,  
`	`"lkSetPoints1": false,  
`	`"lkSetPoints2": false,  
`	`"lkSetPoints3": false,  
`	`"lkSetPoints4": false,  
`	`"input": false,  
`	`"display": false,  
`	`"analogueOutput": false,  
`	`"rsOutput": false,  
`	`"logicFunctions": false,  
`	`"tareKey": false,  
`	`"directSetpoints": false,  
`	`"brightnessColor": false,  
`	`"filterP": false,  
`	`"maxMin": false  
`  `}  
}  

---
**Receive information from the display (GET)**  
**/v1/get\_display**  
curl -X GET "IP/v1/get\_display" -H "X-DTpanel: **token**"  

---

**Reset tare (POST)**  
**/v1/reset\_tare**  
curl -X POST "IP/v1/reset\_tare" -H "X-DTpanel: **token**"  

---

**Reset Max (POST)**  
**/v1/reset\_max**  
curl -X POST "IP/v1/reset\_max" -H "X-DTpanel: **token**"  

---

**Reset Min (POST)**  
**/v1/reset\_min**  
curl -X POST "IP/v1/reset\_min" -H "X-DTpanel: **token**"  

---

**Tare (POST)**  
**/v1/tare**  
curl -X POST "IP/v1/tare" -H "X-DTpanel: **token**"  

---

**Factory Reset (POST)**  
**/v1/factory\_reset**  
curl -X POST "IP/v1/factory\_reset" -H "X-DTpanel: **token**"  

---

**Obtener información del equipo (GET)**  
**/v1/get\_info**  
curl -X GET "IP/v1/get\_info" -H "X-DTpanel: **token**"  
