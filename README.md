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
##CLIENT
```PY
import socket
s=socket.socket()
s.bind(('localhost', 8000))
s.listen(5)
c,addr=s.accept()
while True: 
    i=input("Enter a data: ")
    c.send(i.encode())
    ack=c.recv(1024).decode()
    if ack:
        print(ack)
        continue
    else:
        c.close()
        break
```
##SERVER
```PY
import socket
s=socket.socket()
s.connect(('localhost', 8000))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Recived".encode())
```

## OUTPUT
##CLIENT OUTPUT
![client](https://github.com/Reklies/2a_Stop_and_Wait_Protocol/assets/147139232/9630e2f2-10e1-4112-9693-4050fcdd331e)
##SERVER OUTPUT
![server](https://github.com/Reklies/2a_Stop_and_Wait_Protocol/assets/147139232/f98e5de8-b152-41d3-8ceb-e89bb054b7d9)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
