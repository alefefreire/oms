# Virus Disease Project
A Study of a virus disease in a certain population 
# Setup
The Virus Disease analysis in only served in the user's **local host** using `Docker`
## Testing Instructions
Make sure you have [Docker](https://docs.docker.com/engine/install/) installed and follow the instructions below:

1. To build the image, run these commands in terminal:
```
$ git clone https://github.com/alefefreire/oms.git
$ cd oms
$ docker build -t image-oms .  
```
2. Once the image's been built, you can run the jupyter notebook with the command below:
````
$ docker run -d --rm --name jupyterserver -p 8888:8888 -v $PWD/notebooks:/notebooks image-oms
````
**IMPORTANT**: Make sure that your Docker Setup has pre configured memory resources of, at least, 8GB of RAM otherwise the jupyter's kernel can eventually die in the end to end runnning.

3. After running the container, click here: http://127.0.0.1:8888
4. A web page will appear for you requesting a token access to `jupyter notebook`. In order to get this token, in your terminal, run the following command:
````
$ docker container logs jupyterserver
````
5. In the logs, search for a link which looks like the following one:
````
http://127.0.0.1:8888/lab?token=a837ddbf2c36628de39831f5b15b5b9c4d5bd50eb410fd40
````
6. Just copy and paste the *serial number* after `token=` and click the `Log in` button and the access to `jupyter lab` will be granted.
7. Enjoy the analysis.  :) 