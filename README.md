# nodejs_default_setup_with_mongodb


1) npm init 
2) make app.js --- and paste below app.js content
3) npm install express
4) npm install mongodb
5) node app.js


**#app.js**

const express = require('express')
const app = express()
const port = 4010

//app.get('/', (req, res) => {
//  res.send('Hello World!')
//}

const MongoClient = require('mongodb').MongoClient;
const assert = require('assert');

// Connection URL
const url = 'mongodb://demo_user:9dr5wvfzcs8VTRdrsusbCEEsu7gvbsv@127.0.0.1:27017/demo_db'

//var url = "mongodb://localhost:27017/";

MongoClient.connect(url, function(err, db) {

if (err) throw err;
  var dbo = db.db("demo_db");
  dbo.createCollection("customers", function(err, res) {
    if (err) throw err;
    console.log("Collection created!");
    db.close();

  });

}); 

app.listen(port, () =>{
  console.log(`Example app listening at http://localhost:${port}`)
})


**#app.js**

