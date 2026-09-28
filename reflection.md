# Mission 4 Reflection

This laboratory activity helped me understand the practical difference between running applications in a Virtual Machine and running them inside a Docker container. A Virtual Machine needs a complete operating system, so starting one involves booting the guest operating system and its services. A Docker container can start much faster because it shares the host operating system kernel and only needs the application and its required dependencies. In this activity, running an Nginx container required only a Docker command instead of installing and configuring a complete operating system.

Port mapping is important because the Nginx web server is running inside the container. The command `-p 8080:80` connects port 8080 on the host to port 80 inside the container. This allows me to access the Nginx server through `http://localhost:8080` while Nginx continues to listen on its normal port 80 inside the container.

When the `docker rm` command is used on a container, the container itself is removed after it has been stopped. Any data that exists only inside the writable layer of that container can be lost when the container is removed. This is one reason persistent data should normally be stored using Docker volumes or external storage instead of depending only on the container's temporary filesystem.

Containerization can also improve collaboration between software developers and IT operations teams. Developers can package an application together with its dependencies, while operations teams can use the same container image in different environments. This supports more consistent deployments and is an important part of DevOps practices.

My GitHub portfolio is gradually becoming a record of the cloud computing skills I have practiced. In this mission, I added research about virtualization and containers, documented Docker commands, and recorded evidence of deploying an Nginx web server. Each laboratory activity gives me more experience with cloud technologies and technical documentation.
