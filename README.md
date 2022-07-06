# DocWeb
A Portfolio website hosted by making the image in the docker container and then host it on Heroku.


This project is based on Containerization of applications.In our project we created a web Portfolio using python,HTML and CSS. Containers are small computation units that are light weight, fast to deploy over servers within seconds. When you run an application on the container at the time of production user need to make an image of the container running the application and then that image is deployed directly to the servers with all neccessaries dependencies attached within the image only.

We start by making the requirements.txt file by running the lower command.
```pip freeze > requirements.txt```


To install the packages for a different project we can use 
```pip install -r requirements.txt```

# Setting up the docker.
The system must have docker desktop installed on it so as to run docker containers.
<br/>Step 1:- How to setup a Docker
Make a Dockerfile to intall all the required packages, dependencies so as to run our application. Our Dockerfile looks like this.
```
FROM python:3.8-alpine

# copy the requirements file into the image
COPY ./requirements.txt /app/requirements.txt
WORKDIR /app
RUN pip install -r requirements.txt
COPY . /app 
ENTRYPOINT [ "python" ]

CMD ["view.py" ]
```

Step 2:- Build the docker image 
```
docker image build -t (container_name).
docker image build -t myapp   #my docker image name  # t is used for tagging an image or we can say naming an image.

```
Step 3:- We now run a container with the image we have builded.
```
docker run -p 5000:5000 -d myapp    #p is used for defining port to comminute with external network -d is used for detached mode.
```

Now if we go on localhost:5000 we get to see our web application up and runnning
After this we deployed our container image to Dockerhub registery and after that we made it hosted on Heroku.

Link to the website :- (Porti45)[https://porti45.herokuapp.com/]
Upload a screenshot ```conatiner based.png``` of Heroku plateform showing the application hosted as container.
