---
title: Reporting Services servizio SharePoint e applicazioni di servizio | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 501aa9ee-8c13-458c-bf6f-24e00c82681b
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 5654764f7913002cdae58d3264848250a292c585
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87638270"
---
# <a name="reporting-services-sharepoint-service-and-service-applications"></a><span data-ttu-id="857e8-102">Servizio SharePoint di Reporting Services e applicazioni di servizio</span><span class="sxs-lookup"><span data-stu-id="857e8-102">Reporting Services SharePoint Service and Service Applications</span></span>
  [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] <span data-ttu-id="857e8-103">è basata sull'architettura del servizio SharePoint e prevede l'utilizzo di un servizio SharePoint e di applicazioni di servizio uno-a-molti.</span><span class="sxs-lookup"><span data-stu-id="857e8-103">SharePoint mode is architected on the SharePoint service architecture and utilizes a SharePoint service and one to many service applications.</span></span> <span data-ttu-id="857e8-104">Creando un'applicazione di servizio si rende disponibile il servizio e si genera il database dell'applicazione di servizio.</span><span class="sxs-lookup"><span data-stu-id="857e8-104">Creating a service application makes the service available and generates the service application database.</span></span> <span data-ttu-id="857e8-105">È possibile creare più applicazioni di servizio Reporting Services, tuttavia un'unica applicazione di servizio è sufficiente per la maggior parte degli scenari di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="857e8-105">You can create multiple Reporting Services service applications but one service application is sufficient for most deployment scenarios.</span></span>  
  
 <span data-ttu-id="857e8-106">In questo argomento vengono illustrate le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="857e8-106">This topic covers the following information:</span></span>  
  
