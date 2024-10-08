# Dashboards in Grafana of Simulated Data from KepserverEX through InfluxDB  
*Theme*: To get simulation and visualization of the data under the manipulation of different servers.    


## Prerequisite  
* Install Grafana using [this link](https://grafana.com/grafana/download?platform=windows) and create an account through the provided link.  
* Install the InfluxDB using [this link](https://www.influxdata.com/downloads/) and follow the instructions provided there.  
* Install the KepserverEX using [this link](https://my.kepware.com/s/login/SelfRegister) for a free trial.  
* Install Telegraf(version 2.x) from [this link](https://www.influxdata.com/downloads/) and follow provided instructions.  


## KepserverEX  
* Open the file **Cococola.opf** or **Work_Orders.opf** and go to the tags provided in the devices.  
* Open properties of a tag and extract the data of address row which is in the format of **Extracted_Data + tag_purpose**.  
* After that before going to restart the KepserverEX which is present in the the above of the KepserverEX panel install MOSQUITTO software for MQTT purpose and JRE software.  
* ### MQTT  
> Download MOSQUITO software using [this link](https://mosquitto.org/download/) and follow provided instructions and start the server.  
> **Note**: Download java JRE software through the [Link](https://www.java.com/en/download/) and start the server.  
* Now restart the program of KepserverEX which is the play button present on top of the KepserverEx panel.  
**Note**: Before going to restart the program just run the file "Json_Payload.py" which is the data generation python file.  
* Check whether the MQTT server is taking values or not throught the opc client which is prensent on the top of the KepserverEX panel or just right click on the Device_1 and select the opc-client.  


## Telegraf  
* Open the **telegraf.conf** file and just make changes of **outputs.influxdb_v2** and change the bucket, token, and organization in it.
* ### InfluxDB  
> Create a bucket and a token in InfluxDB before including them in **telegraf.conf** file in the official URL "http://localhost:8086/".   
> Before going to execute the telegraf.conf file run the InfluxDB server after navigating to influxd .exe file in command prompt using
> ~~~
> influxd
> ~~~
> Check the data points in data_explorer of InfluxDB after executing telegraf.conf file.  
* Execute the "telegraf.conf" file by navigating to that file in command prompt and execute it in power shell using the command
~~~
.\telegraf.exe --config telegraf.conf
~~~  


## Creating Dashboards in Grafana  
* Add datasouce of InfluxDB in the grafana official website "http://localhost:3000/" and follow the **Grafana.pdf** document.  
* To recheck the Dashboard copy and paste the required **Grafana_Json_file.json** code provided in Demo_Dashboards folder to  import the dashboard of grafana official website and execute it.  
**Note**: Make sure that influxd.exe, Telegraf.exe, Python code or JSON payload are running or executed.  


For more details go through the "Documentation.pdf" and to get the flow go through the "Flowchart.jpg".
