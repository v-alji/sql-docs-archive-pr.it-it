---
title: Accedere a tabelle FileTable tramite Transact-SQL| Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: filestream
ms.topic: conceptual
helpviewer_keywords:
- FileTables [SQL Server], accessing files with T-SQL
ms.assetid: 3c4a5ffb-c521-4696-99cb-2b03cffc9c02
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 2c47751ef34747e1b3742accf5040846ecde074f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721500"
---
# <a name="access-filetables-with-transact-sql"></a><span data-ttu-id="bf331-102">Accesso a tabelle FileTable tramite Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="bf331-102">Access FileTables with Transact-SQL</span></span>
  <span data-ttu-id="bf331-103">Viene descritto il funzionamento dei comandi [!INCLUDE[tsql](../../includes/tsql-md.md)] DML (Data Manipulation Language) con una tabella FileTable.</span><span class="sxs-lookup"><span data-stu-id="bf331-103">Describes how [!INCLUDE[tsql](../../includes/tsql-md.md)] data manipulation language (DML) commands work with FileTables.</span></span>  
  
##  <a name="insert-operations-on-filetables"></a><a name="BasicsInsert"></a> <span data-ttu-id="bf331-104">Operazioni INSERT in tabelle FileTable</span><span class="sxs-lookup"><span data-stu-id="bf331-104">INSERT Operations on FileTables</span></span>  
 <span data-ttu-id="bf331-105">Le considerazioni seguenti si applicano alle operazioni **INSERT** in tabelle FileTable:</span><span class="sxs-lookup"><span data-stu-id="bf331-105">The following considerations apply to **INSERT** Operations on FileTables:</span></span>  
  
-   <span data-ttu-id="bf331-106">Tutte le colonne di attributi dei file dispongono di vincoli NOT NULL.</span><span class="sxs-lookup"><span data-stu-id="bf331-106">All the file attribute columns have NOT NULL constraints.</span></span> <span data-ttu-id="bf331-107">Se i valori non sono impostati in modo esplicito, vengono forniti valori predefiniti appropriati.</span><span class="sxs-lookup"><span data-stu-id="bf331-107">If values are not explicitly set, then appropriate default values are supplied.</span></span>  
  
-   <span data-ttu-id="bf331-108">Se l'istruzione INSERT imposta **name**, **path_locator**, **parent_path_locator**o gli attributi del file, verranno applicati vincoli definiti dal sistema.</span><span class="sxs-lookup"><span data-stu-id="bf331-108">System-defined constraints are enforced if the INSERT statement sets the **name**, **path_locator**, **parent_path_locator**, or file attributes.</span></span>  
  
-   <span data-ttu-id="bf331-109">L'applicazione può ottenere **path_locator** per un file o una directory passando il percorso del file system alla funzione [GetPathLocator &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/getpathlocator-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="bf331-109">The application can obtain the **path_locator** for a file or directory by providing the file system path to the [GetPathLocator &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/getpathlocator-transact-sql) function.</span></span>  
  
##  <a name="update-operations-on-filetables"></a><a name="BasicsUpdate"></a> <span data-ttu-id="bf331-110">Operazioni UPDATE in tabelle FileTable</span><span class="sxs-lookup"><span data-stu-id="bf331-110">UPDATE Operations on FileTables</span></span>  
 <span data-ttu-id="bf331-111">Le considerazioni seguenti si applicano alle operazioni **UPDATE** in tabelle FileTable:</span><span class="sxs-lookup"><span data-stu-id="bf331-111">The following considerations apply to **UPDATE** operations on FileTables:</span></span>  
  
-   <span data-ttu-id="bf331-112">Sono consentiti aggiornamenti a tutti i dati definiti dall'utente.</span><span class="sxs-lookup"><span data-stu-id="bf331-112">Updates to any user-defined data are allowed.</span></span>  
  
-   <span data-ttu-id="bf331-113">Se l'istruzione INSERT imposta **name**, **path_locator**, **parent_path_locator**o gli attributi del file, verranno applicati vincoli definiti dal sistema.</span><span class="sxs-lookup"><span data-stu-id="bf331-113">System-defined constraints are enforced if the INSERT statement sets the **name**, **path_locator**, **parent_path_locator**, or file attributes.</span></span>  
  
-   <span data-ttu-id="bf331-114">Gli aggiornamenti possono essere effettuati sui dati FILESTREAM nella colonna **file_stream** senza influire su alcune delle altre colonne, compresi i timestamp.</span><span class="sxs-lookup"><span data-stu-id="bf331-114">Updates can be made to the FILESTREAM data in the **file_stream** column without affecting any of the other columns, including the timestamps.</span></span>  
  
##  <a name="delete-operations-on-filetables"></a><a name="BasicsDelete"></a> <span data-ttu-id="bf331-115">Operazioni DELETE in tabelle FileTable</span><span class="sxs-lookup"><span data-stu-id="bf331-115">DELETE Operations on FileTables</span></span>  
 <span data-ttu-id="bf331-116">Le considerazioni seguenti si applicano alle operazioni **DELETE** in tabelle FileTable:</span><span class="sxs-lookup"><span data-stu-id="bf331-116">The following considerations apply to **DELETE** operations on FileTables:</span></span>  
  
-   <span data-ttu-id="bf331-117">L'eliminazione di una riga comporta la rimozione del file o della directory corrispondente dal file system.</span><span class="sxs-lookup"><span data-stu-id="bf331-117">Deleting a row also removes the corresponding file or directory from the file system.</span></span>  
  
