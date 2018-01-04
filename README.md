ChemDrawJS 17.1 Installation Guide
==================================

Overview
--------

ChemDrawJS consists of a JavaScript library and a backend ChemDraw Web Service.
This guide provides instructions for two different deployment strategies for
users to install ChemDrawJS in users’ environment. It depends on how ChemDrawJS
is used in the host web pages to decide which deployment strategy to use.

Installing ChemDrawJS JavaScript Library Only
---------------------------------------------

### Introduction

If the host application only uses the basic drawing tool of the ChemDrawJS, only
the JavaScript library needs to be deployed within the host application.

![InstallLibraryOnly](media/57ba3d02d6228c79fc35f7011b446fe4.png)

InstallLibraryOnly

### Prerequisites

The following files are needed to perform installation.

-   ChemDrawJS-Library-17.1.zip

-   ChemDrawJS-License.xml

### Deployment

| Step | User Input               | Expected Result |
|------|--------------------------|-----------------|
| 1    | Unzip ChemDrawJS         | fda             |
| Step | User Input / User Action | Expected Result |

1\|Unzip ChemDrawJS-Library-17.1.zip\|Three sub-folders can be seen.

chemdrawweb

docs

sample

2\|Copy the three sub-folders to the folder which the host application loads
scripts.\|The two folders are acceable with the URLs below

https://your-server-url/...scriptsurl.../chemdrawweb/

https://your-server-url/...scriptsurl.../sample/

3\|Open the browser and navigate to the sample page.  
e.g. https://your-server-url/...scriptsurl.../sample/index.html

![](media/a5109fdfa5be0e9e22b76bfb7b1d9e4b.png)

\| The sample page shows with the license dialog.

Installing ChemDrawJS Service
-----------------------------

### Introduction

A single ChemDrawJS Service can be installed which offers both JavaScript
library and the ChemDraw Web Service.

![ChemDrawDirectService](media/6d9f7609ab58f54ca2bb9d9c07def098.png)

ChemDrawDirectService

### Prerequisites

The following files are needed to perform installation.

-   ChemDrawJS-Setup-17.1.exe

-   ChemDrawJS-License.xml

The following operating systems are supported by the service:

-   Windows Server 2008 or later

The following software is depended by ChemDrawJS Service, and will be installed
by the installer automatically, if it does not exist:

-   Microsoft .NET Framework 4.5 or above

-   Microsoft Visual C++ 2017 Redistributable Package (x86)

-   PerkinElmer ChemDraw ActiveX Enterprise Constant 17.1

### Upgrading from Earlier Versions

Upgrading from earlier versions to ChemDrawJS 17.1 is not supported. The
previous versions need to be uninstalled manually before installing ChemDrawJS
17.1.

### Interactive Installation

| Steps | User Input / User Action                                                                                                                                                                                                                                                                              | Expected Result                                                                                                                                          |
|-------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1     | [images/Install-2.png](images/Install-2.png)                                                                                                                                                                                                                                                          | ChemDrawJS installation begins and the welcome wizard appears after all the dependency software are installed. The License Agreement dialog-box appears. |
|       | Run **ChemDrawJS-17.1.exe** and click **Next**.                                                                                                                                                                                                                                                       |                                                                                                                                                          |
|       | **Note**: This installer wizard lists the prerequisites which are not installed on your machine. You may need to follow the on-screen instructions to complete the installation of the prerequisite items.                                                                                            |                                                                                                                                                          |
| 2     | [images/Install-3.png](images/Install-3.png)                                                                                                                                                                                                                                                          | The Destination Folder dialog-box appears.                                                                                                               |
|       | Read the license agreement, and if you agree with the license agreement, select the **I accept the terms in the license agreement** option, then click **Next**.                                                                                                                                      |                                                                                                                                                          |
| 3     | [images/Install-5.png](images/Install-5.png)                                                                                                                                                                                                                                                          | The Setting ChemDrawJS dialog-box appears.                                                                                                               |
|       | Click **Next** to install ChemDrawJS 17.1 in the default location. Alternatively, you may click Change to change the default destination location and select a new destination folder.                                                                                                                |                                                                                                                                                          |

4\|

![](media/0ebbdd0fa500e6fdcc203bec10a5cad1.png)

![](media/c51e5fd56c5af98bd2afa9f5c4dd6e42.png)

Select the protocol type and configure other respective settings.  
**HTTP:**

Type: Protocol type: http or https. The type has to be set to https if the host
applications are using https.

Host name: Enter the local server machine name or IP address: local machine name
as default. The host name has to be public domain name or the public IP address
that can be accessed by the end users of the host applications.

Port: Port number of the service. The installation will be rollback if the
specified port is not available.

Virtual directory: Virtual path of the service.  
E.g. The virtual path is used in the URL to access ChemDrawJS and Web Service
like ‘http://[MACHINE NAME]:81/chemdrawjs/js/sample/index.html’ or
‘http://[MACHINE NAME]:81/chemdrawjs/rest/help’.

**HTTPS:**

SSL Certificate: SSL certificate: Click **Select** to add a SSL certificate .pfx
file.

SSL password: SSL certificate file password: Enter the password of SSL
certificate.

Click **Next**. \|The Ready to Install dialog-box appears. 5\|

![](media/ebf52183722c563f93e3f7279451f60c.png)

Click **Install**.\|Installation begins and the **Installing ChemDrawJS** dialog
appears. 6\|

![](media/d6437879f9bf08e525b15ee0b0ce620e.png)

The Wizard Completed dialog appears when the installation completes. Click
**Finish** to exit the wizard.\|The installation wizard exits. The installer log
file and ChemDrawJS sample page opens if the options are checked.

