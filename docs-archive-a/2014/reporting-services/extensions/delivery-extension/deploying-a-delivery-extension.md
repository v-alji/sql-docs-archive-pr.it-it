---
title: Distribuzione di un'estensione per il recapito | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- delivery extensions [Reporting Services], deploying
- Extension element
- deploying [Reporting Services], extensions
ms.assetid: 4436ce48-397d-42c7-9b5d-2a267e2a1b2c
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f4a4e33266c8d3a27ce2a4ab5f568bdee349720f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87638301"
---
# <a name="deploying-a-delivery-extension"></a><span data-ttu-id="a13ba-102">Distribuzione di un'estensione per il recapito</span><span class="sxs-lookup"><span data-stu-id="a13ba-102">Deploying a Delivery Extension</span></span>
  <span data-ttu-id="a13ba-103">Le estensioni per il recapito forniscono le informazioni di configurazione in un file di configurazione XML.</span><span class="sxs-lookup"><span data-stu-id="a13ba-103">Delivery extensions supply their configuration information in the form of an XML configuration file.</span></span> <span data-ttu-id="a13ba-104">Il file XML è conforme all'elemento XML Schema definito per le estensioni per il recapito.</span><span class="sxs-lookup"><span data-stu-id="a13ba-104">The XML file conforms to the XML schema defined for delivery extensions.</span></span> <span data-ttu-id="a13ba-105">Le estensioni per il recapito forniscono l'infrastruttura per l'impostazione e la modifica del file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="a13ba-105">Delivery extensions provide infrastructure for setting and modifying the configuration file.</span></span>  
  
 <span data-ttu-id="a13ba-106">Se un'estensione per il recapito viene sostituita o aggiornata, tutte le sottoscrizioni che fanno riferimento all'estensione per il recapito rimangono valide.</span><span class="sxs-lookup"><span data-stu-id="a13ba-106">If a delivery extension is replaced or upgraded, all subscriptions that reference the delivery extension remain valid.</span></span>  
  
 <span data-ttu-id="a13ba-107">Dopo avere scritto e compilato l'estensione per il recapito [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] in una libreria [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)], è necessario copiarla nella directory appropriata e aggiungere una voce al file di configurazione [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] appropriato, in modo che il server di report possa individuarla.</span><span class="sxs-lookup"><span data-stu-id="a13ba-107">After you have written and compiled your [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] delivery extension into a [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] library, you must copy the extension to the appropriate directory and add an entry to the appropriate [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] configuration file so the report server can locate it.</span></span>  
  
## <a name="configuration-file-extension-element"></a><span data-ttu-id="a13ba-108">Elemento Extension del file di configurazione</span><span class="sxs-lookup"><span data-stu-id="a13ba-108">Configuration-File Extension Element</span></span>  
 <span data-ttu-id="a13ba-109">Le estensioni per il recapito distribuite nel server di report devono essere immesse come elementi `Extension` nel file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="a13ba-109">Delivery extensions that you deploy to the report server need to be entered as `Extension` elements in the configuration file.</span></span> <span data-ttu-id="a13ba-110">Il file di configurazione per il server di report è RSReportServer.config.</span><span class="sxs-lookup"><span data-stu-id="a13ba-110">The configuration file for the report server is RSReportServer.config.</span></span>  
  
 <span data-ttu-id="a13ba-111">Nella tabella riportata di seguito vengono descritti gli attributi dell'elemento `Extension` per le estensioni per il recapito.</span><span class="sxs-lookup"><span data-stu-id="a13ba-111">The following table describes the attributes for the `Extension` element for delivery extensions.</span></span>  
  
