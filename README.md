# SOCKET.IO

## DAS MEATBALLz CHAT

![DAS MEATBALZ CHAT](https://images-gmi-pmc.edge-generalmills.com/80fd8638-9b0d-4cba-ba99-9c4b75b4a20c.jpg)

Das Meatballz is the premire meatball discussion chat. 

Das Meatballz was created with socket.io.

Socket.IO is a JavaScript library that enables users to send and recieve data in realtime
It uses both ExpressJS / NodeJS for the serverside and ReactJS for the front end.


When a user writes a message it is sent to the server. When the server gets the message it emits that data to the other users. 


###  Load socket.io


npm install --save socket.io

in index.js
````
var http = require('http').Server(app);
var io = require('socket.io')(http);

io.on('connection', function(socket){
  console.log('a user connected');
});

http.listen(3000, function(){
  console.log('listening on *:3000');
});

````
in index.html

````
<script src="/socket.io/socket.io.js"></script>
<script>
  var socket = io();
</script>
````
----------------------------------------------------------

The following code shows a snippit of data is emmited to other users.

````
io.on('connection', function(socket){
  socket.on('chat message', function(msg){
    io.emit('chat message', msg);
  });
});

`````
The emited data is captured by the recieving user and inclueded on their page.


# Hurdles

Emiting messages didnt work.
Solution: link js file.


This tutorial can be found at 
https://socket.io/get-started/chat/
