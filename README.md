# ZABBIX
#  1.  Overview
-	Zabbix is a software that monitors numerous parameters of a network and the health and integrity of servers, virtual machines, applications, services, databases, websites, the cloud and more.
-	Zabbix uses a flexible notification mechanism that allows users to configure e-mail- based alerts for virtually any event. This allows a fast reaction to server problems.

#  2.  Zabbix's Components
Zabbix consists of several major software components, the responsibilities of which are outlined below:
-  Zabbix Server"
•	This is the centre of the Zabbix software.
•	The Server can remotely check networked services (such as web servers and mail servers) using simple service checks, but it is also the central component to which the Agents will report availability and integrity information and statistics
•	The Server is the central repository in which all configuration, statistical and operational data are stored, and it is the entity in the Zabbix software that will actively alert administrators when problems arise in any of the monitored systems.

-  Zabbix Agent:
•	In order to actively monitor local resources and applications (such as harddrives, memory, processor statistics etc.) on networked systems, those systems must run the Zabbix Agent.
•	The Agent will gather operational information from the system on which it is running and report these data to the Zabbix for further processing.
•	In case of failures (such as a harddisk running full, or a crashed service process), the Zabbix Server can actively alert the administrators of the particular machine that reported the failure.
•	The Zabbix Agents are extremely efficient because of use of native system calls for gathering statistical information.

-  The Web Interface:
•	In order to allow easy access to the monitoring data and the configuration of Zabbix from anywhere and from any platform, the Web-based Interface is provided.
•	The Interface is a part of the Zabbix Server and is usually (but not necessarily) run on the same physical machine as the one running the Zabbix Server.

#  3.  Operation:
-	Zabbix works via three discovery mode options:
o	Network discovery periodically scans an IT environment and records a device's type, IP address, status, uptimes and downtimes…

o	Low-level discovery automatically creates items, triggers and graphs based on the discovered device. Low-level discovery can create metrics from Simple Network Management Protocol (SNMP) object identifiers, Windows services, Open Database Connectivity (ODBC) Structured Query Language (SQL) queries, network interfaces and more.

o	Auto-discovery automatically starts monitoring any discovered device using a Zabbix agent

# Topology

