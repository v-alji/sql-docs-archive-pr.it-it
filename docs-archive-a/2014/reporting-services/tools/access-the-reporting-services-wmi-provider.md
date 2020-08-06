---
title: Accedere al provider WMI per Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- Reporting Services WMI Provider
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- WMI provider [Reporting Services]
- programming [Reporting Services]
ms.assetid: 22cfbeb8-4ea3-4182-8f54-3341c771e87b
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: db0848ae8c988229a1804bbd4b19e6c38b68c35f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722515"
---
# <a name="access-the-reporting-services-wmi-provider"></a><span data-ttu-id="f537a-102">Accedere al provider WMI per Reporting Services</span><span class="sxs-lookup"><span data-stu-id="f537a-102">Access the Reporting Services WMI Provider</span></span>
  <span data-ttu-id="f537a-103">Nel provider WMI per Reporting Services sono esposte due classi WMI per l'amministrazione di istanze del server di report in modalità nativa tramite scripting:</span><span class="sxs-lookup"><span data-stu-id="f537a-103">The Reporting Services WMI provider exposes two WMI classes for administration of Native mode report server instances through scripting:</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="f537a-104">A partire dalla versione [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] , il provider WMI è supportato solo per server di report in modalità nativa.</span><span class="sxs-lookup"><span data-stu-id="f537a-104">Starting with the [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] release, the WMI provider is supported for only native mode report servers.</span></span> <span data-ttu-id="f537a-105">I server di report in modalità SharePoint possono essere gestiti con pagine di Amministrazione centrale SharePoint e script di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f537a-105">SharePoint mode report servers can be managed with SharePoint Central Administration pages and PowerShell scripts.</span></span>  
  
|<span data-ttu-id="f537a-106">Classe</span><span class="sxs-lookup"><span data-stu-id="f537a-106">Class</span></span>|<span data-ttu-id="f537a-107">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="f537a-107">Namespace</span></span>|<span data-ttu-id="f537a-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f537a-108">Description</span></span>|  
|-----------|---------------|-----------------|  
|<span data-ttu-id="f537a-109">MSReportServer_Instance</span><span class="sxs-lookup"><span data-stu-id="f537a-109">MSReportServer_Instance</span></span>|<span data-ttu-id="f537a-110">root\Microsoft\SqlServer\ReportServer\ RS_ *\<EncodedInstanceName>* \v11</span><span class="sxs-lookup"><span data-stu-id="f537a-110">root\Microsoft\SqlServer\ReportServer\RS_*\<EncodedInstanceName>* \v11</span></span>|<span data-ttu-id="f537a-111">Fornisce le informazioni di base necessarie affinché un client si connetta a un server di report installato.</span><span class="sxs-lookup"><span data-stu-id="f537a-111">Provides basic information required for a client to connect to an installed report server.</span></span>|  
|<span data-ttu-id="f537a-112">MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="f537a-112">MSReportServer_ConfigurationSetting</span></span>|<span data-ttu-id="f537a-113">root\Microsoft\SqlServer\ReportServer\ RS_ *\<EncodedInstanceName>* \v11\Admin</span><span class="sxs-lookup"><span data-stu-id="f537a-113">root\Microsoft\SqlServer\ReportServer\RS_*\<EncodedInstanceName>* \v11\Admin</span></span>|<span data-ttu-id="f537a-114">Rappresenta i parametri di installazione e di runtime di un'istanza del server di report.</span><span class="sxs-lookup"><span data-stu-id="f537a-114">Represents the installation and run-time parameters of a report server instance.</span></span> <span data-ttu-id="f537a-115">Tali parametri sono archiviati nel file di configurazione per il server di report.</span><span class="sxs-lookup"><span data-stu-id="f537a-115">These parameters are stored in the configuration file for the report server.</span></span><br /><br /> <span data-ttu-id="f537a-116">**\*\* Importante \*\*** Questa classe è accessibile solo con privilegi amministrativi.</span><span class="sxs-lookup"><span data-stu-id="f537a-116">**\*\* Important \*\*** This class is only accessible with administrative privileges.</span></span>|  
  
 <span data-ttu-id="f537a-117">Per ogni istanza del server di report viene creata un'istanza di ognuna delle classi sopra indicate.</span><span class="sxs-lookup"><span data-stu-id="f537a-117">An instance of each of the above classes is created for each report server instance.</span></span> <span data-ttu-id="f537a-118">È possibile utilizzare qualsiasi strumento Microsoft o di terze parti per accedere agli oggetti WMI esposti dal server di report, incluse le interfacce di programmazione WMI esposte da .NET Framework stesso.</span><span class="sxs-lookup"><span data-stu-id="f537a-118">You can use any Microsoft or third party tools to access the WMI objects exposed by the report server, including WMI programming interfaces exposed by the .NET Framework itself.</span></span> <span data-ttu-id="f537a-119">Questo argomento descrive come accedere e usare le istanze della classe WMI con il comando PowerShell [Get-WmiObject](https://technet.microsoft.com/library/dd315295.aspx).</span><span class="sxs-lookup"><span data-stu-id="f537a-119">This topic describes how to access and use the WMI class instances with the PowerShell command [Get-WmiObject](https://technet.microsoft.com/library/dd315295.aspx).</span></span>  
  
