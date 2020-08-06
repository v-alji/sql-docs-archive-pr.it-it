---
title: Eliminazione di dati mediante updategram XML (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- <after> block
- updategrams [SQLXML], deleting data
- <before> block
- mapping-schema attribute
- record deletions [SQLXML]
ms.assetid: 4fb116d7-7652-474a-a567-cb475a20765c
author: rothja
ms.author: jroth
ms.openlocfilehash: d941005c71dc33dd8c4f5c5cc15f645cd0e68177
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635981"
---
# <a name="deleting-data-using-xml-updategrams-sqlxml-40"></a><span data-ttu-id="67427-102">Eliminazione di dati mediante updategram XML (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="67427-102">Deleting Data Using XML Updategrams (SQLXML 4.0)</span></span>
  <span data-ttu-id="67427-103">Un updategram indica un'operazione di eliminazione quando un'istanza di record viene visualizzata nel **\<before>** blocco senza record corrispondenti nel **\<after>** blocco.</span><span class="sxs-lookup"><span data-stu-id="67427-103">An updategram indicates a delete operation when a record instance appears in the **\<before>** block with no corresponding records in the **\<after>** block.</span></span> <span data-ttu-id="67427-104">In questo caso, l'updategram elimina il record nel **\<before>** blocco dal database.</span><span class="sxs-lookup"><span data-stu-id="67427-104">In this case, the updategram deletes the record in the **\<before>** block from the database.</span></span>  
  
 <span data-ttu-id="67427-105">Di seguito viene illustrato il formato dell'updategram per un'operazione di eliminazione:</span><span class="sxs-lookup"><span data-stu-id="67427-105">This is the updategram format for a delete operation:</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync [mapping-schema="SampleSchema.xml"]  >  
   <updg:before>  
       <ElementName />  
      [<ElementName .../>... ]  
   </updg:before>  
    [<updg:after>  
    </updg:after>]  
  </updg:sync>  
</ROOT>  
```  
  
 <span data-ttu-id="67427-106">È possibile omettere il **\<after>** tag se l'updategram sta eseguendo solo un'operazione di eliminazione.</span><span class="sxs-lookup"><span data-stu-id="67427-106">You can omit the **\<after>** tag if the updategram is performing only a delete operation.</span></span> <span data-ttu-id="67427-107">Se non si specifica l'attributo facoltativo `mapping-schema` , l' **\<ElementName>** oggetto specificato nell'updategram esegue il mapping a una tabella di database e gli attributi o gli elementi figlio eseguono il mapping alle colonne nella tabella.</span><span class="sxs-lookup"><span data-stu-id="67427-107">If you do not specify the optional `mapping-schema` attribute, the **\<ElementName>** specified in the updategram maps to a database table and the child elements or attributes map to columns in the table.</span></span>  
  
 <span data-ttu-id="67427-108">Se un elemento specificato nell'updategram corrisponde a più di una riga nella tabella o non corrisponde ad alcuna riga, l'updategram restituisce un errore e Annulla l'intero **\<sync>** blocco.</span><span class="sxs-lookup"><span data-stu-id="67427-108">If an element specified in the updategram either matches more than one row in the table or does not match any row, the updategram returns an error and cancels the entire **\<sync>** block.</span></span> <span data-ttu-id="67427-109">Un elemento dell'updategram può eliminare un solo record per volta.</span><span class="sxs-lookup"><span data-stu-id="67427-109">Only one record at a time can be deleted by an element in the updategram.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="67427-110">Esempi</span><span class="sxs-lookup"><span data-stu-id="67427-110">Examples</span></span>  
 <span data-ttu-id="67427-111">Negli esempi presentati in questa sezione viene utilizzato il mapping predefinito, ovvero non viene specificato alcuno schema di mapping nell'updategram.</span><span class="sxs-lookup"><span data-stu-id="67427-111">Examples in this section use default mapping (that is, no mapping schema is specified in the updategram).</span></span> <span data-ttu-id="67427-112">Per ulteriori esempi di updategram che utilizzano schemi di mapping, vedere [specifica di uno schema di mapping con annotazioni in un Updategram &#40;SQLXML 4,0&#41;](specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="67427-112">For more examples of updategrams that use mapping schemas, see [Specifying an Annotated Mapping Schema in an Updategram &#40;SQLXML 4.0&#41;](specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).</span></span>  
  
 <span data-ttu-id="67427-113">Per creare esempi funzionanti utilizzando gli esempi seguenti, è necessario soddisfare i requisiti specificati nei [requisiti per l'esecuzione di esempi SQLXML](../../sqlxml/requirements-for-running-sqlxml-examples.md).</span><span class="sxs-lookup"><span data-stu-id="67427-113">To create working samples using the following examples, you must meet the requirements specified in [Requirements for Running SQLXML Examples](../../sqlxml/requirements-for-running-sqlxml-examples.md).</span></span>  
  
### <a name="a-deleting-a-record-by-using-an-updategram"></a><span data-ttu-id="67427-114">R.</span><span class="sxs-lookup"><span data-stu-id="67427-114">A.</span></span> <span data-ttu-id="67427-115">Eliminazione di un record mediante un updategram</span><span class="sxs-lookup"><span data-stu-id="67427-115">Deleting a record by using an updategram</span></span>  
 <span data-ttu-id="67427-116">Negli updategram seguenti vengono eliminati due record dalla tabella HumanResources.Shift.</span><span class="sxs-lookup"><span data-stu-id="67427-116">The following updategrams deletes two records from the HumanResources.Shift table.</span></span>  
  
 <span data-ttu-id="67427-117">In questi esempi l'updategram non specifica uno schema di mapping,</span><span class="sxs-lookup"><span data-stu-id="67427-117">In these examples, the updategram does not specify a mapping schema.</span></span> <span data-ttu-id="67427-118">pertanto utilizza il mapping predefinito nel quale il nome dell'elemento esegue il mapping a un nome di tabella e gli attributi o i sottoelementi eseguono il mapping alle colonne.</span><span class="sxs-lookup"><span data-stu-id="67427-118">Therefore, the updategram uses default mapping, in which the element name maps to table name and the attributes or subelements map to columns.</span></span>  
  
 <span data-ttu-id="67427-119">Il primo updategram è incentrato sugli attributi e identifica due turni (giorno-sera e sera-notte) nel **\<before>** blocco.</span><span class="sxs-lookup"><span data-stu-id="67427-119">This first updategram is attribute-centric and identifies two shifts (Day-Evening and Evening-Night) in the **\<before>** block.</span></span> <span data-ttu-id="67427-120">Poiché nel blocco non è presente alcun record corrispondente **\<after>** , si tratta di un'operazione di eliminazione.</span><span class="sxs-lookup"><span data-stu-id="67427-120">Because there is no corresponding record in the **\<after>** block, this is a delete operation.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
<updg:sync >  
  <updg:before>  
       <HumanResources.Shift ShiftID="4"  
                        Name="Day-Evening"  
                        StartTime="1900-01-01 11:00:00.000"  
                        EndTime="1900-01-01 19:00:00.000"  
                        ModifiedDate="2004-01-01 00:00:00.000" />  
       <HumanResources.Shift ShiftID="5"  
                        Name="Evening-Night"  
                        StartTime="1900-01-01 19:00:00.000"  
                        EndTime="1900-01-01 03:00:00.000"  
                        ModifiedDate="2004-01-01 00:00:00.000" />  
  </updg:before>  
  <updg:after>  
  </updg:after>  
</updg:sync>  
</ROOT>  
```  
  
##### <a name="to-test-the-updategram"></a><span data-ttu-id="67427-121">Per testare l'updategram</span><span class="sxs-lookup"><span data-stu-id="67427-121">To test the updategram</span></span>  
  
1.  <span data-ttu-id="67427-122">Completare l'esempio B ("inserimento di più record utilizzando un updategram") nell' [inserimento di dati tramite UPDATEGRAM XML &#40;SQLXML 4,0&#41;](inserting-data-using-xml-updategrams-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="67427-122">Complete example B ("Inserting multiple records by using an updategram") in [Inserting Data Using XML Updategrams &#40;SQLXML 4.0&#41;](inserting-data-using-xml-updategrams-sqlxml-4-0.md).</span></span>  
  
2.  <span data-ttu-id="67427-123">Copiare l'updategram precedente nel blocco note e salvarlo come Updategram-RemoveShifts.xml nella stessa cartella utilizzata per completare ("inserimento di più record utilizzando un updategram") nell' [inserimento di dati mediante UPDATEGRAM XML &#40;SQLXML 4,0&#41;](inserting-data-using-xml-updategrams-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="67427-123">Copy the updategram above to Notepad and save it as Updategram-RemoveShifts.xml in the same folder as was used to complete ("Inserting multiple records by using an updategram") in [Inserting Data Using XML Updategrams &#40;SQLXML 4.0&#41;](inserting-data-using-xml-updategrams-sqlxml-4-0.md).</span></span>  
  
3.  <span data-ttu-id="67427-124">Creare e utilizzare lo script di test SQLXML 4.0 (Sqlxml4test.vbs) per eseguire l'updategram.</span><span class="sxs-lookup"><span data-stu-id="67427-124">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the updategram.</span></span>  
  
     <span data-ttu-id="67427-125">Per ulteriori informazioni, vedere [utilizzo di ADO per eseguire query SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="67427-125">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67427-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="67427-126">See Also</span></span>  
 [<span data-ttu-id="67427-127">Considerazioni sulla sicurezza degli updategram &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="67427-127">Updategram Security Considerations &#40;SQLXML 4.0&#41;</span></span>](../security/updategram-security-considerations-sqlxml-4-0.md)  
  
  
