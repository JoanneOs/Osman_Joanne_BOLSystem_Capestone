mkdir backend
cd backend
npm init -y

npm install express mongoose dotenv cors

json scripts: 
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


