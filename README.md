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
  
PS C:\WINDOWS\system32> az login
Note, we have launched a browser for you to login. For old experience with device code, use "az login --use-device-code"
You have logged in. Now let us find all the subscriptions to which you have access...
```json
[
  {
    "cloudName": "AzureCloud",
    "id": "Removed",
    "isDefault": true,
    "name": "Pay-As-You-Go",
    "state": "Enabled",
    "tenantId": "Removed",
    "user": {
      "name": "my_email_address",  
      "type": "user"
    }
  }
]
```

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

Let's use a JMESPath query string. Find out more about it @ http://jmespath.org/

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

Moving on since I don't have any batch deployments to manage.
In effort of completeness, I'm moving over to my Ubuntu system.

marlon@linux:\~$ az billing period list -o table
BillingPeriodEndDate    BillingPeriodStartDate    Name
\----------------------  ------------------------  --------
2019-07-07              2019-06-08                201909-1
2019-06-07              2019-05-08                201908-1
2019-05-07              2019-04-08                201907-1
2019-04-07              2019-03-08                201906-1
2019-04-07              2019-03-08                201905-1
2019-03-06              2019-02-07                201904-1
<br>
Create and deploy bots!
marlon@linux:~$ az bot -h

Group
    az bot : Manage Microsoft Azure Bot Service.

Subgroups:
    authsetting     : Manage OAuth connection settings on a bot.
    directline      : Manage the Directline Channel on a bot.
    email           : Manage the email Channel on a bot.
    facebook        : Manage the Facebook Channel on a bot.
    kik             : Manage the Kik Channel on a bot.
    msteams         : Manage the Microsoft Teams Channel on a bot.
    skype           : Manage the Skype Channel on a bot.
    slack           : Manage the Slack Channel on a bot.
    sms             : Manage the SMS Channel on a bot.
    telegram        : Manage the Telegram Channel on a bot.
    webchat         : Manage the Webchat Channel on a bot.

Commands:
    create          : Create a new bot.
    delete          : Delete an existing bot.
    download        : Download an existing bot.
    prepare-deploy  : Add scripts/config files for publishing with `az webapp deployment`.
    prepare-publish : Add scripts to your local source code directory to be able to publish back
                      using `az bot publish`.
    publish         : Publish to a bot's associated app service.
    show            : Get an existing bot.
    update          : Update an existing bot.
    
See and delete what cache objects you have.

PS C:\WINDOWS\system32> az cache -h

Group
    az cache : Commands to manage CLI objects cached using the `--defer` argument.

Commands:
    delete : Delete an object from the cache.
    list   : List the contents of the object cache.
    purge  : Clear the entire CLI object cache.
    show   : Show the contents of a specific object in the cache.

PS C:\WINDOWS\system32> az cdn -h

Group
    az cdn : Manage Azure Content Delivery Networks (CDNs).

Manage your Azure cloud registration.

PS C:\WINDOWS\system32> az cloud list -o table
IsActive    Name               Profile
\----------  -----------------  ---------
True        AzureCloud         latest
False       AzureChinaCloud    latest
False       AzureUSGovernment  latest
False       AzureGermanCloud   latest

Interested in using Azure's cognitive services? You'll need the SDK.
Then you can leverage things like text sentiment, speech and Bing search services.
From here you can manage the necessary service account.

PS C:\WINDOWS\system32> az cognitiveservices -h

Group
    az cognitiveservices : Manage Azure Cognitive Services accounts.
        This article lists the Azure CLI commands for Azure Cognitive Services account and
        subscription management only. Refer to the documentation at
        https://docs.microsoft.com/azure/cognitive-services/ for individual services to learn how to
        use the APIs and supported SDKs.

Subgroups:
    account : Manage Azure Cognitive Services accounts.
    
Let's look at our Azure resource usage.

marlon@linux:~$ az consumption usage list -h

Command
    az consumption usage list : List the details of Azure resource consumption, either as an invoice
    or within a billing period.

Arguments
    --billing-period-name -p           : Name of the billing period to get the usage details that
                                         associate with.
    --end-date -e                      : End date (YYYY-MM-DD in UTC). If specified, also requires
                                         --start-date.
    --include-additional-properties -a : Include additional properties in the usages.
    --include-meter-details -m         : Include meter details in the usages.
    --start-date -s                    : Start date (YYYY-MM-DD in UTC). If specified, also requires
                                         --end-date.
    --top -t                           : Maximum number of items to return. Value range: 1-1000.

Global Arguments
    --debug                            : Increase logging verbosity to show all debug logs.
    --help -h                          : Show this help message and exit.
    --output -o                        : Output format.  Allowed values: json, jsonc, none, table,
                                         tsv, yaml.  Default: json.
    --query                            : JMESPath query string. See http://jmespath.org/ for more
                                         information and examples.
    --subscription                     : Name or ID of subscription. You can configure the default
                                         subscription using `az account set -s NAME_OR_ID`.
    --verbose                          : Increase logging verbosity. Use --debug for full debug
                                         logs.
                                         
Everyone want's to have more insight about their resource usage, right? So I went deeper with this one.
Here's the usage of the first 3 services under my subscription for the date ranges mentioned.

marlon@linux:~$ az consumption usage list -s 2019-04-01 -e 2019-05-01 --query '[:3].{Service:consumedService,Currency:currency,Usage:usageQuantity}' -o table
Service                         Currency    Usage
\------------------------------  ----------  --------------------------------------------------------------------
Microsoft.AzureActiveDirectory  USD         0.06666666666666699880838820035933167673647403717041015625
Microsoft.Storage               USD         0.000072000000000000001824061734989612659774138592183589935302734375
Microsoft.Storage               USD         0.01460000000000000013045120539345589349977672100067138671875

