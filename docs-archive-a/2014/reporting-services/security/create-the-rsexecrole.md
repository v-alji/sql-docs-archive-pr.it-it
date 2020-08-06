---
title: Creare RSExecRole | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- RSExecRole
ms.assetid: 7ac17341-df7e-4401-870e-652caa2859c0
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 0037ef0c4d7a949b5a30bb45356613f6114db130
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715080"
---
# <a name="create-the-rsexecrole"></a><span data-ttu-id="bb52c-102">Creare RSExecRole</span><span class="sxs-lookup"><span data-stu-id="bb52c-102">Create the RSExecRole</span></span>
  <span data-ttu-id="bb52c-103">In [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] viene utilizzato un ruolo del database predefinito denominato `RSExecRole` che consente di concedere autorizzazioni del server di report al database relativo.</span><span class="sxs-lookup"><span data-stu-id="bb52c-103">[!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] uses a predefined database role called `RSExecRole` to grant report server permissions to the report server database.</span></span> <span data-ttu-id="bb52c-104">Il `RSExecRole` ruolo viene creato automaticamente con il database del server di report.</span><span class="sxs-lookup"><span data-stu-id="bb52c-104">The `RSExecRole` role is created automatically with the report server database.</span></span> <span data-ttu-id="bb52c-105">Si consiglia di non modificare mai né di assegnare utenti a tale ruolo.</span><span class="sxs-lookup"><span data-stu-id="bb52c-105">As a rule, you should never modify it or assign other users to the role.</span></span> <span data-ttu-id="bb52c-106">Tuttavia, quando si sposta un database del server di report in un nuovo o diverso [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../../includes/ssde-md.md)] , è necessario creare nuovamente il ruolo nei database di sistema master e msdb.</span><span class="sxs-lookup"><span data-stu-id="bb52c-106">However, when you move a report server database to a new or different [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../../includes/ssde-md.md)], must re-create the role in the Master and MSDB system databases.</span></span>

 <span data-ttu-id="bb52c-107">Utilizzando le istruzioni indicate di seguito, verranno effettuate le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="bb52c-107">Using the following instructions, you will perform the following steps:</span></span>

-   <span data-ttu-id="bb52c-108">Creazione ed esecuzione del provisioning di `RSExecRole` nel database di sistema master.</span><span class="sxs-lookup"><span data-stu-id="bb52c-108">Create and provision the `RSExecRole` in the Master system database.</span></span>

-   <span data-ttu-id="bb52c-109">Creazione ed esecuzione del provisioning di `RSExecRole` nel database di sistema MSDB.</span><span class="sxs-lookup"><span data-stu-id="bb52c-109">Create and provision the `RSExecRole` in the MSDB system database.</span></span>

> [!NOTE]
>  <span data-ttu-id="bb52c-110">Le istruzioni contenute in questo argomento sono destinate agli utenti che non desiderano eseguire uno script o scrivere codice WMI per effettuare il provisioning del database del server di report.</span><span class="sxs-lookup"><span data-stu-id="bb52c-110">The instructions in this topic are intended for users who do not want to run a script or write WMI code to provision the report server database.</span></span> <span data-ttu-id="bb52c-111">Se si gestisce una distribuzione di dimensioni elevate e i database verranno spostati regolarmente, è consigliabile scrivere uno script per automatizzare questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="bb52c-111">If you manage a large deployment and will be moving databases routinely, you should write a script to automate these steps.</span></span> <span data-ttu-id="bb52c-112">Per altre informazioni, vedere [Accedere al provider WMI per Reporting Services](../tools/access-the-reporting-services-wmi-provider.md).</span><span class="sxs-lookup"><span data-stu-id="bb52c-112">For more information, see [Access the Reporting Services WMI Provider](../tools/access-the-reporting-services-wmi-provider.md).</span></span>

## <a name="before-you-start"></a><span data-ttu-id="bb52c-113">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="bb52c-113">Before you start</span></span>

