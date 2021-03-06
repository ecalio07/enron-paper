# Environment Installation and Configuration
Anaconda 4.3.1(Jupyter Notebook Server 4.3.1, Python 2.7.13, scikit-learn library version 0.18.1, nltk 3.2), git version 2.7.4, Docker Client 17.03.1-ce, docker image ecalio07/ia369z:4.0 adapted from dataquestio/python2-starter.

The experiments can be reproduced in three distinct manners: through anaconda installation on local so, through docker, and oracle virtual box. All of the options make use of Jupyter Notebook as their fundamental tool.

**It is advisable to use Docker as the most reliable of the three options, since image environment will be identical to when it was created. If you rather do it without docker, using only  your local SO and anaconda, be aware that other installations you have, such as other python versions, might affect reproducibility. Or if you prefer virtual box, be aware the file is around 2,50 GB and download might  be affected due to internet limitations**.<br>

**After environment is setup up with the steps below, and before reproduction with Jupyter Notebook begin, it is strongly recommended to test first only the  (%run) cells with comments "REDUCED DATASET" for each type (SVM, BAYES,DECISION TREES). This is because (%run) cells with comment "FULL DATASET" will take long, it might take hours depending on the machine. For that reason, it is best to leave full datasets tests for last.**

Find below reproduction steps with ecalio07/ia369z:4.0 image. If you wish, however, to **create and update your own image** based on another, click [here](Create-Update-DockerImage.md) for details.

=================================< **DOCKER** >================================= 

## Steps to reproduce via DOCKER on MAC OS
1. If you don´t have docker ce client, please install:
https://store.docker.com/editions/community/docker-ce-desktop-mac
2. **Clone for first time or update local git repository**, preferably under /Users/{user}/ directory.<br> Issue command: **git clone https://github.com/ecalio07/enron-paper.git**
3. Run image to create the container. Enter command in terminal: **sudo docker run -p 8888:8888 -v \<cloned enron-paper directory>\:/home/ds/notebooks ecalio07/ia369z:4.0**<br>
This command will automatically download (pull) image ecalio07/ia369z:4.0 from Docker Hub, if image is not available locally. After that, it will copy all content from you local cloned project directory into the docker container (/home/ds/notebooks) and run image in the container.<br> 
**Example in MAC path: sudo docker run -p 8888:8888 -v /Users/marie/enron-paper:/home/ds/notebooks ecalio07/ia369z:4.0**
4. Go to the browser and paste the following url: **http://localhost:8888**
5. In jupyter notebook, access most recent ipyng file inside /deliver folder , executing firstly %run cells for reduced datasets.<br>
**ps: if jupyter notebook opens with no folders or folders different from the project you expect, please verify your local path, right after "-v" parameter for the run command**

## Steps to reproduce via DOCKER on WINDOWS (tested on versions 8 and 10)
1. For most windows versions, install Docker Tool Box: https://www.docker.com/products/docker-toolbox. For Windows 10 Professional and Enterprise 64-bit: https://store.docker.com/editions/community/docker-ce-desktop-windows
2. **Clone for first time or update local git repository**. For docker to mount directory when running image, cloned directory must be inside C:\Users\\{user} directory.<br> Issue command: **git clone https://github.com/ecalio07/enron-paper.git**
3. Open **Docker Terminal(NOT the Windows Terminal)**, make note docker terminal ip address. Usually it is (192.168.99.100). 
4. Run image to create the container. Enter command in terminal:: **docker run -p 8888:8888 -v \<cloned enron-paper directory>\:/home/ds/notebooks ecalio07/ia369z:4.0**<br>
This command will automatically download (pull) image ecalio07/ia369z:4.0 from Docker Hub, if image is not available locally. After that, it will copy all content from you local cloned project directory into the docker container (/home/ds/notebooks) and run image in the container.<br> 
* Example with **Windows path**: **docker run -p 8888:8888 -v /c/Users/DELL/enron-paper:/home/ds/notebooks ecalio07/ia369z:4.0** 
5. Open browser, and use the terminal ip address from step 3, to compose the url: **http://192.168.99.100:8888** and paste it. 
6. Access most recent ipyng file inside /deliver folder , executing firstly %run cells for reduced datasets.<br>
**ps: if jupyter notebook opens with no folders or folders different from the project you expect, please verify your local path, right after "-v" parameter for the run command**

