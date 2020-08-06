---
title: Esempio di configurazione con privilegi minimi per PowerPivot per SharePoint 2013 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: c1e09e6c-52d3-48ab-8c70-818d5d775087
author: minewiskan
ms.author: owend
ms.openlocfilehash: 0188f314e4c354b33d03e6e7948aed1ba4cf8be2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713596"
---
# <a name="example-of-a-minimum-privilege-configuration-for-powerpivot-for-sharepoint-2013"></a><span data-ttu-id="056e0-102">Esempio di una configurazione con privilegi minimi per PowerPivot per SharePoint 2013</span><span class="sxs-lookup"><span data-stu-id="056e0-102">Example of a Minimum-Privilege Configuration for PowerPivot for SharePoint 2013</span></span>
  <span data-ttu-id="056e0-103">In questo argomento viene illustrata una configurazione di esempio di PowerPivot per SharePoint 2013 con privilegi minimi.</span><span class="sxs-lookup"><span data-stu-id="056e0-103">This topic describes an example PowerPivot for SharePoint 2013 configuration with minimum privileges.</span></span> <span data-ttu-id="056e0-104">Nella configurazione viene utilizzato un account diverso per ognuno dei tre componenti e ogni account dispone del livello minimo di privilegi.</span><span class="sxs-lookup"><span data-stu-id="056e0-104">The configuration utilizes a different account for each of the three components and each account has the minimum level of privileges.</span></span>  
  
