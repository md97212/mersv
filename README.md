
Summary:
* Uses Java 11 and H2 in memory DB (included)
* Unzip in to a working directory and cd into `mersv`
* to start the app: either `./gradlew bootRun:start` or `java -jar ./build/libs/mersive-0.0.1-SNAPSHOT.jar` 
* visit `http://localhost:8080/resouce/1` or `http://localhost:8080/image/2`
* For prototype purposes and time constraints used Spring Boot Controllers instead of raw Sockets
* Does `PUT` `GET` `DELETE` on with named resource paths
* To view DB visit `http://localhost:8080/h2-console`, use `jdbc:h2:mem:testdb` as jdbcUrl and `sa`/`password` for DB credentials

Future Work
* Implement in raw sockets for lighter weight footprint if needed
* Add Junit tests as regression tests
* Add Integration tests
* Document API 

#Details:
Supported HTTP Verbs

○ GET: Server should retrieve any data associated with the specified URI.
■ If the request is successful, return HTTP 200 along with any data.
■ If no associated record is found, return HTTP 404.
○ POST: Server should store the MIME type and body data associated with the specified
URI. If the server already had data for this URI, it should be replaced with the new data.
■ If the request is successful, return HTTP 200 and an empty body.
■ If for some reason it is determined that the post cannot be allowed or
completed, return HTTP 403.
○ DELETE: Server should remove any data associated with the specified URI.
■ If the URI exists, remove the data and respond with HTTP 200.
■ If no associated record is found return HTTP 404.
● Supported HTTP Headers
○ Content-Type
■ Referred to also as the MIME type.
■ Specifies the format of the data being sent.
○ Content-Length
■ The length of the content to expect in the HTTP body.
● Features that should not be implemented
○ HTTPS / Security.
○ Any HTTP verb outside of the ones specified above.
○ Any HTTP header outside of the ones specified above.
○ HTTP chunked encoding.
● Additional Requirements
○ The server should ignore any additional HTTP headers provided by client requests.
○ The server should use nothing higher-level than TCP sockets for networking. Do not
use an existing web server library or HTTP parser to handle requests or construct
responses.
○ Any unhandled HTTP verb should return HTTP 405.
○ Include instructions for building and running your solution.
○ Summarize your design, including any tradeoffs, possible improvements, or
performance concerns which may apply.
○ Submit the project in an archive of some format (zip, tar, etc).
○ Please plan an appropriate amount of time to accomplish the goals given in the
summary. For previous submissions, the average is about 5 hours.

