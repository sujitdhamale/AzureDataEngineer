# Create a SQL elastic pool


ADMIN_LOGIN="ServerAdmin"
RESOURCE_GROUP=SujitResourceGroup
SERVERNAME=FitnessSQLServer-01
LOCATION=centralus
PASSWORD=sujit@123


## Create a server named FitnessSQLServer-01.
az sql server create \
--name $SERVERNAME \
--resource-group $RESOURCE_GROUP \
--location $LOCATION \
--admin-user $ADMIN_LOGIN \
--admin-password $PASSWORD

### output 
	sujit@Azure:~$ az sql server create --name $SERVERNAME --resource-group $RESOURCE_GROUP --location $LOCATION --admin-user $ADMIN_LOGIN --admin-password $PASSWORD
	{
	  "administratorLogin": "ServerAdmin",
	  "administratorLoginPassword": null,
	  "fullyQualifiedDomainName": "fitnesssqlserver-01.database.windows.net",
	  "id": "/subscriptions/209c8b9a-4747-4214-85d2-2834220332df/resourceGroups/SujitResourceGroup/providers/Microsoft.Sql/servers/fitnesssqlserver-01",
	  "identity": null,
	  "kind": "v12.0",
	  "location": "centralus",
	  "name": "fitnesssqlserver-01",
	  "resourceGroup": "SujitResourceGroup",
	  "state": "Ready",
	  "tags": null,
	  "type": "Microsoft.Sql/servers",
	  "version": "12.0"
	}
	
## Add a database named FitnessVancouverDB to FitnessSQLServer-nnnn.
az sql db create \
--resource-group $RESOURCE_GROUP \
--server $SERVERNAME \
--name FitnessVancouverDB

## Add a database named FitnessParisDB to FitnessSQLServer-nnnn.
az sql db create \
--resource-group $RESOURCE_GROUP \
--server $SERVERNAME \
--name FitnessParisDB