If the above query string looks a bit cryptic to you, another JMESPATH resource is https://azurecitadel.com/prereqs/cli/cli-3-jmespath/

I'm sure I'll talk about containers in depth on another forum.
For now, note the management capabilities available in az cli.

marlon@linux:~$ az container -h

Group
    az container : Manage Azure Container Instances.

Commands:
    attach  : Attach local standard output and error streams to a container in a container group.
    create  : Create a container group.
    delete  : Delete a container group.
    exec    : Execute a command from within a running container of a container group.
    export  : Export a container group in yaml format.
    list    : List container groups.
    logs    : Examine the logs for a container in a container group.
    restart : Restarts all containers in a container group.
    show    : Get the details of a container group.
    start   : Starts all containers in a container group.
    stop    : Stops all containers in a container group.
    
If you didn't already know, Cosmos DB formerly Azure DocumentDB is a planet-scale NoSQL database.

marlon@linux:~$ az cosmosdb -h

Group
    az cosmosdb : Manage Azure Cosmos DB database accounts.

Subgroups:
    collection               : Manage Azure Cosmos DB collections.
    database                 : Manage Azure Cosmos DB databases.
    network-rule             : Manage Azure Comsos DB network rules.

Commands:
    check-name-exists        : Checks if an Azure Cosmos DB account name exists.
    create                   : Creates a new Azure Cosmos DB database account.
    delete                   : Deletes an Azure Cosmos DB database account.
    failover-priority-change : Changes the failover priority for the Azure Cosmos DB database
                               account.
    list                     : List Azure Cosmos DB database accounts.
    list-connection-strings  : List the connection strings for a Azure Cosmos DB database account.
    list-keys                : List the access keys for a Azure Cosmos DB database account.
    list-read-only-keys      : List the read-only access keys for a Azure Cosmos DB database
                               account.
    regenerate-key           : Regenerate an access key for a Azure Cosmos DB database account.
    show                     : Get the details of an Azure Cosmos DB database account.
    update                   : Update an Azure Cosmos DB database account.
    
If you know me, I'm all about using 'az deployment' to test my ARM Template deployments.

marlon@linux:~$ az deployment -h

Group
    az deployment : Manage Azure Resource Manager deployments at subscription scope.

Subgroups:
    operation : Manage deployment operations.

Commands:
    create    : Start a deployment.
    delete    : Deletes a deployment from the deployment history.
    export    : Export the template used for a deployment.
    list      : Get all the deployments for a subscription.
    show      : Gets a deployment.
    validate  : Validate whether a template is syntactically correct.
    wait      : Place the CLI in a waiting state until a deployment condition is met.
    
Let's see how we can manage out disk.

marlon@linux:~$ az disk -h

Group
    az disk : Manage Azure Managed Disks.
        Azure Virtual Machines use disks as a place to store an operating system, applications, and
        data. All Azure virtual machines have at least two disks: An operating system disk, and a
        temporary disk. The operating system disk is created from an image, and both the operating
        system disk and the image are actually virtual hard disks (VHDs) stored in an Azure storage
        account. Virtual machines also can have one or more data disks, that are also stored as
        VHDs.

        Azure Managed and Unmanaged Data Disks have a maximum size of 4095 GB (with the exception of
        larger disks in preview). Azure Unmanaged Disks also have a maximum capacity of 4095 GB.

        For more information, see:
        - Azure Disks - https://docs.microsoft.com/en-us/azure/virtual-machines/linux/about-disks-
        and-vhds and https://docs.microsoft.com/en-us/azure/virtual-machines/windows/about-disks-
        and-vhds.
        - Larger Managed Disks in Public Preview - https://azure.microsoft.com/en-
        us/blog/introducing-the-public-preview-of-larger-managed-disks-sizes/
        - Ultra SSD Managed Disks in Public Preview - https://docs.microsoft.com/en-
        us/azure/virtual-machines/windows/disks-ultra-ssd.

Commands:
    create        : Create a managed disk.
    delete        : Delete a managed disk.
    grant-access  : Grant a resource access to a managed disk.
    list          : List managed disks.
    revoke-access : Revoke a resource's read access to a managed disk.
    show          : Gets information about a disk.
    update        : Update a managed disk.
    wait          : Place the CLI in a waiting state until a condition of a managed disk is met.


marlon@linux:~$ az disk list -o table
Name                                            ResourceGroup    Location    Zones    Sku          SizeGb    ProvisioningState    OsType
\----------------------------------------------  ---------------  ----------  -------  -----------  --------  -------------------  --------
linuxvm_DataDisk_0                              TESTMACHINESRG   eastasia             Premium_LRS  2046      Succeeded
linuxvm_disk1_c7c98b66a96f4a6995d65269f2e49f3a  TESTMACHINESRG   eastasia             Premium_LRS  30        Succeeded            Linux

It's possible to manage your data migrations as well.

marlon@linux:~$ az dms -h

Group
    az dms : Manage Azure Data Migration Service (DMS) instances.

Subgroups:
    project      : Manage Projects for an instance of the Data Migration Service.

Commands:
    check-name   : Check if a given DMS instance name is available in a given region as well as the
                   name's validity.
    check-status : Perform a health check and return the status of the service and virtual machine
                   size.
    create       : Create an instance of the Data Migration Service.
    delete       : Delete an instance of the Data Migration Service.
    list         : List the DMS instances within your currently configured subscription (to set this
                   use "az account set"). If provided, only show the instances within a given
                   resource group.
    list-skus    : List the SKUs that are supported by the Data Migration Service.
    show         : Show the details for an instance of the Data Migration Service.
    start        : Start an instance of the Data Migration Service. It can then be used to run data
                   migrations.
    stop         : Stop an instance of the Data Migration Service. While stopped, it can't be used
                   to run data migrations and the owner won't be billed.
    wait         : Place the CLI in a waiting state until a condition of the DMS instance is met.
    
