# Introduction to Docker

Docker is perhaps the worlds leading devops tool and many programmers will alreayd be familiar with it. If you feel confident in your understanding of Docker you can skip this part.
Otherwise, or if you feel like you would like to refresh your knowledge this step will give you an adequate understanding of Docker, why docker is so popular, 
and some basic usage of it. 

Docker is perhaps best introduced through its history - as a solution to a problem. The story begins in the days of the early internet when large companies and entities such as
foodchains, banks etc; with new, large prescences on the internet needed to maintaining hosting for their large and varied user needs. If these servers crashed the cost for the enterprise
was potentially catastrophic, and different servers were required for the very varied user specifications. As such, server over-allocation was common and there was great inefficieny,
at great financial cost. Virtualisation was the first solution to this problem.

Virtualisation as a concept and technology had already been around for decades, but it was a fringe functionality that was rarely used up til this point.
In 2005, intel and AMD both added hardware-assisted support for virtualisation, and new companies such as VMware started spreading the functionality to the wider market.
Through virtualisation, one host could run several OS or different applications and support a much wider range of different services to varied users, saving on required server infrastructure.
Yet virtualisation is costly. Each virtualised OS or application requires its own simulated kernel and resources to run.