-   [<span data-ttu-id="857e8-107">Creazione di un'applicazione di servizio Reporting Services</span><span class="sxs-lookup"><span data-stu-id="857e8-107">Creating a Reporting Services Service Application</span></span>](#bkmk_createapp)  
  
-   [<span data-ttu-id="857e8-108">Modificare le associazioni dell'applicazione di servizio con un gruppo di proxy</span><span class="sxs-lookup"><span data-stu-id="857e8-108">Modify the Associations of the Service Application with a proxy group</span></span>](#bkmk_associations)  
  
-   [<span data-ttu-id="857e8-109">Modificare le proprietà dell'applicazione di servizio</span><span class="sxs-lookup"><span data-stu-id="857e8-109">Edit Service Application Properties</span></span>](#bkmk_editserviceapplication)  
  
-   [<span data-ttu-id="857e8-110">Per creare un'applicazione di servizio Reporting Services utilizzando PowerShell</span><span class="sxs-lookup"><span data-stu-id="857e8-110">To create a Reporting Services Service Application using PowerShell</span></span>](#bkmk_powershell_create_ssrs_serviceapp)  
  
-   [<span data-ttu-id="857e8-111">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="857e8-111">Related Tasks</span></span>](#bkmk_related)  
  
##  <a name="creating-a-reporting-services-service-application"></a><a name="bkmk_createapp"></a><span data-ttu-id="857e8-112">Creazione di un'applicazione di servizio Reporting Services</span><span class="sxs-lookup"><span data-stu-id="857e8-112">Creating a Reporting Services Service Application</span></span>  
 <span data-ttu-id="857e8-113">Per creare applicazioni di servizio [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] , è possibile utilizzare Amministrazione centrale SharePoint o script di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="857e8-113">You can use SharePoint Central Administration or PowerShell scripts to create the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] services applications.</span></span> <span data-ttu-id="857e8-114">Per altre informazioni sull'uso di Amministrazione centrale SharePoint, vedere la sezione "Creare un'applicazione di servizio Reporting Services" in [Installare la modalità SharePoint di Reporting Services per SharePoint 2010](../../2014/sql-server/install/install-reporting-services-sharepoint-mode-for-sharepoint-2010.md).</span><span class="sxs-lookup"><span data-stu-id="857e8-114">For more information on using SharePoint Central Administration, see the "Create a Reporting Services Service Application" section in [Install Reporting Services SharePoint Mode for SharePoint 2010](../../2014/sql-server/install/install-reporting-services-sharepoint-mode-for-sharepoint-2010.md).</span></span> <span data-ttu-id="857e8-115">Per uno script di PowerShell di esempio per la creazione di applicazioni di servizio, vedere la sezione relativa a PowerShell più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="857e8-115">See the PowerShell section later in this topic for a sample PowerShell script for creating service applications.</span></span>  
  
##  <a name="modify-the-associations-of-the-service-application-with-a-proxy-group"></a><a name="bkmk_associations"></a><span data-ttu-id="857e8-116">Modificare le associazioni dell'applicazione di servizio con un gruppo di proxy</span><span class="sxs-lookup"><span data-stu-id="857e8-116">Modify the Associations of the Service Application with a proxy group</span></span>  
 <span data-ttu-id="857e8-117">Nella pagina Nuova per la creazione di un'applicazione di servizio è contenuta la sezione **Associazione applicazione Web**.</span><span class="sxs-lookup"><span data-stu-id="857e8-117">The New page for creating a services application contains the section **Web Application Association**.</span></span> <span data-ttu-id="857e8-118">Questa sezione consente di associare l'applicazione di servizio quando viene creata.</span><span class="sxs-lookup"><span data-stu-id="857e8-118">The section allows you to associate your service application as you create it.</span></span> <span data-ttu-id="857e8-119">Utilizzare i passaggi seguenti per modificare l'associazione e assegnare una configurazione personalizzata all'applicazione di servizio.</span><span class="sxs-lookup"><span data-stu-id="857e8-119">Use the following steps to change the association and assign a customer configuration to the service application.</span></span> <span data-ttu-id="857e8-120">Lo stesso processo generale può inoltre essere utilizzato per aggiungere il proxy al gruppo predefinito anziché modificare l'associazione dell'applicazione di servizio a un gruppo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="857e8-120">The same general process can also be used to add the proxy to the default group rather than changing the association of the service application to a custom group.</span></span>  
  
1.  <span data-ttu-id="857e8-121">In Gestione applicazioni di Amministrazione centrale SharePoint fare clic su **Configura associazioni applicazione di servizio**.</span><span class="sxs-lookup"><span data-stu-id="857e8-121">In SharePoint Central Administration, in the Application Management, click **Configure Service Application Associations**.</span></span>  
  
2.  <span data-ttu-id="857e8-122">Nella pagina Associazioni applicazione di servizio modificare la visualizzazione in **Applicazioni di servizio**.</span><span class="sxs-lookup"><span data-stu-id="857e8-122">On the Service application Associations page, change the view to **Service Applications**.</span></span>  
  
3.  <span data-ttu-id="857e8-123">Trovare e fare clic sul nome della nuova applicazione di servizio di [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="857e8-123">Find and click the name of your new [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] Service application.</span></span> <span data-ttu-id="857e8-124">È possibile fare clic anche sull' **impostazione predefinita** del nome del gruppo proxy di applicazione per aggiungere il proxy per impostare il gruppo piuttosto che completare i passaggi seguenti.</span><span class="sxs-lookup"><span data-stu-id="857e8-124">You could also click the application proxy group name **default** to add the proxy to default group rather than completing the following steps.</span></span>  
  
4.  <span data-ttu-id="857e8-125">Nella casella di selezione **Modifica il gruppo di connessioni seguente** scegliere **Personalizza**.</span><span class="sxs-lookup"><span data-stu-id="857e8-125">Select **Custom** in the selection box **Edit the following group of connections**.</span></span>  
  
5.  <span data-ttu-id="857e8-126">Selezionare la casella relativa al proxy e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="857e8-126">Check the box for your proxy and click **Ok**.</span></span>  
  
##  <a name="edit-service-application-properties"></a><a name="bkmk_editserviceapplication"></a><span data-ttu-id="857e8-127">Modificare le proprietà dell'applicazione di servizio</span><span class="sxs-lookup"><span data-stu-id="857e8-127">Edit Service Application Properties</span></span>  
 <span data-ttu-id="857e8-128">È possibile riaprire la pagina delle proprietà dell'applicazione di servizio per modificare le proprietà.</span><span class="sxs-lookup"><span data-stu-id="857e8-128">You can reopen the property page of the service application to modify the properties.</span></span>  
  
1.  <span data-ttu-id="857e8-129">Nel gruppo Gestione applicazioni di amministrazione centrale SharePoint fare clic su **Gestisci applicazioni di servizio**.</span><span class="sxs-lookup"><span data-stu-id="857e8-129">In SharePoint Central Administration, in the Application Management group, click **Manage service applications**.</span></span>  
  
2.  <span data-ttu-id="857e8-130">Selezionare l'applicazione di servizio facendo clic sul tipo di colonna per selezionare l'intera riga.</span><span class="sxs-lookup"><span data-stu-id="857e8-130">Select the service application by clicking the type column to select the entire row.</span></span> <span data-ttu-id="857e8-131">Se si fa clic sul nome dell'applicazione, viene aperta la pagina delle opzioni di gestione per il servizio anziché le proprietà dell'applicazione di servizio.</span><span class="sxs-lookup"><span data-stu-id="857e8-131">If you click the name of the application it, the Management options page for the service opens instead of opening the properties of the service application.</span></span>  
  
3.  <span data-ttu-id="857e8-132">Nella barra multifunzione relativa alle applicazioni di servizio fare clic su **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="857e8-132">In the Service Applications ribbon, click **Properties**.</span></span>  
  
##  <a name="to-create-a-reporting-services-service-application-using-powershell"></a><a name="bkmk_powershell_create_ssrs_serviceapp"></a><span data-ttu-id="857e8-133">Per creare un'applicazione di servizio Reporting Services tramite PowerShell</span><span class="sxs-lookup"><span data-stu-id="857e8-133">To create a Reporting Services Service Application using PowerShell</span></span>  
 <span data-ttu-id="857e8-134">È possibile utilizzare PowerShell per creare l'applicazione di servizio e il proxy.</span><span class="sxs-lookup"><span data-stu-id="857e8-134">You can use PowerShell to create the Service application and proxy.</span></span> <span data-ttu-id="857e8-135">Nell'esempio sottostante si presuppone che si conosca quale pool di applicazioni si desidera configurare affinché venga utilizzato dall'applicazione di servizio.</span><span class="sxs-lookup"><span data-stu-id="857e8-135">The sample below assumes that you know what application pool you want to configure the service application to use.</span></span>  
  
1.  <span data-ttu-id="857e8-136">Aggiungere l'oggetto del pool di applicazioni del nome del pool di applicazioni a una variabile che viene passata in Nuova azione.</span><span class="sxs-lookup"><span data-stu-id="857e8-136">Add the application pool object of your application pool name to a variable that is passed into the New action.</span></span>  
  
    ```powershell
    $appPoolName = Get-SPServiceApplicationPool "<application pool name>"  
    ```  
  
2.  <span data-ttu-id="857e8-137">Creare l'applicazione di servizio con un nome e il nome del pool di applicazioni forniti.</span><span class="sxs-lookup"><span data-stu-id="857e8-137">Create the service application with a name and application pool name you provide.</span></span>  
  
    ```powershell
    New-SPRSServiceApplication -Name 'MyServiceApplication' -ApplicationPool $appPoolName -DatabaseName 'MyServiceApplicationDatabase' -DatabaseServer '<Server Name>'  
    ```  
  
3.  <span data-ttu-id="857e8-138">Ottenere il nuovo oggetto dell'applicazione di servizio e inoltrare tramite pipe l'oggetto nella pipe del nuovo cmdlet del proxy.</span><span class="sxs-lookup"><span data-stu-id="857e8-138">Get the new service application object, and pipe the object into the Pipe the new proxy cmdlet.</span></span>  
  
    ```powershell
    Get-SPRSServiceApplication -name MyServiceApplication | New-SPRSServiceApplicationProxy "MyServiceApplicationProxy"  
    ```  
  
##  <a name="related-tasks"></a><a name="bkmk_related"></a> <span data-ttu-id="857e8-139">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="857e8-139">Related Tasks</span></span>  
  
|<span data-ttu-id="857e8-140">Attività</span><span class="sxs-lookup"><span data-stu-id="857e8-140">Task</span></span>|<span data-ttu-id="857e8-141">Collegamento</span><span class="sxs-lookup"><span data-stu-id="857e8-141">Link</span></span>|  
|----------|----------|  
|<span data-ttu-id="857e8-142">Gestire le impostazioni dell'applicazione di servizio.</span><span class="sxs-lookup"><span data-stu-id="857e8-142">Manage the settings of your Service Application.</span></span>|[<span data-ttu-id="857e8-143">Gestire un'applicazione di servizio Reporting Services SharePoint</span><span class="sxs-lookup"><span data-stu-id="857e8-143">Manage a Reporting Services SharePoint Service Application</span></span>](../../2014/reporting-services/manage-a-reporting-services-sharepoint-service-application.md)|  
|<span data-ttu-id="857e8-144">Eseguire il backup e il ripristino dell'applicazione di servizio e dei componenti correlati, quali chiavi di crittografia e proxy.</span><span class="sxs-lookup"><span data-stu-id="857e8-144">Backup and restore the service application and related components such as encryption keys and proxy.</span></span>|[<span data-ttu-id="857e8-145">Eseguire il backup e il ripristino di applicazioni di servizio SharePoint di Reporting Services</span><span class="sxs-lookup"><span data-stu-id="857e8-145">Backup and Restore Reporting Services SharePoint Service Applications</span></span>](../../2014/reporting-services/backup-and-restore-reporting-services-sharepoint-service-applications.md)|  
