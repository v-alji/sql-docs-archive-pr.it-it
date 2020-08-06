---
title: Chiamata a una stored procedure | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- calling stored procedures
- ODBC, stored procedures
- stored procedures [ODBC], calling
- SQL Server Native Client ODBC driver, stored procedures
- ODBC CALL escape sequence
- escape sequences [SQL Server]
- CALL statement
ms.assetid: d13737f4-f641-45bf-b56c-523e2ffc080f
author: rothja
ms.author: jroth
ms.openlocfilehash: c6fa704e45e4e85b479ae8a40a3e567bea1ec5e9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725639"
---
# <a name="calling-a-stored-procedure"></a><span data-ttu-id="069d7-102">Chiamata di una stored procedure</span><span class="sxs-lookup"><span data-stu-id="069d7-102">Calling a Stored Procedure</span></span>
  <span data-ttu-id="069d7-103">Il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver ODBC di Native Client supporta sia la sequenza di escape ODBC Call sia l' [!INCLUDE[tsql](../../includes/tsql-md.md)] istruzione [Execute](/sql/t-sql/language-elements/execute-transact-sql) per l'esecuzione di stored procedure. la sequenza di escape ODBC Call è il metodo preferito.</span><span class="sxs-lookup"><span data-stu-id="069d7-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver supports both the ODBC CALL escape sequence and the [!INCLUDE[tsql](../../includes/tsql-md.md)][EXECUTE](/sql/t-sql/language-elements/execute-transact-sql) statement for executing stored procedures; the ODBC CALL escape sequence is the preferred method.</span></span> <span data-ttu-id="069d7-104">L'utilizzo di sintassi ODBC consente a un'applicazione di recuperare i codici restituiti delle stored procedure e il driver ODBC di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client è anch'esso ottimizzato per l'utilizzo di un protocollo sviluppato in origine per l'invio di chiamate a procedure remote (RPC, Remote Procedure Call) tra computer che eseguono [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="069d7-104">Using ODBC syntax enables an application to retrieve the return codes of stored procedures and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver is also optimized to use a protocol originally developed for sending remote procedure (RPC) calls between computers running [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="069d7-105">Questo protocollo RPC migliora le prestazioni riducendo l'elaborazione dei parametri e l'analisi delle istruzioni eseguite sul server.</span><span class="sxs-lookup"><span data-stu-id="069d7-105">This RPC protocol increases performance by eliminating much of the parameter processing and statement parsing done on the server.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="069d7-106">Quando si chiamano [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] stored procedure utilizzando parametri denominati con ODBC (per altre informazioni, vedere [associazione di parametri in base al nome (parametri denominati)](https://go.microsoft.com/fwlink/?LinkID=209721)), i nomi dei parametri devono iniziare con il \@ carattere ''.</span><span class="sxs-lookup"><span data-stu-id="069d7-106">When calling [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] stored procedures using named parameters with ODBC (for more information, see [Binding Parameters by Name (Named Parameters)](https://go.microsoft.com/fwlink/?LinkID=209721)), the parameter names must start with the '\@' character.</span></span> <span data-ttu-id="069d7-107">Si tratta di una restrizione specifica di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="069d7-107">This is a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] specific restriction.</span></span> <span data-ttu-id="069d7-108">Il driver ODBC di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client applica questa limitazione in modo più restrittivo rispetto a MDAC (Microsoft Data Access Components).</span><span class="sxs-lookup"><span data-stu-id="069d7-108">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver enforces this restriction more strictly than the Microsoft Data Access Components (MDAC).</span></span>  
  
 <span data-ttu-id="069d7-109">La sequenza di escape ODBC CALL per la chiamata a una procedura è la seguente:</span><span class="sxs-lookup"><span data-stu-id="069d7-109">The ODBC CALL escape sequence for calling a procedure is:</span></span>  
  
 <span data-ttu-id="069d7-110">{[**? =**]**chiama**_procedure_name_[([*parametro*] [**,**[*parametro*]]...)]}</span><span class="sxs-lookup"><span data-stu-id="069d7-110">{[**?=**]**call**_procedure_name_[([*parameter*][**,**[*parameter*]]...)]}</span></span>  
  
 <span data-ttu-id="069d7-111">dove *procedure_name* specifica il nome di una routine e un *parametro* specifica un parametro di procedura.</span><span class="sxs-lookup"><span data-stu-id="069d7-111">where *procedure_name* specifies the name of a procedure and *parameter* specifies a procedure parameter.</span></span> <span data-ttu-id="069d7-112">I parametri denominati sono supportati solo nelle istruzioni che utilizzano la sequenza di escape ODBC CALL.</span><span class="sxs-lookup"><span data-stu-id="069d7-112">Named parameters are only supported in statements using the ODBC CALL escape sequence.</span></span>  
  
 <span data-ttu-id="069d7-113">Una procedura può avere zero o più parametri.</span><span class="sxs-lookup"><span data-stu-id="069d7-113">A procedure can have zero or more parameters.</span></span> <span data-ttu-id="069d7-114">Una procedura può inoltre restituire un valore, come indicato dall'indicatore di parametro facoltativo ?= all'inizio della sintassi.</span><span class="sxs-lookup"><span data-stu-id="069d7-114">It can also return a value (as indicated by the optional parameter marker ?= at the start of the syntax).</span></span> <span data-ttu-id="069d7-115">Se un parametro è un parametro di input/output, può essere un valore letterale o un marcatore di parametro.</span><span class="sxs-lookup"><span data-stu-id="069d7-115">If a parameter is an input or an input/output parameter, it can be a literal or a parameter marker.</span></span> <span data-ttu-id="069d7-116">Se il parametro è un parametro di output, deve essere un marcatore di parametro, in quanto l'output non è noto.</span><span class="sxs-lookup"><span data-stu-id="069d7-116">If the parameter is an output parameter, it must be a parameter marker because the output is unknown.</span></span> <span data-ttu-id="069d7-117">I marcatori di parametro devono essere associati con [SQLBindParameter](../../relational-databases/native-client-odbc-api/sqlbindparameter.md) prima dell'esecuzione dell'istruzione di chiamata di procedura.</span><span class="sxs-lookup"><span data-stu-id="069d7-117">Parameter markers must be bound with [SQLBindParameter](../../relational-databases/native-client-odbc-api/sqlbindparameter.md) before the procedure call statement is executed.</span></span>  
  
 <span data-ttu-id="069d7-118">I parametri di input e di input/output possono essere omessi dalle chiamate alle procedure.</span><span class="sxs-lookup"><span data-stu-id="069d7-118">Input and input/output parameters can be omitted from procedure calls.</span></span> <span data-ttu-id="069d7-119">Se una procedura viene chiamata con parentesi ma senza alcun parametro, il driver indica all'origine dati di utilizzare il valore predefinito per il primo parametro.</span><span class="sxs-lookup"><span data-stu-id="069d7-119">If a procedure is called with parentheses but without any parameters, the driver instructs the data source to use the default value for the first parameter.</span></span> <span data-ttu-id="069d7-120">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="069d7-120">For example:</span></span>  
  
 <span data-ttu-id="069d7-121">{**call** _procedure_name_**()**}</span><span class="sxs-lookup"><span data-stu-id="069d7-121">{**call** _procedure_name_**( )**}</span></span>  
  
 <span data-ttu-id="069d7-122">Se la procedura non include alcun parametro, può non essere eseguita.</span><span class="sxs-lookup"><span data-stu-id="069d7-122">If the procedure does not have any parameters, the procedure can fail.</span></span> <span data-ttu-id="069d7-123">Se una procedura viene chiamata senza parentesi, il driver non invia alcun valore di parametro.</span><span class="sxs-lookup"><span data-stu-id="069d7-123">If a procedure is called without parentheses, the driver does not send any parameter values.</span></span> <span data-ttu-id="069d7-124">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="069d7-124">For example:</span></span>  
  
 <span data-ttu-id="069d7-125">{**call** _procedure_name_}</span><span class="sxs-lookup"><span data-stu-id="069d7-125">{**call** _procedure_name_}</span></span>  
  
 <span data-ttu-id="069d7-126">È possibile specificare valori letterali per parametri di input e di input/output nelle chiamate alle procedure.</span><span class="sxs-lookup"><span data-stu-id="069d7-126">Literals can be specified for input and input/output parameters in procedure calls.</span></span> <span data-ttu-id="069d7-127">La procedura InsertOrder, ad esempio, include cinque parametri di input.</span><span class="sxs-lookup"><span data-stu-id="069d7-127">For example, the procedure InsertOrder has five input parameters.</span></span> <span data-ttu-id="069d7-128">La chiamata seguente a InsertOrder omette il primo parametro, fornisce un valore letterale per il secondo parametro e utilizza un marcatore di parametro per i parametri terzo, quarto e quinto.</span><span class="sxs-lookup"><span data-stu-id="069d7-128">The following call to InsertOrder omits the first parameter, provides a literal for the second parameter, and uses a parameter marker for the third, fourth, and fifth parameters.</span></span> <span data-ttu-id="069d7-129">I parametri sono numerati in sequenza, a partire dal valore 1.</span><span class="sxs-lookup"><span data-stu-id="069d7-129">(Parameters are numbered sequentially, beginning with a value of 1.)</span></span>  
  
