---
title: Evitare conflitti con le operazioni del database nelle applicazioni di FILESTREAM | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.technology: filestream
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- FILESTREAM [SQL Server], Win32 and Transact-SQL Conflicts
ms.assetid: 8b1ee196-69af-4f9b-9bf5-63d8ac2bc39b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 0ac7e681766396d3a3b4412d91a968b4cdc653c4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636240"
---
# <a name="avoid-conflicts-with-database-operations-in-filestream-applications"></a><span data-ttu-id="1aa93-102">Evitare conflitti con le operazioni del database nelle applicazioni di FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="1aa93-102">Avoid Conflicts with Database Operations in FILESTREAM Applications</span></span>
  <span data-ttu-id="1aa93-103">Le applicazioni che usano SqlOpenFilestream() per aprire gli handle di file Win32 per la lettura o la scrittura di dati BLOB FILESTREAM possono entrare in conflitto con le istruzioni [!INCLUDE[tsql](../../includes/tsql-md.md)] gestite in una transazione comune.</span><span class="sxs-lookup"><span data-stu-id="1aa93-103">Applications that use SqlOpenFilestream() to open Win32 file handles for reading or writing FILESTREAM BLOB data can encounter conflict errors with [!INCLUDE[tsql](../../includes/tsql-md.md)] statements that are managed in a common transaction.</span></span> <span data-ttu-id="1aa93-104">Sono incluse le query [!INCLUDE[tsql](../../includes/tsql-md.md)] o MARS la cui esecuzione richiede molto tempo.</span><span class="sxs-lookup"><span data-stu-id="1aa93-104">This includes [!INCLUDE[tsql](../../includes/tsql-md.md)] or MARS queries that take a long time to finish execution.</span></span> <span data-ttu-id="1aa93-105">È necessario progettare con attenzione le applicazioni per evitare questi tipi di conflitti.</span><span class="sxs-lookup"><span data-stu-id="1aa93-105">Applications must be carefully designed to help avoid these types of conflicts.</span></span>  
  
 <span data-ttu-id="1aa93-106">Quando il [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] o le applicazioni provano ad aprire dati BLOB FILESTREAM, il [!INCLUDE[ssDE](../../includes/ssde-md.md)] controlla il contesto di transazione associato.</span><span class="sxs-lookup"><span data-stu-id="1aa93-106">When [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] or applications try to open FILESTREAM BLOBs, the [!INCLUDE[ssDE](../../includes/ssde-md.md)] checks the associated transaction context.</span></span> <span data-ttu-id="1aa93-107">Il [!INCLUDE[ssDE](../../includes/ssde-md.md)] consente o nega la richiesta a seconda che l'operazione di apertura funzioni o meno con le istruzioni DDL, le istruzioni DML, il recupero dei dati o la gestione delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="1aa93-107">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] allows or denies the request based on whether the open operation is working with DDL statements, DML statements, retrieving data, or managing transactions.</span></span> <span data-ttu-id="1aa93-108">Nella tabella seguente viene illustrato il modo in cui il [!INCLUDE[ssDE](../../includes/ssde-md.md)] determina se un 'istruzione [!INCLUDE[tsql](../../includes/tsql-md.md)] verrà consentita o negata in base al tipo di file aperti nella transazione.</span><span class="sxs-lookup"><span data-stu-id="1aa93-108">The following table shows how the [!INCLUDE[ssDE](../../includes/ssde-md.md)] determines whether a [!INCLUDE[tsql](../../includes/tsql-md.md)] statement will be allowed or denied based on the type of files that are open in the transaction.</span></span>  
  
