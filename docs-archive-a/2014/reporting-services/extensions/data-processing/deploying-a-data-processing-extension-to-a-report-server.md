---
title: "Procedura: Distribuire un'estensione per l'elaborazione dati in un server di report | Microsoft Docs"
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- data processing extensions [Reporting Services], deploying
- assemblies [Reporting Services], data processing extension deployments
ms.assetid: e00dface-70f8-434b-9763-8ebee18737d2
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d606096b9f2060d3cf5b9cea1f95a5345e592383
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725295"
---
# <a name="how-to-deploy-a-data-processing-extension-to-a-report-server"></a><span data-ttu-id="f6092-102">Procedura: Distribuire un'estensione per l'elaborazione dati in un server di report</span><span class="sxs-lookup"><span data-stu-id="f6092-102">How to: Deploy a Data Processing Extension to a Report Server</span></span>
  <span data-ttu-id="f6092-103">I server di report utilizzano le estensioni per l'elaborazione dati per il recupero e l'elaborazione di dati nei report visualizzabili.</span><span class="sxs-lookup"><span data-stu-id="f6092-103">Report servers use data processing extensions for retrieving and processing data in rendered reports.</span></span> <span data-ttu-id="f6092-104">È necessario distribuire l'assembly dell'estensione per l'elaborazione dati in un server di report come assembly privato.</span><span class="sxs-lookup"><span data-stu-id="f6092-104">You should deploy your data processing extension assembly to a report server as a private assembly.</span></span> <span data-ttu-id="f6092-105">È inoltre necessario creare una voce nel file di configurazione del server di report, ovvero RSReportServer.config.</span><span class="sxs-lookup"><span data-stu-id="f6092-105">You also need to make an entry in the report server configuration file, RSReportServer.config.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="f6092-106">Procedure</span><span class="sxs-lookup"><span data-stu-id="f6092-106">Procedures</span></span>  
  
#### <a name="to-deploy-a-data-processing-extension-assembly"></a><span data-ttu-id="f6092-107">Per distribuire un assembly dell'estensione per l'elaborazione dati</span><span class="sxs-lookup"><span data-stu-id="f6092-107">To deploy a data processing extension assembly</span></span>  
  
1.  <span data-ttu-id="f6092-108">Copiare l'assembly dal percorso di gestione temporanea nella directory bin del server di report in cui si desidera utilizzare l'estensione per l'elaborazione dati.</span><span class="sxs-lookup"><span data-stu-id="f6092-108">Copy your assembly from your staging location to the bin directory of the report server on which you want to use the data processing extension.</span></span> <span data-ttu-id="f6092-109">Il percorso predefinito della directory bin del server di report è%Programmi%\Microsoft SQL Server \ MSRS10_50. \<*Instance Name*> Services\ReportServer\bin. \Reporting</span><span class="sxs-lookup"><span data-stu-id="f6092-109">The default location of the report server bin directory is %ProgramFiles%\Microsoft SQL Server\MSRS10_50.\<*Instance Name*>\Reporting Services\ReportServer\bin.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f6092-110">Con questo passaggio viene evitato l'aggiornamento a un'istanza di SQL Server più recente.</span><span class="sxs-lookup"><span data-stu-id="f6092-110">This step will prevent an upgrade to a newer instance of SQL Server.</span></span> <span data-ttu-id="f6092-111">Per ulteriori informazioni, vedere [Upgrade and Migrate Reporting Services](../../install-windows/upgrade-and-migrate-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="f6092-111">For more information, see [Upgrade and Migrate Reporting Services](../../install-windows/upgrade-and-migrate-reporting-services.md).</span></span>  
  
2.  <span data-ttu-id="f6092-112">Dopo aver copiato il file di assembly, aprire il file RSReportServer.config</span><span class="sxs-lookup"><span data-stu-id="f6092-112">After the assembly file is copied, open the RSReportServer.config file.</span></span> <span data-ttu-id="f6092-113">che si trova nella directory ReportServer.</span><span class="sxs-lookup"><span data-stu-id="f6092-113">The RSReportServer.config file is located in the ReportServer directory.</span></span> <span data-ttu-id="f6092-114">È necessario immettere una voce nel file di configurazione per il file di assembly dell'estensione per l'elaborazione dati.</span><span class="sxs-lookup"><span data-stu-id="f6092-114">You need to make an entry in the configuration file for your data processing extension assembly file.</span></span> <span data-ttu-id="f6092-115">È possibile aprire il file di configurazione in Visual Studio o in un semplice editor di testo, ad esempio Blocco note.</span><span class="sxs-lookup"><span data-stu-id="f6092-115">You can open the configuration file with Visual Studio or a simple text editor, such as Notepad.</span></span>  
  
