---
title: Creazione di istruzioni SQL per i cursori | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- cursors [ODBC], statement construction
- ODBC applications, cursors
- SQL Server Native Client ODBC driver, statements
- statements [ODBC], constructing
- ODBC applications, statements
- statements [ODBC], cursors
ms.assetid: 134003fd-9c93-4f5c-a988-045990933b80
author: rothja
ms.author: jroth
ms.openlocfilehash: b0fe0831b97c13c5d20067386f4e9d8c97ee19ed
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624123"
---
# <a name="constructing-sql-statements-for-cursors"></a><span data-ttu-id="ee057-102">Costruzione di istruzioni SQL per i cursori</span><span class="sxs-lookup"><span data-stu-id="ee057-102">Constructing SQL Statements for Cursors</span></span>
  <span data-ttu-id="ee057-103">Il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver ODBC di Native client utilizza cursori server per implementare la funzionalità del cursore definita nella specifica ODBC.</span><span class="sxs-lookup"><span data-stu-id="ee057-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver uses server cursors to implement the cursor functionality defined in the ODBC specification.</span></span> <span data-ttu-id="ee057-104">Un'applicazione ODBC controlla il comportamento del cursore utilizzando [SQLSetStmtAttr](../native-client-odbc-api/sqlsetstmtattr.md) per impostare attributi di istruzione differenti.</span><span class="sxs-lookup"><span data-stu-id="ee057-104">An ODBC application controls the cursor behavior by using [SQLSetStmtAttr](../native-client-odbc-api/sqlsetstmtattr.md) to set different statement attributes.</span></span> <span data-ttu-id="ee057-105">Di seguito sono indicati gli attributi e le rispettive impostazioni predefinite.</span><span class="sxs-lookup"><span data-stu-id="ee057-105">These are the attributes and their defaults.</span></span>  
  
