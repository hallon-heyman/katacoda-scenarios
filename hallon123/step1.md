# Introduction to Docker, the why and the how

Docker is perhaps the worlds leading devops tool and many programmers will alreayd be familiar with it. If you feel confident in your understanding of Docker you can skip this part.
Otherwise, or if you feel like you would like to refresh or deepen your knowledge of the docker technology, this step will give you an adequate understanding of how Docker functions, why docker is so popular, 
and some basic usage of it. 

## The problem of server hosting

Docker is perhaps best introduced through its history - as a solution to a problem. The story begins in the days of the early internet when large companies and entities such as
foodchains, banks etc; with new, large prescences on the internet needed to maintaining hosting for their large and varied user needs. If these servers crashed the cost for the enterprise
was potentially catastrophic, and different servers were required for the very varied user specifications. As such, server over-allocation was common and there was great inefficienyat great financial cost. Virtualisation arose as a solution to this problem.

## Virtualisation

Virtualisation as a concept and technology had already been around for decades, but it was a fringe functionality that was rarely used up til this point.
In 2005, intel and AMD both added hardware-assisted support for virtualisation, and new companies such as VMware started spreading the functionality to the wider market.
Through virtualisation, one host could run several OS or different applications and support a much wider range of different services to varied users, saving on required server infrastructure.
Yet virtualisation is costly. If you are unfamiliar with the structure of virtualisation, it requires that a hypervisor is run on the original OS to create the necessary for the environment for the virtualised OS. This hypervisor in turn simulates a kernel and the virtualised OS in full, and finally, the intended executable can run on the virtualised OS.  As such, each virtualised OS or application requires its own hypervisor, simulated kernel, disk storage, RAM allocation, etc; to run. The technology Docker arose as a more efficient solution to the problem of serving a wide range of technological necessities while maintaining efficiency.

## Enter Docker

Docker was released as open-source in 2013 as a new approach to virtualisation with Container Technology. Containers had been around for 10 years already at that point, but Docker added new functionality such as managing and creating your own containers and brought it into the mainstream. Docker introduces the Docker daemon which replaces the hypervisor. Instead of simulating a full OS with kernel, the docker daemon can utilises a container to completely empackage an application and run it without the need of simulating a full extra OS, a great improvement in efficiency. If you would like a more thorough dive into the docker technology we recommend the article [An Introduction To Docker And An Analysis Of Its Performance"](https://d1wqtxts1xzle7.cloudfront.net/52736106/IJCSNS-20170327.pdf?1492765779=&response-content-disposition=inline%3B+filename%3DAn_Introduction_to_Docker_and_Analysis_o.pdf&Expires=1619614220&Signature=ef6~eKYBkJ8VXTqD~-tCZYH~bQNH2qbz5F6DBtJR-l~1YT5diAazBzkMaVw~ljTx0uXvcpcriC7Js6weTlAwAgoVTuxRxYHBjrMHoshSZXfqzohEO3JD4EvXhYFIXE91e6AQKZdYnjeRcbNFpowSW0ppAcKlukkyysbrsb7iVClJTyAy~jSTweQxE~CqPc1DfAvN1JUl3TnL556V4QAybJvgjSyatgQWGZiX6EagCxv4Q8o-JY2RsjFE6HSWef3-4TXzBqby4joLJqXRhVDWDvB-PIjNHgpF5iBhcQ-2HFnHTyo97j0JBJ6VvDMO2qqcca~ODMpD-RPVx0G3eDq5PA__&Key-Pair-Id=APKAJLOHF5GGSLRBV4ZA) by Rad, Bhatti and Ahmadi. Below we give a brief summary of how it works.

## The Container Technology in brief

Docker can be explained as a server-client based application where the server, also daemon, services requests from docker clients. These can be run on the same machine.
Docker images are the building blocks of docker functionality. They are created in two different ways: from read only templates and docker files. Read only templates are essentially copies of base images, operating systems such as ubuntu version x are typically the base images. When something is added to the copy of such a base image, it is saved as a new image. Docker file however contain a list of instructions that are run when the docker build command is executed, as such it is an automated way of building an image.
