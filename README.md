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

The mainstream tool that most developers will use is an application called Docker. Docker is a tool used to run, create, and manage containers.