If you are automating actions within your Azure environment using event grid? You're covered!

PS C:\WINDOWS\system32> az eventgrid -h

Group
    az eventgrid : Manage Azure Event Grid topics and subscriptions.

Subgroups:
    event-subscription : Manage event subscriptions for an Event Grid topic or for an Azure
                         resource.
    topic              : Manage Azure Event Grid topics.
    topic-type         : Get details for topic types.

PS C:\WINDOWS\system32> az eventgrid event-subscription -h

Group
    az eventgrid event-subscription : Manage event subscriptions for an Event Grid topic or for an
    Azure resource.
        Manage event subscriptions for an Event Grid topic, Azure subscription, resource group or
        for any other Azure resource that supports event notifications.

Commands:
    create : Create a new event subscription for an Event Grid topic or for an Azure resource.
    delete : Delete an event subscription.
    list   : List event subscriptions.
    show   : Get the details of an event subscription.
    update : Update an event subscription.
    
Are you streaming event data uses Event Hub? If so, you can manage that from here too.

marlon@localhost:~$ az eventhubs -h

Group
    az eventhubs : Manage Azure Event Hubs namespaces, eventhubs, consumergroups and geo recovery
    configurations - Alias.

Subgroups:
    eventhub          : Manage Azure EventHubs eventhub and authorization-rule.
    georecovery-alias : Manage Azure EventHubs Geo Recovery configuration Alias.
    namespace         : Manage Azure EventHubs namespace and Authorizationrule.

marlon@localhost:~$ az eventhubs eventhub -h

Group
    az eventhubs eventhub : Manage Azure EventHubs eventhub and authorization-rule.

Subgroups:
    authorization-rule : Manage Azure Service Bus Authorizationrule for Eventhub.
    consumer-group     : Manage Azure Event Hubs consumergroup.

Commands:
    create             : Creates the EventHubs Eventhub.
    delete             : Deletes the Eventhub.
    list               : List the EventHub by Namepsace.
    show               : Shows the Eventhub Details.
    update             : Updates the EventHubs Eventhub.

If you're looking to access experimental and preview commands, az extension provides it for you.
<pre>
marlon@localhost:~$ az extension list-available
[
  {
    "installed": false,
    "name": "aem",
    "preview": false,
    "summary": "Manage Azure Enhanced Monitoring Extensions for SAP",
    "version": "0.1.1"
  },
  {
    "installed": false,
    "name": "aks-preview",
    "preview": true,
    "summary": "Provides a preview for upcoming AKS features",
    "version": "0.4.5"
  },
  {
    "installed": false,
    "name": "alias",
    "preview": true,
    "summary": "Support for command aliases",
    "version": "0.5.2"
  },
  {
    "installed": false,
    "name": "appconfig",
    "preview": true,
    "summary": "Provides a preview for upcoming App Configuration features.",
    "version": "0.5.0"
  }
]

</pre>

Curious about the features availabe from various resource providers? Take a look at this small subset!

marlon@localhost:~$ az feature list -o table
Name                                                                              RegistrationState
\--------------------------------------------------------------------------------  -------------------
CloudSimple.PrivateCloudIAAS/stagingRP                                            NotRegistered
Microsoft.AAD/previewAccess                                                       NotRegistered
Microsoft.AnalysisServices/UnifiedGateway                                         NotRegistered
Microsoft.Automation/dsc                                                          NotRegistered
Microsoft.AzureStack/Marketplace                                                  NotRegistered
Microsoft.BatchAI/workspace                                                       NotRegistered
Microsoft.Blockchain/privatePreviewAccess                                         NotRegistered
Microsoft.Blueprint/privatePreview                                                NotRegistered
Microsoft.Cache/betaAccess3                                                       NotRegistered
Microsoft.Cdn/StageCanary                                                         NotRegistered
Microsoft.CognitiveServices/TokenAuthPreview                                      NotRegistered
Microsoft.Compute/AvailabilitySetPinning                                          NotRegistered
Microsoft.Compute/ZRSImagesAndSnapshots                                           NotRegistered
Microsoft.ContainerInstance/extension                                             NotRegistered
Microsoft.ContainerService/DockerEngineImage                                      NotRegistered
Microsoft.DocumentDB/Metrics                                                      NotRegistered
Microsoft.KeyVault/EventGridPreview                                               NotRegistered
Microsoft.ManagedIdentity/EnableSecurityGroups                                    NotRegistered
Microsoft.Microsoft/AllowNetworkWatcherAzureReachabilityReport                    NotRegistered
Microsoft.NetApp/AllowSMB                                                         NotRegistered
Microsoft.Network/AllowVnetPeering                                                NotRegistered
Microsoft.Sql/serverless-publicpreview                                            NotRegistered
Microsoft.Storage/AllowADFS                                                       NotRegistered
Microsoft.TerraformOSS/EnableTerraformPreview                                     NotRegistered
Microsoft.VirtualMachineImages/CanaryAccess                                       NotRegistered
Microsoft.VirtualMachineImages/VirtualMachineTemplatePreview                      NotRegistered
Microsoft.VisualStudio/ExtensionResource                                          NotRegistered
Microsoft.VMwareCloudSimple/CloudSimpleRP1                                        NotRegistered
Microsoft.Network/AllowTcpPort25Out                                               Registered