### Silent Installation

#### Syntax

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
"ChemDrawJS-17.1.exe" /s /v/"qn SERVER_PORT=[post_number] \
SERVER_TYPE=[server_type] \
SERVER_SSL_PATH=[path_to_pfx_file/your_ssl_pfx_file.pfx] \
SERVER_SSL_PWD=[pfx_file_passware] \
SERVER_HOST_NAME=[MACHINENAME] \
SERVER_VIRPATH=[SERVER_VIRPATH]"
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

#### Example

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
"ChemDrawJS-17.1.exe" /s /v/"qn \
SERVER_PORT=443 SERVER_TYPE=https \
SERVER_SSL_PATH=C:\certificate.pfx \
SERVER_SSL_PWD=****** \
SERVER_HOST_NAME=yourappurl.com \
SERVER_VIRPATH=chemdrawjs"
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

#### Parameters

-   SERVER_PORT: The exposed port of the ChemDrawJS Service.

-   SERVER_TYPE: http or https

-   SERVER_SSL_PATH: The path to the SSL certificate file

-   SERVER_SSL_PWD: The password of the SSL certificate

-   SERVER_HOST_NAME: The public domain name or host name or IP address which
    can be accessed by the end users of the host applications. This name will be
    saved into the configuration of ChemDrawJS, so that the ChemDrawJS
    javascript library can find the backend service.

-   SERVER_VIRPATH: Virtual path of the service. This path can be empty. If
    using silent installation with empty virtual path, set the param as
    *SERVER_VIRPATH=""*

**Note**: Administrator permission is required to perform silent installation.

### Starting and Stopping ChemDrawJS Services

After installation, the following two windows services are created. And both
services are configured to be started automatically at windows startup.

-   PerkinElmer ChemDrawJS Service 17.1

-   PerkinElmer ChemDrawJS Service 17.1 Monitor

To stop the services, the **PerkinElmer ChemDrawJS Service 17.1 Monitor** has to
be stopped first. Because the monitor service keeps monitoring the running state
of **PerkinElmer ChemDrawJS Service 17.1** and restart the service when it is
not running.

Preparing ChemDrawJS License
----------------------------

ChemDrawJS requires a license. A license can be loaded into ChemDrawJS by either
a URL to a valid license file which can be accessed by ChemDrawJS library or the
license content in plain text format.

### Exposing ChemDrawJS License with a URL

To enable ChemDrawJS load a license file from a URL, the ChemDrawJS-License.xml
file need to be put with in a HTTP server with the following capabilities:

-   Cross-Origin Resource Sharing (CORS)

-   GET static .xml files

If the host application runs in an HTTPs server, the ChemDrawJS license file
also has to be placed in an HTTPs server.

**Note**: A license file provided by PerkinElmer may have a name other than
ChemDrawJS-License.xml. Also feel free to rename the file. Just make sure the
URL can be accessed by your host application which uses ChemDrawJS library.

The URL to the license file will be used in trying the sample page. It will also
needed when writing the code of your host application which creates and attaches
ChemDrawJS instances. Please refer to **ChemDrawJS 17.1 Developers Guide** for
details.

### Using ChemDrawJS License in Plain Text

ChemDrawJS also accepts a ChemDrawJS license in plain text. It means the host
application can implement its own mechanism to load the license content into
ChemDrawJS when attaching.

Verifying ChemDrawJS Deployment
-------------------------------

The sample page of ChemDrawJS can be used to verify the deployment.

If ChemDrawJS is deployed using the installer, the sample page can be opened
directly if the **Show ChemDrawJS Sample Page** option is checked at the last
step of the installation wizard.

Or a menu item is available in Windows Startup menu to open **ChemDrawJS Sample
Page 17.1**

![](media/a9a4e013bdcd193ca2b0583d03724f6b.png)

### Loading ChemDrawJS License on the Sample Page

The sample page also needs a valid ChemDrawJS license. A dialog will be shown on
the sample page.

![](media/acda5d7f0b77226359f7af840f7a098f.png)

Please input the URL to the license file or copy and paste the license content
into the text box.

If the license is valid, it will be cached in browsers' storage. So that next
time when opening the same sample page with the same URL in the same browser,
the sample page will not ask for a license again.

**Note**: Loading a license on the sample page does not actually install a
license into ChemDrawJS service. It only allows sample page to run. And it means
the host application should still write code to load the license into ChemDrawJS
when attaching. Please refer to **ChemDrawJS 17.1 Developers Guide** for
details.

After the license is loaded, the sample page should show the ChemDraw toolbar.

![](media/4229fe70297c09d1c2709266b16decbc.png)

### Testing ChemDrawJS Service

The tool **Name to Structure** can be used to test installation.

1.  Click **Name to Structure** tool button in the tool bar

![Name to Structure tool button](media/5060c8cc5fcdd52d04c1c711a02ee809.png)

    Name to Structure tool button

1.  Type "water" and click **OK**

![water](media/26535df90dc053e2bc22c2c68b22b149.png)

    water

1.  ChemDrawJS Service works as expected if H-O-H shows on the canvas

![done](media/4011eee1076bce891a97f0f84daf257e.png)

    done

Loading ChemDrawJS Library
--------------------------

To load the library, the web page should load the script **chemdrawweb.js**.
This script will load all the other required resources.

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
<script src="[SERVER_TYPE]://[SERVER_HOST_NAME]:[SERVER_PORT]/[SERVER_VIRPATH]/js/chemdrawweb/chemdrawweb.js"></script>
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

### Example

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
<script src="http://mychemdrawjsserver:8080/chemdrawjs/js/chemdrawweb/chemdrawweb.js"></script>
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
