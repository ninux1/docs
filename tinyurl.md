Tiny url requirements

Functional Requirements

* Input full url and output is shortened URL.
* Providing the end point where the full URL's are received.
* When the user clicks the tiny url , it should be redirected to actual url.
* Links will expire after certain time.


Non Functional reqs.
* The solution has to scalable, i.e should scale up Or Down as required.
* The solution should be highly available.
* Load balancing should be there with replication.
* Database to store shortened url to full url.
* Will use Hash to serach and locate url's for redirection.

Extended Requirements 
* Analytics : How many times the redirection happend.
* This service should also expose rest endpoint, to be usable by other services.

