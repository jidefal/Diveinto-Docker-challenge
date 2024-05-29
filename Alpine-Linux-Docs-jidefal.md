# What is Alpine Linux?

Alpine Linux is a linux distribution built around [musl Libc](https://www.musl-libc.org/) and [BusyBox](https://www.busybox.net/). The Image is only 5MB in size and has access to a package respority that is much more complete than other BusyBox based Images. This makes Alpine Linux a great image base and even production applications. 
[**Source**](https://hub.docker.com/_/alpine) 

## Challenge 1 : Pull the latest version of the alpine image using the traditional docker command format

1. To check the Version of Docker Install on your console 

```bash 
docker --version 
```
![alt text](<Images/SC 01 - Docker Version.PNG>)

2. To download Alpine Linux, Type the command below. 

```bash 
docker pull alpine 
```
![alt text](<Images/SC 02 - Docker Pull.PNG>)

**Note:** Make sure your Docker Desktop is running on your console. 

## Challenge 2: Compare the digest in the pull command output to that on Docker Hub. 

You may be surprised to see that they don’t actually match!

Here is a picture of the Alpine pull Digest at the console. 
 ![Alpine pull digest](<Images/SC 03 - Alpine Pull Digest.PNG>)

 Here is a picture of Alpine pull digest On DOcker Hub. 

 ![Docker Hub Alpine pull digest](<Images/SC 04 - Alpine Docker Hub Digest.PNG>)

 The reason is the alpine image covers many different variants such as amd64 and arm and hence, the digest shown in the ‘docker pull’ output is a top level digest that references all platform variants that you see individually listed in the Docker Hub output.

 There’s a convenient tool that you can use that will show the top level digest, compare the top of this report to what you see in the docker pull output - [Here](https://explore.ggcr.dev/?image=alpine)

 ## Challenge 3: Use the docker history command to inspect the layers that comprise of this image

 Use `docker history` followed by the image name to view its layers. 

 ```bash 
 docker history alpine
 ```

 This command will output a list of layers that makeup the specified image. 

 ![Docker History alpine](<Images/SC 05 - Docker history Alpine.PNG>)

 ## Challenge 4: Compare this to the layers listing on Docker Hub. 

This is Layer Listing on Docker Hub 

 ![Layers on DOcker Hub](<Images/SC 06 - Layers on Docker Hub.PNG>)

 as compared to output from the docker history

  ![Docker History](<Images/SC 05 - Docker history Alpine.PNG>)

  ## Challenge 5: Identify the image id and digest

Use the command `docker Image --digest` to list the details of each image on your console. There you can view the **Image ID** and **Digest** at the same time. 

```bash 
docker images --digests
```
![Image ID and Digest](<Images/SC 07 - Images ID and Digest.PNG>)

## Challenge 6: Remove the alpine image and confirm that it is removed

Here are the steps to remove the alpine image and confirm it has been removed. 

1. List Your Docker images. Use the Command `docker images` to list all the docker images and their IDs. 

```bash 
docker images 
```
![list of docker images](<Images/SC 08 - List of docker images.PNG>)

2. Remove the Alpine Image. Use the `docker rmi` command to remove the Alpine images. You must specify the image by its name and tag or by its Image ID. 

```bash 
docker rmi alpine:latest
```
![Delete alpine result](<Images/SC 09 - Delete Alpine.PNG>)

3. Confirm the images is removed. List the Docker images again to confirm the alpine image has been removed. 

```bash 
docker images 
```
![updated List](<Images/SC 10 - update docker images list.PNG>)

## Challenge 7: Capture a specific version of ubuntu by using the tag 20.04 and the alternative command syntax in the format of docker noun verb

To Pull a specific version of the ubuntu image using the tag '20.04' the command will be 

```bash 
docker image pull ubuntu:20.04
```
This command tells Docker to pull the Ubuntu Image tagged with '20.04' from the Docker Hub respository using the `docker image pull` syntax. 

![Pull Ubuntu Sample](<Images/SC 11 - Docker Pull image Ubuntu.PNG>)

## Challenge 8: Check the digest, using the alternative command syntax

```bash 
docker image --disgests ubuntu:20.04
```
This command checks the list of the digest for the Ubuntu image pulled from the docker hub repository. 
![List Digest](<Images/SC 12 - List Digest.PNG>)

## Challenge 9: Inspect the layers of this image using docker history, via the alternative command syntax

```bash 
docker image history ubuntu:20.04
```
This Command inspects the layers of the Ubuntu image. 

![Layer Ubuntu](<Images/SC 13 - History Ubuntu.PNG>)

## Challenge 10: Remove the ubuntu:20.04 image using the alternative command syntax and confirm that it is removed, again using the alternative command syntax

Using the alternative command syntax, here are the steps to remove the ubuntu image and confirm it has been removed. 

1. List Your Docker images. Use the Command `docker images` to list all the docker images and their IDs. 

```bash 
docker image list 
```
![Ubuntu Image](<Images/SC 14 - Ubuntu image List.PNG>)

2. Remove the ubuntu Image. Use the `docker image rmi` command to remove the Ubuntu images. You must specify the image by its name and tag or by its Image ID. 

```bash 
docker image rmi ubuntu:20.04
```
![Delete Ubuntu](<Images/SC 15 - Delete Ubuntu Image.PNG>)

3. Confirm the images is removed. List the Docker images again to confirm the alpine image has been removed. 

```bash 
docker image list 
```
![Updated image list](<Images/SC 16 - Update image list.PNG>)
