# A_Walkthrough_AZ_CLI
A brief exploration of the AZ CLI commands


PS C:\WINDOWS\system32> az

<img src="https://github.com/marlonsingleton/A_Walkthrough_AZ_CLI/blob/master/Azure_ASCII.jpg" align="left"/></br></br></br>

<tr>
<br/>
<pre>
Welcome to the cool new Azure CLI!

Use `az --version` to display the current version.
Here are the base commands:

    account           : Manage Azure subscription information.
    acr               : Manage private registries with Azure Container Registries.
    acs               : Manage Azure Container Services.
    ad                : Manage Azure Active Directory Graph entities needed for Role Based Access
                       Control.
    advisor           : Manage Azure Advisor.
    aks               : Manage Azure Kubernetes Services.
    ams               : Manage Azure Media Services resources.
    appservice        : Manage App Service plans.
    backup            : Manage Azure Backups.
    batch             : Manage Azure Batch.
    batchai           : Manage Batch AI resources.
    billing           : Manage Azure Billing.
    bot               : Manage Microsoft Azure Bot Service.
    cache             : Commands to manage CLI objects cached using the `--defer` argument.
    cdn               : Manage Azure Content Delivery Networks (CDNs).
    cloud             : Manage registered Azure clouds.
    cognitiveservices : Manage Azure Cognitive Services accounts.
    configure         : Manage Azure CLI configuration. This command is interactive.
    consumption       : Manage consumption of Azure resources.
    container         : Manage Azure Container Instances.
    cosmosdb          : Manage Azure Cosmos DB database accounts.
    deployment        : Manage Azure Resource Manager deployments at subscription scope.
    deploymentmanager : Create and manage rollouts for your service.
    disk              : Manage Azure Managed Disks.
    dla               : (PREVIEW) Manage Data Lake Analytics accounts, jobs, and catalogs.
    dls               : (PREVIEW) Manage Data Lake Store accounts and filesystems.
    dms               : Manage Azure Data Migration Service (DMS) instances.
    eventgrid         : Manage Azure Event Grid topics and subscriptions.
    eventhubs         : Manage Azure Event Hubs namespaces, eventhubs, consumergroups and geo
                       recovery configurations - Alias.
    extension         : Manage and update CLI extensions.
    feature           : Manage resource provider features.
    feedback          : Send feedback to the Azure CLI Team!
    find              : I'm an AI robot, my advice is based on our Azure documentation as well as
                       the usage patterns of Azure CLI and Azure ARM users. Using me improves Azure
                       products and documentation.
    functionapp       : Manage function apps.
    group             : Manage resource groups and template deployments.
    hdinsight         : Manage HDInsight resources.
    identity          : Managed Service Identities.
    image             : Manage custom virtual machine images.
    interactive       : Start interactive mode. Installs the Interactive extension if not installed
                       already.
    iot               : Manage Internet of Things (IoT) assets.
    iotcentral        : Manage IoT Central assets.
    keyvault          : Manage KeyVault keys, secrets, and certificates.
    kusto             : Manage Azure Kusto resources.
    lab               : Manage Azure DevTest Labs.
    lock              : Manage Azure locks.
    login             : Log in to Azure.
    logout            : Log out to remove access to Azure subscriptions.
    managedapp        : Manage template solutions provided and maintained by Independent Software
                       Vendors (ISVs).
    maps              : Manage Azure Maps.
    mariadb           : Manage Azure Database for MariaDB servers.
    monitor           : Manage the Azure Monitor Service.
    mysql             : Manage Azure Database for MySQL servers.
    network           : Manage Azure Network resources.
    openshift         : Manage Azure Red Hat OpenShift Services.
    policy            : Manage resource policies.
    postgres          : Manage Azure Database for PostgreSQL servers.
    ppg               : Manage Proximity Placement Groups.
    provider          : Manage resource providers.
    redis             : Manage dedicated Redis caches for your Azure applications.
    relay             : Manage Azure Relay Service namespaces, WCF relays, hybrid connections, and
                       rules.
    reservations      : Manage Azure Reservations.
    resource          : Manage Azure resources.
    role              : Manage user roles for access control with Azure Active Directory and service
                       principals.
    search            : Manage Azure Search services, admin keys and query keys.
    security          : Manage your security posture with Azure Security Center.
    servicebus        : Manage Azure Service Bus namespaces, queues, topics, subscriptions, rules
                       and geo-disaster recovery configuration alias.
    sf                : Manage and administer Azure Service Fabric clusters.
    sig               : Manage shared image gallery.
    signalr           : Manage Azure SignalR Service.
    snapshot          : Manage point-in-time copies of managed disks, native blobs, or other
                       snapshots.
    sql               : Manage Azure SQL Databases and Data Warehouses.
    storage           : Manage Azure Cloud Storage resources.
    tag               : Manage resource tags.
    vm                : Manage Linux or Windows virtual machines.
    vmss              : Manage groupings of virtual machines in an Azure Virtual Machine Scale Set
                       (VMSS).
    webapp            : Manage web apps.
