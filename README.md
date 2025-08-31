# EX01 Developing a Simple Webserver
## Date:31/08/2025

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
from http.server import HTTPServer, BaseHTTPRequestHandler

content = '''
<html>
<head> <title> data</title>
</head>
<body> 
    <table align="center" border ="1" cellpadding="10">
        <caption>List of protocols in TCP/IP protocol suite</caption>
        <tr><th>S.No</th><th>Name of the layer</th><th>Name of the protocols</th></tr>
        <tr><td>1 </td><td>Application layer</td><td>HTTP,FTP,DNS,Telnet & SSH</td></tr>
        <tr><td>2 </td><td>Transport layer</td><td>TCP/UDP</td></tr>
        <tr><td>3 </td><td>Network layer</td><td>IPV4/IPV6</td></tr>
        <tr><td>4 </td><td>Link layer </td><td>Ethernet</td></tr>
    </table>
</body>
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

![alt text](<Screenshot 2025-08-31 212820.png>)

![alt text](web_exp1.png)

<img width="1918" height="1198" alt="Screenshot 2025-08-31 213248" src="https://github.com/user-attachments/assets/271de416-825f-425c-b6e8-bd26fca08043" />



## RESULT:
The program for implementing simple webserver is executed successfully.
