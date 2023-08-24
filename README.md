# Simple Notes App Deployed on AWS EC2
This is a simple notes app built with React and Django.

## Requirements
1. Python 3.9
2. Node.js
3. React
4. Docker
5. AWS  Linux EC2 instance
6. Docker Hub 

## AUTOMATION CI/CD
```
CODE --> clone through github
 
BUILD --> build through docker

PUSH --> pushed to docker hub

DEPLOY --> deployed on 8000 port on AWS EC2
```

## Nginx

Install Nginx reverse proxy to make this application available

`sudo apt-get update`
`sudo apt install nginx`