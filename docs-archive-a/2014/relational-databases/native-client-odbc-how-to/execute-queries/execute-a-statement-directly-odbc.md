---
title: Eseguire un'istruzione direttamente (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- statement execution
ms.assetid: b690f9de-66e1-4ee5-ab6a-121346fb5f85
author: rothja
ms.author: jroth
ms.openlocfilehash: 2aeada906a925cff93455ffd92e7c17822a80124
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623226"
---
# <a name="execute-a-statement-directly-odbc"></a><span data-ttu-id="bfe7b-102">Eseguire un'istruzione direttamente (ODBC)</span><span class="sxs-lookup"><span data-stu-id="bfe7b-102">Execute a Statement Directly (ODBC)</span></span>
    
### <a name="to-execute-a-statement-directly-and-one-time-only"></a><span data-ttu-id="bfe7b-103">Per eseguire un'istruzione direttamente e solo una volta</span><span class="sxs-lookup"><span data-stu-id="bfe7b-103">To execute a statement directly and one time only</span></span>  
  
1.  <span data-ttu-id="bfe7b-104">Se l'istruzione include marcatori di parametro, usare [SQLBindParameter](../../native-client-odbc-api/sqlbindparameter.md) per associare ogni parametro a una variabile di programma.</span><span class="sxs-lookup"><span data-stu-id="bfe7b-104">If the statement has parameter markers, use [SQLBindParameter](../../native-client-odbc-api/sqlbindparameter.md) to bind each parameter to a program variable.</span></span> <span data-ttu-id="bfe7b-105">Inserire nelle variabili di programma i valori dei dati e quindi configurare tutti i parametri data-at-execution.</span><span class="sxs-lookup"><span data-stu-id="bfe7b-105">Fill the program variables with data values, and then set up any data-at-execution parameters.</span></span>  
  
2.  <span data-ttu-id="bfe7b-106">Chiamare [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) per eseguire l'istruzione.</span><span class="sxs-lookup"><span data-stu-id="bfe7b-106">Call [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) to execute the statement.</span></span>  
  
