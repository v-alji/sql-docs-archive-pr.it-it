---
title: Parametri di binding | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client ODBC driver, parameters
- parameters [SQL Server Native Client], ODBC
- statements [ODBC], parameters
- binding parameters [SQL Server Native Client]
- parameter markers [ODBC]
- unbound parameter markers
- SQLBindParameter function
- ODBC applications, parameters
- bound parameter markers [SQL Server Native Client]
ms.assetid: d6c69739-8f89-475f-a60a-b2f6c06576e2
author: rothja
ms.author: jroth
ms.openlocfilehash: 3402a7efce43d0ce94a20c93504ac1dcb2c7b48f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624104"
---
# <a name="binding-parameters"></a><span data-ttu-id="f4537-102">Associazione di parametri</span><span class="sxs-lookup"><span data-stu-id="f4537-102">Binding Parameters</span></span>
  <span data-ttu-id="f4537-103">Ogni marcatore di parametro in un'istruzione SQL deve essere associato a una variabile nell'applicazione prima di eseguire l'istruzione.</span><span class="sxs-lookup"><span data-stu-id="f4537-103">Each parameter marker in an SQL statement must be associated, or bound, to a variable in the application before the statement can be executed.</span></span> <span data-ttu-id="f4537-104">Questa operazione viene eseguita chiamando la funzione [SQLBindParameter](../native-client-odbc-api/sqlbindparameter.md) .</span><span class="sxs-lookup"><span data-stu-id="f4537-104">This is done by calling the [SQLBindParameter](../native-client-odbc-api/sqlbindparameter.md) function.</span></span> <span data-ttu-id="f4537-105">**SQLBindParameter** descrive la variabile di programma (indirizzo, tipo di dati C e così via) al driver.</span><span class="sxs-lookup"><span data-stu-id="f4537-105">**SQLBindParameter** describes the program variable (address, C data type, and so on) to the driver.</span></span> <span data-ttu-id="f4537-106">La funzione identifica inoltre il marcatore di parametro specificandone il valore ordinale e quindi descrive le caratteristiche dell'oggetto SQL rappresentato (tipo di dati SQL, precisione e così via).</span><span class="sxs-lookup"><span data-stu-id="f4537-106">It also identifies the parameter marker by indicating its ordinal value and then describes the characteristics of the SQL object it represents (SQL data type, precision, and so on).</span></span>

 <span data-ttu-id="f4537-107">I marcatori di parametro possono essere associati o riassociati in qualunque momento prima di eseguire un'istruzione.</span><span class="sxs-lookup"><span data-stu-id="f4537-107">Parameter markers can be bound or rebound at any time before a statement is executed.</span></span> <span data-ttu-id="f4537-108">Un'associazione di parametri rimane effettiva fino a quando non si verifica uno dei casi seguenti:</span><span class="sxs-lookup"><span data-stu-id="f4537-108">A parameter binding remains in effect until one of the following occurs:</span></span>

-   <span data-ttu-id="f4537-109">Una chiamata a [SQLFreeStmt](../native-client-odbc-api/sqlfreestmt.md) con il parametro *Option* impostato su SQL_RESET_PARAMS libera tutti i parametri associati all'handle di istruzione.</span><span class="sxs-lookup"><span data-stu-id="f4537-109">A call to [SQLFreeStmt](../native-client-odbc-api/sqlfreestmt.md) with the *Option* parameter set to SQL_RESET_PARAMS frees all parameters bound to the statement handle.</span></span>

-   <span data-ttu-id="f4537-110">Una chiamata a **SQLBindParameter** con *ParameterNumber* impostato sull'ordinale di un marcatore di parametro associato rilascia automaticamente l'associazione precedente.</span><span class="sxs-lookup"><span data-stu-id="f4537-110">A call to **SQLBindParameter** with *ParameterNumber* set to the ordinal of a bound parameter marker automatically releases the previous binding.</span></span>

 <span data-ttu-id="f4537-111">Un'applicazione può inoltre associare parametri a matrici di variabili di programma per elaborare un'istruzione SQL in batch.</span><span class="sxs-lookup"><span data-stu-id="f4537-111">An application can also bind parameters to arrays of program variables to process an SQL statement in batches.</span></span> <span data-ttu-id="f4537-112">Sono disponibili due tipi diversi di associazione di matrici:</span><span class="sxs-lookup"><span data-stu-id="f4537-112">There are two types of array binding:</span></span>

-   <span data-ttu-id="f4537-113">L'associazione per colonna viene eseguita quando ogni singolo parametro viene associato alla relativa matrice di variabili.</span><span class="sxs-lookup"><span data-stu-id="f4537-113">Column-wise binding is done when each individual parameter is bound to its own array of variables.</span></span>

     <span data-ttu-id="f4537-114">L'associazione per colonna viene specificata chiamando [SQLSetStmtAttr](../native-client-odbc-api/sqlsetstmtattr.md) con *Attribute* impostato su SQL_ATTR_PARAM_BIND_TYPE e *ValuePtr* impostato su SQL_PARAM_BIND_BY_COLUMN.</span><span class="sxs-lookup"><span data-stu-id="f4537-114">Column-wise binding is specified by calling [SQLSetStmtAttr](../native-client-odbc-api/sqlsetstmtattr.md) with *Attribute* set to SQL_ATTR_PARAM_BIND_TYPE and *ValuePtr* set to SQL_PARAM_BIND_BY_COLUMN.</span></span>

