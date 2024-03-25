# DevOps task1
Task -1 :
1) Create a basic python or php web server that says :  "hello world"
2) Create a docker container for it.
3) host it on an EC2 or free azure server.

#Task step by step to perfom:-

1) First I Launch new server with Aws consule step as follows:
   a. Login consolue => launch instance
   
   ![1](https://github.com/Aftabmullaa/Devopstask1/assets/73701345/8a566b19-eac6-403a-abbb-0618060fc4e2)

   b. Give Name(devopstask1),Select OS(Amazon linux),Generate key pair(linux),Create a security group(SG) => lAUNCH Instance.

    ![2](https://github.com/Aftabmullaa/Devopstask1/assets/73701345/87b33ef4-c2b8-4ef7-b238-1a6532f0766b)

   ![3](https://github.com/Aftabmullaa/Devopstask1/assets/73701345/12ef55ec-0a58-4223-875e-38a77e2f7b40)

   ![4](https://github.com/Aftabmullaa/Devopstask1/assets/73701345/f23481c6-caad-479b-9321-b394af1d761b)

   ![5](https://github.com/Aftabmullaa/Devopstask1/assets/73701345/8f0056d3-c23f-4b73-91dc-7b4aff17d6fa)

   ![6](https://github.com/Aftabmullaa/Devopstask1/assets/73701345/bad8d7f9-a32d-43b4-9779-d636fd896d4e)

2) Second connect launch instance

   ![7](https://github.com/Aftabmullaa/Devopstask1/assets/73701345/36a703c6-9e42-417d-b12b-36fe2332863b)

   ![8](https://github.com/Aftabmullaa/Devopstask1/assets/73701345/79e4a826-f2c1-459d-8e07-a8231b607c99)

   ![9](https://github.com/Aftabmullaa/Devopstask1/assets/73701345/bd440124-7e7b-4976-9c42-6625956a260c)

3) Creating shell script file(all.sh) to install dependencies:-
    a. update YUM package manager
    b. install python3
    c. install docker
    d. start docker
   
   ![10](https://github.com/Aftabmullaa/Devopstask1/assets/73701345/9297716b-f158-4d9c-a780-851c61afbcf4)

   ![alldependies](https://github.com/Aftabmullaa/Devopstask1/assets/73701345/af5a9a95-8678-48cb-8053-a41e741cf49e)

   ![11](https://github.com/Aftabmullaa/Devopstask1/assets/73701345/81e8d4eb-0247-42f6-b620-a6e21ffa3258)

   ![12](https://github.com/Aftabmullaa/Devopstask1/assets/73701345/94b15be9-c662-47e2-b78c-70df88d9c312)

4) Create a Python HTTP server:
   a. sudo vi server.py

   ![13](https://github.com/Aftabmullaa/Devopstask1/assets/73701345/09c55f84-5734-4ee4-aadc-2e2bbe7b00f5)

5) Creating Dockerfile without extension Dockerize the server:
   sudo vi Dockerfile.
   
   ![14](https://github.com/Aftabmullaa/Devopstask1/assets/73701345/727171f2-6958-4366-9fa4-3a0ea6c1ebbe)

6) Build the Docker image:
   docker build -t python-web-server .

   ![15](https://github.com/Aftabmullaa/Devopstask1/assets/73701345/54156333-9ac1-4122-a9a1-21cf1a855414)

   ![16](https://github.com/Aftabmullaa/Devopstask1/assets/73701345/3844ee23-7f87-4a6c-a9d9-4261ebac770b)

7) Run the Docker container:
   docker run -d -p 8000:8000 python-web-server

   ![17](https://github.com/Aftabmullaa/Devopstask1/assets/73701345/94419b4d-4895-4508-b3bd-5062bdec1ef5)

8) Access "Hello, world!" through the EC2 public IP:

   ![18](https://github.com/Aftabmullaa/Devopstask1/assets/73701345/55e572a3-3f38-4c44-93bb-f0c5004a9858)

    EC2 instance's security group allows inbound traffic on port 8000:

     ![19](https://github.com/Aftabmullaa/Devopstask1/assets/73701345/79168179-250b-4e0a-93f1-99b1176f163a)

     ![20](https://github.com/Aftabmullaa/Devopstask1/assets/73701345/fd96063b-e8f7-4b29-a021-a25120e55fc6)

   To check output paste public ip new tab: Eg: http://3.81.166.136:8000/
   
   ![21](https://github.com/Aftabmullaa/Devopstask1/assets/73701345/560006c1-0ee8-414f-8750-7e472b85a73d)



   Q.Explain in detail this docker code LINE by LINE:
     1) FROM python:3.9-slim:
        FROM: Specifies the base image for your Docker image. In this case, it's python:3.9-slim, which is an official Python image from Docker Hub.
     2) WORKDIR /app :
        WORKDIR: Sets the working directory inside the container to /app
     3) COPY server.py . :
         COPY: Copies the server.py file from the host (your local machine in this case) to the /app directory inside the container. The . at the end of the command means to copy it to the current working 
         directory (/app in this case).
     4) CMD ["python", "server.py"]
         CMD: Specifies the command to run when the container starts. Here, it runs the Python script server.py using the python interpreter.



     
    






   







   