-   <span data-ttu-id="bb52c-114">Eseguire il backup delle chiavi di crittografia in modo che sia possibile ripristinarle dopo che il database è stato spostato.</span><span class="sxs-lookup"><span data-stu-id="bb52c-114">Back up the encryption keys so that you can restore them after the database is moved.</span></span> <span data-ttu-id="bb52c-115">Questo passaggio non influisce direttamente sulla possibilità di creare e di effettuare il provisioning di `RSExecRole`, ma è necessario disporre di una copia di backup delle chiavi per verificare il proprio lavoro.</span><span class="sxs-lookup"><span data-stu-id="bb52c-115">This is step does not directly affect your ability to create and provision the `RSExecRole`, but you must have a backup of the keys in order to verify your work.</span></span> <span data-ttu-id="bb52c-116">Per altre informazioni, vedere [Eseguire il backup e il ripristino delle chiavi di crittografia di Reporting Services](../install-windows/ssrs-encryption-keys-back-up-and-restore-encryption-keys.md).</span><span class="sxs-lookup"><span data-stu-id="bb52c-116">For more information, see [Back Up and Restore Reporting Services Encryption Keys](../install-windows/ssrs-encryption-keys-back-up-and-restore-encryption-keys.md).</span></span>

-   <span data-ttu-id="bb52c-117">Verificare di avere eseguito l'accesso con un account utente che dispone delle autorizzazioni `sysadmin` sull'istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bb52c-117">Verify you are logged on as a user account that has `sysadmin` permissions on the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance.</span></span>

-   <span data-ttu-id="bb52c-118">Verificare che il servizio [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent sia installato e che sia in esecuzione nell'istanza del [!INCLUDE[ssDE](../../../includes/ssde-md.md)] che si intende utilizzare.</span><span class="sxs-lookup"><span data-stu-id="bb52c-118">Verify [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent service is installed and running on the instance of the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] instance that you plan to use.</span></span>

-   <span data-ttu-id="bb52c-119">Collegare i database reportservertempdb e reportserver.</span><span class="sxs-lookup"><span data-stu-id="bb52c-119">Attach the reportservertempdb and reportserver databases.</span></span> <span data-ttu-id="bb52c-120">Non è necessario collegare i database per creare il ruolo effettivo, ma è necessario che siano collegati prima che sia possibile eseguire il test del proprio lavoro.</span><span class="sxs-lookup"><span data-stu-id="bb52c-120">You are not required to attach the databases to create the actual role, but they must be attached before you can test your work.</span></span>

 <span data-ttu-id="bb52c-121">Le istruzioni per la creazione manuale di `RSExecRole` devono essere utilizzate nel contesto dell'esecuzione della migrazione di un'installazione del server di report.</span><span class="sxs-lookup"><span data-stu-id="bb52c-121">The instructions for manually creating the `RSExecRole` are intended to be used within the context of migrating a report server installation.</span></span> <span data-ttu-id="bb52c-122">Attività importanti come l'esecuzione del backup e lo spostamento del database del server di report non vengono descritte in questo argomento, ma nella documentazione del Motore di database.</span><span class="sxs-lookup"><span data-stu-id="bb52c-122">Important tasks such as backing up and moving the report server database are not addressed in this topic, but are documented in the Database Engine documentation.</span></span>

## <a name="create-rsexecrole-in-master"></a><span data-ttu-id="bb52c-123">Creazione di RSExecRole nel database master</span><span class="sxs-lookup"><span data-stu-id="bb52c-123">Create RSExecRole in Master</span></span>
 [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] <span data-ttu-id="bb52c-124">supporti operazioni pianificate, in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] vengono utilizzate stored procedure estese.</span><span class="sxs-lookup"><span data-stu-id="bb52c-124">uses extended stored procedures for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent service to support scheduled operations.</span></span> <span data-ttu-id="bb52c-125">I passaggi seguenti illustrano come concedere autorizzazioni di esecuzione per le procedure al ruolo `RSExecRole`.</span><span class="sxs-lookup"><span data-stu-id="bb52c-125">The following steps explain how to grant Execute permissions for the procedures to the `RSExecRole` role.</span></span>

#### <a name="to-create-rsexecrole-in-the-master-system-database-using-management-studio"></a><span data-ttu-id="bb52c-126">Per creare RSExecRole nel database di sistema master mediante Management Studio</span><span class="sxs-lookup"><span data-stu-id="bb52c-126">To create RSExecRole in the Master system database using Management Studio</span></span>

1.  <span data-ttu-id="bb52c-127">Avviare [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], quindi connettersi all'istanza del [!INCLUDE[ssDE](../../../includes/ssde-md.md)] in cui è ospitato il database del server di report.</span><span class="sxs-lookup"><span data-stu-id="bb52c-127">Start [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] and connect to the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] instance that hosts the report server database.</span></span>

