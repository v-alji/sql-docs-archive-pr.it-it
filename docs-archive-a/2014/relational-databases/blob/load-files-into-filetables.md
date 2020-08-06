---
title: Caricare file in FileTable | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: filestream
ms.topic: conceptual
helpviewer_keywords:
- FileTables [SQL Server], migrating files
- FileTables [SQL Server], bulk loading
- FileTables [SQL Server], loading files
ms.assetid: dc842a10-0586-4b0f-9775-5ca0ecc761d9
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 43ea31523da2dfa8b387f68ce4f7c7f07868dd6f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723935"
---
# <a name="load-files-into-filetables"></a><span data-ttu-id="dffab-102">Caricamento di file in FileTable</span><span class="sxs-lookup"><span data-stu-id="dffab-102">Load Files into FileTables</span></span>
  <span data-ttu-id="dffab-103">Viene descritto come caricare o eseguire la migrazione dei file in tabelle FileTable.</span><span class="sxs-lookup"><span data-stu-id="dffab-103">Describes how to load or migrate files into FileTables.</span></span>  
  
##  <a name="loading-or-migrating-files-into-a-filetable"></a><a name="BasicsLoadNew"></a> <span data-ttu-id="dffab-104">Caricamento o migrazione di file in tabelle FileTable</span><span class="sxs-lookup"><span data-stu-id="dffab-104">Loading or Migrating Files into a FileTable</span></span>  
 <span data-ttu-id="dffab-105">Il metodo scelto per il caricamento o la migrazione di file in una tabella FileTable dipende dalla posizione in cui sono attualmente archiviati i file.</span><span class="sxs-lookup"><span data-stu-id="dffab-105">The method that you choose for loading or migrating files into a FileTable depends on where the files are currently stored.</span></span>  
  
|<span data-ttu-id="dffab-106">Attuale posizione dei file</span><span class="sxs-lookup"><span data-stu-id="dffab-106">Current location of files</span></span>|<span data-ttu-id="dffab-107">Opzioni per migrazione</span><span class="sxs-lookup"><span data-stu-id="dffab-107">Options for migration</span></span>|  
|-------------------------------|---------------------------|  
|<span data-ttu-id="dffab-108">I file sono attualmente archiviati nel file system.</span><span class="sxs-lookup"><span data-stu-id="dffab-108">Files are currently stored in the file system.</span></span><br /><br /> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="dffab-109">non dispone di conoscenza dei file.</span><span class="sxs-lookup"><span data-stu-id="dffab-109">has no knowledge of the files.</span></span>|<span data-ttu-id="dffab-110">Poiché una tabella FileTable viene visualizzata come cartella nel file system di Windows, è possibile caricare facilmente file in un nuova tabella FileTable tramite alcuni dei metodi disponibili per lo spostamento o la copia di file.</span><span class="sxs-lookup"><span data-stu-id="dffab-110">Since a FileTable appears as a folder in the Windows file system, you can easily load files into a new FileTable by using any of the available methods for moving or copying files.</span></span> <span data-ttu-id="dffab-111">Questi metodi includono Esplora risorse, opzioni della riga di comando come xcopy e robocopy e applicazioni o script personalizzati.</span><span class="sxs-lookup"><span data-stu-id="dffab-111">These methods include Windows Explorer, command line options including xcopy and robocopy, and custom scripts or applications.</span></span><br /><br /> <span data-ttu-id="dffab-112">Non è possibile convertire una cartella esistente in tabella FileTable.</span><span class="sxs-lookup"><span data-stu-id="dffab-112">You cannot convert an existing folder to a FileTable.</span></span>|  
|<span data-ttu-id="dffab-113">I file sono attualmente archiviati nel file system.</span><span class="sxs-lookup"><span data-stu-id="dffab-113">Files are currently stored in the file system.</span></span><br /><br /> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="dffab-114">include una tabella di metadati contenente puntatori ai file.</span><span class="sxs-lookup"><span data-stu-id="dffab-114">contains a table of metadata that contains pointers to the files.</span></span>|<span data-ttu-id="dffab-115">Il primo passaggio consiste nello spostare o copiare i file tramite uno dei metodi indicati in precedenza.</span><span class="sxs-lookup"><span data-stu-id="dffab-115">The first step is to move or copy the files by using one of the methods mentioned above.</span></span><br /><br /> <span data-ttu-id="dffab-116">Il secondo passaggio consiste nell'aggiornare la tabella esistente di metadati in modo che punti alla nuova posizione dei file.</span><span class="sxs-lookup"><span data-stu-id="dffab-116">The second step is to update the existing table of metadata to point to the new location of the files.</span></span><br /><br /> <span data-ttu-id="dffab-117">Per ulteriori informazioni, vedere [Esempio: Migrazione di file dal file system in una tabella FileTable](#HowToMigrateFiles) in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="dffab-117">For more information, see [Example: Migrating Files from the File System into a FileTable](#HowToMigrateFiles) in this topic.</span></span>|  
  
