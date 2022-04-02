---
layout: post
title:  "Spring 22 - Blog 6"
date:   2022-03-31.
categories: Kubernetes Minikube 
---

According to the documentation, Kubernetes is a portable, extensible, open-source platform for managing containerized workloads and services, that facilitates both declarative configuration and automation. It has a large, rapidly growing ecosystem. Kubernetes services, support, and tools are widely available.

Running containers in production has always been the up and coming way to manage production workload. Aside from managing a variety of nodes through a singular manager, it can minimize costs. This will be a guide to setup Kubernetes on a Mac environment.

<h3>Installing Kubernetes on Mac</h3>

1. First, ensure that the Homebrew package manager is installed. Then run the command `brew tap homebrew/cask' <br>
![Imgur](https://i.imgur.com/HhDq300.png)
2. Proceed to install Docker for Mac which is used to create, manage, and run containers. This will allow us to create containers that will run in our Kubernetes Pods. <br>
3. Install VirtualBox for Mac. Either install directly from the website or using this homebrew command `brew cask install virtualbox`. This will allow you to run virtual machines on your Mac. <br>
4. Install kubectl which is a command-line interface that can interact with Kubernetes. Using homebrew, run `brew install kubectl` <br>
![Imgur](https://i.imgur.com/dSb1utL.png)
5. Finally install Minikube which will run a Kubernetes cluster with a single node. Use the command `curl -Lo minikube https://storage.googleapis.com/minikube/releases/v1.18.1/minikube-darwin-amd64` which is using the most recent update for the MAC distro. <br>
6. Continue by running `minikube start` which will then start your cluster. <br>
![Imgur](https://i.imgur.com/djuwLuw.png)