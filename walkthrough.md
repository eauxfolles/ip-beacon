IP Beacon
=========

v1 @ 17.06.2020

Goal
====

If user opens a prepared file (HTML), the IP address of the device in use should be automatically made available to a target system.  

Implementation
==============

**Assumption:** Web server will be started on own workstation. 

1. Create a persistent URL via DynDNS-Provider and direct URL to own, external IP.  
2. Create **tracking pixel** and store it in folder on local workstation (e.g. bacon.png).
3. Create HTML-File and include img-tag (e.g. test.html). 
4. Link source attribute of img-tag to tracking pixel via DynDNS-URL (e.g. "http://< DynDNS-URL >:< port >/bacon.png").  
6. Start web server in folder containing the tracking pixel with port included in HTML-file (via Python's moduel **"http.server"**).
8. Access HTML-file from device of choice which is connected to the internet. 
7. Gather connection data once target is downloading tracking pixel through the HTML-file. 

Local workstation can be replaced by other system (e.g. Raspberry Pi) or web server. 

Components
==========

* DynDNS-Provider, e.g. https://ydns.io
* Tracking Pixel, e.g. **bacon.png**
* HTML-File, e.g. **test.html**
* Python-Code: 
> python -m http.server < port >

Source used: https://en.wikipedia.org/wiki/Web_beacon
