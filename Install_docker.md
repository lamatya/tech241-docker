# Docker

Docker is a tool that allows you to create, manage, and run applications inside isolated environments called "containers." These containers are like lightweight virtual machines that package everything needed to run an application, including code, runtime, libraries, and system tools. 

Docker enables developers to easily build, ship, and deploy applications consistently across different environments, making it easier to develop, test, and deploy software without worrying about compatibility issues or conflicts with the host system. 

It helps streamline the development process and ensures that applications run reliably and consistently on any platform that supports Docker.



# Install Docker on Windows;

1. Download the Docker Desktop installer from the official Docker website.
   
2. Double-click the downloaded installer to start the installation process.
   
3. Follow the on-screen instructions to complete the installation and restart the computer.
   
4. Once installed, Docker Desktop should be accessible from the Start menu.

5. To check if it has been installed go to the Terminal and type the command docker --version. If installed correctly it will give you the version

![Alt text](<images/docker version.png>)

# After installing Docker;

1. Go to start and search for Docker app 
2. Follow the link
3. Step 3: Enable Windows Subsystem for Linux (WSL)
Open PowerShell as Administrator and run the following command:
```
dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
```
4. Step 6: Check if your Windows version supports WSL 2
Make sure you have Windows 10 version 1903 or later, or Windows 11. Check your version by pressing Windows logo key + R, type winver, and press Enter. Update Windows if needed.

5. Step 5: Enable Virtual Machine feature
In PowerShell as Administrator, run:
```
dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
```

5. #### **Restart your computer after this step.**


6.  Set WSL 2 as the default version
Open PowerShell and run:
```
wsl --set-default-version 2
```

Now, WSL 2 is installed on your Windows machine and set as the default version. You can install Linux distributions from the Microsoft Store or other sources to use WSL 2.

# How does Docker API work?

The Docker API works over the internet using HTTP, and it follows the principles of REST, which means it uses standard web communication methods. 

Docker API provides a way for external tools and applications to communicate with Docker programmatically over HTTP. It allows developers to manage Docker containers, images, and other resources, making it easier to automate tasks and integrate Docker into their workflows.


![Alt text](images/Docker-Architecture.png)

# Steps of Creating Images on Docker

1. **docker run hello-world**: This command runs a special Docker image called "hello-world." It's often used as a simple test to verify that Docker is installed and working correctly. When executed, it prints a friendly message to the terminal and then exits.

2. **docker ps**: After running the "hello-world" container, this command shows the list of currently running Docker containers. Since the "hello-world" container has already exited, it won't appear in the list.

3. **docker ps -a**: This command shows a list of all Docker containers, both running and stopped. It provides more detailed information about containers, including those that have already exited.

4. **docker run -d -p 80:80 nginx**: This command runs an Nginx web server in detached mode (-d flag), which means it runs in the background. It also maps port 80 of the host to port 80 of the container (-p 80:80). The container is based on the "nginx" image from Docker Hub. Nginx is a popular web server used for hosting websites and serving web content.

5. **docker ps**: After running the Nginx container, this command shows the list of currently running Docker containers. You should now see the Nginx container listed.

6. **docker stop 67493e8af1ac**: This command stops the Nginx container with the specified container ID (e.g., "67493e8af1ac"). Stopping a container gracefully shuts it down, allowing it to clean up and release resources properly.

7. **docker start 67493e8af1ac**: This command starts the previously stopped Nginx container with the specified container ID. It allows you to restart a container that has been stopped earlier.

8. **docker exec -it 67493e8af1ac sh**: This command allows you to execute a command (sh, which starts a shell) inside the running Nginx container. The -it flags allocate a pseudo-TTY and allow you to interact with the container's shell. This lets you access the container's shell and execute commands directly within it.

9. **docker run -d -p 90:80 ahskhan/tech221-nginx:v1**: This command runs another Nginx container with the port mapping -p 90:80. It pulls the image "ahskhan/tech221-nginx:v1" from Docker Hub if it's not already available locally. This image appears to be a custom version of Nginx with the "tech221" tag.

10. **docker ps**: After running the second Nginx container, this command shows the list of currently running Docker containers. Now, you should see both Nginx containers listed.

11. **docker commit 67493e8af1ac lamatya/tech241-nginx:v1**: This command creates a new Docker image from the changes made to the container with the ID "67493e8af1ac" (the first Nginx container). The new image is then tagged as "lamatya/tech241-nginx:v1."

12. **docker images**: This command lists all the Docker images available on the local machine, including the new "lamatya/tech241-nginx:v1" image created in the previous step.
 

13. **docker push lamatya/tech241-nginx:v1**: This command pushes the "lamatya/tech241-nginx:v1" image to the Docker Hub repository "lamatya/tech241-nginx." By pushing the image, you make it available for others to use and deploy.

14. **docker run -d -p 120:80 lamatya/tech241-nginx:v1**: This command runs yet another instance of the "lamatya/tech241-nginx:v1" container, this time on port 120 of the host to port 80 of the container. This allows you to run multiple containers based on the same image, each accessible on different ports of the host.