Do you have an issue? You can submit an issue directly from Azure CLI.

marlon@localhost:~$ az feedback

We appreciate your feedback!

For more information on getting started, visit: aka.ms/azcli/get-started
If you have questions, visit our Stack Overflow page: aka.ms/azcli/questions

Recent commands:

   [0] create a generic issue.
   [1] az extension list-available: SUCCESS. Ran: 4 days ago. 
   [2] az extension list-available: SUCCESS. Ran: 3 days ago. 
   [3] az extension list-available: SUCCESS. Ran: 3 days ago. 
   [4] az extension --help        : SUCCESS. Ran: 3 days ago. 
   [5] Unknown (features -h)      : FAILURE. Ran: 3 days ago. 
   [6] az feature --help          : SUCCESS. Ran: 3 days ago. 
   [7] az feature list            : SUCCESS. Ran: 3 days ago. 
   [8] az feature list            : SUCCESS. Ran: 3 days ago. 
   [9] az login                   : SUCCESS. Ran: 14 mins ago.

Enter the number of the command you would like to create an issue for. Enter q to quit: _

"az find" may or may not stick around but it makes looking for common commands patterns a bit easier.

marlon@localhost:~$ az find "cache"
This command is in preview. It may be changed/removed in a future release.
Finding examples...

Here are the most common ways to use [cache]: 

Import data into a Redis cache.
az redis import	--files
		--file-format
		--ids
		--name -n
		--resource-group -g
		--subscription

List Redis Caches.
az redis list	--resource-group -g
		--subscription

Update the patching schedule for Redis cache.
az redis patch-schedule update	--name -n
		--resource-group -g
		--schedule-entries
		--subscription
		
		
Of course you've heard of serverless. With functionapps you worry about the code, not the underlying hardware.

marlon@localhost:~$ az functionapp -h

Group
    az functionapp : Manage function apps. To install the Azure Functions Core tools see
    https://github.com/Azure/azure-functions-core-tools.

Subgroups:
    config                     : Configure a function app.
    cors                       : Manage Cross-Origin Resource Sharing (CORS).
    deployment                 : Manage function app deployments.
    devops-pipeline            : Azure Function specific integration with Azure DevOps. Please visit
                                 https://aka.ms/functions-azure-devops for more information.
    identity                   : Manage web app's managed service identity.
    plan                       : Manage App Service Plans for an Azure Function.

Commands:
    create                     : Create a function app.
    delete                     : Delete a function app.
    list                       : List function apps.
    list-consumption-locations : List available locations for running function apps.
    restart                    : Restart a function app.
    show                       : Get the details of a function app.
    start                      : Start a function app.
    stop                       : Stop a function app.
    update                     : Update a function app.
    
Easily manage your resource groups.
    
marlon@localhost:~$ az group -h

Group
    az group : Manage resource groups and template deployments.

Subgroups:
    deployment : Manage Azure Resource Manager deployments.
    lock       : Manage Azure resource group locks.

Commands:
    create     : Create a new resource group.
    delete     : Delete a resource group.
    exists     : Check if a resource group exists.
    export     : Captures a resource group as a template.
    list       : List resource groups.
    show       : Gets a resource group.
    update     : Update a resource group.
    wait       : Place the CLI in a waiting state until a condition of the resource group is met.
    

marlon@localhost:~$ az group list -o table
Name                             Location     Status
\-------------------------------  -----------  ---------
AzureBackupRG_northeurope_1      northeurope  Succeeded
b2cusers                         eastus       Succeeded
cloud-shell-storage-northeurope  northeurope  Succeeded
db_vm_test                       eastus       Succeeded
dbmigration                      brazilsouth  Succeeded
ms-test-app                      centralus    Succeeded
myTFrg                           eastus       Succeeded
NetworkWatcherRG                 northeurope  Succeeded

Working with big data? No problem!

marlon@localhost:~$ az hdinsight -h

Group
    az hdinsight : Manage HDInsight resources.
        This command group is in preview. It may be changed/removed in a future release.
Subgroups:
    application                : Manage HDInsight applications.
    monitor                    : Manage Azure Monitor logs integration on the HDInsight cluster.
    script-action              : Manage HDInsight script actions.

Commands:
    create                     : Creates a new cluster.
    delete                     : Deletes the specified HDInsight cluster.
    list                       : List clusters in the resource group or subscription.
    list-usage                 : Lists the usages for the specified location.
    resize                     : Resizes the specified HDInsight cluster to the specified size.
    rotate-disk-encryption-key : Rotate disk encryption key of the specified HDInsight cluster.
    show                       : Gets the specified cluster.
    update                     : Patch HDInsight cluster with the specified parameters.
    wait                       : Place the CLI in a waiting state until an operation is complete.
    

Are you utilizings "managed service identities"? You can manage them directly from the cli as well.

marlon@localhost:~$ az identity -h

Group
    az identity : Managed Service Identities.

Commands:
    create          : Create or update an identity in the specified subscription and resource group.
    delete          : Deletes the identity.
    list            : List Managed Service Identities.
    list-operations : Lists available operations for the Managed Identity provider.
    show            : Gets the identity.

marlon@localhost:~$ az identity list-operations -o table
Name
\--------------------------------------------------------------
Microsoft.ManagedIdentity/identities/read
Microsoft.ManagedIdentity/userAssignedIdentities/read
Microsoft.ManagedIdentity/userAssignedIdentities/write
Microsoft.ManagedIdentity/userAssignedIdentities/delete
Microsoft.ManagedIdentity/userAssignedIdentities/assign/action
Microsoft.ManagedIdentity/register/action

