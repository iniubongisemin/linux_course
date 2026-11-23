# 1. Verify the environment and command line tools
>> docker --version

# 2. Verify that ibmcloud CLI is installed.
>> ibmcloud version

# 3. cd /home/project
>> Change to your project folder.

# 4. Clone the git repository that contains the artifacts needed
>> [ ! -d 'CC201' ] && git clone https://github.com/ibm-developer-skills-network/CC201.git

# 5. Change to the directory for your project.
>> cd CC201/labs/1_ContainersAndDocker/

# 6. List the contents of this directory to see the artifacts
>> ls

## Pull an image from Docker Hub and run it as a container
# 1. Use the docker CLI to list your images. 
>> docker images

# 2. Pull your first image from Docker Hub.
>> docker pull hello-world

# 3. List images
>> docker images

# 4. Run the hello-world image as a container.
>> docker run hello-world

# 5. List the containers to see that your container ran and exited successfully
>> docker ps -a

# 6. Remove container by ID
>> docker container rm <container_id>

# 7. List containers to verify removal
>> docker ps -a

## Build an image using a Dockerfile
# 1. The current working directory contains a simple Node.js application that we will run in a container. The app will print a hello message along with the hostname. The following files are needed to run the app in a container:
> app.js is the main application, which simply replies with a hello world message.

> package.json defines the dependencies of the application.

> Dockerfile defines the instructions Docker uses to build the image.

# 2. Use the Explorer to view the files needed for this app. Click the Explorer icon (it looks like a sheet of paper) on the left side of the window, and then navigate to the directory for this lab: CC201 > labs > 1_ContainersAndDocker. Click Dockerfile to view the commands required to build an image.

| You can refresh your understanding of the commands mentioned in the Dockerfile below:
| The FROM instruction initializes a new build stage and specifies the base image that subsequent instructions will build upon.
| The COPY command enables us to copy files to our image.
| The RUN instruction executes commands.
| The EXPOSE instruction exposes a particular port with a specified protocol inside a Docker Container.
| The CMD instruction provides a default for executing a container, or in other words, an executable that should run in your container.

# 3. Run the following command to build the image:
>> docker build . -t myimage:v1

# 4. List images to see your image tagged myimage:v1 in the table
>> docker images

# NOTE: That compared to the hello-world image, this image has a different image ID. This means that the two images consist of different layers -- in other words, they're not the same image.

## Run the image as a container
# 1. Now that your image is built, run it as a container with the following command:
>> docker run -dp 8080:8080 myimage:v1
> OUTPUT: f9ac5edb2d11e7578f6b4e86c50bebb65fee85d9d133b0be741976264c348c02
# The output is a unique code allocated by docker for the application you are running

# 2. Run the curl command
>> curl localhost:8080
> OUTPUT: Hello world from f9ac5edb2d11! Your app is up and running!

# 3. Now to stop the container we use docker stop followed by the container id. The following command uses docker ps -q to pass in the list of all running containers
>> docker stop $(docker ps -q)
> OUTPUT: f9ac5edb2d11

# 4. Check if the container has stopped by running the following command.
>> docker ps

## Push the image to IBM Cloud Container Registry
# 1. The environment should have already logged you into the IBM Cloud account 
>> ibmcloud target

# 2. The environment also created an IBM Cloud Container Registry (ICR) namespace for you. Since Container Registry is multi-tenant, namespaces are used to divide the registry among several users.
# Use the following command to see the namespaces you have access to:
>> ibmcloud cr namespaces

# You should see two namespaces listed starting with sn-labs:
> The first one with your username is a namespace just for you. You have full read and write access to this namespace.
> The second namespace, which is a shared namespace, provides you with only Read Access

# 3. Ensure that you are targeting the region appropriate to your cloud account, for instance us-south region where these namespaces reside as you saw in the output of the ibmcloud target command.
>> ibmcloud cr region-set us-south

# 4. Log your local Docker daemon into IBM Cloud Container Registry so that you can push to and pull from the registry.
>> ibmcloud cr login

# 5. Export your namespace as an environment variable so that it can be used in subsequent commands.
>> export MY_NAMESPACE=$sn-labs-$USERNAME

# 6. Tag your image so that it can be pushed to IBM Cloud Container Registry.
>> docker tag myimage:v1 us.icr.io/$MY_NAMESPACE/hello-world:1

# 7. Push the newly tagged image to IBM Cloud Container Registry.
>> docker push us.icr.io/$MY_NAMESPACE/hello-world:1

# 8. Verify that the image was successfully pushed by listing images in Container Registry.
>> ibmcloud cr images

# Optionally, to only view images within a specific namespace.
>> ibmcloud cr images --restrict $MY_NAMESPACE

