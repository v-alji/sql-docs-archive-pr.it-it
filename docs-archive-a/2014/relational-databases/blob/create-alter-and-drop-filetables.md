---
title: Creare, modificare ed eliminare FileTable | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: filestream
ms.topic: conceptual
helpviewer_keywords:
- FileTables [SQL Server], altering
- FileTables [SQL Server], dropping
- FileTables [SQL Server], creating
ms.assetid: 47d69e37-8778-4630-809b-2261b5c41c2c
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 3a10e6333f6dd38a850a832b82a7cb7a0e0bf698
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624774"
---
# <a name="create-alter-and-drop-filetables"></a><span data-ttu-id="2435a-102">Creare, modificare e rilasciare FileTables</span><span class="sxs-lookup"><span data-stu-id="2435a-102">Create, Alter, and Drop FileTables</span></span>
  <span data-ttu-id="2435a-103">Viene descritto come creare una nuova tabella FileTable o modificarne o eliminarne una esistente.</span><span class="sxs-lookup"><span data-stu-id="2435a-103">Describes how to create a new FileTable, or alter or drop an existing FileTable.</span></span>  
  
##  <a name="creating-a-filetable"></a><a name="BasicsCreate"></a> <span data-ttu-id="2435a-104">Creazione di una tabella FileTable</span><span class="sxs-lookup"><span data-stu-id="2435a-104">Creating a FileTable</span></span>  
 <span data-ttu-id="2435a-105">Una tabella FileTable è una tabella utente specializzata con uno schema predefinito e fisso.</span><span class="sxs-lookup"><span data-stu-id="2435a-105">A FileTable is a specialized user table that has a pre-defined and fixed schema.</span></span> <span data-ttu-id="2435a-106">In questo schema sono archiviati dati FILESTREAM, informazioni su file e directory e attributi dei file.</span><span class="sxs-lookup"><span data-stu-id="2435a-106">This schema stores FILESTREAM data, file and directory information, and file attributes.</span></span> <span data-ttu-id="2435a-107">Per informazioni sullo schema FileTable, vedere [FileTable Schema](filetable-schema.md).</span><span class="sxs-lookup"><span data-stu-id="2435a-107">For information about the FileTable schema, see [FileTable Schema](filetable-schema.md).</span></span>  
  
 <span data-ttu-id="2435a-108">È possibile creare una nuova tabella FileTable tramite Transact-SQL o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2435a-108">You can create a new FileTable by using Transact-SQL or [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="2435a-109">Poiché una tabella FileTable ha uno schema fisso, non è necessario specificare un elenco di colonne.</span><span class="sxs-lookup"><span data-stu-id="2435a-109">Since a FileTable has a fixed schema, you do not have to specify a list of columns.</span></span> <span data-ttu-id="2435a-110">La sintassi semplice per la creazione di una tabella FileTable consente di specificare gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="2435a-110">The simple syntax for creating a FileTable lets you specify:</span></span>  
  
-   <span data-ttu-id="2435a-111">Nome di directory.</span><span class="sxs-lookup"><span data-stu-id="2435a-111">A directory name.</span></span> <span data-ttu-id="2435a-112">Nella gerarchia di cartelle FileTable questa directory a livello di tabella diventa il figlio della directory dei database specificata a livello di database e il padre delle directory o dei file archiviati nella tabella.</span><span class="sxs-lookup"><span data-stu-id="2435a-112">In the FileTable folder hierarchy, this table-level directory becomes the child of the database directory specified at the database level, and the parent of the files or directories stored in the table.</span></span>  
  
-   <span data-ttu-id="2435a-113">Nome delle regole di confronto da utilizzare per i nomi di file nella colonna **Name** della tabella FileTable.</span><span class="sxs-lookup"><span data-stu-id="2435a-113">The name of the collation to be used for file names in the **Name** column of the FileTable.</span></span>  
  
-   <span data-ttu-id="2435a-114">Nomi da utilizzare per i 3 vincoli di chiave primaria e univoci creati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="2435a-114">The names to be used for the 3 primary key and unique constraints that are automatically created.</span></span>  
  
