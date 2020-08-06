---
title: Risultati dell'elaborazione (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- result sets [ODBC], about result sets
- SQLRowCount function
- SQL Server Native Client ODBC driver, result sets
- ODBC applications, result sets
- COMPUTE clause
- result sets [ODBC]
- COMPUTE BY clause
ms.assetid: 61a8db19-6571-47dd-84e8-fcc97cb60b45
author: rothja
ms.author: jroth
ms.openlocfilehash: 72c0d15231b07a23f10a03b0fca270d1d014891c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725651"
---
# <a name="processing-results-odbc"></a><span data-ttu-id="a008b-102">Risultati dell'elaborazione (ODBC)</span><span class="sxs-lookup"><span data-stu-id="a008b-102">Processing Results (ODBC)</span></span>
  <span data-ttu-id="a008b-103">Dopo l'invio di un'istruzione SQL da parte di un'applicazione, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] restituisce eventuali dati risultanti come uno o più set di risultati.</span><span class="sxs-lookup"><span data-stu-id="a008b-103">After an application submits a SQL statement, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] returns any resulting data as one or more result sets.</span></span> <span data-ttu-id="a008b-104">Un set di risultati è un set di righe e colonne che corrispondono ai criteri della query.</span><span class="sxs-lookup"><span data-stu-id="a008b-104">A result set is a set of rows and columns that match the criteria of the query.</span></span> <span data-ttu-id="a008b-105">Le istruzioni SELECT, le funzioni di catalogo e alcune stored procedure producono un set di risultati reso disponibile a un'applicazione in formato tabulare.</span><span class="sxs-lookup"><span data-stu-id="a008b-105">SELECT statements, catalog functions, and some stored procedures produce a result set made available to an application in tabular form.</span></span> <span data-ttu-id="a008b-106">Se l'istruzione SQL eseguita è una stored procedure, un batch contenente più comandi o un'istruzione SELECT contenente parole chiave, il numero di set di risultati da elaborare sarà maggiore.</span><span class="sxs-lookup"><span data-stu-id="a008b-106">If the executed SQL statement is a stored procedure, a batch containing multiple commands, or a SELECT statement containing keywords, there will be multiple result sets to process.</span></span>  
  
 <span data-ttu-id="a008b-107">Anche le funzioni di catalogo ODBC possono recuperare dati.</span><span class="sxs-lookup"><span data-stu-id="a008b-107">ODBC catalog functions also can retrieve data.</span></span> <span data-ttu-id="a008b-108">[SQLColumns](../native-client-odbc-api/sqlcolumns.md) , ad esempio, consente di recuperare dati sulle colonne dell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="a008b-108">For example, [SQLColumns](../native-client-odbc-api/sqlcolumns.md) retrieves data about columns in the data source.</span></span> <span data-ttu-id="a008b-109">Questi set di risultati possono contenere zero o più righe.</span><span class="sxs-lookup"><span data-stu-id="a008b-109">These result sets can contain zero or more rows.</span></span>  
  
 <span data-ttu-id="a008b-110">Le altre istruzioni SQL, ad esempio GRANT o REVOKE, non restituiscono set di risultati.</span><span class="sxs-lookup"><span data-stu-id="a008b-110">Other SQL statements, such as GRANT or REVOKE, do not return result sets.</span></span> <span data-ttu-id="a008b-111">Per queste istruzioni, il codice restituito da **SQLExecute** o **SQLExecDirect** è in genere l'unica indicazione che l'istruzione ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="a008b-111">For these statements, the return code from **SQLExecute** or **SQLExecDirect** is usually the only indication the statement was successful.</span></span>  
  
 <span data-ttu-id="a008b-112">Ogni istruzione INSERT, UPDATE e DELETE restituisce un set di risultati contenente solo il numero di righe modificate.</span><span class="sxs-lookup"><span data-stu-id="a008b-112">Each INSERT, UPDATE, and DELETE statement returns a result set containing only the number of rows affected by the modification.</span></span> <span data-ttu-id="a008b-113">Questo conteggio viene reso disponibile quando l'applicazione chiama [SQLRowCount](../native-client-odbc-api/sqlrowcount.md).</span><span class="sxs-lookup"><span data-stu-id="a008b-113">This count is made available when application calls [SQLRowCount](../native-client-odbc-api/sqlrowcount.md).</span></span> <span data-ttu-id="a008b-114">ODBC 3. le applicazioni *x* devono chiamare **SQLRowCount** per recuperare il set di risultati o [SQLMoreResults](../native-client-odbc-api/sqlmoreresults.md) per annullarlo.</span><span class="sxs-lookup"><span data-stu-id="a008b-114">ODBC 3.*x* applications must either call **SQLRowCount** to retrieve the result set or [SQLMoreResults](../native-client-odbc-api/sqlmoreresults.md) to cancel it.</span></span> <span data-ttu-id="a008b-115">Quando un'applicazione esegue un batch o stored procedure contenente più istruzioni INSERT, UPDATE o DELETE, il set di risultati di ogni istruzione di modifica deve essere elaborato utilizzando **SQLRowCount** o annullato utilizzando **SQLMoreResults**.</span><span class="sxs-lookup"><span data-stu-id="a008b-115">When an application executes a batch or stored procedure containing multiple INSERT, UPDATE, or DELETE statements, the result set from each modification statement must be processed using **SQLRowCount** or cancelled using **SQLMoreResults**.</span></span> <span data-ttu-id="a008b-116">Questi conteggi possono essere annullati includendo un'istruzione SET NOCOUNT ON nel batch o nella stored procedure.</span><span class="sxs-lookup"><span data-stu-id="a008b-116">These counts can be cancelled by including a SET NOCOUNT ON statement in the batch or stored procedure.</span></span>  
  
 <span data-ttu-id="a008b-117">Transact-SQL include l'istruzione SET NOCOUNT.</span><span class="sxs-lookup"><span data-stu-id="a008b-117">Transact-SQL includes the SET NOCOUNT statement.</span></span> <span data-ttu-id="a008b-118">Se l'opzione NOCOUNT è impostata su on, SQL Server non restituisce i conteggi delle righe interessate da un'istruzione e **SQLRowCount** restituisce 0.</span><span class="sxs-lookup"><span data-stu-id="a008b-118">When the NOCOUNT option is set on, SQL Server does not return the counts of the rows affected by a statement and **SQLRowCount** returns 0.</span></span> <span data-ttu-id="a008b-119">La [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] versione del driver ODBC di Native Client introduce un'opzione [SQLGetStmtAttr](../native-client-odbc-api/sqlgetstmtattr.md) specifica del driver, SQL_SOPT_SS_NOCOUNT_STATUS, per segnalare se l'opzione NOCOUNT è impostata su on o off.</span><span class="sxs-lookup"><span data-stu-id="a008b-119">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver version introduces a driver-specific [SQLGetStmtAttr](../native-client-odbc-api/sqlgetstmtattr.md) option, SQL_SOPT_SS_NOCOUNT_STATUS, to report on whether the NOCOUNT option is on or off.</span></span> <span data-ttu-id="a008b-120">Quando **SQLRowCount** restituisce 0, l'applicazione deve testare SQL_SOPT_SS_NOCOUNT_STATUS.</span><span class="sxs-lookup"><span data-stu-id="a008b-120">Anytime **SQLRowCount** returns 0, the application should test SQL_SOPT_SS_NOCOUNT_STATUS.</span></span> <span data-ttu-id="a008b-121">Se viene restituito SQL_NC_ON, il valore 0 di **SQLRowCount** indica solo che SQL Server non ha restituito un conteggio di righe.</span><span class="sxs-lookup"><span data-stu-id="a008b-121">If SQL_NC_ON is returned, the value of 0 from **SQLRowCount** only indicates that SQL Server has not returned a row count.</span></span> <span data-ttu-id="a008b-122">Se viene restituito SQL_NC_OFF, significa che NOCOUNT è disattivato e il valore 0 di **SQLRowCount** indica che l'istruzione non ha influire sulle righe.</span><span class="sxs-lookup"><span data-stu-id="a008b-122">If SQL_NC_OFF is returned, it means that NOCOUNT is off and the value of 0 from **SQLRowCount** indicates that the statement did not affect any rows.</span></span> <span data-ttu-id="a008b-123">Quando SQL_SOPT_SS_NOCOUNT_STATUS viene SQL_NC_OFF, le applicazioni non dovrebbero visualizzare il valore di **SQLRowCount** .</span><span class="sxs-lookup"><span data-stu-id="a008b-123">Applications should not display the value of **SQLRowCount** when SQL_SOPT_SS_NOCOUNT_STATUS is SQL_NC_OFF.</span></span> <span data-ttu-id="a008b-124">Le stored procedure o i batch di grandi dimensioni possono contenere più istruzioni SET NOCOUNT, pertanto i programmatori non possono presupporre che SQL_SOPT_SS_NOCOUNT_STATUS rimanga costante.</span><span class="sxs-lookup"><span data-stu-id="a008b-124">Large batches or stored procedures may contain multiple SET NOCOUNT statements so programmers cannot assume SQL_SOPT_SS_NOCOUNT_STATUS remains constant.</span></span> <span data-ttu-id="a008b-125">L'opzione deve essere testata ogni volta che **SQLRowCount** restituisce 0.</span><span class="sxs-lookup"><span data-stu-id="a008b-125">The option should be tested each time **SQLRowCount** returns 0.</span></span>  
  
 <span data-ttu-id="a008b-126">Diverse altre istruzioni Transact-SQL restituiscono nei messaggi dati anziché set di risultati.</span><span class="sxs-lookup"><span data-stu-id="a008b-126">Several other Transact-SQL statements return their data in messages rather than result sets.</span></span> <span data-ttu-id="a008b-127">Quando il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver ODBC di Native client riceve questi messaggi, restituisce SQL_SUCCESS_WITH_INFO per informare l'applicazione che i messaggi informativi sono disponibili.</span><span class="sxs-lookup"><span data-stu-id="a008b-127">When the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver receives these messages, it returns SQL_SUCCESS_WITH_INFO to let the application know that informational messages are available.</span></span> <span data-ttu-id="a008b-128">L'applicazione può quindi chiamare **SQLGetDiagRec** per recuperare questi messaggi.</span><span class="sxs-lookup"><span data-stu-id="a008b-128">The application can then call **SQLGetDiagRec** to retrieve these messages.</span></span> <span data-ttu-id="a008b-129">Le istruzioni [!INCLUDE[tsql](../../includes/tsql-md.md)] che funzionano in questo modo sono:</span><span class="sxs-lookup"><span data-stu-id="a008b-129">The [!INCLUDE[tsql](../../includes/tsql-md.md)] statements that work this way are:</span></span>  
  
