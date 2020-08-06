---
title: Eseguire il provisioning di sottoscrizioni e avvisi per le applicazioni di servizio SSRS | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Reporting Services Shared Service
- SharePoint Mode [Reporting Services]
- SharePoint Mode
- Reporting Services Service Application
- SSRS service application
ms.assetid: d0de3f1f-4887-47fb-bacf-46aaad74c4be
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9c09033b6a31295b8fbe42058cba9059f5d05629
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726620"
---
# <a name="provision-subscriptions-and-alerts-for-ssrs-service-applications"></a><span data-ttu-id="0c64b-102">Provisioning di sottoscrizioni e avvisi per le applicazioni di servizio SSRS</span><span class="sxs-lookup"><span data-stu-id="0c64b-102">Provision Subscriptions and Alerts for SSRS Service Applications</span></span>
  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="0c64b-103">Le sottoscrizioni e gli avvisi dati richiedono SQL Server Agent e la configurazione di autorizzazioni per SQL Server Agent.</span><span class="sxs-lookup"><span data-stu-id="0c64b-103">subscriptions and data alerts require SQL Server Agent and require the configuration of permissions for SQL Server Agent.</span></span> <span data-ttu-id="0c64b-104">Se vengono visualizzati messaggi di errore indicanti che si richiede SQL Server Agent sebbene sia in esecuzione, aggiornare o verificare le autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="0c64b-104">If you see error messages that indicate SQL Server Agent is required and you have verified SQL Server Agent is running, then update or verify permissions.</span></span> <span data-ttu-id="0c64b-105">L'ambito di questo argomento è [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] in modalità SharePoint e vengono descritti tre modi per aggiornare le autorizzazioni di SQL Server Agent con sottoscrizioni di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0c64b-105">The scope of this topic is [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] in SharePoint mode and the topic describes three ways you can update the permissions of SQL Server Agent with [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] subscriptions.</span></span> <span data-ttu-id="0c64b-106">Le credenziali utilizzata nei passaggi di questo argomento devono disporre delle autorizzazioni sufficienti per concedere autorizzazioni di esecuzione a RSExecRole per gli oggetti nell'applicazione di servizio, il database msdb e database master.</span><span class="sxs-lookup"><span data-stu-id="0c64b-106">The credentials you use for the steps in this topic need to have sufficient permissions to grant execute permissions to the RSExecRole for objects in the service application, msdb, and master databases.</span></span>

