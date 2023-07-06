# nginx-reverse-proxy

Configuring Nginx as Reverse Proxy.
I used a simple javascript app to test our proxy and tried it on a Debian machine you can test whatever machine you want and follow the instruction!

## Installation

first, make sure your repos are up-to-date, and install Nginx!

```bash
# If you're using a Redhat-based machine just use dnf or yum instead of apt
sudo apt update -y && sudo apt install nginx -y
```
then make sure that nginx service is up and running:
```bash
sudo systemctl status nginx
```
if nginx service it's not running just do this!
```bash
sudo systemctl enable --now nginx 
```
then for testing the proxy server type curl 127.0.0.1 or localhost
also, you can type localhost ip to ensure it's running on your favorite internet browser!

then create the javascript app and name that to app.js
as you can guess this is a simple app that listens on port 3000 and prints out "Hello, World!" save the file with ":wq"

then hit this command:
```bash
cd /etc/nginx/conf.d
sudo vim nodeapp.conf
```
copy the contents of nodeapp into it then save it with :wq

# For testing the app
```bash
sudo nginx -t
```
if you saw a successful test then type this.

# to restart the proxy server!
```bash
sudo nginx -s
```
now it's time to test our app! so just type:

```bash
node app.js
```
### hint: make sure nodejs package is already installed on your machine
now if you run again curl localhost or enter localhost ip in your browser you can see the "hello world" so the test succeeded and the app used the nginx!