```  
{call InsertOrder(, 10, ?, ?, ?)}  
```  
  
 <span data-ttu-id="069d7-130">Si noti che se si omette un parametro, la virgola che lo delimita rispetto ad altri parametri deve comunque essere presente.</span><span class="sxs-lookup"><span data-stu-id="069d7-130">Note that if a parameter is omitted, the comma delimiting it from other parameters must still appear.</span></span> <span data-ttu-id="069d7-131">Se si omette un parametro di input o di input/output, la procedura utilizza il valore predefinito del parametro.</span><span class="sxs-lookup"><span data-stu-id="069d7-131">If an input or input/output parameter is omitted, the procedure uses the default value of the parameter.</span></span> <span data-ttu-id="069d7-132">Altri modi di specificare il valore predefinito di un parametro di input o di input/output consistono nell'impostare il valore del buffer di lunghezza/indicatore associato al parametro su SQL_DEFAULT_PARAM oppure nell'utilizzare la parola chiave DEFAULT.</span><span class="sxs-lookup"><span data-stu-id="069d7-132">Other ways to specify the default value of an input or input/output parameter are to set the value of the length/indicator buffer bound to the parameter to SQL_DEFAULT_PARAM, or to use the DEFAULT keyword.</span></span>  
  
 <span data-ttu-id="069d7-133">Se si omette un parametro di input/output o se si fornisce un valore letterale per il parametro, il driver ignora il valore di output.</span><span class="sxs-lookup"><span data-stu-id="069d7-133">If an input/output parameter is omitted, or if a literal is supplied for the parameter, the driver discards the output value.</span></span> <span data-ttu-id="069d7-134">Analogamente, se il marcatore di parametro per il valore restituito di una procedura viene omesso, il driver ignora il valore restituito.</span><span class="sxs-lookup"><span data-stu-id="069d7-134">Similarly, if the parameter marker for the return value of a procedure is omitted, the driver discards the return value.</span></span> <span data-ttu-id="069d7-135">Se, infine, un'applicazione specifica un parametro di valore restituito per una procedura che non restituisce alcun valore, il driver imposta il valore per il buffer di lunghezza/indicatore associato al parametro su SQL_NULL_DATA.</span><span class="sxs-lookup"><span data-stu-id="069d7-135">Finally, if an application specifies a return value parameter for a procedure that does not return a value, the driver sets the value of the length/indicator buffer bound to the parameter to SQL_NULL_DATA.</span></span>  
  
