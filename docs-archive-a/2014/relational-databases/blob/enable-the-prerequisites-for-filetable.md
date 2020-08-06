---
title: Abilitare i prerequisiti per la tabella FileTable | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: filestream
ms.topic: conceptual
helpviewer_keywords:
- FileTables [SQL Server], prerequisites
ms.assetid: 6286468c-9dc9-4eda-9961-071d2a36ebd6
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5d5d2c5dab7909ec5403911d482823f488cdd809
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623351"
---
# <a name="enable-the-prerequisites-for-filetable"></a><span data-ttu-id="ca432-102">Abilitazione dei prerequisiti per la tabella FileTable</span><span class="sxs-lookup"><span data-stu-id="ca432-102">Enable the Prerequisites for FileTable</span></span>
  <span data-ttu-id="ca432-103">Viene descritto come abilitare i prerequisiti per la creazione e l'utilizzo di tabelle FileTable.</span><span class="sxs-lookup"><span data-stu-id="ca432-103">Describes how to enable the prerequisites for creating and using FileTables.</span></span>  
  
##  <a name="enabling-the-prerequisites-for-filetable"></a><a name="EnablePrereq"></a> <span data-ttu-id="ca432-104">Abilitazione dei prerequisiti per la tabella FileTable</span><span class="sxs-lookup"><span data-stu-id="ca432-104">Enabling the Prerequisites for FileTable</span></span>  
 <span data-ttu-id="ca432-105">Per abilitare i prerequisiti per la creazione e l'utilizzo di tabelle FileTable, abilitare gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="ca432-105">To enable the prerequisites for creating and using FileTables, enable the following items:</span></span>  
  