</pre>
</tr>
<pre>   
PS C:\WINDOWS\system32> az login
Note, we have launched a browser for you to login. For old experience with device code, use "az login --use-device-code"
You have logged in. Now let us find all the subscriptions to which you have access...
[
  {
    "cloudName": "AzureCloud",
    "id": "Removed",
    "isDefault": true,
    "name": "Pay-As-You-Go",
    "state": "Enabled",
    "tenantId": "Removed",
    "user": {
      "name": "marlonosingleton@yahoo.com",  //No spam please, thanks.
      "type": "user"
    }
  }
]

PS C:\WINDOWS\system32> az account list -o table
Name           CloudName    SubscriptionId                        State    IsDefault
\-------------  -----------  ------------------------------------  -------  -----------
Pay-As-You-Go  AzureCloud   Removed				  Enabled  True

PS C:\WINDOWS\system32> az account show -o table
EnvironmentName    IsDefault    Name           State    TenantId
\-----------------  -----------  -------------  -------  ------------------------------------
AzureCloud         True         Pay-As-You-Go  Enabled  Removed

Important to note that you can set your default subscription using "az account set -s NAME_OR_ID"

PS C:\WINDOWS\system32> az account list-locations -o table
DisplayName          Latitude    Longitude    Name
\-------------------  ----------  -----------  ------------------
East Asia            22.267      114.188      eastasia
Southeast Asia       1.283       103.833      southeastasia
Central US           41.5908     -93.6208     centralus
East US              37.3719     -79.8164     eastus
East US 2            36.6681     -78.3889     eastus2
West US              37.783      -122.417     westus
North Central US     41.8819     -87.6278     northcentralus
South Central US     29.4167     -98.5        southcentralus
North Europe         53.3478     -6.2597      northeurope
West Europe          52.3667     4.9          westeurope
Japan West           34.6939     135.5022     japanwest
Japan East           35.68       139.77       japaneast
Brazil South         -23.55      -46.633      brazilsouth
Australia East       -33.86      151.2094     australiaeast
Australia Southeast  -37.8136    144.9631     australiasoutheast
South India          12.9822     80.1636      southindia
Central India        18.5822     73.9197      centralindia
West India           19.088      72.868       westindia
Canada Central       43.653      -79.383      canadacentral
Canada East          46.817      -71.217      canadaeast
UK South             50.941      -0.799       uksouth
UK West              53.427      -3.084       ukwest
West Central US      40.890      -110.234     westcentralus
West US 2            47.233      -119.852     westus2
Korea Central        37.5665     126.9780     koreacentral
Korea South          35.1796     129.0756     koreasouth
France Central       46.3772     2.3730       francecentral
France South         43.8345     2.1972       francesouth
Australia Central    -35.3075    149.1244     australiacentral
Australia Central 2  -35.3075    149.1244     australiacentral2
South Africa North   -25.731340  28.218370    southafricanorth
South Africa West    -34.075691  18.843266    southafricawest

