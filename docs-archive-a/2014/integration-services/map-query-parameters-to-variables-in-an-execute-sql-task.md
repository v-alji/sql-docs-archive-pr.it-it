---
title: Eseguire il mapping dei parametri di query a variabili in un'attività Esegui SQL | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- queries [Integration Services], parameter mapping
- parameterized SQL commands [Integration Services]
- parameters [Integration Services]
- mapping query parameters to variables [Integration Services]
- Execute SQL task [Integration Services]
- variables [Integration Services], mapping parameters to
ms.assetid: 6a164349-dfcf-4995-80bc-d4e7aee52a83
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8511d70b40f2934680e1cb790763045c04e8204a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627870"
---
# <a name="map-query-parameters-to-variables-in-an-execute-sql-task"></a><span data-ttu-id="8e98b-102">Mapping di parametri di query a variabili in un'attività Esegui SQL</span><span class="sxs-lookup"><span data-stu-id="8e98b-102">Map Query Parameters to Variables in an Execute SQL Task</span></span>

  <span data-ttu-id="8e98b-103">In questo argomento viene descritto come utilizzare un'istruzione SQL con parametri nell'attività Esegui SQL e come creare mapping tra variabili e parametri dell'istruzione SQL.</span><span class="sxs-lookup"><span data-stu-id="8e98b-103">This topic describes how to use a parameterized SQL statement in the Execute SQL task and create mappings between variables and the parameters in the SQL statement.</span></span>  
  
 <span data-ttu-id="8e98b-104">Per sapere di più sull'attività Esegui SQL, sugli indicatori di parametro e sui nomi dei parametri usati con i diversi tipi di connessione, vedere [Attività Esegui SQL](control-flow/execute-sql-task.md) e [Parametri e codici restituiti nell'attività Esegui SQL](../../2014/integration-services/parameters-and-return-codes-in-the-execute-sql-task.md).</span><span class="sxs-lookup"><span data-stu-id="8e98b-104">To learn more about the Execute SQL task, the parameter markers, and parameter names you use with different connection types, see [Execute SQL Task](control-flow/execute-sql-task.md) and [Parameters and Return Codes in the Execute SQL Task](../../2014/integration-services/parameters-and-return-codes-in-the-execute-sql-task.md).</span></span>  
  
### <a name="to-map-a-query-parameter-to-a-variable"></a><span data-ttu-id="8e98b-105">Per eseguire il mapping di un parametro di query a una variabile</span><span class="sxs-lookup"><span data-stu-id="8e98b-105">To map a query parameter to a variable</span></span>  
  
1.  <span data-ttu-id="8e98b-106">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]aprire il pacchetto di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] che si desidera utilizzare.</span><span class="sxs-lookup"><span data-stu-id="8e98b-106">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package you want to work with.</span></span>  
  
2.  <span data-ttu-id="8e98b-107">In Esplora soluzioni fare doppio clic sul pacchetto per aprirlo.</span><span class="sxs-lookup"><span data-stu-id="8e98b-107">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="8e98b-108">Fare clic sulla scheda **Flusso di controllo** .</span><span class="sxs-lookup"><span data-stu-id="8e98b-108">Click the **Control Flow** tab.</span></span>  
  
4.  <span data-ttu-id="8e98b-109">Se il pacchetto non include già un'attività Esegui SQL, aggiungerne una al flusso di controllo del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="8e98b-109">If the package does not already include an Execute SQL task, add one to the control flow of the package.</span></span> <span data-ttu-id="8e98b-110">Per altre informazioni, vedere [aggiungere o eliminare un'attività o un contenitore in un flusso di controllo](control-flow/add-or-delete-a-task-or-a-container-in-a-control-flow.md)</span><span class="sxs-lookup"><span data-stu-id="8e98b-110">For more information, see [Add or Delete a Task or a Container in a Control Flow](control-flow/add-or-delete-a-task-or-a-container-in-a-control-flow.md)</span></span>  
  <span data-ttu-id="8e98b-111">.</span><span class="sxs-lookup"><span data-stu-id="8e98b-111">.</span></span>  
  
