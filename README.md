
<br />
<p align="center">
  <a href="https://github.com/github_username/repo_name">
    <img src="logo.png" alt="Logo" width="80" height="80">
  </a>

  <h3 align="center">efs_dotnet</h3>

  <p align="center">
    Elastic FluentD Splunk .net example
    <br />
   
  </p>
</p>



<!-- TABLE OF CONTENTS -->
<details open="open">
  <summary><h2 style="display: inline-block">Table of Contents</h2></summary>
  <ol>
    <li>
      <a href="#about-the-project">About The Project</a>
      <ul>
        <li><a href="#built-with">Built With</a></li>
      </ul>
    </li>
    <li>
      <a href="#getting-started">Getting Started</a>
      <ul>
        <li><a href="#prerequisites">Prerequisites</a></li>
        <li><a href="#installation">Installation</a></li>
      </ul>
    </li>
    <li><a href="#usage">Usage</a></li>
  </ol>
</details>



<!-- ABOUT THE PROJECT -->
## About The Project


This project aims to bring a development template for a .net app to send logs to both Elastic and Splunk


### Built With

* []() Elastic
* []() Splunk
* []() FluentD
* []() .net core app



<!-- GETTING STARTED -->
## Getting Started

To get a local copy up and running follow these simple steps.

### Prerequisites

1. Go to the code directory and build the .net app image
   ```
   cd src/
   chmod 777 build.sh
   ./build.sh
   ```
2. Spin the enviroment up
   ```
   cd ..
   docker-compose up 
## Usage

1. When you log in to kibana
```http://localhost:5601```
2. You will need to create an index pattern
3. Just write ```fluent*``` its the name of the index template

4. For splunk, you will notice that it doesnt receive logs
thats beacuse we need to reconfigure its index token
5. First login to splunk
http://localhost:8000
6. Go to http://localhost:8000/en-US/manager/search/http-eventcollector
7. Click on new token
```
Name it: webapp
Select the index: webapp
```
8. Copy the token
9. Go to the fluentd dir in this project
Edit the ```fluent.conf``` file
10. Go to the splunk section and change the token with the one you copied

11. Now reset the fluentd service so it will load its new config
```
docker-compose up --force-recreate fluentd
```
12. Make sure the token got updated, you will see in the fluentd logs the loaded config

13. Reset the .net app service, everytime you do it will send a new log

14. In the splunk search type:
```
index="webapp"
```




