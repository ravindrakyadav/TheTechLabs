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


# 🔧 How to Install
--------------------
https://github.com/louislam/uptime-kuma/wiki/%F0%9F%94%A7-How-to-Install


## 🚀 Installer via CLI
------------------------
[Ubuntu/CentOS] Interactive CLI installer, supports Docker or without Docker.

curl -o kuma_install.sh http://git.kuma.pet/install.sh && sudo bash kuma_install.sh


# Advanced Installation
-----------------------
## 🐳 Docker

### Create a volume (only when this is your first docker image/ container)
---------------------------------------------------------------------------
docker volume create uptime-kuma


### Start the container
-----------------------
docker run -d --restart=always -p 3001:3001 -v uptime-kuma:/app/data --name uptime-kuma louislam/uptime-kuma:1 

⚠️ Please use a **local volume** only. Other types such as NFS are not supported.

Browse to [http://localhost:3001](http://localhost:3001/) after starting.




## 💪🏻 Non-Docker (Recommended for x86/x64 only)
------------------------------------------------
A fresh install of linux OS on system or in Virtual environment. (Eg. Debian, Ubuntu, CentOS, etc.) 

### After fresh install, update and upgrade repository and packages
-----------------------------------------------------------------------
sudo apt update && sudo apt upgrade -y



### Following tools are required to run Uptime-Kuma:
----------------------------------------------------

Node.js >= 14

Git

pm2 - For run in background



### Installation of required packages
-------------------------------------
sudo apt install npm git sudo nano curl -y


### Update your npm to the latest version
-----------------------------------------
sudo npm install npm -g

git clone https://github.com/louislam/uptime-kuma.git

cd uptime-kuma

sudo npm run setup                   
      (if an error appears that higher version of nodejs is required then follow as below else skip and move to step through option 2 below)
                (To update nodejs to 18.x run the following commands)
                  sudo apt update
                  curl -sL https://deb.nodesource.com/setup_18.x | sudo bash -
                  sudo apt install -y nodejs
                  node -v



### Option 1. to try 
--------------------
node server/server.js


### Option 2. (Recommended)  Run in background using PM2
--------------------------------------------------------

#### Install PM2 if you don't have it: 

sudo npm install pm2 -g  && sudo pm2 install pm2-logrotate

#### Start Server

pm2 start server/server.js --name uptime-kuma

Browse to http://localhost:3001 after starting.



- Now create your first Admin user and password to login into web console of Uptime Kuma
- In dashboard, now start creating servers and services credentials to monitor via Uptime Kuma
- Finally the dashboard displays the live status that you wishe to monitor.



....Done



================================================================================================================
# Optional Configuration & Commands 
-----------------------------------

### Listen to different port or hostname (optional)
---------------------------------------------------
pm2 start server/server.js --name uptime-kuma -- --port=80 --host=0.0.0.0


### More useful PM2 Commands

pm2 start uptime-kuma

pm2 stop uptime-kuma

pm2 restart uptime-kuma

### If you want to see the current console output
pm2 monit


### If you want to add it to startup
pm2 save && pm2 startup


