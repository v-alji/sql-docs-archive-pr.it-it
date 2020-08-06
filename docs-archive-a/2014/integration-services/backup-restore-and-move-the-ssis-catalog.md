---
title: Backup, ripristino e spostamento del catalogo SSIS | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: bf806aef-8556-48ab-aed5-e95de9a2204e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f9de552ddd54168f516f42d9988302561616fd65
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627367"
---
# <a name="backup-restore-and-move-the-ssis-catalog"></a><span data-ttu-id="5170e-102">Backup, ripristino e spostamento del catalogo SSISDB</span><span class="sxs-lookup"><span data-stu-id="5170e-102">Backup, Restore, and Move the SSIS Catalog</span></span>
  [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] <span data-ttu-id="5170e-103">è incluso il database SSISDB.</span><span class="sxs-lookup"><span data-stu-id="5170e-103">includes the SSISDB database.</span></span> <span data-ttu-id="5170e-104">È possibile eseguire una query sulle viste nel database SSISDB per verificare oggetti, impostazioni e dati operativi archiviati nel catalogo **SSISDB** .</span><span class="sxs-lookup"><span data-stu-id="5170e-104">You query views in the SSISDB database to inspect objects, settings, and operational data that are stored in the **SSISDB** catalog.</span></span> <span data-ttu-id="5170e-105">In questo argomento vengono fornite istruzioni per l'esecuzione del backup e del ripristino del database.</span><span class="sxs-lookup"><span data-stu-id="5170e-105">This topic provides instructions for backing up and restoring the database.</span></span>  
  
 <span data-ttu-id="5170e-106">Nel catalogo **SSISDB** sono archiviati i pacchetti distribuiti nel server [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5170e-106">The **SSISDB** catalog stores the packages that you've deployed to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] server.</span></span> <span data-ttu-id="5170e-107">Per ulteriori informazioni sul catalogo, vedere [Catalogo SSIS](catalog/ssis-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="5170e-107">For more information about the catalog, see [SSIS Catalog](catalog/ssis-catalog.md).</span></span>  
  
##  <a name="to-back-up-the-ssis-database"></a><a name="backup"></a> <span data-ttu-id="5170e-108">Per eseguire il backup del database SSIS</span><span class="sxs-lookup"><span data-stu-id="5170e-108">To Back up the SSIS Database</span></span>  
  
1.  <span data-ttu-id="5170e-109">Aprire [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] e connettersi a un'istanza di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5170e-109">Open [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] and connect to an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
2.  <span data-ttu-id="5170e-110">Eseguire il backup della chiave master per il database SSISDB tramite l'istruzione Transact-SQL BACKUP MASTER KEY.</span><span class="sxs-lookup"><span data-stu-id="5170e-110">Back up the master key for the SSISDB database, by using the BACKUP MASTER KEY Transact-SQL statement.</span></span> <span data-ttu-id="5170e-111">La chiave viene archiviata in un file specificato.</span><span class="sxs-lookup"><span data-stu-id="5170e-111">The key is stored in a file that you specify.</span></span> <span data-ttu-id="5170e-112">Utilizzare una password per crittografare la chiave master nel file.</span><span class="sxs-lookup"><span data-stu-id="5170e-112">Use a password to encrypt the master key in the file.</span></span>  
  
     <span data-ttu-id="5170e-113">Per altre informazioni sull'istruzione, vedere [BACKUP MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-master-key-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="5170e-113">For more information about the statement, see [BACKUP MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-master-key-transact-sql).</span></span>  
  
     <span data-ttu-id="5170e-114">Nell'esempio seguente la chiave master viene esportata nel file `c:\temp directory\RCTestInstKey` .</span><span class="sxs-lookup"><span data-stu-id="5170e-114">In the following example, the master key is exported to the `c:\temp directory\RCTestInstKey` file.</span></span> <span data-ttu-id="5170e-115">Per crittografare la chiave master viene utilizzata la password `LS2Setup!` .</span><span class="sxs-lookup"><span data-stu-id="5170e-115">The `LS2Setup!` password is used to encrypt the master key.</span></span>  
  
    ```  
    backup master key to file = 'c:\temp\RCTestInstKey'  
           encryption by password = 'LS2Setup!'  
  
    ```  
  
3.  <span data-ttu-id="5170e-116">Eseguire il backup del database SSISDB tramite la finestra di dialogo **Backup database** in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5170e-116">Back up the SSISDB database by using the **Backup Database** dialog box in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="5170e-117">Per altre informazioni, vedere [Procedura: Eseguire il backup del database (SQL Server Management Studio)](https://go.microsoft.com/fwlink/?LinkId=231812).</span><span class="sxs-lookup"><span data-stu-id="5170e-117">For more information, see [How to: Back Up a Database (SQL Server Management Studio)](https://go.microsoft.com/fwlink/?LinkId=231812).</span></span>  
  
4.  <span data-ttu-id="5170e-118">Generare lo script CREATE LOGIN per ##MS_SSISServerCleanupJobLogin##, effettuando le operazioni riportate di seguito.</span><span class="sxs-lookup"><span data-stu-id="5170e-118">Generate the CREATE LOGIN script for ##MS_SSISServerCleanupJobLogin##, by doing the following.</span></span> <span data-ttu-id="5170e-119">Per altre informazioni, vedere [CREATE LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-login-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="5170e-119">For more information, see [CREATE LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-login-transact-sql).</span></span>  
  
    1.  <span data-ttu-id="5170e-120">In Esplora oggetti in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]espandere il nodo **Sicurezza** , quindi espandere il nodo **Account di accesso** .</span><span class="sxs-lookup"><span data-stu-id="5170e-120">In Object Explorer in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], expand the **Security** node and then expand the **Logins** node.</span></span>  
  
    2.  <span data-ttu-id="5170e-121">Fare clic con il pulsante destro del mouse su **##MS_SSISServerCleanupJobLogin##** , quindi fare clic su **Crea script per account di accesso** > **Genera codice per istruzione CREATE in** > **Nuova finestra editor di query**.</span><span class="sxs-lookup"><span data-stu-id="5170e-121">Right-click **##MS_SSISServerCleanupJobLogin##**, and then click **Script Login as** > **CREATE To** > **New Query Editor Window**.</span></span>  
  
