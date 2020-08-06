---
title: Eseguire il backup e il ripristino Reporting Services applicazioni di servizio SharePoint | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: dfb4ed77-90e5-4273-b690-89a945508ed2
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 488659d269542381be9bcf1b1b6115acf89f8a98
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628520"
---
# <a name="backup-and-restore-reporting-services-sharepoint-service-applications"></a><span data-ttu-id="a2d85-102">Eseguire il backup e il ripristino di applicazioni di servizio SharePoint di Reporting Services</span><span class="sxs-lookup"><span data-stu-id="a2d85-102">Backup and Restore Reporting Services SharePoint Service Applications</span></span>
  <span data-ttu-id="a2d85-103">In questo argomento vengono descritte le procedure di backup e ripristino di un'applicazione di servizio [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] tramite Amministrazione centrale SharePoint o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a2d85-103">This topic describes how to backup and restore a [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] services application using SharePoint Central Administration or PowerShell.</span></span> <span data-ttu-id="a2d85-104">Contenuto dell'argomento:</span><span class="sxs-lookup"><span data-stu-id="a2d85-104">The topic contains:</span></span>  
  
-   [<span data-ttu-id="a2d85-105">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="a2d85-105">Limitations and Restrictions</span></span>](#bkmk_Restrictions)  
  
-   [<span data-ttu-id="a2d85-106">Eseguire il backup dell'applicazione di servizio</span><span class="sxs-lookup"><span data-stu-id="a2d85-106">Backup The Service application</span></span>](#bkmk_backup)  
  
-   [<span data-ttu-id="a2d85-107">Ripristinare l'applicazione di servizio</span><span class="sxs-lookup"><span data-stu-id="a2d85-107">Restore the Service Application</span></span>](#bkmk_restore)  
  
##  <a name="before-you-begin"></a><a name="bkmk_BeforeYouBegin"></a> <span data-ttu-id="a2d85-108">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="a2d85-108">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="bkmk_Restrictions"></a> <span data-ttu-id="a2d85-109">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="a2d85-109">Limitations and Restrictions</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a2d85-110">È possibile eseguire il backup e il ripristino parziale delle applicazioni di servizio [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] tramite le funzionalità di backup e ripristino di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="a2d85-110">[!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service applications can partially be backed up and restored using the SharePoint backup and restore functionality.</span></span> <span data-ttu-id="a2d85-111">**Sono necessari passaggi aggiuntivi** , illustrati in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="a2d85-111">**Additional steps are required** and the steps are documented in this topic.</span></span> <span data-ttu-id="a2d85-112">Attualmente, tramite il processo di backup **non** viene eseguito il backup di credenziali e chiavi di crittografia per gli account di esecuzione automatica (UEA) o l'autenticazione di Windows nel database di [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a2d85-112">Currently the backup process **does not** backup encryption keys and credentials for unattended execution accounts (UEA) or windows authentication to the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] database.</span></span>  
  
###  <a name="recommendations"></a><a name="bkmk_recommendations"></a> <span data-ttu-id="a2d85-113">Indicazioni</span><span class="sxs-lookup"><span data-stu-id="a2d85-113">Recommendations</span></span>  
  
-   <span data-ttu-id="a2d85-114">Eseguire il backup delle chiavi di crittografia prima di avviare il backup di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="a2d85-114">Backup the encryption keys before starting the SharePoint backup.</span></span> <span data-ttu-id="a2d85-115">Se non si esegue il backup delle chiavi di crittografia, non sarà possibile accedere ai dati crittografati in seguito al ripristino dell'applicazione di servizio.</span><span class="sxs-lookup"><span data-stu-id="a2d85-115">If you do not backup the encryption keys, then you will not be able to access your encrypted data, following the restore of the service application.</span></span> <span data-ttu-id="a2d85-116">Sarà necessario eliminare i dati crittografati.</span><span class="sxs-lookup"><span data-stu-id="a2d85-116">You will need to delete your encrypted data.</span></span>  
  
-   <span data-ttu-id="a2d85-117">Verificare se nell'applicazione di servizio [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] viene utilizzato un account di esecuzione automatica o l'autenticazione di Windows per l'accesso al database.</span><span class="sxs-lookup"><span data-stu-id="a2d85-117">Verify if your [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service application is using UEA or Windows authentication for database access.</span></span> <span data-ttu-id="a2d85-118">In caso affermativo, verificare quali sono le credenziali appropriate, per poter configurare correttamente l'applicazione di servizio dopo il processo di ripristino.</span><span class="sxs-lookup"><span data-stu-id="a2d85-118">If it is using either, verify what the proper credentials are so you can correctly configure the service application after the restore process.</span></span>  
  
-   <span data-ttu-id="a2d85-119">Rivedere il log di backup di SharePoint creato nella stessa cartella del file di backup.</span><span class="sxs-lookup"><span data-stu-id="a2d85-119">Review the SharePoint backup log is created in the same folder as the backup file.</span></span> <span data-ttu-id="a2d85-120">Il file è in genere denominato **spbackup.log**</span><span class="sxs-lookup"><span data-stu-id="a2d85-120">The file is typically named **spbackup.log**</span></span>  
  
##  <a name="backup-the-service-application"></a><a name="bkmk_backup"></a><span data-ttu-id="a2d85-121">Eseguire il backup dell'applicazione di servizio</span><span class="sxs-lookup"><span data-stu-id="a2d85-121">Backup The Service application</span></span>  
 <span data-ttu-id="a2d85-122">Completare i passaggi seguenti nell'ordine indicato:</span><span class="sxs-lookup"><span data-stu-id="a2d85-122">Complete the following steps in order:</span></span>  
  
1.  <span data-ttu-id="a2d85-123">Eseguire il backup delle chiavi di crittografia</span><span class="sxs-lookup"><span data-stu-id="a2d85-123">Backup the encryption keys</span></span>  
  
2.  <span data-ttu-id="a2d85-124">Backup dell'applicazione di servizio</span><span class="sxs-lookup"><span data-stu-id="a2d85-124">Backup the Service application</span></span>  
  
3.  <span data-ttu-id="a2d85-125">Verificare se nell'applicazione di servizio viene utilizzato un account di esecuzione automatica o l'autenticazione di Windows per l'accesso al database.</span><span class="sxs-lookup"><span data-stu-id="a2d85-125">Verify if you service application uses an UEA or Windows authentication for database access.</span></span> <span data-ttu-id="a2d85-126">In caso affermativo, annotare le credenziali in modo da poterle utilizzare per configurare l'applicazione di servizio dopo il ripristino.</span><span class="sxs-lookup"><span data-stu-id="a2d85-126">If it does, make a note of the credentials so you can use them to configure the service application after it is restored.</span></span>  
  
### <a name="backup-the-encryption-keys-using-central-administration"></a><span data-ttu-id="a2d85-127">Eseguire il backup delle chiavi di crittografia tramite Amministrazione centrale</span><span class="sxs-lookup"><span data-stu-id="a2d85-127">Backup the Encryption Keys using Central Administration</span></span>  
 <span data-ttu-id="a2d85-128">Per informazioni sul backup delle [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] chiavi di crittografia, vedere la sezione "chiavi di crittografia" di [gestire un Reporting Services applicazione di servizio SharePoint](../../2014/reporting-services/manage-a-reporting-services-sharepoint-service-application.md).</span><span class="sxs-lookup"><span data-stu-id="a2d85-128">For information on backing up the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] encryption keys, see the "Encryption Keys" section of [Manage a Reporting Services SharePoint Service Application](../../2014/reporting-services/manage-a-reporting-services-sharepoint-service-application.md).</span></span>  
  
###  <a name="backup-the-service-application-using-sharepoint-central-administration"></a><a name="bkmk_centraladmin"></a> <span data-ttu-id="a2d85-129">Eseguire il backup dell'applicazione di servizio tramite Amministrazione centrale SharePoint</span><span class="sxs-lookup"><span data-stu-id="a2d85-129">Backup the Service application Using SharePoint Central Administration</span></span>  
 <span data-ttu-id="a2d85-130">Per eseguire il backup dell'applicazione di servizio, attenersi alla procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="a2d85-130">To back up the Service Application, complete the following steps:</span></span>  
  
1.  <span data-ttu-id="a2d85-131">In Amministrazione centrale SharePoint fare clic su **Esegui backup** nel gruppo **Backup e ripristino** .</span><span class="sxs-lookup"><span data-stu-id="a2d85-131">In SharePoint Central Administration Click **Perform a backup** in the **Backup and Restore** group.</span></span>  
  
2.  <span data-ttu-id="a2d85-132">Nel nodo **Servizi condivisi** espandere **Applicazioni di servizi condivisi** e selezionare l'applicazione di servizio.</span><span class="sxs-lookup"><span data-stu-id="a2d85-132">Under the **Shared Services** node, expand **Shared Service Applications** and select your service application.</span></span> <span data-ttu-id="a2d85-133">L'applicazione sarà di tipo **Applicazione di servizio SQL Server Reporting Services**.</span><span class="sxs-lookup"><span data-stu-id="a2d85-133">It will have a type of **SQL Server Reporting Services Service Application**.</span></span>  
  
3.  <span data-ttu-id="a2d85-134">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a2d85-134">Click **Next**.</span></span>  
  
4.  <span data-ttu-id="a2d85-135">Digitare il percorso in **Percorso backup** , quindi fare clic su **Avvia backup**.</span><span class="sxs-lookup"><span data-stu-id="a2d85-135">Type the path for the **Backup location:** and click **Start Backup**</span></span>  
  
5.  <span data-ttu-id="a2d85-136">Ripetere il processo precedente ma, anziché selezionare l'applicazione di servizio, espandere il nodo **Proxy servizi condivisi** e selezionare il proxy dell'applicazione di servizio.</span><span class="sxs-lookup"><span data-stu-id="a2d85-136">Repeat the process above but instead of selecting the service application, expand the **Shared Services Proxies** node, and select service application proxy.</span></span> <span data-ttu-id="a2d85-137">Il proxy sarà di tipo **Proxy dell'applicazione di servizio SQL Server Reporting Services**.</span><span class="sxs-lookup"><span data-stu-id="a2d85-137">It will have a type of **SQL Server Reporting Services Service Application Proxy**.</span></span>  
  
 <span data-ttu-id="a2d85-138">Per ulteriori informazioni, vedere gli argomenti seguenti nella documentazione di SharePoint:</span><span class="sxs-lookup"><span data-stu-id="a2d85-138">For more information, see the following topics in the SharePoint documentation:</span></span>  
  
 <span data-ttu-id="a2d85-139">[Eseguire il backup di un'applicazione di servizio (SharePoint Foundation 2010) nella documentazione di SharePoint](https://msdn.microsoft.com/library/ee748601.aspx).</span><span class="sxs-lookup"><span data-stu-id="a2d85-139">[Back up a service application (SharePoint Foundation 2010) in the SharePoint documenttation](https://msdn.microsoft.com/library/ee748601.aspx).</span></span>  
  
 [<span data-ttu-id="a2d85-140">Eseguire il backup di un'applicazione di servizio (SharePoint Server 2010)</span><span class="sxs-lookup"><span data-stu-id="a2d85-140">Back up a service application (SharePoint Server 2010)</span></span>](https://technet.microsoft.com/library/ee428318.aspx)  
  
### <a name="verify-execution-account-and-database-authentication"></a><span data-ttu-id="a2d85-141">Verificare l'account di esecuzione e l'autenticazione del database</span><span class="sxs-lookup"><span data-stu-id="a2d85-141">Verify Execution Account and Database Authentication</span></span>  
 <span data-ttu-id="a2d85-142">**Account di esecuzione:** per verificare se nell'applicazione di servizio viene utilizzato un account di esecuzione:</span><span class="sxs-lookup"><span data-stu-id="a2d85-142">**Execution Account:** To verify if your service application is using an execution account:</span></span>  
  
1.  <span data-ttu-id="a2d85-143">In Amministrazione centrale SharePoint fare clic su **Gestisci applicazioni di servizio** nel gruppo **Gestione applicazioni** .</span><span class="sxs-lookup"><span data-stu-id="a2d85-143">In SharePoint Central Administration, click **Manage Service Applications** in the **Application Management** group.</span></span>  
  
2.  <span data-ttu-id="a2d85-144">Fare clic sul nome dell'applicazione di servizio, quindi su **Gestisci** sulla barra multifunzione di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="a2d85-144">Click the name of your service application and then click **Manage** in the SharePoint Ribbon.</span></span>  
  
3.  <span data-ttu-id="a2d85-145">Fare clic su **Account di esecuzione**.</span><span class="sxs-lookup"><span data-stu-id="a2d85-145">Click **Execution Account**.</span></span>  
  
4.  <span data-ttu-id="a2d85-146">Se è configurato un account di esecuzione, è necessario conoscere le credenziali per ripristinare il backup dell'applicazione di servizio.</span><span class="sxs-lookup"><span data-stu-id="a2d85-146">If an execution account is configured, you need to know the credentials when it is time to restore the service application backup.</span></span> <span data-ttu-id="a2d85-147">Non procedere con le operazioni di backup e ripristino fino a quando non si conoscono le credenziali corrette.</span><span class="sxs-lookup"><span data-stu-id="a2d85-147">Do not proceed with the backup and restore procedure until you know the correct credentials.</span></span>  
  
 <span data-ttu-id="a2d85-148">**Autenticazione del database:** per verificare se nell'applicazione di servizio viene utilizzata l'autenticazione di Windows per l'autenticazione del database:</span><span class="sxs-lookup"><span data-stu-id="a2d85-148">**Database Authentication:** To verify if your service application is using Windows Authentication for the database authentication:</span></span>  
  
1.  <span data-ttu-id="a2d85-149">In Amministrazione centrale SharePoint fare clic su **Gestisci applicazioni di servizio** nel gruppo **Gestione applicazioni** .</span><span class="sxs-lookup"><span data-stu-id="a2d85-149">In SharePoint Central Administration, click **Manage Service Applications** in the **Application Management** group.</span></span>  
  
2.  <span data-ttu-id="a2d85-150">Fare clic sul nome dell'applicazione di servizio, quindi su **Proprietà** sulla barra multifunzione di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="a2d85-150">Click the name of your service application and then click **Properties** in the SharePoint Ribbon.</span></span>  
  
3.  <span data-ttu-id="a2d85-151">Analizzare la sezione **Database di servizio di SQL Server Reporting Services (SSRS)** .</span><span class="sxs-lookup"><span data-stu-id="a2d85-151">Review the **Reporting Services (SSRS) Service Database** section.</span></span>  
  
4.  <span data-ttu-id="a2d85-152">Se è configurata l'autenticazione di Windows, è necessario conoscere le credenziali per poter configurare l'applicazione di servizio dopo il ripristino.</span><span class="sxs-lookup"><span data-stu-id="a2d85-152">If Windows Authentication is configured, you need to know the credentials so you can configure the service application after you restore it.</span></span> <span data-ttu-id="a2d85-153">Non procedere con le operazioni di backup e ripristino fino a quando non si conoscono le credenziali corrette.</span><span class="sxs-lookup"><span data-stu-id="a2d85-153">Do not proceed with the backup and restore procedure until you know the correct credentials.</span></span>  
  
##  <a name="restore-the-service-application"></a><a name="bkmk_restore"></a><span data-ttu-id="a2d85-154">Ripristinare l'applicazione di servizio</span><span class="sxs-lookup"><span data-stu-id="a2d85-154">Restore the Service Application</span></span>  
 <span data-ttu-id="a2d85-155">Completare i passaggi seguenti nell'ordine indicato:</span><span class="sxs-lookup"><span data-stu-id="a2d85-155">Complete the following steps in order:</span></span>  
  
1.  <span data-ttu-id="a2d85-156">Ripristinare l'applicazione di servizio [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a2d85-156">Restore the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service application.</span></span>  
  
2.  <span data-ttu-id="a2d85-157">Ripristinare le chiavi di crittografia.</span><span class="sxs-lookup"><span data-stu-id="a2d85-157">Restore the encryption keys</span></span>  
  
3.  <span data-ttu-id="a2d85-158">Se nell'applicazione di servizio viene utilizzato un account di esecuzione o l'autenticazione di Windows per l'accesso al database, configurare le credenziali.</span><span class="sxs-lookup"><span data-stu-id="a2d85-158">If your service application was using an execution account or Windows authentication for database access, configure the credentials.</span></span>  
  
### <a name="restore-the-service-application-using-sharepoint-central-administration"></a><span data-ttu-id="a2d85-159">Ripristinare l'applicazione di servizio tramite Amministrazione centrale SharePoint</span><span class="sxs-lookup"><span data-stu-id="a2d85-159">Restore the Service application Using SharePoint Central Administration</span></span>  
  
1.  <span data-ttu-id="a2d85-160">In Amministrazione centrale SharePoint fare clic su **Ripristina da backup** nel gruppo **Backup e ripristino** .</span><span class="sxs-lookup"><span data-stu-id="a2d85-160">In SharePoint Central Administration Click **Restore from a backup** in the **Backup and Restore** group.</span></span>  
  
2.  <span data-ttu-id="a2d85-161">Digitare il percorso del file di backup nella casella **Percorso directory di backup** , quindi fare clic su **Aggiorna**.</span><span class="sxs-lookup"><span data-stu-id="a2d85-161">Type the path to your backup file in **Backup Directory Location** box and click **Refresh**.</span></span>  
  
3.  <span data-ttu-id="a2d85-162">Selezionare il backup dell'applicazione di servizio nell'elenco **Componente principale** , quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a2d85-162">Select your service application backup from the **Top Component** list and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="a2d85-163">Selezionare l'applicazione [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] , quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a2d85-163">Select your [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] application and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="a2d85-164">Nella sezione **Nomi e password di accesso** digitare la password per il nome di accesso.</span><span class="sxs-lookup"><span data-stu-id="a2d85-164">In the **Login Names and Passwords** section type the password for the login name.</span></span> <span data-ttu-id="a2d85-165">La casella del nome di accesso viene popolata con l'account di accesso utilizzato dall'applicazione di servizio prima del backup.</span><span class="sxs-lookup"><span data-stu-id="a2d85-165">The login name box should be populated with the login the service application was using prior to the backup.</span></span>  
  
6.  <span data-ttu-id="a2d85-166">Fare clic su **Avvia ripristino**.</span><span class="sxs-lookup"><span data-stu-id="a2d85-166">Click **Start Restore**.</span></span>  
  
7.  <span data-ttu-id="a2d85-167">Ripetere il processo precedente ma, anziché ripristinare l'applicazione di servizio, espandere il nodo **Servizi condivisi** , quindi il nodo **Applicazioni di servizi condivisi** .</span><span class="sxs-lookup"><span data-stu-id="a2d85-167">Repeat the process above but instead of restoring the service application, expand the **Shared Services** node and then expand the **Shared Service Applications** node.</span></span>  
  
 <span data-ttu-id="a2d85-168">Per ulteriori informazioni, vedere gli argomenti seguenti nella documentazione di SharePoint:</span><span class="sxs-lookup"><span data-stu-id="a2d85-168">For more information, see the following topics in the SharePoint documentation:</span></span>  
  
 <span data-ttu-id="a2d85-169">[Ripristinare un'applicazione di servizio (SharePoint Foundation 2010)](https://msdn.microsoft.com/library/ee748615.aspx).</span><span class="sxs-lookup"><span data-stu-id="a2d85-169">[Restore a service application (SharePoint Foundation 2010)](https://msdn.microsoft.com/library/ee748615.aspx).</span></span>  
  
 <span data-ttu-id="a2d85-170">[Ripristinare un'applicazione di servizio (SharePoint Server 2010)](https://technet.microsoft.com/library/ee428305.aspx).</span><span class="sxs-lookup"><span data-stu-id="a2d85-170">[Restore a service application (SharePoint Server 2010)](https://technet.microsoft.com/library/ee428305.aspx).</span></span>  
  
### <a name="restore-the-encryption-keys-using-central-administration"></a><span data-ttu-id="a2d85-171">Eseguire il ripristino delle chiavi di crittografia tramite Amministrazione centrale</span><span class="sxs-lookup"><span data-stu-id="a2d85-171">Restore the Encryption Keys using Central Administration</span></span>  
 <span data-ttu-id="a2d85-172">Per informazioni sul ripristino delle [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] chiavi di crittografia, vedere la sezione "chiavi di crittografia" di [gestire un'applicazione di servizio SharePoint Reporting Services](../../2014/reporting-services/manage-a-reporting-services-sharepoint-service-application.md).</span><span class="sxs-lookup"><span data-stu-id="a2d85-172">For information on restoring the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] encryption keys, see the "Encryption Keys" section of [Manage a Reporting Services SharePoint Service Application](../../2014/reporting-services/manage-a-reporting-services-sharepoint-service-application.md).</span></span>  
  
### <a name="configure-the-execution-account-and-database-authentication"></a><span data-ttu-id="a2d85-173">Configurare l'account di esecuzione e l'autenticazione del database</span><span class="sxs-lookup"><span data-stu-id="a2d85-173">Configure the Execution Account and Database Authentication</span></span>  
 <span data-ttu-id="a2d85-174">**Account di esecuzione:** se nell'applicazione di servizio viene utilizzato un account di esecuzione, attenersi alla procedura seguente per configurarlo:</span><span class="sxs-lookup"><span data-stu-id="a2d85-174">**Execution Account:** If your service application was using an execution account complete the following steps to configure it:</span></span>  
  
1.  <span data-ttu-id="a2d85-175">In Amministrazione centrale SharePoint fare clic su **Gestisci applicazioni di servizio** nel gruppo **Gestione applicazioni** .</span><span class="sxs-lookup"><span data-stu-id="a2d85-175">In SharePoint Central Administration, click **Manage Service Applications** in the **Application Management** group.</span></span>  
  
2.  <span data-ttu-id="a2d85-176">Fare clic sul nome dell'applicazione di servizio, quindi su **Gestisci** sulla barra multifunzione di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="a2d85-176">Click the name of your service application and then click **Manage** in the SharePoint Ribbon.</span></span>  
  
3.  <span data-ttu-id="a2d85-177">Fare clic su **Account di esecuzione**.</span><span class="sxs-lookup"><span data-stu-id="a2d85-177">Click **Execution Account**.</span></span>  
  
4.  <span data-ttu-id="a2d85-178">Digitare l'account e la password, quindi selezionare la casella **Specifica account di esecuzione** .</span><span class="sxs-lookup"><span data-stu-id="a2d85-178">Type the account, password, and select the **Specify and Execution Account** box.</span></span>  
  
5.  <span data-ttu-id="a2d85-179">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="a2d85-179">Click **OK**.</span></span>  
  
 <span data-ttu-id="a2d85-180">**Autenticazione del database:** se nell'applicazione di servizio viene utilizzata l'autenticazione di Windows per l'autenticazione del database, attenersi alla procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="a2d85-180">**Database Authentication:** If your service application was using Windows Authentication for the database authentication complete the following steps:</span></span>  
  
1.  <span data-ttu-id="a2d85-181">In Amministrazione centrale SharePoint fare clic su **Gestisci applicazioni di servizio** nel gruppo **Gestione applicazioni** .</span><span class="sxs-lookup"><span data-stu-id="a2d85-181">In SharePoint Central Administration click **Manage Service Applications** in the **Application Management** group.</span></span>  
  
2.  <span data-ttu-id="a2d85-182">Fare clic sul nome dell'applicazione di servizio, quindi su **Proprietà** sulla barra multifunzione di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="a2d85-182">Click the name of your service application and then click **Properties** in the SharePoint Ribbon.</span></span>  
  
3.  <span data-ttu-id="a2d85-183">Analizzare la sezione **Database di servizio di SQL Server Reporting Services (SSRS)** .</span><span class="sxs-lookup"><span data-stu-id="a2d85-183">Review the **Reporting Services (SSRS) Service Database** section.</span></span>  
  
4.  <span data-ttu-id="a2d85-184">Selezionare **Autenticazione di Windows**.</span><span class="sxs-lookup"><span data-stu-id="a2d85-184">Select **Windows Authentication**.</span></span>  
  
5.  <span data-ttu-id="a2d85-185">Digitare l'account e la password.</span><span class="sxs-lookup"><span data-stu-id="a2d85-185">Type the account and password.</span></span> <span data-ttu-id="a2d85-186">Selezionare **Usa come credenziali di Windows** , se appropriato.</span><span class="sxs-lookup"><span data-stu-id="a2d85-186">Select **Use as Windows Credentials** if appropriate.</span></span>  
  
6.  <span data-ttu-id="a2d85-187">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="a2d85-187">Click **Ok**</span></span>  
  
  