2.  <span data-ttu-id="bb52c-128">Aprire **Database**.</span><span class="sxs-lookup"><span data-stu-id="bb52c-128">Open **Databases**.</span></span>

3.  <span data-ttu-id="bb52c-129">Aprire **Database di sistema**.</span><span class="sxs-lookup"><span data-stu-id="bb52c-129">Open **System Databases**.</span></span>

4.  <span data-ttu-id="bb52c-130">Aprire `Master`.</span><span class="sxs-lookup"><span data-stu-id="bb52c-130">Open `Master`.</span></span>

5.  <span data-ttu-id="bb52c-131">Aprire **Sicurezza**.</span><span class="sxs-lookup"><span data-stu-id="bb52c-131">Open **Security**.</span></span>

6.  <span data-ttu-id="bb52c-132">Aprire **Ruoli**.</span><span class="sxs-lookup"><span data-stu-id="bb52c-132">Open **Roles**.</span></span>

7.  <span data-ttu-id="bb52c-133">Fare clic con il pulsante destro del mouse su **Ruoli del database**, quindi scegliere **Nuovo ruolo database**.</span><span class="sxs-lookup"><span data-stu-id="bb52c-133">Right-click **Database Roles**, and select **New Database Role**.</span></span> <span data-ttu-id="bb52c-134">Verrà visualizzata la pagina Generale.</span><span class="sxs-lookup"><span data-stu-id="bb52c-134">The General page appears.</span></span>

8.  <span data-ttu-id="bb52c-135">In **nome ruolo**Digitare `RSExecRole` .</span><span class="sxs-lookup"><span data-stu-id="bb52c-135">In **Role name**, type `RSExecRole`.</span></span>

9. <span data-ttu-id="bb52c-136">In **Proprietario**digitare **DBO**.</span><span class="sxs-lookup"><span data-stu-id="bb52c-136">In **Owner**, type **DBO**.</span></span>

10. <span data-ttu-id="bb52c-137">Fare clic su **Entità a sicurezza diretta**.</span><span class="sxs-lookup"><span data-stu-id="bb52c-137">Click **Securables**.</span></span>

11. <span data-ttu-id="bb52c-138">Fare clic su **Cerca**.</span><span class="sxs-lookup"><span data-stu-id="bb52c-138">Click **Search**.</span></span> <span data-ttu-id="bb52c-139">Verrà visualizzata la finestra di dialogo **Aggiungi oggetti** .</span><span class="sxs-lookup"><span data-stu-id="bb52c-139">The **Add Objects** dialog box appears.</span></span> <span data-ttu-id="bb52c-140">L'opzione **Specifica oggetti** è selezionata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="bb52c-140">The **Specific Objects** option is selected by default.</span></span>

12. <span data-ttu-id="bb52c-141">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="bb52c-141">Click **OK**.</span></span> <span data-ttu-id="bb52c-142">Verrà visualizzata la finestra di dialogo **Seleziona oggetti** .</span><span class="sxs-lookup"><span data-stu-id="bb52c-142">The **Select Objects** dialog box appears.</span></span>

13. <span data-ttu-id="bb52c-143">Fare clic su **Tipi di oggetti**.</span><span class="sxs-lookup"><span data-stu-id="bb52c-143">Click **Object Types**.</span></span>

14. <span data-ttu-id="bb52c-144">Fare clic su **Stored procedure estese**.</span><span class="sxs-lookup"><span data-stu-id="bb52c-144">Click **Extended Stored Procedures**.</span></span>

15. <span data-ttu-id="bb52c-145">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="bb52c-145">Click **OK**.</span></span>

16. <span data-ttu-id="bb52c-146">Fare clic su **Sfoglia**.</span><span class="sxs-lookup"><span data-stu-id="bb52c-146">Click **Browse**.</span></span>

