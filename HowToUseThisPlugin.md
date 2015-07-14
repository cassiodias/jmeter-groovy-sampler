# Introduction #

This plugin serves as a means to use Groovy Scripts to perform any task of your choosing while under inspection, load, threading, and looping by the excellent performance tool, Apache JMeter.


# Details #

Follow these steps to use this plugin:
  * Download JMeter **2.4.3** and _Maven 2.0.9_
  * Set up an environment variable JMETER\_HOME
  * Put this plugin JAR in your JMETER\_HOME/lib/ext directory
  * Start up JMeter
  * Notice the new Add Sampler menu item for Groovy Script Sampler

# Classpath #
All three scripts (Utility, Setup, and Test) are loaded to the same Groovy classloader.  This way your actual test can use items from the utility or setup classes in the main "timed" execution.

# Strategies #
One approach to setting up data elements that you don't want timed, but passing them over to the main setup script can be found in the sample scripts SVN directory ((directory path here)).  This approach uses static variables to accomplish the data handoff, which works since all three scripts are loaded via the same classloader instance.