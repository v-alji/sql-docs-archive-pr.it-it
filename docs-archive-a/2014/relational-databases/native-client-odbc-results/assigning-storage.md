---
title: Assegnazione dell'archiviazione | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- column-wise binding [ODBC]
- SQL Server Native Client ODBC driver, result sets
- ODBC applications, result sets
- SQLBindCol function
- storing data [ODBC]
- result sets [ODBC], storage
- SQL Server Native Client ODBC driver, data storage
- row-wise binding
- binding result sets [SQL Server Native Client]
- array binding
ms.assetid: 11c81955-5300-495f-925f-9256f2587b58
author: rothja
ms.author: jroth
ms.openlocfilehash: ada18c91493d91b36ced51bf84c32513a0c5f5df
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635528"
---
# <a name="assigning-storage"></a><span data-ttu-id="07de3-102">Assegnazione di archiviazione</span><span class="sxs-lookup"><span data-stu-id="07de3-102">Assigning Storage</span></span>
  <span data-ttu-id="07de3-103">In un'applicazione è possibile assegnare l'archiviazione per i risultati prima o dopo l'esecuzione di un'istruzione SQL.</span><span class="sxs-lookup"><span data-stu-id="07de3-103">An application can assign storage for results before or after it executes a SQL statement.</span></span> <span data-ttu-id="07de3-104">Se la preparazione o l'esecuzione dell'istruzione SQL avviene prima, è possibile richiedere informazioni sul set di risultati prima di archiviare i risultati.</span><span class="sxs-lookup"><span data-stu-id="07de3-104">If an application prepares or executes the SQL statement first, it can inquire about the result set before it assigns storage for results.</span></span> <span data-ttu-id="07de3-105">Se ad esempio il set di risultati non è noto, è necessario recuperare il numero di colonne prima dell'assegnazione dell'archiviazione.</span><span class="sxs-lookup"><span data-stu-id="07de3-105">For example, if the result set is unknown, the application must retrieve the number of columns before it can assign storage for them.</span></span>  
  
 <span data-ttu-id="07de3-106">Per associare lo spazio di archiviazione per una colonna di dati, un'applicazione chiama [SQLBindCol](../native-client-odbc-api/sqlbindcol.md)e la passa:</span><span class="sxs-lookup"><span data-stu-id="07de3-106">To associate storage for a column of data, an application calls [SQLBindCol](../native-client-odbc-api/sqlbindcol.md)and passes it:</span></span>  
  
-   <span data-ttu-id="07de3-107">Tipo di dati nel quale devono essere convertiti i dati.</span><span class="sxs-lookup"><span data-stu-id="07de3-107">The data type to which the data is to be converted.</span></span>  
  
-   <span data-ttu-id="07de3-108">Indirizzo di un buffer di output per i dati.</span><span class="sxs-lookup"><span data-stu-id="07de3-108">The address of an output buffer for the data.</span></span>  
  
     <span data-ttu-id="07de3-109">L'applicazione deve allocare questo buffer, e deve essere di dimensioni sufficienti a contenere i dati nel formato nel quale vengono convertiti.</span><span class="sxs-lookup"><span data-stu-id="07de3-109">The application must allocate this buffer, and it must be large enough to hold the data in the form to which it is converted.</span></span>  
  
-   <span data-ttu-id="07de3-110">Lunghezza del buffer di output.</span><span class="sxs-lookup"><span data-stu-id="07de3-110">The length of the output buffer.</span></span>  
  
     <span data-ttu-id="07de3-111">Questo valore viene ignorato se i dati restituiti hanno una larghezza fissa in C, ad esempio un numero intero, un numero reale o una struttura di data.</span><span class="sxs-lookup"><span data-stu-id="07de3-111">This value is ignored if the returned data has a fixed width in C, such as an integer, real number, or date structure.</span></span>  
  