-   <span data-ttu-id="a008b-130">DBCC</span><span class="sxs-lookup"><span data-stu-id="a008b-130">DBCC</span></span>  
  
-   <span data-ttu-id="a008b-131">SET SHOWPLAN (disponibile con versioni precedenti di SQL Server)</span><span class="sxs-lookup"><span data-stu-id="a008b-131">SET SHOWPLAN (available with earlier versions of SQL Server)</span></span>  
  
-   <span data-ttu-id="a008b-132">SET STATISTICS</span><span class="sxs-lookup"><span data-stu-id="a008b-132">SET STATISTICS</span></span>  
  
-   <span data-ttu-id="a008b-133">PRINT</span><span class="sxs-lookup"><span data-stu-id="a008b-133">PRINT</span></span>  
  
-   <span data-ttu-id="a008b-134">RAISERROR</span><span class="sxs-lookup"><span data-stu-id="a008b-134">RAISERROR</span></span>  
  
 <span data-ttu-id="a008b-135">Il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver ODBC di Native Client restituisce SQL_ERROR in un RAISERROR con gravità 11 o superiore.</span><span class="sxs-lookup"><span data-stu-id="a008b-135">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver returns SQL_ERROR on a RAISERROR with a severity of 11 or higher.</span></span> <span data-ttu-id="a008b-136">Se la gravità di RAISERROR è 19 o superiore, viene anche interrotta la connessione.</span><span class="sxs-lookup"><span data-stu-id="a008b-136">If the severity of the RAISERROR is 19 or higher, the connection is also dropped.</span></span>  
  
 <span data-ttu-id="a008b-137">Per elaborare i set di risultati da un'istruzione SQL, l'applicazione:</span><span class="sxs-lookup"><span data-stu-id="a008b-137">To process the result sets from an SQL statement, the application:</span></span>  
  
