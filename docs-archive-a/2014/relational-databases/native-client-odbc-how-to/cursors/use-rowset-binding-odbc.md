---
title: Usare l'associazione di set di righe (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- rowset binding [ODBC]
ms.assetid: a7be05f0-6b11-4b53-9fbc-501e591eef09
author: rothja
ms.author: jroth
ms.openlocfilehash: e2e0671fd1140e72005cd1a7532ea581f077382f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623230"
---
# <a name="use-rowset-binding-odbc"></a><span data-ttu-id="c3b10-102">Utilizzare l'associazione di set di righe (ODBC)</span><span class="sxs-lookup"><span data-stu-id="c3b10-102">Use Rowset Binding (ODBC)</span></span>
    
### <a name="to-use-column-wise-binding"></a><span data-ttu-id="c3b10-103">Per utilizzare l'associazione per colonna</span><span class="sxs-lookup"><span data-stu-id="c3b10-103">To use column-wise binding</span></span>  
  
1.  <span data-ttu-id="c3b10-104">Per ogni colonna associata, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c3b10-104">For each bound column, do the following:</span></span>  
  
    -   <span data-ttu-id="c3b10-105">Allocare una matrice di R (o più) buffer di colonna per archiviare i valori dei dati, dove R è il numero di righe del set di righe.</span><span class="sxs-lookup"><span data-stu-id="c3b10-105">Allocate an array of R (or more) column buffers to store data values, where R is number of rows in the rowset.</span></span>  
  
    -   <span data-ttu-id="c3b10-106">Facoltativamente, allocare una matrice di R (o più) buffer di colonna per archiviare le lunghezze dei dati.</span><span class="sxs-lookup"><span data-stu-id="c3b10-106">Optionally, allocate an array of R (or more) column buffers to store data lengths.</span></span>  
  
    -   <span data-ttu-id="c3b10-107">Chiamare [SQLBindCol](../../native-client-odbc-api/sqlbindcol.md) per associare il valore dei dati e le matrici di lunghezza dei dati della colonna alla colonna del set di righe.</span><span class="sxs-lookup"><span data-stu-id="c3b10-107">Call [SQLBindCol](../../native-client-odbc-api/sqlbindcol.md) to bind the column's data value and data length arrays to the column of the rowset.</span></span>  
  
2.  <span data-ttu-id="c3b10-108">Chiamare [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) per impostare gli attributi seguenti:</span><span class="sxs-lookup"><span data-stu-id="c3b10-108">Call [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) to set the following attributes:</span></span>  
  
    -   <span data-ttu-id="c3b10-109">Impostare SQL_ATTR_ROW_ARRAY_SIZE sul numero di righe nel set di righe (R).</span><span class="sxs-lookup"><span data-stu-id="c3b10-109">Set SQL_ATTR_ROW_ARRAY_SIZE to the number of rows in the rowset (R).</span></span>  
  
    -   <span data-ttu-id="c3b10-110">Impostare SQL_ATTR_ROW_BIND_TYPE su SQL_BIND_BY_COLUMN.</span><span class="sxs-lookup"><span data-stu-id="c3b10-110">Set SQL_ATTR_ROW_BIND_TYPE to SQL_BIND_BY_COLUMN.</span></span>  
  
    -   <span data-ttu-id="c3b10-111">Impostare l'attributo SQL_ATTR_ROWS FETCHED_PTR affinché punti a una variabile SQLUINTEGER per mantenere il numero di righe recuperate.</span><span class="sxs-lookup"><span data-stu-id="c3b10-111">Set the SQL_ATTR_ROWS FETCHED_PTR attribute to point to a SQLUINTEGER variable to hold the number of rows fetched.</span></span>  
  
    -   <span data-ttu-id="c3b10-112">Impostare SQL_ATTR_ROW_STATUS_PTR affinché punti a una matrice [R] di variabili SQLUSSMALLINT per mantenere gli indicatori di stato della riga.</span><span class="sxs-lookup"><span data-stu-id="c3b10-112">Set SQL_ATTR_ROW_STATUS_PTR to point to an array[R] of SQLUSSMALLINT variables to hold the row-status indicators.</span></span>  
  
3.  <span data-ttu-id="c3b10-113">Eseguire l'istruzione.</span><span class="sxs-lookup"><span data-stu-id="c3b10-113">Execute the statement.</span></span>  
  