17. <span data-ttu-id="bb52c-147">Scorrere l'elenco delle stored procedure estese e selezionare gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="bb52c-147">Scroll down the list of extended stored procedures and select the following:</span></span>

    1.  <span data-ttu-id="bb52c-148">xp_sqlagent_enum_jobs</span><span class="sxs-lookup"><span data-stu-id="bb52c-148">xp_sqlagent_enum_jobs</span></span>

    2.  <span data-ttu-id="bb52c-149">xp_sqlagent_is_starting</span><span class="sxs-lookup"><span data-stu-id="bb52c-149">xp_sqlagent_is_starting</span></span>

    3.  <span data-ttu-id="bb52c-150">xp_sqlagent_notify</span><span class="sxs-lookup"><span data-stu-id="bb52c-150">xp_sqlagent_notify</span></span>

18. <span data-ttu-id="bb52c-151">Fare clic su **OK**, quindi fare di nuovo clic su **OK** .</span><span class="sxs-lookup"><span data-stu-id="bb52c-151">Click **OK**, and the click **OK** again.</span></span>

19. <span data-ttu-id="bb52c-152">Nella colonna **Concedi** della riga **Esegui** selezionare la casella di controllo, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="bb52c-152">In the **Execute** row, in the **Grant** column, click the check box, and then click **OK**.</span></span>

20. <span data-ttu-id="bb52c-153">Ripetere il passaggio per ognuna delle stored procedure rimanenti.</span><span class="sxs-lookup"><span data-stu-id="bb52c-153">Repeat for each of the remaining stored procedures.</span></span> <span data-ttu-id="bb52c-154">A `RSExecRole` devono essere concesse le autorizzazioni di esecuzione per tutte le tre stored procedure.</span><span class="sxs-lookup"><span data-stu-id="bb52c-154">`RSExecRole` must be granted Execute permissions for all three stored procedures.</span></span>

 <span data-ttu-id="bb52c-155">![Pagina Proprietà ruolo database](../media/rsexecroledbproperties.gif "Pagina Proprietà ruolo database")</span><span class="sxs-lookup"><span data-stu-id="bb52c-155">![Database Role Properties page](../media/rsexecroledbproperties.gif "Database Role Properties page")</span></span>

## <a name="create-rsexecrole-in-msdb"></a><span data-ttu-id="bb52c-156">Creazione di RSExecRole nel database MSDB</span><span class="sxs-lookup"><span data-stu-id="bb52c-156">Create RSExecRole in MSDB</span></span>
 <span data-ttu-id="bb52c-157">Per supportare operazioni pianificate, in Reporting Services vengono utilizzate le stored procedure per il servizio SQL Server Agent e le informazioni sul processo vengono recuperate dalle tabelle di sistema.</span><span class="sxs-lookup"><span data-stu-id="bb52c-157">Reporting Services uses stored procedures for SQL Server Agent service and retrieves job information from system tables to support scheduled operations.</span></span> <span data-ttu-id="bb52c-158">I passaggi seguenti illustrano come concedere autorizzazioni di esecuzione per le procedure e autorizzazioni di selezione sulle tabelle a RSExecRole.</span><span class="sxs-lookup"><span data-stu-id="bb52c-158">The following steps explain how to grant Execute permissions for the procedures and Select permissions on the tables to the RSExecRole.</span></span>

#### <a name="to-create-rsexecrole-in-the-msdb-system-database"></a><span data-ttu-id="bb52c-159">Per creare RSExecRole nel database di sistema MSDB</span><span class="sxs-lookup"><span data-stu-id="bb52c-159">To create RSExecRole in the MSDB system database</span></span>

1.  <span data-ttu-id="bb52c-160">Ripetere passaggi analoghi per concedere le autorizzazioni alle stored procedure e alle tabelle nel database MSDB.</span><span class="sxs-lookup"><span data-stu-id="bb52c-160">Repeat similar steps for granting permissions to stored procedures and tables in MSDB.</span></span> <span data-ttu-id="bb52c-161">Per semplificare i passaggi, il provisioning delle stored procedure e delle tabelle verrà effettuato separatamente.</span><span class="sxs-lookup"><span data-stu-id="bb52c-161">To simplify the steps, you will provision the stored procedures and tables separately.</span></span>

2.  <span data-ttu-id="bb52c-162">Aprire `MSDB`.</span><span class="sxs-lookup"><span data-stu-id="bb52c-162">Open `MSDB`.</span></span>

3.  <span data-ttu-id="bb52c-163">Aprire **Sicurezza**.</span><span class="sxs-lookup"><span data-stu-id="bb52c-163">Open **Security**.</span></span>

