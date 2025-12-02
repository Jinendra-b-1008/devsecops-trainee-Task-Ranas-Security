1.user_name.sh - The script is used to print the user name and working directory 
2.The docker file used pyhton:3.2 slim as a base image and in that we created user and executed the script layer as non root user
    creating the image
    docker build -t user_script .
