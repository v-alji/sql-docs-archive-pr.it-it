---
title: Gestione dei problemi di concorrenza di database negli updategram (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- <before> block
- low concurrency protection
- database concurrency [SQLXML]
- timestamp column [SQLXML]
- updategrams [SQLXML], database concurrency
- high concurrency protection [SQLXML]
- optimistic concurrency control
- concurrency [SQLXML]
- intermediate concurrency protection [SQLXML]
ms.assetid: d4b908d1-b25b-4ad9-8478-9cd882e8c44e
author: rothja
ms.author: jroth
ms.openlocfilehash: dd808b2688e8bf05149a5454bee91123878fb2ed
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87634957"
---
# <a name="handling-database-concurrency-issues-in-updategrams-sqlxml-40"></a><span data-ttu-id="d04c5-102">Gestione dei problemi di concorrenza di database negli updategram (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="d04c5-102">Handling Database Concurrency Issues in Updategrams (SQLXML 4.0)</span></span>
  <span data-ttu-id="d04c5-103">Analogamente ad altri meccanismi di aggiornamento del database, gli updategram devono gestire aggiornamenti simultanei ai dati in un ambiente multiutente.</span><span class="sxs-lookup"><span data-stu-id="d04c5-103">Like other database update mechanisms, updategrams must deal with concurrent updates to data in a multiuser environment.</span></span> <span data-ttu-id="d04c5-104">Gli updategram utilizzano il controllo della concorrenza ottimistica, che esegue il confronto dei dati di campo come snapshot per garantire che i dati da aggiornare non siano già stati modificati da un'altra applicazione utente dal momento in cui sono stati letti dal database.</span><span class="sxs-lookup"><span data-stu-id="d04c5-104">Updategrams use the Optimistic Concurrency Control, which uses comparison of select field data as snapshots to ensure that the data to be updated has not been altered by another user application since it was read from the database.</span></span> <span data-ttu-id="d04c5-105">Gli updategram includono questi valori di snapshot nel **\<before>** blocco degli updategram.</span><span class="sxs-lookup"><span data-stu-id="d04c5-105">Updategrams include these snapshot values in the **\<before>** block of the updategrams.</span></span> <span data-ttu-id="d04c5-106">Prima di aggiornare il database, l'updategram controlla i valori specificati nel **\<before>** blocco rispetto ai valori attualmente presenti nel database per garantire che l'aggiornamento sia valido.</span><span class="sxs-lookup"><span data-stu-id="d04c5-106">Before updating the database, the updategram checks the values that are specified in the **\<before>** block against the values currently in the database to ensure that the update is valid.</span></span>  
  
 <span data-ttu-id="d04c5-107">Il controllo della concorrenza ottimistica offre tre livelli di protezione in un updategram: basso (nessuno), intermedio ed elevato.</span><span class="sxs-lookup"><span data-stu-id="d04c5-107">The Optimistic Concurrency Control offers three levels of protection in an updategram: low (none), intermediate, and high.</span></span> <span data-ttu-id="d04c5-108">È possibile stabilire il livello di protezione necessario specificando l'updategram di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="d04c5-108">You can decide what level of protection you need by specifying the updategram accordingly.</span></span>  
  
## <a name="lowest-level-of-protection"></a><span data-ttu-id="d04c5-109">Livello di protezione più basso</span><span class="sxs-lookup"><span data-stu-id="d04c5-109">Lowest Level of Protection</span></span>  
 <span data-ttu-id="d04c5-110">Questo livello corrisponde a un aggiornamento nascosto, in cui l'aggiornamento viene elaborato senza riferimento ad altri aggiornamenti eseguiti dall'ultima lettura del database.</span><span class="sxs-lookup"><span data-stu-id="d04c5-110">This level is a blind update, in which the update is processed without reference to other updates that have been made since the database was last read.</span></span> <span data-ttu-id="d04c5-111">In tal caso, si specificano solo le colonne chiave primaria nel **\<before>** blocco per identificare il record e si specificano le informazioni aggiornate nel **\<after>** blocco.</span><span class="sxs-lookup"><span data-stu-id="d04c5-111">In such a case, you specify only the primary key column(s) in the **\<before>** block to identify the record, and you specify the updated information in the **\<after>** block.</span></span>  
  
 <span data-ttu-id="d04c5-112">Il nuovo numero di telefono del contatto nell'updategram seguente, ad esempio, è corretto, indipendentemente dal numero di telefono precedente.</span><span class="sxs-lookup"><span data-stu-id="d04c5-112">For example, the new contact phone number in the following updategram is correct, regardless of what the phone number was previously.</span></span> <span data-ttu-id="d04c5-113">Si noti che il **\<before>** blocco specifica solo la colonna chiave primaria (ContactID).</span><span class="sxs-lookup"><span data-stu-id="d04c5-113">Notice how the **\<before>** block specifies only the primary key column (ContactID).</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
<updg:sync >  
<updg:before>  
   <Person.Contact ContactID="1" />  
</updg:before>  
<updg:after>  
   <Person.Contact ContactID="1" Phone="111-111-1111" />  
</updg:after>  
</updg:sync>  
</ROOT>  
```  
  
## <a name="intermediate-level-of-protection"></a><span data-ttu-id="d04c5-114">Livello di protezione intermedio</span><span class="sxs-lookup"><span data-stu-id="d04c5-114">Intermediate Level of Protection</span></span>  
 <span data-ttu-id="d04c5-115">In questo livello di protezione l'updategram confronta i valori correnti dei dati aggiornati con i valori nelle colonne del database per verificare che i valori non siano stati modificati da altre transazioni dalla lettura del record da parte della transazione.</span><span class="sxs-lookup"><span data-stu-id="d04c5-115">In this level of protection, the updategram compares the current value(s) of the data being updated with the value(s) in the database column(s) to ensure that the values have not been changed by some other transaction since the record was read by your transaction.</span></span>  
  
 <span data-ttu-id="d04c5-116">È possibile ottenere questo livello di protezione specificando le colonne chiave primaria e le colonne che si stanno aggiornando nel **\<before>** blocco.</span><span class="sxs-lookup"><span data-stu-id="d04c5-116">You can get this level of protection by specifying the primary key column(s) and the column(s) that you are updating in the **\<before>** block.</span></span>  
  
 <span data-ttu-id="d04c5-117">Questo updategram, ad esempio, modifica il valore nella colonna Phone della tabella Person.Contact per il contatto con ContactID 1.</span><span class="sxs-lookup"><span data-stu-id="d04c5-117">For example, this updategram changes the value in the Phone column of the Person.Contact table for the contact with ContactID of 1.</span></span> <span data-ttu-id="d04c5-118">Il **\<before>** blocco specifica l'attributo **Phone** per garantire che il valore dell'attributo corrisponda al valore nella colonna corrispondente nel database prima di applicare il valore aggiornato.</span><span class="sxs-lookup"><span data-stu-id="d04c5-118">The **\<before>** block specifies the **Phone** attribute to ensure that this attribute value matches the value in the corresponding column in the database before applying the updated value.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
<updg:sync >  
<updg:before>  
   <Person.Contact ContactID="1" Phone="398-555-0132" />  
</updg:before>  
<updg:after>  
   <Person.Contact ContactID="1" Phone="111-111-1111" />  
</updg:after>  
</updg:sync>  
</ROOT>  
```  
  
## <a name="high-level-of-protection"></a><span data-ttu-id="d04c5-119">Livello di protezione elevato</span><span class="sxs-lookup"><span data-stu-id="d04c5-119">High Level of Protection</span></span>  
 <span data-ttu-id="d04c5-120">Un livello di protezione elevato garantisce che il record resti inalterato dall'ultima lettura da parte dell'applicazione, ovvero dal momento in cui l'applicazione ha letto il record, che non è stato modificato da alcuna transazione.</span><span class="sxs-lookup"><span data-stu-id="d04c5-120">A high level of protection ensures that the record remains the same since your application last read that record (that is, since your application has read the record, it has not been changed by any other transaction).</span></span>  
  
 <span data-ttu-id="d04c5-121">Per ottenere questo livello di protezione elevato contro aggiornamenti simultanei, sono disponibili due metodi:</span><span class="sxs-lookup"><span data-stu-id="d04c5-121">There are two ways you can get this high level of protection against concurrent updates:</span></span>  
  
-   <span data-ttu-id="d04c5-122">Consente di specificare colonne aggiuntive nella tabella del **\<before>** blocco.</span><span class="sxs-lookup"><span data-stu-id="d04c5-122">Specify additional columns in the table in the **\<before>** block.</span></span>  
  
     <span data-ttu-id="d04c5-123">Se si specificano colonne aggiuntive nel **\<before>** blocco, l'updategram confronta i valori specificati per le colonne con i valori presenti nel database prima di applicare l'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="d04c5-123">If you specify additional columns in the **\<before>** block, the updategram compares the values that are specified for these columns with the values that were in the database before applying the update.</span></span> <span data-ttu-id="d04c5-124">Se una o più delle colonne dei record è stata modificata dal momento in cui la transazione ha letto il record, l'updategram non esegue l'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="d04c5-124">If any of the record columns has changed since your transaction read the record, the updategram does not perform the update.</span></span>  
  
     <span data-ttu-id="d04c5-125">Nell'updategram seguente, ad esempio, viene aggiornato il nome dello spostamento, ma vengono specificate colonne aggiuntive (StartTime, EndTime) nel **\<before>** blocco, in modo da richiedere un livello di protezione più elevato rispetto agli aggiornamenti simultanei.</span><span class="sxs-lookup"><span data-stu-id="d04c5-125">For example, the following updategram updates the shift name, but specifies additional columns (StartTime,EndTime) in the **\<before>** block, thereby requesting a higher level of protection against concurrent updates.</span></span>  
  
    ```  
    <ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
    <updg:sync >  
    <updg:before>  
       <HumanResources.Shift ShiftID="1"   
                 Name="Day"   
                 StartTime="1900-01-01 07:00:00.000"   
                 EndTime="1900-01-01 15:00:00.000" />  
    </updg:before>  
    <updg:after>  
       <HumanResources.Shift Name="Morning" />  
    </updg:after>  
    </updg:sync>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="d04c5-126">In questo esempio viene specificato il livello di protezione più elevato specificando tutti i valori di colonna per il record nel **\<before>** blocco.</span><span class="sxs-lookup"><span data-stu-id="d04c5-126">This example specifies the highest level of protection by specifying all column values for the record in the **\<before>** block.</span></span>  
  
-   <span data-ttu-id="d04c5-127">Consente di specificare la colonna timestamp, se disponibile, nel **\<before>** blocco.</span><span class="sxs-lookup"><span data-stu-id="d04c5-127">Specify the timestamp column (if available) in the **\<before>** block.</span></span>  
  
     <span data-ttu-id="d04c5-128">Anziché specificare tutte le colonne dei record nel `<before` blocco>, è possibile specificare solo la colonna timestamp, se presente nella tabella, insieme alle colonne chiave primaria nel **\<before>** blocco.</span><span class="sxs-lookup"><span data-stu-id="d04c5-128">Instead of specifying all the record columns in the `<before`> block, you can just specify the timestamp column (if the table has one) along with the primary key column(s) in the **\<before>** block.</span></span> <span data-ttu-id="d04c5-129">Il database aggiorna la colonna timestamp a un valore univoco dopo ogni aggiornamento del record.</span><span class="sxs-lookup"><span data-stu-id="d04c5-129">The database updates the timestamp column to a unique value after each update of the record.</span></span> <span data-ttu-id="d04c5-130">In questo caso, l'updategram confronta il valore del timestamp con il valore corrispondente nel database.</span><span class="sxs-lookup"><span data-stu-id="d04c5-130">In this case, the updategram compares the value of the timestamp with the corresponding value in the database.</span></span> <span data-ttu-id="d04c5-131">Il valore del timestamp archiviato nel database è un valore binary.</span><span class="sxs-lookup"><span data-stu-id="d04c5-131">The timestamp value stored in the database is a binary value.</span></span> <span data-ttu-id="d04c5-132">La colonna timestamp, pertanto, deve essere specificata nello schema come `dt:type="bin.hex"`, `dt:type="bin.base64"` o `sql:datatype="timestamp"`.</span><span class="sxs-lookup"><span data-stu-id="d04c5-132">Therefore, the timestamp column must be specified in the schema as `dt:type="bin.hex"`, `dt:type="bin.base64"`, or `sql:datatype="timestamp"`.</span></span> <span data-ttu-id="d04c5-133">È possibile specificare il tipo di `xml` dati o il [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="d04c5-133">(You can specify either the `xml` data type or the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] data type.)</span></span>  
  
#### <a name="to-test-the-updategram"></a><span data-ttu-id="d04c5-134">Per testare l'updategram</span><span class="sxs-lookup"><span data-stu-id="d04c5-134">To test the updategram</span></span>  
  
1.  <span data-ttu-id="d04c5-135">Creare questa tabella nel database **tempdb** :</span><span class="sxs-lookup"><span data-stu-id="d04c5-135">Create this table in the **tempdb** database:</span></span>  
  
    ```  
    USE tempdb  
    CREATE TABLE Customer (  
                 CustomerID  varchar(5),  
                 ContactName varchar(20),  
                 LastUpdated timestamp)  
    ```  
  
2.  <span data-ttu-id="d04c5-136">Aggiungere il record di esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="d04c5-136">Add this sample record:</span></span>  
  
    ```  
    INSERT INTO Customer (CustomerID, ContactName) VALUES   
                         ('C1', 'Andrew Fuller')  
    ```  
  
3.  <span data-ttu-id="d04c5-137">Copiare lo schema XSD seguente e incollarlo in Blocco note.</span><span class="sxs-lookup"><span data-stu-id="d04c5-137">Copy the following XSD schema and paste it into Notepad.</span></span> <span data-ttu-id="d04c5-138">Salvarlo come file ConcurrencySampleSchema.xml:</span><span class="sxs-lookup"><span data-stu-id="d04c5-138">Save it as ConcurrencySampleSchema.xml:</span></span>  
  
    ```  
    <xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
                xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
      <xsd:element name="Customer" sql:relation="Customer" >  
       <xsd:complexType>  
            <xsd:attribute name="CustomerID"    
                           sql:field="CustomerID"   
                           type="xsd:string" />   
  
            <xsd:attribute name="ContactName"    
                           sql:field="ContactName"   
                           type="xsd:string" />  
  
            <xsd:attribute name="LastUpdated"   
                           sql:field="LastUpdated"   
                           type="xsd:hexBinary"   
                 sql:datatype="timestamp" />  
  
        </xsd:complexType>  
      </xsd:element>  
    </xsd:schema>  
    ```  
  
4.  <span data-ttu-id="d04c5-139">Copiare il codice dell'updategram seguente in Blocco note e salvarlo come ConcurrencySampleTemplate.xml nella stessa directory in cui è stato salvato lo schema creato nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="d04c5-139">Copy the following updategram code into Notepad and save it as ConcurrencySampleTemplate.xml in the same directory where you saved the schema created in the previous step.</span></span> <span data-ttu-id="d04c5-140">Si noti che il valore del timestamp indicato di seguito per LastUpdated differirà nella tabella Customer di esempio. Copiare pertanto il valore effettivo di LastUpdated dalla tabella e incollarlo nell'updategram.</span><span class="sxs-lookup"><span data-stu-id="d04c5-140">(Note the timestamp value below for LastUpdated will differ in your example Customer table, so copy the actual value for LastUpdated from the table and paste it into the updategram.)</span></span>  
  
    ```  
    <ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
    <updg:sync mapping-schema="SampleSchema.xml" >  
    <updg:before>  
       <Customer CustomerID="C1"   
                 LastUpdated = "0x00000000000007D1" />  
    </updg:before>  
    <updg:after>  
       <Customer ContactName="Robert King" />  
    </updg:after>  
    </updg:sync>  
    </ROOT>  
    ```  
  
5.  <span data-ttu-id="d04c5-141">Creare e utilizzare lo script di test SQLXML 4.0 (Sqlxml4test.vbs) per eseguire il modello.</span><span class="sxs-lookup"><span data-stu-id="d04c5-141">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="d04c5-142">Per ulteriori informazioni, vedere [utilizzo di ADO per eseguire query SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="d04c5-142">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="d04c5-143">Di seguito viene indicato lo schema XDR equivalente:</span><span class="sxs-lookup"><span data-stu-id="d04c5-143">This is the equivalent XDR schema:</span></span>  
  
```  
<?xml version="1.0" ?>  
<Schema xmlns="urn:schemas-microsoft-com:xml-data"  
        xmlns:dt="urn:schemas-microsoft-com:datatypes"  
        xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
<ElementType name="Customer" sql:relation="Customer" >  
    <AttributeType name="CustomerID" />  
    <AttributeType name="ContactName" />  
    <AttributeType name="LastUpdated"  dt:type="bin.hex"   
                                       sql:datatype="timestamp" />  
    <attribute type="CustomerID" />  
    <attribute type="ContactName" />  
    <attribute type="LastUpdated" />  
</ElementType>  
</Schema>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d04c5-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d04c5-144">See Also</span></span>  
 [<span data-ttu-id="d04c5-145">Considerazioni sulla sicurezza degli updategram &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="d04c5-145">Updategram Security Considerations &#40;SQLXML 4.0&#41;</span></span>](../security/updategram-security-considerations-sqlxml-4-0.md)  
  
  