## <a name="summary-of-accounts"></a><span data-ttu-id="056e0-105">Riepilogo degli account</span><span class="sxs-lookup"><span data-stu-id="056e0-105">Summary of Accounts</span></span>  
 <span data-ttu-id="056e0-106">PowerPivot per SharePoint 2013 supporta l'utilizzo dell'account Servizio di rete per l'account del servizio Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="056e0-106">PowerPivot for SharePoint 2013 supports the use of the Network Service account for the Analysis Services service account.</span></span> <span data-ttu-id="056e0-107">L'account Servizio di rete non è supportato con SharePoint 2010.</span><span class="sxs-lookup"><span data-stu-id="056e0-107">The Network Service account is not a supported scenario with SharePoint 2010.</span></span> <span data-ttu-id="056e0-108">Per ulteriori informazioni sugli account del servizio, vedere [configurare account di servizio e autorizzazioni di Windows](../../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md) ( https://msdn.microsoft.com/library/ms143504.aspx) .</span><span class="sxs-lookup"><span data-stu-id="056e0-108">For more information on Service accounts, see [Configure Windows Service Accounts and Permissions](../../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md) (https://msdn.microsoft.com/library/ms143504.aspx).</span></span>  
  
 <span data-ttu-id="056e0-109">Nella tabella seguente sono riepilogati i tre account utilizzati nell'esempio di configurazione con privilegi minimi.</span><span class="sxs-lookup"><span data-stu-id="056e0-109">The following table summarizes the three accounts used in this example of a minimum privileged configuration.</span></span>  
  
|<span data-ttu-id="056e0-110">Scope</span><span class="sxs-lookup"><span data-stu-id="056e0-110">Scope</span></span>|<span data-ttu-id="056e0-111">Nome</span><span class="sxs-lookup"><span data-stu-id="056e0-111">Name</span></span>|  
|-----------|----------|  
|<span data-ttu-id="056e0-112">Account amministratore di SharePoint</span><span class="sxs-lookup"><span data-stu-id="056e0-112">SharePoint Administrator account</span></span>|<span data-ttu-id="056e0-113">**SPAdmin**</span><span class="sxs-lookup"><span data-stu-id="056e0-113">**SPAdmin**</span></span>|  
|<span data-ttu-id="056e0-114">Account farm SharePoint</span><span class="sxs-lookup"><span data-stu-id="056e0-114">SharePoint Farm account</span></span>|<span data-ttu-id="056e0-115">**SPFarm**</span><span class="sxs-lookup"><span data-stu-id="056e0-115">**SPFarm**</span></span>|  
|<span data-ttu-id="056e0-116">Account del servizio Analysis Services</span><span class="sxs-lookup"><span data-stu-id="056e0-116">Analysis Services service account</span></span>|<span data-ttu-id="056e0-117">**SPsvc**</span><span class="sxs-lookup"><span data-stu-id="056e0-117">**SPsvc**</span></span>|  
  
### <a name="the-sharepoint-administrator-account-spadmin"></a><span data-ttu-id="056e0-118">Account amministratore di SharePoint (SpAdmin)</span><span class="sxs-lookup"><span data-stu-id="056e0-118">The SharePoint Administrator account (SpAdmin)</span></span>  
 <span data-ttu-id="056e0-119">**SPAdmin** è un account di dominio usato per installare e configurare la farm.</span><span class="sxs-lookup"><span data-stu-id="056e0-119">**SPAdmin** is a domain account you use to install and configure the farm.</span></span> <span data-ttu-id="056e0-120">Si tratta dell'account utilizzato per eseguire la configurazione guidata SharePoint e dello strumento di configurazione PowerPivot per SharePoint 2013. l'account **SPAdmin** è l'unico account che richiede diritti di amministratore locale.</span><span class="sxs-lookup"><span data-stu-id="056e0-120">It is the account used to run the SharePoint Configuration Wizard and the PowerPivot Configuration Tool for SharePoint 2013.The **SPAdmin** account is the only account that requires local Administrator rights.</span></span> <span data-ttu-id="056e0-121">Prima di eseguire lo strumento di configurazione PowerPivot, concedere i privilegi dell'account **SPAdmin** all'istanza del database di SQL Server in cui SharePoint crea il contenuto e i database di configurazione.</span><span class="sxs-lookup"><span data-stu-id="056e0-121">Before running the PowerPivot Configuration tool, grant the **SPAdmin** account privileges to the SQL Server database instance where SharePoint creates content and configuration databases.</span></span> <span data-ttu-id="056e0-122">Per configurare l'account SPAdmin in uno scenario con privilegi minimi, l'account deve essere un membro dei ruoli **securityadmin** e **dbcreator**.</span><span class="sxs-lookup"><span data-stu-id="056e0-122">To configure the SPAdmin account in a minimum privilege scenario, it should be a member of the roles **securityadmin** and **dbcreator**.</span></span>  
  
### <a name="the-farm-account-spfarm"></a><span data-ttu-id="056e0-123">Account farm (SPFarm)</span><span class="sxs-lookup"><span data-stu-id="056e0-123">The Farm account (SPFarm)</span></span>  
 <span data-ttu-id="056e0-124">**SPFarm** è un account di dominio usato dal servizio Timer di SharePoint e dall'applicazione Web per Amministrazione centrale per accedere al database del contenuto di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="056e0-124">**SPFarm** is a domain account that the SharePoint Timer service and the web application for Central Administration use to access the SharePoint content database.</span></span> <span data-ttu-id="056e0-125">Per questo account non è necessario essere un amministratore locale.</span><span class="sxs-lookup"><span data-stu-id="056e0-125">This account does not need to be a local administrator.</span></span> <span data-ttu-id="056e0-126">Tramite la Configurazione guidata SharePoint vengono concessi i privilegi minimi appropriati nel database back-end di SQL Server. La configurazione di privilegi minimi di SQL Server è l'appartenenza ai ruoli **securityadmin** e **dbcreator**.</span><span class="sxs-lookup"><span data-stu-id="056e0-126">The SharePoint configuration wizard grants the proper minimal privilege in the back-end SQL Server database.The minimum SQL Server privilege configuration is membership in the roles **securityadmin** and **dbcreator**.</span></span>  
  
### <a name="the-service-account-for-powerpivot-service-spsvc"></a><span data-ttu-id="056e0-127">Account del servizio per il servizio PowerPivot (SPscv)</span><span class="sxs-lookup"><span data-stu-id="056e0-127">The Service Account for PowerPivot Service (SPsvc)</span></span>  
 <span data-ttu-id="056e0-128">Se una nuova farm di SharePoint non viene configurata prima dell'esecuzione dello strumento di configurazione di PowerPivot, tramite quest'ultimo, per impostazione predefinita, verranno creati gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="056e0-128">If a new SharePoint farm is not configured before you run the PowerPivot Configuration tool, then by default the PowerPivot Configuration tool will create the following:</span></span>  
  
-   <span data-ttu-id="056e0-129">Applicazione di servizio PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="056e0-129">PowerPivot Service application.</span></span>  
  
-   <span data-ttu-id="056e0-130">Applicazione Excel Services.</span><span class="sxs-lookup"><span data-stu-id="056e0-130">Excel Services application.</span></span>  
  
-   <span data-ttu-id="056e0-131">Applicazione di archiviazione sicura.</span><span class="sxs-lookup"><span data-stu-id="056e0-131">Secure Store application.</span></span>  
  
 <span data-ttu-id="056e0-132">Tramite lo strumento di configurazione di PowerPivot vengono configurate tutte e tre le applicazioni di servizio nel pool di applicazioni predefinito.</span><span class="sxs-lookup"><span data-stu-id="056e0-132">The PowerPivot configuration tool configures all three of the service applications in the default application pool.</span></span> <span data-ttu-id="056e0-133">Il pool di applicazioni viene in genere configurato per l'esecuzione come account SPFarm, tramite cui è possibile accedere a molte risorse non richieste da un account del servizio. Per garantire all'ambiente i privilegi minimi, configurare l'utilizzo di un nuovo account di dominio da parte del pool di applicazioni e dell'applicazione Web appropriati.</span><span class="sxs-lookup"><span data-stu-id="056e0-133">That application pool is typically configured to run as the SPFarm account, which has access to many resources that a service account does not require.To make the environment a minimum-privileged environment, configure a new domain account to be use by the appropriate application pool and web application.</span></span>  
  
 <span data-ttu-id="056e0-134">**Per creare un nuovo account di dominio SPsvc da utilizzare come account del servizio SharePoint:**</span><span class="sxs-lookup"><span data-stu-id="056e0-134">**To create a new domain account SPsvc to be used as a SharePoint Service account:**</span></span>  
  
1.  <span data-ttu-id="056e0-135">In Amministrazione centrale SharePoint fare clic su **sicurezza**.</span><span class="sxs-lookup"><span data-stu-id="056e0-135">In SharePoint Central Administration, click **Security**.</span></span>  
  
2.  <span data-ttu-id="056e0-136">Fare clic su **Configura account di servizio**</span><span class="sxs-lookup"><span data-stu-id="056e0-136">Click **Configure Service Accounts**</span></span>  
  
3.  <span data-ttu-id="056e0-137">Fare clic su **Registra nuovo account gestito**.</span><span class="sxs-lookup"><span data-stu-id="056e0-137">Click **Register new managed account**.</span></span>  
  
 <span data-ttu-id="056e0-138">L'account **SPSvc** non include i privilegi di amministratore locale e SPsvc non avrà alcun privilegio nel database di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="056e0-138">The **SPSvc** account has no local administrator privileges and SPsvc will not have any privileges in the SharePoint database.</span></span> <span data-ttu-id="056e0-139">Gli unici privilegi richiesti da SPsvc sono i diritti di amministratore per l'istanza di PowerPivot di Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="056e0-139">The only privileges SPsvc requires is administrative rights to the PowerPivot Instance of the Analysis Services.</span></span>  
  
 <span data-ttu-id="056e0-140">**Per configurare il pool di applicazioni appropriato per l'utilizzo dell'account SPsvc:**</span><span class="sxs-lookup"><span data-stu-id="056e0-140">**To configure the appropriate application pool to use the SPsvc account :**</span></span>  
  
1.  <span data-ttu-id="056e0-141">In Amministrazione centrale SharePoint fare clic su **sicurezza**.</span><span class="sxs-lookup"><span data-stu-id="056e0-141">In SharePoint Central Administration, click **Security**.</span></span>  
  
2.  <span data-ttu-id="056e0-142">Fare clic su **Configura account di servizio**.</span><span class="sxs-lookup"><span data-stu-id="056e0-142">Click **Configure Service Accounts**.</span></span>  
  
3.  <span data-ttu-id="056e0-143">Selezionare il pool di applicazioni del servizio utilizzato dall'applicazione di servizio PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="056e0-143">Select the service application pool used by the PowerPivot Service application.</span></span> <span data-ttu-id="056e0-144">Successivamente, selezionare l'account SPSvc.</span><span class="sxs-lookup"><span data-stu-id="056e0-144">Then select the SPSvc account.</span></span>  
  
 <span data-ttu-id="056e0-145">**Per concedere l'accesso all'applicazione Web con PowerShell:**</span><span class="sxs-lookup"><span data-stu-id="056e0-145">**To Grant access to the web application with PowerShell:**</span></span>  
  
1.  <span data-ttu-id="056e0-146">Eseguire la shell di gestione di SharePoint 2013 con privilegi di amministratore.</span><span class="sxs-lookup"><span data-stu-id="056e0-146">Run the SharePoint 2013 Management Shell with administrator privileges.</span></span>  
  
2.  <span data-ttu-id="056e0-147">Eseguire il codice PowerShell riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="056e0-147">Run the following PowerShell code:</span></span>  
  
    ```powershell
    $webApp = Get-SPWebApplication "http://<servername>"  
    $webApp.GrantAccessToProcessIdentity("DOMAIN\<ServiceAccountName>")
    ```  