###  <a name="how-to-load-files-into-a-filetable"></a><a name="HowToLoadNew"></a> <span data-ttu-id="dffab-118">Procedura: Caricare file in una tabella FileTable</span><span class="sxs-lookup"><span data-stu-id="dffab-118">How To: Load Files into a FileTable</span></span>  
 <span data-ttu-id="dffab-119">Tra i metodi che è possibile utilizzare per caricare file in una tabella FileTable sono inclusi i seguenti:</span><span class="sxs-lookup"><span data-stu-id="dffab-119">The methods that you can use to load files into a FileTable include the following:</span></span>  
  
-   <span data-ttu-id="dffab-120">Trascinare e rilasciare file dalle cartelle di origine alla nuova cartella FileTable in Esplora risorse.</span><span class="sxs-lookup"><span data-stu-id="dffab-120">Drag and drop files from the source folders to the new FileTable folder in Windows Explorer.</span></span>  
  
-   <span data-ttu-id="dffab-121">Utilizzare opzioni della riga di comando quali MOVE, COPY, XCOPY o ROBOCOPY dal prompt dei comandi o in un file batch o uno script.</span><span class="sxs-lookup"><span data-stu-id="dffab-121">Use command line options such as MOVE, COPY, XCOPY, or ROBOCOPY from the command prompt or in a batch file or script.</span></span>  
  
-   <span data-ttu-id="dffab-122">Scrivere un'applicazione personalizzata in C# o Visual Basic.NET che utilizzi metodi dello spazio dei nomi **System.IO** per spostare o copiare i file.</span><span class="sxs-lookup"><span data-stu-id="dffab-122">Write a custom application in C# or Visual Basic.NET that uses methods from the **System.IO** namespace to move or copy the files.</span></span>  
  
###  <a name="example-migrating-files-from-the-file-system-into-a-filetable"></a><a name="HowToMigrateFiles"></a> <span data-ttu-id="dffab-123">Esempio: Migrazione di file dal file system in una tabella FileTable</span><span class="sxs-lookup"><span data-stu-id="dffab-123">Example: Migrating Files from the File System into a FileTable</span></span>  
 <span data-ttu-id="dffab-124">In questo scenario i file vengono archiviati nel file system ed è disponibile una tabella di metadati in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] contenente puntatori ai file.</span><span class="sxs-lookup"><span data-stu-id="dffab-124">In this scenario, your files are stored in the file system, and you have a table of metadata in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that contains pointers to the files.</span></span> <span data-ttu-id="dffab-125">Si desidera spostare i file in una tabella FileTable, quindi sostituire il percorso UNC originale per ogni file nei metadati con il percorso UNC della tabella FileTable.</span><span class="sxs-lookup"><span data-stu-id="dffab-125">You want to move the files into a FileTable, and then replace the original UNC path for each file in the metadata with the FileTable UNC path.</span></span> <span data-ttu-id="dffab-126">La funzione [GetPathLocator &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/getpathlocator-transact-sql) consente di raggiungere tale obiettivo.</span><span class="sxs-lookup"><span data-stu-id="dffab-126">The [GetPathLocator &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/getpathlocator-transact-sql) function helps you to achieve this goal.</span></span>  
  
 <span data-ttu-id="dffab-127">Per questo esempio, si supponga di disporre di una tabella di database esistente, `PhotoMetadata` , che contiene dati sulle fotografie.</span><span class="sxs-lookup"><span data-stu-id="dffab-127">For this example, assume that there is an existing database table, `PhotoMetadata`, which contains data about photographs.</span></span> <span data-ttu-id="dffab-128">Questa tabella contiene una colonna `UNCPath` di tipo `varchar`(512) contenente il percorso UNC effettivo di un file con estensione jpg.</span><span class="sxs-lookup"><span data-stu-id="dffab-128">This table has a column `UNCPath` of type `varchar`(512) which contains the actual UNC path to a .jpg file.</span></span>  
  
 <span data-ttu-id="dffab-129">Per eseguire la migrazione dei file di immagine dal file system in una tabella FileTable, è necessario effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="dffab-129">To migrate the image files from the file system into a FileTable, you have to do the following:</span></span>  
  
