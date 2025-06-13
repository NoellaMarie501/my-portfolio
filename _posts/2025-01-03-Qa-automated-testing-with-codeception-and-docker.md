---
layout: post
title: "API Automated Testing with Codeception in Docker and AWS/ECR"
summary: "Let's dive into QA shall we!!!. Explore how to run end-to-end API automated acceptance tests using Codeception, Docker, and AWS ECR in a reproducible local setup."
author: mariecheo
date: '2025-01-03 20:30:00 +0000'
category: tutorials
thumbnail: /assets/img/posts/codeception.png
keywords: codeception, automated testing, docker, QA, AWS ECR, acceptance testing, php testing
permalink: /blog/codeception-api-acceptance-tests/
usemathjax: false
---
Suppose you have an API image hosted on a registry—perhaps you're a QA engineer tasked with testing an API built by a developer and pushed to AWS ECR or another container registry. API testing is essential to ensure your backend performs reliably under real-world scenarios. In this guide, I’ll show you how to use Codeception, a powerful PHP testing framework, to run acceptance tests against APIs in a fully containerized environment.

You can use this setup to test your own API container images (hosted on AWS ECR or elsewhere). The process includes spinning up a container, running tests inside a separate test container, and tearing everything down — all automated with a Makefile.

# Why Use Codeception for API Testing?
Powerful DSL: Makes your tests readable and expressive.

Modular: Easily combine REST, DB, and other modules.

Automation-Ready: Works perfectly in CI/CD pipelines.

Docker Friendly: Can be containerized and run anywhere.

# Project Setup (From GitHub)
You can find the full project repo here:
 [Codeception-UAT-Connector on GitHub](https://github.com/NoellaMarie501/Codeception-UAT-Connector)

To get started locally:

```bash
git clone https://github.com/NoellaMarie501/Codeception-UAT-Connector.git
cd Codeception-UAT-Connector
```
🐳 Docker Requirements
Make sure the following are installed:

Docker

Docker Compose

AWS CLI

Install AWS CLI (Linux example)
```bash
sudo apt update && sudo apt install unzip -y
curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
unzip awscliv2.zip
sudo ./aws/install
```
Configure your credentials:

```bash

aws configure
```
# Provide your AWS Access Key, Secret Key, Region, and preferred output format

# Pull the API Image
The project is designed to pull a Docker image from AWS ECR, but you can replace this with your own image by editing the variables.env file.

```bash
make auth2         # Authenticate with AWS ECR
make digitech-pull # Pull the API container image
```
# Or update your image like this in variables.env:
You can also change the `DIGITECH` variable name to match your own API image. In this example, it's called `DIGITECH` because that's the API being tested, but you can rename it to whatever fits your project.

```env
DIGITECH=your-aws-ecr-or-dockerhub-image:your-tag
APPLICATION_ENV=testing
MYSQL_HOST=mysql
```

# Start the Test Environment
```bash

make build  # Build the containers
make up     # Start containers in background

```
This will spin up the API service along with the test container.

# Run Acceptance Tests
Now let’s execute the tests written in Codeception.

```bash
make execute-test
```
The tests will hit endpoints in your running container and verify that the responses and behavior match what’s expected.

# Structure of the Project
This setup uses:

Codeception for writing and executing tests

Makefile to simplify common dev/test operations

Docker Compose for container orchestration

AWS ECR for hosting your API image (can be replaced with any Docker registry)

# Useful Make Commands

Command	Description

make build:	Build all containers

make up:	Start services in background

make stop:	Stop running services

make clean:	Remove containers and orphan volumes

make reset:	Full clean + rebuild and restart

make app-root:	Shell into the app container

make test-root:	Shell into the test container

make execute-test:	Run acceptance tests in test container

make app-logs:	Show logs from the app container(API container)

make test-logs:	Show logs from the test container

# Customizing for Your Own API
Want to use this setup for your own API project? Just do the following:

Replace the image in variables.env with your own Docker or ECR image.

Update or write new test scenarios in the /tests/acceptance/ folder using Codeception’s DSL.

Use the same make commands to run your API in a container and execute your tests.

This makes it easy to build QA pipelines that mirror production environments.

#  What I Learned
This project helped me better understand how QA integrates into DevOps workflows. It showed me how to:

Automate test environments using Docker

Use Codeception to validate API behavior

Execute test pipelines using Make and CLI tooling

Configure and pull secure AWS ECR images

# Resources
Codeception Documentation

AWS CLI

Docker Compose

Makefile Cheatsheet

# Final Thoughts
If you're looking to test your APIs in a real containerized environment, this setup is flexible, repeatable, and easily extendable. Whether you're doing UAT, pre-release QA, or local development sanity checks, you’ll find it a handy base for automated acceptance testing.

Feel free to clone my GitHub repo and adapt it to your needs.

Happy testing!