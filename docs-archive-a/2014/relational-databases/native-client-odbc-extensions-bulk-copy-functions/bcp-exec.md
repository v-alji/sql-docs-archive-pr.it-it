---
title: bcp_exec | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- bcp_exec
api_location:
- sqlncli11.dll
topic_type:
- apiref
helpviewer_keywords:
- bcp_exec function
ms.assetid: b23ea2cc-8545-4873-b0c1-57e76b0a3a7b
author: rothja
ms.author: jroth
ms.openlocfilehash: f925c6cb1e3a36f79ba4f560a06c5b6d499ece4e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623236"
---
# <a name="bcp_exec"></a><span data-ttu-id="dcac4-102">bcp_exec</span><span class="sxs-lookup"><span data-stu-id="dcac4-102">bcp_exec</span></span>
  <span data-ttu-id="dcac4-103">Esegue una copia bulk completa di dati tra una tabella di database e un file utente.</span><span class="sxs-lookup"><span data-stu-id="dcac4-103">Executes a complete bulk copy of data between a database table and a user file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dcac4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dcac4-104">Syntax</span></span>  
  
```  
  
RETCODE bcp_exec (  
HDBC   
hdbc  
,  
LPDBINT   
pnRowsProcessed  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="dcac4-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="dcac4-105">Arguments</span></span>  
 <span data-ttu-id="dcac4-106">*hdbc*</span><span class="sxs-lookup"><span data-stu-id="dcac4-106">*hdbc*</span></span>  
 <span data-ttu-id="dcac4-107">Handle di connessione ODBC abilitato per la copia bulk.</span><span class="sxs-lookup"><span data-stu-id="dcac4-107">Is the bulk copy-enabled ODBC connection handle.</span></span>  
  
 <span data-ttu-id="dcac4-108">*pnRowsProcessed*</span><span class="sxs-lookup"><span data-stu-id="dcac4-108">*pnRowsProcessed*</span></span>  
 <span data-ttu-id="dcac4-109">Puntatore a DBINT.</span><span class="sxs-lookup"><span data-stu-id="dcac4-109">Is a pointer to a DBINT.</span></span> <span data-ttu-id="dcac4-110">La funzione **bcp_exec** compila questo DBINT con il numero di righe copiate correttamente.</span><span class="sxs-lookup"><span data-stu-id="dcac4-110">The **bcp_exec** function fills this DBINT with the number of rows successfully copied.</span></span> <span data-ttu-id="dcac4-111">Se *pnRowsProcessed* è null, viene ignorato da **bcp_exec**.</span><span class="sxs-lookup"><span data-stu-id="dcac4-111">If *pnRowsProcessed* is NULL, it is ignored by **bcp_exec**.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="dcac4-112">Restituisce</span><span class="sxs-lookup"><span data-stu-id="dcac4-112">Returns</span></span>  
 <span data-ttu-id="dcac4-113">SUCCEED, SUCCEED_ASYNC o FAIL.</span><span class="sxs-lookup"><span data-stu-id="dcac4-113">SUCCEED, SUCCEED_ASYNC, or FAIL.</span></span> <span data-ttu-id="dcac4-114">La funzione **bcp_exec** restituisce esito positivo se vengono copiate tutte le righe.</span><span class="sxs-lookup"><span data-stu-id="dcac4-114">The **bcp_exec** function returns SUCCEED if all rows are copied.</span></span> <span data-ttu-id="dcac4-115">**bcp_exec** restituisce SUCCEED_ASYNC se un'operazione di copia bulk asincrona è ancora in attesa.</span><span class="sxs-lookup"><span data-stu-id="dcac4-115">**bcp_exec** returns SUCCEED_ASYNC if an asynchronous bulk copy operation is still outstanding.</span></span> <span data-ttu-id="dcac4-116">**bcp_exec** restituisce esito negativo se si verifica un errore completo o se il numero di righe che generano errori raggiunge il valore specificato per BCPMAXERRS utilizzando [bcp_control](bcp-control.md).</span><span class="sxs-lookup"><span data-stu-id="dcac4-116">**bcp_exec** returns FAIL if a complete failure occurs, or if the number of rows generating errors reaches the value specified for BCPMAXERRS using [bcp_control](bcp-control.md).</span></span> <span data-ttu-id="dcac4-117">Il valore predefinito BCPMAXERRS è 10.</span><span class="sxs-lookup"><span data-stu-id="dcac4-117">BCPMAXERRS defaults to 10.</span></span> <span data-ttu-id="dcac4-118">L'opzione BCPMAXERRS influisce solo sugli errori di sintassi rilevati dal provider durante la lettura delle righe dal file di dati, ma non delle righe inviate al server.</span><span class="sxs-lookup"><span data-stu-id="dcac4-118">The BCPMAXERRS option affects only the syntax errors detected by the provider while reading the rows from the data file (and not the rows sent to the server).</span></span> <span data-ttu-id="dcac4-119">Il server interrompe il batch quando rileva un errore con una riga.</span><span class="sxs-lookup"><span data-stu-id="dcac4-119">Server aborts the batch when it detects an error with a row.</span></span> <span data-ttu-id="dcac4-120">Controllare il parametro *pnRowsProcessed* per il numero di righe copiate correttamente.</span><span class="sxs-lookup"><span data-stu-id="dcac4-120">Check the *pnRowsProcessed* parameter for the number of rows successfully copied.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dcac4-121">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="dcac4-121">Remarks</span></span>  
 <span data-ttu-id="dcac4-122">Questa funzione copia i dati da un file utente a una tabella di database o viceversa, a seconda del valore del parametro *eDirection* in [bcp_init](bcp-init.md).</span><span class="sxs-lookup"><span data-stu-id="dcac4-122">This function copies data from a user file to a database table or vice versa, depending on the value of the *eDirection* parameter in [bcp_init](bcp-init.md).</span></span>  
  
 <span data-ttu-id="dcac4-123">Prima di chiamare **bcp_exec**, chiamare **bcp_init** con un nome di file utente valido.</span><span class="sxs-lookup"><span data-stu-id="dcac4-123">Before calling **bcp_exec**, call **bcp_init** with a valid user file name.</span></span> <span data-ttu-id="dcac4-124">In caso contrario, viene generato un errore.</span><span class="sxs-lookup"><span data-stu-id="dcac4-124">Failure to do so results in an error.</span></span>  
  
 <span data-ttu-id="dcac4-125">**bcp_exec** è l'unica funzione di copia bulk che probabilmente sarà in attesa per un periodo di tempo.</span><span class="sxs-lookup"><span data-stu-id="dcac4-125">**bcp_exec** is the only bulk copy function that is likely to be outstanding for any length of time.</span></span> <span data-ttu-id="dcac4-126">è anche l'unica funzione di copia bulk che supporta la modalità asincrona.</span><span class="sxs-lookup"><span data-stu-id="dcac4-126">It is therefore the only bulk copy function that supports asynchronous mode.</span></span> <span data-ttu-id="dcac4-127">Per impostare la modalità asincrona, utilizzare [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) per impostare SQL_ATTR_ASYNC_ENABLE su SQL_ASYNC_ENABLE_ON prima di chiamare **bcp_exec**.</span><span class="sxs-lookup"><span data-stu-id="dcac4-127">To set asynchronous mode, use [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) to set SQL_ATTR_ASYNC_ENABLE to SQL_ASYNC_ENABLE_ON before calling **bcp_exec**.</span></span> <span data-ttu-id="dcac4-128">Per verificare il completamento, chiamare **bcp_exec** con gli stessi parametri.</span><span class="sxs-lookup"><span data-stu-id="dcac4-128">To test for completion, call **bcp_exec** with the same parameters.</span></span> <span data-ttu-id="dcac4-129">Se la copia bulk non è stata ancora completata, **bcp_exec** restituisce SUCCEED_ASYNC.</span><span class="sxs-lookup"><span data-stu-id="dcac4-129">If the bulk copy has not yet completed, **bcp_exec** returns SUCCEED_ASYNC.</span></span> <span data-ttu-id="dcac4-130">Restituisce anche in *pnRowsProcessed* un conteggio dello stato del numero di righe inviate al server.</span><span class="sxs-lookup"><span data-stu-id="dcac4-130">It also returns in *pnRowsProcessed* a status count of the number of rows that have been sent to the server.</span></span> <span data-ttu-id="dcac4-131">Il commit delle righe inviate al server non viene eseguito fino a quando non viene raggiunta la fine di un batch.</span><span class="sxs-lookup"><span data-stu-id="dcac4-131">Rows sent to the server are not committed until the end of a batch has been reached.</span></span>  
  
 <span data-ttu-id="dcac4-132">Per informazioni sulle modifiche di rilievo apportate alla copia bulk a partire da [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] , vedere [esecuzione di operazioni di copia bulk &#40;&#41;ODBC ](../native-client-odbc-bulk-copy-operations/performing-bulk-copy-operations-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="dcac4-132">For information about a breaking change in bulk-copying beginning in [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], see [Performing Bulk Copy Operations &#40;ODBC&#41;](../native-client-odbc-bulk-copy-operations/performing-bulk-copy-operations-odbc.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="dcac4-133">Esempio</span><span class="sxs-lookup"><span data-stu-id="dcac4-133">Example</span></span>  
 <span data-ttu-id="dcac4-134">Nell'esempio seguente viene illustrato come utilizzare **bcp_exec**:</span><span class="sxs-lookup"><span data-stu-id="dcac4-134">The following example shows how to use **bcp_exec**:</span></span>  
  
```  
// Variables like henv not specified.  
HDBC      hdbc;  
DBINT      nRowsProcessed;  
  
