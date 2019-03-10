#####OVERVIEW

Providing Authenticated access to thingQbator and monitor access. Right now there is no access mechanism exist for thingQbator which leads to unauthorized access and monitoring access becomes difficult.

This repo contains code for both Hardware and Web backend. The entire project is structured like this using Design Thinking tool. Click here for downloading.

#####TASKS

How to open the door only by authenticated user.
How to verify authenticity of a user.
How to log access data.
How to alert the admin if an unauthorized user tries to access thingQbator.
How to add a new user.
How to add admin user.
How to view daily usage.
How to view access log of a single user.

#####DETAILED SOLUTION DESCRIPTION

There are two parts in this system.
Hardware 
Web Backend

**Hardware**

The hardware is composed of authentication mechanism and controller and communication part. In the college, every students have RFID identity cards. So, we are using RFID reader for authentication. For controlling and communication part we are using esp8266. There will be an power module too to power the entire hardware system.  

Also, there is a magnetic lock which is attached to the door which will open and close based on the authentication done in RFID reader.

**Web Backend**

Web backend stores the access logs and provides a mechanism to monitor the data. For the time being, we are using Firebase for backend technology. It can store data and host the web files.


**Hardware Side Working**

When an authenticated used swipes his/her card on RFID reader, the magnetic lock opens, user can enter thingQbator. The system logs the user details, date and time data to cloud.

When the Add user button is pressed, it waits for detecting Admin RFID card. When admin RFID card detected, reader waits for detecting new user card two times. Once adding completed, system goes to normal reading mode.

On system booting, it will connect to the predefined wifi network and fetch authorization and admin list.

The buzzer and led will notify the status of operation of device on different situations.
