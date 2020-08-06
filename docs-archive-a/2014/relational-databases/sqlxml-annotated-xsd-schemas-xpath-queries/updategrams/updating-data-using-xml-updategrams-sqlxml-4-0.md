---
title: Aggiornamento di dati mediante updategram XML (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- IDREF type attribute [SQLXML]
- before attribute
- <sync> block
- <after> block
- id attribute
- <before> block
- updg:after attribute
- mapping-schema attribute
- IDREFS type attribute [SQLXML]
- updg:id attribute
- multiple record updates
- after attribute
- updategrams [SQLXML], updating data
- updg:before attribute
- record updates [SQLXML]
ms.assetid: 90ef8a33-5ae3-4984-8259-608d2f1d727f
author: rothja
ms.author: jroth
ms.openlocfilehash: 6b019478868b61f293eda824d9b302099728dec4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87634948"
---
# <a name="updating-data-using-xml-updategrams-sqlxml-40"></a><span data-ttu-id="2ae4c-102">Aggiornamento di dati tramite updategram XML (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="2ae4c-102">Updating Data Using XML Updategrams (SQLXML 4.0)</span></span>
  <span data-ttu-id="2ae4c-103">Quando si aggiornano i dati esistenti, è necessario specificare entrambi i **\<before>** **\<after>** blocchi e.</span><span class="sxs-lookup"><span data-stu-id="2ae4c-103">When you update existing data, you must specify both the **\<before>** and **\<after>** blocks.</span></span> <span data-ttu-id="2ae4c-104">Gli elementi specificati nei **\<before>** blocchi e **\<after>** descrivono la modifica desiderata.</span><span class="sxs-lookup"><span data-stu-id="2ae4c-104">The elements specified in the **\<before>** and **\<after>** blocks describe the desired change.</span></span> <span data-ttu-id="2ae4c-105">L'updategram utilizza gli elementi specificati nel **\<before>** blocco per identificare i record o i record esistenti nel database.</span><span class="sxs-lookup"><span data-stu-id="2ae4c-105">The updategram uses the element(s) that are specified in the **\<before>** block to identify the existing record(s) in the database.</span></span> <span data-ttu-id="2ae4c-106">Gli elementi corrispondenti nel **\<after>** blocco indicano la modalità di aspetto dei record dopo l'esecuzione dell'operazione di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="2ae4c-106">The corresponding element(s) in the **\<after>** block indicate how the records should look after executing the update operation.</span></span> <span data-ttu-id="2ae4c-107">Da queste informazioni, l'updategram crea un'istruzione SQL che corrisponde al **\<after>** blocco.</span><span class="sxs-lookup"><span data-stu-id="2ae4c-107">From this information, the updategram creates an SQL statement that matches the **\<after>** block.</span></span> <span data-ttu-id="2ae4c-108">L'updategram utilizza quindi questa istruzione per aggiornare il database.</span><span class="sxs-lookup"><span data-stu-id="2ae4c-108">The updategram then uses this statement to update the database.</span></span>  
  
 <span data-ttu-id="2ae4c-109">Di seguito viene illustrato il formato dell'updategram per un'operazione di aggiornamento:</span><span class="sxs-lookup"><span data-stu-id="2ae4c-109">This is the updategram format for an update operation:</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
<updg:sync [mapping-schema="SampleSchema.xml"]  >  
   <updg:before>  
      <ElementName [updg:id="value"] .../>  
      [<ElementName [updg:id="value"] .../> ... ]  
   </updg:before>  
   <updg:after>  
      <ElementName [updg:id="value"] ... />  
      [<ElementName [updg:id="value"] .../> ...]  
   </updg:after>  
</updg:sync>  
</ROOT>  
```  
  
 `<updg:before>`  
 <span data-ttu-id="2ae4c-110">Gli elementi del **\<before>** blocco identificano i record esistenti nelle tabelle di database.</span><span class="sxs-lookup"><span data-stu-id="2ae4c-110">The elements in the **\<before>** block identify existing records in the database tables.</span></span>  
  
 `<updg:after>`  
 <span data-ttu-id="2ae4c-111">Gli elementi nel **\<after>** blocco descrivono il modo in cui i record specificati nel **\<before>** blocco dovrebbero apparire dopo l'applicazione degli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="2ae4c-111">The elements in the **\<after>** block describe how the records specified in the **\<before>** block should look after the updates are applied.</span></span>  
  
 <span data-ttu-id="2ae4c-112">L'attributo `mapping-schema` identifica lo schema di mapping utilizzato dall'updategram.</span><span class="sxs-lookup"><span data-stu-id="2ae4c-112">The `mapping-schema` attribute identifies the mapping schema to be used by the updategram.</span></span> <span data-ttu-id="2ae4c-113">Se l'updategram specifica uno schema di mapping, i nomi degli elementi e degli attributi specificati nei **\<before>** **\<after>** blocchi e devono corrispondere ai nomi nello schema.</span><span class="sxs-lookup"><span data-stu-id="2ae4c-113">If the updategram specifies a mapping schema, the element and attribute names specified in the **\<before>** and **\<after>** blocks must match the names in the schema.</span></span> <span data-ttu-id="2ae4c-114">Lo schema di mapping esegue il mapping di questi nomi degli elementi o degli attributi ai nomi delle tabelle e delle colonne del database.</span><span class="sxs-lookup"><span data-stu-id="2ae4c-114">The mapping schema maps these element or attribute names to the database table and column names.</span></span>  
  
 <span data-ttu-id="2ae4c-115">Se un updategram non specifica uno schema, utilizza il mapping predefinito.</span><span class="sxs-lookup"><span data-stu-id="2ae4c-115">If an updategram does not specify a schema, the updategam uses default mapping.</span></span> <span data-ttu-id="2ae4c-116">Nel mapping predefinito, l' **\<ElementName>** oggetto specificato nell'updategram esegue il mapping alla tabella di database e gli elementi figlio o gli attributi vengono mappati alle colonne del database.</span><span class="sxs-lookup"><span data-stu-id="2ae4c-116">In default mapping, the **\<ElementName>** specified in the updategram maps to the database table and the child elements or attributes map to the database columns.</span></span>  
  
 <span data-ttu-id="2ae4c-117">Un elemento del **\<before>** blocco deve corrispondere a una sola riga della tabella nel database.</span><span class="sxs-lookup"><span data-stu-id="2ae4c-117">An element in the **\<before>** block must match with only one table row in the database.</span></span> <span data-ttu-id="2ae4c-118">Se l'elemento corrisponde a più righe di tabella o non corrisponde ad alcuna riga della tabella, l'updategram restituisce un errore e Annulla l'intero **\<sync>** blocco.</span><span class="sxs-lookup"><span data-stu-id="2ae4c-118">If the element either matches multiple table rows or does not match any table row, the updategram returns an error and cancels the entire **\<sync>** block.</span></span>  
  
 <span data-ttu-id="2ae4c-119">Un updategram può includere più **\<sync>** blocchi.</span><span class="sxs-lookup"><span data-stu-id="2ae4c-119">An updategram can include multiple **\<sync>** blocks.</span></span> <span data-ttu-id="2ae4c-120">Ogni **\<sync>** blocco viene considerato come una transazione.</span><span class="sxs-lookup"><span data-stu-id="2ae4c-120">Each **\<sync>** block is treated as a transaction.</span></span> <span data-ttu-id="2ae4c-121">Ogni **\<sync>** blocco può avere più **\<before>** **\<after>** blocchi e.</span><span class="sxs-lookup"><span data-stu-id="2ae4c-121">Each **\<sync>** block can have multiple **\<before>** and **\<after>** blocks.</span></span> <span data-ttu-id="2ae4c-122">Se ad esempio si stanno aggiornando due dei record esistenti, è possibile specificare due **\<before>** coppie e **\<after>** , una per ogni record da aggiornare.</span><span class="sxs-lookup"><span data-stu-id="2ae4c-122">For example, if you are updating two of the existing records, you could specify two **\<before>** and **\<after>** pairs, one for each record being updated.</span></span>  
  
## <a name="using-the-updgid-attribute"></a><span data-ttu-id="2ae4c-123">Utilizzo dell'attributo updg:id</span><span class="sxs-lookup"><span data-stu-id="2ae4c-123">Using the updg:id Attribute</span></span>  
 <span data-ttu-id="2ae4c-124">Quando si specificano più elementi nei **\<before>** **\<after>** blocchi e, usare l' `updg:id` attributo per contrassegnare le righe **\<before>** nei **\<after>** blocchi e.</span><span class="sxs-lookup"><span data-stu-id="2ae4c-124">When multiple elements are specified in the **\<before>** and **\<after>** blocks, use the `updg:id` attribute to mark rows in the **\<before>** and **\<after>** blocks.</span></span> <span data-ttu-id="2ae4c-125">La logica di elaborazione usa queste informazioni per determinare quale record nelle **\<before>** coppie di blocchi con quale record nel **\<after>** blocco.</span><span class="sxs-lookup"><span data-stu-id="2ae4c-125">The processing logic uses this information to determine what record in the **\<before>** block pairs with what record in the **\<after>** block.</span></span>  
  
 <span data-ttu-id="2ae4c-126">Benché sia consigliabile, l'attributo `updg:id` non è necessario nei casi seguenti:</span><span class="sxs-lookup"><span data-stu-id="2ae4c-126">The `updg:id` attribute is not necessary (although recommended) if either of the following exists:</span></span>  
  
-   <span data-ttu-id="2ae4c-127">Negli elementi nello schema di mapping specificato è definito l'attributo `sql:key-fields`.</span><span class="sxs-lookup"><span data-stu-id="2ae4c-127">The elements in the specified mapping schema have the `sql:key-fields` attribute defined on them.</span></span>  
  
-   <span data-ttu-id="2ae4c-128">Per i campi chiave nell'updategram vengono forniti uno o più valori specifici.</span><span class="sxs-lookup"><span data-stu-id="2ae4c-128">There is one or more specific value supplied for the key field(s) in the updategram.</span></span>  
  
 <span data-ttu-id="2ae4c-129">In tal caso, l'updategram utilizza le colonne chiave specificate in `sql:key-fields` per associare gli elementi nei **\<before>** **\<after>** blocchi e.</span><span class="sxs-lookup"><span data-stu-id="2ae4c-129">If either is the case, the updategram uses the key columns that are specified in the `sql:key-fields` to pair the elements in the **\<before>** and **\<after>** blocks.</span></span>  
  
 <span data-ttu-id="2ae4c-130">Se lo schema di mapping non identifica colonne chiave (tramite `sql:key-fields`) o se l'updategram aggiorna un valore di colonna chiave, è necessario specificare `updg:id`.</span><span class="sxs-lookup"><span data-stu-id="2ae4c-130">If the mapping schema does not identify key columns (by using `sql:key-fields`) or if the updategram is updating a key column value, you must specify `updg:id`.</span></span>  
  
 <span data-ttu-id="2ae4c-131">I record identificati nei **\<before>** blocchi e non **\<after>** devono essere nello stesso ordine.</span><span class="sxs-lookup"><span data-stu-id="2ae4c-131">The records that are identified in the **\<before>** and **\<after>** blocks do not have to be in the same order.</span></span> <span data-ttu-id="2ae4c-132">L' `updg:id` attributo forza l'associazione tra gli elementi specificati nei **\<before>** **\<after>** blocchi e.</span><span class="sxs-lookup"><span data-stu-id="2ae4c-132">The `updg:id` attribute forces the association between the elements that are specified in the **\<before>** and **\<after>** blocks.</span></span>  
  
 <span data-ttu-id="2ae4c-133">Se si specifica un elemento nel **\<before>** blocco e solo un elemento corrispondente nel **\<after>** blocco, l'utilizzo di `updg:id` non è necessario.</span><span class="sxs-lookup"><span data-stu-id="2ae4c-133">If you specify one element in the **\<before>** block and only one corresponding element in the **\<after>** block, using `updg:id` is not necessary.</span></span> <span data-ttu-id="2ae4c-134">È consigliabile, tuttavia, specificare comunque `updg:id` per evitare ambiguità.</span><span class="sxs-lookup"><span data-stu-id="2ae4c-134">However, it is recommended that you specify `updg:id` anyway to avoid ambiguity.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="2ae4c-135">Esempi</span><span class="sxs-lookup"><span data-stu-id="2ae4c-135">Examples</span></span>  
 <span data-ttu-id="2ae4c-136">Prima di utilizzare gli esempi di updategram, tenere presente quanto segue:</span><span class="sxs-lookup"><span data-stu-id="2ae4c-136">Before you use the updategram examples, note the following:</span></span>  
  
-   <span data-ttu-id="2ae4c-137">La maggior parte degli esempi utilizza il mapping predefinito, ovvero non viene specificato alcuno schema di mapping nell'updategram.</span><span class="sxs-lookup"><span data-stu-id="2ae4c-137">Most of the examples use default mapping (that is, no mapping schema is specified in the updategram).</span></span> <span data-ttu-id="2ae4c-138">Per ulteriori esempi di updategram che utilizzano schemi di mapping, vedere [specifica di uno schema di mapping con annotazioni in un Updategram &#40;SQLXML 4,0&#41;](specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="2ae4c-138">For more examples of updategrams that use mapping schemas, see [Specifying an Annotated Mapping Schema in an Updategram &#40;SQLXML 4.0&#41;](specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).</span></span>  
  
-   <span data-ttu-id="2ae4c-139">La maggior parte degli esempi utilizza il database di esempio AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="2ae4c-139">Most of the examples use the AdventureWorks sample database.</span></span> <span data-ttu-id="2ae4c-140">Tutti gli aggiornamenti vengono applicati alle tabelle di questo database.</span><span class="sxs-lookup"><span data-stu-id="2ae4c-140">All the updates are applied to the tables in this database.</span></span> <span data-ttu-id="2ae4c-141">È possibile ripristinare il database AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="2ae4c-141">You can restore the AdventureWorks database.</span></span>  
  
### <a name="a-updating-a-record"></a><span data-ttu-id="2ae4c-142">R.</span><span class="sxs-lookup"><span data-stu-id="2ae4c-142">A.</span></span> <span data-ttu-id="2ae4c-143">Aggiornamento di un record</span><span class="sxs-lookup"><span data-stu-id="2ae4c-143">Updating a record</span></span>  
 <span data-ttu-id="2ae4c-144">Nell'updategram seguente il cognome del dipendente viene aggiornato a Fuller nella tabella Person.Contact del database AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="2ae4c-144">The following updategram updates the employee last name to Fuller in the Person.Contact table in the AdventureWorks database.</span></span> <span data-ttu-id="2ae4c-145">Poiché l'updategram non specifica alcuno schema di mapping, utilizza il mapping predefinito.</span><span class="sxs-lookup"><span data-stu-id="2ae4c-145">The updategram does not specify any mapping schema; therefore, the updategram uses default mapping.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
<updg:sync >  
<updg:before>  
   <Person.Contact ContactID="1" />  
</updg:before>  
<updg:after>  
   <Person.Contact LastName="Abel-Achong" />  
</updg:after>  
</updg:sync>  
</ROOT>  
```  
  
 <span data-ttu-id="2ae4c-146">Il record descritto nel **\<before>** blocco rappresenta il record corrente nel database.</span><span class="sxs-lookup"><span data-stu-id="2ae4c-146">The record described in the **\<before>** block represents the current record in the database.</span></span> <span data-ttu-id="2ae4c-147">L'updategram utilizza tutti i valori di colonna specificati nel **\<before>** blocco per cercare il record.</span><span class="sxs-lookup"><span data-stu-id="2ae4c-147">The updategram uses all of the column values specified in the **\<before>** block to search for the record.</span></span> <span data-ttu-id="2ae4c-148">In questo updategram il **\<before>** blocco fornisce solo la colonna ContactID. Pertanto, l'updategram utilizza solo il valore per cercare il record.</span><span class="sxs-lookup"><span data-stu-id="2ae4c-148">In this updategram, the **\<before>** block provides only the ContactID column; therefore, the updategram uses only the value to search for the record.</span></span> <span data-ttu-id="2ae4c-149">Se si aggiungesse il valore LastName a questo blocco, l'updategram utilizzerebbe sia i valori ContactID e LastName per la ricerca.</span><span class="sxs-lookup"><span data-stu-id="2ae4c-149">If you were to add the LastName value to this block, the updategram would use both the ContactID and LastName values to search.</span></span>  
  
 <span data-ttu-id="2ae4c-150">In questo updategram il **\<after>** blocco fornisce solo il valore della colonna LastName perché questo è l'unico valore che viene modificato.</span><span class="sxs-lookup"><span data-stu-id="2ae4c-150">In this updategram, the **\<after>** block provides only the LastName column value because this is the only value that is being changed.</span></span>  
  
##### <a name="to-test-the-updategram"></a><span data-ttu-id="2ae4c-151">Per testare l'updategram</span><span class="sxs-lookup"><span data-stu-id="2ae4c-151">To test the updategram</span></span>  
  
1.  <span data-ttu-id="2ae4c-152">Copiare il modello di updategram precedente e incollarlo in un file di testo.</span><span class="sxs-lookup"><span data-stu-id="2ae4c-152">Copy the updategram template above and paste it into a text file.</span></span> <span data-ttu-id="2ae4c-153">Salvare il file con il nome UpdateLastName.xml.</span><span class="sxs-lookup"><span data-stu-id="2ae4c-153">Save the file as UpdateLastName.xml.</span></span>  
  
2.  <span data-ttu-id="2ae4c-154">Creare e utilizzare lo script di test SQLXML 4.0 (Sqlxml4test.vbs) per eseguire l'updategram.</span><span class="sxs-lookup"><span data-stu-id="2ae4c-154">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the updategram.</span></span>  
  
     <span data-ttu-id="2ae4c-155">Per ulteriori informazioni, vedere [utilizzo di ADO per eseguire query SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="2ae4c-155">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
### <a name="b-updating-multiple-records-by-using-the-updgid-attribute"></a><span data-ttu-id="2ae4c-156">B.</span><span class="sxs-lookup"><span data-stu-id="2ae4c-156">B.</span></span> <span data-ttu-id="2ae4c-157">Aggiornamento di più record tramite l'attributo updg:id</span><span class="sxs-lookup"><span data-stu-id="2ae4c-157">Updating multiple records by using the updg:id attribute</span></span>  
 <span data-ttu-id="2ae4c-158">In questo esempio l'updategram esegue due aggiornamenti nella tabella HumanResources.Shift del database AdventureWorks:</span><span class="sxs-lookup"><span data-stu-id="2ae4c-158">In this example, the updategram performs two updates on the HumanResources.Shift table in the AdventureWorks database:</span></span>  
  
-   <span data-ttu-id="2ae4c-159">L'updategram modifica il nome del turno diurno originale che inizia alle 7.00 da "Day" a "Early Morning".</span><span class="sxs-lookup"><span data-stu-id="2ae4c-159">It changes the name of the original day shift that starts at 7:00AM from "Day" to "Early Morning".</span></span>  
  
-   <span data-ttu-id="2ae4c-160">L'updategram inserisce quindi un nuovo turno denominato "Late Morning" che inizia alle 10.00.</span><span class="sxs-lookup"><span data-stu-id="2ae4c-160">It inserts a new shift named "Late Morning" that starts at 10:00AM.</span></span>  
  
 <span data-ttu-id="2ae4c-161">Nell'updategram l' `updg:id` attributo crea associazioni tra gli elementi nei **\<before>** **\<after>** blocchi e.</span><span class="sxs-lookup"><span data-stu-id="2ae4c-161">In the updategram, the `updg:id` attribute creates associations between elements in the **\<before>** and **\<after>** blocks.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync >  
    <updg:before>  
       <HumanResources.Shift updg:id="x" Name="Day" />  
    </updg:before>  
    <updg:after>  
      <HumanResources.Shift updg:id="y" Name="Late Morning"   
                            StartTime="1900-01-01 10:00:00.000"  
                            EndTime="1900-01-01 18:00:00.000"  
                            ModifiedDate="2004-06-01 00:00:00.000"/>  
      <HumanResources.Shift updg:id="x" Name="Early Morning" />  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
 <span data-ttu-id="2ae4c-162">Si noti come l' `updg:id` attributo coppie la prima istanza dell' \<HumanResources.Shift> elemento nel **\<before>** blocco con la seconda istanza dell' \<HumanResources.Shift> elemento nel **\<after>** blocco.</span><span class="sxs-lookup"><span data-stu-id="2ae4c-162">Notice how the `updg:id` attribute pairs the first instance of the \<HumanResources.Shift> element in the **\<before>** block with the second instance of the \<HumanResources.Shift> element in the **\<after>** block.</span></span>  
  
##### <a name="to-test-the-updategram"></a><span data-ttu-id="2ae4c-163">Per testare l'updategram</span><span class="sxs-lookup"><span data-stu-id="2ae4c-163">To test the updategram</span></span>  
  
1.  <span data-ttu-id="2ae4c-164">Copiare il modello di updategram precedente e incollarlo in un file di testo.</span><span class="sxs-lookup"><span data-stu-id="2ae4c-164">Copy the updategram template above and paste it into a text file.</span></span> <span data-ttu-id="2ae4c-165">Salvare il file con il nome UpdateMultipleRecords.xml.</span><span class="sxs-lookup"><span data-stu-id="2ae4c-165">Save the file as UpdateMultipleRecords.xml.</span></span>  
  
2.  <span data-ttu-id="2ae4c-166">Creare e utilizzare lo script di test SQLXML 4.0 (Sqlxml4test.vbs) per eseguire l'updategram.</span><span class="sxs-lookup"><span data-stu-id="2ae4c-166">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the updategram.</span></span>  
  
     <span data-ttu-id="2ae4c-167">Per ulteriori informazioni, vedere [utilizzo di ADO per eseguire query SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="2ae4c-167">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
### <a name="c-specifying-multiple-before-and-after-blocks"></a><span data-ttu-id="2ae4c-168">C.</span><span class="sxs-lookup"><span data-stu-id="2ae4c-168">C.</span></span> <span data-ttu-id="2ae4c-169">Specifica \<before> di più \<after> blocchi e</span><span class="sxs-lookup"><span data-stu-id="2ae4c-169">Specifying multiple \<before> and \<after> blocks</span></span>  
 <span data-ttu-id="2ae4c-170">Per evitare ambiguità, è possibile scrivere l'updategram nell'esempio B utilizzando più **\<before>** coppie di **\<after>** blocchi e.</span><span class="sxs-lookup"><span data-stu-id="2ae4c-170">To avoid ambiguity, you can write the updategram in Example B by using multiple **\<before>** and **\<after>** block pairs.</span></span> <span data-ttu-id="2ae4c-171">Specificare **\<before>** le **\<after>** coppie e è un modo per specificare più aggiornamenti con un minimo di confusione.</span><span class="sxs-lookup"><span data-stu-id="2ae4c-171">Specifying **\<before>** and **\<after>** pairs is one way of specifying multiple updates with a minimum of confusion.</span></span> <span data-ttu-id="2ae4c-172">Inoltre, se ciascuno dei **\<before>** blocchi e **\<after>** specifica al massimo un elemento, non è necessario utilizzare l' `updg:id` attributo.</span><span class="sxs-lookup"><span data-stu-id="2ae4c-172">Also, if each of the **\<before>** and **\<after>** blocks specify at most one element, you do not have to use the `updg:id` attribute.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2ae4c-173">Per formare una coppia, il **\<after>** tag deve seguire immediatamente il **\<before>** tag corrispondente.</span><span class="sxs-lookup"><span data-stu-id="2ae4c-173">To form a pair, the **\<after>** tag must immediately follow its corresponding **\<before>** tag.</span></span>  
  
 <span data-ttu-id="2ae4c-174">Nell'updategram seguente la prima e la **\<before>** **\<after>** coppia aggiornano il nome dello spostamento per il giorno turno.</span><span class="sxs-lookup"><span data-stu-id="2ae4c-174">In the following updategram, the first **\<before>** and **\<after>** pair updates the shift name for the day shift.</span></span> <span data-ttu-id="2ae4c-175">La seconda coppia inserisce un record per un nuovo turno.</span><span class="sxs-lookup"><span data-stu-id="2ae4c-175">The second pair inserts a new shift record.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync >  
    <updg:before>  
       <HumanResources.Shift ShiftID="1" Name="Day" />  
    </updg:before>  
    <updg:after>  
      <HumanResources.Shift Name="Early Morning" />  
    </updg:after>  
    <updg:before>  
    </updg:before>  
    <updg:after>  
      <HumanResources.Shift Name="Late Morning"   
                            StartTime="1900-01-01 10:00:00.000"  
                            EndTime="1900-01-01 18:00:00.000"  
                            ModifiedDate="2004-06-01 00:00:00.000"/>  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
##### <a name="to-test-the-updategram"></a><span data-ttu-id="2ae4c-176">Per testare l'updategram</span><span class="sxs-lookup"><span data-stu-id="2ae4c-176">To test the updategram</span></span>  
  
1.  <span data-ttu-id="2ae4c-177">Copiare il modello di updategram precedente e incollarlo in un file di testo.</span><span class="sxs-lookup"><span data-stu-id="2ae4c-177">Copy the updategram template above and paste it into a text file.</span></span> <span data-ttu-id="2ae4c-178">Salvare il file con il nome UpdateMultipleBeforeAfter.xml.</span><span class="sxs-lookup"><span data-stu-id="2ae4c-178">Save the file as UpdateMultipleBeforeAfter.xml.</span></span>  
  
2.  <span data-ttu-id="2ae4c-179">Creare e utilizzare lo script di test SQLXML 4.0 (Sqlxml4test.vbs) per eseguire l'updategram.</span><span class="sxs-lookup"><span data-stu-id="2ae4c-179">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the updategram.</span></span>  
  
     <span data-ttu-id="2ae4c-180">Per ulteriori informazioni, vedere [utilizzo di ADO per eseguire query SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="2ae4c-180">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
### <a name="d-specifying-multiple-sync-blocks"></a><span data-ttu-id="2ae4c-181">D.</span><span class="sxs-lookup"><span data-stu-id="2ae4c-181">D.</span></span> <span data-ttu-id="2ae4c-182">Specifica di più \<sync> blocchi</span><span class="sxs-lookup"><span data-stu-id="2ae4c-182">Specifying multiple \<sync> blocks</span></span>  
 <span data-ttu-id="2ae4c-183">È possibile specificare più **\<sync>** blocchi in un updategram.</span><span class="sxs-lookup"><span data-stu-id="2ae4c-183">You can specify multiple **\<sync>** blocks in an updategram.</span></span> <span data-ttu-id="2ae4c-184">Ogni **\<sync>** blocco specificato è una transazione indipendente.</span><span class="sxs-lookup"><span data-stu-id="2ae4c-184">Each **\<sync>** block that is specified is an independent transaction.</span></span>  
  
 <span data-ttu-id="2ae4c-185">Nell'updategram seguente il primo **\<sync>** blocco aggiorna un record nella tabella Sales. Customer.</span><span class="sxs-lookup"><span data-stu-id="2ae4c-185">In the following updategram, the first **\<sync>** block updates a record in the Sales.Customer table.</span></span> <span data-ttu-id="2ae4c-186">Per motivi di semplicità, l'updategram specifica solo i valori di colonna obbligatori, ovvero il valore Identity (CustomerID) e il valore da aggiornare (SalesPersonID).</span><span class="sxs-lookup"><span data-stu-id="2ae4c-186">For the sake of simplicity, the updategram specifies only the required column values; the identity value (CustomerID) and the value being updated (SalesPersonID).</span></span>  
  
 <span data-ttu-id="2ae4c-187">Il secondo **\<sync>** blocco aggiunge due record alla tabella Sales. SalesOrderHeader.</span><span class="sxs-lookup"><span data-stu-id="2ae4c-187">The second **\<sync>** block adds two records to the Sales.SalesOrderHeader table.</span></span> <span data-ttu-id="2ae4c-188">Per questa tabella la colonna SalesOrderID è una colonna di tipo IDENTITY.</span><span class="sxs-lookup"><span data-stu-id="2ae4c-188">For this table, SalesOrderID is an IDENTITY-type column.</span></span> <span data-ttu-id="2ae4c-189">Pertanto, l'updategram non specifica il valore di SalesOrderID in ogni \<Sales.SalesOrderHeader> elemento.</span><span class="sxs-lookup"><span data-stu-id="2ae4c-189">Therefore, the updategram does not specify the value of SalesOrderID in each of the \<Sales.SalesOrderHeader> elements.</span></span>  
  
 <span data-ttu-id="2ae4c-190">La specifica di più **\<sync>** blocchi è utile perché se il secondo **\<sync>** blocco (una transazione) non è in grado di aggiungere record alla tabella Sales. SalesOrderHeader, il primo **\<sync>** blocco può comunque aggiornare il record del cliente nella tabella Sales. Customer.</span><span class="sxs-lookup"><span data-stu-id="2ae4c-190">Specifying multiple **\<sync>** blocks is useful because if the second **\<sync>** block (a transaction) fails to add records to Sales.SalesOrderHeader table, the first **\<sync>** block can still update the customer record in the Sales.Customer table.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync >  
    <updg:before>  
      <Sales.Customer CustomerID="1" SalesPersonID="280" />  
    </updg:before>  
    <updg:after>  
      <Sales.Customer CustomerID="1" SalesPersonID="283" />  
    </updg:after>  
  </updg:sync>  
  <updg:sync >  
    <updg:before>  
    </updg:before>  
    <updg:after>  
   <Sales.SalesOrderHeader   
             CustomerID="1"  
             RevisionNumber="1"  
             OrderDate="2004-07-01 00:00:00.000"  
             DueDate="2004-07-13 00:00:00.000"  
             OnlineOrderFlag="0"  
             ContactID="378"  
             BillToAddressID="985"  
             ShipToAddressID="985"  
             ShipMethodID="5"  
             SubTotal="24643.9362"  
             TaxAmt="1971.5149"  
             Freight="616.0984"  
             rowguid="01010101-2222-3333-4444-556677889900"  
             ModifiedDate="2004-07-08 00:00:00.000" />  
   <Sales.SalesOrderHeader  
             CustomerID="1"  
             RevisionNumber="1"  
             OrderDate="2004-07-01 00:00:00.000"  
             DueDate="2004-07-13 00:00:00.000"  
             OnlineOrderFlag="0"  
             ContactID="378"  
             BillToAddressID="985"  
             ShipToAddressID="985"  
             ShipMethodID="5"  
             SubTotal="1000.0000"  
             TaxAmt="0.0000"  
             Freight="0.0000"  
             rowguid="10101010-2222-3333-4444-556677889900"  
             ModifiedDate="2004-07-09 00:00:00.000" />  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
##### <a name="to-test-the-updategram"></a><span data-ttu-id="2ae4c-191">Per testare l'updategram</span><span class="sxs-lookup"><span data-stu-id="2ae4c-191">To test the updategram</span></span>  
  
1.  <span data-ttu-id="2ae4c-192">Copiare il modello di updategram precedente e incollarlo in un file di testo.</span><span class="sxs-lookup"><span data-stu-id="2ae4c-192">Copy the updategram template above and paste it into a text file.</span></span> <span data-ttu-id="2ae4c-193">Salvare il file con il nome UpdateMultipleSyncs.xml.</span><span class="sxs-lookup"><span data-stu-id="2ae4c-193">Save the file as UpdateMultipleSyncs.xml.</span></span>  
  
2.  <span data-ttu-id="2ae4c-194">Creare e utilizzare lo script di test SQLXML 4.0 (Sqlxml4test.vbs) per eseguire l'updategram.</span><span class="sxs-lookup"><span data-stu-id="2ae4c-194">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the updategram.</span></span>  
  
     <span data-ttu-id="2ae4c-195">Per ulteriori informazioni, vedere [utilizzo di ADO per eseguire query SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="2ae4c-195">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
### <a name="e-using-a-mapping-schema"></a><span data-ttu-id="2ae4c-196">E.</span><span class="sxs-lookup"><span data-stu-id="2ae4c-196">E.</span></span> <span data-ttu-id="2ae4c-197">Utilizzo di uno schema di mapping</span><span class="sxs-lookup"><span data-stu-id="2ae4c-197">Using a mapping schema</span></span>  
 <span data-ttu-id="2ae4c-198">In questo esempio l'updategram specifica uno schema di mapping tramite l'attributo `mapping-schema`.</span><span class="sxs-lookup"><span data-stu-id="2ae4c-198">In this example, the updategram specifies a mapping schema by using the `mapping-schema` attribute.</span></span> <span data-ttu-id="2ae4c-199">Non è disponibile alcun mapping predefinito, ovvero lo schema di mapping fornisce il mapping necessario di elementi e attributi nell'updategram alle tabelle e alle colonne del database.</span><span class="sxs-lookup"><span data-stu-id="2ae4c-199">(There is no default mapping; that is, the mapping schema provides the necessary mapping of elements and attributes in the updategram to the database tables and columns.)</span></span>  
  
 <span data-ttu-id="2ae4c-200">Gli elementi e gli attributi specificati nell'updategram fanno riferimento agli elementi e agli attributi nello schema di mapping.</span><span class="sxs-lookup"><span data-stu-id="2ae4c-200">The elements and attributes specified in the updategram refer to the elements and attributes in the mapping schema.</span></span>  
  
 <span data-ttu-id="2ae4c-201">Nello schema di mapping XSD seguente sono presenti **\<Customer>** **\<Order>** **\<OD>** gli elementi, e che vengono mappati alle tabelle Sales. Customer, Sales. SalesOrderHeader e Sales. SalesOrderDetail del database.</span><span class="sxs-lookup"><span data-stu-id="2ae4c-201">The following XSD mapping schema has **\<Customer>**, **\<Order>**, and **\<OD>** elements that map to the Sales.Customer, Sales.SalesOrderHeader, and Sales.SalesOrderDetail tables in the database.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
<xsd:annotation>  
  <xsd:appinfo>  
    <sql:relationship name="CustomerOrder"  
          parent="Sales.Customer"  
          parent-key="CustomerID"  
          child="Sales.SalesOrderHeader"  
          child-key="CustomerID" />  
  
    <sql:relationship name="OrderOD"  
          parent="Sales.SalesOrderHeader"  
          parent-key="SalesOrderID"  
          child="Sales.SalesOrderDetail"  
          child-key="SalesOrderID" />  
  </xsd:appinfo>  
</xsd:annotation>  
  
  <xsd:element name="Customer" sql:relation="Sales.Customer" >  
   <xsd:complexType>  
     <xsd:sequence>  
        <xsd:element name="Order"   
                     sql:relation="Sales.SalesOrderHeader"  
                     sql:relationship="CustomerOrder" >  
           <xsd:complexType>  
              <xsd:sequence>  
                <xsd:element name="OD"   
                             sql:relation="Sales.SalesOrderDetail"  
                             sql:relationship="OrderOD" >  
                 <xsd:complexType>  
                  <xsd:attribute name="SalesOrderID" type="xsd:integer" />  
                  <xsd:attribute name="ProductID" type="xsd:integer" />  
                  <xsd:attribute name="UnitPrice" type="xsd:decimal" />  
                  <xsd:attribute name="OrderQty" type="xsd:integer" />  
                  <xsd:attribute name="UnitPriceDiscount" type="xsd:decimal" />   
                 </xsd:complexType>  
                </xsd:element>  
              </xsd:sequence>  
              <xsd:attribute name="CustomerID" type="xsd:string" />  
              <xsd:attribute name="SalesOrderID" type="xsd:integer" />  
              <xsd:attribute name="OrderDate" type="xsd:date" />  
           </xsd:complexType>  
        </xsd:element>  
      </xsd:sequence>  
      <xsd:attribute name="CustomerID"   type="xsd:string" />   
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="2ae4c-202">Questo schema di mapping (UpdategramMappingSchema.xml) viene specificato nell'updategram seguente.</span><span class="sxs-lookup"><span data-stu-id="2ae4c-202">This mapping schema (UpdategramMappingSchema.xml) is specified in the following updategram.</span></span> <span data-ttu-id="2ae4c-203">L'updategram aggiunge un elemento relativo ai dettagli di un ordine nella tabella Sales.SalesOrderDetail per un ordine specifico.</span><span class="sxs-lookup"><span data-stu-id="2ae4c-203">The updategram adds an order detail item in the Sales.SalesOrderDetail table for a specific order.</span></span> <span data-ttu-id="2ae4c-204">L'updategram include elementi annidati, ovvero un **\<OD>** elemento annidato all'interno di un **\<Order>** elemento.</span><span class="sxs-lookup"><span data-stu-id="2ae4c-204">The updategram includes nested elements: an **\<OD>** element nested inside an **\<Order>** element.</span></span> <span data-ttu-id="2ae4c-205">La relazione di chiave primaria/chiave esterna tra questi due elementi viene specificata nello schema di mapping.</span><span class="sxs-lookup"><span data-stu-id="2ae4c-205">The primary key/foreign key relationship between these two elements is specified in the mapping schema.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync mapping-schema="UpdategramMappingSchema.xml" >  
    <updg:before>  
       <Order SalesOrderID="43659" />  
    </updg:before>  
    <updg:after>  
      <Order SalesOrderID="43659" >  
          <OD ProductID="776" UnitPrice="2329.0000"  
              OrderQty="2" UnitPriceDiscount="0.0" />  
      </Order>  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
##### <a name="to-test-the-updategram"></a><span data-ttu-id="2ae4c-206">Per testare l'updategram</span><span class="sxs-lookup"><span data-stu-id="2ae4c-206">To test the updategram</span></span>  
  
1.  <span data-ttu-id="2ae4c-207">Copiare lo schema di mapping precedente e incollarlo in un file di testo.</span><span class="sxs-lookup"><span data-stu-id="2ae4c-207">Copy the mapping schema above and paste it into a text file.</span></span> <span data-ttu-id="2ae4c-208">Salvare il file con il nome UpdategramMappingSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="2ae4c-208">Save the file as UpdategramMappingSchema.xml.</span></span>  
  
2.  <span data-ttu-id="2ae4c-209">Copiare il modello di updategram precedente e incollarlo in un file di testo.</span><span class="sxs-lookup"><span data-stu-id="2ae4c-209">Copy the updategram template above and paste it into a text file.</span></span> <span data-ttu-id="2ae4c-210">Salvare il file con il nome UpdateWithMappingSchema.xml nella stessa cartella utilizzata per salvare lo schema di mapping (UpdategramMappingSchema.xml).</span><span class="sxs-lookup"><span data-stu-id="2ae4c-210">Save the file as UpdateWithMappingSchema.xml in the same folder as was used to save the mapping schema (UpdategramMappingSchema.xml).</span></span>  
  
3.  <span data-ttu-id="2ae4c-211">Creare e utilizzare lo script di test SQLXML 4.0 (Sqlxml4test.vbs) per eseguire l'updategram.</span><span class="sxs-lookup"><span data-stu-id="2ae4c-211">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the updategram.</span></span>  
  
     <span data-ttu-id="2ae4c-212">Per ulteriori informazioni, vedere [utilizzo di ADO per eseguire query SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="2ae4c-212">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="2ae4c-213">Per ulteriori esempi di updategram che utilizzano schemi di mapping, vedere [specifica di uno schema di mapping con annotazioni in un Updategram &#40;SQLXML 4,0&#41;](specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="2ae4c-213">For more examples of updategrams that use mapping schemas, see [Specifying an Annotated Mapping Schema in an Updategram &#40;SQLXML 4.0&#41;](specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).</span></span>  
  
### <a name="f-using-a-mapping-schema-with-idrefs-attributes"></a><span data-ttu-id="2ae4c-214">F.</span><span class="sxs-lookup"><span data-stu-id="2ae4c-214">F.</span></span> <span data-ttu-id="2ae4c-215">Utilizzo di uno schema di mapping con attributi IDREFS</span><span class="sxs-lookup"><span data-stu-id="2ae4c-215">Using a mapping schema with IDREFS attributes</span></span>  
 <span data-ttu-id="2ae4c-216">In questo esempio viene illustrato il modo in cui gli attributi IDREFS nello schema di mapping vengono utilizzati dagli updategram per aggiornare record in più tabelle.</span><span class="sxs-lookup"><span data-stu-id="2ae4c-216">This example illustrates how updategrams use the IDREFS attributes in the mapping schema to update records in multiple tables.</span></span> <span data-ttu-id="2ae4c-217">Nell'esempio si presuppone che il database sia costituito dalle tabelle seguenti:</span><span class="sxs-lookup"><span data-stu-id="2ae4c-217">For this example, assume that the database consists of the following tables:</span></span>  
  
-   <span data-ttu-id="2ae4c-218">Student(StudentID, LastName)</span><span class="sxs-lookup"><span data-stu-id="2ae4c-218">Student(StudentID, LastName)</span></span>  
  
-   <span data-ttu-id="2ae4c-219">Course(CourseID, CourseName)</span><span class="sxs-lookup"><span data-stu-id="2ae4c-219">Course(CourseID, CourseName)</span></span>  
  
-   <span data-ttu-id="2ae4c-220">Enrollment(StudentID, CourseID)</span><span class="sxs-lookup"><span data-stu-id="2ae4c-220">Enrollment(StudentID, CourseID)</span></span>  
  
 <span data-ttu-id="2ae4c-221">Poiché uno studente può iscriversi a molti corsi e un corso può avere molti studenti, la terza tabella, Enrollment, è necessaria per rappresentare questa relazione M:N.</span><span class="sxs-lookup"><span data-stu-id="2ae4c-221">Because a student can enroll in many courses and a course can have many students, the third table, the Enrollment table, is required to represent this M:N relationship.</span></span>  
  
 <span data-ttu-id="2ae4c-222">Nello schema di mapping XSD seguente viene fornita una vista XML delle tabelle tramite gli **\<Student>** **\<Course>** elementi, e **\<Enrollment>** .</span><span class="sxs-lookup"><span data-stu-id="2ae4c-222">The following XSD mapping schema provides an XML view of the tables by using the **\<Student>**, **\<Course>**, and **\<Enrollment>** elements.</span></span> <span data-ttu-id="2ae4c-223">Gli attributi **IDREFS** nello schema di mapping specificano la relazione tra questi elementi.</span><span class="sxs-lookup"><span data-stu-id="2ae4c-223">The **IDREFS** attributes in the mapping schema specify the relationship between these elements.</span></span> <span data-ttu-id="2ae4c-224">L'attributo **StudentIDList** nell' **\<Course>** elemento è un attributo di tipo **IDREFS** che fa riferimento alla colonna StudentID nella tabella di registrazione.</span><span class="sxs-lookup"><span data-stu-id="2ae4c-224">The **StudentIDList** attribute on the **\<Course>** element is an **IDREFS** type attribute that refers to the StudentID column in the Enrollment table.</span></span> <span data-ttu-id="2ae4c-225">Analogamente, l'attributo di cui è stato eseguito l' **rollup** sull' **\<Student>** elemento è un attributo di tipo **IDREFS** che fa riferimento alla colonna CourseID nella tabella di registrazione.</span><span class="sxs-lookup"><span data-stu-id="2ae4c-225">Likewise, the **EnrolledIn** attribute on the **\<Student>** element is an **IDREFS** type attribute that refers to the CourseID column in the Enrollment table.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
<xsd:annotation>  
  <xsd:appinfo>  
    <sql:relationship name="StudentEnrollment"  
          parent="Student"  
          parent-key="StudentID"  
          child="Enrollment"  
          child-key="StudentID" />  
  
    <sql:relationship name="CourseEnrollment"  
          parent="Course"  
          parent-key="CourseID"  
          child="Enrollment"  
          child-key="CourseID" />  
  </xsd:appinfo>  
</xsd:annotation>  
  
  <xsd:element name="Course" sql:relation="Course"   
                             sql:key-fields="CourseID" >  
    <xsd:complexType>  
    <xsd:attribute name="CourseID"  type="xsd:string" />   
    <xsd:attribute name="CourseName"   type="xsd:string" />   
    <xsd:attribute name="StudentIDList" sql:relation="Enrollment"  
                 sql:field="StudentID"  
                 sql:relationship="CourseEnrollment"   
                                     type="xsd:IDREFS" />  
  
    </xsd:complexType>  
  </xsd:element>  
  <xsd:element name="Student" sql:relation="Student" >  
    <xsd:complexType>  
    <xsd:attribute name="StudentID"  type="xsd:string" />   
    <xsd:attribute name="LastName"   type="xsd:string" />   
    <xsd:attribute name="EnrolledIn" sql:relation="Enrollment"  
                 sql:field="CourseID"  
                 sql:relationship="StudentEnrollment"   
                                     type="xsd:IDREFS" />  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="2ae4c-226">Ogni volta che si specifica questo schema in un updategram e si inserisce un record nella tabella Course, l'updategram inserisce un nuovo record di corso nella tabella Course.</span><span class="sxs-lookup"><span data-stu-id="2ae4c-226">Whenever you specify this schema in an updategram and insert a record in the Course table, the updategram inserts a new course record in the Course table.</span></span> <span data-ttu-id="2ae4c-227">Se si specificano uno o più nuovi ID studente per l'attributo StudentIDList, l'updategram inserisce inoltre un record nella tabella Enrollment per ogni nuovo studente.</span><span class="sxs-lookup"><span data-stu-id="2ae4c-227">If you specify one or more new student IDs for the StudentIDList attribute, the updategram also inserts a record in the Enrollment table for the each new student.</span></span> <span data-ttu-id="2ae4c-228">L'updategram fa sì che non vengano aggiunti duplicati alla tabella Enrollment.</span><span class="sxs-lookup"><span data-stu-id="2ae4c-228">The updategram ensures that no duplicates are added to the Enrollment table.</span></span>  
  
##### <a name="to-test-the-updategram"></a><span data-ttu-id="2ae4c-229">Per testare l'updategram</span><span class="sxs-lookup"><span data-stu-id="2ae4c-229">To test the updategram</span></span>  
  
1.  <span data-ttu-id="2ae4c-230">Creare le tabelle seguenti nel database specificato nella radice virtuale:</span><span class="sxs-lookup"><span data-stu-id="2ae4c-230">Create these tables in the database that is specified in the virtual root:</span></span>  
  
    ```  
    CREATE TABLE Student(StudentID varchar(10) primary key,   
                         LastName varchar(25))  
    CREATE TABLE Course(CourseID varchar(10) primary key,   
                        CourseName varchar(25))  
    CREATE TABLE Enrollment(StudentID varchar(10)   
                                      references Student(StudentID),  
                           CourseID varchar(10)   
                                      references Course(CourseID))  
    ```  
  
2.  <span data-ttu-id="2ae4c-231">Aggiungere i dati di esempio seguenti:</span><span class="sxs-lookup"><span data-stu-id="2ae4c-231">Add this sample data:</span></span>  
  
    ```  
    INSERT INTO Student VALUES ('S1','Davoli')  
    INSERT INTO Student VALUES ('S2','Fuller')  
  
    INSERT INTO Course VALUES  ('CS101', 'C Programming')  
    INSERT INTO Course VALUES  ('CS102', 'Understanding XML')  
  
    INSERT INTO Enrollment VALUES ('S1', 'CS101')  
    INSERT INTO Enrollment VALUES ('S1', 'CS102')  
    ```  
  
3.  <span data-ttu-id="2ae4c-232">Copiare lo schema di mapping precedente e incollarlo in un file di testo.</span><span class="sxs-lookup"><span data-stu-id="2ae4c-232">Copy the mapping schema above and paste it into a text file.</span></span> <span data-ttu-id="2ae4c-233">Salvare il file con il nome SampleSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="2ae4c-233">Save the file as SampleSchema.xml.</span></span>  
  
4.  <span data-ttu-id="2ae4c-234">Salvare l'updategram (SampleUpdategram) nella stessa cartella utilizzata per salvare lo schema di mapping nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="2ae4c-234">Save the updategram (SampleUpdategram) in the same folder used to save the mapping schema in the previous step.</span></span> <span data-ttu-id="2ae4c-235">Questo updategram elimina uno studente con StudentID="1" dal corso CS102.</span><span class="sxs-lookup"><span data-stu-id="2ae4c-235">(This updategram drops a student with StudentID="1" from the CS102 course.)</span></span>  
  
    ```  
    <ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
      <updg:sync mapping-schema="SampleSchema.xml" >  
        <updg:before>  
            <Student updg:id="x" StudentID="S1" LastName="Davolio"  
                                 EnrolledIn="CS101 CS102" />  
        </updg:before>  
        <updg:after >  
            <Student updg:id="x" StudentID="S1" LastName="Davolio"  
                                 EnrolledIn="CS101" />  
        </updg:after>  
      </updg:sync>  
    </ROOT>  
    ```  
  
5.  <span data-ttu-id="2ae4c-236">Creare e utilizzare lo script di test SQLXML 4.0 (Sqlxml4test.vbs) per eseguire l'updategram.</span><span class="sxs-lookup"><span data-stu-id="2ae4c-236">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the updategram.</span></span>  
  
     <span data-ttu-id="2ae4c-237">Per ulteriori informazioni, vedere [utilizzo di ADO per eseguire query SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="2ae4c-237">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
6.  <span data-ttu-id="2ae4c-238">Salvare ed eseguire l'updategram seguente come descritto nei passaggi precedenti.</span><span class="sxs-lookup"><span data-stu-id="2ae4c-238">Save and execute the following updategram as described in the previous steps.</span></span> <span data-ttu-id="2ae4c-239">L'updategram aggiunge lo studente con StudentID="1" al corso CS102 tramite l'aggiunta di un record nella tabella Enrollment.</span><span class="sxs-lookup"><span data-stu-id="2ae4c-239">The updategram adds the student with StudentID="1" back into the CS102 course by adding a record in the Enrollment table.</span></span>  
  
    ```  
    <ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
      <updg:sync mapping-schema="SampleSchema.xml" >  
        <updg:before>  
            <Student updg:id="x" StudentID="S1" LastName="Davolio"  
                                 EnrolledIn="CS101" />  
        </updg:before>  
        <updg:after >  
            <Student updg:id="x" StudentID="S1" LastName="Davolio"  
                                 EnrolledIn="CS101 CS102" />  
        </updg:after>  
      </updg:sync>  
    </ROOT>  
    ```  
  
7.  <span data-ttu-id="2ae4c-240">Salvare ed eseguire l'updategram successivo come descritto nei passaggi precedenti.</span><span class="sxs-lookup"><span data-stu-id="2ae4c-240">Save and execute this next updategram as described in the previous steps.</span></span> <span data-ttu-id="2ae4c-241">L'updategram inserisce tre nuovi studenti e li iscrive al corso CS101.</span><span class="sxs-lookup"><span data-stu-id="2ae4c-241">This updategram inserts three new students and enrolls them in the CS101 course.</span></span> <span data-ttu-id="2ae4c-242">La relazione IDREFS inserisce nuovamente record nella tabella Enrollment.</span><span class="sxs-lookup"><span data-stu-id="2ae4c-242">Again, the IDREFS relationship inserts records in the Enrollment table.</span></span>  
  
    ```  
    <ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
      <updg:sync mapping-schema="SampleSchema.xml" >  
        <updg:before>  
           <Course updg:id="y" CourseID="CS101"   
                               CourseName="C Programming" />  
        </updg:before>  
        <updg:after >  
           <Student updg:id="x1" StudentID="S3" LastName="Leverling" />  
           <Student updg:id="x2" StudentID="S4" LastName="Pecock" />  
           <Student updg:id="x3" StudentID="S5" LastName="Buchanan" />  
           <Course updg:id="y" CourseID="CS101"  
                               CourseName="C Programming"  
                               StudentIDList="S3 S4 S5" />  
        </updg:after>  
      </updg:sync>  
    </ROOT>  
    ```  
  
 <span data-ttu-id="2ae4c-243">Di seguito viene indicato lo schema XDR equivalente:</span><span class="sxs-lookup"><span data-stu-id="2ae4c-243">This is the equivalent XDR schema:</span></span>  
  
```  
<?xml version="1.0" ?>  
<Schema xmlns="urn:schemas-microsoft-com:xml-data"  
        xmlns:dt="urn:schemas-microsoft-com:datatypes"  
        xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <ElementType name="Enrollment" sql:relation="Enrollment" sql:key-fields="StudentID CourseID">  
    <AttributeType name="StudentID" dt:type="id" />  
    <AttributeType name="CourseID" dt:type="id" />  
  
    <attribute type="StudentID" />  
    <attribute type="CourseID" />  
  </ElementType>  
  <ElementType name="Course" sql:relation="Course" sql:key-fields="CourseID">  
    <AttributeType name="CourseID" dt:type="id" />  
    <AttributeType name="CourseName" />  
  
    <attribute type="CourseID" />  
    <attribute type="CourseName" />  
  
    <AttributeType name="StudentIDList" dt:type="idrefs" />  
    <attribute type="StudentIDList" sql:relation="Enrollment" sql:field="StudentID" >  
        <sql:relationship  
                key-relation="Course"  
                key="CourseID"  
                foreign-relation="Enrollment"  
                foreign-key="CourseID" />  
    </attribute>  
  
  </ElementType>  
  <ElementType name="Student" sql:relation="Student">  
    <AttributeType name="StudentID" dt:type="id" />  
     <AttributeType name="LastName" />  
  
    <attribute type="StudentID" />  
    <attribute type="LastName" />  
  
    <AttributeType name="EnrolledIn" dt:type="idrefs" />  
    <attribute type="EnrolledIn" sql:relation="Enrollment" sql:field="CourseID" >  
        <sql:relationship  
                key-relation="Student"  
                key="StudentID"  
                foreign-relation="Enrollment"  
                foreign-key="StudentID" />  
    </attribute>  
  
    <element type="Enrollment" sql:relation="Enrollment" >  
        <sql:relationship key-relation="Student"  
                          key="StudentID"  
                          foreign-relation="Enrollment"  
                          foreign-key="StudentID" />  
    </element>  
  </ElementType>  
  
</Schema>  
```  
  
 <span data-ttu-id="2ae4c-244">Per ulteriori esempi di updategram che utilizzano schemi di mapping, vedere [specifica di uno schema di mapping con annotazioni in un Updategram &#40;SQLXML 4,0&#41;](specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="2ae4c-244">For more examples of updategrams that use mapping schemas, see [Specifying an Annotated Mapping Schema in an Updategram &#40;SQLXML 4.0&#41;](specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ae4c-245">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2ae4c-245">See Also</span></span>  
 [<span data-ttu-id="2ae4c-246">Considerazioni sulla sicurezza degli updategram &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="2ae4c-246">Updategram Security Considerations &#40;SQLXML 4.0&#41;</span></span>](../security/updategram-security-considerations-sqlxml-4-0.md)  
  
  
