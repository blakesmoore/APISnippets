# Get Auth Token

```
USERNAME="_USER_NAME_HERE_"
APIKEY="_API_KEY_HERE_"
curl -s -d \
'{
    "auth":
    {
       "RAX-KSKEY:apiKeyCredentials":
       {  
          "username": "'"$USERNAME"'",  
          "apiKey": "'"$APIKEY"'"}
    }  
}' \
-H 'Content-Type: application/json' \
'https://identity.api.rackspacecloud.com/v2.0/tokens' | python -m json.tool
```
