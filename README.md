Azure Functions with Maven and Java
===================================

Creation of a new project
-------------------------
Prerequisites:
* Java
* Maven
* Azure Functions Core
  https://github.com/Azure/azure-functions-core-tools#installing

Steps as documented at https://github.com/microsoft/azure-maven-plugins/blob/develop/azure-functions-maven-plugin/README.md#how-to
1. Create Maven Project
   `mvn archetype:generate -DarchetypeGroupId=com.microsoft.azure -DarchetypeArtifactId=azure-functions-archetype`
   `cd <artifactId>`
2. Add new fuction to project (Optional, a default function will be created with the archetype)
   `mvn azure-functions:add`
3. Build project (Needs to run every time code is changed)
   `mvn clean package`
4. Run Azure Functions locally
   `mvn azure-functions:run`
