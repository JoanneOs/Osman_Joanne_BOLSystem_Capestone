mkdir backend
cd backend
npm init -y

npm install express mongoose dotenv cors

json scripts: 
 "main": "server.js",  updated
  "type": "module",   added
"start": "node server.mjs",
"dev": "nodemon server.mjs",

mkdir data models routes
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