|<span data-ttu-id="a13ba-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="a13ba-112">Attribute</span></span>|<span data-ttu-id="a13ba-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a13ba-113">Description</span></span>|  
|---------------|-----------------|  
|`Name`|<span data-ttu-id="a13ba-114">Nome univoco per l'estensione, ad esempio "Posta elettronica server di report" per l'estensione per il recapito tramite posta elettronica o "Condivisione file server di report" per l'estensione per il recapito tramite condivisione.</span><span class="sxs-lookup"><span data-stu-id="a13ba-114">A unique name for the extension (for example, "Report Server E-Mail" for the e-mail delivery extension or "Report Server FileShare" for the file share delivery extension).</span></span> <span data-ttu-id="a13ba-115">La lunghezza massima consentita per l'attributo `Name` è di 255 caratteri.</span><span class="sxs-lookup"><span data-stu-id="a13ba-115">The maximum length for the `Name` attribute is 255 characters.</span></span> <span data-ttu-id="a13ba-116">Il nome deve essere univoco all'interno di tutte le voci dell'elemento `Extension` di un file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="a13ba-116">The name must be unique among all entries within the `Extension` element of a configuration file.</span></span> <span data-ttu-id="a13ba-117">Se è presente un nome duplicato, il server di report restituirà un errore.</span><span class="sxs-lookup"><span data-stu-id="a13ba-117">If a duplicate name is present, the report server returns an error.</span></span>|  
|`Type`|<span data-ttu-id="a13ba-118">Elenco delimitato da virgole che include lo spazio dei nomi completo insieme al nome dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="a13ba-118">A comma-separated list that includes the fully qualified namespace along with the name of the assembly.</span></span>|  
|`Visible`|<span data-ttu-id="a13ba-119">Il valore `false` indica che l'estensione per il recapito non deve essere visibile nelle interfacce utente.</span><span class="sxs-lookup"><span data-stu-id="a13ba-119">A value of `false` indicates that the delivery extension should not be visible in user interfaces.</span></span> <span data-ttu-id="a13ba-120">Se l'attributo non è incluso, il valore predefinito è `true`.</span><span class="sxs-lookup"><span data-stu-id="a13ba-120">If the attribute is not included, the default value is `true`.</span></span>|  
  
 <span data-ttu-id="a13ba-121">Per altre informazioni sul file RSReportServer.config, vedere [File di configurazione di Reporting Services](../../report-server/reporting-services-configuration-files.md).</span><span class="sxs-lookup"><span data-stu-id="a13ba-121">For more information about the RSReportServer.config file, see [Reporting Services Configuration Files](../../report-server/reporting-services-configuration-files.md).</span></span>  
  
## <a name="deploying-the-extension-to-the-report-server"></a><span data-ttu-id="a13ba-122">Distribuzione dell'estensione nel server di report</span><span class="sxs-lookup"><span data-stu-id="a13ba-122">Deploying the Extension to the Report Server</span></span>  
 <span data-ttu-id="a13ba-123">Il server di report utilizza estensioni per il recapito per l'elaborazione e il recapito di notifiche o report.</span><span class="sxs-lookup"><span data-stu-id="a13ba-123">The report server uses delivery extensions for processing and delivering notifications or reports.</span></span> <span data-ttu-id="a13ba-124">È necessario distribuire l'assembly di estensioni per il recapito in un server di report come assembly privato.</span><span class="sxs-lookup"><span data-stu-id="a13ba-124">You should deploy your delivery extension assembly to the report server as a private assembly.</span></span> <span data-ttu-id="a13ba-125">È inoltre necessario creare una voce nel file di configurazione del server di report, ovvero RSReportServer.config.</span><span class="sxs-lookup"><span data-stu-id="a13ba-125">You also need to make an entry in the report server configuration file, RSReportServer.config.</span></span>  
  
#### <a name="to-deploy-a-deliver-extension-assembly-to-a-report-server"></a><span data-ttu-id="a13ba-126">Per distribuire un assembly di estensioni per il recapito in un server di report</span><span class="sxs-lookup"><span data-stu-id="a13ba-126">To deploy a deliver extension assembly to a report server</span></span>  
  
