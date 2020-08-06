---
title: Registrare un provider di dati .NET Framework standard (SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- reports [Reporting Services], data
- .NET Framework data providers for Reporting Services
- data processing extensions [Reporting Services]
- data providers [Reporting Services]
- data retrieval [Reporting Services]
- Reporting Services, data sources
ms.assetid: d92add64-e93c-4598-8508-55d1bc46acf6
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 5fd26f9c7fa163d9e6005d42e24c7b1483987f3e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712772"
---
# <a name="register-a-standard-net-framework-data-provider-ssrs"></a><span data-ttu-id="33d28-102">Registrare un provider di dati .NET Framework standard (SSRS)</span><span class="sxs-lookup"><span data-stu-id="33d28-102">Register a Standard .NET Framework Data Provider (SSRS)</span></span>
  <span data-ttu-id="33d28-103">Per usare un provider di dati [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] di terze parti per recuperare dati per un set di dati di un report [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] , è necessario distribuire e registrare l'assembly del provider di dati [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] in due posizioni, ovvero nel client di creazione dei report e nel server di report.</span><span class="sxs-lookup"><span data-stu-id="33d28-103">To use a third-party [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] data provider to retrieve data for a [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] report dataset, you need to deploy and register the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] data provider assembly in two locations: on the report authoring client and on the report server.</span></span> <span data-ttu-id="33d28-104">Nel client per la creazione del report, è necessario registrare il provider di dati come tipo di origine dei dati e associarlo a una finestra Progettazione query.</span><span class="sxs-lookup"><span data-stu-id="33d28-104">On the report authoring client, you must register the data provider as a data source type and associate it with a query designer.</span></span> <span data-ttu-id="33d28-105">Sarà quindi possibile selezionare il provider di dati come tipo di origine dei dati per la creazione di un set di dati di report.</span><span class="sxs-lookup"><span data-stu-id="33d28-105">You can then select this data provider as a type of data source when you create a report dataset.</span></span> <span data-ttu-id="33d28-106">La finestra Progettazione query associata verrà aperta per consentire la creazione di query per il tipo di origine dei dati specifico.</span><span class="sxs-lookup"><span data-stu-id="33d28-106">The associated query designer opens to help you create queries for this data source type.</span></span> <span data-ttu-id="33d28-107">Nel server di report il provider di dati deve essere registrato come tipo di origine dei dati.</span><span class="sxs-lookup"><span data-stu-id="33d28-107">On the report server, you must register the data provider as a data source type.</span></span> <span data-ttu-id="33d28-108">Sarà quindi possibile elaborare i report pubblicati che recuperano i dati da un'origine mediante il provider di dati.</span><span class="sxs-lookup"><span data-stu-id="33d28-108">You can then process published reports that retrieve data from a data source using this data provider.</span></span>  
  
 <span data-ttu-id="33d28-109">I provider di dati di terze parti possono non offrire tutte le funzionalità disponibili nelle estensioni per l'elaborazione dati di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="33d28-109">Third-party data providers do not necessarily provide all the functionality available with the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] data processing extensions.</span></span> <span data-ttu-id="33d28-110">Per altre informazioni, vedere [Origini dati supportate da Reporting Services &#40;SSRS&#41;](../create-deploy-and-manage-mobile-and-paginated-reports.md).</span><span class="sxs-lookup"><span data-stu-id="33d28-110">For more information, see [Data Sources Supported by Reporting Services &#40;SSRS&#41;](../create-deploy-and-manage-mobile-and-paginated-reports.md).</span></span> <span data-ttu-id="33d28-111">Per informazioni sull'estensione della funzionalità di un[!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)]</span><span class="sxs-lookup"><span data-stu-id="33d28-111">To learn about extending the functionality of a .[!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)]</span></span> <span data-ttu-id="33d28-112">provider di dati , vedere [Implementazione di un'estensione per l'elaborazione dati](../extensions/data-processing/implementing-a-data-processing-extension.md).</span><span class="sxs-lookup"><span data-stu-id="33d28-112">data provider, see [Implementing a Data Processing Extension](../extensions/data-processing/implementing-a-data-processing-extension.md).</span></span>  
  
 <span data-ttu-id="33d28-113">Per installare e registrare i provider di dati è necessario disporre di credenziali di amministratore.</span><span class="sxs-lookup"><span data-stu-id="33d28-113">You need administrator credentials to install and register data providers.</span></span>  
  
