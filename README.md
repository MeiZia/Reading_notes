# CyATP:Cybersecuirty Awareness Training Platform

[CyATP](http://www.cyber-atp.tk) is a web platform that makes use of the Flask framework for security awareness training.
This platform provides rich training content and combines the game method for learning.
Through learning the security concept and playing the serious game on this platform, 
learners can increase security knowledge and as much as possible to use it in the real environment.  

An overview of the architecture of CyATP is provided in the figure below.

![CyATP Overview](http://www.meizia.net/pic/overview.jpg)

The front end is developed by Bootstrap and jQuery, and the back end is composed of the Neo4j graph database and Flask.
The trainees conducts training through interaction with the front end web pages.
The learning materials are including：security concept map and text, quiz data, crossword puzzle data.


## Prerequisites
The following step must be carried out before using CyATP:
* **Intall Neo4j database.** We store the learning material `concept map` into the Neo4j graph database to make the trainees know more about security knowledge structure. You can download the Neo4j Community Edition for free: https://neo4j.com/download-center/#community. We recommend Neo4j version4.0+. (Note, all versions of  Neo4j require Java to be preinstalled.)

The following step is optional prepared：
* **Create a new virtual environment.** A lot of ways can build a new virtual environment, such as: venv(for Python 3), virtualenv(for Python 2), Conda, and so on. We recommend use the venv to create a "virtual" isolated Python installation and install packages into this virtual installation. You can run the following commend to create and activate the `cyatp-env` environment:
  ```
  python3 -m venv cyatp-env
  source cyatp-env/bin/activate
  ```


## Setup
To set up CyATP manually, follow the steps below:
1. **Download this project the lastest version.** Download the archive of the latest version of the CyATP source code from the [releases](https://github.com/meizia/cyatp) page.

2. **Install packages in the virtual environment.** Go to the directory where the project is located, find the `requirements.txt` from the project file, and install the packages required by running the following command:
  ```
  pip install requirements.txt
  ```
3. **Set the Neo4j database.** Before configuring the database, please stop running it. Then, Copy the `\neo_db\neo4j.db` in the project to the `\neo4j\bin` is located, and run the following command to load the learning material database:
  ``` 
  neo4j-admin load --from=neo4j.db.dump --database=neo4j --force 
  ``` 
### Notes 
* When you install Neo4j and enter http://localhost:7474 for the first time, you will be asked to change the default database password. You should also change the default password in the project's `/neo_db/config.py` file. 
* After you set up the database, go to http://localhost:7474 and run the following command to see the data:
  ``` 
  MATCH (n) RETURN n
  ``` 
  If you want to get other information in the database, you can use [Cypher](https://neo4j.com/developer/cypher/) to retrieve data from graph database.


## Quick Start

Start run the project.   
```
python app.py 
```
成功运行之后可以在localhost中开到初始界面。

Begin the training:

最终平台的页面是什么样子的。

## Deploy this project to the server 
安装ngnix
安装wg什么什么
进行配置

### Notes部署的时候可能会遇到的问题。

## Files Includes With This Project:
├── README.md
├── app.py
├── requirements.txt
├── neo_db
├── raw_data
├── script_py
├── static
│   ├── css
│   ├── fonts
│   ├── images
│   ├── index
│   └── js
└── templates