||
|-|
|<span data-ttu-id="0c64b-107">**[!INCLUDE[applies](../../includes/applies-md.md)]** SharePoint 2013 &#124; SharePoint 2010</span><span class="sxs-lookup"><span data-stu-id="0c64b-107">**[!INCLUDE[applies](../../includes/applies-md.md)]**  SharePoint 2013 &#124; SharePoint 2010</span></span>|

 <span data-ttu-id="0c64b-108">![Autorizzazioni di SQL Agent per i database dell'applicazione di servizio](../../../2014/sql-server/install/media/rs-provisionsqlagent.gif "Autorizzazioni di SQL Agent per i database dell'applicazione di servizio")</span><span class="sxs-lookup"><span data-stu-id="0c64b-108">![SQL Agent permissions to Service Application DBs](../../../2014/sql-server/install/media/rs-provisionsqlagent.gif "SQL Agent permissions to Service Application DBs")</span></span>

||<span data-ttu-id="0c64b-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0c64b-109">Description</span></span>|
|------|-----------------|
|<span data-ttu-id="0c64b-110">**1**</span><span class="sxs-lookup"><span data-stu-id="0c64b-110">**1**</span></span>|<span data-ttu-id="0c64b-111">Istanza del motore di database di SQL Server che ospita i database dell'applicazione di servizio Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="0c64b-111">The instance of SQL Server Database engine that is hosting the Reporting Services service application databases.</span></span>|
|<span data-ttu-id="0c64b-112">**2**</span><span class="sxs-lookup"><span data-stu-id="0c64b-112">**2**</span></span>|<span data-ttu-id="0c64b-113">Istanza di SQL Server Agent per l'istanza del motore di database SQL.</span><span class="sxs-lookup"><span data-stu-id="0c64b-113">The instance of SQL Server agent for the instance of the SQL database engine.</span></span>|
|<span data-ttu-id="0c64b-114">**3**</span><span class="sxs-lookup"><span data-stu-id="0c64b-114">**3**</span></span>|<span data-ttu-id="0c64b-115">Database dell'applicazione di servizio Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="0c64b-115">The Reporting Services service application databases.</span></span> <span data-ttu-id="0c64b-116">I nomi si basano sulle informazioni utilizzate per creare l'applicazione di servizio.</span><span class="sxs-lookup"><span data-stu-id="0c64b-116">The names are based on the information used for creating the service application.</span></span> <span data-ttu-id="0c64b-117">Di seguito sono riportati esempi di nomi di database:</span><span class="sxs-lookup"><span data-stu-id="0c64b-117">The following are example database names:</span></span><br /><br /> <span data-ttu-id="0c64b-118">ReportingService_2fbae157295d49df86d0b85760c704b0</span><span class="sxs-lookup"><span data-stu-id="0c64b-118">ReportingService_2fbae157295d49df86d0b85760c704b0</span></span><br /><br /> <span data-ttu-id="0c64b-119">ReportingService_2fbae157295d49df86d0b85760c704b0_Alerting</span><span class="sxs-lookup"><span data-stu-id="0c64b-119">ReportingService_2fbae157295d49df86d0b85760c704b0_Alerting</span></span><br /><br /> <span data-ttu-id="0c64b-120">ReportingService_2fbae157295d49df86d0b85760c704b0TempDB</span><span class="sxs-lookup"><span data-stu-id="0c64b-120">ReportingService_2fbae157295d49df86d0b85760c704b0TempDB</span></span>|
|<span data-ttu-id="0c64b-121">**4**</span><span class="sxs-lookup"><span data-stu-id="0c64b-121">**4**</span></span>|<span data-ttu-id="0c64b-122">Il database master e MSDB dell'istanza del motore di database SQL Server.</span><span class="sxs-lookup"><span data-stu-id="0c64b-122">The master and MSDB database of the instance of the SQL Server Database engine.</span></span>|

 <span data-ttu-id="0c64b-123">Utilizzare uno dei tre metodi seguenti per aggiornare le autorizzazioni:</span><span class="sxs-lookup"><span data-stu-id="0c64b-123">Use one the following three methods to update the permissions:</span></span>

1.  <span data-ttu-id="0c64b-124">Digitare le credenziali nella pagina **Avvisi e sottoscrizioni provisioning** e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="0c64b-124">From the **Provisions and Subscriptions and Alerts** page, type credentials and click **ok**.</span></span>

2.  <span data-ttu-id="0c64b-125">Nella pagina Avvisi e sottoscrizioni provisioning, fare clic sul pulsante **Download script** per scaricare uno script Transact-SQL che può essere usato per configurare le autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="0c64b-125">From the Provisions and Subscriptions and Alerts page, click the **Download Script** button to download a transact SQL script that can be used to configure permissions.</span></span>

3.  <span data-ttu-id="0c64b-126">Eseguire un cmdlet di PowerShell per compilare uno script Transact-SQL che può essere utilizzato per configurare le autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="0c64b-126">Run a PowerShell cmdlet to build a transact SQL script that can be used to configure permissions.</span></span>

### <a name="to-update-permissions-using-the-provision-page"></a><span data-ttu-id="0c64b-127">Per aggiornare le autorizzazioni utilizzando la pagina di provisioning</span><span class="sxs-lookup"><span data-stu-id="0c64b-127">To update permissions using the provision page</span></span>

1.  <span data-ttu-id="0c64b-128">Nel gruppo **Gestione applicazioni** di Amministrazione centrale SharePoint fare clic su **Gestisci applicazioni di servizio**.</span><span class="sxs-lookup"><span data-stu-id="0c64b-128">From SharePoint Central Administration, in the **Application Management** group click **Manage Service Applications**</span></span>

2.  <span data-ttu-id="0c64b-129">Individuare l'applicazione di servizio nell'elenco e fare clic sul nome dell'applicazione oppure fare clic sulla colonna **Tipo** per selezionare l'applicazione di servizio e fare clic sul pulsante **Gestisci** nella barra multifunzione di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="0c64b-129">Find your service application in the list and click the name of the application or click the **Type** column to select the services application and click the **Manage** button in the SharePoint ribbon.</span></span>

3.  <span data-ttu-id="0c64b-130">Fare clic su **Avvisi e sottoscrizioni provisioning** nella pagina **Gestione applicazione di Reporting Services**.</span><span class="sxs-lookup"><span data-stu-id="0c64b-130">On the **Manage Reporting Services Application** page, click **Provision Subscriptions and Alerts**.</span></span>

4.  <span data-ttu-id="0c64b-131">Digitare le credenziali dell'amministratore di SharePoint se sufficienti per accedere al database master e ai database dell'applicazione di servizio.</span><span class="sxs-lookup"><span data-stu-id="0c64b-131">If the SharePoint administrator has enough privileges to the Master database and the service application databases, type those credentials.</span></span>

5.  <span data-ttu-id="0c64b-132">Fare clic sul pulsante **OK** .</span><span class="sxs-lookup"><span data-stu-id="0c64b-132">Click the **OK** button.</span></span>

##  <a name="to-download-the-transact-sql-script"></a><a name="bkmk_download"></a> <span data-ttu-id="0c64b-133">Per scaricare lo script Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="0c64b-133">To download the Transact-SQL Script</span></span>

1.  <span data-ttu-id="0c64b-134">Nel gruppo **Gestione applicazioni** di Amministrazione centrale SharePoint fare clic su **Gestisci applicazioni di servizio**.</span><span class="sxs-lookup"><span data-stu-id="0c64b-134">From SharePoint Central Administration, in the **Application Management** group click **Manage Service Applications**</span></span>

2.  <span data-ttu-id="0c64b-135">Individuare l'applicazione di servizio nell'elenco e fare clic sul nome dell'applicazione oppure fare clic sulla colonna **Tipo** per selezionare l'applicazione di servizio e fare clic sul pulsante **Gestisci** nella barra multifunzione di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="0c64b-135">Find your service application in the list and click the name of the application or click the **Type** column to select the services application and click the **Manage** button in the SharePoint ribbon.</span></span>

3.  <span data-ttu-id="0c64b-136">Fare clic su **Avvisi e sottoscrizioni provisioning** nella pagina **Gestione applicazione di Reporting Services**.</span><span class="sxs-lookup"><span data-stu-id="0c64b-136">On the **Manage Reporting Services Application** page, click **Provision Subscriptions and Alerts**.</span></span>

4.  <span data-ttu-id="0c64b-137">Verificare che SQL Server Agent sia in esecuzione nell'area **Visualizzazione stato** .</span><span class="sxs-lookup"><span data-stu-id="0c64b-137">In the **View Status** area, verify SQL Server Agent is running.</span></span>

5.  <span data-ttu-id="0c64b-138">Fare clic su **Download script** per scaricare uno script Transact-SQL che può essere eseguito in SQL Server Management Studio per concedere le autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="0c64b-138">Click **Download Script** to download a transact SQL script you can run in SQL Server Management studio to grant permissions.</span></span> <span data-ttu-id="0c64b-139">Il nome del file script creato contiene il nome dell'applicazione di servizio di Reporting Services, ad esempio **[nome dell'applicazione di servizio]-GrantRights.sql**.</span><span class="sxs-lookup"><span data-stu-id="0c64b-139">The script file name that is created will contain the name of your Reporting Services service application name, for example **[name of the service application]-GrantRights.sql**.</span></span>