## <a name="registering-a-net-framework-data-provider-on-the-report-server"></a><span data-ttu-id="33d28-114">Registrazione di un provider di dati .NET Framework nel server di report</span><span class="sxs-lookup"><span data-stu-id="33d28-114">Registering a .NET Framework Data Provider on the Report Server</span></span>  
 <span data-ttu-id="33d28-115">Per elaborare i report pubblicati che utilizzano il provider di dati [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] nel server di report, è necessario installare l'assembly in quest'ultimo.</span><span class="sxs-lookup"><span data-stu-id="33d28-115">In order to process published reports that use this [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] data provider on the report server, you need to install the assembly on the report server.</span></span> <span data-ttu-id="33d28-116">È necessario modificare due file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="33d28-116">You must modify two configuration files.</span></span> <span data-ttu-id="33d28-117">Per registrare il provider di dati, modificare rsreportserver.config.</span><span class="sxs-lookup"><span data-stu-id="33d28-117">Modify rsreportserver.config to register the data provider.</span></span> <span data-ttu-id="33d28-118">Per assegnare autorizzazioni di sicurezza dell'accesso al codice per l'assembly, modificare rssrvpolicy.config.</span><span class="sxs-lookup"><span data-stu-id="33d28-118">Modify rssrvpolicy.config to grant code access security permissions for the assembly.</span></span>  
  
#### <a name="to-install-a-data-provider-assembly-on-the-report-server"></a><span data-ttu-id="33d28-119">Per installare l'assembly di un provider di dati nel server di report</span><span class="sxs-lookup"><span data-stu-id="33d28-119">To install a data provider assembly on the report server</span></span>  
  
1.  <span data-ttu-id="33d28-120">Accedere al percorso predefinito della directory bin nel server di report in cui si vuole usare il provider di dati [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="33d28-120">Navigate to the default location of the bin directory on the report server on which you want to use the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] data provider.</span></span> <span data-ttu-id="33d28-121">Il percorso predefinito della directory bin del server di report è *\<drive>* : \programmi\microsoft SQL Server \ MSRS10_50. MSSQLSERVER\Reporting Services\ReportServer\bin.</span><span class="sxs-lookup"><span data-stu-id="33d28-121">The default location of the report server bin directory is *\<drive>*:\Program Files\Microsoft SQL Server\MSRS10_50.MSSQLSERVER\Reporting Services\ReportServer\bin.</span></span>  
  