-   <span data-ttu-id="a008b-138">Determina le caratteristiche del set di risultati.</span><span class="sxs-lookup"><span data-stu-id="a008b-138">Determines the characteristics of the result set.</span></span>  
  
-   <span data-ttu-id="a008b-139">Associa le colonne a variabili di programma.</span><span class="sxs-lookup"><span data-stu-id="a008b-139">Binds the columns to program variables.</span></span>  
  
-   <span data-ttu-id="a008b-140">Recupera un valore singolo, un'intera riga di valori o più righe di valori.</span><span class="sxs-lookup"><span data-stu-id="a008b-140">Retrieves a single value, an entire row of values, or multiple rows of values.</span></span>  
  
-   <span data-ttu-id="a008b-141">Verifica se sono presenti altri set di risultati e, in caso affermativo, esegue il ciclo all'indietro per determinare le caratteristiche del nuovo set di risultati.</span><span class="sxs-lookup"><span data-stu-id="a008b-141">Tests to see if there are more result sets, and if so, loops back to determining the characteristics of the new result set.</span></span>  
  
 <span data-ttu-id="a008b-142">Il processo che consente di recuperare le righe dall'origine dati e di restituirle alle applicazioni viene denominato recupero.</span><span class="sxs-lookup"><span data-stu-id="a008b-142">The process of retrieving rows from the data source and returning them to the application is called fetching.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a008b-143">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="a008b-143">In This Section</span></span>  
  
