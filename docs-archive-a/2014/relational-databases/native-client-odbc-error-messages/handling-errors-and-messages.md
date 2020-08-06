---
title: Gestione di errori e messaggi | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- ODBC error handling, about error handling
- errors [ODBC]
- SQL Server Native Client ODBC driver, errors
- messages [ODBC], about messages
- ODBC error handling
- SQL_INVALID_HANDLE return code
- errors [ODBC], about error handling
- messages [ODBC]
ms.assetid: 74ea9630-e482-4a46-bb45-f5234f079b48
author: rothja
ms.author: jroth
ms.openlocfilehash: 4701b3224b87e7d19f1121f193d4be20f9d4c441
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714344"
---
# <a name="handling-errors-and-messages"></a><span data-ttu-id="f5b54-102">Gestione di errori e messaggi</span><span class="sxs-lookup"><span data-stu-id="f5b54-102">Handling Errors and Messages</span></span>
  <span data-ttu-id="f5b54-103">Quando un'applicazione chiama una funzione ODBC, il driver esegue la funzione e restituisce le informazioni di diagnostica in due modi: un codice restituito indica l'esito positivo o negativo complessivo di una funzione ODBC e i record di diagnostica forniscono informazioni dettagliate sulla funzione.</span><span class="sxs-lookup"><span data-stu-id="f5b54-103">When an application calls an ODBC function, the driver executes the function and returns diagnostic information in two ways: A return code indicates the overall success or failure of an ODBC function, and diagnostic records provide detailed information about the function.</span></span> <span data-ttu-id="f5b54-104">I record di diagnostica includono un record di intestazione e record di stato.</span><span class="sxs-lookup"><span data-stu-id="f5b54-104">Diagnostic records include a header record and status records.</span></span> <span data-ttu-id="f5b54-105">Anche se la funzione riesce, viene restituito almeno un record di diagnostica, ovvero il record di intestazione.</span><span class="sxs-lookup"><span data-stu-id="f5b54-105">At least one diagnostic record, the header record, is returned even if the function succeeds.</span></span>  
  
 <span data-ttu-id="f5b54-106">Le informazioni di diagnostica vengono utilizzate in fase di sviluppo per rilevare errori di programmazione, ad esempio handle ed errori di sintassi non validi nelle istruzioni SQL hard-coded.</span><span class="sxs-lookup"><span data-stu-id="f5b54-106">Diagnostic information is used at development time to catch programming errors, such as invalid handles and syntax errors in hard-coded SQL statements.</span></span> <span data-ttu-id="f5b54-107">Vengono utilizzate anche in fase di esecuzione per rilevare avvisi ed errori di runtime, ad esempio troncamento di dati, violazioni di regole ed errori di sintassi nelle istruzioni SQL immesse dall'utente.</span><span class="sxs-lookup"><span data-stu-id="f5b54-107">It is also used at run time to catch run-time errors and warnings, such as data truncation, rule violations, and syntax errors in SQL statements entered by the user.</span></span> <span data-ttu-id="f5b54-108">La logica del programma si basa generalmente sui codici restituiti.</span><span class="sxs-lookup"><span data-stu-id="f5b54-108">Program logic is generally based on return codes.</span></span>  
  
 <span data-ttu-id="f5b54-109">Ad esempio, dopo che un'applicazione chiama **SQLFetch** per recuperare le righe in un set di risultati, il codice restituito indica se è stata raggiunta la fine del set di risultati (SQL_NO_DATA), se sono stati restituiti messaggi informativi (SQL_SUCCESS_WITH_INFO) o se si è verificato un errore (SQL_ERROR).</span><span class="sxs-lookup"><span data-stu-id="f5b54-109">For example, after an application calls **SQLFetch** to retrieve the rows in a result set, the return code indicates whether the end of the result set was reached (SQL_NO_DATA), if any informational messages were returned (SQL_SUCCESS_WITH_INFO), or if an error occurred (SQL_ERROR).</span></span>  
  
 <span data-ttu-id="f5b54-110">Se il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver ODBC di Native Client restituisce un valore diverso da SQL_SUCCESS, l'applicazione può chiamare **SQLGetDiagRec** per recuperare qualsiasi messaggio informativo o di errore.</span><span class="sxs-lookup"><span data-stu-id="f5b54-110">If the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver returns anything other than SQL_SUCCESS, the application can call **SQLGetDiagRec** to retrieve any informational or error messages.</span></span> <span data-ttu-id="f5b54-111">Utilizzare **SQLGetDiagRec** per scorrere verso l'alto e verso il basso il set di messaggi se è presente più di un messaggio.</span><span class="sxs-lookup"><span data-stu-id="f5b54-111">Use **SQLGetDiagRec** to scroll up and down the message set if there is more than one message.</span></span>  
  
 <span data-ttu-id="f5b54-112">Il codice restituito SQL_INVALID_HANDLE indica sempre un errore di programmazione e non dovrebbe essere mai rilevato in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="f5b54-112">The return code SQL_INVALID_HANDLE always indicates a programming error and should never be encountered at run time.</span></span> <span data-ttu-id="f5b54-113">Tutti gli altri codici restituiti forniscono informazioni di runtime, anche se SQL_ERROR potrebbe indicare un errore di programmazione.</span><span class="sxs-lookup"><span data-stu-id="f5b54-113">All other return codes provide run-time information, although SQL_ERROR may indicate a programming error.</span></span>  
  
 <span data-ttu-id="f5b54-114">L' [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] API nativa originale, DB-Library per C, consente a un'applicazione di installare le funzioni di gestione degli errori di callback e di gestione dei messaggi che restituiscono errori o messaggi.</span><span class="sxs-lookup"><span data-stu-id="f5b54-114">The original [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] native API, DB-Library for C, allows an application to install callback error-handling and message-handling functions that return errors or messages.</span></span> <span data-ttu-id="f5b54-115">Alcune istruzioni [!INCLUDE[tsql](../../includes/tsql-md.md)], ad esempio PRINT, RAISERROR, DBCC e SET, restituiscono i risultati alla funzione di gestione dei messaggi di DB-Library anziché a un set di risultati.</span><span class="sxs-lookup"><span data-stu-id="f5b54-115">Some [!INCLUDE[tsql](../../includes/tsql-md.md)] statements, such as PRINT, RAISERROR, DBCC, and SET, return their results to the DB-Library message handler function instead of to a result set.</span></span> <span data-ttu-id="f5b54-116">L'API ODBC invece non presenta alcuna funzionalità di callback di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="f5b54-116">However, the ODBC API has no such callback capability.</span></span> <span data-ttu-id="f5b54-117">Quando il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver ODBC di Native client rileva messaggi provenienti da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , imposta il codice ODBC restituito su SQL_SUCCESS_WITH_INFO o SQL_ERROR e restituisce il messaggio come uno o più record di diagnostica.</span><span class="sxs-lookup"><span data-stu-id="f5b54-117">When the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver detects messages coming back from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], it sets the ODBC return code to SQL_SUCCESS_WITH_INFO or SQL_ERROR and returns the message as one or more diagnostic records.</span></span> <span data-ttu-id="f5b54-118">Pertanto, un'applicazione ODBC deve testare attentamente questi codici restituiti e chiamare **SQLGetDiagRec** per recuperare i dati del messaggio.</span><span class="sxs-lookup"><span data-stu-id="f5b54-118">Therefore, an ODBC application must carefully test for these return codes and call **SQLGetDiagRec** to retrieve message data.</span></span>  
  
 <span data-ttu-id="f5b54-119">Per informazioni sulla traccia degli errori, vedere [Data Access Tracing](https://go.microsoft.com/fwlink/?LinkId=125805) (Traccia di accesso ai dati).</span><span class="sxs-lookup"><span data-stu-id="f5b54-119">For information about tracing errors, see [Data Access Tracing](https://go.microsoft.com/fwlink/?LinkId=125805).</span></span> <span data-ttu-id="f5b54-120">Per informazioni sui miglioramenti apportati alla traccia degli errori aggiunta in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], vedere [Accesso alle informazioni di diagnostica nel log degli eventi estesi](../native-client/features/accessing-diagnostic-information-in-the-extended-events-log.md).</span><span class="sxs-lookup"><span data-stu-id="f5b54-120">For information about enhancements to error tracing added in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], see [Accessing Diagnostic Information in the Extended Events Log](../native-client/features/accessing-diagnostic-information-in-the-extended-events-log.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f5b54-121">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="f5b54-121">In This Section</span></span>  
  
-   [<span data-ttu-id="f5b54-122">Elaborazione di istruzioni che generano messaggi</span><span class="sxs-lookup"><span data-stu-id="f5b54-122">Processing Statements That Generate Messages</span></span>](processing-statements-that-generate-messages.md)  
  
-   [<span data-ttu-id="f5b54-123">Campi e record di diagnostica</span><span class="sxs-lookup"><span data-stu-id="f5b54-123">Diagnostic Records and Fields</span></span>](diagnostic-records-and-fields.md)  
  
-   [<span data-ttu-id="f5b54-124">Numeri di errori nativi</span><span class="sxs-lookup"><span data-stu-id="f5b54-124">Native Error Numbers</span></span>](native-error-numbers.md)  
  
-   [<span data-ttu-id="f5b54-125">Codici di errore SQLSTATE &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="f5b54-125">SQLSTATE &#40;ODBC Error Codes&#41;</span></span>](sqlstate-odbc-error-codes.md)  
  
-   [<span data-ttu-id="f5b54-126">Messaggi di errore</span><span class="sxs-lookup"><span data-stu-id="f5b54-126">Error Messages</span></span>](error-messages.md)  
  
## <a name="see-also"></a><span data-ttu-id="f5b54-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f5b54-127">See Also</span></span>  
 [<span data-ttu-id="f5b54-128">SQL Server Native Client &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="f5b54-128">SQL Server Native Client &#40;ODBC&#41;</span></span>](../native-client/odbc/sql-server-native-client-odbc.md)  
  
  
