# MongoDB Start
```
brew services start mongodb-community@8.0
```

# MongoDB Start Check

```
brew services list
```

# MongoDb Connection Check

```
mongosh
```
if Success
Response : 

```
Current Mongosh Log ID: 1234567890
Connecting to: mongodb://127.0.0.1:27017
```
# MongoDb Show Db
```
show dbs
```

# MongoDb Create Admin
```
use admin
db.createUser({
  user: "admin",
  pwd: "****",
  roles: [{ role: "root", db: "admin" }]
})
```
# Open config MongoDb

```
nano /opt/homebrew/etc/mongod.conf

```
or 
```
mongod --config
```
# Open Auth
```
security:
  authorization: enabled
```
# Restart MongoDb
```
brew services restart mongodb-community
```

# Connection 
```
mongosh -u admin -p "***" --authenticationDatabase admin
```

# Read MongoDb Data 
```
db.table_name.find()
```
# Deleted .json

```
db.table_name.updateMany(
    { file_name: { $regex: /\.json$/ } },
    [{ $set: { file_name: { $replaceOne: { input: "$file_name", find: ".json", replacement: "" } } } }]
);
```

# Update data
```
db.Accounts.updateOne(
  { _id: ObjectId("67b726a9ead060976ed454e3") }, 
  { $set: { file_name: "account8" } }
)
```

# List Database Table

```
show collections

```















