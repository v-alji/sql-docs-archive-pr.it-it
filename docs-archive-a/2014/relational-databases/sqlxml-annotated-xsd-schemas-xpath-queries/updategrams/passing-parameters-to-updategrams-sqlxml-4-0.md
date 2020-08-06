---
title: Passaggio di parametri agli updategram (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- nullvalue attribute
- passing parameters [SQLXML]
- parameters [SQLXML]
- updategrams [SQLXML], passing parameters
- null values [SQLXML]
ms.assetid: 2354e6e7-1860-471f-8711-4e374c5a4ed2
author: rothja
ms.author: jroth
ms.openlocfilehash: 4bc29de2dab3d0bc3587cb21b7005c0c23dcf7c5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87634951"
---
# <a name="passing-parameters-to-updategrams-sqlxml-40"></a><span data-ttu-id="141f1-102">Passaggio di parametri agli updategram (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="141f1-102">Passing Parameters to Updategrams (SQLXML 4.0)</span></span>
  <span data-ttu-id="141f1-103">Gli updategram sono modelli e in quanto tali è possibile passare loro parametri.</span><span class="sxs-lookup"><span data-stu-id="141f1-103">Updategrams are templates; therefore, you can pass them parameters.</span></span> <span data-ttu-id="141f1-104">Per ulteriori informazioni sul passaggio di parametri ai modelli, vedere [considerazioni sulla sicurezza degli Updategram &#40;SQLXML 4,0&#41;](../security/updategram-security-considerations-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="141f1-104">For more information about passing parameters to templates, see [Updategram Security Considerations &#40;SQLXML 4.0&#41;](../security/updategram-security-considerations-sqlxml-4-0.md).</span></span>  
  
 <span data-ttu-id="141f1-105">Gli updategram consentono di passare NULL come valore di parametro.</span><span class="sxs-lookup"><span data-stu-id="141f1-105">Updategrams allow you to pass NULL as a parameter value.</span></span> <span data-ttu-id="141f1-106">Per passare il valore di parametro NULL, è necessario specificare l'attributo `nullvalue`.</span><span class="sxs-lookup"><span data-stu-id="141f1-106">To pass the NULL parameter value, you specify the `nullvalue` attribute.</span></span> <span data-ttu-id="141f1-107">Il valore assegnato all'attributo `nullvalue` viene quindi fornito come valore di parametro</span><span class="sxs-lookup"><span data-stu-id="141f1-107">The value that is assigned to the `nullvalue` attribute is then provided as the parameter value.</span></span> <span data-ttu-id="141f1-108">e considerato come NULL dagli updategram.</span><span class="sxs-lookup"><span data-stu-id="141f1-108">Updategrams treat this value as NULL.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="141f1-109">In `<sql:header>` e `<updg:header>` è necessario specificare `nullvalue` come non qualificato, mentre in `<updg:sync>``nullvalue` viene specificato come qualificato (ad esempio, `updg:nullvalue`).</span><span class="sxs-lookup"><span data-stu-id="141f1-109">In `<sql:header>` and `<updg:header>`, you should specify the `nullvalue` as unqualified; whereas, in `<updg:sync>`, you specify the `nullvalue` as qualified (for example, `updg:nullvalue`).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="141f1-110">Esempi</span><span class="sxs-lookup"><span data-stu-id="141f1-110">Examples</span></span>  
 <span data-ttu-id="141f1-111">Per creare esempi funzionanti utilizzando gli esempi seguenti, è necessario soddisfare i requisiti specificati nei [requisiti per l'esecuzione di esempi SQLXML](../../sqlxml/requirements-for-running-sqlxml-examples.md).</span><span class="sxs-lookup"><span data-stu-id="141f1-111">To create working samples using the following examples, you must meet the requirements specified in [Requirements for Running SQLXML Examples](../../sqlxml/requirements-for-running-sqlxml-examples.md).</span></span>  
  
 <span data-ttu-id="141f1-112">Prima di utilizzare gli esempi dell'updategram, si tenga presente quanto segue:</span><span class="sxs-lookup"><span data-stu-id="141f1-112">Before using the updategram examples, note the following:</span></span>  
  
-   <span data-ttu-id="141f1-113">Negli esempi viene utilizzato il mapping predefinito, ovvero non viene specificato alcuno schema di mapping nell'updategram.</span><span class="sxs-lookup"><span data-stu-id="141f1-113">The examples use default mapping (that is, no mapping schema is specified in the updategram).</span></span> <span data-ttu-id="141f1-114">Per ulteriori esempi di updategram che utilizzano schemi di mapping, vedere [specifica di uno schema di mapping con annotazioni in un Updategram &#40;SQLXML 4,0&#41;](specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="141f1-114">For more examples of updategrams that use mapping schemas, see [Specifying an Annotated Mapping Schema in an Updategram &#40;SQLXML 4.0&#41;](specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).</span></span>  
  
### <a name="a-passing-parameters-to-an-updategram"></a><span data-ttu-id="141f1-115">R.</span><span class="sxs-lookup"><span data-stu-id="141f1-115">A.</span></span> <span data-ttu-id="141f1-116">Passaggio di parametri a un updategram</span><span class="sxs-lookup"><span data-stu-id="141f1-116">Passing parameters to an updategram</span></span>  
 <span data-ttu-id="141f1-117">In questo esempio l'updategram modifica il cognome di un dipendente nella tabella HumanResources.Shift.</span><span class="sxs-lookup"><span data-stu-id="141f1-117">In this example, the updategram changes the last name of an employee in the HumanResources.Shift table.</span></span> <span data-ttu-id="141f1-118">All'updategram vengono passati due parametri: ShiftID, utilizzato per identificare in modo univoco un turno, e Name.</span><span class="sxs-lookup"><span data-stu-id="141f1-118">The updategram is passed two parameters: ShiftID, which is used to uniquely identify a shift, and Name.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
<updg:header>  
  <updg:param name="ShiftID"/>  
  <updg:param name="Name" />  
</updg:header>  
  <updg:sync >  
    <updg:before>  
       <HumanResources.Shift ShiftID="$ShiftID" />  
    </updg:before>  
    <updg:after>  
      <HumanResources.Shift Name="$Name" />  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
##### <a name="to-test-the-updategram"></a><span data-ttu-id="141f1-119">Per testare l'updategram</span><span class="sxs-lookup"><span data-stu-id="141f1-119">To test the updategram</span></span>  
  
1.  <span data-ttu-id="141f1-120">Copiare l'updategram sopra indicato in Blocco note e salvarlo in un file con il nome UpdategramWithParameters.xml.</span><span class="sxs-lookup"><span data-stu-id="141f1-120">Copy the updategram above into Notepad and save it to file as UpdategramWithParameters.xml.</span></span>  
  
2.  <span data-ttu-id="141f1-121">Preparare lo script di test SQLXML 4,0 (Sqlxml4test. vbs) nell' [utilizzo di ADO per eseguire query SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md) per eseguire l'updategram aggiungendo le righe seguenti dopo `cmd.Properties("Output Stream").Value = outStream` :</span><span class="sxs-lookup"><span data-stu-id="141f1-121">Prepare the SQLXML 4.0 test script (Sqlxml4test.vbs) in [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md) to execute the updategram by adding the following lines after the `cmd.Properties("Output Stream").Value = outStream`:</span></span>  
  
    ```  
    cmd.NamedParameters = True  
    ' CreateParameter arguments: Name, Type, Direction, Size, Value  
    cmd.Parameters.Append cmd.CreateParameter("@ShiftID",  2, 1,  0, 1)  
    cmd.Parameters.Append cmd.CreateParameter("@Name",   200, 1, 50, "New Name")  
    ```  
  
### <a name="b-passing-null-as-a-parameter-value-to-an-updategram"></a><span data-ttu-id="141f1-122">B.</span><span class="sxs-lookup"><span data-stu-id="141f1-122">B.</span></span> <span data-ttu-id="141f1-123">Passaggio di NULL come valore di parametro a un updategram</span><span class="sxs-lookup"><span data-stu-id="141f1-123">Passing NULL as a parameter value to an updategram</span></span>  
 <span data-ttu-id="141f1-124">Durante l'esecuzione di un updategram, il valore "isnull" viene assegnato al parametro che si desidera impostare su NULL.</span><span class="sxs-lookup"><span data-stu-id="141f1-124">In executing an updategram, the "isnull" value is assigned to the parameter that you want to set to NULL.</span></span> <span data-ttu-id="141f1-125">L'updategram converte il valore di parametro "isnull" in NULL e lo elabora di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="141f1-125">Updategram converts the "isnulll" parameter value to NULL and processes it accordingly.</span></span>  
  
 <span data-ttu-id="141f1-126">Nell'updategram seguente la qualifica di un dipendente viene impostata su NULL:</span><span class="sxs-lookup"><span data-stu-id="141f1-126">The following updategram sets an employee title to NULL:</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
<updg:header nullvalue="isnull" >  
  <updg:param name="EmployeeID"/>  
  <updg:param name="ManagerID" />  
</updg:header>  
  <updg:sync >  
    <updg:before>  
       <HumanResources.Employee EmployeeID="$EmployeeID" />  
    </updg:before>  
    <updg:after>  
      <HumanResources.Employee ManagerID="$ManagerID" />  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
##### <a name="to-test-the-updategram"></a><span data-ttu-id="141f1-127">Per testare l'updategram</span><span class="sxs-lookup"><span data-stu-id="141f1-127">To test the updategram</span></span>  
  
1.  <span data-ttu-id="141f1-128">Copiare l'updategram sopra indicato in Blocco note e salvarlo in un file con il nome UpdategramPassingNullvalues.xml.</span><span class="sxs-lookup"><span data-stu-id="141f1-128">Copy the updategram above into Notepad and save it to file as UpdategramPassingNullvalues.xml.</span></span>  
  
2.  <span data-ttu-id="141f1-129">Preparare lo script di test SQLXML 4,0 (Sqlxml4test. vbs) nell' [utilizzo di ADO per eseguire query SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md) per eseguire l'updategram aggiungendo le righe seguenti dopo `cmd.Properties("Output Stream").Value = outStream` :</span><span class="sxs-lookup"><span data-stu-id="141f1-129">Prepare the SQLXML 4.0 test script (Sqlxml4test.vbs) in [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md) to execute the updategram by adding the following lines after the `cmd.Properties("Output Stream").Value = outStream`:</span></span>  
  
    ```  
    cmd.NamedParameters = True  
    ' CreateParameter arguments: Name, Type, Direction, Size, Value   
    cmd.Parameters.Append cmd.CreateParameter("@EmployeeID", 3, 1, 0, 1)  
    cmd.Parameters.Append cmd.CreateParameter("@ManagerID",  3, 1, 0, Null)  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="141f1-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="141f1-130">See Also</span></span>  
 [<span data-ttu-id="141f1-131">Considerazioni sulla sicurezza degli updategram &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="141f1-131">Updategram Security Considerations &#40;SQLXML 4.0&#41;</span></span>](../security/updategram-security-considerations-sqlxml-4-0.md)  
  
  