-   <span data-ttu-id="bf331-118">L'eliminazione di una riga non riesce se la riga corrisponde a una directory che contiene altri file o directory.</span><span class="sxs-lookup"><span data-stu-id="bf331-118">Deleting a row fails if the row corresponds to a directory that contains other files or directories.</span></span>  
  
##  <a name="constraints-that-are-enforced-for-dml-operations-on-filetables"></a><a name="BasicsConstraints"></a> <span data-ttu-id="bf331-119">Vincoli applicati per operazioni DML in tabelle FileTable</span><span class="sxs-lookup"><span data-stu-id="bf331-119">Constraints That Are Enforced for DML Operations on FileTables</span></span>  
 <span data-ttu-id="bf331-120">I vincoli referenziali/univoci definiti dal sistema garantiscono che le azioni DML non danneggino l'integrità della gerarchia dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="bf331-120">System-defined constraints ensure that DML actions do not compromise the integrity of the file namespace hierarchy.</span></span> <span data-ttu-id="bf331-121">I vincoli applicati includono gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="bf331-121">The constraints that are enforced include the following:</span></span>  
  
-   <span data-ttu-id="bf331-122">Quando si imposta o si modifica il **nome** del file o della directory:</span><span class="sxs-lookup"><span data-stu-id="bf331-122">When you set or change the **name** of the file or directory:</span></span>  
  
    -   <span data-ttu-id="bf331-123">Vengono applicate le convenzioni di denominazione di Windows per file e directory.</span><span class="sxs-lookup"><span data-stu-id="bf331-123">Windows file and directory naming conventions are enforced.</span></span>  
  
    -   <span data-ttu-id="bf331-124">Verrà applicata l'univocità del nome nella directory padre.</span><span class="sxs-lookup"><span data-stu-id="bf331-124">The uniqueness of the name in the parent directory is enforced.</span></span>  
  
-   <span data-ttu-id="bf331-125">Quando si imposta o modifica il percorso di un file o di una directory impostando o modificando **path_locator** o **parent_path_locator**:</span><span class="sxs-lookup"><span data-stu-id="bf331-125">When you set or change the location of a file or directory by setting or changing the **path_locator** or **parent_path_locator**:</span></span>  
  
    -   <span data-ttu-id="bf331-126">Viene applicata l'univocità.</span><span class="sxs-lookup"><span data-stu-id="bf331-126">Uniqueness is enforced.</span></span>  
  
    -   <span data-ttu-id="bf331-127">Viene applicata la consistenza dell'albero gerarchico di directory e file, inclusa la coerenza dei valori **path_locator** e **parent_path_locator** .</span><span class="sxs-lookup"><span data-stu-id="bf331-127">The consistency of the hierarchical tree of directories and files is enforced, including the consistency of **path_locator** and **parent_path_locator** values.</span></span>  
  
-   <span data-ttu-id="bf331-128">Non è possibile impostare il valore **is_directory** su true mentre la colonna **file_stream** è impostata su non Null.</span><span class="sxs-lookup"><span data-stu-id="bf331-128">The value of **is_directory** cannot be set to true when the **file_stream** column is not null.</span></span> <span data-ttu-id="bf331-129">I dati nella colonna **file_stream** indicano che la riga rappresenta un file e non una directory.</span><span class="sxs-lookup"><span data-stu-id="bf331-129">Data in the **file_stream** column indicates that the row represents a file and not a directory.</span></span>  
  
-   <span data-ttu-id="bf331-130">Le colonne degli attributi di file non possono essere Null.</span><span class="sxs-lookup"><span data-stu-id="bf331-130">File attribute columns cannot be null.</span></span> <span data-ttu-id="bf331-131">I vincoli NOT NULL vengono applicati con i valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="bf331-131">NOT NULL constraints are enforced with default values.</span></span>  
  
-   <span data-ttu-id="bf331-132">Il valore di **last_access_time** non può essere precedente a **last_write_time** e **creation_time**.</span><span class="sxs-lookup"><span data-stu-id="bf331-132">The value of **last_access_time** cannot be earlier than **last_write_time** and **creation_time**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf331-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bf331-133">See Also</span></span>  
 <span data-ttu-id="bf331-134">[Caricamento di file in FileTable](load-files-into-filetables.md) </span><span class="sxs-lookup"><span data-stu-id="bf331-134">[Load Files into FileTables](load-files-into-filetables.md) </span></span>  
 <span data-ttu-id="bf331-135">[Work with Directories and Paths in FileTables](work-with-directories-and-paths-in-filetables.md) </span><span class="sxs-lookup"><span data-stu-id="bf331-135">[Work with Directories and Paths in FileTables](work-with-directories-and-paths-in-filetables.md) </span></span>  
 <span data-ttu-id="bf331-136">[Accedere alle tabelle FileTable con API di Input-Output dei file](access-filetables-with-file-input-output-apis.md) </span><span class="sxs-lookup"><span data-stu-id="bf331-136">[Access FileTables with File Input-Output APIs](access-filetables-with-file-input-output-apis.md) </span></span>  
 [<span data-ttu-id="bf331-137">DDL, funzioni, stored procedure e viste FileTable</span><span class="sxs-lookup"><span data-stu-id="bf331-137">FileTable DDL, Functions, Stored Procedures, and Views</span></span>](../views/views.md)  
  
  
