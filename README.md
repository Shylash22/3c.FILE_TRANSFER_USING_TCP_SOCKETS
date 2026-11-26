# 3c.CREATION FOR FILE TRANSFER USING TCP SOCKETS
## AIM
To write a python program for creating File Transfer using TCP Sockets Links
## ALGORITHM:
1. Import the necessary python modules.
2. Create a socket connection using socket module.
3. Send the message to write into the file to the client file.
4. Open the file and then send it to the client in byte format.
5. In the client side receive the file from server and then write the content into it.
## PROGRAM
## sever
```

import socket

s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
s.bind(('localhost', 8002))
s.listen(1)

print("Server waiting for connection...")
conn, addr = s.accept()
print("Client connected")

filename = input("Enter file name: ")

with open(filename, 'rb') as f:
    data = f.read()

conn.sendall(data)
print("File sent successfully")

conn.close()
s.close()

```
## celint
```
import socket

s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
s.connect(('localhost', 8002))

with open('received_file.txt', 'wb') as f:
    while True:
        data = s.recv(1024)
        if not data:
            break
        f.write(data)

print("File received successfully")

s.close()
```
## OUPUT
## server
<img width="417" height="162" alt="image" src="https://github.com/user-attachments/assets/f3846d52-46b0-4b52-970d-89b28251c1ac" />

## client
<img width="636" height="201" alt="image-1" src="https://github.com/user-attachments/assets/45ad6614-d1a8-4d94-8772-36bb7bc8849a" />

## RESULT
Thus, the python program for creating File Transfer using TCP Sockets Links was 
successfully created and executed.
