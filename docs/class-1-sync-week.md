# Welcome to Sync Week!

Let's get started!

## First: Decide _Where_ to host Zcash.
(Non-technical or don't care? Use Google Cloud and Docker. Skip to the instructions below.)

Servers are special computers that made specially with high-quality components to help them function for long periods of time with no downtime.

### External Hosting
Many companies around the world offer servers for rent, hosted in special buildings called datacenters which are built to provide reliable power, cooling, and security. These companies are called "hosts" or "hosting providers" - and for big-tech's hosting offerings, "public clouds".

Renting an entire computer, a server just for yourself, is called renting a "dedicated server".

You can rent a portion of a server for a much lower price. Computer chips today offer many security features that allow multiple people to share a computer safely, without being able to access or affect each other's information or apps.

Renting a portion of a computer is called renting a "virtual machine" or "VM" for short.

For this workshop, we recommend renting a VM in Google Cloud using the $300 of free credits that they give to new users. But if you're feeling adventurous, check out the hundreds of options on ServerHunter.com. You'll want 300gb of disk space, and at least 4gb of RAM.

Chat with us on Session before paying for something, we'll help you verify that it's a good option.

### Self-hosting Zcash
But computers are everywhere! You might even have an extra one in your house.

It can be fun to host useful things on computers in your house. Many people do this, even using multiple computers - it's called a "home lab"!

There are downsides to hosting something at home, however:
1. The computer needs to be online all of the time, never rebooting, and ideally is on a battery backup.
2. You risk revealing information to the world about where you live, through IP address leaks. (a unique identifier that your internet provider gives to your network)
3. If a hacker got access to your server, they could potentially access your home network unless you take advanced precautions.

If you're comfortable with the risks, go for it! We're happy to help and will release specific guides for this in the days ahead. We run a home lab ourselves!

## Now Decide _How_ to host Zcash.

Docker (noun): a person who loads and unloads shipping containers at a marine dock
Docker (noun): a small town in England
[Docker](https://www.docker.com/) (noun): an open-source software project automating the deployment of applications inside software containers 

vs

Kubernetes (noun): Greek work meaning a helmsman or pilot responsible for steering a ship
[Kubernetes](https://kubernetes.io/) (noun): an open-source system that automates the deployment, scaling, and management of containerized applications

Zec.rocks runs on dedicated servers that we maintain around the world, running Zcash on an easy Kubernetes distribution called "k3s". However, as Docker can be an easier entry-point for newcomers, we recommend starting with Docker.

### Docker
Docker is a tool that packages apps and everything they need (code, dependencies, system tools) into standardized containers, so they run the same anywhere. It's like a shipping container for software: keeping it isolated, portable, and easy to run on any computer.

### Kubernetes
Kubernetes is a system that runs lots of containers across multiple computers and makes sure that the software stays online, even if some of the computers stop working. It can even grow and shrink automatically throughout the day. If more people need the software, it adds more computers and containers; if fewer people use it, it removes the extras to save money.

The major public clouds have Kubernetes platforms which offer many cool features. But they're a bit expensive, and are centralized. If you're okay with that, we recommend using Google's $300 of free credits to try Google Kubernetes Engine.

A great thing about Kubernetes is that you don't have to run it on a major cloud, you can run it yourself, even on one computer. You lose the benefits of a large company's reliability, but you gain independence. 

## Action Item 1: Pick a Hosting Provider

Google Cloud offers $300 in free credits, and is our recommendation for people looking for the least technical path forward.

[Vultr](https://www.vultr.com/) is another option for hosting services.

Feeling adventurous? Browse ServerHunter.com for options. But contact us before paying for one, we'll help you make sure that you are picking a good option.

Remember, Zcash is decentralized software! You can completely delete it and start over fresh as many times as you like. You will not cause harm to the blockchain, it is synchronized across many computers around the world.

It's important to note that we will not be storing any money in our Zcash nodes, we are contributing to the decentralization of the network instead of using its wallet functionality. So, try a few hosts out, and both our Docker and Kubernetes approaches, if you'd really like to learn about hosting! You can always reinstall and try again.

Server Requirements: 
- At least 300GB of available disk space
- Minimum 4GB of RAM

## Action Item 2: Configure Your Server

[Work in progress: This will be posted by Wednesday! Thank you for making it this far, say Hello in Chat!]

Feel like racing ahead, comfortable with a terminal, and want to use the Docker method? [Here's the process.](https://github.com/zecrocks/zcash-stack/tree/main/docker)

## Action Item 3: Sync the Blockchain

The Zcash blockchain is ~275gb and can take over a week to download and synchronize. Through this process, your new server will validate each transcation in the blockchain, which can be a lengthy process. 

Another option, is to download a snapshot of the blockchain as starting point, and then let the server validate each new subsequent transcation. This assumes that the snapshot maker has an accurate copy of the history of the blockchain. 

Optional: Download a snapshot of the zcash blockchain (likely takes a few hours)
```
./docker/download-snapshot.sh
```

## Action Item 4: Connect your Server to a Lightwallet

![Connecting your server to a Lightwallet](https://github.com/ReadyMouse/zcash-stack/blob/main/docs/images/node_to_lightwallet_ways.png)