-   [<span data-ttu-id="a008b-144">Determinazione delle caratteristiche di un set di risultati &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="a008b-144">Determining the Characteristics of a Result Set &#40;ODBC&#41;</span></span>](determining-the-characteristics-of-a-result-set-odbc.md)  
  
-   [<span data-ttu-id="a008b-145">Assegnazione di archiviazione</span><span class="sxs-lookup"><span data-stu-id="a008b-145">Assigning Storage</span></span>](assigning-storage.md)  
  
-   [<span data-ttu-id="a008b-146">Recupero di dati dei risultati</span><span class="sxs-lookup"><span data-stu-id="a008b-146">Fetching Result Data</span></span>](fetching-result-data.md)  
  
-   [<span data-ttu-id="a008b-147">Mapping dei tipi di dati &#40;&#41;ODBC</span><span class="sxs-lookup"><span data-stu-id="a008b-147">Mapping Data Types &#40;ODBC&#41;</span></span>](mapping-data-types-odbc.md)  
  
-   [<span data-ttu-id="a008b-148">Utilizzo del tipo di dati</span><span class="sxs-lookup"><span data-stu-id="a008b-148">Data Type Usage</span></span>](data-type-usage.md)  
  
-   [<span data-ttu-id="a008b-149">Conversione automatica dei dati di tipo carattere</span><span class="sxs-lookup"><span data-stu-id="a008b-149">Autotranslation of Character Data</span></span>](autotranslation-of-character-data.md)  
  
## <a name="see-also"></a><span data-ttu-id="a008b-150">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a008b-150">See Also</span></span>  
 <span data-ttu-id="a008b-151">[SQL Server Native Client &#40;ODBC&#41;](../native-client/odbc/sql-server-native-client-odbc.md) </span><span class="sxs-lookup"><span data-stu-id="a008b-151">[SQL Server Native Client &#40;ODBC&#41;](../native-client/odbc/sql-server-native-client-odbc.md) </span></span>  
 [<span data-ttu-id="a008b-152">Procedure per l'elaborazione dei risultati &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="a008b-152">Processing Results How-to Topics &#40;ODBC&#41;</span></span>](../../database-engine/dev-guide/processing-results-how-to-topics-odbc.md)  
  
  
