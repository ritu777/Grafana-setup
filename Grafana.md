 <u><h1 style="text-align:center">SETUP OF GRAFANA WITH GRAPHITE </h1></u>

 ## Task Requirement :
To track the status and performance of their IT infrastructure. It provides a centralized platform for monitoring hosts, services, and network devices.

## Environment Details :
**Os**- Ubuntu 20.04</br>
**Cpu**- 8 Core</br>
**Storage**- 1 TB</br>

## Prerequisites Tools :
1. Podman 
2. Grafana 
3. Graphite
   
###Some steps  for installing grafana and graphite on container</br>
##### 1. First we need to install podman by using this command.
```
apt install -y podman
```
**apt:** apt stands for "Advanced Package Tool. It is used to install, update, and manage software packages on the system.</br>

**install:** This is the sub-command that tells apt to install a package. When you use apt install, you're instructing the package manager to download and install the specified software.</br>
**-y:** This is an option flag that stands for "yes." It's used to automatically answer "yes" to any prompts that may come up during the installation process.</br>
**podman:** This is the name of the package or software you want to install.</br>

##### 2. After that make script file with name of .sh
```
vim test.sh
```
![Alt text](<Screenshot from 2023-09-21 21-25-30.png>)
 **Vim:** It is an editor to create or edit a text file.</br>
 **test.sh:** It is the name of script file.</br>

#####3. Now write a script for what you want to install.</br>
Here I have created a pod with the name of **promgrafna** and two containers with their port.</br>
![Alt text](<Screenshot from 2023-09-21 21-46-48.png>)
#####4. Now pod and container has installed.</br>
![Alt text](<Screenshot from 2023-09-22 11-50-19.png>)


##### 5. Now check container status.
```
podman ps -a
```
![Alt text](<Screenshot from 2023-09-22 12-18-00.png>)

##### 6. Go to the web interface.

type **localhost:3002** for grafana's dashboard and  **localhost:8082** for graphite dashboard.</br>

Then you will get grafana's dashboard and there you can put username and password.</br>
**admin** is the default username and password and after that login grafana dashboard will come.



![Alt text](1.5.png)
After login grafana dashboard will come.</br>
![Alt text](1.7.png)


And, this is the dashboard of graphite.</br>
![Alt text](<Screenshot from 2023-09-16 22-48-24.png>)


####  Integerate  part of grafana with graphite :</br>
**Step-1 :** Go to the left side of navigation bar.</br>

![Alt text](navigation.png)
**Step-2:** Click on navigation bar then you will get options.</br>

![Alt text](1.8.png)

**Step-3:** Click on connection option.</br>

![Alt text](connection.png)
Here you will get interface like this:</br>
![Alt text](<Screenshot from 2023-09-22 16-07-54.png>)

**Step-4:** Now you have to search your data source in search bar like here I am using graphite.</br>

![Alt text](rect8072.png)

**Step-5:** After selecting data source then you will get interface and click on  add new data source.</br>

![Alt text](<ad new datat source.png>)

**Step-6:** Now you can write name which is suitable for you and in url section-
  "http://your_server_ip address:8080"</br> 


![Alt text](url.png)
**Step-7:** After filling url part you have to scroll down and click on save & test option.</br>

![Alt text](<save n test.png>)

 Then you have to scroll up and go to the left side where you get option to build dashboard.</br>
![Alt text](build.png) 

**Step-8:** After clicking on build dashboard option,it will come and you have to change time and go to the add option.</br>

![Alt text](time.png)

Choose data source and mertices which you want to monitor.</br>

![Alt text](....png)


Here you have to select metrices like how I selected in given image and click on save option.</br>
![Alt text](save.png)

**Step-9** Here you can give suitable name for dashboard and save.</br>
![Alt text](last.png)

Now panel will come of graph and table form here you can visual you performance.</br>
![Alt text](<2nd last.png>)