## <a name="determine-the-instance-name-in-the-namespace-string"></a><span data-ttu-id="f537a-120">Determinare il nome dell'istanza nella stringa dello spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="f537a-120">Determine the Instance Name in the Namespace String</span></span>  
 <span data-ttu-id="f537a-121">Il nome dell'istanza nel percorso dello spazio dei nomi per le classi WMI per Reporting Services è una codifica dei nomi di istanze che vengono specificati durante l'installazione delle istanze denominate di Reporting Services;</span><span class="sxs-lookup"><span data-stu-id="f537a-121">The instance name in the namespace path for the Reporting Services WMI classes is an encoding of the instance names that you specify when installing the named Reporting Services instances.</span></span> <span data-ttu-id="f537a-122">ovvero, vengono codificati i caratteri speciali nei nomi delle istanze.</span><span class="sxs-lookup"><span data-stu-id="f537a-122">Namely, special characters in the instance names are encoded.</span></span> <span data-ttu-id="f537a-123">Ad esempio, un carattere di sottolineatura (_) è codificato come "_5f", pertanto un nome di istanza "My_Instance" è codificato come "My_5fInstance" nel percorso dello spazio dei nomi WMI.</span><span class="sxs-lookup"><span data-stu-id="f537a-123">For example, an underline (_) is encoded as "_5f", so an instance name of "My_Instance" is encoded as "My_5fInstance" in the WMI namespace path.</span></span>  
  
 <span data-ttu-id="f537a-124">Per elencare i nomi codificati delle istanze del server di report nel percorso dello spazio dei nomi WMI, utilizzare il comando PowerShell seguente:</span><span class="sxs-lookup"><span data-stu-id="f537a-124">To list the encoded instance names of your report server instances in the WMI namespace path, use the following PowerShell command:</span></span>  
  
```powershell
Get-WmiObject -Namespace root\Microsoft\SqlServer\ReportServer -Class __Namespace -ComputerName hostname | Select Name  
```  
  
## <a name="access-the-wmi-classes-using-powershell"></a><span data-ttu-id="f537a-125">Accedere alle classi WMI utilizzando PowerShell</span><span class="sxs-lookup"><span data-stu-id="f537a-125">Access the WMI Classes Using PowerShell</span></span>  
 <span data-ttu-id="f537a-126">Per accedere alle classi WMI, eseguire il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="f537a-126">To access the WMI classes, run the following command:</span></span>  
  
```powershell
Get-WmiObject -Namespace <namespacename> -Class <classname> -ComputerName <hostname>  
```  
  
 <span data-ttu-id="f537a-127">Ad esempio, per accedere alla classe MSReportServer_ConfigurationSetting nell'istanza del server di report predefinita dell'host myrshost, eseguire il comando riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="f537a-127">For example, to access the MSReportServer_ConfigurationSetting class on the default report server instance of the host myrshost, run the following command.</span></span> <span data-ttu-id="f537a-128">L'istanza del server di report predefinita deve essere installata in myrshost affinché questo comando possa essere eseguito.</span><span class="sxs-lookup"><span data-stu-id="f537a-128">The default report server instance must be installed on myrshost for this command to succeed.</span></span>  
  
```powershell
Get-WmiObject -Namespace "root\Microsoft\SqlServer\ReportServer\RS_MSSQLSERER\v11\Admin" -Class MSReportServer_ConfigurationSetting -ComputerName myrshost  
```  
  
 <span data-ttu-id="f537a-129">Tutti i valori e nomi di proprietà delle classi vengono restituiti dalla sintassi di questo comando.</span><span class="sxs-lookup"><span data-stu-id="f537a-129">This command syntax outputs all class property names and values.</span></span> <span data-ttu-id="f537a-130">Si noti che vengono restituite tutte le istanze della classe MSReportServer_ConfigurationSetting, anche se si accede alla classe nello spazio dei nomi dell'istanza del server di report predefinita (RS_MSSQLSERVER).</span><span class="sxs-lookup"><span data-stu-id="f537a-130">Note that all instances of the class MSReportServer_ConfigurationSetting is returned, even though you are accessing the class in the namespace of the default report server instance (RS_MSSQLSERVER).</span></span> <span data-ttu-id="f537a-131">Ad esempio, se myrshost è installata con l'istanza del server di report predefinita e con un'istanza del server di report denominata SharePoint, tramite questo comando verranno restituiti due oggetti WMI, i nomi di proprietà e i valori di entrambe le istanze del server di report.</span><span class="sxs-lookup"><span data-stu-id="f537a-131">For example, if myrshost is installed with the default report server instance and a named report server instance called SHAREPOINT, this command will return two WMI objects and output the property names and values for both report server instances.</span></span>  
  
 <span data-ttu-id="f537a-132">Per restituire un'istanza specifica della classe quando vengono restituite più istanze, usare il parametro -Filter per filtrare i risultati in base alle proprietà con valori univoci quale InstanceName.</span><span class="sxs-lookup"><span data-stu-id="f537a-132">To return a specific class instance when multiple instances are returned, use the -Filter parameter to filter the results based on properties with unique values such as InstanceName.</span></span> <span data-ttu-id="f537a-133">Ad esempio, per restituire solo l'oggetto WMI per l'istanza del server di report predefinita, utilizzare il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="f537a-133">For example, to return only the WMI object for the default report server instance, use the following command:</span></span>  
  
