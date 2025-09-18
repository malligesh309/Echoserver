# Echoserver
Echo server and client using python socket

# AIM:

To develop a simple webserver to serve html programming pages.

## DESIGN STEPS:

### Step 1:

Design of echo server and client using python socket

### Step 2:

Implementation using Python code

### Step 3:

Testing the server and client 

## PROGRAM:
###name: Malligesh M
###register number: 212223230119
server.py
```
import socket

# Create a TCP/IP socket
server_socket = socket.socket(socket.AF_INET, socket.SOCK_STREAM)

# Bind the socket to an address and port
server_socket.bind(('localhost', 12345))
server_socket.listen(1)

print("Server is listening on port 12345...")

# Wait for a connection
conn, addr = server_socket.accept()
print(f"Connected by {addr}")

while True:
    data = conn.recv(1024)
    if not data:  # If no data, client closed connection
        break
    print(f"Received from client: {data.decode()}")
    conn.sendall(data)  # Echo back the same data

conn.close()
```
client.py
```
import socket

# Create a TCP/IP socket
client_socket = socket.socket(socket.AF_INET, socket.SOCK_STREAM)

# Connect to the server
client_socket.connect(('localhost', 12345))

while True:
    msg = input("Enter message (type 'exit' to quit): ")
    if msg.lower() == 'exit':
        break
    client_socket.sendall(msg.encode())
    data = client_socket.recv(1024)
    print(f"Echo from server: {data.decode()}")

client_socket.close()
```

## OUTPUT:
<img width="811" height="659" alt="Screenshot 2025-09-18 091615" src="https://github.com/user-attachments/assets/1e2aa660-ea7f-4df9-99cf-038128f80b9a" />


<img width="807" height="656" alt="Screenshot 2025-09-18 091603" src="https://github.com/user-attachments/assets/61a92524-64ac-42cd-beb8-25cebbb1bfd7" />

## RESULT:
The program is executed successfully
