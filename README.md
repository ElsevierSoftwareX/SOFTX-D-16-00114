# SOFTX-D-16-00114
Un-Code: Understanding Collective Decision-Making
Version: 1.0
12.08.2016
Created by: Julian Stieg, Peter Marks, Lasse Gerrits
Released Open Source under GPL, see gpl.txt

Online Availability
Un-Code is 24/7 online available at http://www.un-code.org
The website is hosted by the University of Bamberg. Please feel free to use the website for science and experimentation. However you are also free to do a local installation on your machine.

Local Installation
1.	Install a local web server containing Apache, PHP, MySQL, PHPMyAdmin, for example XAMPP (https://www.apachefriends.org).
2.	Put the contents of the .zip file into the server’s “htdocs” folder. (If you are within a Linux system, please make sure, the subfolders “tmp”, “template_c” and “cache” are writeable.)
3.	Start the web server (in XAMPP: Apache + MySQL).
4.	Within the browser, go to the PHPMyAdmin service (in XAMPP: localhost/phpmyadmin/).
5.	Create two databases. One for project data (e.g. “uncode-project”) and one for user data (e.g. “uncode-user”).
6.	Click on the left side on your newly created “uncode-project” database. On the top go to “import”. Select the file “uncode-project.sql” in the same folder as this documentation and accept. This creates the fundamental database structure.
7.	Do the same step as (6) with the “uncode-user” database and import “uncode-user.sql”.
Congratulations, you just completed the installation! Now you can start using Un-Code via your browser. If you use XAMPP and followed the above steps, just go to: “localhost/uncode” via your browser’s address field.

Database configuration (optional)
If you have trouble accessing the MySQL database, you might have to adjust the access values in /include/db.php. This is also the case if you named the databases differently than the above suggested names. However, when following the installation procedure above, in most cases the standard values should suffice.

Usage tutorial
Please see here for a short tutorial on how to get started using the application.

Code structure
Our software uses the Smarty template system for separating back-end php code and front-end html/script code.
•	Back-end PHP code is to be found in the index.php main file.
o	Beginning at line 164, site requests are caught and redirected to the appropriate functions. It is separated between being logged in (PHP session) and being logged out (login screen). If a function is a front-end function (e.g. visualize() at line 2339) it loads the appropriate template via Smarty. Some functions are also just transmitting data for AJAX operations (e.g. when working with the main editing screen or the 3D visualization), e.g. visualizeData() at line 2385 which is the back-end process for sending data to WebGL.
o	To have a look at the C-Score calculation process, see line 708-771.
•	Front-end templates using HTML, JavaScript and JQuery can be found in the /templates folder. WebGL and Three.JS visualization is also done front-end (with data from the back-end).
o	Main editing screen template can be found in project.tpl
o	Front-end for 3D Visualization can be found in visualize.tpl
o	An example for Smarty front-end programming is connections.tpl
•	Graphics can be found in the /img folder.
o	Textures used in 3D Visualization are found in /img/greyscale and /img/color
•	CSS layout code can be found in the /css folder.
•	The /include folder consists of several requirement and configuration files.
o	Database configuration under /include/db.php
o	Common Javascript functions under /include/common.js
o	3rd party Dependencies
	Smarty template system: /smarty, /templates, /templates_c, config, cache
	JQuery: /include/jquery.js, jquery.hotkeys.js
	Three.JS: /include/three.min.js, OrbitControls.js, Detector.js
	Three.JS Terrain generator (used for slope visualization), created by Isaac Sukin and released Open Source under MIT-license: THREE.Terrain.min.js
	PHPExcel under /excel


Further Questions
In case of any questions, advises or discussions please contact me at jstieg@gmx.de
I can also do skype sessions in case of detailed questions.


Thank you for using Un-Code!