### <a name="to-generate-the-transact-sql-statement-with-powershell"></a><span data-ttu-id="0c64b-140">Per generare l'istruzione Transact-SQL con PowerShell</span><span class="sxs-lookup"><span data-stu-id="0c64b-140">To generate the Transact-SQL statement with PowerShell</span></span>

1.  <span data-ttu-id="0c64b-141">È possibile utilizzare un cmdlet di Windows PowerShell nella shell di gestione di SharePoint 2010 anche per creare uno script Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="0c64b-141">You can also use a Windows PowerShell cmdlet in the SharePoint 2010 Management Shell to create the Transact-SQL script.</span></span>

2.  <span data-ttu-id="0c64b-142">Scegliere **Tutti i programmi** dal menu **Start**.</span><span class="sxs-lookup"><span data-stu-id="0c64b-142">On the **Start** menu, click **All Programs**.</span></span>

3.  <span data-ttu-id="0c64b-143">Espandere **prodotti Microsoft sharepoint 2010** e fare clic su **SharePoint 2010 Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="0c64b-143">Expand **Microsoft SharePoint 2010 Products** and click **SharePoint 2010 Management Shell**.</span></span>

4.  <span data-ttu-id="0c64b-144">Aggiornare il seguente cmdlet di PowerShell sostituendo il nome del database del server di report, l'account del pool di applicazioni e il percorso dell'istruzione.</span><span class="sxs-lookup"><span data-stu-id="0c64b-144">Update the following PowerShell cmdlet by replacing the name of the report server database, application pool account, and the path of the statement.</span></span>

     <span data-ttu-id="0c64b-145">**Sintassi del cmdlet:** `Get-SPRSDatabaseRightsScript -DatabaseName <ReportingServices database name> -UserName <app pool account> -IsWindowsUser | Out-File <path of statement>`</span><span class="sxs-lookup"><span data-stu-id="0c64b-145">**Syntax of cmdlet:** `Get-SPRSDatabaseRightsScript -DatabaseName <ReportingServices database name> -UserName <app pool account> -IsWindowsUser | Out-File <path of statement>`</span></span>

     <span data-ttu-id="0c64b-146">**Cmdlet di esempio:** `Get-SPRSDatabaseRightsScript -DatabaseName ReportingService_46fd00359f894b828907b254e3f6257c -UserName "NT AUTHORITY\NETWORK SERVICE" -IsWindowsUser | Out-File c:\SQLServerAgentrights.sql`</span><span class="sxs-lookup"><span data-stu-id="0c64b-146">**Sample cmdlet:** `Get-SPRSDatabaseRightsScript -DatabaseName ReportingService_46fd00359f894b828907b254e3f6257c -UserName "NT AUTHORITY\NETWORK SERVICE" -IsWindowsUser | Out-File c:\SQLServerAgentrights.sql`</span></span>

