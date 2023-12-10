[![CI](https://github.com/nogibjj/Alicia_Individual_4/actions/workflows/cicd.yml/badge.svg)](https://github.com/nogibjj/Alicia_Individual_4/actions/workflows/cicd.yml)
## Individual Project 4: Auto Scaling Flask App Using Any Platform As a Service
### Demo Video:

### Flask App Link:

[Chitchat](http://chitchat123.azurewebsites.net)

### Goal:

This project aims to harness the power of Generative AI technology to develop a web-based chat application using Flask. The development and deployment processes are streamlined through the use of Docker for containerization, ensuring a consistent and isolated environment. Additionally, we leverage Azure for cloud deployment, taking advantage of its robust auto-scaling capabilities to ensure efficient resource utilization and optimal performance.

### File Tree:

```bash
.
├── Dockerfile
├── LICENSE
├── Makefile
├── README.md
├── app.py
├── main.py
├── repeat.sh
├── requirements.txt
├── setup.sh
├── static
│   └── style.css
├── templates
│   ├── about.html
│   ├── home.html
│   ├── index.html
│   └── prompt.html
└── test_main.py
```

## How to create and proceed this project

1. Create a Dockerhub account and a Docker Repository for incoming Docker image.
   
![Alt text](Create_Dockerrepo.png)

3. Log into the Azure
   
5. Find the App Services in search bar
   
![Alt text](<App Services.png>)

7. Click on create "Web App", in "publish" option select "Docker Container", the app name gonna be at the start of your url.

![Alt text](Create_Webapp.png)

8. Click on top session "Docker", select Image Source as "Docker Hub", copy paste the path of Docker repository from Docker hub and click 
"create" to create web app at last.

![Alt text](Webservice_Dockerset.png)

9. Navigate on the left menu, click on "Configuration" under Settings, click "New application setting" and set the port name as "WEBSITES_PORT" with value of 5000

![Alt text](PORT_set.png)

10. Build the Docker Image

`docker build -t <yourimagename> .` Replace `yourimagename` with the name you wish to give to your 
Docker Hub later

![Alt text](Dockerbuild.png)

11. Run the Docker Image(Optional)

`docker run -p 5000:5000 <yourimagename>`

5000 is your port value, remember? when you set it up in Azure Web service

![Alt text](runimage.png)

12. Tag and Push/pull to Docker Hub:

If you create Dockerhub account with your github, 

`docker login`

`docker tag <yourimagename> <yourusername>/<yourrepository>:<yourtag>`

`docker push <yourusername>/<yourrepository:yourtag>`

If you are other people who want to see your Docker image,

`docker pull <yourimagename>/yourrepository:yourtag`

13. Build and Push docker image to Azure web service:

`docker login --<insert username>`

`docker build -t <insert username>/<insert repo name> .`

`docker push <insert username>/<insert repo name>`


After doing all the above steps, now you can safari on my web page with the default domain provided on Azure.
Below is the screenshot of the webpage

![Alt text](homepage.png)

![Alt text](introduction.png)

![Alt text](Chatpage.png)

And also the CI/CD passed

![Alt text](CI_CD.png)
