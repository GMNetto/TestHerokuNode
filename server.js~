var mysql = require("mysql2");
var https = require("https") , fs = require("fs");
var express = require('express');
var app = express();

app.set('port', (process.env.PORT || 5000));

var connection = mysql.createConnection({
    host: 'us-cdbr-iron-east-03.cleardb.net',
    user: 'b56fefe00420cd',
    password: '6e81455e',
    database: 'heroku_6d29352a6951ad0'
});

connection.connect();
app.get('/', function(req, res){
    connection.query('SELECT * FROM USER', function(err, rows){
        console.log(rows);
        res.send('Hello World! ' + rows);
    });
});

//app.listen(app.get('port'));

var server = https.createServer({
  key: fs.readFileSync('private.key'),
  cert: fs.readFileSync('certificate.pem')
}, app).listen(app.get('port'));
