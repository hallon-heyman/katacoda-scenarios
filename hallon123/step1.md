
# Enter Docker

Docker was released as open-source in 2013 as a new approach to virtualisation with Container Technology. Containers had been around for 10 years already at that point, but Docker added new functionality such as managing and creating your own containers and brought it into the mainstream. Docker introduces the Docker daemon which replaces the hypervisor. Instead of simulating a full OS with kernel, the docker daemon can utilises a container to completely empackage an application and run it without the need of simulating a full extra OS, a great improvement in efficiency. If you would like a more thorough dive into the docker technology we recommend the article [An Introduction To Docker And An Analysis Of Its Performance"](https://scholar.googleusercontent.com/scholar?q=cache:PoPiiRcdcjcJ:scholar.google.com/++An+Introduction+To+Docker+And+An+Analysis+Of+Its+Performance&hl=en&as_sdt=0,5) by Rad, Bhatti and Ahmadi. Below we give a brief summary of how it works.

## The Container Technology in brief

![image](https://user-images.githubusercontent.com/62335201/116404265-c579fc00-a82e-11eb-9a24-9ba227a58a9c.png)


Docker can be explained as a server-client based application where the server, also daemon, services requests from docker clients. These can be run on the same machine.
Docker images are the building blocks of docker functionality. They are created in two different ways: from read only templates and Dockerfiles. 

Read only templates are essentially copies of Docker base images, operating systems such as ubuntu version x are typically the base images. All images start from these same images in some way. When something is added to the copy of such a base image, it is saved as a new image. Thus the original image will not get corrupted by whatever someone does with a copy of an image, and this is how Docker images maintain solvency. 

To list the images that is currently available in this web-terminal, run `docker image ls`{{executable}}.

A Dockerfile is a text document that contains all the commands a user could call on the command line to assemble an image. Using docker build users can create an automated build that executes several command-line instructions in succession. You can read more about Dockerfiles on the [official documentation](https://docs.docker.com/engine/reference/builder/#:~:text=A%20Dockerfile%20is%20a%20text,command%2Dline%20instructions%20in%20succession). When a dockerfile is run, retrieving a base image and running docker commands on that base image, each intermediate snapshot of the modified image is saved as a "layer" of that image. Another way to put it is that layers are stacked on top of each other to form a base for a container's root filesystem. We can run the som simple commands to pull an image and then take a look at its layers. Here we will pull the Linux OS debian just as an example before we move over to splunk.

`docker pull debian`{{executable}}. The Docker pull command pulls an image from a registry. If the version of the image is not specified with a *tag*, the :latest tag is added by default, so what we really write here is docker pull debian:latest . 

`docker history debian`{{executable}} displays to us the layers of this image.

`docker inspect debian`{{executable}} shows us the low level information for that image. 

Every image has a unique hash ID. We can see ours by `docker inspect debian | grep Id`{{executable}}. 

Then we can run the container, from the image, using that id if we like!  `docker run -it sha256:0af60a5c6dd017d7023f6b6c71f3ffbb9beb2948d842bcb1ba36d597fb96e75a`{{executable}}.

To exit this debian container, press ctrl+d.

The docker images can be fetched will pull just like git repositories through docker registries, where images can be pushed and pulled and distributed privately or publicly through the docker hub featre.

A docker container is created from a docker image, that is, a Docker container is run from the code that is saved in the image, the container refering to the process on the computer system.  The Splunk container runs from an image of Splunk code embedded with all the necessary dependencies for Splunk to run. The Docker engine runs every container from the same virtualised OS if possible,for example, for several containers using Ubuntu it might just run one ubuntu kernel. This lessened isolation creates efficiency but reduces security. 

This ends our brief introduction to docker as you should have all the understanding you need to know what goes on behind the scenes in this tutorial. In Katacoda it is not necessary to login to docker as every terminal is logged in by default, but a good tutorial reminds its user even of the basics, when you want to start up docker on a linux terminal:

`docker login`{{executable}}
