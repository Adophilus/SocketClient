# SocketClient
A simple socket client class for python


Usage
-----

```
# client.py script
from SocketServer import SocketServer

# The client soket
client = SocketClient();

# callback definition
def onConnect (connected, err):
	if connected:
		print("Connection successful!");
	else:
		print("Connection failed!");

def onReceive (data, err):
	if data:
		print("No data receieved!");
		print(err);
	else:
		print("Received data from server!");
		print(data);
		
def onSend (data, err):
	if data:
		print("An error occurred while sending data.");
		print(err);
	else:
		print("successfully sent data to server!");

# assigning the callbacks
client.connect(onConnect);
client.onReceive(onReceive);
client.onSend(onSend);

# send welcome message to the serevr
client.send("Hello server! I've arrived");
client.receive(_async = False); # Wait for a message
```