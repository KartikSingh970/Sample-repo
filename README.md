# 🌐 AWS-EC2-Webpage

## 🚀 Project Overview
This project demonstrates **manual deployment of a static website** on an AWS EC2 instance. The website contains a simple `index.html` with hover and click effects and is deployed via **git clone from GitHub** using NGINX.

---

## 📁 Repository Structure

AWS-EC2-Webpage/
├── index.html # Main webpage with hover effect
├── index.js # JS file for clickable heading alert
├── README.md # Project documentation
├── OutputAWS.png # Screenshot of deployed site and terminal


---

## 🛠️ Prerequisites

Before deploying, make sure you have:

- 🔹 An **AWS account**  
- 🔹 An **EC2 instance running Ubuntu**  
- 🔹 A **keypair** to connect via SSH  
- 🔹 **NGINX** installed on the instance  
- 🔹 **Git** installed on the instance  
- 🔹 **SSH access** to your EC2 instance  
- 🔹 **GitHub account** with SSH key configured (for cloning repo)

---

## 📝 Steps Performed

### **1️⃣ Connect to EC2 via SSH**

```bash
ssh -i your-key.pem ubuntu@your-ec2-ip

2️⃣ Install NGINX & Git
sudo apt update
sudo apt install nginx git -y


Start NGINX if not running:

sudo systemctl start nginx
sudo systemctl enable nginx

3️⃣ Prepare Local Repository

Created AWS-EC2-Webpage locally with files:

index.html 🖥️

index.js ✨

README.md 📄

Initialized Git and pushed to GitHub via SSH:

git init
git add .
git commit -m "Initial commit with index.html and index.js"
git remote add origin git@github.com:yourusername/AWS-EC2-Webpage.git
git branch -M main
git push -u origin main

4️⃣ Clone Repository on EC2
cd /home/ubuntu
git clone git@github.com:yourusername/AWS-EC2-Webpage.git

5️⃣ Move Files to NGINX Web Root
sudo mv AWS-EC2-Webpage/index.html /var/www/html/
sudo mv AWS-EC2-Webpage/index.js /var/www/html/
sudo chown www-data:www-data /var/www/html/index.*
sudo chmod 644 /var/www/html/index.*

6️⃣ Reload NGINX
sudo systemctl reload nginx

7️⃣ Test Website

Open browser: http://your-ec2-ip 🌍

Hover on the heading → text color changes 🎨

Click heading → alert pops up ⚡

8️⃣ Screenshot

Screenshot of terminal output and website:

9️⃣ Key Learnings

💡 Installing and configuring NGINX on Ubuntu

💡 Using Git and GitHub for version control and deployment

💡 Deploying static websites manually on AWS


🧑‍💻 Author

Kartik Singh