1.  <span data-ttu-id="dffab-130">Creare una nuova tabella FileTable che contenga i file.</span><span class="sxs-lookup"><span data-stu-id="dffab-130">Create a new FileTable to hold the files.</span></span> <span data-ttu-id="dffab-131">In questo esempio si usa il nome di tabella `dbo.PhotoTable` ma non viene illustrato il codice per creare la tabella.</span><span class="sxs-lookup"><span data-stu-id="dffab-131">This example uses the table name, `dbo.PhotoTable`, but does not show the code to create the table.</span></span>  
  
2.  <span data-ttu-id="dffab-132">Utilizzare xcopy o uno strumento simile per copiare i file JPG, con la relativa struttura di directory, nella directory radice della tabella FileTable.</span><span class="sxs-lookup"><span data-stu-id="dffab-132">Use xcopy or a similar tool to copy the .jpg files, with their directory structure, into the root directory of the FileTable.</span></span>  
  
3.  <span data-ttu-id="dffab-133">Correggere i metadati nella tabella `PhotoMetadata` tramite codice simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="dffab-133">Fix the metadata in the `PhotoMetadata` table, by using code similar to the following:</span></span>  
  
```sql  
--  Add a path locator column to the PhotoMetadata table.  
ALTER TABLE PhotoMetadata ADD pathlocator hierarchyid;  
  
-- Get the root path of the Photo directory on the File Server.  
DECLARE @UNCPathRoot varchar(100) = '\\RemoteShare\Photographs';  
  
-- Get the root path of the FileTable.  
DECLARE @FileTableRoot varchar(1000);  
SELECT @FileTableRoot = FileTableRootPath('dbo.PhotoTable');  
  
-- Update the PhotoMetadata table.  
  
-- Replace the File Server UNC path with the FileTable path.  
UPDATE PhotoMetadata  
    SET UNCPath = REPLACE(UNCPath, @UNCPathRoot, @FileTableRoot);  
  
-- Update the pathlocator column to contain the pathlocator IDs from the FileTable.  
UPDATE PhotoMetadata  
    SET pathlocator = GetPathLocator(UNCPath);  
```  
  
##  <a name="bulk-loading-files-into-a-filetable"></a><a name="BasicsBulkLoad"></a> <span data-ttu-id="dffab-134">Caricamento bulk di file in una tabella FileTable</span><span class="sxs-lookup"><span data-stu-id="dffab-134">Bulk Loading Files into a FileTable</span></span>  
 <span data-ttu-id="dffab-135">Una tabella FileTable si comporta come una normale tabella per operazioni bulk, con le caratteristiche seguenti.</span><span class="sxs-lookup"><span data-stu-id="dffab-135">A FileTable behaves like a normal table for bulk operations, with the following qualifications.</span></span>  
  
 <span data-ttu-id="dffab-136">Una tabella FileTable include vincoli definiti dal sistema che garantiscono l'integrità dello spazio dei nomi di file/directory.</span><span class="sxs-lookup"><span data-stu-id="dffab-136">A FileTable has system-defined constraints which ensure that the integrity of the file and directory namespace is maintained.</span></span> <span data-ttu-id="dffab-137">È necessario verificare questi vincoli per i dati caricati in bulk nella tabella FileTable.</span><span class="sxs-lookup"><span data-stu-id="dffab-137">These constraints have to be verified on the data bulk loaded into the FileTable.</span></span> <span data-ttu-id="dffab-138">Poiché alcune operazioni di inserimento bulk consentono di ignorare i vincoli di tabella, si applicano i requisiti seguenti.</span><span class="sxs-lookup"><span data-stu-id="dffab-138">Since some bulk insert operations allow table constraints to be ignored, the following requirements are enforced.</span></span>  
  
