# GroceryApp-Project
# $${\color{red} \textbf{Project GroceryApp}}$$

## ${\color{green} \textbf{DATABASE}}$

**Install MongoDB from Following link**
```
https://www.mongodb.com/docs/manual/tutorial/install-mongodb-on-ubuntu/
```
```
sudo apt-get install gnupg curl
curl -fsSL https://www.mongodb.org/static/pgp/server-8.0.asc | \
   sudo gpg -o /usr/share/keyrings/mongodb-server-8.0.gpg \
   --dearmor
echo "deb [ arch=amd64,arm64 signed-by=/usr/share/keyrings/mongodb-server-8.0.gpg ] https://repo.mongodb.org/apt/ubuntu noble/mongodb-org/8.0 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-8.0.list
sudo apt-get update
sudo apt-get install -y mongodb-org
sudo systemctl start mongod
```
**Log into the Database**
```
mongosh
```
```
use gracerydb;
```
```
db.groceries.find()
```
**NOTE :** if you want to create mongodb server seprately ensure you enlist the mongodbserver ip in server.js files mentioned string if fe , be , db is in same server then do not change anything in the code.

```
// Connect to MongoDB
mongoose.connect("mongodb://IPOfMongoDbServer:27017/grocerydb"
```

## ${\color{green} \textbf{Backend}}$

**Install npm**
```
apt update
apt install npm -y
npm install
```

**install pm2 for daemon service running on server**
```
npm install -g pm2
```
```
pm2 start server.js --name grocery-backend
```
```
pm2 save
```
```
pm2 startup
```
```
pm2 list
```

**run your backend using these commands in runtime but its mostly not needed**
```
npm init -y
npm install express mongoose cors 
node server.js
```

## ${\color{green} \textbf{Frontend}}$
**add the webserver ip in .env file**
```
REACT_APP_API_URL=http://webserverpublicIP:5000
```
**Install npm**
```
apt update
apt install npm -y
npm install 
```
**( if you want to host with npm)**
```
npm start
```
**HOSt**
```
IpofFrontendServer:3000
```
**If You want to deploy Frontend on ${\color{green} \textbf{NGINX}}$**

**Build the code**
```
npm run build
```
**Copy all the data of build in the html Directory**
```
apt install nginx -y
```
cp -r build/* /var/www/html
```

**HOSt**
```
IpofFrontendServer
```