1.  <span data-ttu-id="a13ba-127">Copiare l'assembly dal percorso di gestione temporanea nella directory bin del server di report in cui si desidera utilizzare l'estensione per il recapito.</span><span class="sxs-lookup"><span data-stu-id="a13ba-127">Copy your assembly from your staging location to the bin directory of the report server on which you want to use the delivery extension.</span></span> <span data-ttu-id="a13ba-128">Il percorso predefinito della directory bin del server di report è%Programmi%\Microsoft SQL Server \ MSRS10_50. \<InstanceName> Services\ReportServer\bin. \Reporting</span><span class="sxs-lookup"><span data-stu-id="a13ba-128">The default location of the report server bin directory is %ProgramFiles%\Microsoft SQL Server\MSRS10_50.\<InstanceName>\Reporting Services\ReportServer\bin.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="a13ba-129">Se si tenta di sovrascrivere un assembly di estensioni per il recapito esistente, è necessario arrestare il servizio del server di report prima di copiare l'assembly aggiornato.</span><span class="sxs-lookup"><span data-stu-id="a13ba-129">If you are attempting to overwrite an existing delivery extension assembly, you must first stop the Report Server service before copying the updated assembly.</span></span> <span data-ttu-id="a13ba-130">Riavviare il servizio dopo il completamento della copia dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="a13ba-130">Restart your service after the assembly is through copying.</span></span>  
  
2.  <span data-ttu-id="a13ba-131">Dopo aver copiato il file di assembly, aprire il file RSReportServer.config</span><span class="sxs-lookup"><span data-stu-id="a13ba-131">After the assembly file is copied, open the RSReportServer.config file.</span></span> <span data-ttu-id="a13ba-132">Il file di RSReportServer.config si trova nel percorso%Programmi%\Microsoft SQL Server \ MSRS10_50. \<InstanceName> \Reporting Services\ReportServer directory.</span><span class="sxs-lookup"><span data-stu-id="a13ba-132">The RSReportServer.config file is located in the %ProgramFiles%\Microsoft SQL Server\MSRS10_50.\<InstanceName>\Reporting Services\ReportServer directory.</span></span> <span data-ttu-id="a13ba-133">È necessario immettere una voce nel file di configurazione per il file di assembly di estensioni per il recapito.</span><span class="sxs-lookup"><span data-stu-id="a13ba-133">You need to make an entry in the configuration file for your delivery extension assembly file.</span></span> <span data-ttu-id="a13ba-134">È possibile aprire il file di configurazione con [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] o con un semplice editor di testo, ad esempio Blocco note.</span><span class="sxs-lookup"><span data-stu-id="a13ba-134">You can open the configuration file with [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] or a simple text editor, such as Notepad.</span></span>  
  
3.  <span data-ttu-id="a13ba-135">Individuare l'elemento `Delivery` nel file RSReportServer.config.</span><span class="sxs-lookup"><span data-stu-id="a13ba-135">Locate the `Delivery` element in the RSReportServer.config file.</span></span> <span data-ttu-id="a13ba-136">È necessario immettere una voce per l'estensione per il recapito appena creata nel percorso seguente:</span><span class="sxs-lookup"><span data-stu-id="a13ba-136">An entry for your newly created delivery extension should be made in the following location:</span></span>  
  
    ```  
    <Extensions>  
       <Delivery>  
          <Your extension configuration information goes here>  
       </Delivery>  
    </Extensions>  
    ```  
  