-   <span data-ttu-id="dffab-139">Le operazioni di caricamento bulk che impongono vincoli possono essere eseguite su una tabella FileTable esattamente come su qualsiasi altra tabella.</span><span class="sxs-lookup"><span data-stu-id="dffab-139">Bulk loading operations that enforce constraints can be run against a FileTable as against any other table.</span></span> <span data-ttu-id="dffab-140">Questa categoria include le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="dffab-140">This category includes the following operations:</span></span>  
  
    -   <span data-ttu-id="dffab-141">bcp con clausola CHECK_CONSTRAINTS.</span><span class="sxs-lookup"><span data-stu-id="dffab-141">bcp with CHECK_CONSTRAINTS clause.</span></span>  
  
    -   <span data-ttu-id="dffab-142">BULK INSERT con clausola CHECK_CONSTRAINTS.</span><span class="sxs-lookup"><span data-stu-id="dffab-142">BULK INSERT with CHECK_CONSTRAINTS clause.</span></span>  
  
    -   <span data-ttu-id="dffab-143">INSERT INTO ... SELECT \* FROM OPENROWSET(BULK ...) senza la clausola IGNORE_CONSTRAINTS.</span><span class="sxs-lookup"><span data-stu-id="dffab-143">INSERT INTO ... SELECT \* FROM OPENROWSET(BULK ...) without IGNORE_CONSTRAINTS clause.</span></span>  
  
-   <span data-ttu-id="dffab-144">Le operazioni di caricamento bulk che non applicano vincoli hanno esito negativo a meno i vincoli definiti dal sistema della tabella FileTable non siano stati disabilitati.</span><span class="sxs-lookup"><span data-stu-id="dffab-144">Bulk loading operations that do not enforce constraints fail unless the FileTable system-defined constraints have been disabled.</span></span> <span data-ttu-id="dffab-145">Questa categoria include le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="dffab-145">This category includes the following operations:</span></span>  
  
    -   <span data-ttu-id="dffab-146">bcp senza clausola CHECK_CONSTRAINTS.</span><span class="sxs-lookup"><span data-stu-id="dffab-146">bcp without CHECK_CONSTRAINTS clause.</span></span>  
  
    -   <span data-ttu-id="dffab-147">BULK INSERT senza clausola CHECK_CONSTRAINTS.</span><span class="sxs-lookup"><span data-stu-id="dffab-147">BULK INSERT without CHECK_CONSTRAINTS clause.</span></span>  
  
    -   <span data-ttu-id="dffab-148">INSERT INTO ... SELECT \* FROM OPENROWSET(BULK ...) con la clausola IGNORE_CONSTRAINTS.</span><span class="sxs-lookup"><span data-stu-id="dffab-148">INSERT INTO ... SELECT \* FROM OPENROWSET(BULK ...) with IGNORE_CONSTRAINTS clause.</span></span>  
  
###  <a name="how-to-bulk-load-files-into-a-filetable"></a><a name="HowToBulkLoad"></a> <span data-ttu-id="dffab-149">Procedura: Eseguire il caricamento bulk di file in una tabella FileTable</span><span class="sxs-lookup"><span data-stu-id="dffab-149">How To: Bulk Load Files into a FileTable</span></span>  
 <span data-ttu-id="dffab-150">È possibile utilizzare diversi metodi per eseguire il caricamento bulk di file in una tabella FileTable:</span><span class="sxs-lookup"><span data-stu-id="dffab-150">You can use various methods to bulk load files into a FileTable:</span></span>  
  
-   <span data-ttu-id="dffab-151">**bcp**</span><span class="sxs-lookup"><span data-stu-id="dffab-151">**bcp**</span></span>  
  
    -   <span data-ttu-id="dffab-152">Eseguire una chiamata con la clausola **CHECK_CONSTRAINTS** .</span><span class="sxs-lookup"><span data-stu-id="dffab-152">Call with the **CHECK_CONSTRAINTS** clause.</span></span>  
  
    -   <span data-ttu-id="dffab-153">Disabilitare lo spazio dei nomi FileTable ed eseguire una chiamata senza la clausola **CHECK_CONSTRAINTS** .</span><span class="sxs-lookup"><span data-stu-id="dffab-153">Disable the FileTable namespace and call without the **CHECK_CONSTRAINTS** clause.</span></span> <span data-ttu-id="dffab-154">Riabilitare quindi lo spazio dei nomi FileTable.</span><span class="sxs-lookup"><span data-stu-id="dffab-154">Then re-enable the FileTable namespace.</span></span>  
  
