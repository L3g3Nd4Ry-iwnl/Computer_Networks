# Computer_Networks

## Description
This repository contains my work related to the Computer Networks course in my college. It includes file handling using `pandas` module, socket programming using `TCP, UDP` in `Python` language, Cisco Packet Tracer.

## Contents
1. Basic knowledge on Networking concepts
2. File handling in pandas module

## 1. Basic knowledge on Networking concepts

### TCP
TCP - Transmission Control Protocol
Used to send data which are to be in order, with no loss of data. Internet applications like `WWW, e-mail, FTP, Secure Shell` uses TCP. It is a **connection-oriented** protocol

#### Processes in TCP Server and TCP Client
| Server | Client |
| ------ | ------ |
| Create socket | Create socket |
| Bind socket to (IP, Port) | |
| Listen for new connection | |
| | Connect to the server |
| Accept the connection | |
| Send and receive data | Send and receive data |
| | Close connection |
| Wait for any new connection| Close socket |
| Close socket| |

#### Operations in TCP in Python
1. Create Socket
```python
server_socket=socket.socket(socket.AF_INET, socket.SOCK_STREAM)
```

  In the above line `socket.AF_INET` specifies to make the socket `server_socket` to accept IP's of IPv4 server only, `socket.SOCK_STREAM` specifies that the socket is of **TCP**.

2. Bind Socket to a tuple (IP, Port)
```python
server_socket.bind(('127.0.0.1',42069))
```

  Here `socket.bind()` requires a 2 valued tuple `(IP, Port_number)` since we are using `AF_INET` family, which binds the socket `server_socket` to the specifed IP, Port_number. Generally it has one parameter named *address*.

3. Listen for incoming connections
```python
server_socket.listen(5)
```

  Here `socket.listen()` listens for new connections and has a parameter which is used to specify the number of unaccepted connections that the system will allow before refusing new connections.

4. Accept any incoming connection and do queries
```python
server_socket.accept()
```
  Here  `socket.accept()` accepts any incoming requests and return 2 values namely `(connection, address)` connection is a new socket object and address being the 2 valued tuple mentioned in `socket.bind()`.

5. Sending data to client
```python
client_socket.send()

client_socket.send(bytes("Hello Client!","utf-8"))
````

  The first line is the simple syntax for sending anything to the *client_socket*. In socket programming it is advised to send data in bytes via any encoding, so the order is mainatined. So we use the `bytes()` function and here I have encoded the **ASCII-7** to **UTF-8** format. Other functions like `encode()` can also be used.

6. Recieving data from client
```python
client_socket.recv(1024)

client_socket.recv(1024).decode("utf-8")
```

  Here `socket.recv()` receives data from the socket. It **requires** a paramter which specifies the size in *bytes* to be recieved from the socket and it cannot be **empty**. I usually encode the text in **UTF-8** before sending it, so I have decoded it using `decode()` function in the second line.

7. Close the socket
```python
server_socket.close()
```

  This command is used to close the socket created.


### UDP
UDP - User Datagram Protocol
Used to send data which need not be in order and can have loss of data. `Video streaming, video conferencing` uses UDP. It is a **connection-less** protocol unlike TCP.

#### Processes in UDP Server and UDP Client
| Server | Client |
| ------ | ------ |
| Create socket | Create socket |
| Bind socket to (IP, Port) | |
| Send and receive data | Send and receive data |
| | Close connection |
| Wait for any new connection| Close socket |
| Close socket| |

#### Operations in UDP in Python

1. Create Socket
```python
server_socket=socket.socket(socket.AF_INET, socket.SOCK_DGRAM)
```

  In the above line `socket.AF_INET` specifies to make the socket `server_socket` to accept IP's of IPv4 server only, `socket.SOCK_DGRAM` specifies that the socket is of **UDP**.
  
2. Bind Socket to a tuple (IP, Port)
```python
server_socket.bind(('127.0.0.1',42069))
```

  Here `socket.bind()` requires a 2 valued tuple `(IP, Port_number)` since we are using `AF_INET` family, which binds the socket `server_socket` to the specifed IP, Port_number. Generally it has one parameter named *address*.
 
3.Receive from client
```python
server_socket.recvfrom(1024)
```
 
  Here `socket.recvfrom()` return 2 values `(data, address)` where data is the value received from client and address is the `(IP, Port)` *since IPv4* of the sender. 

4. Sending data to client
```python
server_socket.sendto(message,addr)
```

  Here `socket.sendto()` has 2 parameters `(message, address)` where message needs to be encoded using `encode()` function. The address can be retrieved from the *address* in `recvfrom()`
  
## 2. File handling using pandas

Basics of pandas, where I learnt it was from 

```https://github.com/adeshpande3/Pandas-Tutorial/blob/master/Pandas%20Tutorial.ipynb.```
Thanks @adeshpande3


