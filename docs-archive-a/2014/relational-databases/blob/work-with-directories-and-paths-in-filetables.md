---
title: Usare directory e percorsi in FileTable | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: filestream
ms.topic: conceptual
helpviewer_keywords:
- FileTables [SQL Server], directories
ms.assetid: f1e45900-bea0-4f6f-924e-c11e1f98ab62
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 4641159e894b764cbee4d7f02085f3ceb8e6d87d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712031"
---
# <a name="work-with-directories-and-paths-in-filetables"></a><span data-ttu-id="fb529-102">Utilizzare directory e percorsi in FileTable</span><span class="sxs-lookup"><span data-stu-id="fb529-102">Work with Directories and Paths in FileTables</span></span>
  <span data-ttu-id="fb529-103">Descrive la struttura di directory nella quale vengono archiviati i file in FileTable.</span><span class="sxs-lookup"><span data-stu-id="fb529-103">Describes the directory structure in which the files are stored in FileTables.</span></span>  
  
##  <a name="how-to-work-with-directories-and-paths-in-filetables"></a><a name="HowToDirectories"></a> <span data-ttu-id="fb529-104">Procedura: Utilizzare directory e percorsi in FileTable</span><span class="sxs-lookup"><span data-stu-id="fb529-104">How To: Work with Directories and Paths in FileTables</span></span>  
 <span data-ttu-id="fb529-105">Sono disponibili 3 funzioni che consentono di utilizzare le directory FileTable in [!INCLUDE[tsql](../../includes/tsql-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="fb529-105">You can use the following 3 functions to work with FileTable directories in [!INCLUDE[tsql](../../includes/tsql-md.md)]:</span></span>  
  
|<span data-ttu-id="fb529-106">Per ottenere questo risultato</span><span class="sxs-lookup"><span data-stu-id="fb529-106">To get this result</span></span>|<span data-ttu-id="fb529-107">Utilizzare questa funzione</span><span class="sxs-lookup"><span data-stu-id="fb529-107">Use this function</span></span>|  
|------------------------|-----------------------|  
|<span data-ttu-id="fb529-108">Ottenere il percorso UNC del livello radice di una specifica tabella FileTable o del database corrente.</span><span class="sxs-lookup"><span data-stu-id="fb529-108">Get the root-level UNC path for a specific FileTable or for the current database.</span></span>|[<span data-ttu-id="fb529-109">FileTableRootPath &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="fb529-109">FileTableRootPath &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-functions/filetablerootpath-transact-sql)|  
|<span data-ttu-id="fb529-110">Ottenere un percorso UNC assoluto o relativo di un file o una directory in una tabella FileTable.</span><span class="sxs-lookup"><span data-stu-id="fb529-110">Get an absolute or relative UNC path for a file or directory in a FileTable.</span></span>|[<span data-ttu-id="fb529-111">GetFileNamespacePath &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="fb529-111">GetFileNamespacePath &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-functions/getfilenamespacepath-transact-sql)|  
|<span data-ttu-id="fb529-112">Ottenere il valore dell'ID di posizione del percorso di una directory o di un file specificato in una tabella FileTable, indicandone il percorso.</span><span class="sxs-lookup"><span data-stu-id="fb529-112">Get the path locator ID value for the specified file or directory in a FileTable, by providing the path.</span></span>|[<span data-ttu-id="fb529-113">GetPathLocator &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="fb529-113">GetPathLocator &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-functions/getpathlocator-transact-sql)|  
  
##  <a name="how-to-use-relative-paths-for-portable-code"></a><a name="BestPracticeRelativePaths"></a> <span data-ttu-id="fb529-114">Procedura: Usare percorsi relativi per il codice portabile</span><span class="sxs-lookup"><span data-stu-id="fb529-114">How to: Use Relative Paths for Portable Code</span></span>  
 <span data-ttu-id="fb529-115">Per mantenere il codice e le applicazioni indipendenti dal database e dal computer correnti, evitare di scrivere codice basato su percorsi di file assoluti.</span><span class="sxs-lookup"><span data-stu-id="fb529-115">To keep code and applications independent of the current computer and database, avoid writing code that relies on absolute file paths.</span></span> <span data-ttu-id="fb529-116">Ottenere invece il percorso completo di un file al runtime mediante l'uso combinato delle funzioni [FileTableRootPath &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/filetablerootpath-transact-sql) e [GetFileNamespacePath &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/getfilenamespacepath-transact-sql), come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="fb529-116">Instead, get the complete path for a file at run time by using the [FileTableRootPath &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/filetablerootpath-transact-sql) and [GetFileNamespacePath &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/getfilenamespacepath-transact-sql)) functions together, as shown in the following example.</span></span> <span data-ttu-id="fb529-117">Per impostazione predefinita, la funzione `GetFileNamespacePath` restituisce il percorso relativo del file all'interno del percorso radice per il database.</span><span class="sxs-lookup"><span data-stu-id="fb529-117">By default, the `GetFileNamespacePath` function returns the relative path of the file under the root path for the database.</span></span>  
  
```sql  
USE database_name;  
DECLARE @root nvarchar(100);  
DECLARE @fullpath nvarchar(1000);  
  
SELECT @root = FileTableRootPath();  
SELECT @fullpath = @root + file_stream.GetFileNamespacePath()  
    FROM filetable_name  
    WHERE name = N'document_name';  
  
PRINT @fullpath;  
GO  
```  
  
##  <a name="important-restrictions"></a><a name="restrictions"></a> <span data-ttu-id="fb529-118">Restrizioni importanti</span><span class="sxs-lookup"><span data-stu-id="fb529-118">Important restrictions</span></span>  
  
###  <a name="nesting-level"></a><a name="nesting"></a> <span data-ttu-id="fb529-119">Livello di nidificazione</span><span class="sxs-lookup"><span data-stu-id="fb529-119">Nesting level</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="fb529-120">Non è possibile archiviare più di 15 livelli di sottodirectory nella directory FileTable.</span><span class="sxs-lookup"><span data-stu-id="fb529-120">You cannot store more than 15 levels of subdirectories in the FileTable directory.</span></span> <span data-ttu-id="fb529-121">Quando si archiviano 15 livelli di sottodirectory, il livello più basso non può contenere file, poiché essi rappresenterebbero un ulteriore livello.</span><span class="sxs-lookup"><span data-stu-id="fb529-121">When you store 15 levels of subdirectories, then the lowest level cannot contain files, since these files would represent an additional level.</span></span>  
  
###  <a name="length-of-full-path-name"></a><a name="fqnlength"></a> <span data-ttu-id="fb529-122">Lunghezza del nome e percorso completo</span><span class="sxs-lookup"><span data-stu-id="fb529-122">Length of full path name</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="fb529-123">Il file system NTFS supporta nomi di percorso la cui lunghezza supera il limite di 260 caratteri della shell di Windows e della maggior parte delle API Windows.</span><span class="sxs-lookup"><span data-stu-id="fb529-123">The NTFS file system supports path names that are much longer than the 260-character limit of the Windows shell and most Windows APIs.</span></span> <span data-ttu-id="fb529-124">Pertanto, utilizzando Transact-SQL, è possibile creare file nella gerarchia dei file di una tabella FileTable che non è possibile visualizzare o aprire con Esplora risorse o con molte altre applicazioni Windows, perché il nome e percorso completo superano i 260 caratteri.</span><span class="sxs-lookup"><span data-stu-id="fb529-124">Therefore it is possible to create files in the file hierarchy of a FileTable by using Transact-SQL that you cannot view or open with Windows Explorer or many other Windows applications, because the full path name exceeds 260 characters.</span></span> <span data-ttu-id="fb529-125">Tuttavia, è possibile continuare ad accedere a questi file tramite Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="fb529-125">However you can continue to access these files by using Transact-SQL.</span></span>  
  
##  <a name="the-full-path-to-an-item-stored-in-a-filetable"></a><a name="fullpath"></a> <span data-ttu-id="fb529-126">Percorso completo di un elemento archiviato in una tabella FileTable</span><span class="sxs-lookup"><span data-stu-id="fb529-126">The full path to an item stored in a FileTable</span></span>  
 <span data-ttu-id="fb529-127">Il percorso completo di un file o di una directory in una tabella FileTable inizia con gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="fb529-127">The full path to a file or directory stored in a FileTable begins with the following elements:</span></span>  
  
1.  <span data-ttu-id="fb529-128">Condivisione abilitata per l'accesso di I/O ai file FILESTREAM a livello dell'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fb529-128">The share enabled for FILESTREAM file I/O access at the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance level.</span></span>  
  
2.  <span data-ttu-id="fb529-129">**DIRECTORY_NAME** specificato a livello di database.</span><span class="sxs-lookup"><span data-stu-id="fb529-129">The **DIRECTORY_NAME** specified at the database level.</span></span>  
  
3.  <span data-ttu-id="fb529-130">**FILETABLE_DIRECTORY** specificato a livello di FileTable.</span><span class="sxs-lookup"><span data-stu-id="fb529-130">The **FILETABLE_DIRECTORY** specified at the FileTable level.</span></span>  
  
 <span data-ttu-id="fb529-131">La gerarchia risultante risulta analoga alla seguente:</span><span class="sxs-lookup"><span data-stu-id="fb529-131">The resulting hierarchy looks like this:</span></span>  
  
 `\\<machine>\<instance-level FILESTREAM share>\<database-level directory>\<FileTable directory>\`  
  
 <span data-ttu-id="fb529-132">Questa gerarchia di directory costituisce la radice di uno spazio dei nomi dei file di FileTable.</span><span class="sxs-lookup"><span data-stu-id="fb529-132">This directory hierarchy forms the root of the FileTable's file namespace.</span></span> <span data-ttu-id="fb529-133">In questa gerarchia di directory, i dati FILESTREAM per la tabella FileTable vengono archiviati come file e come sottodirectory che possono a loro volta contenere file e sottodirectory.</span><span class="sxs-lookup"><span data-stu-id="fb529-133">Under this directory hierarchy, the FILESTREAM data for the FileTable is stored as files, and as subdirectories which can also contain files and subdirectories.</span></span>  
  
 <span data-ttu-id="fb529-134">È importante ricordare che la gerarchia di directory creata nella condivisione FILESTREAM a livello di istanza è una gerarchia di directory virtuale.</span><span class="sxs-lookup"><span data-stu-id="fb529-134">It is important to keep in mind that the directory hierarchy created under the instance-level FILESTREAM share is a virtual directory hierarchy.</span></span> <span data-ttu-id="fb529-135">Questa gerarchia viene archiviata nel database di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e non è rappresentata fisicamente nel file system NTFS.</span><span class="sxs-lookup"><span data-stu-id="fb529-135">This hierarchy is stored in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database and is not represented physically in the NTFS file system.</span></span> <span data-ttu-id="fb529-136">Tutte le operazioni che comportano l'accesso a file e directory nella condivisione FILESTREAM e nelle tabelle FileTable in essa contenute sono intercettate e gestite da un componente di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] incorporato nel file system.</span><span class="sxs-lookup"><span data-stu-id="fb529-136">All operations that access files and directories under the FILESTREAM share and in the FileTables that it contains are intercepted and handled by a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] component embedded in the file system.</span></span>  
  
##  <a name="the-semantics-of-the-root-directories-at-the-instance-database-and-filetable-levels"></a><a name="roots"></a> <span data-ttu-id="fb529-137">Semantica delle directory radice a livello di istanza, database e tabella FileTable</span><span class="sxs-lookup"><span data-stu-id="fb529-137">The semantics of the root directories at the instance, database, and FileTable levels</span></span>  
 <span data-ttu-id="fb529-138">Questa gerarchia di directory osserva la semantica seguente:</span><span class="sxs-lookup"><span data-stu-id="fb529-138">This directory hierarchy observes the following semantics:</span></span>  
  
-   <span data-ttu-id="fb529-139">La condivisione FILESTREAM del livello di istanza viene configurata da un amministratore e archiviata come proprietà del server.</span><span class="sxs-lookup"><span data-stu-id="fb529-139">The instance-level FILESTREAM share is configured by an administrator and stored as a property of the server.</span></span> <span data-ttu-id="fb529-140">È possibile rinominare la condivisione mediante Gestione configurazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fb529-140">You can rename this share by using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span> <span data-ttu-id="fb529-141">L'operazione di ridenominazione non viene applicata finché il server non viene riavviato.</span><span class="sxs-lookup"><span data-stu-id="fb529-141">A renaming operation does not take effect until the server is restarted.</span></span>  
  
-   <span data-ttu-id="fb529-142">Per impostazione predefinita, l'elemento **DIRECTORY_NAME** a livello di database è null quando si crea un nuovo database.</span><span class="sxs-lookup"><span data-stu-id="fb529-142">The database-level **DIRECTORY_NAME** is null by default when you create a new database.</span></span> <span data-ttu-id="fb529-143">Un amministratore può impostare o modificare il nome mediante l'istruzione **ALTER DATABASE** .</span><span class="sxs-lookup"><span data-stu-id="fb529-143">An administrator can set or change this name by using the **ALTER DATABASE** statement.</span></span> <span data-ttu-id="fb529-144">Il nome deve essere univoco (in un confronto senza distinzione fra maiuscole e minuscole) nell'istanza in questione.</span><span class="sxs-lookup"><span data-stu-id="fb529-144">The name must be unique (in a case-insensitive comparison) in that instance.</span></span>  
  
-   <span data-ttu-id="fb529-145">In genere, il nome **FILETABLE_DIRECTORY** viene specificato con l'istruzione **CREATE TABLE** al momento di creare una tabella FileTable.</span><span class="sxs-lookup"><span data-stu-id="fb529-145">You typically provide the **FILETABLE_DIRECTORY** name as part of the **CREATE TABLE** statement when you create a FileTable.</span></span> <span data-ttu-id="fb529-146">È possibile modificare questo nome mediante il comando **ALTER TABLE** .</span><span class="sxs-lookup"><span data-stu-id="fb529-146">You can change this name by using the **ALTER TABLE** command.</span></span>  
  
-   <span data-ttu-id="fb529-147">Non è possibile rinominare queste directory radice tramite operazioni di I/O su file.</span><span class="sxs-lookup"><span data-stu-id="fb529-147">You cannot rename these root directories through file I/O operations.</span></span>  
  
-   <span data-ttu-id="fb529-148">Non è possibile aprire queste directory radice con handle di file esclusivi.</span><span class="sxs-lookup"><span data-stu-id="fb529-148">You cannot open these root directories with exclusive file handles.</span></span>  
  
##  <a name="the-is_directory-column-in-the-filetable-schema"></a><a name="is_directory"></a> <span data-ttu-id="fb529-149">Colonna is_directory nello schema della tabella FileTable</span><span class="sxs-lookup"><span data-stu-id="fb529-149">The is_directory column in the FileTable schema</span></span>  
 <span data-ttu-id="fb529-150">La tabella seguente descrive l'interazione tra la colonna **is_directory** e la colonna **file_stream** contenente i dati FILESTREAM in una tabella FileTable.</span><span class="sxs-lookup"><span data-stu-id="fb529-150">The following table describes the interaction between the **is_directory** column and the **file_stream** column that contains the FILESTREAM data in a FileTable.</span></span>  
  
||||  
|-|-|-|  
|<span data-ttu-id="fb529-151">*is_directory* **value**</span><span class="sxs-lookup"><span data-stu-id="fb529-151">*is_directory* **value**</span></span>|<span data-ttu-id="fb529-152">*file_stream* **value**</span><span class="sxs-lookup"><span data-stu-id="fb529-152">*file_stream* **value**</span></span>|<span data-ttu-id="fb529-153">**Comportamento**</span><span class="sxs-lookup"><span data-stu-id="fb529-153">**Behavior**</span></span>|  
|<span data-ttu-id="fb529-154">FALSE</span><span class="sxs-lookup"><span data-stu-id="fb529-154">FALSE</span></span>|<span data-ttu-id="fb529-155">NULL</span><span class="sxs-lookup"><span data-stu-id="fb529-155">NULL</span></span>|<span data-ttu-id="fb529-156">Si tratta di una combinazione non valida che sarà intercettata da un vincolo definito dal sistema.</span><span class="sxs-lookup"><span data-stu-id="fb529-156">This is an invalid combination that will be caught by a system-defined constraint.</span></span>|  
|<span data-ttu-id="fb529-157">FALSE</span><span class="sxs-lookup"><span data-stu-id="fb529-157">FALSE</span></span>|\<value>|<span data-ttu-id="fb529-158">L'elemento rappresenta un file.</span><span class="sxs-lookup"><span data-stu-id="fb529-158">The item represents a file.</span></span>|  
|<span data-ttu-id="fb529-159">TRUE</span><span class="sxs-lookup"><span data-stu-id="fb529-159">TRUE</span></span>|<span data-ttu-id="fb529-160">NULL</span><span class="sxs-lookup"><span data-stu-id="fb529-160">NULL</span></span>|<span data-ttu-id="fb529-161">L'elemento rappresenta una directory.</span><span class="sxs-lookup"><span data-stu-id="fb529-161">The item represents a directory.</span></span>|  
|<span data-ttu-id="fb529-162">TRUE</span><span class="sxs-lookup"><span data-stu-id="fb529-162">TRUE</span></span>|\<value>|<span data-ttu-id="fb529-163">Si tratta di una combinazione non valida che sarà intercettata da un vincolo definito dal sistema.</span><span class="sxs-lookup"><span data-stu-id="fb529-163">This is an invalid combination that will be caught by a system-defined constraint.</span></span>|  
  
##  <a name="using-virtual-network-names-vnns-with-alwayson-availability-groups"></a><a name="alwayson"></a> <span data-ttu-id="fb529-164">Utilizzo di nomi di rete virtuale con i gruppi di disponibilità AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="fb529-164">Using Virtual Network Names (VNNs) with AlwaysOn Availability Groups</span></span>  
 <span data-ttu-id="fb529-165">Quando il database che contiene dati FILESTREAM o FileTable appartiene a un gruppo di disponibilità AlwaysOn:</span><span class="sxs-lookup"><span data-stu-id="fb529-165">When the database that contains FILESTREAM or FileTable data belongs to an AlwaysOn availability group:</span></span>  
  
-   <span data-ttu-id="fb529-166">Le funzioni FILESTREAM e FileTable accettano o restituiscono nomi di rete virtuale anziché nomi computer.</span><span class="sxs-lookup"><span data-stu-id="fb529-166">The FILESTREAM and FileTable functions accept or return virtual network names (VNNs) instead of computer names.</span></span> <span data-ttu-id="fb529-167">Per altre informazioni su queste funzioni, vedere [Funzioni FileStream e FileTable &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/filestream-and-filetable-functions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="fb529-167">For more information about these functions, see [Filestream and FileTable Functions &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/filestream-and-filetable-functions-transact-sql).</span></span>  
  
-   <span data-ttu-id="fb529-168">Ogni accesso a dati FILESTREAM o FileTable tramite le API del file system deve utilizzare VNN anziché nomi computer.</span><span class="sxs-lookup"><span data-stu-id="fb529-168">All access to FILESTREAM or FileTable data through the file system APIs should use VNNs instead of computer names.</span></span> <span data-ttu-id="fb529-169">Per altre informazioni, vedere [FILESTREAM e FileTable con i gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;](../../database-engine/availability-groups/windows/filestream-and-filetable-with-always-on-availability-groups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="fb529-169">For more information, see [FILESTREAM and FileTable with AlwaysOn Availability Groups &#40;SQL Server&#41;](../../database-engine/availability-groups/windows/filestream-and-filetable-with-always-on-availability-groups-sql-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb529-170">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fb529-170">See Also</span></span>  
 <span data-ttu-id="fb529-171">[Abilitazione dei prerequisiti per la tabella FileTable](enable-the-prerequisites-for-filetable.md) </span><span class="sxs-lookup"><span data-stu-id="fb529-171">[Enable the Prerequisites for FileTable](enable-the-prerequisites-for-filetable.md) </span></span>  
 <span data-ttu-id="fb529-172">[Creare, modificare e rilasciare FileTables](create-alter-and-drop-filetables.md) </span><span class="sxs-lookup"><span data-stu-id="fb529-172">[Create, Alter, and Drop FileTables](create-alter-and-drop-filetables.md) </span></span>  
 <span data-ttu-id="fb529-173">[Accesso a tabelle FileTable tramite Transact-SQL](access-filetables-with-transact-sql.md) </span><span class="sxs-lookup"><span data-stu-id="fb529-173">[Access FileTables with Transact-SQL](access-filetables-with-transact-sql.md) </span></span>  
 [<span data-ttu-id="fb529-174">Accedere alle tabelle FileTable con API di input/output dei file</span><span class="sxs-lookup"><span data-stu-id="fb529-174">Access FileTables with File Input-Output APIs</span></span>](access-filetables-with-file-input-output-apis.md)  
  
  
