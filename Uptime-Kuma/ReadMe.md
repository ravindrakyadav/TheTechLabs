A fancy self-hosted monitoring tool. It  is a great way to monitor your servers & self hosted services.

https://github.com/louislam/uptime-kuma


Features: 
--

- Monitoring uptime for HTTP(s) / TCP / HTTP(s) Keyword / Ping / DNS Record / Push / Steam Game Server / Docker Containers.
- Fancy, Reactive, Fast UI/UX.
- Notifications via Telegram, Discord, Gotify, Slack, Pushover, Email (SMTP), and 90+ notification services, click here for the full list.
- 20 second intervals.
- Multi Languages
- Multiple Status Pages
- Map Status Page to Domain
- Ping Chart
 - Certificate Info
- Proxy Support
- 2FA available


## 🔧 How to Install
https://github.com/louislam/uptime-kuma/wiki/%F0%9F%94%A7-How-to-Install


### 🐳 Docker

docker run -d --restart=always -p 3001:3001 -v uptime-kuma:/app/data --name uptime-kuma louislam/uptime-kuma:1 

⚠️ Please use a **local volume** only. Other types such as NFS are not supported.

Browse to [http://localhost:3001](http://localhost:3001/) after starting.



### 💪🏻 Non-Docker

Required Tools:

Node.js >= 14
Git
pm2 - For run in background

# Install required packages

sudo apt install npm git -y


# Update your npm to the latest version
npm install npm -g

git clone https://github.com/louislam/uptime-kuma.git

cd uptime-kuma

npm run setup

## Option 1. Try it
node server/server.js

## Option 2. (Recommended)  Run in background using PM2

### Install PM2 if you don't have it: 
npm install pm2 -g && pm2 install pm2-logrotate

### Start Server
pm2 start server/server.js --name uptime-kuma

Browse to http://localhost:3001 after starting.


## Listen to different port or hostname
pm2 start server/server.js --name uptime-kuma -- --port=80 --host=0.0.0.0


## More useful PM2 Commands

pm2 start uptime-kuma

pm2 stop uptime-kuma

pm2 restart uptime-kuma

### If you want to see the current console output
pm2 monit


### If you want to add it to startup
pm2 save && pm2 startup


