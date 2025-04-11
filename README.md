# Fetch Take Home Exercise

Requirements
---
- Must use either the provided Go or Python code as your starting point
- Must accept a YAML configuration as command line argument
- YAML format must match that in the sample provided
- Must accurately determine the availability of all endpoints during every check cycle
- Endpoints are only considered available if they meet the following conditions
- Status code is between 200 and 299
- Endpoint responds in 500ms or less
- Must determine availability cumulatively
- Must return availability by domain
- Must ignore port numbers when determining domain
- Check cycles must run and log availability results every 15 seconds regardless of the number of endpoints or their response times
---

## Getting started
To run this code you need to have following packages installed on your machine.

- Python
  ```
  python --version
  Python 3.10.5
  ```
- Pip
  ```
  python -m pip --version
  pip 25.0.1 
  ```
- Requests library
  ```
  python -m pip show requests
  Name: requests
  Version: 2.32.3
  Summary: Python HTTP for Humans.
  Home-page: https://requests.readthedocs.io
  Author: Kenneth Reitz
  Author-email: me@kennethreitz.org
  License: Apache-2.0
  Location: c:\users\19295\appdata\local\programs\python\python310\lib\site-packages
  Requires: certifi, charset-normalizer, idna, urllib3
  Required-by:
  ```
- PyYaml package
  ```
  python -m pip show pyyaml  
  Name: PyYAML
  Version: 6.0
  Summary: YAML parser and emitter for Python
  Home-page: https://pyyaml.org/
  Author: Kirill Simonov
  Author-email: xi@resolvent.net
  License: MIT
  Location: c:\users\19295\appdata\roaming\python\python310\site-packages
  Requires:
  Required-by: ansible-core
  ```

## File Structure 
- main.py -- File with the main script which will execute to determine availability for URL
- sample.yaml -- File with sample yaml data which will be given as parameter to main.py

## Code Changes
---
Following changes were made in the code to generate desired output
- In function check_health
  - Method will get the value from yaml but since it is optional field the missing value will be treated as 'GET'
  - Headers is an optional field it is set to {} if there is no HTTP body included in request
  - There is a if-else loop which will check if the body is present in the yaml file and based on that it will generate the response which will be checked for its status code.

## Code Execution

To execute the code run the following command
```
python main.py sample.yaml
```
**Sample output**
```
dev-sre-take-home-exercise-rubric.us-east-1.recruiting-public.fetchrewards.com has 25% availability percentage
---
dev-sre-take-home-exercise-rubric.us-east-1.recruiting-public.fetchrewards.com has 25% availability percentage
---
dev-sre-take-home-exercise-rubric.us-east-1.recruiting-public.fetchrewards.com has 25% availability percentage
---
dev-sre-take-home-exercise-rubric.us-east-1.recruiting-public.fetchrewards.com has 25% availability percentage
---
```
**Terminate code**  
To terminate the code press ctrl+c and it should stop the execution giving you an output message like:  
**Monitoring stopped by user.**
