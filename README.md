# Azure client archetype

`azure-client-archetype` is a Maven archetype to generate an Azure track 2 client library template

# Run the archetype

To run the archetype, execute the following maven command in an **empty directory**. If this is run in a non-empty 
directory, the archetype will fail to create the maven module.

```shell
mvn archetype:generate \
   -DarchetypeGroupId=com.azure.tools \
   -DarchetypeArtifactId=azure-client-archetype \
   -DarchetypeVersion=1.0-SNAPSHOT
```
Running the above command will prompt you to enter a details of the new client library
1. `groupId` - This is the Maven group id of the client library. For data-plane libraries, this is generally `com.azure`.
2. `artifactId` - This is the Maven artifact id of the client library. For data-plane libraries, follow the 
   naming pattern of `azure-<group>-<service>` as defined in the [Java guidelines](https://azure.github.io/azure-sdk/java_introduction.html#namespaces).
3. `version` - The version of the client library. This defaults to `1.0.0-beta.1` but you can override the version 
   by entering 'N' when you are prompted to confirm the details of the package after all these steps.
4. `package` - Name of the root package. The recommended name is `com.azure.<group>.<service>`. This will also be 
   the module name for JDK 9+ versions.
5. `servicedirectory` - This is the directory under `sdk/` this client library will be placed in 
   `azure-sdk-for-java` repository.
6. `servicename` - This is the name used in package description and README. For e.g. Text Analytics, Storage Blob, 
   App Configuration, CosmosDB etc. NOTE: Do not prefix `Azure` to the service name as this is already included in 
   the template.
7. Accept the package details when prompted to generate the maven project.
8. Copy the generated project to appropriate service directory in azure-sdk-for-java repository.