5.  <span data-ttu-id="5170e-122">Se si ripristina il database SSISDB a un'istanza di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] in cui il catalogo SSISDB non è mai stato creato, generare lo script CREATE PROCEDURE per sp_ssis_startup, effettuando le operazioni riportate di seguito.</span><span class="sxs-lookup"><span data-stu-id="5170e-122">If you will be restoring the SSISDB database to an [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] instance where the SSISDB catalog was never created, generate the CREATE PROCEDURE script for sp_ssis_startup, by doing the following.</span></span> <span data-ttu-id="5170e-123">Per altre informazioni, vedere [CREATE PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-procedure-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="5170e-123">For more information, see [CREATE PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-procedure-transact-sql).</span></span>  
  
    1.  <span data-ttu-id="5170e-124">In Esplora oggetti espandere il nodo **database** , quindi espandere il **System Databases**  >  **master**  >  **Programmability**  >  nodo**stored procedure** di programmabilità master database di sistema.</span><span class="sxs-lookup"><span data-stu-id="5170e-124">In Object Explorer, expand the **Databases** node and then expand the **System Databases** > **master** > **Programmability** > **Stored Procedures** node.</span></span>  
  
    2.  <span data-ttu-id="5170e-125">Fare clic con il pulsante destro del mouse su **dbo.sp_ssis_startup**, quindi fare clic su **Crea script per stored procedure** > **Genera codice per istruzione CREATE in** > **Nuova finestra editor di query**.</span><span class="sxs-lookup"><span data-stu-id="5170e-125">Right click **dbo.sp_ssis_startup**, and then click **Script Stored Procedure as** > **CREATE To** > **New Query Editor Window**.</span></span>  
  
