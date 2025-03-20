Name: A Ahil Santo

Register Number: 212224040018

# 2a_Stop_and_Wait_Protocol

## AIM 
To write a python program to perform stop and wait protocol
## ALGORITHM
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM

Server.py

```
import socket
s=socket.socket()
s.bind(("localhost",8000))
s.listen(5)

c,add=s.accept()
while True:
    
    i=input("Enter a data:" )
    c.send(i.encode())
    ack=c.recv(1024).decode()
    if ack:
        print(ack)
        continue
    else:
        c.close()
        break

```

Client.py

```
import socket
s=socket.socket()
s.connect(("localhost",8000))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Recived".encode())

```
## OUTPUT

Server Side

![server](https://github.com/user-attachments/assets/d701b824-1238-4d72-9101-77ac9f25990e)

Client

![client](https://github.com/user-attachments/assets/fe90f24d-5844-453a-b646-1c64fd1b654b)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
