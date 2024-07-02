## Introduction:

* 👋 Hey everyone! Welcome back to my GitHub.
* 🎥 This repo shows you how to deploy a website using Docker Compose and a Node.js script for the deployment.
* 📊 Node.js is an open-source JavaScript runtime built on Chrome's V8 engine, enabling server-side scripting for scalable, data-intensive applications.

## Prerequisites:
* 💻 A computer with Docker and Docker Compose installed.
* 📁 Basic understanding of Docker and command-line interface.

## Steps:
**1. Get the codes/scripts from this repo.**

git clone https://github.com/Here2ServeU/docker-nodejs-webapp

**2. Move into the working directory:**
cd docker-nodejs-webapp  

**3. Build and Run Docker Compose:**
docker-compose build
docker-compose up

**4. Validate:**
* Open your browser and go to http://localhost:3000 🌐.
* If you did not change the code, you should see your website live with a message like this: "Hello, World, from Dr. Emmanuel here at T2S!"

**5. Clean Up:**
docker-compose down

## Troubleshooting:
* 🚨 Make sure Docker is running and you have sufficient resources allocated.
* 🛠️ Check container logs using docker logs <container_name> if something goes wrong. Use this command, "docker-compose logs myapp." Replace 'myapp' with the name of your application. 


## Outro:
* 🎉 Congrats! You have successfully deployed a website built on a node.js script and using Docker Compose.
* 💬 Leave any questions or comments down below, and I'll be happy to help!
