
# Enter Docker

Docker was released as open-source in 2013 as a new approach to virtualisation with Container Technology. Containers had been around for 10 years already at that point, but Docker added new functionality such as managing and creating your own containers and brought it into the mainstream. Docker introduces the Docker daemon which replaces the hypervisor. Instead of simulating a full OS with kernel, the docker daemon can utilises a container to completely empackage an application and run it without the need of simulating a full extra OS, a great improvement in efficiency. If you would like a more thorough dive into the docker technology we recommend the article [An Introduction To Docker And An Analysis Of Its Performance"](https://d1wqtxts1xzle7.cloudfront.net/52736106/IJCSNS-20170327.pdf?1492765779=&response-content-disposition=inline%3B+filename%3DAn_Introduction_to_Docker_and_Analysis_o.pdf&Expires=1619614220&Signature=ef6~eKYBkJ8VXTqD~-tCZYH~bQNH2qbz5F6DBtJR-l~1YT5diAazBzkMaVw~ljTx0uXvcpcriC7Js6weTlAwAgoVTuxRxYHBjrMHoshSZXfqzohEO3JD4EvXhYFIXE91e6AQKZdYnjeRcbNFpowSW0ppAcKlukkyysbrsb7iVClJTyAy~jSTweQxE~CqPc1DfAvN1JUl3TnL556V4QAybJvgjSyatgQWGZiX6EagCxv4Q8o-JY2RsjFE6HSWef3-4TXzBqby4joLJqXRhVDWDvB-PIjNHgpF5iBhcQ-2HFnHTyo97j0JBJ6VvDMO2qqcca~ODMpD-RPVx0G3eDq5PA__&Key-Pair-Id=APKAJLOHF5GGSLRBV4ZA) by Rad, Bhatti and Ahmadi. Below we give a brief summary of how it works.

## The Container Technology in brief

![image](https://user-images.githubusercontent.com/62335201/116404265-c579fc00-a82e-11eb-9a24-9ba227a58a9c.png)


Docker can be explained as a server-client based application where the server, also daemon, services requests from docker clients. These can be run on the same machine.
Docker images are the building blocks of docker functionality. They are created in two different ways: from read only templates and docker files. Read only templates are essentially copies of base images, operating systems such as ubuntu version x are typically the base images. When something is added to the copy of such a base image, it is saved as a new image. Docker file however contain a list of instructions that are run when the docker build command is executed, as such it is an automated way of building an image. In this tutorial building will not be necessary as we are to pull the only container we need, but it is important to be aware of how these containers are created.

The docker images can be used just like repositories through docker registries, where images can be pushed and pulled and distributed privately or publicly through the docker hub featre.

A docker container is created from a docker image, that is, a docker container is run from the code that is saved in the image, the container refering to the process on the computer system.  The splunk container runs from an image of splunk code embedded with all the necessary dependencies for splunk to run. The docker engine runs every container from the same virtualised OS if possible,for example, for several containers using ubuntu it might just run one ubuntu kernel. This lessened isolation creates efficiency but reduces security. 

This ends our brief introduction to docker as you should have all the understanding you need to know what goes on behind the scenes in this tutorial. In katakoda it is not necessary to login to docker as every terminal is logged in by default, but a good tutorial reminds its user even of the basics.

`docker login`{{executable}}
