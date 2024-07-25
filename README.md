# docker-tutorial
Containerization is the process of turning an application or piece of software into a containered form. This containered form becomes an independent application that runs by itself without the help from any outside sources.
So, now it becomes important to discuss what a container actaully is, and how they work. Why is containerization an important skill to understand and learn more about?

Well, a container as mentioned before, is an independent environment that holds a peice of software or an application. A container containes 3 components to it to achieve being totally independent.
  1. Every container contains a small isolated operating system, whether it be linux based or windows based.
  2. Each container includes all the dependencies, environmental variables, and scritps needed for a specific applciation.
  3. Finally, the container includes the code and configurations to run the application.

Containers are essentially tools that work out of the box. Meaning they function as soon as you run the container, and usually do not need any extra setup if built correctly.
This offers a lot of unique benefits, for example: if you want to develop a project with a friend, instead of needing to make sure your friend has all the required tools needed to run the application, you can just make a container and share it with your friend. This way you can continue to develop on the application without needing to install any additional tools on your friends computer.

Now, from hearing about all these amazing things that containers can do, the biggest drawback to a containerized lifestyle is the computational power and RAM required. Since containers are small independent systems, they take up more RAM then a typical application would if it was not containerized. The amount of RAM used by containers is dependent on each situation, but from what I have seen  it is usually around 1-3gb of RAM per container. For example, if you are just needing to run an SQL server on your machine, this container will take up around 1gb of RAM.

Now, lets get more indepth with how to create and run containers on your own system.

Now, for a few important terms:
  Images: Images are blueprints for containers. With an image you can make multiple of the same exact container.
  Volumes: Volumes are a way to store data in a container, without actually taking up space in a container. It acts as a pointer to a storage system on the host machine that is running the container.
          - Volumes are one of the only ways that a container is able to have direct access to the host machine.
  Docker Engine: The Docker Engine is themain processor involved with running containers. The docker engine acts as a "Client side application" with a sevrer for a daemon process called dockerd.
  Dockerd: Dockerd is a persistant process provided by the docker engine from running containers. This is mainly a background tool that runs without you needing to know about it.

The mainstream tool that most developers will use is an application called Docker. Docker is a tool used to run, create, and manage containers.
Docker comes in a few different formats:
  1. If you are on Windows, Mac, or Linux you can download Docker Desktop : https://www.docker.com/products/docker-desktop/
  2. If you are on Linux you can also install the Docker Engine for interacting with Docker via the command line

The most user friendly version of Docker is there GUI application called Docker Desktop. From this application, you can pull images from Docker Hub (Which is a repository system from storing Images).
  - By the way, images are blueprints of containers. You need an image in order to run a container.

# We will be using the Docker CLI provided by installing Docker Desktop onto your system for the rest of the tutorial

Docker CLI is a command line interface for interacting with Docker. We will be using Docker CLI for a majority of this lesson.

Once you all have Docker Desktop installed onto your system, make sure to have Docker Desktop currently running as the only way to run containers is by having the "Docker Engine" running. 
So now that everyone has Docker running on there computers it is time to began a demonstration of a few different docker tools.

Firstly: the main way to create a container is by using a thing called a Dockerfile:

Now as the instructor, go to the "helloWorldDocker" folder and do a build along with the dockerfile. It is super basic stuff. 
First, have everyone at the lesson make a new folder and open an IDE (like visual studioes code or sublime text).
Second make an index.html file in that new folder:
Put in a basic hello world script
```
<!DOCTYPE html>
<html>
<body>
    <h1>Hello, World!</h1>
</body>
</html>
```
Then tell them to make a file called "Dockerfile": The D must be capital.

remind them that the dockerfile is how an Image is created.

Once the dockerfile is created, add in this code:
```
FROM nginx:alpine
COPY index.html /usr/share/nginx/html/
EXPOSE 80
```
The FROM statment in the dockerfile is calling an image called "nginx:alpine" as the base of the docker image.
All docker images are built off of other docker images, so the first line in the dockerfile should always be a FROM statement.

The COPY statment takes the index.html file we created and copies it into the container at the directory of "/usr/share/nginx/html/"

The EXPOSE statement exposes the port number 80, so when you run the container you can connect to the container from port number 80.

Then once the dockerfile and index.html file has been created, tell everyone to open up a command prompt.
Then have everyone use the "cd" command to go to the directory for the helloWorld application. Make sure everyone is in the right folder.

Now in order to start the container we have to build it first. The building sequence takes the dockerfile and generates us an image that ca be used as the blueprint for our container.

So type out the following command
```
docker build -t hello-world:0.1 .
```
the -t tage represents the name of the container followed by the tag of the container, so it will be called helloWorld with a tag number or version number of 0.1.
Then the . represents the location of the dockerfile, which is the current directory.

The docker build command will create for us a docker image, so once the build command finishes we can type out
```
docker run -p 80:80 -t hello-world:0.1
```
The -p tag represents the port number the application is accessible on, and the -t tag represents the docker image being ran.

Now that the container is running, open up the web broweser and go to localhost:80 and the Hello World application should be up and running perfectly!

# Minecraft Docker Container Tutorial

After setting up the nginx mini container set up, this next part will explore Docker-Compose files, and how they work.
