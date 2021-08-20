---
layout: default
title: "Ark & MC: My first Dockerfiles"
---

# Ark & MC: My first Dockerfiles

I'm publishing my first Dockerfiles. The first is [docker-ark](https://github.com/surprise-automation/docker-ark) and the second is [docker-minecraft](https://github.com/surprise-automation/docker-minecraft).

## Docker Ark...

... aims to provide a set of scripts and ideas for running multiple Ark servers in a cluster. Currently there is an issue where the final Ark server will not come online - this is a known issue with Ark clusters but finding information is a total pain.

I also haven't baked in mod support yet. This is possible however it's a huge time investment with such little gain for me. I'm personally running unmodded crossplay servers, so I haven't had the motivation to add it.

Another thing to note is that each Ark server has to run inside of it's own folder, however you must link together the `Saved` directories. I do this with Docker Volumes, more in the `README.md`.

## Docker Minecraft...

... aims to provide the scripts and information that you need to build a SpigotMC server running in a Docker container with easily-accessible, persistent world files.

The `README.md` provides a simple set of repeatable instructions to build the `spigot.jar` file and install the correct Java version to run the server. I am using this image to run a Spigot MC server with Geyser, Floodgate and Dynmap.

- **Spigot MC** builds from the Minecraft server `.jar` to provide a modding framework for extra functionality
- **Geysey MC** is a proxy that listens on Bedrock Editions port and translates between Bedrock Clients and the Java Edition server, allowing all Minecraft builds to connect to your server.
- **Floodgate** handles Bedrock authentication into a Java Edition server, allowing your Bedrock players to play on your Java server without owning the Java Edition. Without Floodgate, your players will be forced to enter their Java or Bedrock credentials into a prompt that appears after they connect to your server, which in my opinion is bad practice. Floodgate fixes this potential for training bad habits into uses, so it's quintessential.
- **Dynmap** creates a map of your Minecraft worlds in 2D and 3D.