4.  <span data-ttu-id="c3b10-114">Ogni chiamata a [SQLFetch](https://go.microsoft.com/fwlink/?LinkId=58401) o [SQLFetchScroll](../../native-client-odbc-api/sqlfetchscroll.md) recupera le righe R e trasferisce i dati nelle colonne delimitate.</span><span class="sxs-lookup"><span data-stu-id="c3b10-114">Each call to [SQLFetch](https://go.microsoft.com/fwlink/?LinkId=58401) or [SQLFetchScroll](../../native-client-odbc-api/sqlfetchscroll.md) retrieves R rows and transfers the data into the bound columns.</span></span>  
  
### <a name="to-use-row-wise-binding"></a><span data-ttu-id="c3b10-115">Per utilizzare l'associazione per riga</span><span class="sxs-lookup"><span data-stu-id="c3b10-115">To use row-wise binding</span></span>  
  
1.  <span data-ttu-id="c3b10-116">Allocare una matrice [R] di strutture, dove R è il numero di righe nel set di righe.</span><span class="sxs-lookup"><span data-stu-id="c3b10-116">Allocate an array[R] of structures, where R is the number of rows in the rowset.</span></span> <span data-ttu-id="c3b10-117">La struttura dispone di un elemento per ogni colonna e ogni elemento dispone di due parti:</span><span class="sxs-lookup"><span data-stu-id="c3b10-117">The structure has one element for each column, and each element has two parts:</span></span>  
  
    -   <span data-ttu-id="c3b10-118">La prima parte è una variabile del tipo di dati appropriato per mantenere i dati della colonna.</span><span class="sxs-lookup"><span data-stu-id="c3b10-118">The first part is a variable of the appropriate data type to hold the column data.</span></span>  
  
    -   <span data-ttu-id="c3b10-119">La seconda parte è una variabile SQLINTEGER per mantenere l'indicatore di stato della colonna.</span><span class="sxs-lookup"><span data-stu-id="c3b10-119">The second part is a SQLINTEGER variable to hold the column status indicator.</span></span>  
  
2.  <span data-ttu-id="c3b10-120">Chiamare [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) per impostare gli attributi seguenti:</span><span class="sxs-lookup"><span data-stu-id="c3b10-120">Call [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) to set the following attributes:</span></span>  
  
    -   <span data-ttu-id="c3b10-121">Impostare SQL_ATTR_ROW_ARRAY_SIZE sul numero di righe nel set di righe (R).</span><span class="sxs-lookup"><span data-stu-id="c3b10-121">Set SQL_ATTR_ROW_ARRAY_SIZE to the number of rows in the rowset (R).</span></span>  
  
    -   <span data-ttu-id="c3b10-122">Impostare SQL_ATTR_ROW_BIND_TYPE sulla dimensione della struttura allocata nel Passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="c3b10-122">Set SQL_ATTR_ROW_BIND_TYPE to the size of the structure allocated in Step 1.</span></span>  
  
    -   <span data-ttu-id="c3b10-123">Impostare l'attributo SQL_ATTR_ROWS_FETCHED_PTR affinché punti a una variabile SQLUINTEGER per mantenere il numero di righe recuperate.</span><span class="sxs-lookup"><span data-stu-id="c3b10-123">Set the SQL_ATTR_ROWS_FETCHED_PTR attribute to point to a SQLUINTEGER variable to hold the number of rows fetched.</span></span>  
  
    -   <span data-ttu-id="c3b10-124">Impostare SQL_ATTR_PARAMS_STATUS_PTR affinché punti a una matrice [R] di variabili SQLUSSMALLINT per mantenere gli indicatori di stato della riga.</span><span class="sxs-lookup"><span data-stu-id="c3b10-124">Set SQL_ATTR_PARAMS_STATUS_PTR to point to an array[R] of SQLUSSMALLINT variables to hold the row-status indicators.</span></span>  
  
3.  <span data-ttu-id="c3b10-125">Per ogni colonna nel set di risultati, chiamare [SQLBindCol](../../native-client-odbc-api/sqlbindcol.md) per puntare il valore dei dati e il puntatore della lunghezza dei dati della colonna alle relative variabili nel primo elemento della matrice di strutture allocate nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="c3b10-125">For each column in the result set, call [SQLBindCol](../../native-client-odbc-api/sqlbindcol.md) to point the data value and data length pointer of the column to their variables in the first element of the array of structures allocated in Step 1.</span></span>  
  
4.  <span data-ttu-id="c3b10-126">Eseguire l'istruzione.</span><span class="sxs-lookup"><span data-stu-id="c3b10-126">Execute the statement.</span></span>  
  
5.  <span data-ttu-id="c3b10-127">Ogni chiamata a [SQLFetch](https://go.microsoft.com/fwlink/?LinkId=58401) o [SQLFetchScroll](../../native-client-odbc-api/sqlfetchscroll.md) recupera le righe R e trasferisce i dati nelle colonne delimitate.</span><span class="sxs-lookup"><span data-stu-id="c3b10-127">Each call to [SQLFetch](https://go.microsoft.com/fwlink/?LinkId=58401) or [SQLFetchScroll](../../native-client-odbc-api/sqlfetchscroll.md) retrieves R rows and transfers the data into the bound columns.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3b10-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c3b10-128">See Also</span></span>  
 <span data-ttu-id="c3b10-129">[Procedure per l'utilizzo di cursori &#40;ODBC&#41;](using-cursors-how-to-topics-odbc.md) </span><span class="sxs-lookup"><span data-stu-id="c3b10-129">[Using Cursors How-to Topics &#40;ODBC&#41;](using-cursors-how-to-topics-odbc.md) </span></span>  
 <span data-ttu-id="c3b10-130">[Modalità di implementazione di cursori](../../native-client-odbc-cursors/implementation/how-cursors-are-implemented.md) </span><span class="sxs-lookup"><span data-stu-id="c3b10-130">[How Cursors Are Implemented](../../native-client-odbc-cursors/implementation/how-cursors-are-implemented.md) </span></span>  
 [<span data-ttu-id="c3b10-131">Utilizzare cursori &#40;&#41;ODBC</span><span class="sxs-lookup"><span data-stu-id="c3b10-131">Use Cursors &#40;ODBC&#41;</span></span>](use-cursors-odbc.md)  
  
  
