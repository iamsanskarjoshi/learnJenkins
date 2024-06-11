# Jenkins

## How to Create an API Token in Jenkins
1. Navigate to the Jenkins dashboard.
2. Click on your username in the top right corner to go to your user configuration page.
3. Click on Configure in the left-hand menu.
4. Click on Add new Token.
5. Provide a name for the token and click Generate.
6. Copy the generated token and store it securely


## Trigger Jenkins Job using curl 
```bash
curl -s -X POST -u "sanskar:1179e500a9f2b218b3ea44292d892bd4f4" "http://localhost:8080/job/test/build"
```

## Trigger Jenkins Job using Python 
```python
import requests
from requests.auth import HTTPBasicAuth

# Jenkins credentials
username = 'sanskar'
api_token = '1179e500a9f2b218b3ea44292d892bd4f4'

# Jenkins job URL
jenkins_url = 'http://localhost:8080/job/test/build'

# Trigger the Jenkins job
response = requests.post(jenkins_url, auth=HTTPBasicAuth(username, api_token))

if response.status_code == 201:
    print('Job triggered successfully!')
else:
    print(f'Failed to trigger job. Status code: {response.status_code}')

```