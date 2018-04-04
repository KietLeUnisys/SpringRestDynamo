###Running DynamoDB Locally
Initialize the database before running the project. In localdynomo directory, we have the jar file for DynamoDB
#####Start Dynamo Locally
```java -Djava.library.path=./DynamoDBLocal_lib -jar DynamoDBLocal.jar -sharedDb```

#####Create Customer Database
```aws dynamodb create-table --table-name Customer --attribute-definitions AttributeName=Id,AttributeType=S --key-schema AttributeName=Id,KeyType=HASH --provisioned-throughput ReadCapacityUnits=1,WriteCapacityUnits=1 --endpoint-url http://localhost:8000```

###Running The Project
``./gradlew bootRun``
###

###How to use the project
Base Url will be http://localhost:8080/

#####Initialize the data
```http://localhost:8080/save```
#####Find All Data
```http://localhost:8080/findalll```
#####Find By Id 
```http://localhost:8080/findbyid?id=<string id>```
#####Delete All
```http://localhost:8080/delete```

#####Check DynamoDB Table
```http://localhost:8000/shell```