-   <span data-ttu-id="ca432-106">**A livello di istanza:**</span><span class="sxs-lookup"><span data-stu-id="ca432-106">**At the instance level:**</span></span>  
  
    -   [<span data-ttu-id="ca432-107">Abilitazione di FILESTREAM a livello di istanza</span><span class="sxs-lookup"><span data-stu-id="ca432-107">Enabling FILESTREAM at the Instance Level</span></span>](#BasicsFilestream)  
  
-   <span data-ttu-id="ca432-108">**A livello di database:**</span><span class="sxs-lookup"><span data-stu-id="ca432-108">**At the database level:**</span></span>  
  
    -   [<span data-ttu-id="ca432-109">Fornitura di un filegroup FILESTREAM a livello di database</span><span class="sxs-lookup"><span data-stu-id="ca432-109">Providing a FILESTREAM Filegroup at the Database Level</span></span>](#filegroup)  
  
    -   [<span data-ttu-id="ca432-110">Abilitazione dell'accesso non transazionale a livello di database</span><span class="sxs-lookup"><span data-stu-id="ca432-110">Enabling Non-Transactional Access at the Database Level</span></span>](#BasicsNTAccess)  
  
    -   [<span data-ttu-id="ca432-111">Specifica di una directory per tabelle FileTable a livello di database</span><span class="sxs-lookup"><span data-stu-id="ca432-111">Specifying a Directory for FileTables at the Database Level</span></span>](#BasicsDirectory)  
  
##  <a name="enabling-filestream-at-the-instance-level"></a><a name="BasicsFilestream"></a> <span data-ttu-id="ca432-112">Abilitazione di FILESTREAM a livello di istanza</span><span class="sxs-lookup"><span data-stu-id="ca432-112">Enabling FILESTREAM at the Instance Level</span></span>  
 <span data-ttu-id="ca432-113">Le tabelle FileTable estendono le funzionalità della caratteristica FILESTREAM di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ca432-113">FileTables extend the capabilities of the FILESTREAM feature of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="ca432-114">È pertanto necessario abilitare FILESTREAM per l'accesso I/O ai file a livello di Windows e nell'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] prima di poter creare e usare le tabelle FileTable.</span><span class="sxs-lookup"><span data-stu-id="ca432-114">Therefore you have to enable FILESTREAM for file I/O access at the Windows level and on the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] before you can create and use FileTables.</span></span>  
  
###  <a name="how-to-enable-filestream-at-the-instance-level"></a><a name="HowToFilestream"></a> <span data-ttu-id="ca432-115">Procedura: Abilitare FILESTREAM a livello di istanza</span><span class="sxs-lookup"><span data-stu-id="ca432-115">How To: Enable FILESTREAM at the Instance Level</span></span>  
 <span data-ttu-id="ca432-116">Per informazioni su come abilitare FILESTREAM, vedere [Abilitare e configurare FILESTREAM](enable-and-configure-filestream.md).</span><span class="sxs-lookup"><span data-stu-id="ca432-116">For information about how to enable FILESTREAM, see [Enable and Configure FILESTREAM](enable-and-configure-filestream.md).</span></span>  
  
 <span data-ttu-id="ca432-117">Quando si chiama `sp_configure` per abilitare FILESTREAM a livello di istanza, è necessario impostare l'opzione filestream_access_level su 2.</span><span class="sxs-lookup"><span data-stu-id="ca432-117">When you call `sp_configure` to enable FILESTREAM at the instance level, you have to set the filestream_access_level option to 2.</span></span> <span data-ttu-id="ca432-118">Per altre informazioni, vedere [Opzione di configurazione del server filestream access level](../../database-engine/configure-windows/filestream-access-level-server-configuration-option.md).</span><span class="sxs-lookup"><span data-stu-id="ca432-118">For more information, see [filestream access level Server Configuration Option](../../database-engine/configure-windows/filestream-access-level-server-configuration-option.md).</span></span>  
  
###  <a name="how-to-allow-filestream-through-the-firewall"></a><a name="firewall"></a> <span data-ttu-id="ca432-119">Procedura: Abilitare FILESTREAM attraverso il firewall</span><span class="sxs-lookup"><span data-stu-id="ca432-119">How To: Allow FILESTREAM through the Firewall</span></span>  
 <span data-ttu-id="ca432-120">Per informazioni sull'abilitazione di FILESTREAM attraverso il firewall, vedere [Configure a Firewall for FILESTREAM Access](configure-a-firewall-for-filestream-access.md).</span><span class="sxs-lookup"><span data-stu-id="ca432-120">For information about how to allow FILESTREAM through the firewall, see [Configure a Firewall for FILESTREAM Access](configure-a-firewall-for-filestream-access.md).</span></span>  
  
##  <a name="providing-a-filestream-filegroup-at-the-database-level"></a><a name="filegroup"></a> <span data-ttu-id="ca432-121">Fornitura di un filegroup FILESTREAM a livello di database</span><span class="sxs-lookup"><span data-stu-id="ca432-121">Providing a FILESTREAM Filegroup at the Database Level</span></span>  
 <span data-ttu-id="ca432-122">Per poter creare FileTable in un database, è necessario che il database disponga di un filegroup FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="ca432-122">Before you can create FileTables in a database, the database must have a FILESTREAM filegroup.</span></span> <span data-ttu-id="ca432-123">Per altre informazioni su questo prerequisito, vedere [Creare un database abilitato per FILESTREAM](create-a-filestream-enabled-database.md).</span><span class="sxs-lookup"><span data-stu-id="ca432-123">For more information about this prerequisite, see [Create a FILESTREAM-Enabled Database](create-a-filestream-enabled-database.md).</span></span>  
  
##  <a name="enabling-non-transactional-access-at-the-database-level"></a><a name="BasicsNTAccess"></a> <span data-ttu-id="ca432-124">Abilitazione dell'accesso non transazionale a livello di database</span><span class="sxs-lookup"><span data-stu-id="ca432-124">Enabling Non-Transactional Access at the Database Level</span></span>  
 <span data-ttu-id="ca432-125">Le tabelle FileTable consentono alle applicazioni di Windows di ottenere un handle di file Windows per i dati FILESTREAM senza che sia necessaria una transazione.</span><span class="sxs-lookup"><span data-stu-id="ca432-125">FileTables let Windows applications obtain a Windows file handle to FILESTREAM data without requiring a transaction.</span></span> <span data-ttu-id="ca432-126">Per consentire questo accesso non transazionale ai file archiviati in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], è necessario specificare il livello desiderato di accesso non transazionale a livello di database per ogni database che conterrà le tabelle FileTable.</span><span class="sxs-lookup"><span data-stu-id="ca432-126">To allow this non-transactional access to files stored in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you have to specify the desired level of non-transactional access at the database level for each database that will contain FileTables.</span></span>  
  
###  <a name="how-to-check-whether-non-transactional-access-is-enabled-on-databases"></a><a name="HowToCheckAccess"></a> <span data-ttu-id="ca432-127">Procedura: Verificare l'abilitazione dell'accesso non transazionale nei database</span><span class="sxs-lookup"><span data-stu-id="ca432-127">How To: Check Whether Non-Transactional Access Is Enabled on Databases</span></span>  
 <span data-ttu-id="ca432-128">Eseguire una query sulla vista del catalogo [sys.database_filestream_options &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-filestream-options-transact-sql) e verificare le colonne **non_transacted_access** e **non_transacted_access_desc**.</span><span class="sxs-lookup"><span data-stu-id="ca432-128">Query the catalog view [sys.database_filestream_options &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-filestream-options-transact-sql) and check the **non_transacted_access** and **non_transacted_access_desc** columns.</span></span>  
  
```sql  
SELECT DB_NAME(database_id), non_transacted_access, non_transacted_access_desc  
    FROM sys.database_filestream_options;  
GO  
```  
  
###  <a name="how-to-enable-non-transactional-access-at-the-database-level"></a><a name="HowToNTAccess"></a> <span data-ttu-id="ca432-129">Procedura: Abilitare l'accesso non transazionale a livello di database</span><span class="sxs-lookup"><span data-stu-id="ca432-129">How To: Enable Non-Transactional Access at the Database Level</span></span>  
 <span data-ttu-id="ca432-130">I livelli disponibili di accesso non transazionale sono FULL, READ_ONLY e OFF.</span><span class="sxs-lookup"><span data-stu-id="ca432-130">The available levels of non-transactional access are FULL, READ_ONLY, and OFF.</span></span>  
  
 <span data-ttu-id="ca432-131">**Specificare il livello di accesso non transazionale tramite Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="ca432-131">**Specify the level of non-transactional access by using Transact-SQL**</span></span>  
 -   <span data-ttu-id="ca432-132">Quando si **crea un nuovo database**, chiamare l'istruzione [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) con l'opzione FILESTREAM **NON_TRANSACTED_ACCESS**.</span><span class="sxs-lookup"><span data-stu-id="ca432-132">When you **create a new database**, call the [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) statement with the **NON_TRANSACTED_ACCESS** FILESTREAM option.</span></span>  
  
    ```sql  
    CREATE DATABASE database_name  
        WITH FILESTREAM ( NON_TRANSACTED_ACCESS = FULL, DIRECTORY_NAME = N'directory_name' )  
    ```  
  
-   <span data-ttu-id="ca432-133">Quando si **modifica un database esistente**, chiamare l'istruzione [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) con l'opzione FILESTREAM **NON_TRANSACTED_ACCESS**.</span><span class="sxs-lookup"><span data-stu-id="ca432-133">When you **alter an existing database**, call the [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) statement with the **NON_TRANSACTED_ACCESS** FILESTREAM option.</span></span>  
  
    ```sql  
    ALTER DATABASE database_name  
        SET FILESTREAM ( NON_TRANSACTED_ACCESS = FULL, DIRECTORY_NAME = N'directory_name' )  
    ```  
  
 <span data-ttu-id="ca432-134">**Specificare il livello di accesso non transazionale tramite SQL Server Management Studio**</span><span class="sxs-lookup"><span data-stu-id="ca432-134">**Specify the level of non-transactional access by using SQL Server Management Studio**</span></span>  
 <span data-ttu-id="ca432-135">È possibile specificare il livello di accesso non transazionale nel campo **Accesso FILESTREAM non transazionale** della pagina **Opzioni** della finestra di dialogo **Proprietà database** .</span><span class="sxs-lookup"><span data-stu-id="ca432-135">You can specify the level of non-transactional access in the **FILESTREAM Non-transacted Access** field of the **Options** page of the **Database Properties** dialog box.</span></span> <span data-ttu-id="ca432-136">Per altre informazioni su questa finestra di dialogo, vedere [Proprietà del database &#40;pagina Opzioni&#41;](../databases/database-properties-options-page.md).</span><span class="sxs-lookup"><span data-stu-id="ca432-136">For more information about this dialog box, see [Database Properties &#40;Options Page&#41;](../databases/database-properties-options-page.md).</span></span>  
  
##  <a name="specifying-a-directory-for-filetables-at-the-database-level"></a><a name="BasicsDirectory"></a> <span data-ttu-id="ca432-137">Specifica di una directory per tabelle FileTable a livello di database</span><span class="sxs-lookup"><span data-stu-id="ca432-137">Specifying a Directory for FileTables at the Database Level</span></span>  
 <span data-ttu-id="ca432-138">Quando si abilita l'accesso non transazionale ai file a livello di database, è anche possibile specificare simultaneamente un nome di directory usando l'opzione **DIRECTORY_NAME** .</span><span class="sxs-lookup"><span data-stu-id="ca432-138">When you enable non-transactional access to files at the database level, you can optionally provide a directory name at the same time by using the **DIRECTORY_NAME** option.</span></span> <span data-ttu-id="ca432-139">Se non si specifica un nome di directory quando si abilita l'accesso non transazionale, è necessario specificarlo in seguito prima di poter creare le tabelle FileTable nel database.</span><span class="sxs-lookup"><span data-stu-id="ca432-139">If you do not provide a directory name when you enable non-transactional access, then you have to provide it later before you can create FileTables in the database.</span></span>  
  
 <span data-ttu-id="ca432-140">Nella gerarchia di cartelle FileTable questa directory a livello di database diventa l'elemento figlio del nome di condivisione specificato per FILESTREAM a livello di istanza e l'elemento padre delle tabelle FileTable create nel database.</span><span class="sxs-lookup"><span data-stu-id="ca432-140">In the FileTable folder hierarchy, this database-level directory becomes the child of the share name specified for FILESTREAM at the instance level, and the parent of the FileTables created in the database.</span></span> <span data-ttu-id="ca432-141">Per altre informazioni, vedere [Work with Directories and Paths in FileTables](work-with-directories-and-paths-in-filetables.md).</span><span class="sxs-lookup"><span data-stu-id="ca432-141">For more information, see [Work with Directories and Paths in FileTables](work-with-directories-and-paths-in-filetables.md).</span></span>  
  
###  <a name="how-to-specify-a-directory-for-filetables-at-the-database-level"></a><a name="HowToDirectory"></a> <span data-ttu-id="ca432-142">Procedura: Specificare una directory per tabelle FileTable a livello di database</span><span class="sxs-lookup"><span data-stu-id="ca432-142">How To: Specify a Directory for FileTables at the Database Level</span></span>  
 <span data-ttu-id="ca432-143">Il nome specificato deve essere univoco in tutta l'istanza per le directory a livello di database.</span><span class="sxs-lookup"><span data-stu-id="ca432-143">The name that you specify must be unique across the instance for database-level directories.</span></span>  
  
 <span data-ttu-id="ca432-144">**Specificare una directory per tabelle FileTable tramite Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="ca432-144">**Specify a directory for FileTables by using Transact-SQL**</span></span>  
 -   <span data-ttu-id="ca432-145">Quando si **crea un nuovo database**, chiamare l'istruzione [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) con l'opzione FILESTREAM **DIRECTORY_NAME**.</span><span class="sxs-lookup"><span data-stu-id="ca432-145">When you **create a new database**, call the [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) statement with the **DIRECTORY_NAME** FILESTREAM option.</span></span>  
  
    ```sql  
    CREATE DATABASE database_name  
        WITH FILESTREAM ( NON_TRANSACTED_ACCESS = FULL, DIRECTORY_NAME = N'directory_name' );  
    GO  
    ```  
  
-   <span data-ttu-id="ca432-146">Quando si **modifica un database esistente**, chiamare l'istruzione [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) con l'opzione FILESTREAM **DIRECTORY_NAME**.</span><span class="sxs-lookup"><span data-stu-id="ca432-146">When you **alter an existing database**, call the [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) statement with the **DIRECTORY_NAME** FILESTREAM option.</span></span> <span data-ttu-id="ca432-147">Quando si usano queste opzioni per modificare il nome di directory, è necessario bloccare il database in modo esclusivo, senza handle di file aperti.</span><span class="sxs-lookup"><span data-stu-id="ca432-147">When you use these options to change the directory name, the database must be exclusively locked, with no open file handles.</span></span>  
  
    ```sql  
    ALTER DATABASE database_name  
        SET FILESTREAM ( NON_TRANSACTED_ACCESS = FULL, DIRECTORY_NAME = N'directory_name' );  
    GO  
    ```  
  
-   <span data-ttu-id="ca432-148">Quando si **collega un database**, chiamare l'istruzione [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) con l'opzione **FOR ATTACH** e con l'opzione FILESTREAM **DIRECTORY_NAME**.</span><span class="sxs-lookup"><span data-stu-id="ca432-148">When you **attach a database**, call the [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) statement with the **FOR ATTACH** option and with the **DIRECTORY_NAME** FILESTREAM option.</span></span>  
  
    ```sql  
    CREATE DATABASE database_name  
        FOR ATTACH WITH FILESTREAM ( DIRECTORY_NAME = N'directory_name' );  
    GO  
    ```  
  
-   <span data-ttu-id="ca432-149">Quando si **ripristina un database**, chiamare l'istruzione [RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) con l'opzione FILESTREAM **DIRECTORY_NAME**.</span><span class="sxs-lookup"><span data-stu-id="ca432-149">When you **restore a database**, call the [RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) statement with the **DIRECTORY_NAME** FILESTREAM option.</span></span>  
  
    ```sql  
    RESTORE DATABASE database_name  
        WITH FILESTREAM ( DIRECTORY_NAME = N'directory_name' );  
    GO  
    ```  
  
 <span data-ttu-id="ca432-150">**Specificare una directory per tabelle FileTable tramite SQL Server Management Studio**</span><span class="sxs-lookup"><span data-stu-id="ca432-150">**Specify a directory for FileTables by using SQL Server Management Studio**</span></span>  
 <span data-ttu-id="ca432-151">È possibile specificare un nome di directory nel campo **Nome di directory FILESTREAM** della pagina **Opzioni** della finestra di dialogo **Proprietà database** .</span><span class="sxs-lookup"><span data-stu-id="ca432-151">You can specify a directory name in the **FILESTREAM Directory Name** field of the **Options** page of the **Database Properties** dialog box.</span></span> <span data-ttu-id="ca432-152">Per altre informazioni su questa finestra di dialogo, vedere [Proprietà del database &#40;pagina Opzioni&#41;](../databases/database-properties-options-page.md).</span><span class="sxs-lookup"><span data-stu-id="ca432-152">For more information about this dialog box, see [Database Properties &#40;Options Page&#41;](../databases/database-properties-options-page.md).</span></span>  
  
###  <a name="how-to-view-existing-directory-names-for-the-instance"></a><a name="viewnames"></a> <span data-ttu-id="ca432-153">Procedura: Visualizzare i nomi di directory esistenti per l'istanza</span><span class="sxs-lookup"><span data-stu-id="ca432-153">How to: View Existing Directory Names for the Instance</span></span>  
 <span data-ttu-id="ca432-154">Per visualizzare l'elenco di nomi di directory esistenti per l'istanza, eseguire una query sulla vista del catalogo [sys.database_filestream_options &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-filestream-options-transact-sql) e verificare la colonna **filestream_database_directory_name**.</span><span class="sxs-lookup"><span data-stu-id="ca432-154">To view the list of existing directory names for the instance, query the catalog view [sys.database_filestream_options &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-filestream-options-transact-sql) and check the **filestream_database_directory_name** column.</span></span>  
  
```sql  
SELECT DB_NAME ( database_id ), directory_name  
    FROM sys.database_filestream_options;  
GO  
```  
  
###  <a name="requirements-and-restrictions-for-the-database-level-directory"></a><a name="ReqDirectory"></a> <span data-ttu-id="ca432-155">Requisiti e restrizioni per la directory a livello di database</span><span class="sxs-lookup"><span data-stu-id="ca432-155">Requirements and Restrictions for the Database-Level Directory</span></span>  
  
-   <span data-ttu-id="ca432-156">L'impostazione di **DIRECTORY_NAME** è facoltativa quando si chiama **CREATE DATABASE** o **ALTER DATABASE**.</span><span class="sxs-lookup"><span data-stu-id="ca432-156">Setting the **DIRECTORY_NAME** is optional when you call **CREATE DATABASE** or **ALTER DATABASE**.</span></span> <span data-ttu-id="ca432-157">Se non si specifica un valore per **DIRECTORY_NAME**, il nome di directory rimane Null.</span><span class="sxs-lookup"><span data-stu-id="ca432-157">If you do not specify a value for **DIRECTORY_NAME**, then the directory name remains null.</span></span> <span data-ttu-id="ca432-158">Non è tuttavia possibile creare tabelle FileTable nel database se prima non si specifica un valore per **DIRECTORY_NAME** a livello di database.</span><span class="sxs-lookup"><span data-stu-id="ca432-158">However you cannot create FileTables in the database until you specify a value for **DIRECTORY_NAME** at the database level.</span></span>  
  
-   <span data-ttu-id="ca432-159">Il nome di directory specificato deve essere conforme ai requisiti del file system relativi ai nomi di directory validi.</span><span class="sxs-lookup"><span data-stu-id="ca432-159">The directory name that you provide must comply with the requirements of the file system for a valid directory name.</span></span>  
  
-   <span data-ttu-id="ca432-160">Quando il database contiene tabelle FileTable, non è possibile reimpostare **DIRECTORY_NAME** su un valore Null.</span><span class="sxs-lookup"><span data-stu-id="ca432-160">When the database contains FileTables, you cannot set the **DIRECTORY_NAME** back to a null value.</span></span>  
  
-   <span data-ttu-id="ca432-161">Quando si collega o ripristina un database, l'operazione non riesce se il nuovo database include un valore per **DIRECTORY_NAME** già presente nell'istanza di destinazione.</span><span class="sxs-lookup"><span data-stu-id="ca432-161">When you attach or restore a database, the operation fails if the new database has a value for **DIRECTORY_NAME** that already exists in the target instance.</span></span> <span data-ttu-id="ca432-162">Specificare un valore univoco per **DIRECTORY_NAME** quando si chiama **CREATE DATABASE FOR ATTACH** o **RESTORE DATABASE**.</span><span class="sxs-lookup"><span data-stu-id="ca432-162">Specify a unique value for **DIRECTORY_NAME** when you call **CREATE DATABASE FOR ATTACH** or **RESTORE DATABASE**.</span></span>  
  
-   <span data-ttu-id="ca432-163">Quando si aggiorna un database esistente a [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], il valore di **DIRECTORY_NAME** è Null.</span><span class="sxs-lookup"><span data-stu-id="ca432-163">When you upgrade an existing database to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], the value of **DIRECTORY_NAME** is null.</span></span>  
  
-   <span data-ttu-id="ca432-164">Quando si abilita o disabilita l'accesso non transazionale a livello di database, l'operazione non verifica se è stato specificato il nome di directory o se questo è univoco.</span><span class="sxs-lookup"><span data-stu-id="ca432-164">When you enable or disable non-transactional access at the database level, the operation does not check whether the directory name has been specified or whether it is unique.</span></span>  
  
-   <span data-ttu-id="ca432-165">Quando si elimina un database abilitato per tabelle FileTable, vengono rimosse la directory a livello di database e tutte le strutture di directory di tutte le tabelle FileTable in essa contenute.</span><span class="sxs-lookup"><span data-stu-id="ca432-165">When you drop a database that was enabled for FileTables, the database-level directory and all the directory stuctures of all the FileTables under it are removed.</span></span>  
  
  
