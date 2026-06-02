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