3.  <span data-ttu-id="f6092-116">Individuare l'elemento `Data` nel file RSReportServer.config.</span><span class="sxs-lookup"><span data-stu-id="f6092-116">Locate the `Data` element in the RSReportServer.config file.</span></span> <span data-ttu-id="f6092-117">È necessario immettere una voce per l'estensione per l'elaborazione dati appena creata nel percorso seguente:</span><span class="sxs-lookup"><span data-stu-id="f6092-117">An entry for your newly created data processing extension should be made in the following location:</span></span>  
  
    ```  
    <Extensions>  
       <Data>  
          <Your extension configuration information goes here>  
       </Data>  
    </Extensions>  
    ```  
  
4.  <span data-ttu-id="f6092-118">Aggiungere una voce per l'estensione per l'elaborazione dati.</span><span class="sxs-lookup"><span data-stu-id="f6092-118">Add an entry for your data processing extension.</span></span> <span data-ttu-id="f6092-119">La voce deve includere un elemento `Extension` con valori per `Name` e `Type` e può essere simile a quanto riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="f6092-119">Your entry should include an `Extension` element with values for `Name` and `Type` and might look like the following:</span></span>  
  
    ```  
    <Extension Name="ExtensionName" Type="CompanyName.ExtensionName.MyConnectionClass, MyExtensionAssembly" />  
    ```  
  
     <span data-ttu-id="f6092-120">Il valore per `Name` è il nome univoco dell'estensione per l'elaborazione dati.</span><span class="sxs-lookup"><span data-stu-id="f6092-120">The value for `Name` is the unique name of the data processing extension.</span></span> <span data-ttu-id="f6092-121">Il valore per `Type` è un elenco delimitato da virgole che include una voce per lo spazio dei nomi completo della classe che implementa le interfacce <xref:Microsoft.ReportingServices.Interfaces.IExtension> e <xref:Microsoft.ReportingServices.DataProcessing.IDbConnection>, seguito dal nome dell'assembly, senza l'estensione dll.</span><span class="sxs-lookup"><span data-stu-id="f6092-121">The value for `Type` is a comma-separated list that includes an entry for the fully qualified namespace of your class that implements the <xref:Microsoft.ReportingServices.Interfaces.IExtension> and <xref:Microsoft.ReportingServices.DataProcessing.IDbConnection> interfaces, followed by the name of your assembly (not including the .dll file extension).</span></span> <span data-ttu-id="f6092-122">Per impostazione predefinita, le estensioni per l'elaborazione dati sono visibili.</span><span class="sxs-lookup"><span data-stu-id="f6092-122">By default, data processing extensions are visible.</span></span> <span data-ttu-id="f6092-123">Per nascondere un'estensione dalle interfacce utente, come Gestione report, aggiungere un attributo `Visible` all'elemento `Extension` e impostarlo su `false`.</span><span class="sxs-lookup"><span data-stu-id="f6092-123">To hide an extension from user interfaces, such as Report Manager, add a `Visible` attribute to the `Extension` element, and set it to `false`.</span></span>  
  