|<span data-ttu-id="1aa93-109">istruzioni Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1aa93-109">Transact-SQL statements</span></span>|<span data-ttu-id="1aa93-110">Aperte per l'accesso in lettura</span><span class="sxs-lookup"><span data-stu-id="1aa93-110">Opened for read</span></span>|<span data-ttu-id="1aa93-111">Aperte per l'accesso in scrittura</span><span class="sxs-lookup"><span data-stu-id="1aa93-111">Opened for write</span></span>|  
|------------------------------|---------------------|----------------------|  
|<span data-ttu-id="1aa93-112">Istruzioni DDL che funzionano con i metadati del database, ad esempio CREATE TABLE, CREATE INDEX, DROP TABLE e ALTER TABLE.</span><span class="sxs-lookup"><span data-stu-id="1aa93-112">DDL statements that work with database metadata, such as CREATE TABLE, CREATE INDEX, DROP TABLE, and ALTER TABLE.</span></span>|<span data-ttu-id="1aa93-113">Consentito</span><span class="sxs-lookup"><span data-stu-id="1aa93-113">Allowed</span></span>|<span data-ttu-id="1aa93-114">Bloccate ed errore di timeout.</span><span class="sxs-lookup"><span data-stu-id="1aa93-114">Are blocked and fail with a time-out.</span></span>|  
|<span data-ttu-id="1aa93-115">Istruzioni DML che funzionano con i dati archiviati nel database, ad esempio UPDATE, DELETE e INSERT.</span><span class="sxs-lookup"><span data-stu-id="1aa93-115">DML statements that work with the data that is stored in the database, such as UPDATE, DELETE, and INSERT.</span></span>|<span data-ttu-id="1aa93-116">Consentito</span><span class="sxs-lookup"><span data-stu-id="1aa93-116">Allowed</span></span>|<span data-ttu-id="1aa93-117">Negate</span><span class="sxs-lookup"><span data-stu-id="1aa93-117">Denied</span></span>|  
|<span data-ttu-id="1aa93-118">SELECT</span><span class="sxs-lookup"><span data-stu-id="1aa93-118">SELECT</span></span>|<span data-ttu-id="1aa93-119">Consentito</span><span class="sxs-lookup"><span data-stu-id="1aa93-119">Allowed</span></span>|<span data-ttu-id="1aa93-120">Consentito</span><span class="sxs-lookup"><span data-stu-id="1aa93-120">Allowed</span></span>|  
|<span data-ttu-id="1aa93-121">COMMIT TRANSACTION</span><span class="sxs-lookup"><span data-stu-id="1aa93-121">COMMIT TRANSACTION</span></span>|<span data-ttu-id="1aa93-122">Negate\*</span><span class="sxs-lookup"><span data-stu-id="1aa93-122">Denied\*</span></span>|<span data-ttu-id="1aa93-123">Negate\*</span><span class="sxs-lookup"><span data-stu-id="1aa93-123">Denied\*.</span></span>|  
|<span data-ttu-id="1aa93-124">SAVE TRANSACTION</span><span class="sxs-lookup"><span data-stu-id="1aa93-124">SAVE TRANSACTION</span></span>|<span data-ttu-id="1aa93-125">Negate\*</span><span class="sxs-lookup"><span data-stu-id="1aa93-125">Denied\*</span></span>|<span data-ttu-id="1aa93-126">Negate\*</span><span class="sxs-lookup"><span data-stu-id="1aa93-126">Denied\*</span></span>|  
|<span data-ttu-id="1aa93-127">ROLLBACK</span><span class="sxs-lookup"><span data-stu-id="1aa93-127">ROLLBACK</span></span>|<span data-ttu-id="1aa93-128">Consentite\*</span><span class="sxs-lookup"><span data-stu-id="1aa93-128">Allowed\*</span></span>|<span data-ttu-id="1aa93-129">Consentite\*</span><span class="sxs-lookup"><span data-stu-id="1aa93-129">Allowed\*</span></span>|  
  
 <span data-ttu-id="1aa93-130">\* La transazione viene annullata e gli handle aperti per il contesto di transazione vengono invalidati.</span><span class="sxs-lookup"><span data-stu-id="1aa93-130">\* The transaction is canceled, and open handles for the transaction context are invalidated.</span></span> <span data-ttu-id="1aa93-131">L'applicazione deve chiudere tutti gli handle aperti.</span><span class="sxs-lookup"><span data-stu-id="1aa93-131">The application must close all open handles.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="1aa93-132">Esempi</span><span class="sxs-lookup"><span data-stu-id="1aa93-132">Examples</span></span>  
 <span data-ttu-id="1aa93-133">Gli esempi seguenti illustrano come le istruzioni [!INCLUDE[tsql](../../includes/tsql-md.md)] e l'accesso Win32 FILESTREAM possano creare conflitti.</span><span class="sxs-lookup"><span data-stu-id="1aa93-133">The following examples show how [!INCLUDE[tsql](../../includes/tsql-md.md)] statements and FILESTREAM Win32 access can cause conflicts.</span></span>  
  