###  <a name="how-to-create-a-filetable"></a><a name="HowToCreate"></a> <span data-ttu-id="2435a-115">Procedura: Creare una tabella FileTable</span><span class="sxs-lookup"><span data-stu-id="2435a-115">How To: Create a FileTable</span></span>  
 <span data-ttu-id="2435a-116">**Creare una tabella FileTable tramite Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="2435a-116">**Create a FileTable by Using Transact-SQL**</span></span>  
 <span data-ttu-id="2435a-117">Creare una tabella FileTable chiamando l'istruzione [CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql) con l'opzione **AS FileTable**.</span><span class="sxs-lookup"><span data-stu-id="2435a-117">Create a FileTable by calling the [CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql) statement with the **AS FileTable** option.</span></span> <span data-ttu-id="2435a-118">Poiché una tabella FileTable ha uno schema fisso, non è necessario specificare un elenco di colonne.</span><span class="sxs-lookup"><span data-stu-id="2435a-118">Since a FileTable has a fixed schema, you do not have to specify a list of columns.</span></span> <span data-ttu-id="2435a-119">È invece possibile specificare le impostazioni seguenti per la nuova tabella FileTable:</span><span class="sxs-lookup"><span data-stu-id="2435a-119">You can specify the following settings for the new FileTable:</span></span>  
  
1.  <span data-ttu-id="2435a-120">**FILETABLE_DIRECTORY**.</span><span class="sxs-lookup"><span data-stu-id="2435a-120">**FILETABLE_DIRECTORY**.</span></span> <span data-ttu-id="2435a-121">Specifica la directory che serve come directory radice per tutti i file e le directory archiviata in FileTable.</span><span class="sxs-lookup"><span data-stu-id="2435a-121">Specifies the directory that serves as the root directory for all the files and directories stored in the FileTable.</span></span> <span data-ttu-id="2435a-122">Questo nome deve essere univoco tra tutti i nomi di directory FileTable nel database.</span><span class="sxs-lookup"><span data-stu-id="2435a-122">This name should be unique among all the FileTable directory names in the database.</span></span> <span data-ttu-id="2435a-123">Nel confronto dell'univocità non viene applicata la distinzione tra maiuscole e minuscole, indipendentemente dalle impostazioni delle regole di confronto correnti.</span><span class="sxs-lookup"><span data-stu-id="2435a-123">Comparison for uniqueness is case-insensitive, regardless of the current collation settings.</span></span>  
  
    -   <span data-ttu-id="2435a-124">Questo valore è di tipo **nvarchar(255)** e usa regole di confronto fisse **Latin1_General_CI_AS_KS_WS**.</span><span class="sxs-lookup"><span data-stu-id="2435a-124">This value has a data type of **nvarchar(255)** and uses a fixed collation of **Latin1_General_CI_AS_KS_WS**.</span></span>  
  
    -   <span data-ttu-id="2435a-125">Il nome di directory specificato deve essere conforme ai requisiti del file system relativi ai nomi di directory validi.</span><span class="sxs-lookup"><span data-stu-id="2435a-125">The directory name that you provide must comply with the requirements of the file system for a valid directory name.</span></span>  
  
    -   <span data-ttu-id="2435a-126">Questo nome deve essere univoco tra tutti i nomi di directory FileTable nel database.</span><span class="sxs-lookup"><span data-stu-id="2435a-126">This name should be unique among all the FileTable directory names in the database.</span></span> <span data-ttu-id="2435a-127">Nel confronto dell'univocità non viene applicata la distinzione tra maiuscole e minuscole, indipendentemente dalle impostazioni delle regole di confronto correnti.</span><span class="sxs-lookup"><span data-stu-id="2435a-127">Comparison for uniqueness is case-insensitive, regardless of the current collation settings.</span></span>  
  
    -   <span data-ttu-id="2435a-128">Se non si fornisce un nome di directory quando si crea la tabella FileTable, allora il suo nome viene utilizzato come nome di directory.</span><span class="sxs-lookup"><span data-stu-id="2435a-128">If you do not provide a directory name when you create the FileTable, then the name of the FileTable itself is used as the directory name.</span></span>  
  