4.  <span data-ttu-id="bb52c-164">Aprire **Ruoli**.</span><span class="sxs-lookup"><span data-stu-id="bb52c-164">Open **Roles**.</span></span>

5.  <span data-ttu-id="bb52c-165">Fare clic con il pulsante destro del mouse su **Ruoli del database**, quindi scegliere **Nuovo ruolo database**.</span><span class="sxs-lookup"><span data-stu-id="bb52c-165">Right-click **Database Roles**, and select **New Database Role**.</span></span> <span data-ttu-id="bb52c-166">Verrà visualizzata la pagina Generale.</span><span class="sxs-lookup"><span data-stu-id="bb52c-166">The General page appears.</span></span>

6.  <span data-ttu-id="bb52c-167">In nome ruolo digitare `RSExecRole` .</span><span class="sxs-lookup"><span data-stu-id="bb52c-167">In Role name, type `RSExecRole`.</span></span>

7.  <span data-ttu-id="bb52c-168">In proprietario digitare **dbo**.</span><span class="sxs-lookup"><span data-stu-id="bb52c-168">In Owner, type **DBO**.</span></span>

8.  <span data-ttu-id="bb52c-169">Fare clic su **Entità a sicurezza diretta**.</span><span class="sxs-lookup"><span data-stu-id="bb52c-169">Click **Securables**.</span></span>

9. <span data-ttu-id="bb52c-170">Scegliere **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="bb52c-170">Click **Add**.</span></span> <span data-ttu-id="bb52c-171">Verrà visualizzata la finestra di dialogo **Aggiungi oggetti** .</span><span class="sxs-lookup"><span data-stu-id="bb52c-171">The **Add Objects** dialog box appears.</span></span> <span data-ttu-id="bb52c-172">L'opzione **Specifica oggetti** è selezionata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="bb52c-172">The **Specify Objects** option is selected by default.</span></span>

10. <span data-ttu-id="bb52c-173">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="bb52c-173">Click **OK**.</span></span>

11. <span data-ttu-id="bb52c-174">Fare clic su **Tipi di oggetto**.</span><span class="sxs-lookup"><span data-stu-id="bb52c-174">Click **Object Types**.</span></span>

12. <span data-ttu-id="bb52c-175">Fare clic su **Stored procedure**.</span><span class="sxs-lookup"><span data-stu-id="bb52c-175">Click **Stored Procedures.**</span></span>

13. <span data-ttu-id="bb52c-176">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="bb52c-176">Click **OK**.</span></span>

14. <span data-ttu-id="bb52c-177">Fare clic su **Sfoglia**.</span><span class="sxs-lookup"><span data-stu-id="bb52c-177">Click **Browse**.</span></span>

15. <span data-ttu-id="bb52c-178">Scorrere l'elenco degli elementi e selezionare gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="bb52c-178">Scroll down the list of items and select the following:</span></span>

    1.  <span data-ttu-id="bb52c-179">sp_add_category</span><span class="sxs-lookup"><span data-stu-id="bb52c-179">sp_add_category</span></span>

    2.  <span data-ttu-id="bb52c-180">sp_add_job</span><span class="sxs-lookup"><span data-stu-id="bb52c-180">sp_add_job</span></span>

    3.  <span data-ttu-id="bb52c-181">sp_add_jobschedule</span><span class="sxs-lookup"><span data-stu-id="bb52c-181">sp_add_jobschedule</span></span>

    4.  <span data-ttu-id="bb52c-182">sp_add_jobserver</span><span class="sxs-lookup"><span data-stu-id="bb52c-182">sp_add_jobserver</span></span>

    5.  <span data-ttu-id="bb52c-183">sp_add_jobstep</span><span class="sxs-lookup"><span data-stu-id="bb52c-183">sp_add_jobstep</span></span>

    6.  <span data-ttu-id="bb52c-184">sp_delete_job</span><span class="sxs-lookup"><span data-stu-id="bb52c-184">sp_delete_job</span></span>

    7.  <span data-ttu-id="bb52c-185">sp_help_category</span><span class="sxs-lookup"><span data-stu-id="bb52c-185">sp_help_category</span></span>

    8.  <span data-ttu-id="bb52c-186">sp_help_job</span><span class="sxs-lookup"><span data-stu-id="bb52c-186">sp_help_job</span></span>

    9. <span data-ttu-id="bb52c-187">sp_help_jobschedule</span><span class="sxs-lookup"><span data-stu-id="bb52c-187">sp_help_jobschedule</span></span>

    10. <span data-ttu-id="bb52c-188">sp_verify_job_identifiers</span><span class="sxs-lookup"><span data-stu-id="bb52c-188">sp_verify_job_identifiers</span></span>