3.  <span data-ttu-id="bfe7b-107">Se vengono utilizzati parametri di input data-at-execution, [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) restituisce SQL_NEED_DATA.</span><span class="sxs-lookup"><span data-stu-id="bfe7b-107">If data-at-execution input parameters are used, [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) returns SQL_NEED_DATA.</span></span> <span data-ttu-id="bfe7b-108">Inviare i dati in blocchi usando [SQLParamData](https://go.microsoft.com/fwlink/?LinkId=58405) e [SQLPutData](../../native-client-odbc-api/sqlputdata.md).</span><span class="sxs-lookup"><span data-stu-id="bfe7b-108">Send the data in chunks by using [SQLParamData](https://go.microsoft.com/fwlink/?LinkId=58405) and [SQLPutData](../../native-client-odbc-api/sqlputdata.md).</span></span>  
  
### <a name="to-execute-a-statement-multiple-times-by-using-column-wise-parameter-binding"></a><span data-ttu-id="bfe7b-109">Per eseguire un'istruzione più volte utilizzando l'associazione di parametri per colonna</span><span class="sxs-lookup"><span data-stu-id="bfe7b-109">To execute a statement multiple times by using column-wise parameter binding</span></span>  
  
1.  <span data-ttu-id="bfe7b-110">Chiamare [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) per impostare gli attributi seguenti:</span><span class="sxs-lookup"><span data-stu-id="bfe7b-110">Call [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) to set the following attributes:</span></span>  
  
     <span data-ttu-id="bfe7b-111">Impostare SQL_ATTR_PARAMSET_SIZE sul numero di set (S) di parametri.</span><span class="sxs-lookup"><span data-stu-id="bfe7b-111">Set SQL_ATTR_PARAMSET_SIZE to the number of sets (S) of parameters.</span></span>  
  
     <span data-ttu-id="bfe7b-112">Impostare SQL_ATTR_PARAM_BIND_TYPE su SQL_PARAMETER_BIND_BY_COLUMN.</span><span class="sxs-lookup"><span data-stu-id="bfe7b-112">Set SQL_ATTR_PARAM_BIND_TYPE to SQL_PARAMETER_BIND_BY_COLUMN.</span></span>  
  
     <span data-ttu-id="bfe7b-113">Impostare l'attributo SQL_ATTR_PARAMS_PROCESSED_PTR in modo che punti a una variabile SQLUINTEGER che contenga il numero di parametri elaborati.</span><span class="sxs-lookup"><span data-stu-id="bfe7b-113">Set the SQL_ATTR_PARAMS_PROCESSED_PTR attribute to point to a SQLUINTEGER variable to hold the number of parameters processed.</span></span>  
  
     <span data-ttu-id="bfe7b-114">Impostare SQL_ATTR_PARAMS_STATUS_PTR in modo che punti a una matrice [S] di variabili SQLUSSMALLINT contenente gli indicatori di stato dei parametri.</span><span class="sxs-lookup"><span data-stu-id="bfe7b-114">Set SQL_ATTR_PARAMS_STATUS_PTR to point to an array[S] of SQLUSSMALLINT variables to hold the parameter status indicators.</span></span>  
  
2.  <span data-ttu-id="bfe7b-115">Per ogni marcatore di parametro:</span><span class="sxs-lookup"><span data-stu-id="bfe7b-115">For each parameter marker:</span></span>  
  
     <span data-ttu-id="bfe7b-116">Allocare una matrice di buffer di S parametri per archiviare i valori dei dati.</span><span class="sxs-lookup"><span data-stu-id="bfe7b-116">Allocate an array of S parameter buffers to store data values.</span></span>  
  
     <span data-ttu-id="bfe7b-117">Allocare una matrice di buffer di S parametri per archiviare le lunghezze dei dati.</span><span class="sxs-lookup"><span data-stu-id="bfe7b-117">Allocate an array of S parameter buffers to store data lengths.</span></span>  
  
     <span data-ttu-id="bfe7b-118">Chiamare [SQLBindParameter](../../native-client-odbc-api/sqlbindparameter.md) per associare il valore dei dati del parametro e le matrici di lunghezza dei dati al parametro dell'istruzione.</span><span class="sxs-lookup"><span data-stu-id="bfe7b-118">Call [SQLBindParameter](../../native-client-odbc-api/sqlbindparameter.md) to bind the parameter data value and data length arrays to the statement parameter.</span></span>  
  
     <span data-ttu-id="bfe7b-119">Configurare tutti i parametri data-at-execution di tipo text o image.</span><span class="sxs-lookup"><span data-stu-id="bfe7b-119">Set up any data-at-execution text or image parameters.</span></span>  
  
     <span data-ttu-id="bfe7b-120">Inserire S valori dei dati e S lunghezze dei dati nella matrice di parametri associati.</span><span class="sxs-lookup"><span data-stu-id="bfe7b-120">Put S data values and S data lengths into the bound parameter arrays.</span></span>  
  
3.  <span data-ttu-id="bfe7b-121">Chiamare [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) per eseguire l'istruzione.</span><span class="sxs-lookup"><span data-stu-id="bfe7b-121">Call [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) to execute the statement.</span></span> <span data-ttu-id="bfe7b-122">Il driver esegue in modo efficace l'istruzione S volte, una volta per ogni set di parametri.</span><span class="sxs-lookup"><span data-stu-id="bfe7b-122">The driver efficiently executes the statement S times, once for each set of parameters.</span></span>  
  
4.  <span data-ttu-id="bfe7b-123">Se vengono utilizzati parametri di input data-at-execution, [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) restituisce SQL_NEED_DATA.</span><span class="sxs-lookup"><span data-stu-id="bfe7b-123">If data-at-execution input parameters are used, [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) returns SQL_NEED_DATA.</span></span> <span data-ttu-id="bfe7b-124">Inviare i dati in blocchi usando [SQLParamData](https://go.microsoft.com/fwlink/?LinkId=58405) e [SQLPutData](../../native-client-odbc-api/sqlputdata.md).</span><span class="sxs-lookup"><span data-stu-id="bfe7b-124">Send the data in chunks by using [SQLParamData](https://go.microsoft.com/fwlink/?LinkId=58405) and [SQLPutData](../../native-client-odbc-api/sqlputdata.md).</span></span>  
  
### <a name="to-execute-a-statement-multiple-times-by-using-row-wise-parameter-binding"></a><span data-ttu-id="bfe7b-125">Per eseguire un'istruzione più volte utilizzando l'associazione di parametri per riga</span><span class="sxs-lookup"><span data-stu-id="bfe7b-125">To execute a statement multiple times by using row-wise parameter binding</span></span>  
  
1.  <span data-ttu-id="bfe7b-126">Allocare una matrice [S] di strutture, dove S è il numero di set di parametri.</span><span class="sxs-lookup"><span data-stu-id="bfe7b-126">Allocate an array[S] of structures, where S is the number of sets of parameters.</span></span> <span data-ttu-id="bfe7b-127">Nella struttura è presente un elemento per ogni parametro e ogni elemento è costituito da due parti:</span><span class="sxs-lookup"><span data-stu-id="bfe7b-127">The structure has one element for each parameter, and each element has two parts:</span></span>  
  
     <span data-ttu-id="bfe7b-128">La prima parte è una variabile del tipo di dati appropriato che contiene i dati dei parametri.</span><span class="sxs-lookup"><span data-stu-id="bfe7b-128">The first part is a variable of the appropriate data type to hold the parameter data.</span></span>  
  
     <span data-ttu-id="bfe7b-129">La seconda parte è una variabile SQLINTEGER che deve contenere l'indicatore di stato.</span><span class="sxs-lookup"><span data-stu-id="bfe7b-129">The second part is a SQLINTEGER variable to hold the status indicator.</span></span>  
  
2.  <span data-ttu-id="bfe7b-130">Chiamare [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) per impostare gli attributi seguenti:</span><span class="sxs-lookup"><span data-stu-id="bfe7b-130">Call [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) to set the following attributes:</span></span>  
  
     <span data-ttu-id="bfe7b-131">Impostare SQL_ATTR_PARAMSET_SIZE sul numero di set (S) di parametri.</span><span class="sxs-lookup"><span data-stu-id="bfe7b-131">Set SQL_ATTR_PARAMSET_SIZE to the number of sets (S) of parameters.</span></span>  
  
     <span data-ttu-id="bfe7b-132">Impostare SQL_ATTR_PARAM_BIND_TYPE sulla dimensione della struttura allocata nel Passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="bfe7b-132">Set SQL_ATTR_PARAM_BIND_TYPE to the size of the structure allocated in Step 1.</span></span>  
  
     <span data-ttu-id="bfe7b-133">Impostare l'attributo SQL_ATTR_PARAMS_PROCESSED_PTR in modo che punti a una variabile SQLUINTEGER che contenga il numero di parametri elaborati.</span><span class="sxs-lookup"><span data-stu-id="bfe7b-133">Set the SQL_ATTR_PARAMS_PROCESSED_PTR attribute to point to a SQLUINTEGER variable to hold the number of parameters processed.</span></span>  
  
     <span data-ttu-id="bfe7b-134">Impostare SQL_ATTR_PARAMS_STATUS_PTR in modo che punti a una matrice [S] di variabili SQLUSSMALLINT contenente gli indicatori di stato dei parametri.</span><span class="sxs-lookup"><span data-stu-id="bfe7b-134">Set SQL_ATTR_PARAMS_STATUS_PTR to point to an array[S] of SQLUSSMALLINT variables to hold the parameter status indicators.</span></span>  
  
3.  <span data-ttu-id="bfe7b-135">Per ogni marcatore di parametro, chiamare [SQLBindParameter](../../native-client-odbc-api/sqlbindparameter.md) per puntare il valore dei dati del parametro e il puntatore alla lunghezza dei dati alle variabili nel primo elemento della matrice di strutture allocate nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="bfe7b-135">For each parameter marker, call [SQLBindParameter](../../native-client-odbc-api/sqlbindparameter.md) to point the parameter's data value and data length pointer to their variables in the first element of the array of structures allocated in Step 1.</span></span> <span data-ttu-id="bfe7b-136">Se il parametro è di tipo data-at-execution, configurarlo.</span><span class="sxs-lookup"><span data-stu-id="bfe7b-136">If the parameter is a data-at-execution parameter, set it up.</span></span>  
  
4.  <span data-ttu-id="bfe7b-137">Inserire i valori dei dati nella matrice di buffer dei parametri associati.</span><span class="sxs-lookup"><span data-stu-id="bfe7b-137">Fill the bound parameter buffer array with data values.</span></span>  
  
5.  <span data-ttu-id="bfe7b-138">Chiamare [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) per eseguire l'istruzione.</span><span class="sxs-lookup"><span data-stu-id="bfe7b-138">Call [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) to execute the statement.</span></span> <span data-ttu-id="bfe7b-139">Il driver esegue in modo efficace l'istruzione S volte, una volta per ogni set di parametri.</span><span class="sxs-lookup"><span data-stu-id="bfe7b-139">The driver efficiently executes the statement S times, once for each set of parameters.</span></span>  
  
6.  <span data-ttu-id="bfe7b-140">Se vengono utilizzati parametri di input data-at-execution, [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) restituisce SQL_NEED_DATA.</span><span class="sxs-lookup"><span data-stu-id="bfe7b-140">If data-at-execution input parameters are used, [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) returns SQL_NEED_DATA.</span></span> <span data-ttu-id="bfe7b-141">Inviare i dati in blocchi usando [SQLParamData](https://go.microsoft.com/fwlink/?LinkId=58405) e [SQLPutData](../../native-client-odbc-api/sqlputdata.md).</span><span class="sxs-lookup"><span data-stu-id="bfe7b-141">Send the data in chunks by using [SQLParamData](https://go.microsoft.com/fwlink/?LinkId=58405) and [SQLPutData](../../native-client-odbc-api/sqlputdata.md).</span></span>  
  
 <span data-ttu-id="bfe7b-142">**Nota** Le associazioni a livello di colonna e di riga vengono in genere utilizzate in combinazione con la [funzione SQLPrepare](https://go.microsoft.com/fwlink/?LinkId=59360) e [SQLExecute](https://go.microsoft.com/fwlink/?LinkId=58400) anziché con [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399).</span><span class="sxs-lookup"><span data-stu-id="bfe7b-142">**Note** Column-wise and row-wise binding are more typically used in conjunction with [SQLPrepare Function](https://go.microsoft.com/fwlink/?LinkId=59360) and [SQLExecute](https://go.microsoft.com/fwlink/?LinkId=58400) than with [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfe7b-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bfe7b-143">See Also</span></span>  
 [<span data-ttu-id="bfe7b-144">Procedure relative all'esecuzione di query &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="bfe7b-144">Executing Queries How-to Topics &#40;ODBC&#41;</span></span>](executing-queries-how-to-topics-odbc.md)  
  
  
