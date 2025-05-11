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

/backend
├── /node_modules
├── /models
│   └── bol.js
├── /routes
│   └── bolRoutes.js
├── .env
├── .gitignore
├── package-lock.json
├── package.json
├── server.mjs
└── readme.md


coding:
server.mjs Overview
In this file, I set up an Express.js server, loaded environment variables with dotenv, and enabled CORS and JSON parsing. I also connected to a MongoDB database using Mongoose (defaulting to bol-system), and added a test route at / that just returns "BOL Tracker API".
I then mounted the BOL-related routes under /api/bols and set the server to run on process.env.PORT or 3000 if not specified.

Bol.js Overview
In this file, I defined the BOL schema using Mongoose. The schema includes the following fields:

loadNumber (String): A required and unique field to identify the BOL.
date (Date): Defaults to the current date when a BOL is created.
shipper (String): A required field for the shipper’s name.
consignee (String): A required field for the consignee’s name.
rate (Number): A required field to specify the rate.
miles (Number): Optional field for the miles.
status (String): An enumerated field that can be "Pending", "Paid", or "Disputed", defaulting to "Pending".
Finally, I exported the model so it can be used in the routes.

bolRoutes.js Overview
In this file, I created the routes for handling BOL CRUD operations:

GET /api/bols: Retrieves all BOLs from the database, sorted by date in descending order (newest first).
GET /api/bols/:id: Retrieves a single BOL by its ID. If the BOL is not found, it returns a 404 error.
POST /api/bols: Creates a new BOL. The status defaults to "Pending" if not provided. If there's a validation error, it returns a 400 error.
PUT /api/bols/:id: Updates an existing BOL by its ID. If the BOL doesn't exist, it returns a 404 error.
DELETE /api/bols/:id: Deletes a BOL by its ID. If the BOL doesn't exist, it returns a 404 error.
The routes handle error responses with appropriate status codes (e.g., 500 for server errors, 400 for validation errors) and return JSON data.

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