4.  <span data-ttu-id="a13ba-137">Aggiungere una voce per l'estensione per il recapito.</span><span class="sxs-lookup"><span data-stu-id="a13ba-137">Add an entry for your delivery extension.</span></span> <span data-ttu-id="a13ba-138">La voce deve includere un elemento `Extension` con valori per `Name` e `Type` e può essere simile a quanto riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="a13ba-138">Your entry should include an `Extension` element with values for `Name` and `Type`, and might look like the following:</span></span>  
  
    ```  
    <Extension Name="My Delivery Extension Name" Type="CompanyName.ExtensionName.MyDeliveryExtensionClass, AssemblyName" />  
    ```  
  
     <span data-ttu-id="a13ba-139">Il valore per `Name` è il nome univoco dell'estensione per il recapito.</span><span class="sxs-lookup"><span data-stu-id="a13ba-139">The value for `Name` is the unique name of the delivery extension.</span></span> <span data-ttu-id="a13ba-140">Il valore per `Type` è un elenco delimitato da virgole che include una voce per lo spazio dei nomi completo della classe che implementa l'interfaccia <xref:Microsoft.ReportingServices.Interfaces.IDeliveryExtension>, seguita dal nome dell'assembly, senza l'estensione dll.</span><span class="sxs-lookup"><span data-stu-id="a13ba-140">The value for `Type` is a comma-separated list that includes an entry for the fully qualified namespace of your class that implements the <xref:Microsoft.ReportingServices.Interfaces.IDeliveryExtension> interface, followed by the name of your assembly (not including the .dll file extension).</span></span> <span data-ttu-id="a13ba-141">Per impostazione predefinita, le estensioni per il recapito sono visibili.</span><span class="sxs-lookup"><span data-stu-id="a13ba-141">By default, delivery extensions are visible.</span></span> <span data-ttu-id="a13ba-142">Per nascondere un'estensione dalle interfacce utente, come Gestione report, aggiungere un attributo `Visible` all'elemento `Extension` e impostarlo su `false`.</span><span class="sxs-lookup"><span data-stu-id="a13ba-142">To hide an extension from user interfaces, such as Report Manager, add a `Visible` attribute to the `Extension` element, and set it to `false`.</span></span>  
  
5.  <span data-ttu-id="a13ba-143">Aggiungere infine un gruppo di codice per l'assembly personalizzato che conceda l'autorizzazione `FullTrust` per l'estensione per il recapito.</span><span class="sxs-lookup"><span data-stu-id="a13ba-143">Finally, add a code group for your custom assembly that grants `FullTrust` permission for your delivery extension.</span></span> <span data-ttu-id="a13ba-144">A tale scopo, aggiungere il gruppo di codice al file rssrvpolicy.config che si trova per impostazione predefinita in%programmi%\Microsoft SQL Server \ MSRS10_50. \<InstanceName> Services\ReportServer. \Reporting</span><span class="sxs-lookup"><span data-stu-id="a13ba-144">You do this by adding the code group to the rssrvpolicy.config file located by default in %ProgramFiles%\Microsoft SQL Server\MSRS10_50.\<InstanceName>\Reporting Services\ReportServer.</span></span> <span data-ttu-id="a13ba-145">Il gruppo di codice può essere simile a quanto riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="a13ba-145">Your code group might look like the following:</span></span>  
  
    ```  
    <CodeGroup class="UnionCodeGroup"  
       version="1"  
       PermissionSetName="FullTrust"  
       Name="MyExtensionCodeGroup"  
       Description="Code group for my delivery extension">  
          <IMembershipCondition class="UrlMembershipCondition"  
             version="1"  
             Url="C:\Program Files\Microsoft SQL Server\MSRS10_50.<InstanceName>\Reporting Services\ReportServer\bin\MyExtensionAssembly.dll"  
           />  
    </CodeGroup>  
    ```  
  
     <span data-ttu-id="a13ba-146">L'appartenenza URL è solo una delle numerose condizioni di appartenenza che è possibile scegliere per l'estensione per il recapito.</span><span class="sxs-lookup"><span data-stu-id="a13ba-146">URL membership is only one of many membership conditions you might choose for your delivery extension.</span></span> <span data-ttu-id="a13ba-147">Per altre informazioni sulla sicurezza dall'accesso di codice in [!INCLUDE[ssRS](../../../includes/ssrs.md)], vedere [Sviluppo sicuro &#40;Reporting Services&#41;](../secure-development/secure-development-reporting-services.md)</span><span class="sxs-lookup"><span data-stu-id="a13ba-147">For more information about code access security in [!INCLUDE[ssRS](../../../includes/ssrs.md)], see.[Secure Development &#40;Reporting Services&#41;](../secure-development/secure-development-reporting-services.md)</span></span>  
  