### <a name="a-opening-a-filestream-blob-for-write-access"></a><span data-ttu-id="1aa93-134">R.</span><span class="sxs-lookup"><span data-stu-id="1aa93-134">A.</span></span> <span data-ttu-id="1aa93-135">Apertura di dati BLOB FILESTREAM per l'accesso in scrittura</span><span class="sxs-lookup"><span data-stu-id="1aa93-135">Opening a FILESTREAM BLOB for write access</span></span>  
 <span data-ttu-id="1aa93-136">Nell'esempio seguente viene mostrato l'effetto dell'apertura di un file per il solo accesso in scrittura.</span><span class="sxs-lookup"><span data-stu-id="1aa93-136">The following example shows the effect of opening a file for write access only.</span></span>  
  
```  
dstHandle =  OpenSqlFilestream(dstFilePath, Write, 0,  
    transactionToken, cbTransactionToken, 0);  
  
//Write some date to the FILESTREAM BLOB.  
WriteFile(dstHandle, updateData, ...);  
  
//DDL statements will be denied.  
//DML statements will be denied.  
//SELECT statements will be allowed. The FILESTREAM BLOB is  
//returned without the modifications that are made by  
//WriteFile(dstHandle, updateData, ...).  
CloseHandle(dstHandle);  
  
//DDL statements will be allowed.  
//DML statements will be allowed.  
//SELECT statements will be allowed. The FILESTREAM BLOB  
//is returned with the updateData applied.  
```  
  
### <a name="b-opening-a-filestream-blob-for-read-access"></a><span data-ttu-id="1aa93-137">B.</span><span class="sxs-lookup"><span data-stu-id="1aa93-137">B.</span></span> <span data-ttu-id="1aa93-138">Apertura di dati BLOB FILESTREAM per l'accesso in lettura</span><span class="sxs-lookup"><span data-stu-id="1aa93-138">Opening a FILESTREAM BLOB for read access</span></span>  
 <span data-ttu-id="1aa93-139">Nell'esempio seguente viene mostrato l'effetto dell'apertura di un file per il solo accesso in lettura.</span><span class="sxs-lookup"><span data-stu-id="1aa93-139">The following example shows the effect of opening a file for read access only.</span></span>  
  
```  
dstHandle =  OpenSqlFilestream(dstFilePath, Read, 0,  
    transactionToken, cbTransactionToken, 0);  
//DDL statements will be denied.  
//DML statements will be allowed. Any changes that are  
//made to the FILESTREAM BLOB will not be returned until  
//the dstHandle is closed.  
//SELECT statements will be allowed.  
CloseHandle(dstHandle);  
  
//DDL statements will be allowed.  
//DML statements will be allowed.  
//SELECT statements will be allowed.  
```  
  
### <a name="c-opening-and-closing-multiple-filestream-blob-files"></a><span data-ttu-id="1aa93-140">C.</span><span class="sxs-lookup"><span data-stu-id="1aa93-140">C.</span></span> <span data-ttu-id="1aa93-141">Apertura e chiusura di più file BLOB FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="1aa93-141">Opening and closing multiple FILESTREAM BLOB files</span></span>  
 <span data-ttu-id="1aa93-142">Se sono aperti più file, viene utilizzata la regola più restrittiva.</span><span class="sxs-lookup"><span data-stu-id="1aa93-142">If multiple files are open, the most restrictive rule is used.</span></span> <span data-ttu-id="1aa93-143">Nell'esempio seguente vengono aperti due file.</span><span class="sxs-lookup"><span data-stu-id="1aa93-143">The following example opens two files.</span></span> <span data-ttu-id="1aa93-144">Il primo file è aperto in lettura, il secondo in scrittura.</span><span class="sxs-lookup"><span data-stu-id="1aa93-144">The first file is opened for read and the second for write.</span></span> <span data-ttu-id="1aa93-145">Le istruzioni DML rimarranno negate finché non viene aperto il secondo file.</span><span class="sxs-lookup"><span data-stu-id="1aa93-145">DML statements will be denied until the second file is opened.</span></span>  
  
