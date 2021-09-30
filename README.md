# ExternalCallout.apxc

//Call any api without any request parameter and header parameter
public HttpResponse get(string url)

//Call any api with request parameter and without any header parameter
public HttpResponse get(string url, Map params);

//Call any api with any request parameter and header parameter
public HttpResponse get(string urlornc, Map params,Map headers);

//Call any API to create and update request 
public HttpResponse post(string url,Map headers, Map params);

//Call any delete api
public HttpResponse del(string url,Map headers, Map params);


**Call Shopify API using get method and named credential**

//User name and password - change as per your requirement
Blob headerValue = Blob.valueOf(username + ':' + password);
String authorizationHeader = 'BASIC ' +EncodingUtil.base64Encode(headerValue);

//Create header map 
Map headers=new Map {
'Content-Type' => 'application/json',
'Authorization'=> authorizationHeader
};

//Create url parameter 
Map param=new Map {
'status'=>'any',
'limit'=>1,
'since_id' => '3859435711778'
};

//Call api using params
HttpResponse response=new ExternalCallout().get('Shopify', param,headers);
system.debug(response.getBody());