2.  <span data-ttu-id="2435a-129">**FILETABLE_COLLATE_FILENAME**.</span><span class="sxs-lookup"><span data-stu-id="2435a-129">**FILETABLE_COLLATE_FILENAME**.</span></span> <span data-ttu-id="2435a-130">Specifica il nome delle regole di confronto da applicare alla colonna **Name** della tabella FileTable.</span><span class="sxs-lookup"><span data-stu-id="2435a-130">Specifies the name of the collation to be applied to the **Name** column in the FileTable.</span></span>  
  
    1.  <span data-ttu-id="2435a-131">Nelle regole di confronto specificate deve essere fatta una **distinzione tra maiuscole e minuscole** affinché siano conformi alla semantica di denominazione file di Windows.</span><span class="sxs-lookup"><span data-stu-id="2435a-131">The specified collation must be **case-insensitive** to comply with Windows file naming semantics.</span></span>  
  
    2.  <span data-ttu-id="2435a-132">Se non si specifica un valore per **FILETABLE_COLLATE_FILENAME**o si specifica **database_default**, la colonna eredita le regole di confronto del database corrente.</span><span class="sxs-lookup"><span data-stu-id="2435a-132">If you do not provide a value for **FILETABLE_COLLATE_FILENAME**, or you specify **database_default**, the column inherits the collation of the current database.</span></span> <span data-ttu-id="2435a-133">Se nelle regole di confronto del database corrente viene applicata la distinzione tra maiuscole e minuscole, viene generato un errore e l'operazione **CREATE TABLE** non viene completata.</span><span class="sxs-lookup"><span data-stu-id="2435a-133">If the current database collation is case-sensitive, an error is raised and the **CREATE TABLE** operation fails.</span></span>  
  
3.  <span data-ttu-id="2435a-134">È inoltre possibile specificare i nomi da utilizzare per i 3 vincoli di chiave primaria e univoci creati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="2435a-134">You can also specify the names to be used for the 3 primary key and unique constraints that are automatically created.</span></span> <span data-ttu-id="2435a-135">Se non si forniscono nomi, vengono generati dal sistema come descritto più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="2435a-135">If you do not provide names, then the system generates names as described later in this topic.</span></span>  
  
    -   <span data-ttu-id="2435a-136">**FILETABLE_PRIMARY_KEY_CONSTRAINT_NAME**</span><span class="sxs-lookup"><span data-stu-id="2435a-136">**FILETABLE_PRIMARY_KEY_CONSTRAINT_NAME**</span></span>  
  
    -   <span data-ttu-id="2435a-137">**FILETABLE_STREAMID_UNIQUE_CONSTRAINT_NAME**</span><span class="sxs-lookup"><span data-stu-id="2435a-137">**FILETABLE_STREAMID_UNIQUE_CONSTRAINT_NAME**</span></span>  
  
    -   <span data-ttu-id="2435a-138">**FILETABLE_FULLPATH_UNIQUE_CONSTRAINT_NAME**</span><span class="sxs-lookup"><span data-stu-id="2435a-138">**FILETABLE_FULLPATH_UNIQUE_CONSTRAINT_NAME**</span></span>  
  
 <span data-ttu-id="2435a-139">**esempi**</span><span class="sxs-lookup"><span data-stu-id="2435a-139">**Examples**</span></span>  
  
 <span data-ttu-id="2435a-140">Nell'esempio seguente viene creata una nuova tabella FileTable e vengono specificati valori definiti dall'utente sia per **FILETABLE_DIRECTORY** che per **FILETABLE_COLLATE_FILENAME**.</span><span class="sxs-lookup"><span data-stu-id="2435a-140">The following example creates a new FileTable and specifies user-defined values for both **FILETABLE_DIRECTORY** and **FILETABLE_COLLATE_FILENAME**.</span></span>  
  
```sql  
CREATE TABLE DocumentStore AS FileTable  
    WITH (   
          FileTable_Directory = 'DocumentTable',  
          FileTable_Collate_Filename = database_default  
         );  
GO  
```  
  
 <span data-ttu-id="2435a-141">Nell'esempio seguente viene inoltre creata una nuova tabella FileTable.</span><span class="sxs-lookup"><span data-stu-id="2435a-141">The following example also creates a new FileTable.</span></span> <span data-ttu-id="2435a-142">Poiché non sono specificati valori definiti dall'utente, il valore di **FILETABLE_DIRECTORY** diventa il nome della tabella FileTable, il valore di **FILETABLE_COLLATE_FILENAME** diventa database_default e tramite i vincoli di chiave primaria e univoci si ricevono i nomi generati dal sistema.</span><span class="sxs-lookup"><span data-stu-id="2435a-142">Since user-defined values are not specified, the value of **FILETABLE_DIRECTORY** becomes the name of the FileTable, the value of **FILETABLE_COLLATE_FILENAME** becomes database_default, and the primary key and unique contraints receive system-generated names.</span></span>  
  
