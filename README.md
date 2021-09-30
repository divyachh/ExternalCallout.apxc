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