## <a name="deploying-the-extension-to-report-manager"></a><span data-ttu-id="a13ba-148">Distribuzione dell'estensione in Gestione report</span><span class="sxs-lookup"><span data-stu-id="a13ba-148">Deploying the Extension to Report Manager</span></span>  
 <span data-ttu-id="a13ba-149">Se l'estensione per il recapito implementa l'interfaccia <xref:Microsoft.ReportingServices.Interfaces.ISubscriptionBaseUIUserControl>, può essere utilizzata con la pagina di sottoscrizione di Gestione report.</span><span class="sxs-lookup"><span data-stu-id="a13ba-149">If your delivery extension implements the <xref:Microsoft.ReportingServices.Interfaces.ISubscriptionBaseUIUserControl> interface, your delivery extension can be used with the Report Manager Subscription page.</span></span> <span data-ttu-id="a13ba-150">Per rendere disponibile l'interfaccia utente di sottoscrizione, è necessario distribuire l'estensione in Gestione report.</span><span class="sxs-lookup"><span data-stu-id="a13ba-150">To make the subscription user interface available, you need to deploy your extension to Report Manager.</span></span>  
  
#### <a name="to-deploy-a-deliver-extension-assembly-to-report-manager"></a><span data-ttu-id="a13ba-151">Per distribuire un assembly di estensioni per il recapito in Gestione report</span><span class="sxs-lookup"><span data-stu-id="a13ba-151">To deploy a deliver extension assembly to Report Manager</span></span>  
  
1.  <span data-ttu-id="a13ba-152">Copiare l'assembly dal percorso di gestione temporanea nella directory bin di Gestione report.</span><span class="sxs-lookup"><span data-stu-id="a13ba-152">Copy your assembly from your staging location to the bin directory of Report Manager.</span></span> <span data-ttu-id="a13ba-153">Il percorso predefinito della directory Gestione report bin è%Programmi%\Microsoft SQL Server \ MSRS10_50. \<InstanceName> Services\ReportManager\bin. \Reporting</span><span class="sxs-lookup"><span data-stu-id="a13ba-153">The default location of the Report Manager bin directory is %ProgramFiles%\Microsoft SQL Server\MSRS10_50.\<InstanceName>\Reporting Services\ReportManager\bin.</span></span>  
  
2.  <span data-ttu-id="a13ba-154">Dopo aver copiato il file di assembly, aprire il file RSReportServer.config</span><span class="sxs-lookup"><span data-stu-id="a13ba-154">After the assembly file is copied, open the RSReportServer.config file.</span></span> <span data-ttu-id="a13ba-155">Il file di RSReportServer.config si trova nel percorso%Programmi%\Microsoft SQL Server \ MSRS10_50. \<InstanceName> \Reporting Services\ReportServer directory.</span><span class="sxs-lookup"><span data-stu-id="a13ba-155">The RSReportServer.config file is located in the %ProgramFiles%\Microsoft SQL Server\MSRS10_50.\<InstanceName>\Reporting Services\ReportServer directory.</span></span> <span data-ttu-id="a13ba-156">È necessario immettere una voce nel file di configurazione per il file di assembly di estensioni per il recapito.</span><span class="sxs-lookup"><span data-stu-id="a13ba-156">You need to make an entry in the configuration file for your delivery extension assembly file.</span></span> <span data-ttu-id="a13ba-157">È possibile aprire il file di configurazione in Visual Studio .NET o in un semplice editor di testo, ad esempio Blocco note.</span><span class="sxs-lookup"><span data-stu-id="a13ba-157">You can open the configuration file with Visual Studio .NET or a simple text editor, such as Notepad.</span></span>  
  