16. <span data-ttu-id="bb52c-189">Fare clic su **OK**, quindi fare di nuovo clic su **OK** .</span><span class="sxs-lookup"><span data-stu-id="bb52c-189">Click **OK**, and the click **OK** again.</span></span>

17. <span data-ttu-id="bb52c-190">Selezionare la prima stored procedure, ovvero sp_add_category.</span><span class="sxs-lookup"><span data-stu-id="bb52c-190">Select the first stored procedure: sp_add_category.</span></span>

18. <span data-ttu-id="bb52c-191">Nella colonna **Concedi** della riga **Esegui** selezionare la casella di controllo, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="bb52c-191">In the **Execute** row, in the **Grant** column, click the checkbox, and then click **OK**.</span></span>

19. <span data-ttu-id="bb52c-192">Ripetere il passaggio per ognuna delle stored procedure rimanenti.</span><span class="sxs-lookup"><span data-stu-id="bb52c-192">Repeat for each of the remaining stored procedures.</span></span> <span data-ttu-id="bb52c-193">A RSExecRole devono essere concesse le autorizzazioni di esecuzione per tutte le dieci stored procedure.</span><span class="sxs-lookup"><span data-stu-id="bb52c-193">RSExecRole must be granted Execute permissions for all ten stored procedures.</span></span>

20. <span data-ttu-id="bb52c-194">Nella scheda Entità a sicurezza diretta fare clic nuovamente su **Aggiungi** .</span><span class="sxs-lookup"><span data-stu-id="bb52c-194">On the Securables tab, and click **Add** again.</span></span> <span data-ttu-id="bb52c-195">Verrà visualizzata la finestra di dialogo **Aggiungi oggetti** .</span><span class="sxs-lookup"><span data-stu-id="bb52c-195">The **Add Objects** dialog box appears.</span></span> <span data-ttu-id="bb52c-196">L'opzione **Specifica oggetti** è selezionata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="bb52c-196">The **Specify Objects** option is selected by default.</span></span>

21. <span data-ttu-id="bb52c-197">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="bb52c-197">Click **OK**.</span></span>

22. <span data-ttu-id="bb52c-198">Fare clic su **Tipi di oggetto**.</span><span class="sxs-lookup"><span data-stu-id="bb52c-198">Click **Object Types**.</span></span>

23. <span data-ttu-id="bb52c-199">Fare clic su **Tabelle**.</span><span class="sxs-lookup"><span data-stu-id="bb52c-199">Click **Tables.**</span></span>

24. <span data-ttu-id="bb52c-200">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="bb52c-200">Click **OK**.</span></span>

25. <span data-ttu-id="bb52c-201">Fare clic su **Sfoglia**.</span><span class="sxs-lookup"><span data-stu-id="bb52c-201">Click **Browse**.</span></span>

26. <span data-ttu-id="bb52c-202">Scorrere l'elenco degli elementi e selezionare gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="bb52c-202">Scroll down the list of items and select the following:</span></span>

    1.  <span data-ttu-id="bb52c-203">syscategories</span><span class="sxs-lookup"><span data-stu-id="bb52c-203">syscategories</span></span>

    2.  <span data-ttu-id="bb52c-204">sysjobs</span><span class="sxs-lookup"><span data-stu-id="bb52c-204">sysjobs</span></span>

27. <span data-ttu-id="bb52c-205">Fare clic su **OK**, quindi fare di nuovo clic su **OK** .</span><span class="sxs-lookup"><span data-stu-id="bb52c-205">Click **OK**, and the click **OK** again.</span></span>

28. <span data-ttu-id="bb52c-206">Selezionare la prima tabella, ovvero syscategories.</span><span class="sxs-lookup"><span data-stu-id="bb52c-206">Select the first table: syscategories.</span></span>

29. <span data-ttu-id="bb52c-207">Nella colonna **Concedi** della riga **Seleziona** selezionare la casella di controllo, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="bb52c-207">In the **Select** row, in the **Grant** column, click the checkbox, and then click **OK**.</span></span>