-   <span data-ttu-id="dffab-155">**BULK INSERT**</span><span class="sxs-lookup"><span data-stu-id="dffab-155">**BULK INSERT**</span></span>  
  
    -   <span data-ttu-id="dffab-156">Eseguire una chiamata con la clausola **CHECK_CONSTRAINTS** .</span><span class="sxs-lookup"><span data-stu-id="dffab-156">Call with the **CHECK_CONSTRAINTS** clause.</span></span>  
  
    -   <span data-ttu-id="dffab-157">Disabilitare lo spazio dei nomi FileTable ed eseguire una chiamata senza la clausola **CHECK_CONSTRAINTS** .</span><span class="sxs-lookup"><span data-stu-id="dffab-157">Disable the FileTable namespace and call without the **CHECK_CONSTRAINTS** clause.</span></span> <span data-ttu-id="dffab-158">Riabilitare quindi lo spazio dei nomi FileTable.</span><span class="sxs-lookup"><span data-stu-id="dffab-158">Then re-enable the FileTable namespace.</span></span>  
  
-   <span data-ttu-id="dffab-159">**INSERT INTO ... SELECT \* FROM OPENROWSET(BULK ...)**</span><span class="sxs-lookup"><span data-stu-id="dffab-159">**INSERT INTO ... SELECT \* FROM OPENROWSET(BULK ...)**</span></span>  
  
    -   <span data-ttu-id="dffab-160">Eseguire una chiamata con la clausola **IGNORE_CONSTRAINTS** .</span><span class="sxs-lookup"><span data-stu-id="dffab-160">Call with the **IGNORE_CONSTRAINTS** clause.</span></span>  
  
    -   <span data-ttu-id="dffab-161">Disabilitare lo spazio dei nomi FileTable ed eseguire una chiamata senza la clausola **IGNORE_CONSTRAINTS** .</span><span class="sxs-lookup"><span data-stu-id="dffab-161">Disable the FileTable namespace and call without the **IGNORE_CONSTRAINTS** clause.</span></span> <span data-ttu-id="dffab-162">Riabilitare quindi lo spazio dei nomi FileTable.</span><span class="sxs-lookup"><span data-stu-id="dffab-162">Then re-enable the FileTable namespace.</span></span>  
  
 <span data-ttu-id="dffab-163">Per informazioni su come disabilitare i vincoli FileTable, vedere [Gestire le tabelle FileTable](manage-filetables.md).</span><span class="sxs-lookup"><span data-stu-id="dffab-163">For information about disabling the FileTable constraints, see [Manage FileTables](manage-filetables.md).</span></span>  
  
###  <a name="how-to-disable-filetable-constraints-for-bulk-loading"></a><a name="disabling"></a> <span data-ttu-id="dffab-164">Procedura: Disabilitare vincoli FileTable per eseguire il caricamento bulk</span><span class="sxs-lookup"><span data-stu-id="dffab-164">How To: Disable FileTable Constraints for Bulk Loading</span></span>  
 <span data-ttu-id="dffab-165">Per eseguire il caricamento bulk di file in una tabella FileTable senza la necessità di applicare vincoli definiti dal sistema, è possibile disabilitare temporaneamente i vincoli.</span><span class="sxs-lookup"><span data-stu-id="dffab-165">To bulk load files into a FileTable without the overhead of enforcing the system-defined constraints, you can temporarily disable the constraints.</span></span> <span data-ttu-id="dffab-166">Per altre informazioni, vedere [Gestire le tabelle FileTable](manage-filetables.md).</span><span class="sxs-lookup"><span data-stu-id="dffab-166">For more information, see [Manage FileTables](manage-filetables.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dffab-167">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dffab-167">See Also</span></span>  
 <span data-ttu-id="dffab-168">[Accesso a tabelle FileTable tramite Transact-SQL](access-filetables-with-transact-sql.md) </span><span class="sxs-lookup"><span data-stu-id="dffab-168">[Access FileTables with Transact-SQL](access-filetables-with-transact-sql.md) </span></span>  
 [<span data-ttu-id="dffab-169">Accedere alle tabelle FileTable con API di input/output dei file</span><span class="sxs-lookup"><span data-stu-id="dffab-169">Access FileTables with File Input-Output APIs</span></span>](access-filetables-with-file-input-output-apis.md)  
  
  