## <a name="using-the-transact-sql-script"></a><span data-ttu-id="0c64b-147">Utilizzo dello script Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="0c64b-147">Using the Transact-SQL Script</span></span>
 <span data-ttu-id="0c64b-148">Le seguenti procedure possono essere utilizzate con gli script scaricati dalla pagina di provisioning o creati tramite PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0c64b-148">The following procedures can be used with scripts download from the provisions page or scripts created using PowerShell.</span></span>

#### <a name="to-load-the-transact-sql-script-in-sql-server-management-studio"></a><span data-ttu-id="0c64b-149">Per caricare lo script Transact-SQL in SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="0c64b-149">To load the Transact-SQL script in SQL Server Management Studio</span></span>

1.  <span data-ttu-id="0c64b-150">Per aprire SQL Server Management Studio, fare clic sul menu **Start** , scegliere **Microsoft SQL Server 2012** e fare clic su **SQL Server Management Studio**.</span><span class="sxs-lookup"><span data-stu-id="0c64b-150">To open SQL Server Management Studio, on the **Start** menu, click **Microsoft SQL Server 2012** and click **SQL Server Management Studio**.</span></span>

2.  <span data-ttu-id="0c64b-151">Nella finestra di dialogo **Connetti al server** impostare le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0c64b-151">In the **Connect to Server** dialog box set the following options:</span></span>

    -   <span data-ttu-id="0c64b-152">Nell'elenco **Tipo server** selezionare **Motore di database**.</span><span class="sxs-lookup"><span data-stu-id="0c64b-152">In the **Server type** list, select **Database Engine**</span></span>

    -   <span data-ttu-id="0c64b-153">Nella casella **Nome server**digitare il nome dell'istanza di SQL Server in cui si desidera configurare SQL Server Agent.</span><span class="sxs-lookup"><span data-stu-id="0c64b-153">In **Server Name**, type the name of the SQL Server instance on which you want to configure SQL Server Agent.</span></span>

    -   <span data-ttu-id="0c64b-154">Selezionare una modalità di autenticazione.</span><span class="sxs-lookup"><span data-stu-id="0c64b-154">Select an authentication mode.</span></span>

    -   <span data-ttu-id="0c64b-155">Se ci si connette utilizzando l'autenticazione di SQL Server, specificare un account e una password.</span><span class="sxs-lookup"><span data-stu-id="0c64b-155">If connecting using SQL Server Authentication, provide a login and password.</span></span>

3.  <span data-ttu-id="0c64b-156">Fare clic su **Connetti**.</span><span class="sxs-lookup"><span data-stu-id="0c64b-156">Click **Connect**.</span></span>

#### <a name="to-run-the-transact-sql-statement"></a><span data-ttu-id="0c64b-157">Per eseguire l'istruzione Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="0c64b-157">To run the Transact-SQL statement</span></span>

1.  <span data-ttu-id="0c64b-158">Fare clic su **Nuova query**nella barra degli strumenti di SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="0c64b-158">On the toolbar of SQL Server Management Studio, click **New Query**.</span></span>

2.  <span data-ttu-id="0c64b-159">Scegliere **Apri** dal menu **File**e quindi fare clic su **File**.</span><span class="sxs-lookup"><span data-stu-id="0c64b-159">On the **File** menu, click **Open**, and then click **File**.</span></span>

3.  <span data-ttu-id="0c64b-160">Passare alla cartella in cui è stata salvata l'istruzione Transact-SQL generata nella shell di gestione di SharePoint 2010.</span><span class="sxs-lookup"><span data-stu-id="0c64b-160">Navigate to the folder where you saved the Transact-SQL statement that you generated in SharePoint 2010 Management Shell.</span></span>

4.  <span data-ttu-id="0c64b-161">Selezionare il file, quindi fare clic su **Apri**.</span><span class="sxs-lookup"><span data-stu-id="0c64b-161">Click the file and then click **Open**.</span></span>

     <span data-ttu-id="0c64b-162">L'istruzione viene aggiunta alla finestra della query.</span><span class="sxs-lookup"><span data-stu-id="0c64b-162">The statement is added to the query window.</span></span>

5.  <span data-ttu-id="0c64b-163">Fare clic su **Execute**.</span><span class="sxs-lookup"><span data-stu-id="0c64b-163">Click **Execute**.</span></span>


