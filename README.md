# JMeter-configuration
Distributed Testing by JMeter configuration steps:
This is short notes on how to use multiple systems to perform stress testing using JMeter. Before we start, the following are pre-requisites: 
1.	The firewalls on the systems are turned off. 
2.	All the clients are on the same subnet. 
3.	Make sure you use the same version of JMeter on all the systems.
Assuming you already have JMeter installed on all the systems (Master and Slaves). The way JMeter works is 1 master controller initiates the test on multiple slave systems.
Terminology :
Master – the system running Jmeter GUI, which controls the test. 
Slave – the system running jmeter-server, which takes commands from the GUI and send requests to the target system(s) 
Target – the webserver we plan to stress test
 
Steps:
1.	On the slave systems, go to jmeter/bin directory and execute jmeter-server.bat (jmeter-server on unix). On windows, you should see a dos window appear with “jre\[version]\bin\rmiregistry.exe”. 
2.	On master system acting as the console, open windows explorer and go to jmeter/bin directory 
3.	Open jmeter.properties in a text editor 
4.	edit the line remote_hosts=192.168.0.10,192.168.0.11,192.168.0.12,192.168.0.13,192.168.0.14 
5.	Start jmeter.
6.	Open the test plan you want to use
Start a single clients:
1.	click Run at the top
2.	select Remote start
3.	select the IP address
Start all clients:
1.	click Run at the top 
2.	select Remote start all or use CRTL-Z
