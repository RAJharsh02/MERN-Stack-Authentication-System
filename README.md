MERN-Stack-Authentication-System
A full-stack authentication system built with the MERN stack (MongoDB, Express.js, React, Node.js). This project includes a backend API for user authentication and a React-based frontend for the user interface.
Table of Contents

Project Overview
File Structure
Environment Setup
Running the Project
Troubleshooting

Project Overview
This project implements a user authentication system using the MERN stack. The backend handles user registration, login, and JWT-based authentication, while the frontend provides a React-based UI for user interaction. MongoDB Atlas is used as the database, and MongoDB Compass is recommended for database management.
File Structure
The project is organized into two main directories: backend and frontend.


MERN-Stack-Authentication-System/

├── backend/

│   ├── config/              # Configuration files (e.g., database connection)

│   ├── controller/          # Express controllers for handling requests

│   ├── models/              # Mongoose models for MongoDB schemas

│   ├── routes/              # Express routes for API endpoints

│   ├── DS_Store             # macOS system file (can be ignored)

│   ├── .env                 # Environment variables (e.g., MongoDB URI, JWT secret)

│   ├── .gitignore           # Git ignore file

│   ├── index.js             # Backend entry point (Express server)

│   ├── package-lock.json    # NPM lock file for backend dependencies

│   └── package.json         # Backend dependencies and scripts

└── frontend/

    ├── public/              # Static assets for React
    
    ├── src/                 # React source code
    
    ├── .env                 # Environment variables for frontend
    
    ├── .gitignore           # Git ignore file
    
    ├── README.md            # Default Create React App README
    
    ├── package-lock.json    # NPM lock file for frontend dependencies
    
    ├── package.json         # Frontend dependencies and scripts
    
    └── tailwind.config.js   # Tailwind CSS configuration

Environment Setup
Follow these steps to set up the project on your local machine.
Prerequisites

Node.js: Version 14.18.0 or higher (required for superagent@9.0.0+).
MongoDB Atlas: A MongoDB Atlas account for the database.
MongoDB Compass: For database management (optional but recommended).
Homebrew: For macOS users to install dependencies easily.

Step 1: Install Node.js

Check your Node.js version:
node --version

If below v14.18.0, install a newer version:

Using Homebrew (macOS):brew install node


Using nvm:curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash
nvm install node
nvm use node




Verify the installation:
node --version
npm --version



Step 2: Set Up MongoDB Atlas

Create a MongoDB Atlas account at mongodb.com.
Create a cluster and get the connection string (e.g., mongodb+srv://<username>:<password>@cluster0.mongodb.net/<dbname>).
Whitelist your IP address in Atlas under Network Access.
Create a database user under Database Access.

Step 3: Install MongoDB Compass (Optional)
MongoDB Compass is useful for managing your Atlas database.

Install via Homebrew (macOS):brew install --cask mongodb-compass


Verify the installation:/Applications/MongoDB\ Compass.app/Contents/MacOS/MongoDB\ Compass --version


Launch Compass:open /Applications/MongoDB\ Compass.app


Connect to your Atlas cluster using the connection string.

Step 4: Clone the Repository
Clone the project from GitHub

Step 5: Set Up Environment Variables
Backend

Navigate to the backend directory:cd backend


Create a .env file:touch .env


Add the following variables:MONGO_URI=<your-mongodb-atlas-connection-string>
JWT_SECRET=<your-jwt-secret>
PORT=5001


Replace <your-mongodb-atlas-connection-string> with your Atlas connection string.
Replace <your-jwt-secret> with a secure random string for JWT signing.



Frontend

Navigate to the frontend directory:cd ../frontend


Create a .env file:touch .env


Add the following variable:REACT_APP_API_URL=http://localhost:5001



Step 6: Install Dependencies
Backend

In the backend directory:npm install


If you see warnings about deprecated packages (inflight, glob, superagent):npm install superagent@latest glob@latest
npm update


Fix vulnerabilities:npm audit fix

If high-severity vulnerabilities persist, run npm audit for details and manually update affected packages.



Frontend

In the frontend directory:npm install


Address any warnings or vulnerabilities similarly:npm audit fix





Running the Project
Step 1: Start the Backend

In the backend directory:npm start


The backend will run on http://localhost:5001 (or the port specified in .env).



Step 2: Start the Frontend

In the frontend directory:npm start


The React app will run on http://localhost:3000 and open in your browser.



Step 3: Test the Application

Open http://localhost:3000 in your browser.
Register or log in to test the authentication system.
Use MongoDB Compass to inspect your Atlas database.

Troubleshooting

Port 5001 in Use:If port 5001 is occupied:
lsof -i :5001
kill -9 <PID>

Alternatively, change the PORT in backend/.env to another value (e.g., 5002).

MongoDB Compass Errors:If you see mach_port_rendezvous.cc or shared_memory_switch.cc errors:

Grant permissions in System Settings > Privacy & Security > Full Disk Access for /Applications/MongoDB Compass.app.
Temporarily disable Gatekeeper:sudo spctl --master-disable
/Applications/MongoDB\ Compass.app/Contents/MacOS/MongoDB\ Compass --version
sudo spctl --master-enable




NPM Warnings:If deprecated package warnings persist, manually update the affected packages:
npm install <package>@latest


MongoDB Atlas Connection Issues:Ensure your IP is whitelisted in Atlas and your connection string is correct in backend/.env.


**Preview:**
![PHOTO-2025-05-19-17-00-35](https://github.com/user-attachments/assets/a7ccf2dd-98ed-4a51-bbf7-1aa94fdd970d)
![PHOTO-2025-05-19-17-01-15](https://github.com/user-attachments/assets/381439f7-56f5-4ff7-91c9-5df90b5afee3)


**Demo:**
https://mern-stack-authentication-system.vercel.app/