```powershell
Get-WmiObject -Namespace "root\Microsoft\SqlServer\ReportServer\RS_MSSQLServer\v11\Admin" -Class MSReportServer_ConfigurationSetting -ComputerName myrshost -Filter "InstanceName='MSSQLSERVER'"  
```  
  
## <a name="query-the-available-methods-and-properties"></a><span data-ttu-id="f537a-134">Eseguire una query sui metodi e sulle proprietà disponibili</span><span class="sxs-lookup"><span data-stu-id="f537a-134">Query the Available Methods and Properties</span></span>  
 <span data-ttu-id="f537a-135">Per visualizzare i metodi e le proprietà disponibili in una delle classi WMI per Reporting Services, inviare i risultati da Get-WmiObject al comando Get-Member.</span><span class="sxs-lookup"><span data-stu-id="f537a-135">To see what methods and properties are available in one of the Reporting Services WMI classes, pipe the results from Get-WmiObject to the Get-Member command.</span></span> <span data-ttu-id="f537a-136">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="f537a-136">For example:</span></span>  
  
```powershell
Get-WmiObject -Namespace "root\Microsoft\SqlServer\ReportServer\RS_MSSQLServer\v11\Admin" -Class MSReportServer_ConfigurationSetting -ComputerName myrshost | Get-Member  
```  
  
 <span data-ttu-id="f537a-137">Per la documentazione sulle proprietà e sui metodi delle classi WMI Reporting Services, vedere....</span><span class="sxs-lookup"><span data-stu-id="f537a-137">For documentation on the properties and methods of the Reporting Services WMI classes, see ....</span></span>  
  
## <a name="use-a-wmi-method-or-property"></a><span data-ttu-id="f537a-138">Utilizzare un metodo o una proprietà WMI</span><span class="sxs-lookup"><span data-stu-id="f537a-138">Use a WMI Method or Property</span></span>  
 <span data-ttu-id="f537a-139">Una volta che si dispone degli oggetti WMI nelle classi di Reporting Services e che si conoscono i metodi e le proprietà disponibili, è possibile utilizzare questi ultimi.</span><span class="sxs-lookup"><span data-stu-id="f537a-139">Once you have the WMI objects to the Reporting Services classes and know the available methods and properties, you can use these methods and properties.</span></span> <span data-ttu-id="f537a-140">Ad esempio, se si dispone di un'istanza del server di report denominata in modalità integrata SharePoint chiamata SHAREPOINT, utilizzare la sequenza dei comandi riportata di seguito per recuperare l'URL per il sito Amministrazione centrale SharePoint:</span><span class="sxs-lookup"><span data-stu-id="f537a-140">For example, if you have a named report server instance in SharePoint integrated mode called SHAREPOINT, use the following command sequence to retrieve the URL for the SharePoint Central Administration site:</span></span>  
  
```powershell
$rsconfig = Get-WmiObject -Namespace "root\Microsoft\SqlServer\ReportServer\RS_MSSQLServer\v11\Admin" -Class MSReportServer_ConfigurationSetting -ComputerName myrshost -Filter "InstanceName='SHAREPOINT'"  
$rsconfig.GetAdminSiteUrl()  
```  
  
## <a name="see-also"></a><span data-ttu-id="f537a-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f537a-141">See Also</span></span>
 <span data-ttu-id="f537a-142">[Reporting Services riferimento alla libreria del provider WMI &#40;SSRS&#41;](../wmi-provider-library-reference/reporting-services-wmi-provider-library-reference-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="f537a-142">[Reporting Services WMI Provider Library Reference &#40;SSRS&#41;](../wmi-provider-library-reference/reporting-services-wmi-provider-library-reference-ssrs.md) </span></span>  
 [<span data-ttu-id="f537a-143">File di configurazione RSReportServer</span><span class="sxs-lookup"><span data-stu-id="f537a-143">RSReportServer Configuration File</span></span>](../report-server/rsreportserver-config-configuration-file.md)  
