
# Docker AEM (Windows)
This project holds all our 6.2 AEM docker images we have built so far.  At this time we have only completed and tested the standard tar MK based images.  We will be working to include more as time goes on.

The easiest way to get start would be to clone this repo, start  Docker Quickstart Terminal, then CD to the compose2 folder and execute docker-compose up

## Install additional packages

The system also allows for the ability to install additional packages such as hotfixes, featurepacks etc. Currently this is done per AEM image (author and publish). Each of the author-tar and publish-tar directories contain a packagelist.txt file and packages directory under the resources directory. The packagelist.txt file should contain a list of packages to be installed with each line of the file representing one package. This way we can guarantee the order of installation of the packages which in some cases in AEM is important. Ensure the file is stored in Unix Ascii format

The /resources/packages directory is where the actual packages are expected to be placed and this is where the installation script will look for them. Currently only packages (.zip files) are supported.

The /resources/osgi directory is where the osgi configurations are expected to be placed and this is where the installation script will look for them. 

How are the AEM instances configured?  Each of the AEM images (author, publish) are configured via quickstart properties.  The quickstart file that is responsible for the configuration can be found under each images resources subdirectory.

This has only been tested on a Windows. Also, I have left the bash shell scripts as is, they will still continue to work from the docker terminal
