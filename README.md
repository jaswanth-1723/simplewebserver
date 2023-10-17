# EX01 Developing a Simple Webserver
## Date:

## AIM:
To develop a simple webserver to serve html pages.

## DESIGN STEPS:
### Step 1: 
HTML content creation.

### Step 2:
Design of webserver workflow.

### Step 3:
Implementation using Python code.

### Step 4:
Serving the HTML pages.

### Step 5:
Testing the webserver.

## PROGRAM:
```
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<!DOCTYPE html>
<html>
<head>
<title>My webserver</title>
</head>
<body>
<h1>Top 5 Revenue Generating Software Companies<h1>
</body>
<ul>
    <li>Accenture</li>
    <li>TCS</li>
    <li>Zoho</li>
    <li>Infosys</li>
    <li>Cognizent</li>
</ul>
</html>
"""
class myhandler(BaseHTTPRequestHandler):
    def do_GET(self):
        print("request received")
        self.send_response(200)
        self.send_header('content-type', 'text/html; charset=utf-8')
        self.end_headers()
        self.wfile.write(content.encode())
server_address = ('',8000)
httpd = HTTPServer(server_address,myhandler)
print("my webserver is running...")
httpd.serve_forever()
```

## OUTPUT:
![input](https://github.com/jaswanth-1723/simplewebserver/assets/127680667/39102018-ce21-49c0-9359-e71f6bfdfb98)

![out](https://github.com/jaswanth-1723/simplewebserver/assets/127680667/3dcf1f5c-5aa7-4678-b5ef-b022a9fca9dd)



## RESULT:
The program for implementing simple webserver is executed successfully.