```  
dstHandle =  OpenSqlFilestream(dstFilePath, Read, 0,  
    transactionToken, cbTransactionToken, 0);  
//DDL statements will be denied.  
//DML statements will be allowed.  
//SELECT statements will be allowed.  
  
dstHandle1 =  OpenSqlFilestream(dstFilePath1, Write, 0,  
    transactionToken, cbTransactionToken, 0);  
  
//DDL statements will be denied.  
//DML statements will be denied.  
//SELECT statements will be allowed.  
  
//Close the read handle. The write handle is still open.  
CloseHandle(dstHandle);  
//DML statements are still denied because the write handle is open.  
  
//DDL statements will be denied.  
//DML statements will be denied.  
//SELECT statements will be allowed.  
  
CloseHandle(dstHandle1);  
//DDL statements will be allowed.  
//DML statements will be allowed.  
//SELECT statements will be allowed.  
```  
  
### <a name="d-failing-to-close-a-cursor"></a><span data-ttu-id="1aa93-146">D.</span><span class="sxs-lookup"><span data-stu-id="1aa93-146">D.</span></span> <span data-ttu-id="1aa93-147">Chiusura non riuscita di un cursore</span><span class="sxs-lookup"><span data-stu-id="1aa93-147">Failing to close a cursor</span></span>  
 <span data-ttu-id="1aa93-148">Nell'esempio seguente viene illustrato come un cursore dell'istruzione non chiuso possa impedire a `OpenSqlFilestream()` di aprire i dati BLOB per l'accesso in scrittura.</span><span class="sxs-lookup"><span data-stu-id="1aa93-148">The following example shows how a statement cursor that is not closed can prevent `OpenSqlFilestream()` from opening the BLOB for write access.</span></span>  
  
```  
TCHAR *sqlDBQuery =  
TEXT("SELECT GET_FILESTREAM_TRANSACTION_CONTEXT(),")  
TEXT("Chart.PathName() FROM Archive.dbo.Records");  
  
//Execute a long-running Transact-SQL statement. Do not allow  
//the statement to complete before trying to  
//open the file.  
  
SQLExecDirect(hstmt, sqlDBQuery, SQL_NTS);  
  
//Before you call OpenSqlFilestream() any open files  
//that the Cursor the Transact-SQL statement is using  
// must be closed. In this example,  
//SQLCloseCursor(hstmt) is not called so that  
//the transaction will indicate that there is a file  
//open for reading. This will cause the call to  
//OpenSqlFilestream() to fail because the file is  
//still open.  
  
HANDLE srcHandle =  OpenSqlFilestream(srcFilePath,  
     Write, 0,  transactionToken,  cbTransactionToken,  0);  
  
//srcHandle will == INVALID_HANDLE_VALUE because the  
//cursor is still open.  
```  
  
## <a name="see-also"></a><span data-ttu-id="1aa93-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1aa93-149">See Also</span></span>  
 <span data-ttu-id="1aa93-150">[Accesso ai dati FILESTREAM con OpenSqlFilestream](access-filestream-data-with-opensqlfilestream.md) </span><span class="sxs-lookup"><span data-stu-id="1aa93-150">[Access FILESTREAM Data with OpenSqlFilestream](access-filestream-data-with-opensqlfilestream.md) </span></span>  
 [<span data-ttu-id="1aa93-151">Uso di MARS &#40;Multiple Active Result Set&#41;</span><span class="sxs-lookup"><span data-stu-id="1aa93-151">Using Multiple Active Result Sets &#40;MARS&#41;</span></span>](../native-client/features/using-multiple-active-result-sets-mars.md)  
  
  
