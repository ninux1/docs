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
* Will use Hash to search and locate url's for redirection.
* Implement caching for performance

Extended Requirements 
* Analytics : How many times the redirection happend.
* This service should also expose rest endpoint, to be usable by other services.

Database reqs.
* Storing huge number of records.
* Distributed since we need it for billions of records.
* Dynamo Or cassandra a good choice ?

Define the API's after the requirements.
create_url
delete_url
query_url
total_redirects_per_url



