
# How to Run and Deploy the Picture Finder App #

## Overview of the app ##

Use the IBM Bluemix Location services and Instagram to find pictures near an address.  It's written in Node.js and uses the following Bluemix services:

- Pitney Bowes Geocoding service

### Deploying the App and Binding the Geocoding Service ###
Multiple methods exist for interacting with the BlueMix platform. Outlined below are two of those methods.

## Method: Command-Line ##

Before we begin, we first need to install the [**cf**](https://github.com/cloudfoundry/cli/releases) command line tool that will be used to upload and manage your application. If you've previously installed an older version of the cf tool, make sure you are now using v6 of cf by passing it the -v flag:

    cf -v

Clone the Node picture finder application from the IBM jStart DevOps repository.

git clone https://hub.jazz.net/git/jstart/Picture.Finder.(Node)

Go to the directory of your app and follow these steps:

Login to Bluemix.

   | *usage:*   | `$ cf login [-a API_URL]`                    |
   |:-----------|:---------------------------------------------|
   | *example:* | `$ cf login -a https://api.ng.bluemix.net`   |

**From the directory that houses the _app.js_ file** (not from the root directory that contains this *README.md* file), locate the manifest file. 
A manifest.yml file is included with the application to streamline the deployment process. It sets the application name, memory, and the number of instances.
Edit manifest.yml to change the values that must be unique for your app - the host name and the name of the already-created Geocoding servic. The host name must be something other than picturefinder so that your resulting URL route doesn't conflict with the demo URL (http://picturefinder.ng.bluemix.net).

Also located in the **app** directory, edit app.js and replace the Instagram ID and secret with your ID and secret.

Push the the application.  You do not need to supply any parameters on the push as they are supplied through the manifest.yml file.

   | *usage:*   | `$ cf push APPNAME [--no-manifest] [-c COMMAND]`                        |
   |:-----------|:--------------------------------------------------------------------|
   | *example:* | `$ cf push `            |
   
  
## Method:  IBM DevOps Services ##
1. Browse to the  DevOps Services project repository located [here](https://hub.jazz.net/project/jstart/Picture%20Finder%20%28Node%29/overview).  Click on **Edit Code** for the project.
2. Click on "Fork".  This will provide you with a personal copy of the code within your DevOps Services project space.
3. Located in the **app** directory of the project, edit manifest.yml and change the host name to something unique and the service name
to the name of your already-created Geocoding service.
4. Also located in the **app** directory, edit app.js and replace the Instagram ID and secret with your ID and secret.
5. Next, click on "Deploy".  This will use information within the **manifest.yml** to deploy the sample application directly into the codename: BlueMix platform.


  You may continue to deploy changes to your BlueMix application directly from DevOps Services using the "Deploy" and "Deploy As" buttons.

5. Next, click on the Root Project Name and scroll to the **Manual Deployment Information** section.


  You can check the status of the app using this section. If a green filled circle is visible, you may click the Application Name shown within the section and interact with the running application.  However, if a red filled circle is displayed, you may click **Manage** and directly interact with the BlueMix User interface for further investigation and debugging.


## License ##
Licensed under the Apache License, Version 2.0 (the "License"); you may not use this file except in compliance with the License. You may obtain a copy of the License at

     http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software distributed under the License is distributed on an "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied. See the License for the specific language governing permissions and limitations under the License.