```sql  
CREATE TABLE DocumentStore AS FileTable;  
GO  
```  
  
 <span data-ttu-id="2435a-143">**Creare una tabella FileTable tramite SQL Server Management Studio**</span><span class="sxs-lookup"><span data-stu-id="2435a-143">**Create a FileTable by Using SQL Server Management Studio**</span></span>  
 <span data-ttu-id="2435a-144">In Esplora oggetti espandere gli oggetti inclusi nel database selezionato, fare clic con il pulsante destro del mouse sulla cartella **Tabelle** , quindi scegliere **Nuova FileTable**.</span><span class="sxs-lookup"><span data-stu-id="2435a-144">In Object Explorer, expand the objects under the selected database, then right-click on the **Tables** folder, and then select **New FileTable**.</span></span>  
  
 <span data-ttu-id="2435a-145">Verrà visualizzata una nuova finestra di script contenente un modello di script Transact-SQL, che è possibile personalizzare ed eseguire per creare una tabella FileTable.</span><span class="sxs-lookup"><span data-stu-id="2435a-145">This option opens a new script window which contains a Transact-SQL script template that you can customize and run to create a FileTable.</span></span> <span data-ttu-id="2435a-146">Per personalizzare facilmente lo script, utilizzare l'opzione **Imposta valori per parametri modello** dal menu **Query** .</span><span class="sxs-lookup"><span data-stu-id="2435a-146">Use the **Specify Values for Template Parameters** option on the **Query** menu to customize the script easily.</span></span>  
  
###  <a name="requirements-and-restrictions-for-creating-a-filetable"></a><a name="ReqCreate"></a> <span data-ttu-id="2435a-147">Requisiti e restrizioni per la creazione di una tabella FileTable</span><span class="sxs-lookup"><span data-stu-id="2435a-147">Requirements and Restrictions for Creating a FileTable</span></span>  
  
-   <span data-ttu-id="2435a-148">Non è possibile modificare una tabella esistente per convertirla in tabella FileTable.</span><span class="sxs-lookup"><span data-stu-id="2435a-148">You cannot alter an existing table to convert it into a FileTable.</span></span>  
  
-   <span data-ttu-id="2435a-149">La directory padre specificata precedentemente a livello di database deve includere un valore diverso da Null.</span><span class="sxs-lookup"><span data-stu-id="2435a-149">The parent directory previously specified at the database level must have a non-null value.</span></span> <span data-ttu-id="2435a-150">Per informazioni sulla specifica della directory a livello di database, vedere [Abilitazione dei prerequisiti per la tabella FileTable](enable-the-prerequisites-for-filetable.md).</span><span class="sxs-lookup"><span data-stu-id="2435a-150">For information about specifying the database-level directory, see [Enable the Prerequisites for FileTable](enable-the-prerequisites-for-filetable.md).</span></span>  
  
-   <span data-ttu-id="2435a-151">Poiché una tabella FileTable contiene una colonna FILESTREAM, tale tabella richiede un filegroup FILESTREAM valido.</span><span class="sxs-lookup"><span data-stu-id="2435a-151">A FileTable requires a valid FILESTREAM filegroup, since a FileTable contains a FILESTREAM column.</span></span> <span data-ttu-id="2435a-152">È eventualmente possibile specificare un filegroup FILESTREAM valido come parte del comando **CREATE TABLE** per la creazione di una tabella FileTable.</span><span class="sxs-lookup"><span data-stu-id="2435a-152">You can optionally specify a valid FILESTREAM filegroup as part of the **CREATE TABLE** command for creating a FileTable.</span></span> <span data-ttu-id="2435a-153">Se non si specifica un filegroup, la tabella FileTable utilizza il filegroup FILESTREAM predefinito per il database.</span><span class="sxs-lookup"><span data-stu-id="2435a-153">If you do not specify a filegroup, then the FileTable uses the default FILESTREAM filegroup for the database.</span></span> <span data-ttu-id="2435a-154">Se il database non include un filegroup FILESTREAM, viene generato un errore.</span><span class="sxs-lookup"><span data-stu-id="2435a-154">If the database does not have a FILESTREAM filegroup, then an error is raised.</span></span>  
  
-   <span data-ttu-id="2435a-155">Non è possibile creare un vincolo di tabella come parte di un'istruzione **CREATE TABLE...AS FILETABLE**.</span><span class="sxs-lookup"><span data-stu-id="2435a-155">You cannot create a table constraint as part of a **CREATE TABLE...AS FILETABLE** statement.</span></span> <span data-ttu-id="2435a-156">Sarà tuttavia possibile aggiungere il vincolo in seguito utilizzando un'istruzione **ALTER TABLE** .</span><span class="sxs-lookup"><span data-stu-id="2435a-156">However you can add the constraint later by using an **ALTER TABLE** statement.</span></span>  
  
