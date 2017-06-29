#	INTRODUCTION
Sound exists in space. Sometimes. And NASA has released a series of space sounds via sound cloud. We have abstracted away some of the hassle in accessing these sounds, so that developers can play with the audio files. For example, a useful application would be an automatic filter to identify human voices in these audio files.

As part of testing this API, Below are the scenarios

# PURPOSE OF THIS DOCUMENT
The purpose of this document is put down scenarios to test below API

https://api.nasa.gov/planetary/sounds

This document covers basic scenarios to test the above mentioned API. This Covers Manual and Automated Tests

Given Information:

HTTP REQUEST

GET https://api.nasa.gov/planetary/sounds

QUERY PARAMETERS

Parameter |	Type | Default | Description
--------- | ---- | ------- | ------------
q | string | None | Search text to filter results
limit | int | 10 | number of tracks to return
#api_key | string | DEMO_KEY | api.nasa.gov key for expanded usage

EXAMPLE 	QUERY


https://api.nasa.gov/planetary/sounds?q=apollo&api_key=DEMO_KEY

#	MANUAL TESTING

### Scenarios:

* Testing the Api with below Test data individually
* Testing the Api with below Test data by taking combination of two parameters
* Testing the Api with below Test data by taking all the three combination at a time

  1. Query with q = Null
  2. Query with q = Meaningful String
  3. Query with q = Invalid String
  4. Query with q = Integer
  5. Query without q(field/parameter) - String
  6. Query without limit(field/parameter)
  7. Query with limit - As int
  8. Query with limit - As 0
  9. Query with limit - As -1
  10. Query with limit - As 1
  11. Query with limit - As 10
  12. Query with limit - As 100
  13. Query with limit - As 101
  14. Query with limit - As String
  15. Query without api_key field/parameter
  16. Query with api_key = DEMO_KEY
  17. Query with api_key = Null
  18. Query with api_key = Invalid String
  19. Query with api_key = Integer
  20. Query with api_key = "" or ""="" -- Sql Injection
  21. Query with api_key = 1=1 -- Sql Injection
  
 With all the above mentioned Test data and Test scenarios, it is expected to produce the resulsts in Positive test cases and give meaningful information as response for invalid data / scenarios.

## Tests Not covered:

The results obtained from the primary query are not in turn tested again.

#	AUTOMATED TESTING

Below are Positive and Negative test cases covered in Automation testing. Responses for each test data is captured, only response code is logged for failed test cases. Response code and response are captured and printed in the log for positive test cases.

###  Negative Test cases:

Query with q = Null

https://api.nasa.gov/planetary/sounds?q=

Query with q = Meaningful String

https://api.nasa.gov/planetary/sounds?q=apollo

Query with q = Invalid String

url=https://api.nasa.gov/planetary/sounds?q=xyz

Query with q = Integer

url=https://api.nasa.gov/planetary/sounds?q=123

Query without q(field/parameter) - String

url=https://api.nasa.gov/planetary/sounds?api_key=DEMO_KEY&limit=20

Query with limit - As int

url=https://api.nasa.gov/planetary/sounds?limit=20

Query with limit - As 0

url=https://api.nasa.gov/planetary/sounds?limit=0

Query with limit - As -1

url=https://api.nasa.gov/planetary/sounds?limit=-1

Query with limit - As 1

url=https://api.nasa.gov/planetary/sounds?limit=1

Query with limit - As 10

url=https://api.nasa.gov/planetary/sounds?limit=10

Query with limit - As 100

url=https://api.nasa.gov/planetary/sounds?limit=100

Query with limit - As 101

url=https://api.nasa.gov/planetary/sounds?limit=101

Query with limit - As String

url=https://api.nasa.gov/planetary/sounds?limit=abc

Query without api_key field/parameter

url=https://api.nasa.gov/planetary/sounds?q=AllMissions&limit=20

Query with api_key = DEMO_KEY

url=https://api.nasa.gov/planetary/sounds?api_key=DEMO_KEY

Query with api_key = Null

url=https://api.nasa.gov/planetary/sounds?api_key=

Query with api_key = Invalid String

url=https://api.nasa.gov/planetary/sounds?api_key=DEMO_KEYasdf

Query with api_key = Integer

url=https://api.nasa.gov/planetary/sounds?api_key=123

Query with api_key = "" or ""="" -- Sql Injection

url=https://api.nasa.gov/planetary/sounds?api_key=""

Query with api_key = 1=1 -- Sql Injection

url=https://api.nasa.gov/planetary/sounds?api_key="1=1"

Test With Invalid Parameters

url=https://api.nasa.gov/planetary/sounds?q=xyz&api_key=Test&limit=abc

### Positive Test Cases:

Query without limit(field/parameter)

url=https://api.nasa.gov/planetary/sounds?q=AllMissions&api_key=DEMO_KEY

Test With Valid Parameters

url=https://api.nasa.gov/planetary/sounds?q=AllMissions&api_key=DEMO_KEY&limit=20

Test With All Three Parameters

url=https://api.nasa.gov/planetary/sounds?q=apollo&api_key=DEMO_KEY&limit=70 
