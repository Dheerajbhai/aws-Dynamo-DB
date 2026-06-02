Lab 3:->

aws dynamodb create-table  --table-name Notes --attribute-definitions AttributeName=UserId,AttributeType=S AttributeName=NoteId,AttributeType=N --key-schema AttributeName=UserId,KeyType=HASH AttributeName=NoteId,KeyType=RANGE --provisioned-throughput ReadCapacityUnits=5,WriteCapacityUnits=5

aws dynamodb wait table-exists --table-name Notes

aws dynamodb describe-table --table-name Notes | findstr TableStatus

mvn dependency:copy-dependencies
java -cp "target/classes;target/dependency/*" dev.labs.dynamodb.notesLoadData


mvn dependency:copy-dependencies
java -cp "target/classes;target/dependency/*" dev.labs.dynamodb.notesQuery

mvn dependency:copy-dependencies
java -cp "target/classes;target/dependency/*" dev.labs.dynamodb.notesScan

mvn dependency:copy-dependencies
java -cp "target/classes;target/dependency/*" dev.labs.dynamodb.notesUpdate

http://localhost:63342/aws-Dynamo-DB/Lab-DynamoDB/Developing%20on%20AWS%20-%20Lab%203%20(Java)%20-%20Develop%20Solutions%20Using%20Amazon%20DynamoDB%20_%20Self-Paced%20Labs.html?_ijt=u1pd4u1un6fkiha9h4l3s8tq2u&_ij_reload=RELOAD_ON_SAVE
