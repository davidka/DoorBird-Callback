#DoorBird Callback Servlet for openHAB Integration#

This is a simple implementation to provide web ressources to register with a [DoorBird](http://www.doorbird.com/).
In openHAB 2 `Switch` items have to be created name `DoorBird_MotionSensor` and `DoorBird_DoorBell` to receive notifications for both motion sensor as well as door bell events registered with DoorBird.
(see http://doorbird.com/api for more details.)

The implementation uses openHAB's rest service to post an `ON` command to the above mentioned items.

To configure the URL of openHAB simply edit the `WEB-INF/web.xml` file and set the following context parameters accordingly:

	<context-param>
		<param-name>user</param-name>
		<param-value></param-value>
	</context-param>
	<context-param>
		<param-name>password</param-name>
		<param-value></param-value>
	</context-param>
	<context-param>
		<param-name>ipAddress</param-name>
		<param-value></param-value>
	</context-param>
	<context-param>
		<param-name>port</param-name>
		<param-value></param-value>
	</context-param>

To deploy simply copy the WAR file (in folder `target`) into openHAB's `webapps` folder.

The URLs for the callback ressources are then
* http://`openhab-ip`:`openhab-port`/doorbird-callback-1.0/motion-sensor
* http://`openhab-ip`:`openhab-port`/doorbird-callback-1.0/door-bell
