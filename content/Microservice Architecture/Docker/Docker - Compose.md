# Docker compose
#docker #containers 

It is a tool for defining and running multi-container [Docker](Microservice%20Architecture/Docker/Docker.md) applications. With Compose, you use a YAML file to configure your application's services.

If you want to setup multi container application which requires different container components stiched together, docker-compose provides the functionality to make this happen. 

Compose revolves around a config file called `docker-compose.yml`. In it we define all of our services. Think of a service as a part of your application; a database or API for example. All of our services rely on an image with which we create a container. Spinning up a container can have many options; how these options are configured will be stored in the yml file.


![Pasted image 20221017161114](Microservice%20Architecture/Attachments/Pasted%20image%2020221017161114.png)

## Features:
-   [Multiple isolated environments on a single host](https://docs.docker.com/compose/#multiple-isolated-environments-on-a-single-host)
-   [Preserve volume data when containers are created](https://docs.docker.com/compose/#preserve-volume-data-when-containers-are-created)
-   [Only recreate containers that have changed](https://docs.docker.com/compose/#only-recreate-containers-that-have-changed)
-   [Variables and moving a composition between environments](https://docs.docker.com/compose/#variables-and-moving-a-composition-between-environments)



https://towardsdatascience.com/docker-compose-for-absolute-beginners-how-does-it-work-and-how-to-use-it-examples-733ca24c5e6c