|<span data-ttu-id="ee057-106">Attributo</span><span class="sxs-lookup"><span data-stu-id="ee057-106">Attribute</span></span>|<span data-ttu-id="ee057-107">Predefinito</span><span class="sxs-lookup"><span data-stu-id="ee057-107">Default</span></span>|  
|---------------|-------------|  
|<span data-ttu-id="ee057-108">SQL_ATTR_CONCURRENCY</span><span class="sxs-lookup"><span data-stu-id="ee057-108">SQL_ATTR_CONCURRENCY</span></span>|<span data-ttu-id="ee057-109">SQL_CONCUR_READ_ONLY</span><span class="sxs-lookup"><span data-stu-id="ee057-109">SQL_CONCUR_READ_ONLY</span></span>|  
|<span data-ttu-id="ee057-110">SQL_ATTR_CURSOR_TYPE</span><span class="sxs-lookup"><span data-stu-id="ee057-110">SQL_ATTR_CURSOR_TYPE</span></span>|<span data-ttu-id="ee057-111">SQL_CURSOR_FORWARD_ONLY</span><span class="sxs-lookup"><span data-stu-id="ee057-111">SQL_CURSOR_FORWARD_ONLY</span></span>|  
|<span data-ttu-id="ee057-112">SQL_ATTR_CURSOR_SCROLLABLE</span><span class="sxs-lookup"><span data-stu-id="ee057-112">SQL_ATTR_CURSOR_SCROLLABLE</span></span>|<span data-ttu-id="ee057-113">SQL_NONSCROLLABLE</span><span class="sxs-lookup"><span data-stu-id="ee057-113">SQL_NONSCROLLABLE</span></span>|  
|<span data-ttu-id="ee057-114">SQL_ATTR_CURSOR_SENSITIVITY</span><span class="sxs-lookup"><span data-stu-id="ee057-114">SQL_ATTR_CURSOR_SENSITIVITY</span></span>|<span data-ttu-id="ee057-115">SQL_UNSPECIFIED</span><span class="sxs-lookup"><span data-stu-id="ee057-115">SQL_UNSPECIFIED</span></span>|  
|<span data-ttu-id="ee057-116">SQL_ATTR_ROW_ARRAY_SIZE</span><span class="sxs-lookup"><span data-stu-id="ee057-116">SQL_ATTR_ROW_ARRAY_SIZE</span></span>|<span data-ttu-id="ee057-117">1</span><span class="sxs-lookup"><span data-stu-id="ee057-117">1</span></span>|  
  
 <span data-ttu-id="ee057-118">Quando queste opzioni sono impostate sui valori predefiniti al momento dell'esecuzione di un'istruzione SQL, il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver ODBC di Native client non utilizza un cursore server per implementare il set di risultati, bensì utilizza un set di risultati predefinito.</span><span class="sxs-lookup"><span data-stu-id="ee057-118">When these options are set to their defaults at the time an SQL statement is executed, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver does not use a server cursor to implement the result set; instead, it uses a default result set.</span></span> <span data-ttu-id="ee057-119">Se una di queste opzioni viene modificata rispetto alle impostazioni predefinite nel momento in cui viene eseguita un'istruzione SQL, il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver ODBC di Native client tenta di utilizzare un cursore server per implementare il set di risultati.</span><span class="sxs-lookup"><span data-stu-id="ee057-119">If any of these options are changed from their defaults at the time an SQL statement is executed, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver attempts to use a server cursor to implement the result set.</span></span>  
  
 <span data-ttu-id="ee057-120">I set di risultati predefiniti supportano tutte le istruzioni [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ee057-120">Default result sets support all of the [!INCLUDE[tsql](../../includes/tsql-md.md)] statements.</span></span> <span data-ttu-id="ee057-121">Non sono presenti restrizioni sui tipi di istruzioni SQL che è possibile eseguire quando si utilizza un set di risultati predefinito.</span><span class="sxs-lookup"><span data-stu-id="ee057-121">There are no restrictions on the types of SQL statements that can be executed when using a default result set.</span></span>  
  
 <span data-ttu-id="ee057-122">I cursori server non supportano tutte le istruzioni [!INCLUDE[tsql](../../includes/tsql-md.md)] e</span><span class="sxs-lookup"><span data-stu-id="ee057-122">Server cursors do not support all [!INCLUDE[tsql](../../includes/tsql-md.md)] statements.</span></span> <span data-ttu-id="ee057-123">non supportano un'istruzione SQL che genera più set di risultati.</span><span class="sxs-lookup"><span data-stu-id="ee057-123">Server cursors do not support any SQL statement that generates multiple result sets.</span></span>  
  
 <span data-ttu-id="ee057-124">Di seguito sono indicati i tipi di istruzioni non supportati dai cursori server:</span><span class="sxs-lookup"><span data-stu-id="ee057-124">The following types of statements are not supported by server cursors:</span></span>  
  
-   <span data-ttu-id="ee057-125">Batch</span><span class="sxs-lookup"><span data-stu-id="ee057-125">Batches</span></span>  
  
     <span data-ttu-id="ee057-126">Istruzioni SQL compilate da due o più istruzioni SQL SELECT singole, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="ee057-126">SQL statements built from two or more individual SQL SELECT statements, for example:</span></span>  
  
    ```  
    SELECT * FROM Authors; SELECT * FROM Titles  
    ```  
  
-   <span data-ttu-id="ee057-127">Stored procedure con più istruzioni SELECT</span><span class="sxs-lookup"><span data-stu-id="ee057-127">Stored procedures with multiple SELECT statements</span></span>  
  
     <span data-ttu-id="ee057-128">Istruzioni SQL che eseguono una stored procedure che contiene più di un'istruzione SELECT.</span><span class="sxs-lookup"><span data-stu-id="ee057-128">SQL statements that execute a stored procedure containing more than one SELECT statement.</span></span> <span data-ttu-id="ee057-129">Sono incluse le istruzioni SELECT che vengono inserite in parametri o variabili.</span><span class="sxs-lookup"><span data-stu-id="ee057-129">This includes SELECT statements that fill parameters or variables.</span></span>  
  
-   <span data-ttu-id="ee057-130">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ee057-130">Keywords</span></span>  
  
     <span data-ttu-id="ee057-131">Istruzioni SQL contenenti le parole chiave FOR BROWSE o INTO.</span><span class="sxs-lookup"><span data-stu-id="ee057-131">SQL statements containing the keywords FOR BROWSE, or INTO.</span></span>  
  
 <span data-ttu-id="ee057-132">Se in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] un'istruzione SQL che corrisponde a una di queste condizioni viene eseguita con un cursore server, il cursore server viene convertito implicitamente in un set di risultati predefinito.</span><span class="sxs-lookup"><span data-stu-id="ee057-132">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], if an SQL statement that matches any of these conditions is executed with a server cursor, the server cursor is implicitly converted to a default result set.</span></span> <span data-ttu-id="ee057-133">Quando **SQLExecDirect** o **sqlexecute** restituisce SQL_SUCCESS_WITH_INFO, gli attributi del cursore verranno impostati nuovamente sulle impostazioni predefinite.</span><span class="sxs-lookup"><span data-stu-id="ee057-133">After **SQLExecDirect** or **SQLExecute** returns SQL_SUCCESS_WITH_INFO, the cursor attributes will be set back to their default settings.</span></span>  
  
 <span data-ttu-id="ee057-134">Le istruzioni SQL che non rientrano nelle categorie sopra riportate possono essere eseguite con qualsiasi impostazione degli attributi di istruzione. Il funzionamento è identico con un set di risultati predefinito o con un cursore server.</span><span class="sxs-lookup"><span data-stu-id="ee057-134">SQL statements that do not fit the categories above can be executed with any statement attribute settings; they work equally well with either a default result set or a server cursor.</span></span>  
  