30. <span data-ttu-id="bb52c-208">Ripetere il passaggio per la tabella sysjobs.</span><span class="sxs-lookup"><span data-stu-id="bb52c-208">Repeat for the sysjobs table.</span></span> <span data-ttu-id="bb52c-209">A RSExecRole devono essere concesse le autorizzazioni di selezione per entrambe le tabelle.</span><span class="sxs-lookup"><span data-stu-id="bb52c-209">RSExecRole must be granted Select permissions for both tables.</span></span>

## <a name="move-the-report-server-database"></a><span data-ttu-id="bb52c-210">Spostamento del database del server di report</span><span class="sxs-lookup"><span data-stu-id="bb52c-210">Move the Report Server Database</span></span>
 <span data-ttu-id="bb52c-211">Dopo avere creato i ruoli, è possibile spostare il database del server di report in una nuova istanza di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="bb52c-211">After you create the roles, you can move the report server database to new SQL Server instance.</span></span> <span data-ttu-id="bb52c-212">Per altre informazioni, vedere [Spostamento di database del server di report in un altro computer &#40;modalità nativa SSRS&#41;](../report-server/moving-the-report-server-databases-to-another-computer-ssrs-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="bb52c-212">For more information, see [Moving the Report Server Databases to Another Computer &#40;SSRS Native Mode&#41;](../report-server/moving-the-report-server-databases-to-another-computer-ssrs-native-mode.md).</span></span>

 <span data-ttu-id="bb52c-213">L'aggiornamento del [!INCLUDE[ssDE](../../../includes/ssde-md.md)] a [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)]può essere eseguito prima o dopo lo spostamento del database.</span><span class="sxs-lookup"><span data-stu-id="bb52c-213">If you are upgrading the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] to [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], you can upgrade it before or after moving the database.</span></span>

 <span data-ttu-id="bb52c-214">Il database del server di report verrà aggiornato automaticamente a [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] quando il server di report si connette al database stesso.</span><span class="sxs-lookup"><span data-stu-id="bb52c-214">The report server database will be upgraded to the [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] automatically when the report server connects to it.</span></span> <span data-ttu-id="bb52c-215">Non sono necessari passaggi specifici per aggiornare il database.</span><span class="sxs-lookup"><span data-stu-id="bb52c-215">There are no specific steps required for upgrading the database.</span></span>

## <a name="restore-encryption-keys-and-verify-your-work"></a><span data-ttu-id="bb52c-216">Ripristino delle chiavi di crittografia e verifica del lavoro</span><span class="sxs-lookup"><span data-stu-id="bb52c-216">Restore Encryption Keys and Verify Your Work</span></span>
 <span data-ttu-id="bb52c-217">Se i database del server di report sono stati collegati, è possibile completare i passaggi seguenti per verificare il lavoro.</span><span class="sxs-lookup"><span data-stu-id="bb52c-217">If you have attached the report server databases, you should now be able to complete the following steps to verify your work.</span></span>

#### <a name="to-verify-report-server-operability-after-a-database-move"></a><span data-ttu-id="bb52c-218">Per verificare il funzionamento del server di report dopo uno spostamento del database</span><span class="sxs-lookup"><span data-stu-id="bb52c-218">To verify report server operability after a database move</span></span>

1.  <span data-ttu-id="bb52c-219">Avviare lo strumento di configurazione di Reporting Services e connettersi al server di report.</span><span class="sxs-lookup"><span data-stu-id="bb52c-219">Start the Reporting Services Configuration tool and connect to the report server.</span></span>

2.  <span data-ttu-id="bb52c-220">Fare clic su **Database**.</span><span class="sxs-lookup"><span data-stu-id="bb52c-220">Click **Database**.</span></span>

3.  <span data-ttu-id="bb52c-221">Fare clic su **Cambia database**.</span><span class="sxs-lookup"><span data-stu-id="bb52c-221">Click **Change Database**.</span></span>

4.  <span data-ttu-id="bb52c-222">Fare clic su **Scegli un database del server di report esistente**.</span><span class="sxs-lookup"><span data-stu-id="bb52c-222">Click **Choose an existing report server database**.</span></span>

5.  <span data-ttu-id="bb52c-223">Immettere il nome del server del Motore di database.</span><span class="sxs-lookup"><span data-stu-id="bb52c-223">Enter the server name of the Database Engine.</span></span> <span data-ttu-id="bb52c-224">Se i database del server di report sono stati collegati a un'istanza denominata, è necessario digitare il nome dell'istanza nel formato seguente: \<servername> \\<NomeIstanza \> .</span><span class="sxs-lookup"><span data-stu-id="bb52c-224">If you attached the report server databases to a named instance, you must type the instance name in this format: \<servername>\\<instancename\>.</span></span>

6.  <span data-ttu-id="bb52c-225">Fare clic su **Test connessione**.</span><span class="sxs-lookup"><span data-stu-id="bb52c-225">Click **Test Connection**.</span></span>

7.  <span data-ttu-id="bb52c-226">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="bb52c-226">Click **Next**.</span></span>

8.  <span data-ttu-id="bb52c-227">In Database selezionare il database del server di report.</span><span class="sxs-lookup"><span data-stu-id="bb52c-227">On the Database, select the report server database.</span></span>

9. <span data-ttu-id="bb52c-228">Fare clic su **Avanti** e completare la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="bb52c-228">Click **Next** and complete the wizard.</span></span>

10. <span data-ttu-id="bb52c-229">Fare clic su **Chiavi di crittografia**.</span><span class="sxs-lookup"><span data-stu-id="bb52c-229">Click **Encryption Keys**.</span></span>

11. <span data-ttu-id="bb52c-230">Fare clic su **Ripristina**.</span><span class="sxs-lookup"><span data-stu-id="bb52c-230">Click **Restore**.</span></span>

12. <span data-ttu-id="bb52c-231">Selezionare il file con nome sicuro (con estensione snk) in cui è presente la copia di backup della chiave simmetrica utilizzata per decrittografare le credenziali e le informazioni di connessione archiviate nel database del server di report.</span><span class="sxs-lookup"><span data-stu-id="bb52c-231">Select the strong file (.snk) that has the backup copy of the symmetric key used to decrypt stored credentials and connection information in the report server database.</span></span>

13. <span data-ttu-id="bb52c-232">Immettere la password, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="bb52c-232">Enter the password and click **OK**.</span></span>

14. <span data-ttu-id="bb52c-233">Fare clic su **URL Gestione report**.</span><span class="sxs-lookup"><span data-stu-id="bb52c-233">Click **Report Manager URL**.</span></span>

15. <span data-ttu-id="bb52c-234">Fare clic sul collegamento per aprire Gestione report.</span><span class="sxs-lookup"><span data-stu-id="bb52c-234">Click the link to open Report Manager.</span></span> <span data-ttu-id="bb52c-235">Gli elementi del server di report dovrebbero essere visualizzati dal database del server di report.</span><span class="sxs-lookup"><span data-stu-id="bb52c-235">You should see the report server items from the report server database.</span></span>

## <a name="see-also"></a><span data-ttu-id="bb52c-236">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bb52c-236">See Also</span></span>
 <span data-ttu-id="bb52c-237">[Trasferimento dei database del server di report in un altro Computer &#40;modalità nativa SSRS&#41;](../report-server/moving-the-report-server-databases-to-another-computer-ssrs-native-mode.md) [Reporting Services Configuration Manager &#40;modalità nativa&#41;](../../sql-server/install/reporting-services-configuration-manager-native-mode.md) [creare un database del server di report in modalità nativa &#40;SSRS](../install-windows/ssrs-report-server-create-a-native-mode-report-server-database.md) Configuration Manager&#41;[backup e ripristino delle chiavi di crittografia Reporting Services](../install-windows/ssrs-encryption-keys-back-up-and-restore-encryption-keys.md)</span><span class="sxs-lookup"><span data-stu-id="bb52c-237">[Moving the Report Server Databases to Another Computer &#40;SSRS Native Mode&#41;](../report-server/moving-the-report-server-databases-to-another-computer-ssrs-native-mode.md) [Reporting Services Configuration Manager &#40;Native Mode&#41;](../../sql-server/install/reporting-services-configuration-manager-native-mode.md) [Create a Native Mode Report Server Database  &#40;SSRS Configuration Manager&#41;](../install-windows/ssrs-report-server-create-a-native-mode-report-server-database.md) [Back Up and Restore Reporting Services Encryption Keys](../install-windows/ssrs-encryption-keys-back-up-and-restore-encryption-keys.md)</span></span>


