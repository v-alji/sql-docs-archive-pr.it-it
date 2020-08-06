---
title: Spostare un database protetto da TDE in un'altra istanza di SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Transparent Data Encryption, moving
- TDE, moving a database
ms.assetid: fb420903-df54-4016-bab6-49e6dfbdedc7
author: jaszymas
ms.author: jaszymas
ms.openlocfilehash: 3b03b4d9ecf31e9953fd3e22cec5c51bbacc0c25
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726848"
---
# <a name="move-a-tde-protected-database-to-another-sql-server"></a><span data-ttu-id="bfb1e-102">Spostare un database protetto da TDE in un'altra istanza di SQL Server</span><span class="sxs-lookup"><span data-stu-id="bfb1e-102">Move a TDE Protected Database to Another SQL Server</span></span>
  <span data-ttu-id="bfb1e-103">Questo argomento illustra come proteggere un database tramite TDE (Transparent Data Encryption) e spostare il database in un'altra istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] usando [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bfb1e-103">This topic describes how to protect a database by using transparent data encryption (TDE), and then move the database to another instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="bfb1e-104">TDE esegue la crittografia e la decrittografia delle operazioni di I/O di file di dati e log in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="bfb1e-104">TDE performs real-time I/O encryption and decryption of the data and log files.</span></span> <span data-ttu-id="bfb1e-105">La crittografia usa una chiave di crittografia del database (DEK) che viene archiviata nel record di avvio del database per la disponibilità durante il ripristino.</span><span class="sxs-lookup"><span data-stu-id="bfb1e-105">The encryption uses a database encryption key (DEK), which is stored in the database boot record for availability during recovery.</span></span> <span data-ttu-id="bfb1e-106">La chiave di decrittografia è una chiave simmetrica protetta tramite un certificato archiviato nel database `master` del server o una chiave asimmetrica protetta da un modulo EKM.</span><span class="sxs-lookup"><span data-stu-id="bfb1e-106">The DEK is a symmetric key secured by using a certificate stored in the `master` database of the server or an asymmetric key protected by an EKM module.</span></span>  
  
 <span data-ttu-id="bfb1e-107">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="bfb1e-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="bfb1e-108">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="bfb1e-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="bfb1e-109">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="bfb1e-109">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="bfb1e-110">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="bfb1e-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="bfb1e-111">**Per creare un database protetto con TDE usando:**</span><span class="sxs-lookup"><span data-stu-id="bfb1e-111">**To create a database protected by transparent data encryption, using:**</span></span>  
  
     [<span data-ttu-id="bfb1e-112">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="bfb1e-112">SQL Server Management Studio</span></span>](#SSMSCreate)  
  
     [<span data-ttu-id="bfb1e-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="bfb1e-113">Transact-SQL</span></span>](#TsqlCreate)  
  
-   <span data-ttu-id="bfb1e-114">**Per spostare un database usando:**</span><span class="sxs-lookup"><span data-stu-id="bfb1e-114">**To move a database, using:**</span></span>  
  
     [<span data-ttu-id="bfb1e-115">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="bfb1e-115">SQL Server Management Studio</span></span>](#SSMSMove)  
  
     [<span data-ttu-id="bfb1e-116">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="bfb1e-116">Transact-SQL</span></span>](#TsqlMove)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="bfb1e-117">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="bfb1e-117">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="bfb1e-118">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="bfb1e-118">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="bfb1e-119">Quando si sposta il database protetto con TDE, è necessario spostare anche la chiave asimmetrica o il certificato usato per aprire la chiave di decrittografia.</span><span class="sxs-lookup"><span data-stu-id="bfb1e-119">When moving a TDE protected database, you must also move the certificate or asymmetric key that is used to open the DEK.</span></span> <span data-ttu-id="bfb1e-120">Il certificato o la chiave asimmetrica deve essere installato nel `master` database del server di destinazione, in modo che [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] possa accedere ai file del database.</span><span class="sxs-lookup"><span data-stu-id="bfb1e-120">The certificate or asymmetric key must be installed in the `master` database of the destination server, so that [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] can access the database files.</span></span> <span data-ttu-id="bfb1e-121">Per altre informazioni sulla crittografia trasparente del database, vedere [Transparent Data Encryption &#40;TDE&#41;](transparent-data-encryption.md).</span><span class="sxs-lookup"><span data-stu-id="bfb1e-121">For more information, see [Transparent Data Encryption &#40;TDE&#41;](transparent-data-encryption.md).</span></span>  
  
-   <span data-ttu-id="bfb1e-122">Ai fini del recupero del certificato, è necessario mantenere copie sia del file del certificato sia del file della chiave privata.</span><span class="sxs-lookup"><span data-stu-id="bfb1e-122">You must retain copies of both the certificate file and the private key file in order to recover the certificate.</span></span> <span data-ttu-id="bfb1e-123">La password per la chiave primaria non deve essere uguale a quella della chiave master del database.</span><span class="sxs-lookup"><span data-stu-id="bfb1e-123">The password for the private key does not have to be the same as the database master key password.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]<span data-ttu-id="bfb1e-124">Archivia i file creati qui in **C:\Programmi\Microsoft SQL Server\MSSQL12. MSSQLSERVER\MSSQL\DATA** per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="bfb1e-124">stores the files created here in **C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\DATA** by default.</span></span> <span data-ttu-id="bfb1e-125">I nomi e i percorsi dei file possono essere diversi.</span><span class="sxs-lookup"><span data-stu-id="bfb1e-125">Your file names and locations might be different.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="bfb1e-126">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="bfb1e-126">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="bfb1e-127">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="bfb1e-127">Permissions</span></span>  
  
-   <span data-ttu-id="bfb1e-128">È richiesta l' `CONTROL DATABASE` autorizzazione `master` per il database per creare la chiave master del database.</span><span class="sxs-lookup"><span data-stu-id="bfb1e-128">Requires `CONTROL DATABASE` permission on the `master` database to create the database master key.</span></span>  
  
-   <span data-ttu-id="bfb1e-129">È richiesta l' `CREATE CERTIFICATE` autorizzazione `master` per il database per creare il certificato che protegge la chiave di crittografia.</span><span class="sxs-lookup"><span data-stu-id="bfb1e-129">Requires `CREATE CERTIFICATE` permission on the `master` database to create the certificate that protects the DEK.</span></span>  
  
-   <span data-ttu-id="bfb1e-130">Sono richieste l'autorizzazione `CONTROL DATABASE` per il database crittografato e l'autorizzazione `VIEW DEFINITION` per la chiave asimmetrica o il certificato usato per crittografare la chiave di crittografia del database.</span><span class="sxs-lookup"><span data-stu-id="bfb1e-130">Requires `CONTROL DATABASE` permission on the encrypted database and `VIEW DEFINITION` permission on the certificate or asymmetric key that is used to encrypt the database encryption key.</span></span>  
  
##  <a name="to-create-a-database-protected-by-transparent-data-encryption"></a><a name="SSMSProcedure"></a> <span data-ttu-id="bfb1e-131">Per creare un database protetto con TDE</span><span class="sxs-lookup"><span data-stu-id="bfb1e-131">To create a database protected by transparent data encryption</span></span>  
  
###  <a name="using-sql-server-management-studio"></a><a name="SSMSCreate"></a> <span data-ttu-id="bfb1e-132">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="bfb1e-132">Using SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="bfb1e-133">Creare una chiave master e un certificato del database nel `master` database.</span><span class="sxs-lookup"><span data-stu-id="bfb1e-133">Create a database master key and certificate in the `master` database.</span></span> <span data-ttu-id="bfb1e-134">Per altre informazioni, vedere **Uso di Transact-SQL** di seguito.</span><span class="sxs-lookup"><span data-stu-id="bfb1e-134">For more information, see **Using Transact-SQL** below.</span></span>  
  
2.  <span data-ttu-id="bfb1e-135">Creare un backup del certificato del server nel `master` database.</span><span class="sxs-lookup"><span data-stu-id="bfb1e-135">Create a backup of the server certificate in the `master` database.</span></span> <span data-ttu-id="bfb1e-136">Per altre informazioni, vedere **Uso di Transact-SQL** di seguito.</span><span class="sxs-lookup"><span data-stu-id="bfb1e-136">For more information, see **Using Transact-SQL** below.</span></span>  
  
3.  <span data-ttu-id="bfb1e-137">In Esplora oggetti fare clic con il pulsante destro del mouse sulla cartella **Database** e selezionare **Nuovo database**.</span><span class="sxs-lookup"><span data-stu-id="bfb1e-137">In Object Explorer, right-click the **Databases** folder and select **New Database**.</span></span>  
  
4.  <span data-ttu-id="bfb1e-138">Nella finestra di dialogo **Nuovo database** digitare il nome del nuovo database nella casella **Nome database** .</span><span class="sxs-lookup"><span data-stu-id="bfb1e-138">In the **New Database** dialog box, in the **Database name** box, enter the name of the new database.</span></span>  
  
5.  <span data-ttu-id="bfb1e-139">Nella casella **Proprietario** digitare il nome del proprietario del nuovo database.</span><span class="sxs-lookup"><span data-stu-id="bfb1e-139">In the **Owner** box, enter the name of the new database's owner.</span></span> <span data-ttu-id="bfb1e-140">In alternativa, fare clic sui puntini di sospensione **(...)** per aprire la finestra di dialogo **Seleziona proprietario database**.</span><span class="sxs-lookup"><span data-stu-id="bfb1e-140">Alternately, click the ellipsis **(...)** to open the **Select Database Owner** dialog box.</span></span> <span data-ttu-id="bfb1e-141">Per altre informazioni sulla creazione di un nuovo database, vedere [Create a Database](../../databases/create-a-database.md).</span><span class="sxs-lookup"><span data-stu-id="bfb1e-141">For more information on creating a new database, see [Create a Database](../../databases/create-a-database.md).</span></span>  
  
6.  <span data-ttu-id="bfb1e-142">In Esplora oggetti fare clic sul segno più per espandere la cartella **Database** .</span><span class="sxs-lookup"><span data-stu-id="bfb1e-142">In Object Explorer, click the plus sign to expand the **Databases** folder.</span></span>  
  
7.  <span data-ttu-id="bfb1e-143">Fare clic con il pulsante destro del mouse sul database creato, scegliere **Attività**e quindi fare clic su **Gestione crittografia del database**.</span><span class="sxs-lookup"><span data-stu-id="bfb1e-143">Right-click the database you created, point to **Tasks**, and select **Manage Database Encryption**.</span></span>  
  
     <span data-ttu-id="bfb1e-144">Nella finestra di dialogo **Gestione crittografia del database** sono disponibili le opzioni indicate di seguito.</span><span class="sxs-lookup"><span data-stu-id="bfb1e-144">The following options are available on the **Manage Database Encryption** dialog box.</span></span>  
  
     <span data-ttu-id="bfb1e-145">**Algoritmo di crittografia**</span><span class="sxs-lookup"><span data-stu-id="bfb1e-145">**Encryption Algorithm**</span></span>  
     <span data-ttu-id="bfb1e-146">Visualizza o imposta l'algoritmo da usare per la crittografia del database.</span><span class="sxs-lookup"><span data-stu-id="bfb1e-146">Displays or sets the algorithm to use for database encryption.</span></span> <span data-ttu-id="bfb1e-147">L'algoritmo predefinito è `AES128`.</span><span class="sxs-lookup"><span data-stu-id="bfb1e-147">`AES128` is the default algorithm.</span></span> <span data-ttu-id="bfb1e-148">Il campo non può essere vuoto.</span><span class="sxs-lookup"><span data-stu-id="bfb1e-148">This field cannot be blank.</span></span> <span data-ttu-id="bfb1e-149">Per altre informazioni sugli algoritmi di crittografia, vedere [Choose an Encryption Algorithm](choose-an-encryption-algorithm.md).</span><span class="sxs-lookup"><span data-stu-id="bfb1e-149">For more information on encryption algorithms, see [Choose an Encryption Algorithm](choose-an-encryption-algorithm.md).</span></span>  
  
     <span data-ttu-id="bfb1e-150">**Usa certificato server**</span><span class="sxs-lookup"><span data-stu-id="bfb1e-150">**Use server certificate**</span></span>  
     <span data-ttu-id="bfb1e-151">Imposta la sicurezza della crittografia mediante un certificato.</span><span class="sxs-lookup"><span data-stu-id="bfb1e-151">Sets the encryption to be secured by a certificate.</span></span> <span data-ttu-id="bfb1e-152">Selezionarne uno dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="bfb1e-152">Select one from the list.</span></span> <span data-ttu-id="bfb1e-153">Se non si dispone dell'autorizzazione `VIEW DEFINITION` per i certificati del server, l'elenco sarà vuoto.</span><span class="sxs-lookup"><span data-stu-id="bfb1e-153">If you do not have the `VIEW DEFINITION` permission on server certificates, this list will be empty.</span></span> <span data-ttu-id="bfb1e-154">Se viene selezionato un metodo certificato di crittografia, il valore non può essere vuoto.</span><span class="sxs-lookup"><span data-stu-id="bfb1e-154">If a certificate method of encryption is selected, this value cannot be empty.</span></span> <span data-ttu-id="bfb1e-155">Per altre informazioni sui certificati, vedere [SQL Server Certificates and Asymmetric Keys](../sql-server-certificates-and-asymmetric-keys.md).</span><span class="sxs-lookup"><span data-stu-id="bfb1e-155">For more information about certificates, see [SQL Server Certificates and Asymmetric Keys](../sql-server-certificates-and-asymmetric-keys.md).</span></span>  
  
     <span data-ttu-id="bfb1e-156">**Usa chiave asimmetrica server**</span><span class="sxs-lookup"><span data-stu-id="bfb1e-156">**Use server asymmetric key**</span></span>  
     <span data-ttu-id="bfb1e-157">Imposta la sicurezza della crittografia mediante una chiave asimmetrica.</span><span class="sxs-lookup"><span data-stu-id="bfb1e-157">Sets the encryption to be secured by an asymmetric key.</span></span> <span data-ttu-id="bfb1e-158">Vengono visualizzate solo le chiavi asimmetriche disponibili.</span><span class="sxs-lookup"><span data-stu-id="bfb1e-158">Only available asymmetric keys are displayed.</span></span> <span data-ttu-id="bfb1e-159">Solo una chiave asimmetrica protetta da un modulo EKM può crittografare un database tramite Transparent Data Encryption.</span><span class="sxs-lookup"><span data-stu-id="bfb1e-159">Only an asymmetric key protected by an EKM module can encrypt a database using TDE.</span></span>  
  
     <span data-ttu-id="bfb1e-160">**Attiva crittografia del database**</span><span class="sxs-lookup"><span data-stu-id="bfb1e-160">**Set Database Encryption On**</span></span>  
     <span data-ttu-id="bfb1e-161">Modifica il database per abilitare (se selezionata) o disabilitare la funzionalità TDE (se deselezionata).</span><span class="sxs-lookup"><span data-stu-id="bfb1e-161">Alters the database to turn on (checked) or turn off (unchecked) TDE.</span></span>  
  
8.  <span data-ttu-id="bfb1e-162">Al termine, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="bfb1e-162">When finished, click **OK**.</span></span>  
  
###  <a name="using-transact-sql"></a><a name="TsqlCreate"></a> <span data-ttu-id="bfb1e-163">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="bfb1e-163">Using Transact-SQL</span></span>  
  
1.  <span data-ttu-id="bfb1e-164">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bfb1e-164">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="bfb1e-165">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="bfb1e-165">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="bfb1e-166">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="bfb1e-166">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Create a database master key and a certificate in the master database.  
    USE master ;  
    GO  
    CREATE MASTER KEY ENCRYPTION BY PASSWORD = '*rt@40(FL&dasl1';  
    GO  
    CREATE CERTIFICATE TestSQLServerCert   
    WITH SUBJECT = 'Certificate to protect TDE key'  
    GO  
    -- Create a backup of the server certificate in the master database.  
    -- The following code stores the backup of the certificate and the private key file in the default data location for this instance of SQL Server   
    -- (C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\DATA).  
  
    BACKUP CERTIFICATE TestSQLServerCert   
    TO FILE = 'TestSQLServerCert'  
    WITH PRIVATE KEY   
    (  
        FILE = 'SQLPrivateKeyFile',  
        ENCRYPTION BY PASSWORD = '*rt@40(FL&dasl1'  
    );  
    GO  
    -- Create a database to be protected by TDE.  
    CREATE DATABASE CustRecords ;  
    GO  
    -- Switch to the new database.  
    -- Create a database encryption key, that is protected by the server certificate in the master database.   
    -- Alter the new database to encrypt the database using TDE.  
    USE CustRecords;  
    GO  
    CREATE DATABASE ENCRYPTION KEY  
    WITH ALGORITHM = AES_128  
    ENCRYPTION BY SERVER CERTIFICATE TestSQLServerCert;  
    GO  
    ALTER DATABASE CustRecords  
    SET ENCRYPTION ON;  
    GO  
    ```  
  
 <span data-ttu-id="bfb1e-167">Per altre informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="bfb1e-167">For more information, see:</span></span>  
  
-   [<span data-ttu-id="bfb1e-168">CREATE MASTER KEY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="bfb1e-168">CREATE MASTER KEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-master-key-transact-sql)  
  
-   [<span data-ttu-id="bfb1e-169">CREATE CERTIFICATE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="bfb1e-169">CREATE CERTIFICATE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-certificate-transact-sql)  
  
-   [<span data-ttu-id="bfb1e-170">BACKUP CERTIFICATE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="bfb1e-170">BACKUP CERTIFICATE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/backup-certificate-transact-sql)  
  
-   [<span data-ttu-id="bfb1e-171">CREATE DATABASE &#40;SQL Server Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="bfb1e-171">CREATE DATABASE &#40;SQL Server Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-database-sql-server-transact-sql)  
  
-   [<span data-ttu-id="bfb1e-172">CREATE DATABASE ENCRYPTION KEY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="bfb1e-172">CREATE DATABASE ENCRYPTION KEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-database-encryption-key-transact-sql)  
  
-   [<span data-ttu-id="bfb1e-173">ALTER DATABASE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="bfb1e-173">ALTER DATABASE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql)  
  
##  <a name="to-move-a-database"></a><a name="TsqlProcedure"></a><span data-ttu-id="bfb1e-174">Per spostare un database</span><span class="sxs-lookup"><span data-stu-id="bfb1e-174">To move a database</span></span>  
  
###  <a name="using-sql-server-management-studio"></a><a name="SSMSMove"></a> <span data-ttu-id="bfb1e-175">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="bfb1e-175">Using SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="bfb1e-176">In Esplora oggetti fare clic con il pulsante destro del mouse sul database crittografato in precedenza, scegliere **Attività** e fare clic su **Scollega...** .</span><span class="sxs-lookup"><span data-stu-id="bfb1e-176">In Object Explorer, right-click the database you encrypted above, point to **Tasks** and select **Detach...**.</span></span>  
  
     <span data-ttu-id="bfb1e-177">Nella finestra di dialogo **Scollega database** sono disponibili le opzioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="bfb1e-177">The following options are available in the **Detach Database** dialog box.</span></span>  
  
     <span data-ttu-id="bfb1e-178">**Database da scollegare**</span><span class="sxs-lookup"><span data-stu-id="bfb1e-178">**Databases to detach**</span></span>  
     <span data-ttu-id="bfb1e-179">Consente di visualizzare i database da scollegare.</span><span class="sxs-lookup"><span data-stu-id="bfb1e-179">Lists the databases to detach.</span></span>  
  
     <span data-ttu-id="bfb1e-180">**Nome database**</span><span class="sxs-lookup"><span data-stu-id="bfb1e-180">**Database Name**</span></span>  
     <span data-ttu-id="bfb1e-181">Consente di visualizzare il nome del database da scollegare.</span><span class="sxs-lookup"><span data-stu-id="bfb1e-181">Displays the name of the database to be detached.</span></span>  
  
     <span data-ttu-id="bfb1e-182">**Interrompi connessioni**</span><span class="sxs-lookup"><span data-stu-id="bfb1e-182">**Drop Connections**</span></span>  
     <span data-ttu-id="bfb1e-183">Consente di interrompere le connessioni al database specificato.</span><span class="sxs-lookup"><span data-stu-id="bfb1e-183">Disconnect connections to the specified database.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="bfb1e-184">Non è possibile scollegare un database con connessioni attive.</span><span class="sxs-lookup"><span data-stu-id="bfb1e-184">You cannot detach a database with active connections.</span></span>  
  
     <span data-ttu-id="bfb1e-185">**Aggiorna statistiche**</span><span class="sxs-lookup"><span data-stu-id="bfb1e-185">**Update Statistics**</span></span>  
     <span data-ttu-id="bfb1e-186">Per impostazione predefinita, con l'operazione di scollegamento è possibile mantenere eventuali statistiche di ottimizzazione non aggiornate prima di scollegare il database. Per aggiornare le statistiche di ottimizzazione esistenti, fare clic su questa casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="bfb1e-186">By default, the detach operation retains any out-of-date optimization statistics when detaching the database; to update the existing optimization statistics, click this check box.</span></span>  
  
     <span data-ttu-id="bfb1e-187">**Mantieni cataloghi full-text**</span><span class="sxs-lookup"><span data-stu-id="bfb1e-187">**Keep Full-Text Catalogs**</span></span>  
     <span data-ttu-id="bfb1e-188">Per impostazione predefinita, con l'operazione di scollegamento è possibile mantenere eventuali cataloghi full-text associati al database.</span><span class="sxs-lookup"><span data-stu-id="bfb1e-188">By default, the detach operation keeps any full-text catalogs that are associated with the database.</span></span> <span data-ttu-id="bfb1e-189">Per rimuoverli, deselezionare la casella di controllo **Mantieni cataloghi full-text** .</span><span class="sxs-lookup"><span data-stu-id="bfb1e-189">To remove them, clear the **Keep Full-Text Catalogs** check box.</span></span> <span data-ttu-id="bfb1e-190">Questa opzione è visualizzata solo quando si aggiorna un database da [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bfb1e-190">This option appears only when you are upgrading a database from [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)].</span></span>  
  
     <span data-ttu-id="bfb1e-191">**Status**</span><span class="sxs-lookup"><span data-stu-id="bfb1e-191">**Status**</span></span>  
     <span data-ttu-id="bfb1e-192">Consente di visualizzare uno degli stati seguenti: **Pronto** o **Non pronto**.</span><span class="sxs-lookup"><span data-stu-id="bfb1e-192">Displays one of the following states: **Ready** or **Not ready**.</span></span>  
  
     <span data-ttu-id="bfb1e-193">**Messaggio**</span><span class="sxs-lookup"><span data-stu-id="bfb1e-193">**Message**</span></span>  
     <span data-ttu-id="bfb1e-194">Nella colonna **Messaggio** possono essere visualizzate informazioni sul database simili alle seguenti:</span><span class="sxs-lookup"><span data-stu-id="bfb1e-194">The **Message** column may display information about the database, as follows:</span></span>  
  
    -   <span data-ttu-id="bfb1e-195">Quando un database è coinvolto nella replica, lo **Stato** è **Non pronto** e nella colonna **Messaggio** viene visualizzato **Database replicato**.</span><span class="sxs-lookup"><span data-stu-id="bfb1e-195">When a database is involved with replication, the **Status** is **Not ready** and the **Message** column displays **Database replicated**.</span></span>  
  
    -   <span data-ttu-id="bfb1e-196">Quando per un database esistono una o più connessioni attive, il valore di **Stato** è **Non pronto** e la colonna **Messaggio** visualizza _<number_of_active_connections>_ **Connessioni attive**, ad esempio: **Connessioni attive: 1**.</span><span class="sxs-lookup"><span data-stu-id="bfb1e-196">When a database has one or more active connections, the **Status** is **Not ready** and the **Message** column displays _<number_of_active_connections>_**Active connection(s)** - for example: **1 Active connection(s)**.</span></span> <span data-ttu-id="bfb1e-197">Prima di poter scollegare il database è necessario disconnettere tutte le connessioni attive selezionando **Interrompi connessioni**.</span><span class="sxs-lookup"><span data-stu-id="bfb1e-197">Before you can detach the database, you need to disconnect any active connections by selecting **Drop Connections**.</span></span>  
  
     <span data-ttu-id="bfb1e-198">Per ottenere ulteriori informazioni su un messaggio, fare clic sul testo del collegamento ipertestuale per aprire Monitoraggio attività.</span><span class="sxs-lookup"><span data-stu-id="bfb1e-198">To obtain more information about a message, click the hyperlinked text to open Activity Monitor.</span></span>  
  
2.  <span data-ttu-id="bfb1e-199">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="bfb1e-199">Click **OK**.</span></span>  
  
3.  <span data-ttu-id="bfb1e-200">Usando Esplora risorse spostare o copiare i file del database dal server di origine nello stesso percorso nel server di destinazione.</span><span class="sxs-lookup"><span data-stu-id="bfb1e-200">Using Windows Explorer, move or copy the database files from the source server to the same location on the destination server.</span></span>  
  
4.  <span data-ttu-id="bfb1e-201">Usando Esplora risorse spostare o copiare il backup dei file del certificato del server e della chiave privata dal server di origine nello stesso percorso nel server di destinazione.</span><span class="sxs-lookup"><span data-stu-id="bfb1e-201">Using Windows Explorer, move or copy the backup of the server certificate and the private key file from the source server to the same location on the destination server.</span></span>  
  
5.  <span data-ttu-id="bfb1e-202">Creare una chiave master del database nell'istanza di destinazione di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bfb1e-202">Create a database master key on the destination instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="bfb1e-203">Per altre informazioni, vedere **Uso di Transact-SQL** di seguito.</span><span class="sxs-lookup"><span data-stu-id="bfb1e-203">For more information, see **Using Transact-SQL** below.</span></span>  
  
6.  <span data-ttu-id="bfb1e-204">Ricreare il certificato del server usando il file di backup del certificato del server originale.</span><span class="sxs-lookup"><span data-stu-id="bfb1e-204">Recreate the server certificate by using the original server certificate backup file.</span></span> <span data-ttu-id="bfb1e-205">Per altre informazioni, vedere **Uso di Transact-SQL** di seguito.</span><span class="sxs-lookup"><span data-stu-id="bfb1e-205">For more information, see **Using Transact-SQL** below.</span></span>  
  
7.  <span data-ttu-id="bfb1e-206">In Esplora oggetti in [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], fare clic con il pulsante destro del mouse sulla cartella **Database** e selezionare **Collega...** .</span><span class="sxs-lookup"><span data-stu-id="bfb1e-206">In Object Explorer in [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], right-click the **Databases** folder and select **Attach...**.</span></span>  
  
8.  <span data-ttu-id="bfb1e-207">Nella finestra di dialogo **Collega database** , in **Database da collegare**fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="bfb1e-207">In the **Attach Databases** dialog box, under **Databases to attach**, click **Add**.</span></span>  
  
9. <span data-ttu-id="bfb1e-208">Nella finestra di dialogo **Individua file di database-**_server_name_ Selezionare il file di database da alporre al nuovo server e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="bfb1e-208">In the **Locate Database Files -**_server_name_ dialog box, select the database file to attach to the new server and click **OK**.</span></span>  
  
     <span data-ttu-id="bfb1e-209">Nella finestra di dialogo **Collega database** sono disponibili le opzioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="bfb1e-209">The following options are available in the **Attach Databases** dialog box.</span></span>  
  
     <span data-ttu-id="bfb1e-210">**Database da collegare**</span><span class="sxs-lookup"><span data-stu-id="bfb1e-210">**Databases to attach**</span></span>  
     <span data-ttu-id="bfb1e-211">Consente di visualizzare informazioni sui database selezionati.</span><span class="sxs-lookup"><span data-stu-id="bfb1e-211">Displays information about the selected databases.</span></span>  
  
     \<no column header>  
     <span data-ttu-id="bfb1e-212">Consente di visualizzare un'icona che indica lo stato dell'operazione di collegamento.</span><span class="sxs-lookup"><span data-stu-id="bfb1e-212">Displays an icon indicating the status of the attach operation.</span></span> <span data-ttu-id="bfb1e-213">Le icone possibili sono illustrate di seguito nella descrizione di **Stato** .</span><span class="sxs-lookup"><span data-stu-id="bfb1e-213">The possible icons are described in the **Status** description, below).</span></span>  
  
     <span data-ttu-id="bfb1e-214">**Percorso file MDF**</span><span class="sxs-lookup"><span data-stu-id="bfb1e-214">**MDF File Location**</span></span>  
     <span data-ttu-id="bfb1e-215">Consente di visualizzare il percorso e il nome del file MDF selezionato.</span><span class="sxs-lookup"><span data-stu-id="bfb1e-215">Displays the path and file name of the selected MDF file.</span></span>  
  
     <span data-ttu-id="bfb1e-216">**Nome database**</span><span class="sxs-lookup"><span data-stu-id="bfb1e-216">**Database Name**</span></span>  
     <span data-ttu-id="bfb1e-217">Consente di visualizzare il nome del database.</span><span class="sxs-lookup"><span data-stu-id="bfb1e-217">Displays the name of the database.</span></span>  
  
     <span data-ttu-id="bfb1e-218">**Collega come**</span><span class="sxs-lookup"><span data-stu-id="bfb1e-218">**Attach As**</span></span>  
     <span data-ttu-id="bfb1e-219">Facoltativamente, è possibile specificare un nome diverso per il database da collegare.</span><span class="sxs-lookup"><span data-stu-id="bfb1e-219">Optionally, specifies a different name for the database to attach as.</span></span>  
  
     <span data-ttu-id="bfb1e-220">**Proprietario**</span><span class="sxs-lookup"><span data-stu-id="bfb1e-220">**Owner**</span></span>  
     <span data-ttu-id="bfb1e-221">Consente di visualizzare un elenco a discesa di possibili proprietari del database in cui è possibile selezionare un proprietario diverso.</span><span class="sxs-lookup"><span data-stu-id="bfb1e-221">Provides a drop-down list of possible database owners from which you can optionally select a different owner.</span></span>  
  
     <span data-ttu-id="bfb1e-222">**Status**</span><span class="sxs-lookup"><span data-stu-id="bfb1e-222">**Status**</span></span>  
     <span data-ttu-id="bfb1e-223">Consente di visualizzare lo stato del base in base alla tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="bfb1e-223">Displays the status of the database according to the following table.</span></span>  
  
    |<span data-ttu-id="bfb1e-224">Icona</span><span class="sxs-lookup"><span data-stu-id="bfb1e-224">Icon</span></span>|<span data-ttu-id="bfb1e-225">Testo Stato</span><span class="sxs-lookup"><span data-stu-id="bfb1e-225">Status text</span></span>|<span data-ttu-id="bfb1e-226">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bfb1e-226">Description</span></span>|  
    |----------|-----------------|-----------------|  
    |<span data-ttu-id="bfb1e-227">(Nessuna icona)</span><span class="sxs-lookup"><span data-stu-id="bfb1e-227">(No icon)</span></span>|<span data-ttu-id="bfb1e-228">(Nessun testo)</span><span class="sxs-lookup"><span data-stu-id="bfb1e-228">(No text)</span></span>|<span data-ttu-id="bfb1e-229">L'operazione di collegamento non è stata avviata o può essere sospesa per questo oggetto.</span><span class="sxs-lookup"><span data-stu-id="bfb1e-229">Attach operation has not been started or may be pending for this object.</span></span> <span data-ttu-id="bfb1e-230">È il valore predefinito all'apertura della finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="bfb1e-230">This is the default when the dialog is opened.</span></span>|  
    |<span data-ttu-id="bfb1e-231">Triangolo verde che punta a destra</span><span class="sxs-lookup"><span data-stu-id="bfb1e-231">Green, right-pointing triangle</span></span>|<span data-ttu-id="bfb1e-232">In corso</span><span class="sxs-lookup"><span data-stu-id="bfb1e-232">In progress</span></span>|<span data-ttu-id="bfb1e-233">L'operazione di collegamento è stata avviata ma non ancora completata.</span><span class="sxs-lookup"><span data-stu-id="bfb1e-233">Attach operation has been started but it is not complete.</span></span>|  
    |<span data-ttu-id="bfb1e-234">Segno di spunta verde</span><span class="sxs-lookup"><span data-stu-id="bfb1e-234">Green check mark</span></span>|<span data-ttu-id="bfb1e-235">Operazione completata</span><span class="sxs-lookup"><span data-stu-id="bfb1e-235">Success</span></span>|<span data-ttu-id="bfb1e-236">L'oggetto è stato collegato.</span><span class="sxs-lookup"><span data-stu-id="bfb1e-236">The object has been attached successfully.</span></span>|  
    |<span data-ttu-id="bfb1e-237">Cerchio rosso con croce bianca</span><span class="sxs-lookup"><span data-stu-id="bfb1e-237">Red circle containing a white cross</span></span>|<span data-ttu-id="bfb1e-238">Errore</span><span class="sxs-lookup"><span data-stu-id="bfb1e-238">Error</span></span>|<span data-ttu-id="bfb1e-239">Si è verificato un errore durante l'operazione. Il collegamento non è stato completato.</span><span class="sxs-lookup"><span data-stu-id="bfb1e-239">Attach operation encountered an error and did not complete successfully.</span></span>|  
    |<span data-ttu-id="bfb1e-240">Cerchio con due quadranti neri a destra e a sinistra e due quadranti bianchi in alto e in basso</span><span class="sxs-lookup"><span data-stu-id="bfb1e-240">Circle containing two black quadrants (on left and right) and two white quadrants (on top and bottom)</span></span>|<span data-ttu-id="bfb1e-241">Arrestato</span><span class="sxs-lookup"><span data-stu-id="bfb1e-241">Stopped</span></span>|<span data-ttu-id="bfb1e-242">L'operazione di collegamento non è stata completata perché l'utente ne ha arrestato l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="bfb1e-242">Attach operation was not completed successfully because the user stopped the operation.</span></span>|  
    |<span data-ttu-id="bfb1e-243">Cerchio con freccia curva che punta in senso antiorario.</span><span class="sxs-lookup"><span data-stu-id="bfb1e-243">Circle containing a curved arrow pointing counter-clockwise</span></span>|<span data-ttu-id="bfb1e-244">È stato eseguito il rollback</span><span class="sxs-lookup"><span data-stu-id="bfb1e-244">Rolled Back</span></span>|<span data-ttu-id="bfb1e-245">L'operazione di collegamento è stata completata ma ne è stato eseguito il rollback a causa di un errore durante il collegamento di un altro oggetto.</span><span class="sxs-lookup"><span data-stu-id="bfb1e-245">Attach operation was successful but it has been rolled back due to an error during attachment of another object.</span></span>|  
  
     <span data-ttu-id="bfb1e-246">**Messaggio**</span><span class="sxs-lookup"><span data-stu-id="bfb1e-246">**Message**</span></span>  
     <span data-ttu-id="bfb1e-247">Non viene visualizzato alcun messaggio oppure viene visualizzato il collegamento ipertestuale "Impossibile trovare il file".</span><span class="sxs-lookup"><span data-stu-id="bfb1e-247">Displays either a blank message or a "File not found" hyperlink.</span></span>  
  
     <span data-ttu-id="bfb1e-248">**Aggiungere**</span><span class="sxs-lookup"><span data-stu-id="bfb1e-248">**Add**</span></span>  
     <span data-ttu-id="bfb1e-249">Consente di individuare i file principali del database necessari.</span><span class="sxs-lookup"><span data-stu-id="bfb1e-249">Find the necessary main database files.</span></span> <span data-ttu-id="bfb1e-250">Se l'utente seleziona un file con estensione mdf, le informazioni appropriate vengono inserite automaticamente nei rispettivi campi della griglia **Database da collegare** .</span><span class="sxs-lookup"><span data-stu-id="bfb1e-250">When the user selects an .mdf file, applicable information is automatically filled in the respective fields of the **Databases to attach** grid.</span></span>  
  
     <span data-ttu-id="bfb1e-251">**Rimuovi**</span><span class="sxs-lookup"><span data-stu-id="bfb1e-251">**Remove**</span></span>  
     <span data-ttu-id="bfb1e-252">Consente di rimuovere il file selezionato dalla griglia **Database da collegare** .</span><span class="sxs-lookup"><span data-stu-id="bfb1e-252">Removes the selected file from the **Databases to attach** grid.</span></span>  
  
     <span data-ttu-id="bfb1e-253">**"** _<nome_database>_ **" dettagli database**</span><span class="sxs-lookup"><span data-stu-id="bfb1e-253">**"** _<database_name>_ **" database details**</span></span>  
     <span data-ttu-id="bfb1e-254">Consente di visualizzare i nomi dei file da collegare.</span><span class="sxs-lookup"><span data-stu-id="bfb1e-254">Displays the names of the files to be attached.</span></span> <span data-ttu-id="bfb1e-255">Per verificare o modificare il percorso di un file, fare clic sul pulsante **Sfoglia** ( **...** ).</span><span class="sxs-lookup"><span data-stu-id="bfb1e-255">To verify or change the pathname of a file, click the **Browse** button (**...**).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="bfb1e-256">Se il file non esiste, nella colonna **Messaggio** verrà visualizzato il testo "File non trovato".</span><span class="sxs-lookup"><span data-stu-id="bfb1e-256">If a file does not exist, the **Message** column displays "Not found."</span></span> <span data-ttu-id="bfb1e-257">Se non rilevato, un file di log può trovarsi in un'altra directory o essere stato eliminato.</span><span class="sxs-lookup"><span data-stu-id="bfb1e-257">If a log file is not found, it exists in another directory or has been deleted.</span></span> <span data-ttu-id="bfb1e-258">È necessario aggiornare il percorso del file nella griglia **Dettagli database** in modo che indichi la posizione corretta oppure rimuovere il file di log dalla griglia.</span><span class="sxs-lookup"><span data-stu-id="bfb1e-258">You need to either update the file path in the **database details** grid to point to the correct location or remove the log file from the grid.</span></span> <span data-ttu-id="bfb1e-259">Se non viene rilevato un file di dati con estensione ndf, è necessario aggiornare il percorso nella griglia in modo che indichi la posizione corretta.</span><span class="sxs-lookup"><span data-stu-id="bfb1e-259">If an .ndf data file is not found, you need to update its path in the grid to point to the correct location.</span></span>  
  
     <span data-ttu-id="bfb1e-260">**Nome file originale**</span><span class="sxs-lookup"><span data-stu-id="bfb1e-260">**Original File Name**</span></span>  
     <span data-ttu-id="bfb1e-261">Consente di visualizzare il nome del file collegato appartenente al database.</span><span class="sxs-lookup"><span data-stu-id="bfb1e-261">Displays the name of the attached file belonging to the database.</span></span>  
  
     <span data-ttu-id="bfb1e-262">**Tipo di file**</span><span class="sxs-lookup"><span data-stu-id="bfb1e-262">**File Type**</span></span>  
     <span data-ttu-id="bfb1e-263">Indica il tipo di file, ovvero **Dati** o **Log**.</span><span class="sxs-lookup"><span data-stu-id="bfb1e-263">Indicates the type of file, **Data** or **Log**.</span></span>  
  
     <span data-ttu-id="bfb1e-264">**Percorso file corrente**</span><span class="sxs-lookup"><span data-stu-id="bfb1e-264">**Current File Path**</span></span>  
     <span data-ttu-id="bfb1e-265">Consente di visualizzare il percorso del file di database selezionato.</span><span class="sxs-lookup"><span data-stu-id="bfb1e-265">Displays the path to the selected database file.</span></span> <span data-ttu-id="bfb1e-266">Il percorso può essere modificato manualmente.</span><span class="sxs-lookup"><span data-stu-id="bfb1e-266">The path can be edited manually.</span></span>  
  
     <span data-ttu-id="bfb1e-267">**Messaggio**</span><span class="sxs-lookup"><span data-stu-id="bfb1e-267">**Message**</span></span>  
     <span data-ttu-id="bfb1e-268">Non viene visualizzato alcun messaggio oppure viene visualizzato il collegamento ipertestuale**Impossibile trovare il file**.</span><span class="sxs-lookup"><span data-stu-id="bfb1e-268">Displays either a blank message or a "**File not found**" hyperlink.</span></span>  
  
###  <a name="using-transact-sql"></a><a name="TsqlMove"></a> <span data-ttu-id="bfb1e-269">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="bfb1e-269">Using Transact-SQL</span></span>  
  
1.  <span data-ttu-id="bfb1e-270">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bfb1e-270">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="bfb1e-271">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="bfb1e-271">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="bfb1e-272">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="bfb1e-272">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Detach the TDE protected database from the source server.   
    USE master ;  
    GO  
    EXEC master.dbo.sp_detach_db @dbname = N'CustRecords';  
    GO  
    -- Move or copy the database files from the source server to the same location on the destination server.   
    -- Move or copy the backup of the server certificate and the private key file from the source server to the same location on the destination server.   
    -- Create a database master key on the destination instance of SQL Server.   
    USE master;  
    GO  
    CREATE MASTER KEY ENCRYPTION BY PASSWORD = '*rt@40(FL&dasl1';  
    GO  
    -- Recreate the server certificate by using the original server certificate backup file.   
    -- The password must be the same as the password that was used when the backup was created.  
  
    CREATE CERTIFICATE TestSQLServerCert   
    FROM FILE = 'TestSQLServerCert'  
    WITH PRIVATE KEY   
    (  
        FILE = 'SQLPrivateKeyFile',  
        DECRYPTION BY PASSWORD = '*rt@40(FL&dasl1'  
    );  
    GO  
    -- Attach the database that is being moved.   
    -- The path of the database files must be the location where you have stored the database files.  
    CREATE DATABASE [CustRecords] ON   
    ( FILENAME = N'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\DATA\CustRecords.mdf' ),  
    ( FILENAME = N'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\DATA\CustRecords_log.LDF' )  
    FOR ATTACH ;  
    GO  
    ```  
  
 <span data-ttu-id="bfb1e-273">Per altre informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="bfb1e-273">For more information, see:</span></span>  
  
-   [<span data-ttu-id="bfb1e-274">sp_detach_db &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="bfb1e-274">sp_detach_db &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-detach-db-transact-sql)  
  
-   [<span data-ttu-id="bfb1e-275">CREATE MASTER KEY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="bfb1e-275">CREATE MASTER KEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-master-key-transact-sql)  
  
-   [<span data-ttu-id="bfb1e-276">CREATE CERTIFICATE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="bfb1e-276">CREATE CERTIFICATE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-certificate-transact-sql)  
  
-   [<span data-ttu-id="bfb1e-277">CREATE DATABASE &#40;SQL Server Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="bfb1e-277">CREATE DATABASE &#40;SQL Server Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-database-sql-server-transact-sql)  
  
## <a name="see-also"></a><span data-ttu-id="bfb1e-278">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bfb1e-278">See Also</span></span>  
 [<span data-ttu-id="bfb1e-279">Collegamento e scollegamento di un database &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="bfb1e-279">Database Detach and Attach &#40;SQL Server&#41;</span></span>](../../databases/database-detach-and-attach-sql-server.md)  
  
  
