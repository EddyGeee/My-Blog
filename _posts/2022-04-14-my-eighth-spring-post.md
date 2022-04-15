---
layout: post
title:  "Spring 22 - Blog 8"
date:   2022-04-14.
categories: jekyll update
---

![Imgur](https://i.imgur.com/2QlfQeR.jpg)

Docker is a great virtualization tool used by developers to create and deliver distributed applications in packages called containers. As you create bigger and more robust applications you'll find yourself seeking a production ready environment to host your Docker images. AWS ECR (Elastic Container Registry) is a commonly used solution for developers who want to store their images in a cloud-based infrastructure. Other used container registries are Docker Hub and Google Container Registry. 

For those who are unfamiliar with Docker check out their website [here][d-o] to get started.

**Installing Docker on an Amazon EC2 instance**

If you don't plan on running Docker on a local development system, I recommend installing it on an EC2 instance. For this tutorial I'll be using the Amazon Linux 2 AMI to maintain *free tier eligibility*.

1. After you provision and gain access to your instance, you'll want to this command to update installed packages on your instance:<br>
`sudo yum update -y`<br>
2. In order to install the most recent edition of Docker run:<br>
`sudo amazon-linux-extras install docker`<br>
3. Finally, to start up Docker use:<br>
`sudo service docker start`<br>

Play around with Docker and see if you can create your very first Docker image. Start by running the command `touch Dockerfile` to create a Dockerfile within the directory. Here is a snippet of an example Dockerfile:

![Imgur](https://i.imgur.com/UddTAmK.png)

**Pushing your Docker image onto Amazon ECR**

*Note:* Make sure you have [AWS CLI][i-o] installed and configured before moving on. 

Once you have Docker images ready to be pushed onto Amazon ECR, follow these steps:

1. Create an ECR repository to store your Docker image using this command as an example:<br>
`aws ecr create-repository --repository-name example-repository --region region`<br>
2. You'll notice a `repositoryUri` in the output. Tag the image with the `repositoryUri` value:<br>
`docker tag example aws_account_id.dkr.ecr.region.amazonaws.com/example-repository`<br>
3. Afterwards, you'll need to authenticate yourself to gain access to the repository. Use this command as an example but replace the appropriate credentials:<br>
`aws ecr get-login-password | docker login --username AWS --password-stdin aws_account_id.dkr.ecr.region.amazonaws.com`<br>
4. Once you've authenticated yourself, push your Docker image to Amazon ECR with the `repositoryUri` value from step 2. <br>
`docker push aws_account_id.dkr.ecr.region.amazonaws.com/example-repository`

Remember to delete any unused repositories to minimize costs! I'll cover deploying Docker containers onto Amazon ECS (Elastic Container Service) in a future post. 

[d-o]: https://www.docker.com/
[i-o]:https://docs.aws.amazon.com/cli/latest/userguide/cli-chap-install.html