## Steps to reproduce via DOCKER on UBUNTU (tested on version 16.04 LTS):
1. If you don´t have docker client, please install:
https://store.docker.com/editions/community/docker-ce-server-ubuntu
2. **Clone for first time or update local git repository**: **git clone https://github.com/ecalio07/enron-paper.git**
3. Run image to create the container. Enter command in terminal: **sudo docker run -p 8888:8888 -v \<cloned enron-paper directory>\:/home/ds/notebooks ecalio07/ia369z:4.0**<br>
This command will automatically download (pull) image ecalio07/ia369z:4.0 from Docker Hub, if image is not available locally. After that, it will copy all content from you local cloned project directory into the docker container (/home/ds/notebooks) and run image in the container.<br> 
4. Go to the browser and paste the following url: **http://localhost:8888**
5. In jupyter notebook, access most recent ipyng file inside /deliver folder , executing firstly %run cells for reduced datasets.<br>
**ps: if jupyter notebook opens with no folders or folders different from the project you expect, please verify your local path, right after "-v" parameter for the run command**

==============================< **LOCAL SO WITH ANACONDA** >======================= 

## Steps to reproduce via Anaconda on Windows:
1. Download and Install Anaconda 4.3.1 for Python 2.7.13. https://www.continuum.io/downloads . Anaconda will include all packages necessary for this experiment: git, python 2.7, scikit-learn and jupyter notebook.
2. After installation close the terminal and start a new one.
3. Enter into preferred directoy and issue the command to clone project:**git clone https://github.com/ecalio07/enron-paper.git**
4. Enter into the newly cloned directory root(c:\xxx\xxx\enron-paper) and issue the command: **jupyter notebook**
5. In the browser enter url http://localhost:8888 and reproduce the experiments using the most recent file .ipynb within /deliver directory, executing firstly %run cells for reduced datasets.<br>

## Steps to reproduce via Anaconda on Ubuntu:
1. Download and Install Anaconda 4.3.1 for Python 2.7.13. https://www.continuum.io/downloads . Anaconda will include all packages necessary for this experiment: git, python 2.7, scikit-learn and jupyter notebook.
2. After installation close the terminal and start a new one.
3. Enter into preferred directoy and issue the command to clone project:**git clone https://github.com/ecalio07/enron-paper.git** 
4. Enter into the newly cloned directory root(/home/youruser/notebooks/enron-paper) and issue the command: **jupyter notebook** 
5. In the browser enter url http://localhost:8888 and reproduce the experiments using the most recent file .ipynb within /deliver directory, executing firstly %run cells for reduced datasets.<br>

=================================< **VIRTUALBOX** >=============================

## Steps to reproduce via VirtualBox:
1. If you don't have VirtualBox installed, please consult url:
https://www.virtualbox.org/wiki/Downloads
2. Start Oracle Virtual Machine and donwload the file .OVA [here](https://drive.google.com/file/d/0B4KJCoCOJkpGZWlIeFY5Qk1LSFU/view?usp=sharing)
3. Go to menu File/Import Appliance, and select donwloaded *.OVA.
4. Start  (VM Ubuntu 16.04_escience) and open a terminal.
5. Go into the directory enron-paper using terminal: **cd /home/enron/enron-paper**
6. Verify if git project is udated using (git fetch/git status). If necessary, update from repository.
7. Inside enron-paper root directory, execute the following command: **jupyter notebook**
8. Wait for the browser to open in the following url : http://localhost:8888. Insert manually if necessary.
9. To reproduce the project, follow instructions in the most recent paper into /deliver folder, executing firstly %run cells for reduced datasets.<br>
 