![image](https://github.com/nguyendinhkha/Network-and-System-Administration/assets/82517228/20b329f5-c2af-4d88-8e42-ba47ff90d520)

# 2.	Setup Server &    3.   SETUP AGENT (Linux) AND CONFIGURE (review PDF file)

#  4.  MONITOR FROM SERVER (use the web interface)
-  To monitor from server , first we have to create host by doing the following steps :
1.	Go to zabbix server ‘s display
2.	Click Configuration => hosts => Create host

![image](https://github.com/nguyendinhkha/Network-and-System-Administration/assets/82517228/3a0906bf-d09c-4468-996c-9402d32a3e4e)

-  Fill the form with information of the agent and click add:
![image](https://github.com/nguyendinhkha/Network-and-System-Administration/assets/82517228/16d03a9b-a7a1-4b85-9ef0-476efc899067)
For example : My added host

Check the connection : " Monitoring => hosts"

![image](https://github.com/nguyendinhkha/Network-and-System-Administration/assets/82517228/73cd1578-c0bc-4bcb-bec8-43787d9a0e69)
=> Working fine

-  Then, right click on the name of agent and choose the part want to see:

![image](https://github.com/nguyendinhkha/Network-and-System-Administration/assets/82517228/dabe997e-a071-48e3-806c-2c670abb323e)

![image](https://github.com/nguyendinhkha/Network-and-System-Administration/assets/82517228/0139a2e8-e5e4-4f0b-bb9c-4c325948a56d)
Choosing “ latest data “ for example.

#  5.  SETUP AGENT (WINDOW)
Download window agent : "https://www.zabbix.com/download_agents?version=6.2&release=6.2.3&os=Windows&os_version=Any&hardware=amd64&encryption=OpenSSL&packaging=MSI&show_legacy=0 "

-  Install and fill the ip of zabbix server:
![image](https://github.com/nguyendinhkha/Network-and-System-Administration/assets/82517228/faef211e-fcff-4fe1-8caa-e76b5dcb2da1)
Go to server and configure client with Host name and its ip address.

=> The result :

![image](https://github.com/nguyendinhkha/Network-and-System-Administration/assets/82517228/0fa9a98b-e892-4cae-bd73-4dbee9f93bcf)

Window agent is monitored.

![image](https://github.com/nguyendinhkha/Network-and-System-Administration/assets/82517228/88b34fbf-5d12-41ff-a0d3-5246a192c851)

![image](https://github.com/nguyendinhkha/Network-and-System-Administration/assets/82517228/74c15207-6a4f-476c-b2da-0a38d07071bb)

![image](https://github.com/nguyendinhkha/Network-and-System-Administration/assets/82517228/ba134eff-5f99-4e62-8b26-0eb320ca8e99)

![image](https://github.com/nguyendinhkha/Network-and-System-Administration/assets/82517228/d0256e79-6e42-4673-b0fe-e1220f90d20e)

![image](https://github.com/nguyendinhkha/Network-and-System-Administration/assets/82517228/6e050d03-702c-4913-826b-b58d9b5b16d5)

=> Some of its graphs ‘s information.

#  6.  Setup (WEBSERVER / WEBSITES) for monitoring
-  Configuration => hosts => Create host => Add
![image](https://github.com/nguyendinhkha/Network-and-System-Administration/assets/82517228/6ad6485b-e648-4126-9aae-69a771378940)

Different from window and linux monitoring , the hostname of website can be set by user opinion.

![image](https://github.com/nguyendinhkha/Network-and-System-Administration/assets/82517228/0c9d2523-cedc-48df-9006-cbfcece8e673)

-  Click on “web” button of “Web monitoring” to configure its feature:
![image](https://github.com/nguyendinhkha/Network-and-System-Administration/assets/82517228/297141f2-4754-4693-be26-740dfc35a8a7)

-  Next , “Create web senario” in the top right corner:
![image](https://github.com/nguyendinhkha/Network-and-System-Administration/assets/82517228/ca4b9564-57bf-4944-add0-f7869c1b5ea2)

-  Now , there are a lot of parameters to fill in, and name’s field is optional.
+  Update interval : how often user want to check our website
+  Attemps: how many times user want to collect data from the web
+  Agent: kind of browser user want to monitor
+  Variables and headers: the purpose of these set up is to check the page is it up or is running , check the response code
E.x: Some sort of forum , when user want to log in , post some sort of comments , verify that this comment is pushlished , etc.
![image](https://github.com/nguyendinhkha/Network-and-System-Administration/assets/82517228/5d6a9392-b159-43b5-b6f1-2b4400a50786)

-  Move to “step” and click add:
![image](https://github.com/nguyendinhkha/Network-and-System-Administration/assets/82517228/21d62ed1-37eb-4998-9f12-795d8380618e)

![image](https://github.com/nguyendinhkha/Network-and-System-Administration/assets/82517228/812543e1-7216-47de-8dd0-2403040233c9)

+  Post type : post the form data or the raw data
+  Post field : what kind of post fields with the values I want to add variables and headers.  This is only used if I want to login , post some content and check its conditions (for the simple monitoring I’ll skip this )
+  Follow redirects : depends on webpage’s configuration . Whether this url is opening the web page right away or there is some sort of redirect
+  Retrieve mode : Full body or just the header of the reponses or both . Also can apply the curl request through CLI when checking some sort of the webpage
+  Time out : what will be the timeout for this check
+  Required string : allow to check some sort of the string in the webpage I try to open . I can check for “whatever string” in the web page
+  The required status code : this should be http code and if everything is correct => The expected code is 200

#  DEMO
Click Add.  This demo I’ll check two pages so this is the configuration of the second page :

![image](https://github.com/nguyendinhkha/Network-and-System-Administration/assets/82517228/00bd4aa5-e312-490f-beff-3153d90ed60a)

![image](https://github.com/nguyendinhkha/Network-and-System-Administration/assets/82517228/1abf6e49-1614-4394-811a-cb42d9c1a8a9)

![image](https://github.com/nguyendinhkha/Network-and-System-Administration/assets/82517228/28439779-4272-4dbe-85d1-475f11f9340e)

-  After added two steps in the scenario .Let’s go to Monitoring -> Hosts

![image](https://github.com/nguyendinhkha/Network-and-System-Administration/assets/82517228/b0bbb533-5142-4bcc-9e7c-c31a06ecf66c)

-  In the “Web monitoring” has the “web” with the blue color , click on it and see its status
![image](https://github.com/nguyendinhkha/Network-and-System-Administration/assets/82517228/75f0e7e1-5638-453e-bc42-d188f84d9ca3)

-  Click “Zabbix documentaion” to have a closer look
![image](https://github.com/nguyendinhkha/Network-and-System-Administration/assets/82517228/df69beac-4684-470d-8ef8-40c47afab5ad)

-  I can see its speed , response time , response code , status and its graphs:

![image](https://github.com/nguyendinhkha/Network-and-System-Administration/assets/82517228/b770836a-8e8e-4d17-9e92-9ce99b33285e)

![image](https://github.com/nguyendinhkha/Network-and-System-Administration/assets/82517228/7af8b529-a061-4f8d-8467-038d4b3ce896)

-  These pages don’t support javascripts so as long as I log in form is using javascript most likely I will not able use tips and tricks or whatever else to success-fully log in using the web scenario
-  There is no IF – ELSE . Ex : I created multiple steps no limitations , if the first step fails then all scenario fails and there is no way I can do the if else scenario
To solve this problem, I created a trigger for my monitoration ( Triggers are logical expressions that "evaluate" data gathered by items and represent the current system state )
-  Configuration -> Hosts -> “Web monitoring” -> triggers -> Create triggers

![image](https://github.com/nguyendinhkha/Network-and-System-Administration/assets/82517228/1c52bd1a-642e-444a-87ca-e62beae863f6)

-  In this trigger , I set up if last value is higher than 5 then it’ll be a high severity problem
-  Click add
-  In the previous data , the first index page’s download speed is much higher than 5 . Now I go to Monitoring -> Dashboard  -> Global view to see what are showed .

![image](https://github.com/nguyendinhkha/Network-and-System-Administration/assets/82517228/bc39264d-5f83-4eec-817f-eb87b104aa90)

=> The problems are showed .

P/s : There are more informations than just download speed , … depends on my configuration and what I want to see.

