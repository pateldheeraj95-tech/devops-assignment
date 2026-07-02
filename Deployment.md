# DevOps Assignment - Deployment Guide

## Prerequisites
- AWS Account
- EC2 Instance (Ubuntu)
- Docker
- Git

## Step 1: Launch EC2
- Create an EC2 t3.micro instance.
- Allow ports 22 (SSH), 80 (HTTP), and 3000 (Application).
- Connect to the EC2 instance using SSH.

## Step 2: Install Docker

sudo apt update
sudo apt install docker.io -y
sudo systemctl start docker
sudo systemctl enable docker

## Step 3: Clone Repository

git clone https://github.com/pateldheeraj95-tech/devops-assignment.git
cd devops-assignment

## Step 4: Build Docker Image

docker build -t devops-assignment .

## Step 5: Run Docker Container

docker run -d -p 3000:3000 --name devops-container devops-assignment

## Step 6: Verify Deployment

docker ps

Open the application in browser:

http://<EC2-Public-IP>:3000

## Step 7: S3 Backup

- Create an S3 bucket.
- Upload project backup files.

## Step 8: CloudWatch Monitoring

- Create a CPU Utilization Alarm.
- Configure SNS Email Notification.

## Step 9: Load Testing

Install k6

Run:

k6 run load-test.js

## Deployment Completed Successfully