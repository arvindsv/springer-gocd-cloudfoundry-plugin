# springer-gocd-cloudfoundry-plugin
Go plugin for detecting application version whenever the application is 
deployed into Cloud Foundry.

Status: Awarded first prize for ThoughtWorks Go Plugin Challenge, 
March 2015

## Potential use cases
* Execution of tests that don't need to block a deploy.
* Deploy of an application that needs to match the version of the other 
application - e.g. an application providing preview functionality for 
CMS managed content.
* Performance testing - keep a record of the app over time without 
having to hook these tests into the application's build pipeline.

## Requirements
Versions 1.0.0 - 1.0.2: Java 6 or higher.

Version 2.0.0: Java 8.

## Building
./gradlew clean build

## Installing
After building, copy the generated jar file from 
build/libs/springer-gocd-cloudfoundry-plugin-2.0.1.jar to your Go 
server's external plugins directory.

Restart Go server to allow it to detect and install the new plugin.

Verify that the plugin has successfully been installed by navigating to
the Admin / Plugins section on your Go server.

## Usage
There are two stages involved in making use of this Material:
  * Admin / Package Repositories
     Add Package Repository - select Cloud Foundry as the type and
     provide the credentials for accessing your Cloud Foundry
  * During pipeline creation, specify Package as Material type and
  select the repository that you created in the previous step
     Select Define New and provide the details of your app.

## GoCD version support
According to the release notes for version 16.10.0 of GoCD, the API 
used by this plugin has been deprecated and will cease to be usable 
from version 17.1 - expected around January 2017.

## About the name
springer = I worked for Springer Science+Business Media during the
development of this plugin and started development during a hack day
there.

gocd = The plugin runs inside the ThoughtWorks GoCD Continuous Delivery
server.

cloudfoundry = The platform that the plugin polls to detect updates to
a deployed application.

plugin = A self-contained module which runs inside an application.

## Version History
**2.0.0**

8 March 2015

Java 8 required.  This should make the plugin more appealing to
developers who may want to fork it and customise.

Minor inconvenience - if your Go Server installation is using an older
JVM then it should fail to load the plugin (but, let's face it, you
want to upgrade).

**1.0.2**

23 February 2015

Revision number parsing updated to support positive real numbers.

**1.0.1**

22 February 2015

Password property 'secure'.

**1.0.0**

18 February 2015

Original release.

