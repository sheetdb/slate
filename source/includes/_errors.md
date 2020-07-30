# HTTP Status Codes

Each response is in JSON format. Of course, there is a status code in each response. Here is the list of available response codes:


Status Code | Meaning
---------- | -------
200 OK | The request has succeeded for GET, PUT, PATCH and DELETE requests.
201 Created | The request has succeeded for POST requests.
400 Bad Request | API could not understand the request.
401 Unauthorized | An error with authorization using a Google account or incorrect credentials for API if Basic Auth is enabled.
402 Payment Required | Payment is required to process the request.
403 Forbidden | Action is forbidden.
404 Not Found | The server did not find anything matching the request.
429 Too Many Requests | Exhausted limit requests. [Check API limits](#api-limits)
500 Internal Server Error | We had a problem with our server. Try again later.
1015 Rate limit | You are making too much requests, limit is 60 requests per 10 seconds. Try again in a minute.
