# APE
 Angular JS REST client

![Angular JS REST client](https://github.com/Orkiv/ape-js/raw/master/logo.png)

# Install 

#### Via bower

	bower install ape-js

#### Via npm 

	npm install ape-js

Or download the package directly [here](https://github.com/Orkiv/ape-js/archive/master.zip) 

# Getting Started

Insert this tag  after your angularjs initialization :

	<script type="text/javascript" src="bower_components/ape-js/ape.js"></script>
	/*
	OR
	*/
	<script type="text/javascript" src="/ape-js/ape.js"></script>
	/*
	OR
	*/
	<script type="text/javascript" src="node_modules/ape-js/ape.js"></script>



## Injection

	 var myApp = angular.module('myApp', ['Ape']);
	 ...
      myApp.controller('Cntrl', function ($scope, Ape) {
            ...
      });


# Documentation

## Service functions

### Request - function(verb String, url String, parameters Object, callback  function([response](#response), [angular-http-response](https://docs.angularjs.org/api/ng/service/$http) )

Perform an APE request to the desired url.

#### verb 
RESTful verb to use with request.

#### url

API endpoint to call.

#### parameters 

Parameters to send with request. On `PUT` and `POST` requests, explicitly define url based parameters. ie : `http://domain.com/url?param1` 

##### callback

Called once the request is finished,

Checkout this sample [request](#sample-request)

### Init - function(ape [Ape](#ape))

Set a new Ape logic. 

#### ape 

Desired Ape automation parameter set to use.


# Models

## Ape

#### base - String

String to be prepended with each request.

#### headers - Object
Object with header parameters sent with each request.

#### start - function()
Function called prior to each request.

#### end - function([response](#response) ,  [angular-http-response](https://docs.angularjs.org/api/ng/service/$http) )
Function called after each request.

## Response
Response of API request. This varies with the data your endpoint is sending.
** On API error the value of this model will always be `false` .


# Sample request

In the example below a `GET` request is performed to the endpoint `/your/test/endpoint`.

	  Ape.Request("GET", "/your/test/endpoint", {param1: "azert"} , function(data){
                console.log("response => ");
                console.log(data);
              });