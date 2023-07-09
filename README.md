# nginx-reverse-proxy

Configuring Nginx as Reverse Proxy.
I used a simple javascript app to test our proxy and tried it on a Debian machine you can test whatever machine you want and follow the instruction!

## Installation

First, make sure your repos are up-to-date, and install Nginx

```bash
# If you're using a Redhat-based machine just use dnf or yum instead of apt
sudo apt update -y && sudo apt install nginx -y
```
Verify nginx service is up and running
```bash
sudo systemctl status nginx
```
If nginx service it's not running RUN the below command
```bash
sudo systemctl enable --now nginx 
```
Then for testing the proxy server type curl 127.0.0.1 or localhost in the terminal
also, you can type localhost ip to ensure it's running on your favorite internet browser!

Create this simple javascript app with a text editore like vim and name that to app.js
as you can guess this is a simple app that listens on port 3000 and prints out "Hello, World!" save the file with ":wq"

Now RUN the below commands
```bash
cd /etc/nginx/conf.d
sudo vim nodeapp.conf
```
Copy the contents of nodeapp into it then save it with :wq

# For testing the app
```bash
sudo nginx -t
```
if you saw a successful test then type this.

# to restart the proxy server!
```bash
sudo nginx -s
```
Once you are done with the above steps it's time to test our app! so just type

```bash
node app.js
```
### hint: make sure nodejs package is already installed on your machine
Now if you run again curl localhost or enter localhost ip in your browser you can see the "hello world" so the test succeeded and the app used the nginx!

