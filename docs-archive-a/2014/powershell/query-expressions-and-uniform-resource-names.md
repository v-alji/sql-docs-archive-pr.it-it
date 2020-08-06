---
title: Espressioni di query e Uniform Resource Name | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: scripting
ms.topic: conceptual
helpviewer_keywords:
- query expressions
- unique resource names
- URN
ms.assetid: e0d30dbe-7daf-47eb-8412-1b96792b6fb9
author: stevestein
ms.author: sstein
ms.openlocfilehash: db6e311dd7d8a824b0e2f22e538e15eefa9fd9ab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627861"
---
# <a name="query-expressions-and-uniform-resource-names"></a><span data-ttu-id="75516-102">Espressioni di query e Uniform Resource Name</span><span class="sxs-lookup"><span data-stu-id="75516-102">Query Expressions and Uniform Resource Names</span></span>
  <span data-ttu-id="75516-103">I modelli SMO ( [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Management Object) e gli snap-in PowerShell per [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] usano due tipi di stringhe di espressione simili alle espressioni XPath.</span><span class="sxs-lookup"><span data-stu-id="75516-103">The [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Management Object (SMO) models and [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] PowerShell snap-ins use two types of expression strings that are similar to XPath expressions.</span></span> <span data-ttu-id="75516-104">Le espressioni di query sono stringhe che specificano un set di criteri utilizzato per enumerare uno o più oggetti in una gerarchia del modello a oggetti.</span><span class="sxs-lookup"><span data-stu-id="75516-104">Query expressions are strings that specify a set of criteria used to enumerate one or more objects in an object model hierarchy.</span></span> <span data-ttu-id="75516-105">Un Unique Resource Name (URN) è un tipo specifico di stringa di espressione di query che identifica un singolo oggetto in modo univoco.</span><span class="sxs-lookup"><span data-stu-id="75516-105">A Uniform Resource Name (URN) is a specific type of query expression string that uniquely identifies a single object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75516-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="75516-106">Syntax</span></span>  
  
```
      Object1  
      [<FilterExpression1>]/ ... /ObjectN[<FilterExpressionN>]<FilterExpression>::=  
<PropertyExpression> [and <PropertyExpression>][...n]  
  
<PropertyExpression>::=@BooleanPropertyName=true()  
 | @BooleanPropertyName=false()  
 | contains(@StringPropertyName, 'PatternString')  
  | @StringPropertyName='String'  
 | @DatePropertyName=datetime('DateString')  
 | is_null(@PropertyName)  
 | not(<PropertyExpression>)  
```  
  
## <a name="arguments"></a><span data-ttu-id="75516-107">Argomenti</span><span class="sxs-lookup"><span data-stu-id="75516-107">Arguments</span></span>  
 <span data-ttu-id="75516-108">*Object*</span><span class="sxs-lookup"><span data-stu-id="75516-108">*Object*</span></span>  
 <span data-ttu-id="75516-109">Specifica il tipo di oggetto che è rappresentato in corrispondenza del nodo della stringa di espressione.</span><span class="sxs-lookup"><span data-stu-id="75516-109">Specifies the type of object that is represented at that node of the expression string.</span></span> <span data-ttu-id="75516-110">Ciascun oggetto rappresenta una classe di raccolte dai seguenti spazi dei nomi del modello a oggetti SMO:</span><span class="sxs-lookup"><span data-stu-id="75516-110">Each object represents a collection class from these SMO object model namespaces:</span></span>  
  
 <xref:Microsoft.SqlServer.Management.Smo>  
  
 <xref:Microsoft.SqlServer.Management.Smo.Agent>  
  
 <xref:Microsoft.SqlServer.Management.Smo.Broker>  
  
 <xref:Microsoft.SqlServer.Management.Smo.Mail>  
  
 <xref:Microsoft.SqlServer.Management.Dmf>  
  
 <xref:Microsoft.SqlServer.Management.Facets>  
  
 <xref:Microsoft.SqlServer.Management.RegisteredServers>  
  
 <xref:Microsoft.SqlServer.Management.Smo.RegSvrEnum>  
  
 <span data-ttu-id="75516-111">Ad esempio, specificare Server per la classe **ServerCollection** , Database per la classe **DatabaseCollection** .</span><span class="sxs-lookup"><span data-stu-id="75516-111">For example, specify Server for the **ServerCollection** class, Database for the **DatabaseCollection** class.</span></span>  
  
 <span data-ttu-id="75516-112">\@*PropertyName*</span><span class="sxs-lookup"><span data-stu-id="75516-112">\@*PropertyName*</span></span>  
 <span data-ttu-id="75516-113">Specifica il nome di una delle proprietà della classe associato all'oggetto specificato in *Object*.</span><span class="sxs-lookup"><span data-stu-id="75516-113">Specifies the name of one of the properties of the class that is associated with the object specified in *Object*.</span></span> <span data-ttu-id="75516-114">Il nome della proprietà deve essere preceduto dal carattere \@.</span><span class="sxs-lookup"><span data-stu-id="75516-114">The name of the property must be prefixed with the \@ character.</span></span> <span data-ttu-id="75516-115">Ad esempio, specificare \@ IsAnsiNull per la proprietà della classe di **database** **IsAnsiNull**.</span><span class="sxs-lookup"><span data-stu-id="75516-115">For example, specify \@IsAnsiNull for the **Database** class property **IsAnsiNull**.</span></span>  
  
 <span data-ttu-id="75516-116">\@*BooleanPropertyName*=true()</span><span class="sxs-lookup"><span data-stu-id="75516-116">\@*BooleanPropertyName*=true()</span></span>  
 <span data-ttu-id="75516-117">Enumera tutti gli oggetti in cui la proprietà Boolean specificata è impostata su TRUE.</span><span class="sxs-lookup"><span data-stu-id="75516-117">Enumerates all objects where the specified Boolean property is set to TRUE.</span></span>  
  
 <span data-ttu-id="75516-118">\@*BooleanPropertyName*=false()</span><span class="sxs-lookup"><span data-stu-id="75516-118">\@*BooleanPropertyName*=false()</span></span>  
 <span data-ttu-id="75516-119">Enumera tutti gli oggetti in cui la proprietà Boolean specificata è impostata su FALSE.</span><span class="sxs-lookup"><span data-stu-id="75516-119">Enumerates all objects where the specified Boolean property is set to FALSE.</span></span>  
  
 <span data-ttu-id="75516-120">Contains ( \@ *StringtPropertyName*,'*PatternString*')</span><span class="sxs-lookup"><span data-stu-id="75516-120">contains(\@*StringPropertyName*, '*PatternString*')</span></span>  
 <span data-ttu-id="75516-121">Enumera tutti gli oggetti in cui la proprietà della stringa specificata contiene almeno un'occorrenza del set di caratteri specificato in '*PatternString*'.</span><span class="sxs-lookup"><span data-stu-id="75516-121">Enumerates all objects where the specified string property contains at least one occurrence of the set of characters that is specified in '*PatternString*'.</span></span>  
  
 <span data-ttu-id="75516-122">\@*StringPropertyName*='*PatternString*'</span><span class="sxs-lookup"><span data-stu-id="75516-122">\@*StringPropertyName*='*PatternString*'</span></span>  
 <span data-ttu-id="75516-123">Enumera tutti gli oggetti in cui il valore della proprietà della stringa specificata è esattamente uguale al modello di caratteri specificato in '*PatternString*'.</span><span class="sxs-lookup"><span data-stu-id="75516-123">Enumerates all objects where the value of the specified string property is exactly the same as the character pattern that is specified in '*PatternString*'.</span></span>  
  
 <span data-ttu-id="75516-124">\@*DatePropertyName*= datetime('*DateString*')</span><span class="sxs-lookup"><span data-stu-id="75516-124">\@*DatePropertyName*= datetime('*DateString*')</span></span>  
 <span data-ttu-id="75516-125">Enumera tutti gli oggetti in cui il valore della proprietà Date specificata corrisponde alla data specificata in '*DateString*'.</span><span class="sxs-lookup"><span data-stu-id="75516-125">Enumerates all objects where the value of the specified date property matches the date that is specified in '*DateString*'.</span></span> <span data-ttu-id="75516-126">*DateString* deve essere nel formato aaaa-mm-gg oo:mi:ss.mmm</span><span class="sxs-lookup"><span data-stu-id="75516-126">*DateString* must follow the format yyyy-mm-dd hh:mi:ss.mmm</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="75516-127">aaaa</span><span class="sxs-lookup"><span data-stu-id="75516-127">yyyy</span></span>|<span data-ttu-id="75516-128">Anno espresso a quattro cifre.</span><span class="sxs-lookup"><span data-stu-id="75516-128">Four digit year.</span></span>|  
|<span data-ttu-id="75516-129">MM</span><span class="sxs-lookup"><span data-stu-id="75516-129">mm</span></span>|<span data-ttu-id="75516-130">Mese a due cifre (da 01 a 12)</span><span class="sxs-lookup"><span data-stu-id="75516-130">Two digit month (01 through 12).</span></span>|  
|<span data-ttu-id="75516-131">gg</span><span class="sxs-lookup"><span data-stu-id="75516-131">dd</span></span>|<span data-ttu-id="75516-132">Data a due cifre (da 01 a 31)</span><span class="sxs-lookup"><span data-stu-id="75516-132">Two digit date (01 through 31).</span></span>|  
|<span data-ttu-id="75516-133">hh</span><span class="sxs-lookup"><span data-stu-id="75516-133">hh</span></span>|<span data-ttu-id="75516-134">Ora a 2 cifre nel formato a 24 ore (da 01 a 23)</span><span class="sxs-lookup"><span data-stu-id="75516-134">Two digit hour using a 24 hour clock (01 through 23).</span></span>|  
|<span data-ttu-id="75516-135">mi</span><span class="sxs-lookup"><span data-stu-id="75516-135">mi</span></span>|<span data-ttu-id="75516-136">Minuti a due cifre (da 01 a 59)</span><span class="sxs-lookup"><span data-stu-id="75516-136">Two digit minutes (01 through 59).</span></span>|  
|<span data-ttu-id="75516-137">ss</span><span class="sxs-lookup"><span data-stu-id="75516-137">ss</span></span>|<span data-ttu-id="75516-138">Secondi a due cifre (da 01 a 59)</span><span class="sxs-lookup"><span data-stu-id="75516-138">Two digit seconds (01 through 59).</span></span>|  
|<span data-ttu-id="75516-139">mmm</span><span class="sxs-lookup"><span data-stu-id="75516-139">mmm</span></span>|<span data-ttu-id="75516-140">Numero di millisecondi (da 001 a 999).</span><span class="sxs-lookup"><span data-stu-id="75516-140">Number of milliseconds (001 through 999).</span></span>|  
  
 <span data-ttu-id="75516-141">Le date specificate in questo formato possono essere valutate rispetto a qualsiasi formato della data archiviato in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="75516-141">The dates that are specified in this format can be evaluated against any date format that is stored in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="75516-142">is_null ( \@ *PropertyName*)</span><span class="sxs-lookup"><span data-stu-id="75516-142">is_null(\@*PropertyName*)</span></span>  
 <span data-ttu-id="75516-143">Enumera tutti gli oggetti in cui la proprietà specificata è impostata su NULL.</span><span class="sxs-lookup"><span data-stu-id="75516-143">Enumerates all objects where the specified property has a value of NULL.</span></span>  
  
 <span data-ttu-id="75516-144">Not ( \<*PropertyExpression*> )</span><span class="sxs-lookup"><span data-stu-id="75516-144">not(\<*PropertyExpression*>)</span></span>  
 <span data-ttu-id="75516-145">Nega il valore della valutazione della *PropertyExpression*, enumerando tutti gli oggetti che non corrispondono alla condizione specificata nella *PropertyExpression*.</span><span class="sxs-lookup"><span data-stu-id="75516-145">Negates the evaluation value of the *PropertyExpression*, enumerating all objects that do not match the condition specified in *PropertyExpression*.</span></span> <span data-ttu-id="75516-146">Ad esempio, not(contains(\@Name, 'xyz')) enumera tutti gli oggetti i cui nomi non contengono la stringa xyz.</span><span class="sxs-lookup"><span data-stu-id="75516-146">For example, not(contains(\@Name, 'xyz')) enumerates all objects that do not have the string xyz in their names.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="75516-147">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="75516-147">Remarks</span></span>  
 <span data-ttu-id="75516-148">Le espressioni di query sono stringhe che enumerano i nodi in una gerarchia del modello SMO.</span><span class="sxs-lookup"><span data-stu-id="75516-148">Query expressions are strings that enumerate the nodes in an SMO model hierarchy.</span></span> <span data-ttu-id="75516-149">Ciascun nodo dispone di un'espressione di filtro che specifica i criteri per determinare quali oggetti in corrispondenza di un dato nodo sono enumerati.</span><span class="sxs-lookup"><span data-stu-id="75516-149">Each node has a filter expression that specifies the criteria for determining which objects at that node are enumerated.</span></span> <span data-ttu-id="75516-150">Le espressioni di query vengono modellate sul linguaggio delle espressioni XPath.</span><span class="sxs-lookup"><span data-stu-id="75516-150">Query expressions are modeled on the XPath expression language.</span></span> <span data-ttu-id="75516-151">Le espressioni di query implementano un piccolo subset delle espressioni che sono supportate da XPath; inoltre dispongono di alcune estensioni che non si trovano in XPath.</span><span class="sxs-lookup"><span data-stu-id="75516-151">Query expressions implement a small subset of the expressions that are supported by XPath, and also have some extensions that are not found in XPath.</span></span> <span data-ttu-id="75516-152">Le espressioni XPath sono stringhe che specificano un set di criteri che vengono utilizzati per enumerare uno o più tag in un documento XML.</span><span class="sxs-lookup"><span data-stu-id="75516-152">XPath expressions are strings that specify a set of criteria that are used to enumerate one or more of the tags in an XML document.</span></span> <span data-ttu-id="75516-153">Per altre informazioni su XPath, vedere [W3C XPath Language](http://www.w3.org/TR/xpath20/).</span><span class="sxs-lookup"><span data-stu-id="75516-153">For more information about XPath, see [W3C XPath Language](http://www.w3.org/TR/xpath20/).</span></span>  
  
 <span data-ttu-id="75516-154">Le espressioni di query devono iniziare con un riferimento assoluto all'oggetto Server.</span><span class="sxs-lookup"><span data-stu-id="75516-154">Query expressions must start with an absolute reference to the Server object.</span></span> <span data-ttu-id="75516-155">Le espressioni relative con un carattere "/" iniziale non sono consentite.</span><span class="sxs-lookup"><span data-stu-id="75516-155">Relative expressions with a leading / are not allowed.</span></span> <span data-ttu-id="75516-156">La sequenza di oggetti che sono specificati in un'espressione di query deve seguire la gerarchia di oggetti Collection nel modello a oggetti associato.</span><span class="sxs-lookup"><span data-stu-id="75516-156">The sequence of objects that are specified in a query expression must follow the hierarchy of collection objects in the associated object model.</span></span> <span data-ttu-id="75516-157">Ad esempio, un'espressione di query che fa riferimento a oggetti nello spazio dei nomi Microsoft.SqlServer.Management.Smo deve iniziare con un nodo Server seguito da un nodo Database e così via.</span><span class="sxs-lookup"><span data-stu-id="75516-157">For example, a query expression that references objects in the Microsoft.SqlServer.Management.Smo namespace must start with a Server node followed by a Database node, and so on.</span></span>  
  
 <span data-ttu-id="75516-158">Se *\<FilterExpression>* non si specifica un oggetto per un oggetto, vengono enumerati tutti gli oggetti in tale nodo.</span><span class="sxs-lookup"><span data-stu-id="75516-158">If a *\<FilterExpression>* is not specified for an object, all the objects at that node are enumerated.</span></span>  
  
## <a name="uniform-resource-names-urn"></a><span data-ttu-id="75516-159">Unique Resource Name (URN)</span><span class="sxs-lookup"><span data-stu-id="75516-159">Uniform Resource Names (URN)</span></span>  
 <span data-ttu-id="75516-160">Gli URN sono un subset di espressioni di query.</span><span class="sxs-lookup"><span data-stu-id="75516-160">URNs are a subset of query expressions.</span></span> <span data-ttu-id="75516-161">Ciascun URN rappresenta un riferimento completo a un oggetto singolo.</span><span class="sxs-lookup"><span data-stu-id="75516-161">Each URN forms a fully-qualified reference to a single object.</span></span> <span data-ttu-id="75516-162">Il tipico URN utilizza la proprietà Name per identificare un singolo oggetto in corrispondenza di ciascun nodo.</span><span class="sxs-lookup"><span data-stu-id="75516-162">A typical URN uses the Name property to identify a single object at each node.</span></span> <span data-ttu-id="75516-163">Ad esempio, questo URN si riferisce a una colonna specifica:</span><span class="sxs-lookup"><span data-stu-id="75516-163">For example, this URN refers to a specific column:</span></span>  
  
```  
Server[@Name='MYCOMPUTER']/Database[@Name='AdventureWorks2012']/Table[@Name='SalesPerson' and @Schema='Sales']/Column[@Name='SalesPersonID']  
```  
  
## <a name="examples"></a><span data-ttu-id="75516-164">Esempi</span><span class="sxs-lookup"><span data-stu-id="75516-164">Examples</span></span>  
  
### <a name="a-enumerating-objects-using-false"></a><span data-ttu-id="75516-165">R.</span><span class="sxs-lookup"><span data-stu-id="75516-165">A.</span></span> <span data-ttu-id="75516-166">Enumerazione di oggetti utilizzando false()</span><span class="sxs-lookup"><span data-stu-id="75516-166">Enumerating objects using false()</span></span>  
 <span data-ttu-id="75516-167">Questa espressione di query enumera tutti i database il cui attributo **AutoClose** è impostato su False nell'istanza predefinita in **MyComputer**.</span><span class="sxs-lookup"><span data-stu-id="75516-167">This query expression enumerates all the databases that have the **AutoClose** attribute set to false in the default instance on **MyComputer**.</span></span>  
  
```  
Server[@Name='MYCOMPUTER']/Database[@AutoClose=false()]  
```  
  
### <a name="b-enumerating-objects-using-contains"></a><span data-ttu-id="75516-168">B.</span><span class="sxs-lookup"><span data-stu-id="75516-168">B.</span></span> <span data-ttu-id="75516-169">Enumerazione di oggetti utilizzando contains</span><span class="sxs-lookup"><span data-stu-id="75516-169">Enumerating objects using contains</span></span>  
 <span data-ttu-id="75516-170">Questa espressione di query enumera tutti i database per quali non viene fatta distinzione tra maiuscole e minuscole e i cui nomi contengono il carattere "m".</span><span class="sxs-lookup"><span data-stu-id="75516-170">This query expression enumerates all the databases that are case-insensitive and have the character 'm' in their name.</span></span>  
  
```  
Server[@Name='MYCOMPUTER']/Database[@CaseSensitive=false() and contains(@Name, 'm')]   
```  
  
### <a name="c-enumerating-objects-using-not"></a><span data-ttu-id="75516-171">C.</span><span class="sxs-lookup"><span data-stu-id="75516-171">C.</span></span> <span data-ttu-id="75516-172">Enumerazione di oggetti utilizzando not</span><span class="sxs-lookup"><span data-stu-id="75516-172">Enumerating objects using not</span></span>  
 <span data-ttu-id="75516-173">Questa espressione di query enumera tutte le tabelle di [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] che non sono nello schema **Production** e i cui nomi contengono la parola History:</span><span class="sxs-lookup"><span data-stu-id="75516-173">This query expression enumerates all of [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] tables that are not in the **Production** schema and contain the word History in the table name:</span></span>  
  
```  
Server[@Name='MYCOMPUTER']/Database[@Name='AdventureWorks2012']/Table[not(@Schema='Production') and contains(@Name, 'History')]  
```  
  
### <a name="d-not-supplying-a-filter-expression-for-the-final-node"></a><span data-ttu-id="75516-174">D.</span><span class="sxs-lookup"><span data-stu-id="75516-174">D.</span></span> <span data-ttu-id="75516-175">Mancata specifica di un'espressione di filtro per il nodo finale</span><span class="sxs-lookup"><span data-stu-id="75516-175">Not supplying a filter expression for the final node</span></span>  
 <span data-ttu-id="75516-176">Questa espressione di query enumera tutte le colonne nella tabella **AdventureWorks2012.Sales.SalesPerson** :</span><span class="sxs-lookup"><span data-stu-id="75516-176">This query expression enumerates all the columns in the **AdventureWorks2012.Sales.SalesPerson** table:</span></span>  
  
```  
Server[@Name='MYCOMPUTER']/Database[@Name='AdventureWorks2012"]/Table[@Schema='Sales' and @Name='SalesPerson']/Columns  
```  
  
### <a name="e-enumerating-objects-using-datetime"></a><span data-ttu-id="75516-177">E.</span><span class="sxs-lookup"><span data-stu-id="75516-177">E.</span></span> <span data-ttu-id="75516-178">Enumerazione di oggetti utilizzando datetime</span><span class="sxs-lookup"><span data-stu-id="75516-178">Enumerating objects using datetime</span></span>  
 <span data-ttu-id="75516-179">Questa espressione di query enumera tutte le tabelle create nel database [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] a un'ora specifica:</span><span class="sxs-lookup"><span data-stu-id="75516-179">This query expression enumerates all the tables that are created in the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] database at a specific time:</span></span>  
  
```  
Server[@Name='MYCOMPUTER']/Database[@Name='AdventureWorks2012"]/Table[@CreateDate=datetime('2008-03-21 19:49:32.647')]  
```  
  
### <a name="f-enumerating-objects-using-is_null"></a><span data-ttu-id="75516-180">F.</span><span class="sxs-lookup"><span data-stu-id="75516-180">F.</span></span> <span data-ttu-id="75516-181">Enumerazione di oggetti utilizzando is_null</span><span class="sxs-lookup"><span data-stu-id="75516-181">Enumerating objects using is_null</span></span>  
 <span data-ttu-id="75516-182">Questa espressione di query enumera tutte le tabelle nel database [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] le cui proprietà di data ultima modifica non sono impostate su NULL:</span><span class="sxs-lookup"><span data-stu-id="75516-182">This query expression enumerates all the tables in the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] database that do not have NULL for their date last modified property:</span></span>  
  
```  
Server[@Name='MYCOMPUTER']/Database[@Name='AdventureWorks2012"]/Table[Not(is_null(@DateLastModified))]  
```  
  
## <a name="see-also"></a><span data-ttu-id="75516-183">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="75516-183">See Also</span></span>  
 <span data-ttu-id="75516-184">[Cmdlet Invoke-PolicyEvaluation](../database-engine/invoke-policyevaluation-cmdlet.md) </span><span class="sxs-lookup"><span data-stu-id="75516-184">[Invoke-PolicyEvaluation cmdlet](../database-engine/invoke-policyevaluation-cmdlet.md) </span></span>  
 [<span data-ttu-id="75516-185">SQL Server Audit &#40;Database Engine&#41;</span><span class="sxs-lookup"><span data-stu-id="75516-185">SQL Server Audit &#40;Database Engine&#41;</span></span>](../relational-databases/security/auditing/sql-server-audit-database-engine.md)  
