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

# 5. 