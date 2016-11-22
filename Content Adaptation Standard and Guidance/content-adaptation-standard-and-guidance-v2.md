# Content Adaptation Standard and Guidance

This article introduces how to adapt Global technical contents to Mooncake Environment.

## Terms replacement

### Domain and endpoint replacement

The following is a list of Domains or endpoints that needs to be replaced in Mooncake.

|Service Type |Global |Mooncake |
|--------|--------|---------|
|Azure - regular |`*.windows.net` |`*.chinacloudapi.cn` |
|Azure - Compute |`*.cloudapp.net` |`*.chinacloudapp.cn` |
|Azure - Service Fabric Cluster |`*.cloudapp.azure.com` |`*.chinaeast.chinacloudapp.cn` |
|Azure - Storage |`*.blob.core.windows.net`<br/>`*.queue.core.windows.net`<br/>`*.table.core.windows.net` |`*.blob.core.chinacloudapi.cn`<br/>`*.queue.core.chinacloudapi.cn`<br/>`*.table.core.chinacloudapi.cn` |
|Azure - Service Management |`https://management.core.windows.net` |`https://management.core.chinacloudapi.cn` |
|Azure - Resource Manager (ARM) |`https://management.azure.com` |`https://management.chinacloudapi.cn` |
|SQL Database |`*.database.windows.net` |`*.database.chinacloudapi.cn` |
|Azure Portal |`https://manage.windowsazure.com`<br/>`https://portal.azure.com` |`https://manage.windowsazure.cn`<br/>`https://portal.azure.cn` |
|Azure SQL Database Management API |`https://management.database.windows.net` |`https://management.database.chinacloudapi.cn` |
|Service Bus |`*.servicebus.windows.net` |`*.servicebus.chinacloudapi.cn` |
|ACS |`*.accesscontrol.windows.net` |`*.accesscontrol.chinacloudapi.cn` |
|HDInsight |`*.azurehdinsight.net` |`*.azurehdinsight.cn` |
|AAD |`*.onmicrosoft.com` |`*.partner.onmschina.cn` |
|AAD Login |`https://login.windows.net`<br/>`https://login.microsoftonline.com` |`https://login.chinacloudapi.cn` |
|AAD Graph API |`https://graph.windows.net` |`https://graph.chinacloudapi.cn` |
|Azure Cognitive Service |`https://api.projectoxford.ai/face/v1.0` |`https://api.cognitive.azure.cn/face/v1.0` |
|Azure Media Services API Server URI |`https://media.windows.net/api/` | China East: `https://wamsshaclus001rest-hs.chinacloudapp.cn/API/`<br/> China North: `https://wamsbjbclus001rest-hs.chinacloudapp.cn/API/` |

There are exception for these damain and endpoint replacements. For Example, in HDInsight, There are articles that contain links to Global Azure Storage blobs. Those are sample data or sample script for HDInsight. Replacing those blob endpo will cause HTTP 404 error while trying to download. Such a link should not be replaced. The following is a list of endpoints that **should not** be replaced.

- hdiconfigactions.blob.core.windows.net
- hditutorialdata.blob.core.windows.net
- sidneyhcontent.blob.core.windows.net
- smf.cloudapp.net
- amsplayer.azurewebsites.net
- aestoken.azurewebsites.net
- sltoken.azurewebsites.net
- dashplayer.azurewebsites.net
- dsahandler.blob.core.windows.net
- dastouri.azurewebsites.net
- auxmktplceprod.blob.core.windows.net
- blitline.blob.core.windows.net
- zumo.blob.core.windows.net
- azuresdkscu.blob.core.windows.net

### Link replacement

1. Relative paths of articles should be replaced with the relative addresses on the site. For Example, "**./virtual-machines-command-line-tools.md**" should be replaced by "**/documentation/articles/virtual-machines-command-line-tools/**"

1. MSDN or technet document should be replaced by the Chinese version. For Example, "**[https://msdn.microsoft.com/library/ee460799.aspx](https://msdn.microsoft.com/library/ee460799.aspx)**" should be replaced by "**[https://msdn.microsoft.com/zh-cn/library/ee460799.aspx](https://msdn.microsoft.com/zh-cn/library/ee460799.aspx)**", and "**[https://technet.microsoft.com/library/dn282285.aspx](https://technet.microsoft.com/library/dn282285.aspx)**" should be replaced by "**[https://technet.microsoft.com/zh-cn/library/dn282285.aspx](https://technet.microsoft.com/zh-cn/library/dn282285.aspx)**".