6.  <span data-ttu-id="5170e-126">Verificare che SQL Server Agent sia stato avviato.</span><span class="sxs-lookup"><span data-stu-id="5170e-126">Confirm that SQL Server Agent has been started</span></span>  
  
7.  <span data-ttu-id="5170e-127">Se si ripristina il database SSISDB a un'istanza di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] in cui il catalogo SSISDB non è mai stato creato, generare uno script per il processo di manutenzione del server SSIS, effettuando le operazioni riportate di seguito.</span><span class="sxs-lookup"><span data-stu-id="5170e-127">If you will be restoring the SSISDB database to an [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] instance where the SSISDB catalog was never created, generate a script for the SSIS Server Maintenance Job by doing the following.</span></span> <span data-ttu-id="5170e-128">Lo script viene creato automaticamente in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent quando viene creato il catalogo SSISDB.</span><span class="sxs-lookup"><span data-stu-id="5170e-128">The script is created in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent automatically when the SSISDB catalog is created.</span></span> <span data-ttu-id="5170e-129">Il processo consente di pulire i log operazioni di pulizia al di fuori del periodo di memorizzazione e di rimuovere le versioni precedenti dei progetti.</span><span class="sxs-lookup"><span data-stu-id="5170e-129">The job helps clean up cleanup operation logs outside the retention window and remove older versions of projects.</span></span>  
  
    1.  <span data-ttu-id="5170e-130">In Esplora oggetti espandere il nodo **SQL Server Agent** , quindi espandere il nodo **Processi** .</span><span class="sxs-lookup"><span data-stu-id="5170e-130">In Object Explorer, expand the **SQL Server Agent** node and then expand the **Jobs** node.</span></span>  
  
    2.  <span data-ttu-id="5170e-131">Fare clic con il pulsante destro del mouse su processo di manutenzione del server SSIS, quindi scegliere Crea **script**  >  **per processo in**  >  **nuova finestra Editor di query**.</span><span class="sxs-lookup"><span data-stu-id="5170e-131">Right click SSIS Server Maintenance Job, and then click **Script Job as** > **CREATE To** > **New Query Editor Window**.</span></span>  
  
### <a name="to-restore-the-ssis-database"></a><span data-ttu-id="5170e-132">Per ripristinare il database SSIS</span><span class="sxs-lookup"><span data-stu-id="5170e-132">To Restore the SSIS Database</span></span>  
  
1.  <span data-ttu-id="5170e-133">Se si ripristina il database SSISDB a un'istanza di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] in cui il catalogo SSISDB non è mai stato creato, abilitare Common Language Runtime (CLR) eseguendo la stored procedure sp_configure.</span><span class="sxs-lookup"><span data-stu-id="5170e-133">If you are restoring the SSISDB database to an [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] instance where the SSISDB catalog was never created, enable common language runtime (clr) by running the sp_configure stored procedure.</span></span> <span data-ttu-id="5170e-134">Per altre informazioni, vedere [sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) e [Opzione clr enabled](https://go.microsoft.com/fwlink/?LinkId=231855).</span><span class="sxs-lookup"><span data-stu-id="5170e-134">For more information, see [sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) and [clr enabled Option](https://go.microsoft.com/fwlink/?LinkId=231855).</span></span>  
  
    ```  
    use master   
           sp_configure 'clr enabled', 1  
           reconfigure  
  
    ```  
  