5.  <span data-ttu-id="8e98b-112">Fare doppio clic sull'attività Esegui SQL.</span><span class="sxs-lookup"><span data-stu-id="8e98b-112">Double-click the Execute SQL task.</span></span>  
  
6.  <span data-ttu-id="8e98b-113">Specificare un comando SQL con parametri in uno dei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="8e98b-113">Provide a parameterized SQL command in one of the following ways:</span></span>  
  
    -   <span data-ttu-id="8e98b-114">Usare l'input diretto e digitare il comando SQL nella proprietà SQLStatement.</span><span class="sxs-lookup"><span data-stu-id="8e98b-114">Use direct input and type the SQL command in the SQLStatement property.</span></span>  
  
    -   <span data-ttu-id="8e98b-115">Usare l'input diretto, fare clic su **Compila query**, quindi creare un comando SQL usando gli strumenti grafici disponibili in Generatore query.</span><span class="sxs-lookup"><span data-stu-id="8e98b-115">Use direct input, click **Build Query**, and then create an SQL command using the graphical tools that the Query Builder provides.</span></span>  
  
    -   <span data-ttu-id="8e98b-116">Utilizzare una connessione file e quindi fare riferimento al file che contiene il comando SQL.</span><span class="sxs-lookup"><span data-stu-id="8e98b-116">Use a file connection and then reference the file that contains the SQL command.</span></span>  
  
    -   <span data-ttu-id="8e98b-117">Utilizzare una variabile e quindi fare riferimento alla variabile che contiene il comando SQL.</span><span class="sxs-lookup"><span data-stu-id="8e98b-117">Use a variable and then reference the variable that contains the SQL command.</span></span>  
  
     <span data-ttu-id="8e98b-118">I marcatori di parametro che è possibile utilizzare nelle istruzioni SQL con parametri dipendono dal tipo di connessione utilizzato dall'attività Esegui SQL.</span><span class="sxs-lookup"><span data-stu-id="8e98b-118">The parameter markers that you use in parameterized SQL statements depend on the connection type that the Execute SQL task uses.</span></span>  
  
    |<span data-ttu-id="8e98b-119">Tipo di connessione</span><span class="sxs-lookup"><span data-stu-id="8e98b-119">Connection type</span></span>|<span data-ttu-id="8e98b-120">Marcatore di parametro</span><span class="sxs-lookup"><span data-stu-id="8e98b-120">Parameter marker</span></span>|  
    |---------------------|----------------------|  
    |<span data-ttu-id="8e98b-121">ADO</span><span class="sxs-lookup"><span data-stu-id="8e98b-121">ADO</span></span>|<span data-ttu-id="8e98b-122">?</span><span class="sxs-lookup"><span data-stu-id="8e98b-122">?</span></span>|  
    |<span data-ttu-id="8e98b-123">ADO.NET e SQLMOBILE</span><span class="sxs-lookup"><span data-stu-id="8e98b-123">ADO.NET and SQLMOBILE</span></span>|@\<parameter name>|  
    |<span data-ttu-id="8e98b-124">ODBC</span><span class="sxs-lookup"><span data-stu-id="8e98b-124">ODBC</span></span>|<span data-ttu-id="8e98b-125">?</span><span class="sxs-lookup"><span data-stu-id="8e98b-125">?</span></span>|  
    |<span data-ttu-id="8e98b-126">EXCEL e OLE DB</span><span class="sxs-lookup"><span data-stu-id="8e98b-126">EXCEL and OLE DB</span></span>|<span data-ttu-id="8e98b-127">?</span><span class="sxs-lookup"><span data-stu-id="8e98b-127">?</span></span>|  
  
     <span data-ttu-id="8e98b-128">Nella tabella seguente sono elencati esempi di comandi SELECT per tipo di gestione connessione.</span><span class="sxs-lookup"><span data-stu-id="8e98b-128">The following table lists examples of the SELECT command by connection manager type.</span></span> <span data-ttu-id="8e98b-129">I parametri specificano i valori del filtro per la clausola WHERE.</span><span class="sxs-lookup"><span data-stu-id="8e98b-129">Parameters provide the filter values in the WHERE clauses.</span></span> <span data-ttu-id="8e98b-130">Negli esempi l'istruzione SELECT viene usata per recuperare dalla tabella **Product** del database [!INCLUDE[ssSampleDBUserInputNonLocal](../includes/sssampledbuserinputnonlocal-md.md)] i prodotti con **ProductID** compreso tra i valori specificati da due parametri.</span><span class="sxs-lookup"><span data-stu-id="8e98b-130">The examples use SELECT to return products from the **Product** table in [!INCLUDE[ssSampleDBUserInputNonLocal](../includes/sssampledbuserinputnonlocal-md.md)] that have a **ProductID** greater than and less than the values specified by two parameters.</span></span>  
  
    |<span data-ttu-id="8e98b-131">Tipo di connessione</span><span class="sxs-lookup"><span data-stu-id="8e98b-131">Connection type</span></span>|<span data-ttu-id="8e98b-132">Sintassi dell'istruzione SELECT</span><span class="sxs-lookup"><span data-stu-id="8e98b-132">SELECT syntax</span></span>|  
    |---------------------|-------------------|  
    |<span data-ttu-id="8e98b-133">EXCEL, ODBC e OLEDB</span><span class="sxs-lookup"><span data-stu-id="8e98b-133">EXCEL, ODBC, and OLEDB</span></span>|`SELECT* FROM Production.Product WHERE ProductId > ? AND ProductID < ?`|  
    |<span data-ttu-id="8e98b-134">ADO</span><span class="sxs-lookup"><span data-stu-id="8e98b-134">ADO</span></span>|`SELECT* FROM Production.Product WHERE ProductId > ? AND ProductID < ?`|  
    |[!INCLUDE[vstecado](../includes/vstecado-md.md)]|`SELECT* FROM Production.Product WHERE ProductId > @parmMinProductID AND ProductID < @parmMaxProductID`|  
  
     <span data-ttu-id="8e98b-135">Per esempi di utilizzo di parametri con stored procedure, vedere [Parametri e codici restituiti nell'attività Esegui SQL](../../2014/integration-services/parameters-and-return-codes-in-the-execute-sql-task.md).</span><span class="sxs-lookup"><span data-stu-id="8e98b-135">For examples of using parameters with stored procedures, see [Parameters and Return Codes in the Execute SQL Task](../../2014/integration-services/parameters-and-return-codes-in-the-execute-sql-task.md).</span></span>  
  
7.  <span data-ttu-id="8e98b-136">Fare clic su **Mapping parametri**.</span><span class="sxs-lookup"><span data-stu-id="8e98b-136">Click **Parameter Mapping**.</span></span>  
  
8.  <span data-ttu-id="8e98b-137">Per aggiungere un mapping parametri, fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="8e98b-137">To add a parameter mapping, click **Add**.</span></span>  
  
9. <span data-ttu-id="8e98b-138">Specificare un nome nella casella **Nome parametro** .</span><span class="sxs-lookup"><span data-stu-id="8e98b-138">Provide a name in the **Parameter Name** box.</span></span>  
  
     <span data-ttu-id="8e98b-139">I nomi dei parametri utilizzati dipendono dal tipo di connessione utilizzato dall'attività Esegui SQL.</span><span class="sxs-lookup"><span data-stu-id="8e98b-139">The parameter names that you use depend on the connection type that the Execute SQL task uses.</span></span>  
  
    |<span data-ttu-id="8e98b-140">Tipo di connessione</span><span class="sxs-lookup"><span data-stu-id="8e98b-140">Connection type</span></span>|<span data-ttu-id="8e98b-141">Nome parametro</span><span class="sxs-lookup"><span data-stu-id="8e98b-141">Parameter name</span></span>|  
    |---------------------|--------------------|  
    |<span data-ttu-id="8e98b-142">ADO</span><span class="sxs-lookup"><span data-stu-id="8e98b-142">ADO</span></span>|<span data-ttu-id="8e98b-143">Param1, Param2, ...</span><span class="sxs-lookup"><span data-stu-id="8e98b-143">Param1, Param2, ...</span></span>|  
    |<span data-ttu-id="8e98b-144">ADO.NET e SQLMOBILE</span><span class="sxs-lookup"><span data-stu-id="8e98b-144">ADO.NET and SQLMOBILE</span></span>|@\<parameter name>|  
    |<span data-ttu-id="8e98b-145">ODBC</span><span class="sxs-lookup"><span data-stu-id="8e98b-145">ODBC</span></span>|<span data-ttu-id="8e98b-146">1, 2, 3, ...</span><span class="sxs-lookup"><span data-stu-id="8e98b-146">1, 2, 3, ...</span></span>|  
    |<span data-ttu-id="8e98b-147">EXCEL e OLE DB</span><span class="sxs-lookup"><span data-stu-id="8e98b-147">EXCEL and OLE DB</span></span>|<span data-ttu-id="8e98b-148">0, 1, 2, 3, ...</span><span class="sxs-lookup"><span data-stu-id="8e98b-148">0, 1, 2, 3, ...</span></span>|  
  
10. <span data-ttu-id="8e98b-149">Selezionare una variabile nell'elenco **Nome variabile** .</span><span class="sxs-lookup"><span data-stu-id="8e98b-149">From the **Variable Name** list, select a variable.</span></span> <span data-ttu-id="8e98b-150">Per altre informazioni, vedere [Aggiungere, eliminare o modificare l'ambito di una variabile definita dall'utente in un pacchetto](../../2014/integration-services/add-delete-change-scope-of-user-defined-variable-in-a-package.md).</span><span class="sxs-lookup"><span data-stu-id="8e98b-150">For more information, see [Add, Delete, Change Scope of User-Defined Variable in a Package](../../2014/integration-services/add-delete-change-scope-of-user-defined-variable-in-a-package.md).</span></span>  
  
11. <span data-ttu-id="8e98b-151">Nell'elenco **Direzione** specificare se il parametro è un input, un output o un valore restituito.</span><span class="sxs-lookup"><span data-stu-id="8e98b-151">In the **Direction** list, specify if the parameter is an input, an output, or a return value.</span></span>  
  
12. <span data-ttu-id="8e98b-152">Nell'elenco **Tipo di dati** impostare il tipo di dati del parametro.</span><span class="sxs-lookup"><span data-stu-id="8e98b-152">In the **Data Type** list, set the data type of the parameter.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="8e98b-153">Il tipo di dati del parametro deve essere compatibile con quello della variabile.</span><span class="sxs-lookup"><span data-stu-id="8e98b-153">The data type of the parameter must be compatible with the data type of the variable.</span></span>  
  
13. <span data-ttu-id="8e98b-154">Ripetere i passaggi da 8 a 11 per ogni parametro nell'istruzione SQL.</span><span class="sxs-lookup"><span data-stu-id="8e98b-154">Repeat steps 8 through 11 for each parameter in the SQL statement.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="8e98b-155">I mapping dei parametri devono essere specificati nello stesso ordine con cui compaiono i parametri nell'istruzione SQL.</span><span class="sxs-lookup"><span data-stu-id="8e98b-155">The order of parameter mappings must be the same as the order in which the parameters appear in the SQL statement.</span></span>  
  
14. <span data-ttu-id="8e98b-156">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="8e98b-156">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e98b-157">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8e98b-157">See Also</span></span>  
 <span data-ttu-id="8e98b-158">[Attività Esegui SQL](control-flow/execute-sql-task.md) </span><span class="sxs-lookup"><span data-stu-id="8e98b-158">[Execute SQL Task](control-flow/execute-sql-task.md) </span></span>  
 <span data-ttu-id="8e98b-159">[Parametri e codici restituiti nell'attività Esegui SQL](../../2014/integration-services/parameters-and-return-codes-in-the-execute-sql-task.md) </span><span class="sxs-lookup"><span data-stu-id="8e98b-159">[Parameters and Return Codes in the Execute SQL Task](../../2014/integration-services/parameters-and-return-codes-in-the-execute-sql-task.md) </span></span>  
 [<span data-ttu-id="8e98b-160">Variabili di Integration Services &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="8e98b-160">Integration Services &#40;SSIS&#41; Variables</span></span>](integration-services-ssis-variables.md)  
  
  
