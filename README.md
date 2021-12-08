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
Goto ECS Service

![1](https://user-images.githubusercontent.com/58024415/82076932-2da5ff80-96fc-11ea-90d1-2868e91a877e.png)
Click on Get Started
-------
![2](https://user-images.githubusercontent.com/58024415/82077397-f8e67800-96fc-11ea-86e7-4d5e37a3aaa9.png)
Click on Configure
-------
![3](https://user-images.githubusercontent.com/58024415/82077424-06036700-96fd-11ea-85ea-b64dd67f0c46.png)
Click on Update
----
![4](https://user-images.githubusercontent.com/58024415/82077443-14518300-96fd-11ea-8dfb-c540a8c0e9e0.png)
Click on Save
------
![5](https://user-images.githubusercontent.com/58024415/82077454-17e50a00-96fd-11ea-908d-2326935b0198.png)
Click on Save
------
![6](https://user-images.githubusercontent.com/58024415/82077458-1b789100-96fd-11ea-9bbd-a245c2ca4ea3.png)
Click on Next
------
![7](https://user-images.githubusercontent.com/58024415/82077465-1ddaeb00-96fd-11ea-9380-e640d8201772.png)
Click on Next
------

Review Launch Status
------

![8](https://user-images.githubusercontent.com/58024415/82077469-1fa4ae80-96fd-11ea-82fb-6f144bca7e5c.png)

Click on Service
--------

![9](https://user-images.githubusercontent.com/58024415/82077646-65617700-96fd-11ea-96b6-8f4429d2e61c.png)

Goto LoadBalancer in EC2 service and copy DNS
-------

![10](https://user-images.githubusercontent.com/58024415/82077781-9e99e700-96fd-11ea-9371-963269bfb9c2.png)

Goto WebUI and Give as shown below
-------

    http://ec2co-ecsel-h1vjes3arngr-417700232.us-west-2.elb.amazonaws.com:5000/
