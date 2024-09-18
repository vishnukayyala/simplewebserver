# Developing a Simple Webserver
## AIM:
To develop a simple webserver to serve html pages.

## DESIGN STEPS:
### Step 1: 
HTML content creation
### Step 2:
Design of webserver workflow
### Step 3:
Implementation using Python code
### Step 4:
Serving the HTML pages.
### Step 5:
Testing the webserver

## PROGRAM:
```
from http.server import HTTPServer,BaseHTTPRequestHandler

content='''
<!doctype html>
<html>
<head>
<title> My Web Server</title>
</head>
<body>
<h1>Top Five Web Application Development Frameworks</h1>
<h2>1. Django</h2>
<h2>2. MEAN Stack</h2>
<h2>3. React</h2>
<h2>4. Ruby on Rails </h2>
<h2>5. Spring </h2>
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
![image](https://github.com/rakeshcoder2004/simplewebserver/assets/121490890/6a7e1544-fafd-4f82-8c26-7b8c66d3ffa0)

### Client Output:

![image](https://github.com/rakeshcoder2004/simplewebserver/assets/121490890/acc7a76e-ea6f-4c49-932f-623b63a75c16)




## RESULT:
The program for implementing simple webserver is executed successfully.

