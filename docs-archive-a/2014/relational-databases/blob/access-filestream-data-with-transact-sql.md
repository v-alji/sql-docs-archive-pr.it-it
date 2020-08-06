---
title: Accedere a Dati FILESTREAM con Transact-SQL| Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: filestream
ms.topic: conceptual
helpviewer_keywords:
- FILESTREAM [SQL Server], Transact-SQL
ms.assetid: a6bf0ce7-7e5e-4a07-8917-ee526c9d0a05
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 06d395f1acc3723fc6b45fdfa08efbae354d8014
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718288"
---
# <a name="access-filestream-data-with-transact-sql"></a><span data-ttu-id="c868c-102">Accedere a Dati FILESTREAM con Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c868c-102">Access FILESTREAM Data with Transact-SQL</span></span>
  <span data-ttu-id="c868c-103">Questo argomento descrive come usare le istruzioni [!INCLUDE[tsql](../../includes/tsql-md.md)] INSERT, UPDATE e DELETE per gestire dati FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="c868c-103">This topic describes how to use the [!INCLUDE[tsql](../../includes/tsql-md.md)] INSERT, UPDATE, and DELETE statements to manage FILESTREAM data.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c868c-104">Gli esempi riportati in questo argomento richiedono il database e la tabella abilitati per FILESTREAM creati in [Creare un database abilitato per FILESTREAM](create-a-filestream-enabled-database.md) e [Creare una tabella per archiviare dati FILESTREAM](create-a-table-for-storing-filestream-data.md).</span><span class="sxs-lookup"><span data-stu-id="c868c-104">The examples in this topic require the FILESTREAM-enabled database and table that are created in [Create a FILESTREAM-Enabled Database](create-a-filestream-enabled-database.md) and [Create a Table for Storing FILESTREAM Data](create-a-table-for-storing-filestream-data.md).</span></span>  
  
##  <a name="inserting-a-row-that-contains-filestream-data"></a><a name="ins"></a> <span data-ttu-id="c868c-105">Inserimento di una riga che contiene dati FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="c868c-105">Inserting a Row That Contains FILESTREAM Data</span></span>  
 <span data-ttu-id="c868c-106">Per aggiungere una riga a una tabella che supporta i dati FILESTREAM, utilizzare l'istruzione [!INCLUDE[tsql](../../includes/tsql-md.md)] INSERT.</span><span class="sxs-lookup"><span data-stu-id="c868c-106">To add a row to a table that supports FILESTREAM data, use the [!INCLUDE[tsql](../../includes/tsql-md.md)] INSERT statement.</span></span> <span data-ttu-id="c868c-107">Quando vengono inseriti dati in una colonna FILESTREAM, è possibile inserire NULL o un valore `varbinary(max)`.</span><span class="sxs-lookup"><span data-stu-id="c868c-107">When you insert data into a FILESTREAM column, you can insert NULL or a `varbinary(max)` value.</span></span>  
  
