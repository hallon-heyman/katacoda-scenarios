# How to use Splunk through a Docker container

![image](https://user-images.githubusercontent.com/62335201/116403937-70d68100-a82e-11eb-96c6-1382cf039134.png)

This tutorial will teach you how to use the tool splunk enterprise through Docker. Docker is perhaps the worlds leading devops tool, it uses containerization technology to allow applications to be packaged as images and easily and efficiently run in containers. Splunk is a monitoring tool used by many companies in order to analyse data comming from various systems.  Using docker to set up splunk is relatively easy and does not require you to install unecessary software on you machine thanks to this tutorial being run through Katakoda. Remember that this instance of Splunk is entirely EPHEMERAL which is to say it will not remember anything you put in, when you close this tutorial all data that you uploaded to splunk will be lost, likewise, feel free to play around in the playground of an online tutorial.

We will first introduce Docker, its history and a brief summary of its underlying technology, and then move over to Splunk. If the user takes the time to fully read the background material accompanying the executable commands, the user will end this tutorial with a strong understanding of both Docker and Splunk, and how they are used together.
We begin with a short introduction to Docker.


## Introduction to Docker, the why and the how

Many developers will already be familiar with Docker. If you feel confident in your understanding of Docker you can skip this part.
Otherwise, or if you feel like you would like to refresh or deepen your knowledge of the docker technology, this background and the following first step will give you an adequate understanding of how Docker functions, why docker is so popular, 
and some basic usage of it. 

## The problem of server hosting

Docker is perhaps best introduced through its history - as a solution to a problem. The story begins in the days of the early internet when large companies and entities such as
foodchains, banks etc; with new, large prescences on the internet needed to maintaining hosting for their large and varied user needs. If these servers crashed the cost for the enterprise
was potentially catastrophic, and different servers were required for the very varied user specifications. As such, server over-allocation was common and there was great inefficienyat great financial cost. Virtualisation arose as a solution to this problem.

## Virtualisation

Virtualisation as a concept and technology had already been around for decades, but it was a fringe functionality that was rarely used up til this point.
In 2005, intel and AMD both added hardware-assisted support for virtualisation, and new companies such as VMware started spreading the functionality to the wider market.
Through virtualisation, one host could run several OS or different applications and support a much wider range of different services to varied users, saving on required server infrastructure.
Yet virtualisation is costly. If you are unfamiliar with the structure of virtualisation, it requires that a hypervisor is run on the original OS to create the necessary for the environment for the virtualised OS. This hypervisor in turn simulates a kernel and the virtualised OS in full, and finally, the intended executable can run on the virtualised OS.  As such, each virtualised OS or application requires its own hypervisor, simulated kernel, disk storage, RAM allocation, etc; to run. The technology Docker arose as a more efficient solution to the problem of serving a wide range of technological necessities while maintaining efficiency. In the next step, we will dive into some introductionary Docker.
