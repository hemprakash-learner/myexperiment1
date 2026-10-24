# EX01 Developing a Simple Webserver
## Date:15/10/2026
## REG NO:26016351

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
~~~
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>TCP/IP Protocol Suite</title>
<style>
  body { font-family: system-ui, Arial, sans-serif; max-width: 900px; margin: 2rem auto; padding: 0 1rem; line-height: 1.5; }
  .scroll { overflow-x: auto; }
  table { border-collapse: collapse; width: 100%; }
  th, td { border: 1px solid #ccc; padding: .6rem .8rem; text-align: left; vertical-align: top; }
  th { background: #1f4e79; color: #fff; }
  tbody tr:nth-child(even) { background: #f3f6fa; }
  td.layer { font-weight: 600; white-space: nowrap; }
</style>
</head>
<body>

<h1>TCP/IP Protocol Suite</h1>

<!-- TABLE FORMAT -->
<div class="scroll">
<table>
  <thead>
    <tr><th>Layer</th><th>Protocol</th><th>Full name</th><th>Purpose</th></tr>
  </thead>
  <tbody>
    <tr><td class="layer" rowspan="10">Application</td><td>HTTP/HTTPS</td><td>Hypertext Transfer Protocol (Secure)</td><td>Web page transfer</td></tr>
    <tr><td>FTP</td><td>File Transfer Protocol</td><td>File transfer between hosts</td></tr>
    <tr><td>SMTP</td><td>Simple Mail Transfer Protocol</td><td>Sending email</td></tr>
    <tr><td>POP3</td><td>Post Office Protocol v3</td><td>Downloading email</td></tr>
    <tr><td>IMAP</td><td>Internet Message Access Protocol</td><td>Accessing email on a server</td></tr>
    <tr><td>DNS</td><td>Domain Name System</td><td>Resolving names to IP addresses</td></tr>
    <tr><td>DHCP</td><td>Dynamic Host Configuration Protocol</td><td>Automatic IP address assignment</td></tr>
    <tr><td>Telnet / SSH</td><td>Telnet / Secure Shell</td><td>Remote login</td></tr>
    <tr><td>SNMP</td><td>Simple Network Management Protocol</td><td>Network device management</td></tr>
    <tr><td>TFTP</td><td>Trivial File Transfer Protocol</td><td>Simple file transfer</td></tr>

    <tr><td class="layer" rowspan="2">Transport</td><td>TCP</td><td>Transmission Control Protocol</td><td>Reliable, connection-oriented delivery</td></tr>
    <tr><td>UDP</td><td>User Datagram Protocol</td><td>Fast, connectionless delivery</td></tr>

    <tr><td class="layer" rowspan="6">Internet (Network)</td><td>IP (IPv4/IPv6)</td><td>Internet Protocol</td><td>Addressing and routing packets</td></tr>
    <tr><td>ICMP</td><td>Internet Control Message Protocol</td><td>Error reporting and diagnostics (ping)</td></tr>
    <tr><td>IGMP</td><td>Internet Group Management Protocol</td><td>Multicast group management</td></tr>
    <tr><td>ARP</td><td>Address Resolution Protocol</td><td>IP address to MAC address mapping</td></tr>
    <tr><td>RARP</td><td>Reverse Address Resolution Protocol</td><td>MAC address to IP address mapping</td></tr>
    <tr><td>IPsec</td><td>Internet Protocol Security</td><td>Encrypted, authenticated IP traffic</td></tr>

    <tr><td class="layer" rowspan="4">Network Access (Link)</td><td>Ethernet</td><td>IEEE 802.3</td><td>Wired LAN framing</td></tr>
    <tr><td>Wi-Fi</td><td>IEEE 802.11</td><td>Wireless LAN</td></tr>
    <tr><td>PPP</td><td>Point-to-Point Protocol</td><td>Direct link between two nodes</td></tr>
    <tr><td>Frame Relay / ATM</td><td>Frame Relay / Asynchronous Transfer Mode</td><td>WAN link technologies</td></tr>
  </tbody>
</table>
</div>

<!-- LIST FORMAT -->
<h2>Same content as a list</h2>
<ul>
  <li><strong>Application layer</strong>
    <ul>
      <li>HTTP/HTTPS</li>
      <li>FTP</li>
      <li>SMTP, POP3, IMAP</li>
      <li>DNS</li>
      <li>DHCP</li>
      <li>Telnet, SSH</li>
      <li>SNMP</li>
      <li>TFTP</li>
    </ul>
  </li>
  <li><strong>Transport layer</strong>
    <ul>
      <li>TCP</li>
      <li>UDP</li>
    </ul>
  </li>
  <li><strong>Internet layer</strong>
    <ul>
      <li>IP (IPv4/IPv6)</li>
      <li>ICMP</li>
      <li>IGMP</li>
      <li>ARP, RARP</li>
      <li>IPsec</li>
    </ul>
  </li>
  <li><strong>Network access layer</strong>
    <ul>
      <li>Ethernet</li>
      <li>Wi-Fi (802.11)</li>
      <li>PPP</li>
      <li>Frame Relay, ATM</li>
    </ul>
  </li>
</ul>

</body>
</html>
"""
class myhandler(BaseHTTPRequestHandler):
    def do_GET(self):
        print("request received")
        self.send_response(200)
        self.send_header('content-type', 'text/html; charset=utf-8')
        self.end_headers()
        self.wfile.write(content.encode())
server_address = ('',880)
httpd = HTTPServer(server_address,myhandler)
print("my webserver is running...")
httpd.serve_forever()
~~~
## OUTPUT:
![alt text](<Screenshot 2026-10-15 142828.png>)
![alt text](<Screenshot 2026-10-15 142858.png>)
![alt text](<Screenshot 2026-10-15 142915.png>)
## RESULT:
The program for implementing simple webserver is executed successfully.

