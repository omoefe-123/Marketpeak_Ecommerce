## Capstone Project-Introduction to Cloud Computing

# Capstone Project: E-Commerce Platform Deployment with Git, Linux, and AWS
Project Instructions:

In this project I will be developing an e-commerce website for a new online marketplace named "MarketPeak." This platform will feature product listings, a shopping cart, and user authentication.To implement this project I will use Git for version control, the develpoment platform will be in a Linux environment, and deploy it on an AWS EC2 instance. You can find a suitable website template here to kickstart your development

## Tasks

**1. Implement Version Control with Git**

## 1.1. Initialize Git Repository
![repositry-withou-a-README.md](Images/creating-repo.jpg)

![git-command](Images/git-command.jpg)

I created a project directory or folder and named it "Marketpeak_Ecommerce using vscode cli i used the following command

 `mkdir MarketPeak_Ecommerce`

 `cd MarketPeak_Ecommerce`

 `git init`

 `git add .`

 `git commit -m "...."`

 `git push`
 
 ## 1.2. Obtain and prepare the E-commerce Website Template
 I obtained and prepared a pre-existing e-commerce website template
 ![Html-Template](Images/html-template.jpg)
 I downloaded a Website Template by visiting (Tooplate)
 ![Template-download](Images/Template-download.jpg)

 I obtained also the url
 [Template](https://www.tooplate.com/view/2130-waso-strategy)
 
 ## 1.2 Prepare the Website Template: 
 Extract the downloaded template into my project directory,
  marketpeak_Ecommerce  
                    

## 1.3. Stage and commit the Template to Git
 ```git add .
 git config --global user.name "YourUsername"
 git config --global user.email "youremail@example. com"
 git commit -m "Initial commit with basic e-commerce  site structure"
 ```
 ## 1.4 Push the code to your Github repository

![zip-file](Images/2137_barista_cafe.jpg)

# 2. AWS Deployment
## Task 2.1: Setup an AWS EC2 instance
* Log into the AWS management Console.
* Launch an EC2 Instance using an Amazon linux AMI
* Connect to the instance using SSH
* The image below shows the EC2 on AWS Console:

![Launching-instance](Images/Lauching-linux-server.jpg)

## 2.2. Clone the repository on the Linux Server
  * Navigate to my repository in my github console
  * i selected the `code` as highlighted in the image below
  * Using HTTPS Method

![HTTPS-method](Images/HTTPS-code.jpg)

  ## Note: With AWS Linux, git is not preinstalled so i have to install it manually by using the following command
  
   `sudo yum istall git`

   `git clone https://github.com/omoefe123/MarketPeak_Ecommerce.git`
   
 The image below shows the cloning interface on the cli

![instaling-cloning-git](Images/clone-linux-server.jpg)

# Task 3. Installing a Web Server on EC2
 Using yum package manager for htttpd software
 The below command was used to install Apache

 `sudo yum update -y`

`sudo yum install httpd -y`

`sudo systemctl start httpd`

`sudo systemctl enable httpd`

## Task 4. Configure httpd for Website
  
  Prepare the Web Directory: Clear the default httpd web directory and copy MarketPeak Ecommerce website files to it.
  The below command was used:

 `sudo rm -rf /var/www/html/*`
s
 `sudo cp -r ~/Marketpeak_Ecommerce/* /var/www/html/`
 
  This is the out put image below

  ![The-output-image](Images/prepare-web-directory.jpg)

  To reload httpd, the following command was used to apply cganges

  `sudo systemctl reload httpd`

  Below is the output interface

![Reload-httpd](Images/system-reloaded.jpg)
  
## Task 5 Access Website From Browser
  * With httpd configured and website files in place, Marketpeak Ecommerce platform is now live on the internet:
  * Open a web browser and access the public IP of your EC2 instace to view the deployed website.
## Note: HTTP Port 80 was opened in AWS Security group

![](Images/Barista_cafe.jpg)


## Task 6 Continous Integration and Deployment Workflow 
 * To ensure a smooth workflow for developing, testing and deploying my e-commerce platform follow this structured approach.
 ### 1. Developing New Features and Fixes
   Create a Develpoment Branch using the below command
   
   `git branch development`

   `git checkout development`

![command](Images/git-command-interface.jpg)

   * Version control With Git
    Run the following command to stage, commit, and push to develpoment branch

    `git add .`

    `git commit -m "Add new features or fix bugs"`

    `git push origin development`
    





 


