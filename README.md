# EX01 Developing a Simple Webserver
## Date:15.04.2025

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
    <title>TCP/IP Protocol Suite</title>
</head>
<body>
    <h1>TCP/IP Protocol Suite</h1>
    <ul>
        <li><strong>Application Layer</strong>
            <ul>
                <li>HTTP, HTTPS</li>
                <li>FTP, TFTP</li>
                <li>SMTP, POP3, IMAP</li>
                <li>DNS</li>
                <li>Telnet, SSH</li>
            </ul>
        </li>
        <li><strong>Transport Layer</strong>
            <ul>
                <li>TCP</li>
                <li>UDP</li>
            </ul>
        </li>
        <li><strong>Internet Layer</strong>
            <ul>
                <li>IP (IPv4, IPv6)</li>
                <li>ICMP, IGMP</li>
                <li>ARP</li>
            </ul>
        </li>
        <li><strong>Network Access Layer</strong>
            <ul>
                <li>Ethernet</li>
                <li>Wi-Fi</li>
                <li>PPP</li>
            </ul>
        </li>
    </ul>
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
![alt text](<Screenshot (3).png>)

![alt text](<Screenshot (4).png>)
## RESULT:
The program for implementing simple webserver is executed successfully.