3.  <span data-ttu-id="a13ba-158">Individuare l'elemento `DeliveryUI` nel file RSReportServer.config.</span><span class="sxs-lookup"><span data-stu-id="a13ba-158">Locate the `DeliveryUI` element in the RSReportServer.config file.</span></span> <span data-ttu-id="a13ba-159">È necessario immettere una voce per l'estensione per il recapito appena creata nel percorso seguente:</span><span class="sxs-lookup"><span data-stu-id="a13ba-159">An entry for your newly created delivery extension should be made in the following location:</span></span>  
  
    ```  
    <Extensions>  
       <DeliveryUI>  
          <Your extension configuration information goes here>  
       </DeliveryUI>  
    </Extensions>  
    ```  
  
4.  <span data-ttu-id="a13ba-160">Aggiungere una voce per l'estensione per il recapito.</span><span class="sxs-lookup"><span data-stu-id="a13ba-160">Add an entry for your delivery extension.</span></span> <span data-ttu-id="a13ba-161">La voce deve includere un elemento `Extension` con valori per `Name` e `Type` e può essere simile a quanto riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="a13ba-161">Your entry should include an `Extension` element with values for `Name` and `Type` and might look like the following:</span></span>  
  
    ```  
    <Extension Name="My Delivery Extension Name" Type="CompanyName.ExtensionName.MyDeliveryUIExtensionClass, AssemblyName" />  
    ```  
  
     <span data-ttu-id="a13ba-162">Il valore per `Name` è il nome univoco dell'estensione per il recapito.</span><span class="sxs-lookup"><span data-stu-id="a13ba-162">The value for `Name` is the unique name of the delivery extension.</span></span> <span data-ttu-id="a13ba-163">Il valore per `Type` è un elenco delimitato da virgole che include una voce per lo spazio dei nomi completo della classe che implementa l'interfaccia <xref:Microsoft.ReportingServices.Interfaces.ISubscriptionBaseUIUserControl>, seguita dal nome dell'assembly, senza l'estensione dll.</span><span class="sxs-lookup"><span data-stu-id="a13ba-163">The value for `Type` is a comma-separated list that includes an entry for the fully qualified namespace of your class that implements the <xref:Microsoft.ReportingServices.Interfaces.ISubscriptionBaseUIUserControl> interface, followed by the name of your assembly (not including the .dll file extension).</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="a13ba-164">Il valore dell'attributo `Name` deve essere identico per le voci dei file di configurazione del server di report e di Gestione report.</span><span class="sxs-lookup"><span data-stu-id="a13ba-164">The value of the `Name` attribute must be identical for both the Report Server and Report Manager configuration file entries.</span></span> <span data-ttu-id="a13ba-165">Se non sono identici, la configurazione del server non è valida.</span><span class="sxs-lookup"><span data-stu-id="a13ba-165">If they are not identical, your server configuration is not valid.</span></span>  
  
     <span data-ttu-id="a13ba-166">Aggiungere infine un gruppo di codice per l'assembly personalizzato che conceda l'autorizzazione `FullTrust` per l'estensione per il recapito.</span><span class="sxs-lookup"><span data-stu-id="a13ba-166">Finally, add a code group for your custom assembly that grants `FullTrust` permission for your delivery extension.</span></span> <span data-ttu-id="a13ba-167">A tale scopo, aggiungere il gruppo di codice al file RSmgrpolicy.config che si trova per impostazione predefinita nella cartella C:\Programmi\Microsoft SQL Server \ MSRS10_50. \<InstanceName> Services\ReportManager. \Reporting</span><span class="sxs-lookup"><span data-stu-id="a13ba-167">You do this by adding the code group to the RSmgrpolicy.config file located by default in C:\Program Files\Microsoft SQL Server\MSRS10_50.\<InstanceName>\Reporting Services\ReportManager.</span></span> <span data-ttu-id="a13ba-168">Il gruppo di codice può essere simile a quanto riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="a13ba-168">Your code group might look like the following:</span></span>  
  
    ```  
    <CodeGroup class="UnionCodeGroup"  
       version="1"  
       PermissionSetName="FullTrust"  
       Name="MyExtensionCodeGroup"  
       Description="Code group for my delivery UI extension">  
          <IMembershipCondition class="UrlMembershipCondition"  
             version="1"  
             Url="C:\Program Files\Microsoft SQL Server\MSRS10_50.<InstanceName>\Reporting Services\ReportManager\bin\MyExtensionAssembly.dll"  
           />  
    </CodeGroup>  
    ```  
  
     <span data-ttu-id="a13ba-169">L'appartenenza URL è solo una delle numerose condizioni di appartenenza che è possibile scegliere per l'estensione per il recapito.</span><span class="sxs-lookup"><span data-stu-id="a13ba-169">URL membership is only one of many membership conditions you might choose for your delivery extension.</span></span> <span data-ttu-id="a13ba-170">Per altre informazioni sulla sicurezza dall'accesso di codice in [!INCLUDE[ssRS](../../../includes/ssrs.md)] , vedere [sviluppo protetto &#40;Reporting Services&#41;](../secure-development/secure-development-reporting-services.md)</span><span class="sxs-lookup"><span data-stu-id="a13ba-170">For more information about code access security in [!INCLUDE[ssRS](../../../includes/ssrs.md)], see [Secure Development &#40;Reporting Services&#41;](../secure-development/secure-development-reporting-services.md)</span></span>  
  