Let's use JMESPath query string @ http://jmespath.org/

PS C:\WINDOWS\system32> az account list-locations --query "[?longitude == '18.843266']" -o table
Name             DisplayName        Latitude    Longitude
\---------------  -----------------  ----------  -----------
southafricawest  South Africa West  -34.075691  18.843266

Quick Notes About Navigation: 
Move back a word or symbol press Ctrl <-- 
Move forward a word or symbol press Ctrl -->
Home and End to respectively move to Beginning or End of line
Esc to clear the entire line

Moving on...

You can manage your Container Registries directly from the CLI.

PS C:\WINDOWS\system32> az acr -h

Group
    az acr : Manage private registries with Azure Container Registries.

Subgroups:
    config       : Configure policies for Azure Container Registries.
    credential   : Manage login credentials for Azure Container Registries.
    helm         : Manage helm charts for Azure Container Registries.
    network-rule : Manage network rules for Azure Container Registries.
    replication  : Manage geo-replicated regions of Azure Container Registries.
    repository   : Manage repositories (image names) for Azure Container Registries.
    task         : Manage a collection of steps for building, testing and OS & Framework patching
                   container images using Azure Container Registries.
    webhook      : Manage webhooks for Azure Container Registries.

Commands:
    build        : Queues a quick build, providing streaming logs for an Azure Container Registry.
    check-name   : Checks if an Azure Container Registry name is valid and available for use.
    create       : Creates an Azure Container Registry.
    delete       : Deletes an Azure Container Registry.
    import       : Imports an image to an Azure Container Registry from another Container Registry.
                   Import removes the need to docker pull, docker tag, docker push.
    list         : Lists all the container registries under the current subscription.
    login        : Log in to an Azure Container Registry through the Docker CLI.
    run          : Queues a quick run providing streamed logs for an Azure Container Registry.
    show         : Get the details of an Azure Container Registry.
    show-usage   : Get the storage usage for an Azure Container Registry.
    update       : Update an Azure Container Registry.

You can manage AD service principals, users and groups.

PS C:\WINDOWS\system32> az ad -h

Group
    az ad : Manage Azure Active Directory Graph entities needed for Role Based Access Control.

Subgroups:
    app            : Manage applications with AAD Graph.
    group          : Manage Azure Active Directory groups.
    signed-in-user : Show graph information about current signed-in user in CLI.
    sp             : Manage Azure Active Directory service principals for automation authentication.
    user           : Manage Azure Active Directory users and user authentication.

Get recommendations on your current infrastructure. How cool is that!


PS C:\WINDOWS\system32> az advisor recommendation list --query '[].{Category:category, Impact:impact, LastUpdated:lastUpdated}' -o table
Category          Impact    LastUpdated
\----------------  --------  --------------------------------
HighAvailability  Medium    2019-05-30T11:05:09.168278+00:00
HighAvailability  Low       2019-05-30T11:05:57.174631+00:00

Apparently people love deploying ACI Connectors on Kubernetes.
We see there's an upgrade-connector in preview.

PS C:\WINDOWS\system32> az aks -h

Group
    az aks : Manage Azure Kubernetes Services.