-   <span data-ttu-id="2435a-157">Non è possibile creare una tabella FileTable nel database **tempdb** o in qualsiasi altro database di sistema.</span><span class="sxs-lookup"><span data-stu-id="2435a-157">You cannot create a FileTable in the **tempdb** database or in any of the other system databases.</span></span>  
  
-   <span data-ttu-id="2435a-158">Non è possibile creare una tabella FileTable come tabella temporanea.</span><span class="sxs-lookup"><span data-stu-id="2435a-158">You cannot create a FileTable as a temporary table.</span></span>  
  
##  <a name="altering-a-filetable"></a><a name="BasicsAlter"></a> <span data-ttu-id="2435a-159">Modifica di una tabella FileTable</span><span class="sxs-lookup"><span data-stu-id="2435a-159">Altering a FileTable</span></span>  
 <span data-ttu-id="2435a-160">Poiché una tabella FileTable ha uno schema predefinito e fisso, non è possibile aggiungere colonne o modificarle.</span><span class="sxs-lookup"><span data-stu-id="2435a-160">Since a FileTable has a pre-defined and fixed schema, you cannot add or change its columns.</span></span> <span data-ttu-id="2435a-161">È invece possibile aggiungere indici, trigger, vincoli e altri elementi personalizzati a una tabella FileTable.</span><span class="sxs-lookup"><span data-stu-id="2435a-161">However, you can add custom indexes, triggers, constraints, and other options to a FileTable.</span></span>  
  
 <span data-ttu-id="2435a-162">Per informazioni sull'uso dell'istruzione ALTER TABLE per abilitare o disabilitare lo spazio dei nomi FileTable, inclusi i vincoli definiti dal sistema, vedere [Gestione di tabelle FileTable](manage-filetables.md).</span><span class="sxs-lookup"><span data-stu-id="2435a-162">For information about using the ALTER TABLE statement to enable or disable the FileTable namespace, including the system-defined constraints, see [Manage FileTables](manage-filetables.md).</span></span>  
  
###  <a name="how-to-change-the-directory-for-a-filetable"></a><a name="HowToChange"></a> <span data-ttu-id="2435a-163">Procedura: Modificare la directory per una tabella FileTable</span><span class="sxs-lookup"><span data-stu-id="2435a-163">How To: Change the Directory for a FileTable</span></span>  
 <span data-ttu-id="2435a-164">**Modificare la directory per una tabella FileTable tramite Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="2435a-164">**Change the Directory for a FileTable by Using Transact-SQL**</span></span>  
 <span data-ttu-id="2435a-165">Chiamare l'istruzione ALTER TABLE e specificare un nuovo valore valido per l'opzione SET di **FILETABLE_DIRECTORY** .</span><span class="sxs-lookup"><span data-stu-id="2435a-165">Call the ALTER TABLE statement and provide a valid new value for the **FILETABLE_DIRECTORY** SET option.</span></span>  
  
 <span data-ttu-id="2435a-166">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="2435a-166">**Example**</span></span>  
  
```sql  
ALTER TABLE filetable_name  
    SET ( FILETABLE_DIRECTORY = N'directory_name' );  
GO  
```  
  
 <span data-ttu-id="2435a-167">**Modificare la directory per una tabella FileTable tramite SQL Server Management Studio**</span><span class="sxs-lookup"><span data-stu-id="2435a-167">**Change the Directory for a FileTable by Using SQL Server Management Studio**</span></span>  
 <span data-ttu-id="2435a-168">In Esplora oggetti fare clic con il pulsante destro del mouse sulla tabella FileTable e selezionare **Proprietà** per aprire la finestra di dialogo **Proprietà tabella** .</span><span class="sxs-lookup"><span data-stu-id="2435a-168">In Object Explorer, right-click on the FileTable and select **Properties** to open the **Table Properties** dialog box.</span></span> <span data-ttu-id="2435a-169">Nella pagina **FileTable** immettere un nuovo valore per **Nome di directory FileTable**.</span><span class="sxs-lookup"><span data-stu-id="2435a-169">On the **FileTable** page, enter a new value for **FileTable directory name**.</span></span>  
  
###  <a name="requirements-and-restrictions-for-altering-a-filetable"></a><a name="ReqAlter"></a> <span data-ttu-id="2435a-170">Requisiti e restrizioni per la modifica di una tabella FileTable</span><span class="sxs-lookup"><span data-stu-id="2435a-170">Requirements and Restrictions for Altering a FileTable</span></span>  
  
