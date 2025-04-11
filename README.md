# EX01 Developing a Simple Webserver
## Date: 11.04.2025

## AIM:
To develop a simple webserver to serve html pages and display the list of protocols in TCP/IP Protocol Suite.

## DESIGN STEPS:
### Step 1: 
HTML content creation.

### Step 2:
Design of webserver workflow.

### Step 3:
Implementation using Python code.

### Step 4:
Import the necessary modules.

### Step 5:
Define a custom request handler.

### Step 6:
Start an HTTP server on a specific port.

### Step 7:
Run the Python script to serve web pages.

### Step 8:
Serve the HTML pages.

### Step 9:
Start the server script and check for errors.

### Step 10:
Open a browser and navigate to http://127.0.0.1:8000 (or the assigned port).

## PROGRAM:
```
from http.server import HTTPServer,BaseHTTPRequestHandler

content='''
<html>
<head>
<title>TCP/IP PROTOCOLS</title>
</head>
<body><center>
    <h1>TCP/IP Protocol Suite</h1>
    <table border="5" cell panding="1" align="center">
        <tr>
            <th>TCP/IP Layer</th>
            <th>Key Protocols</th>
       </tr>
       <tr>
            <td>Application Layer</td>
            <td>HTTP, HTTPS, FTP, SMTP, POP3, IMAP, DNS, DHCP, TELNET, SNMP</td>
       </tr>
       <tr>
            <td>Transport Layer</td>
            <td>TCP, UDP, SCTP</td>
       </tr>
       <tr>
            <td>Internet Layer</td>
            <td>IP (IPv4, IPv6), ICMP, ARP, IGMP</td>
       </tr>
       <tr>
            <td>Network Access Layer</td>
            <td>Ethernet, Wi-Fi (IEEE 802.11), PPP, Frame Relay, DSL</td>
       </tr>
    </table>
</center>
</body>
</html>
'''

class MyServer(BaseHTTPRequestHandler):
    def do_GET(self):
        print("Get request received...")
        self.send_response(200) 
        self.send_header("content-type", "text/html")       
        self.end_headers()
        self.wfile.write(content.encode())

print("This is my webserver") 
server_address =('',8000)
httpd = HTTPServer(server_address,MyServer)
httpd.serve_forever()
```

## OUTPUT:
![Screenshot 2025-04-11 104228](https://github.com/user-attachments/assets/35f7d509-115a-4060-bff3-c9075f777a51)
![Screenshot 2025-04-11 104322](https://github.com/user-attachments/assets/0b4ee5ff-f2a4-43e8-a06d-e74872a8508e)

## RESULT:
The program for implementing simple webserver is executed successfully.