Are you using custom scripts in your subscription? You can list and manage them here.

marlon@Azure:~$ az image list -h

Command
    az image list : List custom VM images.

Arguments
    --resource-group -g : Name of resource group. You can configure the default group using `az
                          configure --defaults group=<name>`.

Global Arguments
    --debug             : Increase logging verbosity to show all debug logs.
    --help -h           : Show this help message and exit.
    --output -o         : Output format.  Allowed values: json, jsonc, none, table, tsv, yaml.
                          Default: json.
    --query             : JMESPath query string. See http://jmespath.org/ for more information and
                          examples.
    --subscription      : Name or ID of subscription. You can configure the default subscription
                          using `az account set -s NAME_OR_ID`.
    --verbose           : Increase logging verbosity. Use --debug for full debug logs.

Looking to utilize auto-completion, descriptions, examples...? Use "az interactive".

You'll receive a prompt like below.

marlon@Azure:~$ az interactive
This command is in preview. It may be changed/removed in a future release.
Installing the Interactive extension...
The installed extension 'interactive' is in preview.

Do you agree to sending telemetry (yes/no)? Default answer is yes:

Got IoT? : )

marlon@Azure:~$ az iot -h

Group
    az iot : Manage Internet of Things (IoT) assets.
        Comprehensive IoT data-plane functionality is available in the Azure IoT CLI Extension. For
        more info and install guide go to https://github.com/Azure/azure-iot-cli-extension.

Subgroups:
    dps : Manage Azure IoT Hub Device Provisioning Service.
    hub : Manage Azure IoT hubs.
    pnp : Manage IoT Plug and Play repositories and repository access keys.
    
Get more granular managing IoT devices.
    
marlon@Azure:~$ az iotcentral app -h

Group
    az iotcentral app : Manage IoT Central applications.

Commands:
    create : Create an IoT Central application.
    delete : Delete an IoT Central application.
    list   : List IoT Central applications.
    show   : Get the details of an IoT Central application.
    update : Update metadata for an IoT Central application.
    
Protect your secrets with az keyvault.
    
marlon@Azure:~$ az keyvault -h

Group
    az keyvault : Manage KeyVault keys, secrets, and certificates.

Subgroups:
    certificate   : Manage certificates.
    key           : Manage keys.
    network-rule  : Manage vault network ACLs.
    secret        : Manage secrets.
    storage       : Manage storage accounts.

Commands:
    create        : Create a key vault.
    delete        : Delete a key vault.
    delete-policy : Delete security policy settings for a Key Vault.
    list          : List key vaults.
    list-deleted  : Gets information about the deleted vaults in a subscription.
    purge         : Permanently deletes the specified vault.
    recover       : Recover a key vault.
    set-policy    : Update security policy settings for a Key Vault.
    show          : Show details of a key vault.
    update        : Update the properties of a key vault.
    
 Manage Kusto Clusters and Resources.
 
 marlon@localhost:~$ az kusto -h

Group
    az kusto : Manage Azure Kusto resources.

Subgroups:
    cluster  : Manage Azure Kusto clusters.
    database : Manage Azure Kusto databases.

Manage your dev environment and artifacts with az lab.

marlon@Azure:~$ az lab -h

Group
    az lab : Manage Azure DevTest Labs.
        This command group is in preview. It may be changed/removed in a future release.
Subgroups:
    arm-template    : Manage Azure Resource Manager (ARM) templates in an Azure DevTest Lab.
    artifact        : Manage DevTest Labs artifacts.
    artifact-source : Manage DevTest Lab artifact sources.
    custom-image    : Manage custom images of a DevTest Lab.
    environment     : Manage environments for an Azure DevTest Lab.
    formula         : Manage formulas for an Azure DevTest Lab.
    gallery-image   : List Azure Marketplace images allowed for a DevTest Lab.
    secret          : Manage secrets of an Azure DevTest Lab.
    vm              : Manage VMs in an Azure DevTest Lab.
    vnet            : Manage virtual networks of an Azure DevTest Lab.

Commands:
    delete          : Delete lab.
    get             : Get lab.
    
    
Lock your resources to prevent accidental changes using "az lock"

marlon@localhost:~$ az lock -h

Group
    az lock : Manage Azure locks.

Commands:
    create : Create a lock.
    delete : Delete a lock.
    list   : List lock information.
    show   : Show the properties of a lock.
    update : Update a lock.

Interactive sign-in from Azure CLI.
<pre>
marlon@Azure:~$ az login -h

Command
    az login : Log in to Azure.

Arguments
    --allow-no-subscriptions : Support access tenants without subscriptions. It's uncommon but
                               useful to run tenant level commands, such as 'az ad'.
    --password -p            : Credentials like user password, or for a service principal, provide
                               client secret or a pem file with key and public certificate. Will
                               prompt if not given.
    --service-principal      : The credential representing a service principal.
    --tenant -t              : The AAD tenant, must provide when using service principals.
    --use-cert-sn-issuer     : Used with a service principal configured with Subject Name and Issuer
                               Authentication in order to support automatic certificate rolls.
    --use-device-code        : Use CLI's old authentication flow based on device code. CLI will also
                               use this if it can't launch a browser in your behalf, e.g. in remote
                               SSH or Cloud Shell.
    --username -u            : User name, service principal, or managed service identity ID.

Managed Service Identity Arguments
    --identity -i            : Log in using the Virtual Machine's identity.

Global Arguments
    --debug                  : Increase logging verbosity to show all debug logs.
    --help -h                : Show this help message and exit.
    --output -o              : Output format.  Allowed values: json, jsonc, none, table, tsv, yaml.
                               Default: json.
    --query                  : JMESPath query string. See http://jmespath.org/ for more information
                               and examples.
    --verbose                : Increase logging verbosity. Use --debug for full debug logs.

