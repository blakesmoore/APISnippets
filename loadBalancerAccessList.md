# Load Balancer Accesslist Snippets

All of the below snippets assume the following varibles are set:

```
DDI="RACKSPACE DDI"
REGION="IAD"
LB_URL="https://$REGION.loadbalancers.api.rackspacecloud.com/v1.0/$DDI/loadbalancers"
LB_ID="Load Balacner ID"
AUTHTOKEN="_AUTH_TOKEN_"
```

# Adding an IP to an access list

```
curl -s -X POST \
  -H "X-Auth-Token: $AUTHTOKEN" \
  -H "Content-type: application/json" \
  -d \
  '{
    "accessList": [
        {
            "type": "DENY", 
            "address": "12.34.56.78"
        }
    ]
}' \
  "${LB_URL}/${LB_ID}/accesslist" | python -m json.tool
```

# Displaying current access list

```
curl -s -X GET \
  -H "X-Auth-Token: $AUTHTOKEN" \
  -H "Content-type: application/json" \
  "${LB_URL}/${LB_ID}/accesslist" | python -m json.tool
```

# Delete specific network from access list

```
NETWORK_ID="accessListID"
curl -s -X DELETE \
  -H "X-Auth-Token: $AUTHTOKEN" \
  -H "Content-type: application/json" \
  "${LB_URL}/${LB_ID}/accesslist/$NETWORK_ID"
```

# Delete entire access list

```
curl -s -X DELETE \
  -H "X-Auth-Token: $AUTHTOKEN" \
  -H "Content-type: application/json" \
  "${LB_URL}/${LB_ID}/accesslist/"
```
