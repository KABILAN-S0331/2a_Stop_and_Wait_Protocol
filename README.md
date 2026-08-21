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
## CLIENT
```
import socket 
s=socket.socket() 
host='127.0.0.1'
port=8080
s.bind((host,port)) 
s.listen(5) 
c,addr=s.accept()
while True:
    i=input("Enter Ram's script: ")
    c.send(i.encode())
    ack=c.recv(1024).decode()
    if ack: 
        print(ack) 
        continue
    else: 
        c.close() 
        break
```
## SERVER
```
import socket 
s=socket.socket() 
host='127.0.0.1'
port=8080
s.connect((host,port)) 
while True:
    print(s.recv(1024).decode())
    s.send("Dialogue Completed.".encode())
```
## OUTPUT
## SERVER
<img width="581" height="162" alt="image" src="https://github.com/user-attachments/assets/424ef80a-ae90-427e-9d0c-94350effd1ad" />

## CLIENT
<img width="785" height="251" alt="image" src="https://github.com/user-attachments/assets/ac5f13db-6b84-4c9e-a151-e66e061a0e46" />

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
