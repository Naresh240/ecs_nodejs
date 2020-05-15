# ecs_nodejs

Pre-requisites
--------
    - Install Git
    - Install Docker
    
Clone code from Git
-----
    git clone https://github.com/Naresh240/ecs_nodejs.git
    cd ecs_nodejs
    
Create Repository in ECR 
----------
    aws ecr create-repository --repository-name ecs-flask/home
    
Login to ECR
-------
    $(aws ecr get-login --no-include-email --region us-west-2)
    
Build docker image
------
    docker build -t ecs-flask/home .
    
Tag your image so you can push the image to this repository
-----------
    docker tag ecs-flask/home:latest 791382328408.dkr.ecr.us-west-2.amazonaws.com/ecs-flask/home:latest
   
Push image to repository
------------
    docker push 791382328408.dkr.ecr.us-west-2.amazonaws.com/ecs-flask/home:latest
    
Now open ECS and deploy Application
------------
    
