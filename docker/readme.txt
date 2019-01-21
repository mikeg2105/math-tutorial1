#Notes for docker run version of sage math

#To run the notebook:
sudo docker run -p 8080:8080 mikeg64/jupyter-sage

#Paste sage math server address into browser

To rebuild new image and upload to docker respository

#move to this directory with the dockerfile
sudo docker build . -t jupyter-sage

#set the tag for the newly built docker image
sudo docker tag jupyter-sage mikeg64/jupyter-sage

#now push the docker iage to the new repository
sudo docker push mikeg64/jupyter-sage