// Application initiation, get an ODBC environment handle, allocate the  
// hdbc, and so on.  
...   
  
// Enable bulk copy prior to connecting on allocated hdbc.  
SQLSetConnectAttr(hdbc, SQL_COPT_SS_BCP, (SQLPOINTER) SQL_BCP_ON,  
   SQL_IS_INTEGER);  
  
// Connect to the data source, return on error.  
if (!SQL_SUCCEEDED(SQLConnect(hdbc, _T("myDSN"), SQL_NTS,  
   _T("myUser"), SQL_NTS, _T("myPwd"), SQL_NTS)))  
   {  
   // Raise error and return.  
   return;  
   }  
  
// Initialize bulk copy.   
if (bcp_init(hdbc, _T("pubs..authors"), _T("authors.sav"), NULL, DB_OUT)  
   == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
  
// Now, execute the bulk copy.   
if (bcp_exec(hdbc, &nRowsProcessed) == FAIL)  
   {  
   if (nRowsProcessed == -1)  
      {  
      printf_s("No rows processed on bulk copy execution.\n");  
      }  
   else  
      {  
      printf_s("Incomplete bulk copy.   Only %ld row%s copied.\n",  
         nRowsProcessed, (nRowsProcessed == 1) ? "": "s");  
      }  
   return;  
   }  
  
printf_s("%ld rows processed.\n", nRowsProcessed);  
  
// Carry on.  
```  
  
## <a name="see-also"></a><span data-ttu-id="dcac4-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dcac4-135">See Also</span></span>  
 [<span data-ttu-id="dcac4-136">Funzioni di copia bulk</span><span class="sxs-lookup"><span data-stu-id="dcac4-136">Bulk Copy Functions</span></span>](sql-server-driver-extensions-bulk-copy-functions.md)  
  
  
