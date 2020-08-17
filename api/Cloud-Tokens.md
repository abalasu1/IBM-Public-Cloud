# Get IBM cloud bearer token for api calls

- Create a service ID for making API Calls
![Service ID](https://user-images.githubusercontent.com/13202504/90374520-40302c00-e091-11ea-89ba-df1b7e1204d3.png)

- Associate a API key with the service ID
![API Key](https://user-images.githubusercontent.com/13202504/90374706-88e7e500-e091-11ea-8392-d27c7dcdf57b.png)

- Assign appropriate access policies/access group
![Assign Access](https://user-images.githubusercontent.com/13202504/90374809-b0d74880-e091-11ea-93ed-cda1abb4553c.png)

- Execute api call to get IBM Cloud bearer token
```
curl -k -X POST \
  -H "Content-Type: application/x-www-form-urlencoded" \
  -H "Accept: application/json" \
  --data-urlencode "grant_type=urn:ibm:params:oauth:grant-type:apikey" \
  --data-urlencode "response_type=cloud_iam" \
  --data-urlencode "apikey=<api-key>" \
  "https://iam.cloud.ibm.com/identity/token" | jq . { access_token }
```