-   <span data-ttu-id="2435a-171">Non è possibile modificare il valore di **FILETABLE_COLLATE_FILENAME**.</span><span class="sxs-lookup"><span data-stu-id="2435a-171">You cannot alter the value of **FILETABLE_COLLATE_FILENAME**.</span></span>  
  
-   <span data-ttu-id="2435a-172">Non è possibile modificare, eliminare o disabilitare le colonne definite dal sistema di una tabella FileTable.</span><span class="sxs-lookup"><span data-stu-id="2435a-172">You cannot change, drop, or disable the system-defined columns of a FileTable.</span></span>  
  
-   <span data-ttu-id="2435a-173">Non è possibile aggiungere nuove colonne utente, colonne calcolate o colonne calcolate persistenti a una tabella FileTable.</span><span class="sxs-lookup"><span data-stu-id="2435a-173">You cannot add new user columns, computed columns, or persisted computed columns to a FileTable.</span></span>  
  
##  <a name="dropping-a-filetable"></a><a name="BasicsDrop"></a> <span data-ttu-id="2435a-174">Eliminazione di una tabella FileTable</span><span class="sxs-lookup"><span data-stu-id="2435a-174">Dropping a FileTable</span></span>  
 <span data-ttu-id="2435a-175">È possibile eliminare una tabella FileTable tramite la sintassi ordinaria dell'istruzione [DROP TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2435a-175">You can drop a FileTable by using the ordinary syntax for the [DROP TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-table-transact-sql) statement.</span></span>  
  
 <span data-ttu-id="2435a-176">Quando si elimina una tabella FileTable, anche i seguenti oggetti vengono eliminati:</span><span class="sxs-lookup"><span data-stu-id="2435a-176">When you drop a FileTable, the following objects are also dropped:</span></span>  
  
-   <span data-ttu-id="2435a-177">Vengono inoltre rilasciate tutte le colonne della tabella FileTable e tutti gli oggetti a essa associati, come gli indici, i vincoli e i trigger.</span><span class="sxs-lookup"><span data-stu-id="2435a-177">All the columns of the FileTable and all the objects associated with the table, such as indexes, constraints, and triggers, are also dropped.</span></span>  
  
-   <span data-ttu-id="2435a-178">La directory FileTable e le sottodirectory in essa contenute scompaiono dal file FILESTREAM e dalla gerarchia di directory del database.</span><span class="sxs-lookup"><span data-stu-id="2435a-178">The FileTable directory and the sub-directories that it contained disappear from the FILESTREAM file and directory hierarchy of the database.</span></span>  
  
 <span data-ttu-id="2435a-179">Il comando DROP TABLE ha esito negativo se nello spazio dei nomi dei file della tabella FileTable sono presenti handle di file aperti.</span><span class="sxs-lookup"><span data-stu-id="2435a-179">The DROP TABLE command fails if there are open file handles in the FileTable's file namespace.</span></span> <span data-ttu-id="2435a-180">Per informazioni sulla chiusura di handle aperti, vedere [Gestione di tabelle FileTable](manage-filetables.md).</span><span class="sxs-lookup"><span data-stu-id="2435a-180">For information about closing open handles, see [Manage FileTables](manage-filetables.md).</span></span>  
  