5.  <span data-ttu-id="f6092-124">Aggiungere un gruppo di codice per l'assembly personalizzato che conceda l'autorizzazione `FullTrust` per l'estensione.</span><span class="sxs-lookup"><span data-stu-id="f6092-124">Add a code group for your custom assembly that grants `FullTrust` permission for your extension.</span></span> <span data-ttu-id="f6092-125">A tale scopo, aggiungere il gruppo di codice al file rssrvpolicy.config che si trova per impostazione predefinita in%programmi%\Microsoft SQL Server \\<MSRS10_50. \<*Instance Name*> Services\ReportServer. \Reporting</span><span class="sxs-lookup"><span data-stu-id="f6092-125">You do this by adding the code group to the rssrvpolicy.config file located by default in %ProgramFiles%\Microsoft SQL Server\\<MSRS10_50.\<*Instance Name*>\Reporting Services\ReportServer.</span></span> <span data-ttu-id="f6092-126">Il gruppo di codice può essere simile a quanto riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="f6092-126">Your code group might look like the following:</span></span>  
  
    ```  
    <CodeGroup class="UnionCodeGroup"  
       version="1"  
       PermissionSetName="FullTrust"  
       Name="MyExtensionCodeGroup"  
       Description="Code group for my data processing extension">  
          <IMembershipCondition class="UrlMembershipCondition"  
             version="1"  
             Url="C:\Program Files\Microsoft SQL Server\MSRS10_50.<Instance Name>\Reporting Services\ReportServer\bin\MyExtensionAssembly.dll"  
           />  
    </CodeGroup>  
    ```  
  
 <span data-ttu-id="f6092-127">L'appartenenza URL è solo una delle diverse condizioni di appartenenza selezionabili per l'estensione per l'elaborazione dati.</span><span class="sxs-lookup"><span data-stu-id="f6092-127">URL membership is only one of many membership conditions you might choose for your data processing extension.</span></span> <span data-ttu-id="f6092-128">Per altre informazioni sulla sicurezza dall'accesso di codice in [!INCLUDE[ssCurrentUI](../../../includes/sscurrentui-md.md)] [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)], vedere [Sviluppo sicuro &#40;Reporting Services&#41;](../secure-development/secure-development-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="f6092-128">For more information about code access security in [!INCLUDE[ssCurrentUI](../../../includes/sscurrentui-md.md)] [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)], see [Secure Development &#40;Reporting Services&#41;](../secure-development/secure-development-reporting-services.md).</span></span>  
  
## <a name="verifying-the-deployment"></a><span data-ttu-id="f6092-129">Verifica della distribuzione</span><span class="sxs-lookup"><span data-stu-id="f6092-129">Verifying the Deployment</span></span>  
 <span data-ttu-id="f6092-130">È possibile verificare se l'estensione per l'elaborazione dati è stata distribuita correttamente nel server di report tramite il metodo <xref:ReportService2010.ReportingService2010.ListExtensions%2A> del servizio Web.</span><span class="sxs-lookup"><span data-stu-id="f6092-130">You can verify whether your data processing extension was deployed successfully to the report server by using the Web service <xref:ReportService2010.ReportingService2010.ListExtensions%2A> method.</span></span> <span data-ttu-id="f6092-131">È inoltre possibile aprire Gestione report e verificare che l'estensione sia inclusa nell'elenco delle origini dati disponibili.</span><span class="sxs-lookup"><span data-stu-id="f6092-131">You can also open Report Manager and verify that your extension is included in the list of available data sources.</span></span> <span data-ttu-id="f6092-132">Per altre informazioni su Gestione report e sulle origini dati, vedere [Creare, modificare ed eliminare origini dati condivise &#40;SSRS&#41;](../../report-data/create-modify-and-delete-shared-data-sources-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="f6092-132">For more information about Report Manager and data sources, see [Create, Modify, and Delete Shared Data Sources &#40;SSRS&#41;](../../report-data/create-modify-and-delete-shared-data-sources-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6092-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f6092-133">See Also</span></span>  
 <span data-ttu-id="f6092-134">[Distribuzione di un'estensione per l'elaborazione dati](deploying-a-data-processing-extension.md) </span><span class="sxs-lookup"><span data-stu-id="f6092-134">[Deploying a Data Processing Extension](deploying-a-data-processing-extension.md) </span></span>  
 <span data-ttu-id="f6092-135">[Estensioni di Reporting Services](../reporting-services-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="f6092-135">[Reporting Services Extensions](../reporting-services-extensions.md) </span></span>  
 <span data-ttu-id="f6092-136">[Implementazione di un'estensione per l'elaborazione dati](implementing-a-data-processing-extension.md) </span><span class="sxs-lookup"><span data-stu-id="f6092-136">[Implementing a Data Processing Extension](implementing-a-data-processing-extension.md) </span></span>  
 [<span data-ttu-id="f6092-137">Libreria di estensioni di Reporting Services</span><span class="sxs-lookup"><span data-stu-id="f6092-137">Reporting Services Extension Library</span></span>](../reporting-services-extension-library.md)  
  
  