## <a name="delimiters-in-call-statements"></a><span data-ttu-id="069d7-136">Delimitatori nelle istruzioni CALL</span><span class="sxs-lookup"><span data-stu-id="069d7-136">Delimiters in CALL Statements</span></span>  
 <span data-ttu-id="069d7-137">Il driver ODBC di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client supporta inoltre per impostazione predefinita un'opzione di compatibilità specifica della sequenza di escape ODBC {CALL}.</span><span class="sxs-lookup"><span data-stu-id="069d7-137">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver by default also supports a compatibility option specific to the ODBC { CALL } escape sequence.</span></span> <span data-ttu-id="069d7-138">Il driver accetta istruzioni CALL con un singolo set di virgolette doppie che delimitano l'intero nome di stored procedure:</span><span class="sxs-lookup"><span data-stu-id="069d7-138">The driver accepts CALL statements with only a single set of double quotation marks delimiting the entire stored procedure name:</span></span>  
  
```  
{ CALL "master.dbo.sp_who" }  
```  
  
 <span data-ttu-id="069d7-139">Per impostazione predefinita, il driver ODBC di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client accetta inoltre istruzioni CALL che seguono le regole ISO e racchiudono ogni identificatore tra virgolette doppie:</span><span class="sxs-lookup"><span data-stu-id="069d7-139">By default the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver also accepts CALL statements that follow the ISO rules and enclose each identifier in double quotation marks:</span></span>  
  