## <a name="verifying-the-deployment"></a><span data-ttu-id="a13ba-171">Verifica della distribuzione</span><span class="sxs-lookup"><span data-stu-id="a13ba-171">Verifying the Deployment</span></span>  
 <span data-ttu-id="a13ba-172">È possibile verificare se l'estensione per il recapito è stata distribuita correttamente nel server di report tramite il metodo <xref:ReportService2010.ReportingService2010.ListExtensions%2A> del servizio Web.</span><span class="sxs-lookup"><span data-stu-id="a13ba-172">You can verify whether your delivery extension was deployed successfully to the report server by using the Web service <xref:ReportService2010.ReportingService2010.ListExtensions%2A> method.</span></span> <span data-ttu-id="a13ba-173">È inoltre possibile aprire Gestione report e verificare che l'estensione sia inclusa nell'elenco delle estensioni per il recapito disponibili per una sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="a13ba-173">You can also open Report Manager and verify that your extension is included in the list of available delivery extensions for a subscription.</span></span> <span data-ttu-id="a13ba-174">Per ulteriori informazioni su Gestione report e sulle sottoscrizioni, vedere [sottoscrizioni e recapito &#40;Reporting Services&#41;](../../subscriptions/subscriptions-and-delivery-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="a13ba-174">For more information about Report Manager and subscriptions, see [Subscriptions and Delivery &#40;Reporting Services&#41;](../../subscriptions/subscriptions-and-delivery-reporting-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a13ba-175">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a13ba-175">See Also</span></span>  
 <span data-ttu-id="a13ba-176">[Implementazione di un'estensione per il recapito](implementing-a-delivery-extension.md) </span><span class="sxs-lookup"><span data-stu-id="a13ba-176">[Implementing a Delivery Extension](implementing-a-delivery-extension.md) </span></span>  
 [<span data-ttu-id="a13ba-177">Libreria di estensioni di Reporting Services</span><span class="sxs-lookup"><span data-stu-id="a13ba-177">Reporting Services Extension Library</span></span>](../reporting-services-extension-library.md)  
  
  
