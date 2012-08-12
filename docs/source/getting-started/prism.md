# Using Adhearsion with PRISM

## Requirements
* [Voxeo PRISM version 11.0 or later (11.5 recommended)](http://voxeolabs.com/prism)
* [rayo-server application](http://ci.voxeolabs.net/jenkins/job/Rayo/lastSuccessfulBuild/artifact/rayo-war/target/)

After downloading the Rayo WAR file it will have the build number in the file name (eg. rayo.b189.war).  Rename this file to simply "rayo.war".

While PRISM itself is a commercial product, a free license with 2-port concurrency is available to developers.  Also, the "rayo-server" application is open source and can be found on its [Github repository](https://github.com/rayo/rayo-server).

Rayo is officially supported on RedHat Enterprise Linux, CentOS and Mac OSX.  Users have also reported getting it to work successfully on Debian and Ubuntu, though this may not be supported by Voxeo.

## Getting PRISM

PRISM can be downloaded for free from 

## Configuring PRISM


1. Set PRISM_HOME to the base directory where you installed PRISM.  This is optional, but recommended to make the following instructions copy/pasteable.  For example "export PRISM_HOME=/opt/voxeo/prism"
2. If PRISM is running, shut it down. This can be done by using the application launcher in OSX or by running "/etc/init.d/voxeo-as stop" on Linux.
3. Rename your Rayo WAR file to simply "rayo.war" and copy it to the PRISM apps directory. By default this is $PRISM_HOME/apps
4. Start PRISM to allow it to unpack and launch the Rayo application.  After starting PRISM wait around 2 minutes for the application to be detected and unpacked.
5. Shut PRISM down again to begin configuration.
6. Edit the file $PRISM_HOME/config/portappmapping.properties to map port 5060 to Rayo:
5060:rayo

Important! Ensure that only one line in this file begins with "5060".


### Licensing PRISM

If you are using a Rayo server, you will need to configure your JID and password and ensure that the DIDs have been mapped to your selected JID. Refer to your Rayo server's documentation for how to do this.  You likely will also want to configure your root_domain to point to your Rayo server's domain name for routing outbound calls.

## Getting Help