### <a name="inserting-null"></a><span data-ttu-id="c868c-108">Inserimento di NULL</span><span class="sxs-lookup"><span data-stu-id="c868c-108">Inserting NULL</span></span>  
 <span data-ttu-id="c868c-109">Nell'esempio seguente viene illustrato come inserire il valore `NULL`.</span><span class="sxs-lookup"><span data-stu-id="c868c-109">The following example shows how to insert `NULL`.</span></span> <span data-ttu-id="c868c-110">Se il valore FILESTREAM è `NULL`, il [!INCLUDE[ssDE](../../includes/ssde-md.md)] non crea alcun file nel file system.</span><span class="sxs-lookup"><span data-stu-id="c868c-110">When the FILESTREAM value is `NULL`, the [!INCLUDE[ssDE](../../includes/ssde-md.md)] does not create a file in the file system.</span></span>  
  
 [!code-sql[FILESTREAM#FS_InsertNULL](../../snippets/tsql/SQL15/tsql/filestream/transact-sql/filestream.sql#fs_insertnull)]  
  
### <a name="inserting-a-zero-length-record"></a><span data-ttu-id="c868c-111">Inserimento di un record di lunghezza zero</span><span class="sxs-lookup"><span data-stu-id="c868c-111">Inserting a Zero-Length Record</span></span>  
 <span data-ttu-id="c868c-112">Nell'esempio seguente viene illustrato l'utilizzo di `INSERT` per creare un record di lunghezza zero.</span><span class="sxs-lookup"><span data-stu-id="c868c-112">The following example shows how to use `INSERT` to create a zero-length record.</span></span> <span data-ttu-id="c868c-113">Questa istruzione risulta utile quando si desidera ottenere un handle di file, ma si modifica il file utilizzando API Win32.</span><span class="sxs-lookup"><span data-stu-id="c868c-113">This is useful for when you want to obtain a file handle, but will be manipulating the file by using Win32 APIs.</span></span>  
  
 [!code-sql[FILESTREAM#FS_InsertZero](../../snippets/tsql/SQL15/tsql/filestream/transact-sql/filestream.sql#fs_insertzero)]  
  
### <a name="creating-a-data-file"></a><span data-ttu-id="c868c-114">Creazione di un file di dati</span><span class="sxs-lookup"><span data-stu-id="c868c-114">Creating a Data File</span></span>  
 <span data-ttu-id="c868c-115">Nell'esempio seguente viene illustrato l'utilizzo di `INSERT` per creare un file contenente dati.</span><span class="sxs-lookup"><span data-stu-id="c868c-115">The following example shows how to use `INSERT` to create a file that contains data.</span></span> <span data-ttu-id="c868c-116">Il [!INCLUDE[ssDE](../../includes/ssde-md.md)] converte la stringa `Seismic Data` in un valore `varbinary(max)` .</span><span class="sxs-lookup"><span data-stu-id="c868c-116">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] converts the string `Seismic Data` to a `varbinary(max)` value.</span></span> <span data-ttu-id="c868c-117">Se non esiste già, FILESTREAM crea il file di Windows. I dati verranno quindi aggiunti al file di dati.</span><span class="sxs-lookup"><span data-stu-id="c868c-117">FILESTREAM creates the Windows file if it does not already exist.The data is then added to the data file.</span></span>  
  
 [!code-sql[FILESTREAM#FS_InsertData](../../snippets/tsql/SQL15/tsql/filestream/transact-sql/filestream.sql#fs_insertdata)]  
  
 <span data-ttu-id="c868c-118">Se si selezionano tutti i dati della tabella `Archive`,`dbo.Records`</span><span class="sxs-lookup"><span data-stu-id="c868c-118">When you select all data from the `Archive`.`dbo.Records`</span></span> <span data-ttu-id="c868c-119">i risultati dovrebbero essere analoghi a quelli illustrati nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="c868c-119">table, the results are similar to the results that are shown in the following table.</span></span> <span data-ttu-id="c868c-120">La colonna `Id` conterrà tuttavia GUID diversi.</span><span class="sxs-lookup"><span data-stu-id="c868c-120">However, the `Id` column will contain different GUIDs.</span></span>  
  
|<span data-ttu-id="c868c-121">ID</span><span class="sxs-lookup"><span data-stu-id="c868c-121">Id</span></span>|<span data-ttu-id="c868c-122">SerialNumber</span><span class="sxs-lookup"><span data-stu-id="c868c-122">SerialNumber</span></span>|<span data-ttu-id="c868c-123">Riprendi</span><span class="sxs-lookup"><span data-stu-id="c868c-123">Resume</span></span>|  
|--------|------------------|------------|  
|`C871B90F-D25E-47B3-A560-7CC0CA405DAC`|`1`|`NULL`|  
|`F8F5C314-0559-4927-8FA9-1535EE0BDF50`|`2`|`0x`|  
|`7F680840-B7A4-45D4-8CD5-527C44D35B3F`|`3`|`0x536569736D69632044617461`|  
  
##  <a name="updating-filestream-data"></a><a name="upd"></a> <span data-ttu-id="c868c-124">Aggiornamento di dati FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="c868c-124">Updating FILESTREAM Data</span></span>  
 <span data-ttu-id="c868c-125">Per aggiornare i dati in file del file system, è possibile usare [!INCLUDE[tsql](../../includes/tsql-md.md)] , sebbene sia preferibile evitare questa procedura quando si devono trasmettere elevate quantità di dati a un file.</span><span class="sxs-lookup"><span data-stu-id="c868c-125">You can use [!INCLUDE[tsql](../../includes/tsql-md.md)] to update the data in the file system file; although, you might not want to do this when you have to stream large amounts of data to a file.</span></span>  
  
 <span data-ttu-id="c868c-126">Nel seguente esempio il testo nel record del file viene sostituito con il testo `Xray 1`.</span><span class="sxs-lookup"><span data-stu-id="c868c-126">The following example replaces any text in the file record with the text `Xray 1`.</span></span>  
  
 [!code-sql[FILESTREAM#FS_UpdateData](../../snippets/tsql/SQL15/tsql/filestream/transact-sql/filestream.sql#fs_updatedata)]  
  
##  <a name="deleting-filestream-data"></a><a name="del"></a> <span data-ttu-id="c868c-127">Eliminazione di dati FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="c868c-127">Deleting FILESTREAM Data</span></span>  
 <span data-ttu-id="c868c-128">Quando si elimina una riga che contiene un campo FILESTREAM, vengono eliminati anche i file del file system sottostanti.</span><span class="sxs-lookup"><span data-stu-id="c868c-128">When you delete a row that contains a FILESTREAM field, you also delete its underlying file system files.</span></span> <span data-ttu-id="c868c-129">L'unico modo per eliminare una riga e pertanto il file è l'utilizzo dell'istruzione [!INCLUDE[tsql](../../includes/tsql-md.md)] DELETE.</span><span class="sxs-lookup"><span data-stu-id="c868c-129">The only way to delete a row, and therefore the file, is to use the [!INCLUDE[tsql](../../includes/tsql-md.md)] DELETE statement.</span></span>  
  
 <span data-ttu-id="c868c-130">Nell'esempio seguente viene descritta l'eliminazione di una riga e dei file del file system associati.</span><span class="sxs-lookup"><span data-stu-id="c868c-130">The following example shows how to delete a row and its associated file system files.</span></span>  
  
 [!code-sql[FILESTREAM#FS_DeleteData](../../snippets/tsql/SQL15/tsql/filestream/transact-sql/filestream.sql#fs_deletedata)]  
  
 <span data-ttu-id="c868c-131">Se si selezionano tutti i dati della tabella `dbo.Archive` , si nota che la riga non è più presente.</span><span class="sxs-lookup"><span data-stu-id="c868c-131">When you select all data from the `dbo.Archive` table, the row is gone.</span></span> <span data-ttu-id="c868c-132">Non è più possibile utilizzare il file associato.</span><span class="sxs-lookup"><span data-stu-id="c868c-132">You can no longer use the associated file.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c868c-133">I file sottostanti vengono rimossi dal Garbage Collector di FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="c868c-133">The underlying files are removed by the FILESTREAM garbage collector.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c868c-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c868c-134">See Also</span></span>  
 <span data-ttu-id="c868c-135">[Abilitare e configurare FILESTREAM](enable-and-configure-filestream.md) </span><span class="sxs-lookup"><span data-stu-id="c868c-135">[Enable and Configure FILESTREAM](enable-and-configure-filestream.md) </span></span>  
 [<span data-ttu-id="c868c-136">Evitare conflitti con le operazioni del database nelle applicazioni di FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="c868c-136">Avoid Conflicts with Database Operations in FILESTREAM Applications</span></span>](avoid-conflicts-with-database-operations-in-filestream-applications.md)  
  
  
