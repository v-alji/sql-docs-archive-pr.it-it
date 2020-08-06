---
title: Preparare ed eseguire un'istruzione (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- statement execution
- statement preparation
ms.assetid: 0adecc63-4da5-486c-bc48-09a004a2fae6
author: rothja
ms.author: jroth
ms.openlocfilehash: 607d8ad1509eca1204f6d029842b04120d3f5d9a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723811"
---
# <a name="prepare-and-execute-a-statement-odbc"></a><span data-ttu-id="108dc-102">Preparare ed eseguire un'istruzione (ODBC)</span><span class="sxs-lookup"><span data-stu-id="108dc-102">Prepare and Execute a Statement (ODBC)</span></span>
    
### <a name="to-prepare-a-statement-once-and-then-execute-it-multiple-times"></a><span data-ttu-id="108dc-103">Per preparare un'istruzione da eseguire più volte</span><span class="sxs-lookup"><span data-stu-id="108dc-103">To prepare a statement once, and then execute it multiple times</span></span>  
  
1.  <span data-ttu-id="108dc-104">Chiamare la [funzione SQLPrepare](https://go.microsoft.com/fwlink/?LinkId=59360) per preparare l'istruzione.</span><span class="sxs-lookup"><span data-stu-id="108dc-104">Call [SQLPrepare Function](https://go.microsoft.com/fwlink/?LinkId=59360) to prepare the statement.</span></span>  
  
2.  <span data-ttu-id="108dc-105">Facoltativamente, chiamare [SQLNumParams](https://go.microsoft.com/fwlink/?LinkId=58404) per determinare il numero di parametri nell'istruzione preparata.</span><span class="sxs-lookup"><span data-stu-id="108dc-105">Optionally, call [SQLNumParams](https://go.microsoft.com/fwlink/?LinkId=58404) to determine the number of parameters in the prepared statement.</span></span>  
  
3.  <span data-ttu-id="108dc-106">Per ogni parametro dell'istruzione preparata è possibile:</span><span class="sxs-lookup"><span data-stu-id="108dc-106">Optionally, for each parameter in the prepared statement:</span></span>  
  
    -   <span data-ttu-id="108dc-107">Chiamare [SQLDescribeParam](../../native-client-odbc-api/sqldescribeparam.md) per ottenere informazioni sui parametri.</span><span class="sxs-lookup"><span data-stu-id="108dc-107">Call [SQLDescribeParam](../../native-client-odbc-api/sqldescribeparam.md) to get parameter information.</span></span>  
  
    -   <span data-ttu-id="108dc-108">Associare ogni parametro a una variabile di programma usando [SQLBindParameter](../../native-client-odbc-api/sqlbindparameter.md).</span><span class="sxs-lookup"><span data-stu-id="108dc-108">Bind each parameter to a program variable by using [SQLBindParameter](../../native-client-odbc-api/sqlbindparameter.md).</span></span> <span data-ttu-id="108dc-109">Configurare i parametri data-at-execution.</span><span class="sxs-lookup"><span data-stu-id="108dc-109">Set up any data-at-execution parameters.</span></span>  
  
4.  <span data-ttu-id="108dc-110">Per ogni esecuzione di un'istruzione preparata:</span><span class="sxs-lookup"><span data-stu-id="108dc-110">For each execution of a prepared statement:</span></span>  
  
    -   <span data-ttu-id="108dc-111">Se nell'istruzione sono inclusi marcatori di parametro, inserire i valori dei dati nel buffer di parametri associato.</span><span class="sxs-lookup"><span data-stu-id="108dc-111">If the statement has parameter markers, put the data values into the bound parameter buffer.</span></span>  
  
    -   <span data-ttu-id="108dc-112">Chiamare [SQLExecute](https://go.microsoft.com/fwlink/?LinkId=58400) per eseguire l'istruzione preparata.</span><span class="sxs-lookup"><span data-stu-id="108dc-112">Call [SQLExecute](https://go.microsoft.com/fwlink/?LinkId=58400) to execute the prepared statement.</span></span>  
  
    -   <span data-ttu-id="108dc-113">Se vengono utilizzati parametri di input data-at-execution, [SQLExecute](https://go.microsoft.com/fwlink/?LinkId=58400) restituisce SQL_NEED_DATA.</span><span class="sxs-lookup"><span data-stu-id="108dc-113">If data-at-execution input parameters are used, [SQLExecute](https://go.microsoft.com/fwlink/?LinkId=58400) returns SQL_NEED_DATA.</span></span> <span data-ttu-id="108dc-114">Inviare i dati in blocchi usando [SQLParamData](https://go.microsoft.com/fwlink/?LinkId=58405) e [SQLPutData](../../native-client-odbc-api/sqlputdata.md).</span><span class="sxs-lookup"><span data-stu-id="108dc-114">Send the data in chunks by using [SQLParamData](https://go.microsoft.com/fwlink/?LinkId=58405) and [SQLPutData](../../native-client-odbc-api/sqlputdata.md).</span></span>  
  
### <a name="to-prepare-a-statement-with-column-wise-parameter-binding"></a><span data-ttu-id="108dc-115">Per preparare un'istruzione con associazione di parametri a livello di colonna</span><span class="sxs-lookup"><span data-stu-id="108dc-115">To prepare a statement with column-wise parameter binding</span></span>  
  
1.  <span data-ttu-id="108dc-116">Chiamare [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) per impostare gli attributi seguenti:</span><span class="sxs-lookup"><span data-stu-id="108dc-116">Call [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) to set the following attributes:</span></span>  
  
    -   <span data-ttu-id="108dc-117">Impostare SQL_ATTR_PARAMSET_SIZE sul numero di set (S) di parametri.</span><span class="sxs-lookup"><span data-stu-id="108dc-117">Set SQL_ATTR_PARAMSET_SIZE to the number of sets (S) of parameters.</span></span>  
  
    -   <span data-ttu-id="108dc-118">Impostare SQL_ATTR_PARAM_BIND_TYPE su SQL_PARAMETER_BIND_BY_COLUMN.</span><span class="sxs-lookup"><span data-stu-id="108dc-118">Set SQL_ATTR_PARAM_BIND_TYPE to SQL_PARAMETER_BIND_BY_COLUMN.</span></span>  
  
    -   <span data-ttu-id="108dc-119">Impostare l'attributo SQL_ATTR_PARAMS_PROCESSED_PTR in modo che punti a una variabile SQLUINTEGER che contenga il numero di parametri elaborati.</span><span class="sxs-lookup"><span data-stu-id="108dc-119">Set the SQL_ATTR_PARAMS_PROCESSED_PTR attribute to point to a SQLUINTEGER variable to hold the number of parameters processed.</span></span>  
  
    -   <span data-ttu-id="108dc-120">Impostare SQL_ATTR_PARAMS_STATUS_PTR in modo che punti a una matrice [S] di variabili SQLUSSMALLINT che contenga gli indicatori di stato dei parametri.</span><span class="sxs-lookup"><span data-stu-id="108dc-120">Set SQL_ATTR_PARAMS_STATUS_PTR to point to an array[S] of SQLUSSMALLINT variables to hold parameter status indicators.</span></span>  
  
2.  <span data-ttu-id="108dc-121">Chiamare SQLPrepare per preparare l'istruzione.</span><span class="sxs-lookup"><span data-stu-id="108dc-121">Call SQLPrepare to prepare the statement.</span></span>  
  
3.  <span data-ttu-id="108dc-122">Facoltativamente, chiamare [SQLNumParams](https://go.microsoft.com/fwlink/?LinkId=58404) per determinare il numero di parametri nell'istruzione preparata.</span><span class="sxs-lookup"><span data-stu-id="108dc-122">Optionally, call [SQLNumParams](https://go.microsoft.com/fwlink/?LinkId=58404) to determine the number of parameters in the prepared statement.</span></span>  
  
4.  <span data-ttu-id="108dc-123">Facoltativamente, per ogni parametro nell'istruzione preparata, chiamare SQLDescribeParam per ottenere informazioni sui parametri.</span><span class="sxs-lookup"><span data-stu-id="108dc-123">Optionally, for each parameter in the prepared statement, call SQLDescribeParam to get parameter information.</span></span>  
  
5.  <span data-ttu-id="108dc-124">Per ogni marcatore di parametro:</span><span class="sxs-lookup"><span data-stu-id="108dc-124">For each parameter marker:</span></span>  
  
    -   <span data-ttu-id="108dc-125">Allocare una matrice di buffer di S parametri per archiviare i valori dei dati.</span><span class="sxs-lookup"><span data-stu-id="108dc-125">Allocate an array of S parameter buffers to store data values.</span></span>  
  
    -   <span data-ttu-id="108dc-126">Allocare una matrice di buffer di S parametri per archiviare le lunghezze dei dati.</span><span class="sxs-lookup"><span data-stu-id="108dc-126">Allocate an array of S parameter buffers to store data lengths.</span></span>  
  
    -   <span data-ttu-id="108dc-127">Chiamare SQLBindParameter per associare il valore dei dati del parametro e le matrici di lunghezza dei dati al parametro dell'istruzione.</span><span class="sxs-lookup"><span data-stu-id="108dc-127">Call SQLBindParameter to bind the parameter data value and data length arrays to the statement parameter.</span></span>  
  
    -   <span data-ttu-id="108dc-128">Se il parametro è un testo data-at-execution o un parametro di immagine, configurarlo.</span><span class="sxs-lookup"><span data-stu-id="108dc-128">If the parameter is a data-at-execution text or image parameter, set it up.</span></span>  
  
    -   <span data-ttu-id="108dc-129">Se vengono utilizzati parametri data-at-execution, configurarli.</span><span class="sxs-lookup"><span data-stu-id="108dc-129">If any data-at-execution parameters are used, set them up.</span></span>  
  
6.  <span data-ttu-id="108dc-130">Per ogni esecuzione di un'istruzione preparata:</span><span class="sxs-lookup"><span data-stu-id="108dc-130">For each execution of a prepared statement:</span></span>  
  
    -   <span data-ttu-id="108dc-131">Inserire le S lunghezze e gli S valori di dati nelle matrici di parametri associate.</span><span class="sxs-lookup"><span data-stu-id="108dc-131">Put the S data values and S data lengths into the bound parameter arrays.</span></span>  
  
    -   <span data-ttu-id="108dc-132">Chiamare SQLExecute per eseguire l'istruzione preparata.</span><span class="sxs-lookup"><span data-stu-id="108dc-132">Call SQLExecute to execute the prepared statement.</span></span>  
  
    -   <span data-ttu-id="108dc-133">Se vengono utilizzati parametri di input data-at-execution, SQLExecute restituisce SQL_NEED_DATA.</span><span class="sxs-lookup"><span data-stu-id="108dc-133">If data-at-execution input parameters are used, SQLExecute returns SQL_NEED_DATA.</span></span> <span data-ttu-id="108dc-134">Inviare i dati in blocchi usando SQLParamData e SQLPutData.</span><span class="sxs-lookup"><span data-stu-id="108dc-134">Send the data in chunks by using SQLParamData and SQLPutData.</span></span>  
  
### <a name="to-prepare-a-statement-with-row-wise-bound-parameters"></a><span data-ttu-id="108dc-135">Per preparare un'istruzione con associazione di parametri a livello di riga</span><span class="sxs-lookup"><span data-stu-id="108dc-135">To prepare a statement with row-wise bound parameters</span></span>  
  
1.  <span data-ttu-id="108dc-136">Allocare una matrice [S] di strutture, dove S è il numero di set di parametri.</span><span class="sxs-lookup"><span data-stu-id="108dc-136">Allocate an array[S] of structures, where S is the number of sets of parameters.</span></span> <span data-ttu-id="108dc-137">Nella struttura è presente un elemento per ogni parametro e ogni elemento è costituito da due parti:</span><span class="sxs-lookup"><span data-stu-id="108dc-137">The structure has one element for each parameter, and each element has two parts:</span></span>  
  
    -   <span data-ttu-id="108dc-138">La prima parte è una variabile del tipo di dati appropriato che contiene i dati dei parametri.</span><span class="sxs-lookup"><span data-stu-id="108dc-138">The first part is a variable of the appropriate data type to hold the parameter data.</span></span>  
  
    -   <span data-ttu-id="108dc-139">La seconda parte è una variabile SQLINTEGER che deve contenere l'indicatore di stato.</span><span class="sxs-lookup"><span data-stu-id="108dc-139">The second part is a SQLINTEGER variable to hold the status indicator.</span></span>  
  
2.  <span data-ttu-id="108dc-140">Chiamare [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) per impostare gli attributi seguenti:</span><span class="sxs-lookup"><span data-stu-id="108dc-140">Call [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) to set the following attributes:</span></span>  
  
    -   <span data-ttu-id="108dc-141">Impostare SQL_ATTR_PARAMSET_SIZE sul numero di set (S) di parametri.</span><span class="sxs-lookup"><span data-stu-id="108dc-141">Set SQL_ATTR_PARAMSET_SIZE to the number of sets (S) of parameters.</span></span>  
  
    -   <span data-ttu-id="108dc-142">Impostare SQL_ATTR_PARAM_BIND_TYPE sulla dimensione della struttura allocata nel Passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="108dc-142">Set SQL_ATTR_PARAM_BIND_TYPE to the size of the structure allocated in Step 1.</span></span>  
  
    -   <span data-ttu-id="108dc-143">Impostare l'attributo SQL_ATTR_PARAMS_PROCESSED_PTR in modo che punti a una variabile SQLUINTEGER che contenga il numero di parametri elaborati.</span><span class="sxs-lookup"><span data-stu-id="108dc-143">Set the SQL_ATTR_PARAMS_PROCESSED_PTR attribute to point to a SQLUINTEGER variable to hold the number of parameters processed.</span></span>  
  
    -   <span data-ttu-id="108dc-144">Impostare SQL_ATTR_PARAMS_STATUS_PTR in modo che punti a una matrice [S] di variabili SQLUSSMALLINT che contenga gli indicatori di stato dei parametri.</span><span class="sxs-lookup"><span data-stu-id="108dc-144">Set SQL_ATTR_PARAMS_STATUS_PTR to point to an array[S] of SQLUSSMALLINT variables to hold parameter status indicators.</span></span>  
  
3.  <span data-ttu-id="108dc-145">Chiamare SQLPrepare per preparare l'istruzione.</span><span class="sxs-lookup"><span data-stu-id="108dc-145">Call SQLPrepare to prepare the statement.</span></span>  
  
4.  <span data-ttu-id="108dc-146">Per ogni marcatore di parametro, chiamare SQLBindParameter per puntare il valore dei dati del parametro e il puntatore alla lunghezza dei dati alle variabili nel primo elemento della matrice di strutture allocate nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="108dc-146">For each parameter marker, call SQLBindParameter to point the parameter data value and data length pointer to their variables in the first element of the array of structures allocated in Step 1.</span></span> <span data-ttu-id="108dc-147">Se il parametro è di tipo data-at-execution, configurarlo.</span><span class="sxs-lookup"><span data-stu-id="108dc-147">If the parameter is a data-at-execution parameter, set it up.</span></span>  
  
5.  <span data-ttu-id="108dc-148">Per ogni esecuzione di un'istruzione preparata:</span><span class="sxs-lookup"><span data-stu-id="108dc-148">For each execution of a prepared statement:</span></span>  
  
    -   <span data-ttu-id="108dc-149">Inserire i valori dei dati nella matrice di buffer dei parametri associati.</span><span class="sxs-lookup"><span data-stu-id="108dc-149">Fill the bound parameter buffer array with data values.</span></span>  
  
    -   <span data-ttu-id="108dc-150">Chiamare SQLExecute per eseguire l'istruzione preparata.</span><span class="sxs-lookup"><span data-stu-id="108dc-150">Call SQLExecute to execute the prepared statement.</span></span> <span data-ttu-id="108dc-151">Il driver esegue in modo efficace l'istruzione SQL S volte, una volta per ogni set di parametri.</span><span class="sxs-lookup"><span data-stu-id="108dc-151">The driver efficiently executes the SQL statement S times, once for each set of parameters.</span></span>  
  
    -   <span data-ttu-id="108dc-152">Se vengono utilizzati parametri di input data-at-execution, SQLExecute restituisce SQL_NEED_DATA.</span><span class="sxs-lookup"><span data-stu-id="108dc-152">If data-at-execution input parameters are used, SQLExecute returns SQL_NEED_DATA.</span></span> <span data-ttu-id="108dc-153">Inviare i dati in blocchi usando SQLParamData e SQLPutData.</span><span class="sxs-lookup"><span data-stu-id="108dc-153">Send the data in chunks by using SQLParamData and SQLPutData.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="108dc-154">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="108dc-154">See Also</span></span>  
 [<span data-ttu-id="108dc-155">Procedure relative all'esecuzione di query &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="108dc-155">Executing Queries How-to Topics &#40;ODBC&#41;</span></span>](executing-queries-how-to-topics-odbc.md)  
  
  
