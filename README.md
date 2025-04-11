** Fetch Take Home Exercise **

Requirements
---
Must use either the provided Go or Python code as your starting point
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