2.  <span data-ttu-id="33d28-122">Copiare l'assembly dal percorso di gestione temporanea nella directory bin del server di report.</span><span class="sxs-lookup"><span data-stu-id="33d28-122">Copy your assembly from your staging location to the bin directory of the report server.</span></span> <span data-ttu-id="33d28-123">In alternativa, è possibile caricare l'assembly nella Global Assembly Cache (GAC).</span><span class="sxs-lookup"><span data-stu-id="33d28-123">Alternatively, you can load your assembly in the global assembly cache (GAC).</span></span> <span data-ttu-id="33d28-124">Per altre informazioni, vedere [Utilizzo di assembly e della Global Assembly Cache](https://go.microsoft.com/fwlink/?linkid=63912) nella documentazione di [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] SDK in MSDN.</span><span class="sxs-lookup"><span data-stu-id="33d28-124">For more information, see [Working with Assemblies and the Global Assembly Cache](https://go.microsoft.com/fwlink/?linkid=63912) in the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] SDK documentation on MSDN.</span></span>  
  
#### <a name="to-register-a-net-data-provider-on-the-report-server"></a><span data-ttu-id="33d28-125">Per registrare un provider di dati .NET nel server di report</span><span class="sxs-lookup"><span data-stu-id="33d28-125">To register a .NET data provider on the report server</span></span>  
  
1.  <span data-ttu-id="33d28-126">Eseguire una copia di backup del file RSReportServer.config nella directory padre di ReportServer per bin.</span><span class="sxs-lookup"><span data-stu-id="33d28-126">Make a backup of the RSReportServer.config file in the ReportServer parent directory for bin.</span></span>  
  
2.  <span data-ttu-id="33d28-127">Aprire RSReportServer.config. È possibile aprire il file di configurazione con [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] o con un semplice editor di testo, ad esempio il Blocco note.</span><span class="sxs-lookup"><span data-stu-id="33d28-127">Open RSReportServer.config. You can open the configuration file with [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] or a simple text editor, such as Notepad.</span></span>  
  
3.  <span data-ttu-id="33d28-128">Individuare l'elemento `Data` nel file RSReportServer.config.</span><span class="sxs-lookup"><span data-stu-id="33d28-128">Locate the `Data` element in the RSReportServer.config file.</span></span> <span data-ttu-id="33d28-129">Una voce relativa al provider di dati [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] dovrà essere inserita nella posizione seguente:</span><span class="sxs-lookup"><span data-stu-id="33d28-129">An entry for the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] data provider should be made in the following location:</span></span>  
  
    ```  
    <Extensions>  
       <Data>  
          <Extension Your data provider configuration information goes here />  
       </Data>  
    </Extensions>  
    ```  
  
4.  <span data-ttu-id="33d28-130">Aggiungere una voce per il provider di dati [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="33d28-130">Add an entry for the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] data provider.</span></span>  
  
    |<span data-ttu-id="33d28-131">Attributo</span><span class="sxs-lookup"><span data-stu-id="33d28-131">Attribute</span></span>|<span data-ttu-id="33d28-132">Descrizione</span><span class="sxs-lookup"><span data-stu-id="33d28-132">Description</span></span>|  
    |---------------|-----------------|  
    |`Name`|<span data-ttu-id="33d28-133">Specificare un nome univoco per il provider di dati, ad esempio **ProviderDatiNET**.</span><span class="sxs-lookup"><span data-stu-id="33d28-133">Provide a unique name for the data provider, for example, **MyNETDataProvider**.</span></span> <span data-ttu-id="33d28-134">La lunghezza massima consentita per l'attributo `Name` è di 255 caratteri.</span><span class="sxs-lookup"><span data-stu-id="33d28-134">The maximum length for the `Name` attribute is 255 characters.</span></span> <span data-ttu-id="33d28-135">Il nome deve essere univoco all'interno di tutte le voci dell'elemento `Extension` di un file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="33d28-135">The name must be unique among all entries within the `Extension` element of a configuration file.</span></span> <span data-ttu-id="33d28-136">Il valore indicato qui viene inserito nell'elenco a discesa dei tipi di origini dei dati per la creazione di una nuova origine.</span><span class="sxs-lookup"><span data-stu-id="33d28-136">The value you include here appears in the drop-down list of data source types when you create a new data source.</span></span>|  
    |`Type`|<span data-ttu-id="33d28-137">Immettere un elenco delimitato da virgole che includa lo spazio dei nomi completo della classe che implementa l'interfaccia <xref:System.Data.IDbConnection> , seguito dal nome dell'assembly del provider di dati [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] , senza l'estensione dll.</span><span class="sxs-lookup"><span data-stu-id="33d28-137">Enter a comma-separated list that includes the fully qualified namespace of the class that implements the <xref:System.Data.IDbConnection> interface, followed by the name of the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] data provider assembly (not including the .dll file name extension).</span></span>|  
  
     <span data-ttu-id="33d28-138">La voce relativa a una DLL distribuita nella directory bin del server di report potrebbe essere analoga alla seguente:</span><span class="sxs-lookup"><span data-stu-id="33d28-138">For example, the entry might resemble the following for a DLL deployed to the report server bin directory:</span></span>  
  
    ```  
    <Extension Name="MyNETDataProvider" Type="CompanyName.ExtensionName.DataProviderConnectionClass, DataProviderAssembly" />   
    ```  
  
     <span data-ttu-id="33d28-139">Se si carica l'assembly nella Global Assembly Cache (GAC), è necessario impostare le proprietà del nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="33d28-139">If you load your assembly into the global assembly cache (GAC), you must provide the strong name properties.</span></span> <span data-ttu-id="33d28-140">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="33d28-140">For example:</span></span>  
  
    ```  
    <Extension Name="MyNETDataProvider" Type="CompanyName.ExtensionName.DataProviderConnectionClass, DataProviderAssembly,Version=1.0.0.0, Culture=neutral, PublicKeyToken=MyPublicToken"/>  
    ```  
  
#### <a name="to-set-the-code-group-policy-for-a-net-data-provider"></a><span data-ttu-id="33d28-141">Per impostare criteri di gruppo di codice per un provider di dati .NET.</span><span class="sxs-lookup"><span data-stu-id="33d28-141">To set the code group policy for a .NET data provider</span></span>  
  
1.  <span data-ttu-id="33d28-142">Eseguire una copia di backup del file rssrvpolicy.config nella directory padre di ReportServer per bin.</span><span class="sxs-lookup"><span data-stu-id="33d28-142">Make a backup copy of the rssrvpolicy.config file in the ReportServer parent directory for bin.</span></span>  
  
2.  <span data-ttu-id="33d28-143">Aprire rssrvpolicy.config. È possibile aprire il file di configurazione con [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] o con un semplice editor di testo, ad esempio Blocco note.</span><span class="sxs-lookup"><span data-stu-id="33d28-143">Open rssrvpolicy.config. You can open the configuration file with [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] or a simple text editor such as Notepad.</span></span>  
  
3.  <span data-ttu-id="33d28-144">Individuare l'elemento `CodeGroup` nel file rssrvpolicy.config.</span><span class="sxs-lookup"><span data-stu-id="33d28-144">Locate the `CodeGroup` element in the rssrvpolicy.config file.</span></span>  
  
4.  <span data-ttu-id="33d28-145">Aggiungere un gruppo di codice relativo all'assembly del provider di dati che assegni l'autorizzazione `FullTrust`.</span><span class="sxs-lookup"><span data-stu-id="33d28-145">Add a code group for the data provider assembly that grants `FullTrust` permission.</span></span> <span data-ttu-id="33d28-146">Il gruppo di codice potrà avere l'aspetto seguente:</span><span class="sxs-lookup"><span data-stu-id="33d28-146">Your code group might resemble the following:</span></span>  
  
    ```  
    <CodeGroup class="UnionCodeGroup"  
       version="1"  
       PermissionSetName="FullTrust"  
       Name="ThisDataProviderCodeGroup"  
       Description="Code group for the .NET data provider">  
          <IMembershipCondition class="UrlMembershipCondition"  
             version="1"  
             Url=  
    "C:\Program Files\Microsoft SQL Server\MSRS10_50.MSSQLSERVER\Reporting Services\ReportServer\bin\DataProviderAssembly.dll"  
           />  
    </CodeGroup>  
    ```  
  
 <span data-ttu-id="33d28-147">L'appartenenza URL è solo una delle diverse condizioni di appartenenza selezionabili per il provider di dati.</span><span class="sxs-lookup"><span data-stu-id="33d28-147">URL membership is only one of many membership conditions you might select for the data provider.</span></span>  
  
### <a name="verifying-the-deployment-and-registration"></a><span data-ttu-id="33d28-148">Verifica della distribuzione e della registrazione</span><span class="sxs-lookup"><span data-stu-id="33d28-148">Verifying the Deployment and Registration</span></span>  
 <span data-ttu-id="33d28-149">È possibile verificare se la distribuzione del provider di dati nel server di report ha avuto esito positivo aprendo Gestione report e controllando che sia incluso nell'elenco delle origini dati disponibili.</span><span class="sxs-lookup"><span data-stu-id="33d28-149">You can verify whether the data provider was deployed successfully to the report server by opening Report Manager and verifying that the data provider is included in the list of available data sources.</span></span> <span data-ttu-id="33d28-150">Per altre informazioni su Gestione report e sulle origini dati, vedere [Creare, modificare ed eliminare origini dati condivise &#40;SSRS&#41;](create-modify-and-delete-shared-data-sources-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="33d28-150">For more information about Report Manager and data sources, see [Create, Modify, and Delete Shared Data Sources &#40;SSRS&#41;](create-modify-and-delete-shared-data-sources-ssrs.md).</span></span>  
  
## <a name="registering-a-net-framework-data-provider-on-the-report-designer-client"></a><span data-ttu-id="33d28-151">Registrazione di un provider di dati .NET Framework nel client di Progettazione report</span><span class="sxs-lookup"><span data-stu-id="33d28-151">Registering a .NET Framework Data Provider on the Report Designer Client</span></span>  
 <span data-ttu-id="33d28-152">Per creare report che utilizzino il provider di dati [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] per un'origine dei dati, è necessario installare l'assembly nel computer client che esegue Progettazione report.</span><span class="sxs-lookup"><span data-stu-id="33d28-152">In order to author reports that use this [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] data provider for a data source, you must install the assembly on your client computer that runs Report Designer.</span></span> <span data-ttu-id="33d28-153">È necessario modificare due file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="33d28-153">You must modify two configuration files.</span></span> <span data-ttu-id="33d28-154">Modificare RSReportDesigner.config per registrare il provider di dati come origine dei dati e per utilizzare la finestra Progettazione query standard.</span><span class="sxs-lookup"><span data-stu-id="33d28-154">Modify RSReportDesigner.config to register the data provider as a data source and to use the generic query designer.</span></span> <span data-ttu-id="33d28-155">Modificare RSPreviewPolicy.config per assegnare autorizzazioni di sicurezza dell'accesso al codice per l'assembly del provider di dati.</span><span class="sxs-lookup"><span data-stu-id="33d28-155">Modify RSPreviewPolicy.config to grant code access security permissions for the data provider assembly.</span></span>  
  
#### <a name="to-install-a-data-provider-assembly-on-the-report-designer-client"></a><span data-ttu-id="33d28-156">Per installare l'assembly di un provider di dati nel client di Progettazione report</span><span class="sxs-lookup"><span data-stu-id="33d28-156">To install a data provider assembly on the Report Designer client</span></span>  
  
1.  <span data-ttu-id="33d28-157">Accedere al percorso predefinito della directory PrivateAssemblies nel client di Progettazione report in cui si vuole usare il provider di dati [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="33d28-157">Navigate to the default location of the PrivateAssemblies directory on the Report Designer client on which you want to use the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] data provider.</span></span> <span data-ttu-id="33d28-158">Il percorso predefinito della directory PrivateAssemblies è *\<drive>* : \Programmi\microsoft Visual Studio 9.0 \ Common7\IDE\PrivateAssemblies.</span><span class="sxs-lookup"><span data-stu-id="33d28-158">The default location of the PrivateAssemblies directory is *\<drive>*:\Program Files\Microsoft Visual Studio 9.0\Common7\IDE\PrivateAssemblies.</span></span>  
  
2.  <span data-ttu-id="33d28-159">Copiare l'assembly dal percorso di gestione temporanea nella directory PrivateAssemblies del client di Progettazione report.</span><span class="sxs-lookup"><span data-stu-id="33d28-159">Copy your assembly from your staging location to the PrivateAssemblies directory of the Report Designer client.</span></span> <span data-ttu-id="33d28-160">In alternativa, è possibile caricare l'assembly nella Global Assembly Cache (GAC).</span><span class="sxs-lookup"><span data-stu-id="33d28-160">Alternatively, you can load your assembly in the global assembly cache (GAC).</span></span> <span data-ttu-id="33d28-161">Per altre informazioni, vedere [Utilizzo di assembly e della Global Assembly Cache](https://go.microsoft.com/fwlink/?linkid=63912) nella documentazione di [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] SDK in MSDN.</span><span class="sxs-lookup"><span data-stu-id="33d28-161">For more information, see [Working with Assemblies and the Global Assembly Cache](https://go.microsoft.com/fwlink/?linkid=63912) in the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] SDK documentation on MSDN.</span></span>  
  
#### <a name="to-register-a-net-data-provider-on-the-report-designer-client"></a><span data-ttu-id="33d28-162">Per registrare un provider di dati .NET nel client di Progettazione report</span><span class="sxs-lookup"><span data-stu-id="33d28-162">To register a .NET data provider on the Report Designer client</span></span>  
  
1.  <span data-ttu-id="33d28-163">Eseguire una copia di backup del file RSReportDesigner.config nella directory PrivateAssemblies.</span><span class="sxs-lookup"><span data-stu-id="33d28-163">Make a backup copy of the RSReportDesigner.config file in the PrivateAssemblies directory.</span></span>  
  
2.  <span data-ttu-id="33d28-164">Aprire RSReportDesigner.config con [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] o con un semplice editor di testo, ad esempio Blocco note.</span><span class="sxs-lookup"><span data-stu-id="33d28-164">Open RSReportDesigner.config with [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] or a simple text editor such as Notepad.</span></span>  
  
3.  <span data-ttu-id="33d28-165">Individuare l'elemento `Data` nel file RSReportDesigner.config.</span><span class="sxs-lookup"><span data-stu-id="33d28-165">Locate the `Data` element in the RSReportDesigner.config file.</span></span> <span data-ttu-id="33d28-166">Una voce relativa al provider di dati dovrà essere inserita nella posizione seguente:</span><span class="sxs-lookup"><span data-stu-id="33d28-166">An entry for the data provider should be made in the following location:</span></span>  
  
    ```  
    <Extensions>  
       <Data>  
          <Extension Your data provider configuration information goes here />  
       </Data>  
    </Extensions>  
    ```  
  
4.  <span data-ttu-id="33d28-167">Aggiungere una voce per il provider di dati.</span><span class="sxs-lookup"><span data-stu-id="33d28-167">Add an entry for the data provider.</span></span>  
  
    |<span data-ttu-id="33d28-168">Attributo</span><span class="sxs-lookup"><span data-stu-id="33d28-168">Attribute</span></span>|<span data-ttu-id="33d28-169">Descrizione</span><span class="sxs-lookup"><span data-stu-id="33d28-169">Description</span></span>|  
    |---------------|-----------------|  
    |`Name`|<span data-ttu-id="33d28-170">Specificare un nome univoco per il provider di dati, ad esempio **ProviderDatiNET**.</span><span class="sxs-lookup"><span data-stu-id="33d28-170">Provide a unique name for the data provider, for example, **MyNETDataProvider**.</span></span> <span data-ttu-id="33d28-171">La lunghezza massima consentita per l'attributo `Name` è di 255 caratteri.</span><span class="sxs-lookup"><span data-stu-id="33d28-171">The maximum length for the `Name` attribute is 255 characters.</span></span> <span data-ttu-id="33d28-172">Il nome deve essere univoco all'interno di tutte le voci dell'elemento `Extension` di un file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="33d28-172">The name must be unique among all entries within the `Extension` element of a configuration file.</span></span> <span data-ttu-id="33d28-173">Il valore indicato qui viene inserito nell'elenco a discesa dei tipi di origini dei dati per la creazione di una nuova origine.</span><span class="sxs-lookup"><span data-stu-id="33d28-173">The value that you include here appears in the drop-down list of data source types when you create a new data source.</span></span>|  
    |`Type`|<span data-ttu-id="33d28-174">Immettere un elenco delimitato da virgole che includa lo spazio dei nomi completo della classe che implementa l'interfaccia <xref:System.Data.IDbConnection> , seguito dal nome dell'assembly del provider di dati [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] , senza l'estensione dll.</span><span class="sxs-lookup"><span data-stu-id="33d28-174">Enter a comma-separated list that includes the fully qualified namespace of the class that implements the <xref:System.Data.IDbConnection> interface, followed by the name of the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] data provider assembly (not including the .dll file name extension).</span></span>|  
  
     <span data-ttu-id="33d28-175">Ad esempio, la voce per una DLL distribuita nella directory PrivateAssemblies di [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] può essere simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="33d28-175">For example, the entry might resemble the following for a DLL deployed to the [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] PrivateAssemblies directory:</span></span>  
  
    ```  
    <Extension Name="MyNETDataProvider" Type="CompanyName.ExtensionName.DataProviderConnectionClass, DataProviderAssembly" />   
    ```  
  
     <span data-ttu-id="33d28-176">Se si carica l'assembly nella cache di assembly globale (CAG), è necessario impostare le proprietà del nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="33d28-176">If you load your assembly into the GAC, you must provide the strong name properties.</span></span> <span data-ttu-id="33d28-177">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="33d28-177">For example:</span></span>  
  
    ```  
    <Extension Name="MyNETDataProvider" Type="CompanyName.ExtensionName.DataProviderConnectionClass, DataProviderAssembly, Version=1.0.0.0, Culture=neutral, PublicKeyToken=MyPublicToken"/>  
    ```  
  
5.  <span data-ttu-id="33d28-178">Individuare l'elemento `Designer` nel file RSReportDesigner.config.</span><span class="sxs-lookup"><span data-stu-id="33d28-178">Locate the `Designer` element in the RSReportDesigner.config file.</span></span> <span data-ttu-id="33d28-179">Una voce relativa al provider di dati [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] dovrà essere inserita nella posizione seguente:</span><span class="sxs-lookup"><span data-stu-id="33d28-179">An entry for the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] data provider should be made in the following location:</span></span>  
  
    ```  
    <Extensions>  
       <Designer>  
          <Your data provider configuration information goes here>  
       </Designer>  
    </Extensions>  
    ```  
  
6.  <span data-ttu-id="33d28-180">Aggiungere la voce seguente al file RSReportDesigner.config nell'elemento `Designer`.</span><span class="sxs-lookup"><span data-stu-id="33d28-180">Add the following entry to the RSReportDesigner.config file under the `Designer` element.</span></span> <span data-ttu-id="33d28-181">È necessario sostituire solo l'attributo `Name` con il nome specificato nelle voci precedenti.</span><span class="sxs-lookup"><span data-stu-id="33d28-181">You need to replace only the `Name` attribute with the name that you provided in previous entries.</span></span>  
  
    ```  
    <Extension Name="MyNETDataProvider" Type="Microsoft.ReportingServices.QueryDesigners.GenericQueryDesigner,Microsoft.ReportingServices.QueryDesigners"/>  
    ```  
  
#### <a name="to-set-the-code-group-policy-for-a-net-data-provider-on-the-report-designer-client"></a><span data-ttu-id="33d28-182">Per impostare criteri di gruppo di codice per un provider di dati .NET nel client di Progettazione report</span><span class="sxs-lookup"><span data-stu-id="33d28-182">To set the code group policy for a .NET data provider on the Report Designer client</span></span>  
  
1.  <span data-ttu-id="33d28-183">Eseguire una copia di backup del file RSPreviewPolicy.config file nella directory PrivateAssemblies.</span><span class="sxs-lookup"><span data-stu-id="33d28-183">Make a backup copy of the RSPreviewPolicy.config file in the PrivateAssemblies directory.</span></span>  
  
2.  <span data-ttu-id="33d28-184">Aprire RSPreviewPolicy.config con [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] o con un semplice editor di testo, ad esempio il Blocco note.</span><span class="sxs-lookup"><span data-stu-id="33d28-184">Open RSPreviewPolicy.config with [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] or a simple text editor, such as Notepad.</span></span>  
  
3.  <span data-ttu-id="33d28-185">Individuare l'elemento `CodeGroup` nel file RSPreviewPolicy.config.</span><span class="sxs-lookup"><span data-stu-id="33d28-185">Locate the `CodeGroup` element in the RSPreviewPolicy.config file.</span></span>  
  
4.  <span data-ttu-id="33d28-186">Aggiungere un gruppo di codice relativo all'assembly del provider di dati [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] che assegni l'autorizzazione `FullTrust`.</span><span class="sxs-lookup"><span data-stu-id="33d28-186">Add a code group for the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] data provider assembly that grants `FullTrust` permission.</span></span> <span data-ttu-id="33d28-187">Il gruppo di codice potrà avere l'aspetto seguente:</span><span class="sxs-lookup"><span data-stu-id="33d28-187">Your code group might resemble the following:</span></span>  
  
    ```  
    <CodeGroup class="UnionCodeGroup"  
       version="1"  
       PermissionSetName="FullTrust"  
       Name="ThisDataProviderCodeGroup"  
       Description="Code group for the .NET data provider">  
          <IMembershipCondition class="UrlMembershipCondition"  
             version="1"  
             Url=  
    " C:\Program Files\Microsoft Visual Studio 9\Common7\IDE\PrivateAssemblies\DataProviderAssembly.dll"  
           />  
    </CodeGroup>  
    ```  
  
 <span data-ttu-id="33d28-188">L'appartenenza URL è solo una delle diverse condizioni di appartenenza selezionabili per il provider di dati.</span><span class="sxs-lookup"><span data-stu-id="33d28-188">URL membership is only one of many membership conditions you might select for the data provider.</span></span>  
  
### <a name="verifying-the-deployment-and-registration-on-the-report-designer-client"></a><span data-ttu-id="33d28-189">Verifica della distribuzione e della registrazione nel client di Progettazione report</span><span class="sxs-lookup"><span data-stu-id="33d28-189">Verifying the Deployment and Registration on the Report Designer Client</span></span>  
 <span data-ttu-id="33d28-190">Per poter verificare la distribuzione, è necessario chiudere tutte le istanze di [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="33d28-190">Before you can verify deployment, you must close all instances of [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] on your local computer.</span></span> <span data-ttu-id="33d28-191">Dopo aver chiuso tutte le sessioni correnti, è possibile verificare se la distribuzione del provider di dati in Progettazione report è riuscita creando un nuovo progetto di report in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="33d28-191">After you have ended all current sessions, you can verify whether your data provider was deployed successfully to Report Designer by creating a new report project in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span></span> <span data-ttu-id="33d28-192">Quando si crea un nuovo set di dati per il report il provider di dati dovrebbe essere incluso nell'elenco dei tipi di origini dei dati disponibili.</span><span class="sxs-lookup"><span data-stu-id="33d28-192">The data provider should be included in the list of available data source types when you create a new data set for your report.</span></span>  
  
## <a name="platform-considerations"></a><span data-ttu-id="33d28-193">Considerazioni relative alla piattaforma</span><span class="sxs-lookup"><span data-stu-id="33d28-193">Platform Considerations</span></span>  
 <span data-ttu-id="33d28-194">In una piattaforma a 64 bit (x64) [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)] viene eseguito in modalità WOW a 32 bit.</span><span class="sxs-lookup"><span data-stu-id="33d28-194">On a 64-bit (x64) platform, [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)] runs in 32-bit WOW mode.</span></span> <span data-ttu-id="33d28-195">Quando si creano report su una piattaforma x64, per visualizzarne l'anteprima è necessario che i provider di dati a 32 bit siano installati nel client per la creazione di report.</span><span class="sxs-lookup"><span data-stu-id="33d28-195">When you author reports on an x64 platform, you need 32-bit data providers installed on the report authoring client in order to preview your reports.</span></span> <span data-ttu-id="33d28-196">Se si pubblica il report sul medesimo sistema, per poterlo visualizzare in Gestione report saranno necessari i provider di dati x64.</span><span class="sxs-lookup"><span data-stu-id="33d28-196">If you publish the report on the same system, you need x64 data providers to view the report with Report Manager.</span></span>  
  
 [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)] <span data-ttu-id="33d28-197">non è supportato per le piattaforme con processore [!INCLUDE[vcpritanium](../../includes/vcpritanium-md.md)].</span><span class="sxs-lookup"><span data-stu-id="33d28-197">is not supported for [!INCLUDE[vcpritanium](../../includes/vcpritanium-md.md)]-based platforms.</span></span>  
  
 <span data-ttu-id="33d28-198">Le estensioni per l'elaborazione dati installate con [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] devono essere compilate in modo nativo per ogni piattaforma e installate nei percorsi corretti.</span><span class="sxs-lookup"><span data-stu-id="33d28-198">The data processing extensions that are installed with [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] must be compiled natively for each platform and installed in the correct locations.</span></span> <span data-ttu-id="33d28-199">Se si registra un provider di dati personalizzato o un provider di dati [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] standard, sarà necessario compilarlo in modo nativo per la piattaforma appropriata e installarlo nei percorsi adeguati.</span><span class="sxs-lookup"><span data-stu-id="33d28-199">If you register a custom data provider or a standard [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] data provider, it needs to be compiled natively for the appropriate platform and installed the appropriate locations.</span></span> <span data-ttu-id="33d28-200">Se si esegue una piattaforma a 32 bit, il provider di dati deve essere compilato per tale tipo di piattaforma.</span><span class="sxs-lookup"><span data-stu-id="33d28-200">If you are running on a 32-bit platform, the data provider must be compiled for a 32-bit platform.</span></span> <span data-ttu-id="33d28-201">Se si esegue una piattaforma a 64 bit, il provider di dati deve essere invece compilato di conseguenza per tale tipo di piattaforma.</span><span class="sxs-lookup"><span data-stu-id="33d28-201">If you are running on a 64-bit platform, the data provider must be compiled for the 64-bit platform.</span></span> <span data-ttu-id="33d28-202">Non è possibile utilizzare un provider di dati a 32 bit di cui è stato eseguito il wrapping con interfacce a 64 bit su una piattaforma a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="33d28-202">You cannot use a 32-bit data provider wrapped with 64-bit interfaces on a 64 bit platform.</span></span> <span data-ttu-id="33d28-203">Per informazioni relative al funzionamento del provider di dati sulla piattaforma installata, vedere la documentazione del software di terze parti.</span><span class="sxs-lookup"><span data-stu-id="33d28-203">Check your third-party software for information about whether the data provider will work on the installed platform.</span></span> <span data-ttu-id="33d28-204">Per altre informazioni sui provider di dati e sulle piattaforme supportate, vedere [Origini dati supportate da Reporting Services &#40;SSRS&#41;](../create-deploy-and-manage-mobile-and-paginated-reports.md).</span><span class="sxs-lookup"><span data-stu-id="33d28-204">For more information about data providers and platform support, see [Data Sources Supported by Reporting Services &#40;SSRS&#41;](../create-deploy-and-manage-mobile-and-paginated-reports.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33d28-205">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="33d28-205">See Also</span></span>  
 <span data-ttu-id="33d28-206">[Configurare e amministrare un server di report &#40;modalità nativa SSRS&#41;](../report-server/configure-and-administer-a-report-server-ssrs-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="33d28-206">[Configure and Administer a Report Server &#40;SSRS Native Mode&#41;](../report-server/configure-and-administer-a-report-server-ssrs-native-mode.md) </span></span>  
 <span data-ttu-id="33d28-207">[Implementazione di un'estensione per l'elaborazione dati](../extensions/data-processing/implementing-a-data-processing-extension.md) </span><span class="sxs-lookup"><span data-stu-id="33d28-207">[Implementing a Data Processing Extension](../extensions/data-processing/implementing-a-data-processing-extension.md) </span></span>  
 <span data-ttu-id="33d28-208">[File di configurazione di Reporting Services](../report-server/reporting-services-configuration-files.md) </span><span class="sxs-lookup"><span data-stu-id="33d28-208">[Reporting Services Configuration Files](../report-server/reporting-services-configuration-files.md) </span></span>  
 [<span data-ttu-id="33d28-209">Sicurezza dall'accesso di codice in Reporting Services</span><span class="sxs-lookup"><span data-stu-id="33d28-209">Code Access Security in Reporting Services</span></span>](../extensions/secure-development/code-access-security-in-reporting-services.md)  
  
  
