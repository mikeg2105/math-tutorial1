#Notes for docker run version of sage math

#To run the notebook:
sudo docker run -p 8888:8888 mikeg64/jupyter-sage

#To run the notebook using sage math notebooks in host directory ~/proj/math-tutorial1 mounted on docker directory /home/sage/notebooks in the docker container
sudo docker run -p 8888:8888 -v ~/proj/math-tutorial1:/home/sage/notebooks mikeg64/jupyter-sage

To make folders accesible from container use
From chmod -R 1000 math

#Paste sage math server address into browser

To rebuild new image and upload to docker respository

#move to this directory with the dockerfile
sudo docker build . -t jupyter-sage

#set the tag for the newly built docker image
sudo docker tag jupyter-sage mikeg64/jupyter-sage

#now push the docker iage to the new repository
sudo docker push mikeg64/jupyter-sage

#To run the notebook:
docker run -p 8888:8888 mikeg64/jupyter-sage


When docker starts the Jupyter notebook it responds with a message like

    Copy/paste this URL into your browser when you connect for the first time,
    to login with a token:
        http://172.17.0.2:8888/?token=aa43e233d1d6c950c6250b871ffb75a0d8a0ab26c3c5fd93&token=aa43e233d1d6c950c6250b871ffb75a0d8a0ab26c3c5fd93

		 http://ec2-52-213-60-210.eu-west-1.compute.amazonaws.com:8888/?token=aa43e233d1d6c950c6250b871ffb75a0d8a0ab26c3c5fd93&token=aa43e233d1d6c950c6250b871ffb75a0d8a0ab26c3c5fd93

		 i.e. substitute 172.17.0.2:8888 with ec2-52-213-60-210.eu-west-1.compute.amazonaws.com:8888
		 
		 where ec2-52-213-60-210.eu-west-1.compute.amazonaws.com is the address 
		 "Connect to your instance"

4. Connect to your instance using it's Public DNS
           ec2-52-213-60-210.eu-west-1.compute.amazonaws.com

It's important to set 
Security group inbound rules and outbound rules		

set port 8888   
		
		
