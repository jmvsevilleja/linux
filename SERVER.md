
Start a demo server

`python3 -m http.server 8000`

Create network
`ncat -l 9999`
Connect network
`ncat localhost 9999`

Host IP
`hosts www.google.com`

Host IP and DNS IP
`nslookup www.google.com`

Connect Web Server
`ncat 127.0.0.1 8000`

`GET / HTTP/1.1`
`Location: http://www.google.com/`

`HTTP/1.1 307 Temporary Redirect`
`Location: https://www.eff.org/`


Check Own open Ports
`sudo netstat -plunt`


Find out the process ID
`sudo lsof -i :5955`

Kill Port
`sudo kill -9 PID`