Logout out of your Azure subscription.

marlon@Azure:~$ az logout -h

Command
    az logout : Log out to remove access to Azure subscriptions.

Arguments
    --username  : Account user, if missing, logout the current active account.

Global Arguments
    --debug     : Increase logging verbosity to show all debug logs.
    --help -h   : Show this help message and exit.
    --output -o : Output format.  Allowed values: json, jsonc, none, table, tsv, yaml.  Default:
                  json.
    --query     : JMESPath query string. See http://jmespath.org/ for more information and examples.
    --verbose   : Increase logging verbosity. Use --debug for full debug logs.
    
You can manage template solutions provided and maintained by Independent Software Vendors (ISVs).

marlon@Azure:~$ az managedapp -h

Group
    az managedapp : Manage template solutions provided and maintained by Independent Software
    Vendors (ISVs).

Subgroups:
    definition : Manage Azure Managed Applications.

Commands:
    create     : Create a managed application.
    delete     : Delete a managed application.
    list       : List managed applications.
    show       : Gets a managed application.
    
Manage the geospatial services that use fresh mapping data to provide accurate geographic context to your web and mobile applications.

marlon@Azure:~$ az maps account -h

Group
    az maps account : Manage Azure Maps accounts.

Subgroups:
    keys   : Manage Azure Maps account keys.

Commands:
    create : Create a maps account.
    delete : Delete a maps account.
    list   : Show all maps accounts in a subscription or in a resource group.
    show   : Show the details of a maps account.
    update : Update the properties of a maps account.
    
Manage Azure DBs for MariaDB servers.

marlon@localhost:~$ az mariadb -h

Group
    az mariadb : Manage Azure Database for MariaDB servers.

Subgroups:
    db          : Manage MariaDB databases on a server.
    server      : Manage MariaDB servers.
    server-logs : Manage server logs.
    
Do you need to manage Azure Monitor?

marlon@Azure:~$ az monitor -h

Group
    az monitor : Manage the Azure Monitor Service.

Subgroups:
    action-group        : Manage action groups.
    activity-log        : Manage activity logs.
    autoscale           : Manage autoscale settings.
    diagnostic-settings : Manage service diagnostic settings.
    log-profiles        : Manage log profiles.
    metrics             : View Azure resource metrics.
    
Manage your Azure MySQL servers.

marlon@Azure:~$ az mysql -h

Group
    az mysql : Manage Azure Database for MySQL servers.

Subgroups:
    db          : Manage MySQL databases on a server.
    server      : Manage MySQL servers.
    server-logs : Manage server logs.
    
Manage your Azure Network resources.

marlon@Azure:~$ az network -h

Group
    az network : Manage Azure Network resources.

Subgroups:
    application-gateway            : Manage application-level routing and load balancing services.
    asg                            : Manage application security groups (ASGs).
    ddos-protection                : Manage DDoS Protection Plans.
    dns                            : Manage DNS domains in Azure.
    express-route                  : Manage dedicated private network fiber connections to Azure.
    lb                             : Manage and configure load balancers.
    local-gateway                  : Manage local gateways.
    nat                            : Commands to manage NAT resources.
    nic                            : Manage network interfaces.
    nsg                            : Manage Azure Network Security Groups (NSGs).
    private-dns                    : Manage Private DNS domains in Azure.
    private-endpoint               : Manage private endpoints.
    private-link-service [Preview] : Manage private link services.
    profile                        : Manage network profiles.
    public-ip                      : Manage public IP addresses.
    route-filter         [Preview] : Manage route filters.
    route-table                    : Manage route tables.
    service-endpoint               : Manage policies related to service endpoints.
    traffic-manager                : Manage the routing of incoming traffic.
    vnet                           : Manage Azure Virtual Networks.
    vnet-gateway                   : Use an Azure Virtual Network Gateway to establish secure,
                                     cross-premises connectivity.
    vpn-connection                 : Manage VPN connections.
    watcher                        : Manage the Azure Network Watcher.

Commands:
    list-service-tags              : List all service tags which are below to different resources.
    list-usages                    : List the number of network resources in a region that are used
                                     against a subscription quota.
				     
Are you utilizing Red Hat OpenShift? Discover Azure Red Hat OpenShift Services.

Group
    az openshift : Manage Azure Red Hat OpenShift Services.

Commands:
    create : Create a new managed OpenShift cluster.
    delete : Delete a managed OpenShift cluster.
    list   : List managed OpenShift clusters.
    scale  : Scale the compute pool in a managed OpenShift cluster.
    show   : Show the details for a managed OpenShift cluster.
    wait   : Wait for a managed OpenShift cluster to reach a desired state.
    
Azure Policy helps enforce and manage rules needed for your organization to met and maintain compliance standards.

marlon@Azure:~$ az policy -h

Group
    az policy : Manage resource policies.

Subgroups:
    assignment            : Manage resource policy assignments.
    definition            : Manage resource policy definitions.
    event       [Preview] : Manage policy events.
    remediation [Preview] : Manage resource policy remediations.
    set-definition        : Manage resource policy set definitions.
    state       [Preview] : Manage policy compliance states.
    
Manage your PostgreSQL servers/databases on Azure.

marlon@Azure:~$ az postgres -h

Group
    az postgres : Manage Azure Database for PostgreSQL servers.

Subgroups:
    db          : Manage PostgreSQL databases on a server.
    server      : Manage PostgreSQL servers.
    server-logs : Manage server logs.
    
Azure Proximity Placement Groups helps control network latency by controlling the placement of VMs.    
    