2.  <span data-ttu-id="5170e-135">Se si ripristina il database SSISDB a un'istanza di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] in cui il catalogo SSISDB non è mai stato creato, creare la chiave asimmetrica e l'accesso da quest'ultima e concedere l'autorizzazione UNSAFE all'account di accesso.</span><span class="sxs-lookup"><span data-stu-id="5170e-135">If you are restoring the SSISDB database to an [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] instance where the SSISDB catalog was never created, create the asymmetric key and the login from the asymmetric key, and grant UNSAFE permission to the login.</span></span>  
  
    ```  
    Create Asymmetric key MS_SQLEnableSystemAssemblyLoadingKey  
           FROM Executable File = 'C:\Program Files\Microsoft SQL Server\110\DTS\Binn\Microsoft.SqlServer.IntegrationServices.Server.dll'  
  
    ```  
  
     [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="5170e-136">Per le stored procedure CLR è necessario concedere le autorizzazioni UNSAFE all'account di accesso, poiché per questo account è richiesto un accesso aggiuntivo alle risorse limitate, ad esempio l'API Microsoft Win32.</span><span class="sxs-lookup"><span data-stu-id="5170e-136">CLR stored procedures require UNSAFE permissions to be granted to the login because the login requires additional access to restricted resources, such as the Microsoft Win32 API.</span></span> <span data-ttu-id="5170e-137">Per altre informazioni sull'autorizzazione codice UNSAFE, vedere [Creazione di un assembly](../relational-databases/clr-integration/assemblies/creating-an-assembly.md).</span><span class="sxs-lookup"><span data-stu-id="5170e-137">For more information about the UNSAFE code permission, see [Creating an Assembly](../relational-databases/clr-integration/assemblies/creating-an-assembly.md).</span></span>  
  
    ```  
    Create Login MS_SQLEnableSystemAssemblyLoadingUser  
           FROM Asymmetric key MS_SQLEnableSystemAssemblyLoadingKey   
  
           Grant unsafe Assembly to MS_SQLEnableSystemAssemblyLoadingUser  
  
    ```  
  
3.  <span data-ttu-id="5170e-138">Ripristinare il database SSISDB dal backup tramite la finestra di dialogo **Ripristina database** in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5170e-138">Restore the SSISDB database from the backup by using the **Restore Database** dialog box in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="5170e-139">Per ulteriori informazioni, vedere gli argomenti seguenti.</span><span class="sxs-lookup"><span data-stu-id="5170e-139">For more information, see the following topics.</span></span>  
  
    -   [<span data-ttu-id="5170e-140">Ripristina database &#40;pagina Generale&#41;</span><span class="sxs-lookup"><span data-stu-id="5170e-140">Restore Database &#40;General Page&#41;</span></span>](general-page-of-integration-services-designers-options.md)  
  
    -   [<span data-ttu-id="5170e-141">Ripristina database &#40;pagina File&#41;</span><span class="sxs-lookup"><span data-stu-id="5170e-141">Restore Database &#40;Files Page&#41;</span></span>](../relational-databases/backup-restore/restore-database-files-page.md)  
  
    -   [<span data-ttu-id="5170e-142">Ripristina database &#40;pagina Opzioni&#41;</span><span class="sxs-lookup"><span data-stu-id="5170e-142">Restore Database &#40;Options Page&#41;</span></span>](../relational-databases/backup-restore/restore-database-options-page.md)  
  
4.  <span data-ttu-id="5170e-143">Eseguire gli script creati nella procedura [Per eseguire il backup del database SSIS](#backup) per ##MS_SSISServerCleanupJobLogin##, sp_ssis_startup e per il processo di manutenzione del server SSIS.</span><span class="sxs-lookup"><span data-stu-id="5170e-143">Execute the scripts that you created in the [To Back up the SSIS Database](#backup) for ##MS_SSISServerCleanupJobLogin##, sp_ssis_startup, and SSIS Server Maintenance Job.</span></span> <span data-ttu-id="5170e-144">Verificare che SQL Server Agent sia stato avviato.</span><span class="sxs-lookup"><span data-stu-id="5170e-144">Confirm that SQL Server Agent has been started.</span></span>  
  
5.  <span data-ttu-id="5170e-145">Eseguire l'istruzione riportata di seguito per impostare l'esecuzione automatica della stored procedure sp_ssis_startup.</span><span class="sxs-lookup"><span data-stu-id="5170e-145">Run the following statement to set the sp_ssis_startup prodecure for autoexecution.</span></span> <span data-ttu-id="5170e-146">Per altre informazioni, vedere [sp_procoption &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-procoption-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="5170e-146">For more information, see [sp_procoption &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-procoption-transact-sql).</span></span>  
  
    ```  
    EXEC sp_procoption N'sp_ssis_startup','startup','on'  
    ```  
  
6.  <span data-ttu-id="5170e-147">Eseguire il mapping dell'utente di SSISDB ##MS_SSISServerCleanupJobUser## (database SSISDB) a ##MS_SSISServerCleanupJobLogin## tramite la finestra di dialogo **Proprietà account di accesso** in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5170e-147">Map the SSISDB user ##MS_SSISServerCleanupJobUser## (SSISDB database) to ##MS_SSISServerCleanupJobLogin##, by using the **Login Properties** dialog box in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
7.  <span data-ttu-id="5170e-148">Ripristinare la chiave master utilizzando uno dei metodi riportati di seguito.</span><span class="sxs-lookup"><span data-stu-id="5170e-148">Restore the master key by using one of the following methods.</span></span> <span data-ttu-id="5170e-149">Per ulteriori informazioni sulla crittografia e sulle chiavi master, vedere [Gerarchia di crittografia](../relational-databases/security/encryption/encryption-hierarchy.md).</span><span class="sxs-lookup"><span data-stu-id="5170e-149">For more information about encryption, see [Encryption Hierarchy](../relational-databases/security/encryption/encryption-hierarchy.md).</span></span>  
  
    -   <span data-ttu-id="5170e-150">**Metodo 1**</span><span class="sxs-lookup"><span data-stu-id="5170e-150">**Method 1**</span></span>  
  
         <span data-ttu-id="5170e-151">Usare questo metodo se si è già eseguito un backup della chiave master del database e si dispone della password usata per crittografare la chiave master.</span><span class="sxs-lookup"><span data-stu-id="5170e-151">Use this method if you've already performed a backup of the database master key, and you have the password used to encrypt the master key.</span></span>  
  
        ```  
               Restore master key from file = 'c:\temp\RCTestInstKey'  
               Decryption by password = 'LS2Setup!' -- 'Password used to encrypt the master key during SSISDB backup'  
               Encryption by password = 'LS3Setup!' -- 'New Password'  
               Force  
  
        ```  
  
        > [!NOTE]  
        >  <span data-ttu-id="5170e-152">Verificare che l'account del servizio [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] disponga delle autorizzazioni per leggere il file della chiave di backup.</span><span class="sxs-lookup"><span data-stu-id="5170e-152">Confirm that the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] service account has permissions to read the backup key file.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="5170e-153">Se la chiave master del database non è stata ancora crittografata dalla chiave master del servizio, si riceverà il messaggio di avviso seguente visualizzato in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5170e-153">You will see the following warning message displayed in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] if the database master key has not yet been encrypted by the service master key.</span></span> <span data-ttu-id="5170e-154">Ignorare il messaggio.</span><span class="sxs-lookup"><span data-stu-id="5170e-154">Ignore the warning message.</span></span>  
        >   
        >  <span data-ttu-id="5170e-155">**Impossibile decrittografare la chiave master corrente. L'errore è stato ignorato perché è stata specificata l'opzione FORCE.**</span><span class="sxs-lookup"><span data-stu-id="5170e-155">**The current master key cannot be decrypted. The error was ignored because the FORCE option was specified.**</span></span>  
        >   
        >  <span data-ttu-id="5170e-156">L'argomento FORCE consente di specificare che è consigliabile che il processo di ripristino continui anche se la chiave master del database corrente non è aperta.</span><span class="sxs-lookup"><span data-stu-id="5170e-156">The FORCE argument specifies that the restore process should continue even if the current database master key is not open.</span></span> <span data-ttu-id="5170e-157">Per il catalogo SSISDB, dal momento che la chiave master del database non è stata aperta nell'istanza in cui si esegue il ripristino del database, si visualizzerà questo messaggio.</span><span class="sxs-lookup"><span data-stu-id="5170e-157">For the SSISDB catalog, because the database master key has not been opened on the instance where you are restoring the database, you will see this message.</span></span>  
  
    -   <span data-ttu-id="5170e-158">**Metodo 2**</span><span class="sxs-lookup"><span data-stu-id="5170e-158">**Method 2**</span></span>  
  
         <span data-ttu-id="5170e-159">Utilizzare questo metodo se si dispone della password originale utilizzata per creare SSISDB.</span><span class="sxs-lookup"><span data-stu-id="5170e-159">Use this method if you have the original password that was used to create SSISDB.</span></span>  
  
        ```  
        open master key decryption by password = 'LS1Setup!' --'Password used when creating SSISDB'  
               Alter Master Key Add encryption by Service Master Key  
        ```  
  
8.  <span data-ttu-id="5170e-160">Determinare se lo schema del catalogo SSISDB e i file binari di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] (assembly ISServerExec e SQLCLR) sono compatibili eseguendo [catalog.check_schema_version](/sql/integration-services/system-stored-procedures/catalog-check-schema-version).</span><span class="sxs-lookup"><span data-stu-id="5170e-160">Determine whether the SSISDB catalog schema and the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] binaries (ISServerExec and SQLCLR assembly) are compatible, by running [catalog.check_schema_version](/sql/integration-services/system-stored-procedures/catalog-check-schema-version).</span></span>  
  
9. <span data-ttu-id="5170e-161">Per verificare il corretto ripristino del database SSISDB, effettuare delle operazioni nel catalogo SSISDB, ad esempio l'esecuzione dei pacchetti distribuiti nel server [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5170e-161">To confirm that the SSISDB database has been restored successfully, perform operations against the SSISDB catalog such as running packages that have been deployed to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] server.</span></span> <span data-ttu-id="5170e-162">Per altre informazioni, vedere [Eseguire un pacchetto sul server SSIS mediante SQL Server Management Studio](run-a-package-on-the-ssis-server-using-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="5170e-162">For more information, see [Run a Package on the SSIS Server Using SQL Server Management Studio](run-a-package-on-the-ssis-server-using-sql-server-management-studio.md).</span></span>  
  
### <a name="to-move-the-ssis-database"></a><span data-ttu-id="5170e-163">Per spostare il database SSIS</span><span class="sxs-lookup"><span data-stu-id="5170e-163">To Move the SSIS Database</span></span>  
  
-   <span data-ttu-id="5170e-164">Seguire le istruzioni per lo spostamento di database utente.</span><span class="sxs-lookup"><span data-stu-id="5170e-164">Follow the instructions for moving user databases.</span></span> <span data-ttu-id="5170e-165">Per altre informazioni, vedere [Spostare database utente](../relational-databases/databases/move-user-databases.md).</span><span class="sxs-lookup"><span data-stu-id="5170e-165">For more information, see [Move User Databases](../relational-databases/databases/move-user-databases.md).</span></span>  
  
     <span data-ttu-id="5170e-166">Assicurarsi che venga eseguito il backup della chiave master per il database SSISDB e proteggere il file di backup.</span><span class="sxs-lookup"><span data-stu-id="5170e-166">Ensure that you back up the master key for the SSISDB database and protect the backup file.</span></span> <span data-ttu-id="5170e-167">Per altre informazioni, vedere [Per eseguire il backup del database SSIS](#backup).</span><span class="sxs-lookup"><span data-stu-id="5170e-167">For more information, see [To Back up the SSIS Database](#backup).</span></span>  
  
     <span data-ttu-id="5170e-168">Assicurarsi che gli oggetti pertinenti a Integration Services (SSIS) vengano creati nella nuova istanza di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] in cui non è ancora stato creato il catalogo SSISDB.</span><span class="sxs-lookup"><span data-stu-id="5170e-168">Ensure that the Integration Services (SSIS) relevant objects are created in the new [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] instance where the SSISDB catalog has not yet been created.</span></span>  
  
  
