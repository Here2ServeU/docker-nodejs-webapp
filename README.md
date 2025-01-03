## Introduction:

* 👋 Hey everyone! Welcome back to my GitHub.
* 🎥 This repo shows you how to deploy a website using Docker Compose and a Node.js script for the deployment.
* 📊 Node.js is an open-source JavaScript runtime built on Chrome's V8 engine, enabling server-side scripting for scalable, data-intensive applications.

---

## Prerequisites:
* 💻 A computer with Docker and Docker Compose installed.
* 📁 Basic understanding of Docker and command-line interface.

## Steps:
**1. Get the codes/scripts from this repo.**
```bash
git clone https://github.com/Here2ServeU/docker-nodejs-webapp
```
**2. Move into the working directory:**
```bash
cd docker-nodejs-webapp  
```
**3. Build and Run Docker Compose:**
```bash
docker-compose build
docker-compose up
```
**4. Validate:**
* Open your browser and go to http://localhost:3000 🌐.
```text
If you did not change the code, you should see your website live with this message: "Hello, World, from Dr. Emmanuel here at T2S!"
```
**5. Clean Up:**
```bash
docker-compose down
```
---

## Troubleshooting:
* 🚨 Make sure Docker is running, and you have sufficient resources allocated.
* 🛠️ Check container logs using docker logs <container_name> if something goes wrong. Use this command, "docker-compose logs myapp." Replace 'myapp' with the name of your application. 


## Outro:
* 🎉 Congrats! You have successfully deployed a website built on a node.js script and using Docker Compose.
* 💬 Leave any questions or comments below; I'll be happy to help!
