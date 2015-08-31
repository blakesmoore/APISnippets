# Adding an IP to an access list

```
DDI="RACKSPACE DDI"
REGION="IAD"
LB_URL="https://$REGION.loadbalancers.api.rackspacecloud.com/v1.0/$DDI/loadbalancers"
LB_ID="Load Balacner ID"
OS_AUTH_TOKEN="_AUTH_TOKEN_"
curl -s -X POST \
  -H "X-Auth-Token: $OS_AUTH_TOKEN" \
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
