mkdir backend
cd backend
npm init -y

npm install express mongoose dotenv cors

json scripts: 
 "main": "server.js",  updated
  "type": "module",   added
"start": "node server.mjs",
"dev": "nodemon server.mjs",

mkdir models routes
touch .env .gitignore server.mjs

touch models/Bol.js
touch routes/bolRoutes.js

.gitignore:
.env
node_modules/

.env:
PORT=
MONGODB_URI=

git init

git add .
git commit -m "Initial backend structure with models and routes"

git remote add origin https://github.com/JoanneOs/Osman_Joanne_BOLSystem_Capestone.git
git branch -M main
git push -u origin main

npm run dev

Post man:
GET: 
http://localhost:3000/api/bols

POST: body raw json
http://localhost:3000/api/bols
Content-Type: application/json
{
  "loadNumber": "LOAD123",
  "shipper": "Shipper A",
  "consignee": "Consignee B",
  "rate": 1500,
  "miles": 300,
  "status": "Pending"
}

GET: http://localhost:3000/api/bols6820016ba80cc2c433c888eb

PUT:
http://localhost:3000/api/bols6820016ba80cc2c433c888eb
{
  "status": "Paid",
  "rate": 1700
}

DELETE:
http://localhost:3000/api/bols/6820024fa80cc2c433c888f3



