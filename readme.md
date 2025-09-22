# Project Management Tool

![Full-Stack-CRUD-WebApp](CRUD.gif)

A web-based project management application built with **React** and **Ant Design (antd)** to simplify team collaboration and task tracking. The application provides an intuitive interface for managing projects, assigning developers, and monitoring progress.

## Features
- **Project CRUD**: Create, read, update, and delete projects.
- **Developer Assignment**: Assign team members to specific projects.
- **Interactive UI**: Ant Design table and slider for efficient project tracking.
- **Search & Pagination**: Quickly find projects and navigate large datasets.
- **Responsive Design**: Optimized for smooth usage across devices.

## Stack
**Frontend**: React.js, Javascript
**Backend**: Node.js Express, Javascript

“This project does not use a database. CRUD operations are implemented using custom JSON logic in React state.”

## How to install 
```
**Project tree**

Root folder
├── backend
│   ├── database
│   ├── product
│   ├── server.js
│   └── swaggerDoc.json
├── frontend
│   ├── public
│   ├── src
│   ├── package-lock.json
│   └── package.json
├── .gitignore
├── package-lock.json
├── package.json
└── README.md 

```
This repository consists of a frontend and a backend folder. 
To run without error, you need to install node modules for both frontend and backend.


### Order of the installation

#1 Install backend node module
1. Make sure you are in the root folder directory
2. Run terminal, and type npm install and press enter
	> npm install
3. Confirm that node_modules folder is created
4. Now you installed node_modules for backend

#2 Install frontend node module
1.  At the terminal, move to frontend folder 
      > cd frontend
2. Type npm install and press enter
	 > npm install
3.  Confirm that node_modules folder is created in frontend folder
4.  Move to the root folder, using cd command
5.  At the root folder, run npm start command
	> npm start
6. It will run at http://localhost:3001/ on your browser

## Troubleshooting 

1.  "react-scripts": "5.0.1" warning issue solution

	* After you installed both frontend and backend's node modules Please go to frontend directory> node modules> react-scripts 
	* Find config > webpackDevServer.config.js
	* In the file, you can see two functions 'onBeforeSetupMiddleware' , 'onAfterSetupMiddleware'
	* Remove them and copy below code under the return scope.
	```
	setupMiddlewares: (middlewares, devServer) => {
      if (!devServer) {
          throw new Error('webpack-dev-server is not defined')
      }
  
      if (fs.existsSync(paths.proxySetup)) {
          require(paths.proxySetup)(devServer.app)
      }
  
      middlewares.push(
          evalSourceMapMiddleware(devServer),
          redirectServedPath(paths.publicUrlOrPath),
          noopServiceWorkerMiddleware(paths.publicUrlOrPath)
      )
  
         return middlewares;
      }
	```
	

    * Make sure there are no warnings

2. Normal issue's solutions

	* Make sure you type 'npm start' at root folder
	* Make sure there are no other applications are running on port 3000, 3001
	* If npm start is not working, you need to run each backend and frontend using different command at the root folder
		* At the root folder, type npm run server and confirm server is running on port 3000
			 > npm run server 
		* Open another terminal, type 'npm run client' and confirm that application is running on localhost:3001
			> npm run client
	* If the port is already used
		* this will list all PID listening on this port, once you have the PID you can terminate it with the following:
			> sudo lsof -i :3000	
		* Terminate the PID
			> kill -9 PIDNUMBER


**You should run backend first and run client**


## Swagger Documentation
After the server is running, you can see at [http://localhost:3000/api/api-docs](http://localhost:3000/api/api-docs).