1. Some wikipedia links can be replaced with the Chinese version. For Example, "**[http://en.wikipedia.org/wiki/Adaptive_bitrate_streaming](http://en.wikipedia.org/wiki/Adaptive_bitrate_streaming)**" should be replaced by "**[http://zh.wikipedia.org/wiki/自适性串流](http://zh.wikipedia.org/wiki/自适性串流)**"

1. Some other links which have been found in the QA section. For example, some MSDN links are redirected to Azure articles in global site. Those links should be replaced with a relative url if exists.

    There are msdn links redirecting to Global Azure articles. For example, **[http://msdn.microsoft.com/zh-cn/library/azure/gg551722.aspx](http://msdn.microsoft.com/library/azure/gg551722.aspx)** is redirecting to **[https://docs.microsoft.com/azure/cloud-services/cloud-services-certs-create](https://docs.microsoft.com/azure/cloud-services/cloud-services-certs-create)**; hence, it should be replaced with "**/documentation/articles/cloud-services-certs-create/**".

    Furthermore, There are **go.microsoft.com** and **aka.ms** forwarding links redirecting to Global Azure articles. For example, **[http://go.microsoft.com/fwlink/?LinkId=296649](http://go.microsoft.com/fwlink/?LinkId=296649)** is redirecting to **[https://docs.microsoft.com/azure/virtual-network/virtual-networks-overview](https://docs.microsoft.com/azure/virtual-network/virtual-networks-overview)**, so it should be replaced with "**/documentation/articles/virtual-networks-overview/**". And, **[http://aka.ms/runbookauthor/azure/runbookoutput](http://aka.ms/runbookauthor/azure/runbookoutput)** is redirecting to **[https://docs.microsoft.com/azure/automation/automation-runbook-output-and-messages](https://docs.microsoft.com/azure/automation/automation-runbook-output-and-messages)**, so it should be replaced with "**/documentation/articles/automation-runbook-output-and-messages/**".

### Other terminologies

1. **Azure Region**. All Azure Region should be replaced by either "**China North**" or "**China East**".

    There are 28 regions in Global Azure, while there are only 2 in Azure China. Be careful if there are more than 2 regions involved within one article. For example, in [Traffic Manager nested Profile](https://docs.microsoft.com/en-ca/azure/traffic-manager/traffic-manager-nested-profiles), The article involved with 3 regions, **West US**, **West Europe**, and **East Asia**. A simple replacement will create ambiguousness. Hence, in the [Mooncake artcle](https://www.azure.cn/documentation/articles/traffic-manager-nested-profiles/), **West US** is replaced with **China North**, **West Europe** is replaced with **China East Site 1**, and **East Asia** is replaced with **China East Site 2**. Here, the traffic manager only involved web sites; hence, such a replacement is meaningful. If the article must have more than 3 regions, delete it from Mooncake.

1. **Azure portal**. The Ibiza portal should be replaced by "**Azure Portal Preview**", and the classic portal should be replaced with "**Azure Classic Management Portal**".

1. **Microsoft Azure**. "**Microsoft Azure**" Should be replaced by "**Azure**".

1. **Free trial**. "**Free trial**" should be replaced with "**1rmb trial**".

1. **Azure Login**. AzureChinaCloud Environment should be specified.

    - Azure PowerShell - `Add-AzureAccount -EnvironmentName AzureChinaCloud` or `Add-AzureRmAccount -EnvironmentName AzureChinaCloud`
    - Azure CLI - `azure login -e AzureChinaCloud`

For term replacement, a tool has been developed with python. Here is the [GitHub Repo](https://github.com/rockboyfor/CustomizeTool).

## Deleting not suitable contents

For features that are not available in Mooncake, The corresponding technical contents should be removed.

## Some detailed customizations

For some important articles, contents may not be suitable for Mooncake. However, if a substitute solution exits, those articles still can be customized.

For Example, in App Service of Mooncake Environment. Continuous deployment is not possible to be set through the Portal. However, it can be done for public Repo in GitHub with KUDU and Webhook. Since, the continuous deployment functionality is quite important for App Service, and it's related with Agile Development which is also very important for App Service. Customizing the article other than simply deleting it would be a good idea.

However, if the features involved become available in Mooncake, those customizations will not be needed any more. That is what happened for Redis Cache. Before the Ibiza portal is available in Mooncake, Redis Cache could only be manageable with Azure PowerShell or Azure CLI. So, all portal solutions were replaced by command line solutions. After Redis Cache is available in the preview portal, all those customizations should be rolled back.