-   <span data-ttu-id="f4537-115">L'associazione per riga viene eseguita quando tutti i parametri nell'istruzione SQL vengono associati come unità a una matrice di strutture contenente le singole variabili per i parametri.</span><span class="sxs-lookup"><span data-stu-id="f4537-115">Row-wise binding is done when all of the parameters in the SQL statement are bound as a unit to an array of structures that contain the individual variables for the parameters.</span></span>

     <span data-ttu-id="f4537-116">L'associazione per riga viene specificata chiamando **SQLSetStmtAttr** con *Attribute* impostato su SQL_ATTR_PARAM_BIND_TYPE e *ValuePtr* impostato sulle dimensioni della struttura che contiene le variabili di programma.</span><span class="sxs-lookup"><span data-stu-id="f4537-116">Row-wise binding is specified by calling **SQLSetStmtAttr** with *Attribute* set to SQL_ATTR_PARAM_BIND_TYPE and *ValuePtr* set to the size of the structure holding the program variables.</span></span>

 <span data-ttu-id="f4537-117">Quando il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver ODBC di Native client invia parametri di stringa di tipo carattere o binario al server, i valori vengono ripresi alla lunghezza specificata nel parametro **SQLBindParameter** *ColumnSize* .</span><span class="sxs-lookup"><span data-stu-id="f4537-117">When the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver sends character or binary string parameters to the server, it pads the values to the length specified in **SQLBindParameter** *ColumnSize* parameter.</span></span> <span data-ttu-id="f4537-118">Se un'applicazione ODBC 2. x specifica 0 per *ColumnSize*, il driver riempie il valore del parametro con la precisione del tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="f4537-118">If an ODBC 2.x application specifies 0 for *ColumnSize*, the driver pads the parameter value to the precision of the data type.</span></span> <span data-ttu-id="f4537-119">La precisione è 8000 in caso di connessione a server [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], 255 in caso di connessione a versioni precedenti di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f4537-119">The precision is 8000 when connected to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] servers, 255 when connected to earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="f4537-120">*ColumnSize* è in byte per le colonne variant.</span><span class="sxs-lookup"><span data-stu-id="f4537-120">*ColumnSize* is in bytes for variant columns.</span></span>

 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="f4537-121">supporta la definizione di nomi per parametri delle stored procedure.</span><span class="sxs-lookup"><span data-stu-id="f4537-121">supports defining names for stored procedure parameters.</span></span> <span data-ttu-id="f4537-122">Anche in ODBC 3.5 è stato introdotto il supporto per parametri denominati utilizzati per chiamare stored procedure [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f4537-122">ODBC 3.5 also introduced support for named parameters used when calling [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] stored procedures.</span></span> <span data-ttu-id="f4537-123">Questo supporto può essere utilizzato per effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f4537-123">This support can be used to:</span></span>

-   <span data-ttu-id="f4537-124">Chiamare una stored procedure e fornire valori per un subset dei parametri definiti per la stored procedure.</span><span class="sxs-lookup"><span data-stu-id="f4537-124">Call a stored procedure and provide values for a subset of the parameters defined for the stored procedure.</span></span>

-   <span data-ttu-id="f4537-125">Specificare i parametri in un ordine diverso nell'applicazione rispetto all'ordine specificato alla creazione della stored procedure.</span><span class="sxs-lookup"><span data-stu-id="f4537-125">Specify the parameters in a different order in the application than the order specified when the stored procedure was created.</span></span>

 <span data-ttu-id="f4537-126">I parametri denominati sono supportati solo quando si utilizza l' [!INCLUDE[tsql](../../includes/tsql-md.md)] `EXECUTE` istruzione o la sequenza di escape ODBC CALL per eseguire un stored procedure.</span><span class="sxs-lookup"><span data-stu-id="f4537-126">Named parameters are only supported when using the [!INCLUDE[tsql](../../includes/tsql-md.md)] `EXECUTE` statement or the ODBC CALL escape sequence to execute a stored procedure.</span></span>

 <span data-ttu-id="f4537-127">Se per un parametro della stored procedure è impostato `SQL_DESC_NAME`, sarà necessario impostare `SQL_DESC_NAME` anche per tutti gli altri parametri della stored procedure nella query.</span><span class="sxs-lookup"><span data-stu-id="f4537-127">If `SQL_DESC_NAME` is set for a stored procedure parameter, all stored procedure parameters in the query should also set `SQL_DESC_NAME`.</span></span>  <span data-ttu-id="f4537-128">Se vengono usati valori letterali nelle chiamate di stored procedure, in cui sono `SQL_DESC_NAME` impostati i parametri, i valori letterali devono usare il formato *' nome* = *valore*', dove *nome* è il nome del parametro di stored procedure (ad esempio, @p1 ).</span><span class="sxs-lookup"><span data-stu-id="f4537-128">If literals are used in stored procedure calls, where parameters have `SQL_DESC_NAME` set, the literals should use the format *'name*=*value*', where *name* is the stored procedure parameter name (for example, @p1).</span></span> <span data-ttu-id="f4537-129">Per ulteriori informazioni, vedere [associazione di parametri in base al nome (parametri denominati)](https://go.microsoft.com/fwlink/?LinkId=167215).</span><span class="sxs-lookup"><span data-stu-id="f4537-129">For more information, see [Binding Parameters by Name (Named Parameters)](https://go.microsoft.com/fwlink/?LinkId=167215).</span></span>

## <a name="see-also"></a><span data-ttu-id="f4537-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f4537-130">See Also</span></span>
 [<span data-ttu-id="f4537-131">Utilizzo dei parametri delle istruzioni</span><span class="sxs-lookup"><span data-stu-id="f4537-131">Using Statement Parameters</span></span>](using-statement-parameters.md)


