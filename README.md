Viper SmartStart Control
==========

About
-----
Viper SmartStart Control is a php script that connects to the Viper SmartStart servers and sends commands to your registered vehicle.


Demo Videos
-----------

See the script being called by a ruby plugin for "[Siri Proxy](https://github.com/plamoni/SiriProxy)" here: [http://www.youtube.com/watch?v=tAQMXbrDgbM](http://www.youtube.com/watch?v=tAQMXbrDgbM) and [http://www.youtube.com/watch?v=SO6RNO8t06c](http://www.youtube.com/watch?v=SO6RNO8t06c) 

Read more about the "[Siri Proxy](https://github.com/plamoni/SiriProxy)" plugin here: [http://fiquett.com/?p=791](http://fiquett.com/?p=791)



Set-up Instructions
-------------------

If you are going to run via command line or through a http GET and do not want to pass in credentials, add your Viper SmartStart credentials on lines 9-10: (keep the single quotes around both) 

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
	    [5] => AUX2
	    [6] => AUX3
	    [7] => direct_io_lock_400
	    [8] => direct_io_lock_750
	    [9] => direct_io_lock_3500
	    [10] => direct_io_unlock_400
	    [11] => direct_io_unlock_750
	    [12] => direct_io_unlock_3500
	    [13] => direct_io_remote_750
	    [14] => direct_io_trunk_750_with_unlock
	    [15] => direct_io_trunk_750
	    [16] => direct_io_lock_400_2pulse
	    [17] => direct_io_lock_750_2pulse
	    [18] => direct_io_lock_3500_2pulse
	    [19] => direct_io_unlock_400_2pulse
	    [20] => direct_io_unlock_750_2pulse
	    [21] => direct_io_unlock_3500_2pulse
	    [22] => FN_START_REM_STATUS
	    [23] => FN_STOP_REM_STATUS
	    [24] => REMOTE
	    [25] => REQ_VIN_1
	    [26] => REQ_VIN_2
	    [27] => REQ_EXTENDED_STATUS
	    [28] => REQ_VIN_3
	    [29] => REQ_DTC_CODE
	    [30] => REQ_CLR_DTC
	    [31] => DISARM
	    [32] => FN_UNLOCK_ALL_REM2_ON_STATUS
	    [33] => FN_UNLOCK_ALL_REM3_ON_STATUS
	    [34] => ARM
	    [35] => FN_LOCK_REM2_ON_STATUS
	    [36] => FN_LOCK_REM3_ON_STATUS
	    [37] => PANIC
	    [38] => FN_PANIC_REM2_ON_STATUS
	    [39] => FN_PANIC_REM3_ON_STATUS
	    [40] => FN_PANIC_REM1_OFF_STATUS
	    [41] => FN_PANIC_REM2_OFF_STATUS
	    [42] => FN_PANIC_REM3_OFF_STATUS
	    [43] => TRUNK
	    [44] => FN_TRUNK_REM2_ON_STATUS
	    [45] => FN_TRUNK_REM2_ON_STATUS
	    [46] => AUX2
	    [47] => FN_AUX1_REM2_ON
	    [48] => FN_AUX1_REM3_ON
	    [49] => AUX3
	    [50] => FN_AUX2_REM2_ON
	    [51] => FN_AUX2_REM3_ON
	    [52] => AL_ALERT_CLEAR
	    [53] => FN_EXTEND_RUNTIME
	    [54] => REQ_VIN_4
	    [55] => REQ_VIN_5
	    [56] => REQ_VIN_6
	    [57] => REQ_DTC
	    [58] => AL_QUERY
	    [59] => REQ_MODULE_INFO_1
	    [60] => REQ_MODULE_INFO_2
	    [61] => REQ_MODULE_INFO_3
	    [62] => REQ_MODULE_INFO_4
	    [63] => REQ_PROTOCOL_VER
	    [64] => REQ_RUNTIME
	    [65] => REQ_FUEL_LEVEL
	    [66] => REQ_ODO
	    [67] => REQ_BAT_VOLT
	    [68] => REQ_TPMS
	    [69] => REQ_RPM
	    [70] => REQ_SPEED
	    [71] => REQ_ENG_TEMP
	    [72] => REQ_INT_TEMP
	    [73] => REQ_EXTENDED_STATUS_SUPPORT
	    [74] => AUX3
	    [75] => READ_CURRENT
	    [76] => READ_ACTIVE
	    [77] => READ_CURRENT
	    [78] => READ_ACTIVE
	    [79] => AUX2
	    [80] => FN_START_STOP_REM
	    [81] => REMOTE_NOSTATUS
	    [82] => ARM_NOSTATUS
	    [83] => DISARM_NOSTATUS
	    [84] => TRUNK_NOSTATUS
	    [85] => PANIC_NOSTATUS
	    [86] => FN_UNLOCK_ALL_REM2_ON_NOSTATUS
	    [87] => FN_UNLOCK_ALL_REM3_ON_NOSTATUS
	    [88] => FN_LOCK_REM2_ON_NOSTATUS
	    [89] => FN_LOCK_REM3_ON_NOSTATUS
	    [90] => FN_TRUNK_REM2_ON_NOSTATUS
	    [91] => FN_TRUNK_REM3_ON_NOSTATUS
	    [92] => FN_PANIC_REM2_ON_NOSTATUS
	    [93] => FN_PANIC_REM3_ON_NOSTATUS
	    [94] => FN_PANIC_REM2_OFF_NOSTATUS
	    [95] => FN_PANIC_REM3_OFF_NOSTATUS
	    [96] => FN_PANIC_REM1_OFF_NOSTATUS
	    [97] => DISARM_STATUS
	    [98] => ARM_STATUS
	    [99] => PANIC_STATUS
	    [100] => TRUNK_STATUS
	    [101] => REMOTE_STATUS
	    [102] => force_id_report
	    [103] => cancel_retries
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