-   <span data-ttu-id="07de3-112">Indirizzo di un buffer di archiviazione nel quale restituire il numero di byte dei dati disponibili.</span><span class="sxs-lookup"><span data-stu-id="07de3-112">The address of a storage buffer in which to return the number of bytes of available data.</span></span>  
  
 <span data-ttu-id="07de3-113">Un'applicazione può inoltre associare colonne del set di risultati a matrici di variabili di programma per consentire il supporto del recupero di righe in blocchi.</span><span class="sxs-lookup"><span data-stu-id="07de3-113">An application can also bind result set columns to arrays of program variables to support fetching result set rows in blocks.</span></span> <span data-ttu-id="07de3-114">Sono disponibili due tipi diversi di associazione di matrici:</span><span class="sxs-lookup"><span data-stu-id="07de3-114">There are two different types of array binding:</span></span>  
  
-   <span data-ttu-id="07de3-115">L'associazione a livello di colonna è completa quando ogni colonna è associata alla rispettiva matrice di variabili.</span><span class="sxs-lookup"><span data-stu-id="07de3-115">Column-wise binding is finished when each column is bound to its own array of variables.</span></span>  
  
     <span data-ttu-id="07de3-116">L'associazione per colonna viene specificata chiamando [SQLSetStmtAttr](../native-client-odbc-api/sqlsetstmtattr.md) con *Attribute* impostato su SQL_ATTR_ROW_BIND_TYPE e *ValuePtr* impostato su SQL_BIND_BY_COLUMN.</span><span class="sxs-lookup"><span data-stu-id="07de3-116">Column-wise binding is specified by calling [SQLSetStmtAttr](../native-client-odbc-api/sqlsetstmtattr.md) with *Attribute* set to SQL_ATTR_ROW_BIND_TYPE and *ValuePtr* set to SQL_BIND_BY_COLUMN.</span></span> <span data-ttu-id="07de3-117">Tutte le matrici devono avere lo stesso numero di elementi.</span><span class="sxs-lookup"><span data-stu-id="07de3-117">All the arrays must have the same number of elements.</span></span>  
  
-   <span data-ttu-id="07de3-118">L'associazione a livello di riga è completa quando tutti i parametri dell'istruzione SQL vengono associati come un'unità a una matrice di strutture contenenti le singole variabili per i parametri.</span><span class="sxs-lookup"><span data-stu-id="07de3-118">Row-wise binding is finished when all the parameters in the SQL statement are bound as a unit to an array of structures that contain the individual variables for the parameters.</span></span>  
  
     <span data-ttu-id="07de3-119">L'associazione per riga viene specificata chiamando **SQLSetStmtAttr** con *Attribute* impostato su SQL_ATTR_ROW_BIND_TYPE e *ValuePtr* impostato sulle dimensioni della struttura che contiene le variabili che riceveranno le colonne del set di risultati.</span><span class="sxs-lookup"><span data-stu-id="07de3-119">Row-wise binding is specified by calling **SQLSetStmtAttr** with *Attribute* set to SQL_ATTR_ROW_BIND_TYPE and *ValuePtr* set to the size of the structure holding the variables that will receive the result set columns.</span></span>  
  
 <span data-ttu-id="07de3-120">Viene inoltre impostato SQL_ATTR_ROW_ARRAY_SIZE sul numero di elementi presenti nelle matrici di colonne o di righe e vengono impostati SQL_ATTR_ROW_STATUS_PTR e SQL_ATTR_ROWS_FETCHED_PTR.</span><span class="sxs-lookup"><span data-stu-id="07de3-120">The application also sets SQL_ATTR_ROW_ARRAY_SIZE to the number of elements in the column or row arrays and sets SQL_ATTR_ROW_STATUS_PTR and SQL_ATTR_ROWS_FETCHED_PTR.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07de3-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="07de3-121">See Also</span></span>  
 [<span data-ttu-id="07de3-122">Elaborazione dei risultati &#40;&#41;ODBC</span><span class="sxs-lookup"><span data-stu-id="07de3-122">Processing Results &#40;ODBC&#41;</span></span>](processing-results-odbc.md)  
  
  
