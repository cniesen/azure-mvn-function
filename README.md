Azure Functions with Maven and Java
===================================

Creation of a new project
-------------------------
Prerequisites:
* Java

* Maven

* Azure CLI
  https://docs.microsoft.com/en-us/cli/azure/install-azure-cli?view=azure-cli-latest
  
* Azure Functions Core
  https://github.com/Azure/azure-functions-core-tools#installing

Steps as documented at https://github.com/microsoft/azure-maven-plugins/blob/develop/azure-functions-maven-plugin/README.md#how-to
1. Create Maven Project
   `mvn archetype:generate -DarchetypeGroupId=com.microsoft.azure -DarchetypeArtifactId=azure-functions-archetype`
   `cd <artifactId>`
   
   Following Properties are to be entered:
   
   * groupId: Best practice is to use the package name (e.g. `com.example`)
   
   * artifactId: (e.g. `SampleFunctions`)
   
   * version: (e.g. `1.0`)
   
   * package: Java package name (e.g. `com.example`)
      
   * appName: Azure app server name that hosts the functions.  Also in url. (i.e. `azure-mvn-functions`)
   
   * appRegion: Azure region in function app server should be hosted (i.e. `centralus`)
   
   * resourceGroup: Azure resource group (i.e. `sample-functions-group`)
   
   These properties can also be specified on the command line (i.e. `-Dversion=1.0`)
   
2. Add new function to project (Optional, a default function will be created with the archetype)
   `mvn azure-functions:add`

Running Functions
-----------------
1. Build project (Needs to run every time code is changed)
   `mvn clean package`

2. Run Azure Functions locally
   `mvn azure-functions:run`
   
Deploying Functions
-------------------
1. Build project (Needs to run every time code is changed)
   `mvn clean package`

2. Deploy Functions to Azure
   `mvn azure-functions:deploy`