## <a name="errors"></a><span data-ttu-id="ee057-135">Errors</span><span class="sxs-lookup"><span data-stu-id="ee057-135">Errors</span></span>  
 <span data-ttu-id="ee057-136">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 7.0 e versioni successive un tentativo di eseguire un'istruzione che produce più set di risultati genera SQL_SUCCESS_WITH INFO e il messaggio seguente:</span><span class="sxs-lookup"><span data-stu-id="ee057-136">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 7.0 and later, an attempt to execute a statement that produces multiple result sets generates SQL_SUCCESS_WITH INFO and the following message:</span></span>  
  
```  
SqlState: 01S02"  
pfNative: 0  
szErrorMsgString: "[Microsoft][SQL Server Native Client][SQL Server]  
               Cursor type changed."  
```  
  
 <span data-ttu-id="ee057-137">Le applicazioni ODBC che ricevono questo messaggio possono chiamare [SQLGetStmtAttr](../native-client-odbc-api/sqlgetstmtattr.md) per determinare le impostazioni correnti del cursore.</span><span class="sxs-lookup"><span data-stu-id="ee057-137">ODBC applications receiving this message can call [SQLGetStmtAttr](../native-client-odbc-api/sqlgetstmtattr.md) to determine the current cursor settings.</span></span>  
  
 <span data-ttu-id="ee057-138">Un tentativo di eseguire una procedura con più istruzioni SELECT quando si utilizzano cursori server genera l'errore seguente:</span><span class="sxs-lookup"><span data-stu-id="ee057-138">An attempt to execute a procedure with multiple SELECT statements when using server cursors generates the following error:</span></span>  
  
```  
SqlState: 42000  
pfNative: 16937  
szErrorMsgString: [Microsoft][SQL Server Native Client][SQL Server]  
               A server cursor is not allowed on a stored procedure  
               with more than one SELECT statement in it. Use a  
               default result set or client cursor.  
```  
  
 <span data-ttu-id="ee057-139">Un tentativo di eseguire un batch con più istruzioni SELECT quando l'utilizzo di cursori server genera l'errore seguente:</span><span class="sxs-lookup"><span data-stu-id="ee057-139">An attempt to execute a batch with multiple SELECT statements when using server cursors generates the following error:</span></span>  
  
```  
SqlState: 42000  
pfNative: 16938  
szErrorMsgString: [Microsoft][SQL Server Native Client][SQL Server]  
               sp_cursoropen. The statement parameter can only  
               be a single SELECT statement or a single stored   
               procedure.  
```  
  
 <span data-ttu-id="ee057-140">Nelle applicazioni ODBC che ricevono questi errori devono essere reimpostati tutti gli attributi di istruzione di cursore sui valori predefiniti prima di tentare di eseguire l'istruzione.</span><span class="sxs-lookup"><span data-stu-id="ee057-140">ODBC applications receiving these errors must reset all the cursor statement attributes to their defaults before attempting to execute the statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee057-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ee057-141">See Also</span></span>  
 [<span data-ttu-id="ee057-142">Esecuzione di query &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="ee057-142">Executing Queries &#40;ODBC&#41;</span></span>](executing-queries-odbc.md)  
  
  
