lightum - MacBook automatic light sensor daemon
(c)2011-2012 Pau Oliva Fora - pof[at]eslack(.)org

lightum is a daemon to control the keyboard brightness and monitor backlight on
MacBook based laptops.

By default it will run in "auto" mode, this means it will read data from the
ambient light sensor (located on the iSight camera) and automatically:

	a) light up or dim the keyboard brightness 
	b) light up or dim the the video backlight 

It will also dim the keyboard brightness and screen backlight when the computer
is not used for a configurable amount of seconds (5 by default).

If you choose to run it in "manual" mode, it will not query the ambient light
sensor, but instead it will use the brightness and backlight values you set
manually using the function keys.

When first launched lightum will create a configuration file in the folder
~/.config/lightum/lightum.conf, inside the user's home directory with the
default configuration values. When launched without parameters, lightum will
read the configuration from this config file, but the configuration values can
be overwritten via the command line:

Usage:  lightum [OPTION]...
     -m 4..255 : maximum brightness value in auto mode (default=255)
     -n 0..3   : minimum brightness value in auto mode (default=0)
     -M 4..15  : maximum backlight value in auto mode (default=15)
     -N 1..3   : minimum backlight value in auto mode (default=1)
     -p num    : number of milliseconds between light sensor polls (default=300)
     -i num    : power off keyboard light on session idle seconds (0 to disable)
     -I num    : power off screen backlight on session idle seconds (0 to disable)
     -w num    : 1 manage brightness, 2 manage backlight, 3 both (default:3)
     -x        : manual mode (will honor the brightness value set with Fn keys)
     -u        : do not ignore brightness changes happening outside lightum
     -s        : power off keyboard light when screen saver is active
     -f        : run in foreground (do not daemonize)
     -v        : verbose mode, useful for debugging with -f and -d
     -d num    : debug mode: 1 brightness, 2 backlight, 3 both


Official Ubuntu packages are available in poliva/lightum-mba ppa:

     sudo add-apt-repository ppa:poliva/lightum-mba
     sudo apt-get update
     sudo apt-get install lightum

Enjoy! :)