Commands:
    browse             : Show the dashboard for a Kubernetes cluster in a web browser.
    create             : Create a new managed Kubernetes cluster.
    delete             : Delete a managed Kubernetes cluster.
    disable-addons     : Disable Kubernetes addons.
    enable-addons      : Enable Kubernetes addons.
    get-credentials    : Get access credentials for a managed Kubernetes cluster.
    get-upgrades       : Get the upgrade versions available for a managed Kubernetes cluster.
    get-versions       : Get the versions available for creating a managed Kubernetes cluster.
    install-cli        : Download and install kubectl, the Kubernetes command-line tool.
    install-connector  : (PREVIEW) Install the ACI Connector on a managed Kubernetes cluster.
    list               : List managed Kubernetes clusters.
    remove-connector   : (PREVIEW) Remove the ACI Connector from a managed Kubernetes cluster.
    remove-dev-spaces  : Remove Azure Dev Spaces from a managed Kubernetes cluster.
    scale              : Scale the node pool in a managed Kubernetes cluster.
    show               : Show the details for a managed Kubernetes cluster.
    update-credentials : Update credentials for a managed Kubernetes cluster, like service
                         principal.
    upgrade            : Upgrade a managed Kubernetes cluster to a newer version.
    upgrade-connector  : (PREVIEW) Upgrade the ACI Connector on a managed Kubernetes cluster.
    use-dev-spaces     : Use Azure Dev Spaces with a managed Kubernetes cluster.
    wait               : Wait for a managed Kubernetes cluster to reach a desired state.

Looking for a media service that can support your workload? Heard of Azure Media Services?
https://docs.microsoft.com/en-us/azure/media-services/
 
PS C:\WINDOWS\system32> az ams -h

Group
    az ams : Manage Azure Media Services resources.

Subgroups:
    account            : Manage Azure Media Services accounts.
    account-filter     : Manage account filters for an Azure Media Services account.
    asset              : Manage assets for an Azure Media Services account.
    asset-filter       : Manage asset filters for an Azure Media Services account.
    content-key-policy : Manage content key policies for an Azure Media Services account.
    job                : Manage jobs for a transform.
    live-event         : Manage live events for an Azure Media Service account.
    live-output        : Manage live outputs for an Azure Media Service account.
    streaming-endpoint : Manage streaming endpoints for an Azure Media Service account.
    streaming-locator  : Manage streaming locators for an Azure Media Services account.
    streaming-policy   : Manage streaming policies for an Azure Media Services account.
    transform          : Manage transforms for an Azure Media Services account.

Note: App Service Plan SKUs are not available everywhere. Check first!

PS C:\WINDOWS\system32> az appservice list-locations --sku P3V2 -o table
Name
\-------------------
Central US
North Europe
West Europe
Southeast Asia
East Asia
West US
East US
Japan West
Japan East
East US 2
North Central US
South Central US
Brazil South
Australia East
Australia Southeast
East Asia (Stage)
Central India
West India
South India
Canada Central
Canada East
West Central US
West US 2
UK West
UK South
East US 2 EUAP
Central US EUAP
France South
France Central
Australia Central 2
Australia Central
South Africa North
South Africa West

Backups can also be managed from the CLI. 
I haven't set up an Azure Recovery Services vault, so I'm using the example provided by Microsoft.

Example
    Show details of a particular policy
        az backup policy show --name MyBackupPolicy --resource-group MyResourceGroup --vault-name
        MyVault

Batch Jobs! You should be running a High CPU to Memory ratio VM sku for this.
You can manage anything for your task, pool, job schedule and more.

PS C:\WINDOWS\system32> az batch -h

Group
    az batch : Manage Azure Batch.

Subgroups:
    account      : Manage Azure Batch accounts.
    application  : Manage Batch applications.
    certificate  : Manage Batch certificates.
    job          : Manage Batch jobs.
    job-schedule : Manage Batch job schedules.
    location     : Manage Batch service options for a subscription at the region level.
    node         : Manage Batch compute nodes.
    pool         : Manage Batch pools.
    task         : Manage Batch tasks.

Auto scale your Batch AI cluster

PS C:\WINDOWS\system32> az batchai cluster -h

Group
    az batchai cluster : Commands to manage clusters.

Subgroups:
    file       : Commands to work with files generated by node setup task.
    node       : Commands to work with cluster nodes.

Commands:
    auto-scale : Set auto-scale parameters for a cluster.
    create     : Create a cluster.
    delete     : Delete a cluster.
    list       : List clusters.
    resize     : Resize a cluster.
    show       : Show information about a cluster.
</pre>

---
(Incomplete) More coming soon!!!
