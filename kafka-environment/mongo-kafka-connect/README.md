### MongoDB connector


#### Sink for nycdriver my_trip topic
```
curl -X POST http://localhost:8083/connectors -H "Content-Type: application/json" -d '
{
  "name": "mongo-sink2",
  "config": {
    "connector.class": "com.mongodb.kafka.connect.MongoSinkConnector",
    "tasks.max": "1",
    "topics": "my_trip",
    "connection.uri": "mongodb://mongo:27017",
    "database": "my-trip",
    "collection": "events",
    "key.converter": "org.apache.kafka.connect.storage.StringConverter",
    "value.converter": "org.apache.kafka.connect.json.JsonConverter",
    "value.converter.schemas.enable": "false"
  }
}'

```