marlon@Azure:~$ az ppg -h

Group
    az ppg : Manage Proximity Placement Groups.

Commands:
    create : Create a proximity placement group.
    delete : Delete a proximity placement group.
    list   : List proximity placement groups.
    show   : Get a proximity placement group.
    update : Update a proximity placement group.
    
A resource provider is a service that provides Azure resources. Let's list what providers have not been registered.

marlon@Azure:~$ az provider list --query "[?registrationState=='NotRegistered']" -o table
Namespace                               RegistrationState    RegistrationPolicy
--------------------------------------  -------------------  --------------------
84codes.CloudAMQP                       NotRegistered        RegistrationRequired
Conexlink.MyCloudIT                     NotRegistered        RegistrationRequired
Crypteron.DataSecurity                  NotRegistered        RegistrationRequired
LiveArena.Broadcast                     NotRegistered        RegistrationRequired
Mailjet.Email                           NotRegistered        RegistrationRequired
Microsoft.AAD                           NotRegistered        RegistrationRequired
Microsoft.Addons                        NotRegistered        RegistrationRequired
Microsoft.Advisor                       NotRegistered        RegistrationRequired
Microsoft.AlertsManagement              NotRegistered        RegistrationRequired
Microsoft.AnalysisServices              NotRegistered        RegistrationRequired
Microsoft.ApiManagement                 NotRegistered        RegistrationRequired
Microsoft.AppConfiguration              NotRegistered        RegistrationRequired
Microsoft.AppPlatform                   NotRegistered        RegistrationRequired
Microsoft.Attestation                   NotRegistered        RegistrationRequired
Microsoft.Automation                    NotRegistered        RegistrationRequired
Microsoft.AzureActiveDirectory          NotRegistered        RegistrationRequired
Microsoft.AzureData                     NotRegistered        RegistrationRequired
Microsoft.AzureStack                    NotRegistered        RegistrationRequired
Microsoft.Batch                         NotRegistered        RegistrationRequired
Microsoft.BatchAI                       NotRegistered        RegistrationRequired
Microsoft.BingMaps                      NotRegistered        RegistrationRequired
Microsoft.Blockchain                    NotRegistered        RegistrationRequired
Microsoft.Blueprint                     NotRegistered        RegistrationRequired
Microsoft.BotService                    NotRegistered        RegistrationRequired
Microsoft.Cache                         NotRegistered        RegistrationRequired
Microsoft.Capacity                      NotRegistered        RegistrationRequired
Microsoft.Cdn                           NotRegistered        RegistrationRequired
Microsoft.CertificateRegistration       NotRegistered        RegistrationRequired
Microsoft.ChangeAnalysis                NotRegistered        RegistrationRequired
Microsoft.ClassicCompute                NotRegistered        RegistrationRequired
Microsoft.ClassicInfrastructureMigrate  NotRegistered        RegistrationRequired
Microsoft.ClassicNetwork                NotRegistered        RegistrationRequired
Microsoft.ClassicStorage                NotRegistered        RegistrationRequired
Microsoft.CognitiveServices             NotRegistered        RegistrationRequired
Microsoft.ContainerInstance             NotRegistered        RegistrationRequired
Microsoft.ContainerRegistry             NotRegistered        RegistrationRequired
Microsoft.ContainerService              NotRegistered        RegistrationRequired
Microsoft.CostManagementExports         NotRegistered        RegistrationRequired
Microsoft.CustomerLockbox               NotRegistered        RegistrationRequired
Microsoft.CustomProviders               NotRegistered        RegistrationRequired
Microsoft.DataBox                       NotRegistered        RegistrationRequired
Microsoft.DataBoxEdge                   NotRegistered        RegistrationRequired
Microsoft.Databricks                    NotRegistered        RegistrationRequired
Microsoft.DataCatalog                   NotRegistered        RegistrationRequired
Microsoft.DataFactory                   NotRegistered        RegistrationRequired
Microsoft.DataLakeAnalytics             NotRegistered        RegistrationRequired
Microsoft.DataLakeStore                 NotRegistered        RegistrationRequired
Microsoft.DataMigration                 NotRegistered        RegistrationRequired
Microsoft.DataShare                     NotRegistered        RegistrationRequired
Microsoft.DBforMariaDB                  NotRegistered        RegistrationRequired
Microsoft.DBforMySQL                    NotRegistered        RegistrationRequired
Microsoft.DBforPostgreSQL               NotRegistered        RegistrationRequired
Microsoft.DeploymentManager             NotRegistered        RegistrationRequired
Microsoft.DesktopVirtualization         NotRegistered        RegistrationRequired
Microsoft.Devices                       NotRegistered        RegistrationRequired
Microsoft.DevOps                        NotRegistered        RegistrationRequired
Microsoft.DevSpaces                     NotRegistered        RegistrationRequired
Microsoft.DocumentDB                    NotRegistered        RegistrationRequired
Microsoft.DomainRegistration            NotRegistered        RegistrationRequired
Microsoft.EnterpriseKnowledgeGraph      NotRegistered        RegistrationRequired
Microsoft.EventGrid                     NotRegistered        RegistrationRequired
Microsoft.EventHub                      NotRegistered        RegistrationRequired
Microsoft.GuestConfiguration            NotRegistered        RegistrationRequired
Microsoft.HanaOnAzure                   NotRegistered        RegistrationRequired
Microsoft.HardwareSecurityModules       NotRegistered        RegistrationRequired
Microsoft.HDInsight                     NotRegistered        RegistrationRequired
Microsoft.HealthcareApis                NotRegistered        RegistrationRequired
Microsoft.HybridCompute                 NotRegistered        RegistrationRequired
Microsoft.HybridData                    NotRegistered        RegistrationRequired
Microsoft.Hydra                         NotRegistered        RegistrationRequired
Microsoft.ImportExport                  NotRegistered        RegistrationRequired
microsoft.insights                      NotRegistered        RegistrationRequired
Microsoft.IoTCentral                    NotRegistered        RegistrationRequired
Microsoft.IoTSpaces                     NotRegistered        RegistrationRequired
Microsoft.Kusto                         NotRegistered        RegistrationRequired
Microsoft.LabServices                   NotRegistered        RegistrationRequired
Microsoft.Logic                         NotRegistered        RegistrationRequired
Microsoft.MachineLearning               NotRegistered        RegistrationRequired
Microsoft.MachineLearningServices       NotRegistered        RegistrationRequired
Microsoft.ManagedIdentity               NotRegistered        RegistrationRequired
Microsoft.ManagedServices               NotRegistered        RegistrationRequired
Microsoft.Management                    NotRegistered        RegistrationRequired
Microsoft.Maps                          NotRegistered        RegistrationRequired
Microsoft.Marketplace                   NotRegistered        RegistrationRequired
Microsoft.MarketplaceApps               NotRegistered        RegistrationRequired
Microsoft.Media                         NotRegistered        RegistrationRequired
Microsoft.Migrate                       NotRegistered        RegistrationRequired
Microsoft.MixedReality                  NotRegistered        RegistrationRequired
Microsoft.NetApp                        NotRegistered        RegistrationRequired
Microsoft.NotificationHubs              NotRegistered        RegistrationRequired
Microsoft.ObjectStore                   NotRegistered        RegistrationRequired
Microsoft.OffAzure                      NotRegistered        RegistrationRequired
Microsoft.OperationalInsights           NotRegistered        RegistrationRequired
Microsoft.OperationsManagement          NotRegistered        RegistrationRequired
Microsoft.Peering                       NotRegistered        RegistrationRequired
Microsoft.PowerBI                       NotRegistered        RegistrationRequired
Microsoft.PowerBIDedicated              NotRegistered        RegistrationRequired
Microsoft.ProviderHub                   NotRegistered        RegistrationRequired
Microsoft.RecoveryServices              NotRegistered        RegistrationRequired
Microsoft.Relay                         NotRegistered        RegistrationRequired
Microsoft.SaaS                          NotRegistered        RegistrationRequired
Microsoft.Scheduler                     NotRegistered        RegistrationRequired
Microsoft.Search                        NotRegistered        RegistrationRequired
Microsoft.SecurityInsights              NotRegistered        RegistrationRequired
Microsoft.ServiceBus                    NotRegistered        RegistrationRequired
Microsoft.ServiceFabric                 NotRegistered        RegistrationRequired
Microsoft.ServiceFabricMesh             NotRegistered        RegistrationRequired
Microsoft.Services                      NotRegistered        RegistrationRequired
Microsoft.SignalRService                NotRegistered        RegistrationRequired
Microsoft.SoftwarePlan                  NotRegistered        RegistrationRequired
Microsoft.Solutions                     NotRegistered        RegistrationRequired
Microsoft.Sql                           NotRegistered        RegistrationRequired
Microsoft.StorageCache                  NotRegistered        RegistrationRequired
Microsoft.StorageSync                   NotRegistered        RegistrationRequired
Microsoft.StorSimple                    NotRegistered        RegistrationRequired
Microsoft.StreamAnalytics               NotRegistered        RegistrationRequired
Microsoft.Subscription                  NotRegistered        RegistrationRequired
Microsoft.TimeSeriesInsights            NotRegistered        RegistrationRequired
Microsoft.Token                         NotRegistered        RegistrationRequired
Microsoft.VirtualMachineImages          NotRegistered        RegistrationRequired
microsoft.visualstudio                  NotRegistered        RegistrationRequired
Microsoft.VMwareCloudSimple             NotRegistered        RegistrationRequired
Microsoft.Web                           NotRegistered        RegistrationRequired
Microsoft.WindowsIoT                    NotRegistered        RegistrationRequired
Myget.PackageManagement                 NotRegistered        RegistrationRequired
Paraleap.CloudMonix                     NotRegistered        RegistrationRequired
Pokitdok.Platform                       NotRegistered        RegistrationRequired
RavenHq.Db                              NotRegistered        RegistrationRequired
Raygun.CrashReporting                   NotRegistered        RegistrationRequired
Sendgrid.Email                          NotRegistered        RegistrationRequired
Sparkpost.Basic                         NotRegistered        RegistrationRequired
stackify.retrace                        NotRegistered        RegistrationRequired
U2uconsult.TheIdentityHub               NotRegistered        RegistrationRequired

Are you using Redis Cache to improve the performance and scalability of your systems?

marlon@Azure:~$ az redis -h

Group
    az redis : Manage dedicated Redis caches for your Azure applications.

Subgroups:
    firewall-rules  : Manage Redis firewall rules.
    patch-schedule  : Manage Redis patch schedules.
    server-link     : Manage Redis server links.

Commands:
    create          : Create new Redis Cache instance.
    delete          : Deletes a Redis cache.
    export          : Export data stored in a Redis cache.
    force-reboot    : Reboot specified Redis node(s).
    import          : Import data into a Redis cache.
    list            : List Redis Caches.
    list-keys       : Retrieve a Redis cache's access keys.
    regenerate-keys : Regenerate Redis cache's access keys.
    show            : Gets a Redis cache (resource description).
    update          : Update a Redis cache.
</pre>

---
(Incomplete) updated frequently!!!
