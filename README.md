### 2a_Stop_and_Wait_Protocol
### AIM 
To write a python program to perform stop and wait protocol
### ALGORITHM
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
   
### PROGRAM:

## Client output:
```
import socket
s=socket.socket()
s.bind(('localhost',8000))
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
## Server Output:
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
 print(s.recv(1024).decode())
 s.send("Acknowledgement Recived".encode())
```
### OUTPUT

## Client Output:
![Client](https://github.com/ROHITHTHUKKARAM/2a_Stop_and_Wait_Protocol/assets/159523335/fe18db4c-753f-4cb3-99ba-2e76b2dbdfcc)
## Server Output:
![server](https://github.com/ROHITHTHUKKARAM/2a_Stop_and_Wait_Protocol/assets/159523335/09f44d89-207b-4de5-90b1-7c05c514d219)
![Screenshot 2024-03-01 123337](https://github.com/ROHITHTHUKKARAM/2a_Stop_and_Wait_Protocol/assets/159523335/527612bc-1b5f-43a6-a642-8db01b3769f5)

### RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
