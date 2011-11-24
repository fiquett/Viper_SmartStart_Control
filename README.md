Viper SmartStart Control
==========

About
-----
Viper SmartStart Control is a php script that connects to the Viper SmartStart servers and sends commands to your registered vehicle.


Demo Videos
-----------

See the script being called by a ruby plugin for "Siri Proxy" here: [http://www.youtube.com/watch?v=tAQMXbrDgbM](http://www.youtube.com/watch?v=tAQMXbrDgbM) and [http://www.youtube.com/watch?v=SO6RNO8t06c](http://www.youtube.com/watch?v=SO6RNO8t06c) 


Set-up Instructions
-------------------

If you are going to run via command line or through a http GET and do not want to pass in credentials, add your Viper SmartStart credentials on lines 9-10:

	$smartstart_username = 'VIPER_EMAIL_ADDRESS';
	$smartstart_password = 'VIPER_PASSWORD';

Copy the file viper_control.php to your web server.

Run from CLI:
	
	$ php path_to_web_dir\viper_control.php
	Running from CLI
	Requesting Session ID...
	Session ID: ******censored******* 
	Getting Vechicle List...
	1 vehicle(s) available. 
	Array
	(
		[0] => remote
		[1] => arm
		[2] => disarm
		[3] => trunk
		[4] => panic
		[5] => enable_alarm_alert
		[6] => AUX2
		[7] => AUX3
		[8] => direct_io_lock_400
		[9] => direct_io_lock_750
		[10] => direct_io_lock_3500
		[11] => direct_io_unlock_400
		[12] => direct_io_unlock_750
		[13] => direct_io_unlock_3500
		[14] => direct_io_remote_750
		[15] => direct_io_trunk_750_with_unlock
		[16] => direct_io_trunk_750
		[17] => direct_io_lock_400_2pulse
		[18] => direct_io_lock_750_2pulse
		[19] => direct_io_lock_3500_2pulse
		[20] => direct_io_unlock_400_2pulse
		[21] => direct_io_unlock_750_2pulse
		[22] => direct_io_unlock_3500_2pulse
	)
	Enter Command: arm
	Command received successfully.

Run from browser or HTTP application:

	To Arm:
		http://www.yourserver.com/viper_control.php?action=arm 
	To Disarm:
		http://www.yourserver.com/viper_control.php?action=disarm 
	To Remote Start/Stop:
		http://www.yourserver.com/viper_control.php?action=remote 
	To Pop Trunk:
		http://www.yourserver.com/viper_control.php?action=trunk 
	To Panic:
		http://www.yourserver.com/viper_control.php?action=panic 

Licensing
---------

Re-use of my code is fine under a Creative Commons 3.0 [Non-commercial, Attribution, Share-Alike](http://creativecommons.org/licenses/by-nc-sa/3.0/) license. In short, this means that you can use my code, modify it, do anything you want. Just don't sell it and make sure to give me a shout-out. Also, you must license your derivatives under a compatible license (sorry, no closed-source derivatives). If you would like to purchase a more permissive license (for a closed-source and/or commercial license), please contact me directly. See the Creative Commons site for more information.


Disclaimer
----------
I'm not affiliated with Viper in any way. They don't endorse this application. They own all the rights to Viper SmartStart (and all associated trademarks). 

This software is provided as-is with no warranty whatsoever. 

Viper could do things to block this kind of behavior if they want, hopefully they do not. Also, if you cause problems (by sending lots of trash to the Viper servers or anything), your on your own.