```  
{ CALL "master"."dbo"."sp_who" }  
```  
  
 <span data-ttu-id="069d7-140">Se eseguito con le impostazioni predefinite, tuttavia, il driver ODBC di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client non supporta l'utilizzo di alcuna forma di identificatore tra virgolette con identificatori che contengono caratteri non specificati come validi negli identificatori dallo standard ISO.</span><span class="sxs-lookup"><span data-stu-id="069d7-140">When running with the default settings, however, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver does not support using either form of quoted identifier with identifiers that contain characters not specified as legal in identifiers by the ISO standard.</span></span> <span data-ttu-id="069d7-141">Il driver, ad esempio, non può accedere a un stored procedure denominato **"My. proc"** utilizzando un'istruzione Call con identificatori delimitati:</span><span class="sxs-lookup"><span data-stu-id="069d7-141">For example, the driver cannot access a stored procedure named **"My.Proc"** using a CALL statement with quoted identifiers:</span></span>  
  
```  
{ CALL "MyDB"."MyOwner"."My.Proc" }  
```  
  
 <span data-ttu-id="069d7-142">Questa istruzione viene interpretata dal driver nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="069d7-142">This statement is interpreted by the driver as:</span></span>  
  
```  
{ CALL MyDB.MyOwner.My.Proc }  
```  
  
 <span data-ttu-id="069d7-143">Il server genera un errore che segnala che un server collegato denominato **mydb** non esiste.</span><span class="sxs-lookup"><span data-stu-id="069d7-143">The server raises an error that a linked server named **MyDB** does not exist.</span></span>  
  
 <span data-ttu-id="069d7-144">Il problema non si verifica quando si utilizzano identificatori tra parentesi. In questo caso, l'istruzione viene interpretata correttamente:</span><span class="sxs-lookup"><span data-stu-id="069d7-144">The issue does not exist when using bracketed identifiers, this statement is interpreted correctly:</span></span>  
  
```  
{ CALL [MyDB].[MyOwner].[My.Table] }  
```  
  
## <a name="see-also"></a><span data-ttu-id="069d7-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="069d7-145">See Also</span></span>  
 [<span data-ttu-id="069d7-146">Esecuzione delle stored procedure</span><span class="sxs-lookup"><span data-stu-id="069d7-146">Running Stored Procedures</span></span>](../../relational-databases/native-client-odbc-stored-procedures/running-stored-procedures.md)  
  
  