##  <a name="other-database-objects-are-created-when-you-create-a-filetable"></a><a name="BasicsOtherObjects"></a> <span data-ttu-id="2435a-181">Quando si crea una tabella FileTable, vengono creati altri oggetti di database</span><span class="sxs-lookup"><span data-stu-id="2435a-181">Other Database Objects Are Created When You Create a FileTable</span></span>  
 <span data-ttu-id="2435a-182">Quando si crea una nuova tabella FileTable, vengono creati anche alcuni indici e vincoli definiti dal sistema.</span><span class="sxs-lookup"><span data-stu-id="2435a-182">When you create a new FileTable, some system-defined indexes and constraints are also created.</span></span> <span data-ttu-id="2435a-183">Non è possibile modificare o eliminare questi oggetti, che verranno eliminato solo all'eliminazione della tabella FileTable stessa.</span><span class="sxs-lookup"><span data-stu-id="2435a-183">You cannot alter or drop these objects; they disappear only when the FileTable itself is dropped.</span></span> <span data-ttu-id="2435a-184">Per visualizzare l'elenco di questi oggetti, eseguire una query sulla vista del catalogo [sys.filetable_system_defined_objects &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-filetable-system-defined-objects-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2435a-184">To see the list of these objects, query the catalog view [sys.filetable_system_defined_objects &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-filetable-system-defined-objects-transact-sql).</span></span>  
  
```sql  
--View all objects for all filetables, unsorted  
SELECT * FROM sys.filetable_system_defined_objects;  
GO  
  
--View sorted list with friendly names  
SELECT OBJECT_NAME(parent_object_id) AS 'FileTable', OBJECT_NAME(object_id) AS 'System-defined Object'  
    FROM sys.filetable_system_defined_objects  
    ORDER BY FileTable, 'System-defined Object';  
GO  
```  
  
 <span data-ttu-id="2435a-185">**Indici creati durante la creazione di una nuova tabella FileTable**</span><span class="sxs-lookup"><span data-stu-id="2435a-185">**Indexes that are created when you create a new FileTable**</span></span>  
 <span data-ttu-id="2435a-186">Quando si crea una nuova tabella FileTable, vengono creati anche gli indici definiti dal sistema seguenti:</span><span class="sxs-lookup"><span data-stu-id="2435a-186">When you create a new FileTable, the following system-defined indexes are also created:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2435a-187">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="2435a-187">**Columns**</span></span>|<span data-ttu-id="2435a-188">**Tipo di indice**</span><span class="sxs-lookup"><span data-stu-id="2435a-188">**Index type**</span></span>|  
|<span data-ttu-id="2435a-189">[path_locator] ASC</span><span class="sxs-lookup"><span data-stu-id="2435a-189">[path_locator] ASC</span></span>|<span data-ttu-id="2435a-190">Chiave primaria, non cluster</span><span class="sxs-lookup"><span data-stu-id="2435a-190">Primary Key, nonclustered</span></span>|  
|<span data-ttu-id="2435a-191">[parent_path_locator] ASC,</span><span class="sxs-lookup"><span data-stu-id="2435a-191">[parent_path_locator] ASC,</span></span><br /><br /> <span data-ttu-id="2435a-192">[name] ASC</span><span class="sxs-lookup"><span data-stu-id="2435a-192">[name] ASC</span></span>|<span data-ttu-id="2435a-193">Univoco, non cluster</span><span class="sxs-lookup"><span data-stu-id="2435a-193">Unique, nonclustered</span></span>|  
|<span data-ttu-id="2435a-194">[stream_id] ASC</span><span class="sxs-lookup"><span data-stu-id="2435a-194">[stream_id] ASC</span></span>|<span data-ttu-id="2435a-195">Univoco, non cluster</span><span class="sxs-lookup"><span data-stu-id="2435a-195">Unique, nonclustered</span></span>|  
  
 <span data-ttu-id="2435a-196">**Vincoli creati durante la creazione di una nuova tabella FileTable**</span><span class="sxs-lookup"><span data-stu-id="2435a-196">**Constraints that are created when you create a new FileTable**</span></span>  
 <span data-ttu-id="2435a-197">Quando si crea una nuova tabella FileTable, vengono creati anche i vincoli definiti dal sistema seguenti:</span><span class="sxs-lookup"><span data-stu-id="2435a-197">When you create a new FileTable, the following system-defined constraints are also created:</span></span>  
  
|<span data-ttu-id="2435a-198">Vincoli</span><span class="sxs-lookup"><span data-stu-id="2435a-198">Constraints</span></span>|<span data-ttu-id="2435a-199">Imposizioni</span><span class="sxs-lookup"><span data-stu-id="2435a-199">Enforces</span></span>|  
|-----------------|--------------|  
|<span data-ttu-id="2435a-200">Vincoli predefiniti sulle seguenti colonne:</span><span class="sxs-lookup"><span data-stu-id="2435a-200">Default constraints on the following columns:</span></span><br /><br /> <span data-ttu-id="2435a-201">**creation_time**</span><span class="sxs-lookup"><span data-stu-id="2435a-201">**creation_time**</span></span> <br /> <span data-ttu-id="2435a-202">**is_archive**</span><span class="sxs-lookup"><span data-stu-id="2435a-202">**is_archive**</span></span> <br /> <span data-ttu-id="2435a-203">**is_directory**</span><span class="sxs-lookup"><span data-stu-id="2435a-203">**is_directory**</span></span> <br /> <span data-ttu-id="2435a-204">**is_hidden**</span><span class="sxs-lookup"><span data-stu-id="2435a-204">**is_hidden**</span></span> <br /> <span data-ttu-id="2435a-205">**is_offline**</span><span class="sxs-lookup"><span data-stu-id="2435a-205">**is_offline**</span></span> <br /> <span data-ttu-id="2435a-206">**is_readonly**</span><span class="sxs-lookup"><span data-stu-id="2435a-206">**is_readonly**</span></span> <br /> <span data-ttu-id="2435a-207">**is_system**</span><span class="sxs-lookup"><span data-stu-id="2435a-207">**is_system**</span></span> <br /> <span data-ttu-id="2435a-208">**is_temporary**</span><span class="sxs-lookup"><span data-stu-id="2435a-208">**is_temporary**</span></span> <br /> <span data-ttu-id="2435a-209">**last_access_time**</span><span class="sxs-lookup"><span data-stu-id="2435a-209">**last_access_time**</span></span> <br /> <span data-ttu-id="2435a-210">**last_write_time**</span><span class="sxs-lookup"><span data-stu-id="2435a-210">**last_write_time**</span></span> <br /> <span data-ttu-id="2435a-211">**path_locator**</span><span class="sxs-lookup"><span data-stu-id="2435a-211">**path_locator**</span></span> <br /> <span data-ttu-id="2435a-212">**stream_id**</span><span class="sxs-lookup"><span data-stu-id="2435a-212">**stream_id**</span></span>|<span data-ttu-id="2435a-213">I vincoli predefiniti definiti dal sistema applicano valori predefiniti per le colonne specificate.</span><span class="sxs-lookup"><span data-stu-id="2435a-213">The system-defined default constraints enforce default values for the specified columns.</span></span>|  
|<span data-ttu-id="2435a-214">Vincoli CHECK</span><span class="sxs-lookup"><span data-stu-id="2435a-214">Check constraints</span></span>|<span data-ttu-id="2435a-215">I vincoli CHECK definiti dal sistema applicano i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="2435a-215">The system-defined check constraints enforce the following requirements:</span></span><br /><br /> <span data-ttu-id="2435a-216">Nomi file validi.</span><span class="sxs-lookup"><span data-stu-id="2435a-216">Valid filenames.</span></span><br /><br /> <span data-ttu-id="2435a-217">Attributi di file validi.</span><span class="sxs-lookup"><span data-stu-id="2435a-217">Valid file attributes.</span></span><br /><br /> <span data-ttu-id="2435a-218">L'oggetto padre deve essere una directory.</span><span class="sxs-lookup"><span data-stu-id="2435a-218">Parent object must be a directory.</span></span><br /><br /> <span data-ttu-id="2435a-219">La gerarchia dello spazio dei nomi è bloccata durante la modifica dei file.</span><span class="sxs-lookup"><span data-stu-id="2435a-219">Namespace hierarchy is locked during file manipulation.</span></span>|  
  
 <span data-ttu-id="2435a-220">**Convenzione di denominazione per i vincoli definiti dal sistema**</span><span class="sxs-lookup"><span data-stu-id="2435a-220">**Naming convention for the system-defined constraints**</span></span>  
 <span data-ttu-id="2435a-221">I vincoli definiti dal sistema descritti in precedenza vengono denominati usando il formato **\<constraintType>_\<tablename>[\_\<columnname>]\_\<uniquifier>** dove:</span><span class="sxs-lookup"><span data-stu-id="2435a-221">The system-defined constraints described above are named in the format **\<constraintType>_\<tablename>[\_\<columnname>]\_\<uniquifier>** where:</span></span>  
  
-   <span data-ttu-id="2435a-222">*<tipovincolo>* è CK (vincolo CHECK), DF (vincolo DEFAULT), FK (chiave esterna), PK (chiave primaria) o UQ (vincolo UNIQUE).</span><span class="sxs-lookup"><span data-stu-id="2435a-222">*<constraint_type>* is CK (check constraint), DF (default constraint), FK (foreign key), PK (primary key), or UQ (unique constraint).</span></span>  
  
-   <span data-ttu-id="2435a-223">*\<uniquifier>* è una stringa generata dal sistema per specificare un nome univoco.</span><span class="sxs-lookup"><span data-stu-id="2435a-223">*\<uniquifier>* is a system-generated string to make the name unique.</span></span> <span data-ttu-id="2435a-224">È possibile che questa stringa contenga il nome della tabella FileTable e un identificatore univoco.</span><span class="sxs-lookup"><span data-stu-id="2435a-224">This string may contain the FileTable name and a unique identifier.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2435a-225">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2435a-225">See Also</span></span>  
 [<span data-ttu-id="2435a-226">Gestire tabelle FileTable</span><span class="sxs-lookup"><span data-stu-id="2435a-226">Manage FileTables</span></span>](manage-filetables.md)  
  
  
