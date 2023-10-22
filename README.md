Terminal 1

```sh
docker build -t docker-image:test .
docker run -p 9000:8080 docker-image:test
```

Terminal 2

```sh
curl "http://localhost:9000/2015-03-31/functions/function/invocations" -d @api-gateway-event-example.json | jq .
```

Should return:

```json
{
  "statusCode": 200,
  "headers": {
    "content-length": "17",
    "content-type": "application/json"
  },
  "multiValueHeaders": {},
  "body": "{\"Hello\":\"World\"}",
  "isBase64Encoded": false
}
```
