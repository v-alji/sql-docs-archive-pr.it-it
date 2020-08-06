---
title: Processo di generazione di record (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- XML Bulk Load [SQLXML], record generation process
- node scopes [SQLXML]
- record subsets [SQLXML]
- scope [SQLXML]
- key ordering rules [SQLXML]
- record generation process for bulk loads [SQLXML]
- entering node scope [SQLXML]
- bulk load [SQLXML], record generation process
- leaving node scope [SQLXML]
- schema mapping [SQLXML]
ms.assetid: d8885bbe-6f15-4fb9-9684-ca7883cfe9ac
author: rothja
ms.author: jroth
ms.openlocfilehash: 5734776864aecbda7adaf0b9b16180b5ebd55ce3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711819"
---
# <a name="record-generation-process-sqlxml-40"></a><span data-ttu-id="12869-102">Processo di generazione di record (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="12869-102">Record Generation Process (SQLXML 4.0)</span></span>
  <span data-ttu-id="12869-103">Il caricamento bulk XML elabora i dati di input XML e prepara record per le tabelle appropriate in Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="12869-103">XML Bulk Load processes the XML input data and prepares records for the appropriate tables in Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="12869-104">La logica nel caricamento bulk XML determina il momento in cui generare un nuovo record, i valori di elemento o attributo figlio da copiare nei campi del record e il momento in cui il record è completo e pronto per essere inviato a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] per l'inserimento.</span><span class="sxs-lookup"><span data-stu-id="12869-104">The logic in XML Bulk Load determines when to generate a new record, what child element or attribute values to copy into the fields of the record, and when the record is complete and ready to be sent to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] for insertion.</span></span>  
  
 <span data-ttu-id="12869-105">Il caricamento bulk XML non carica tutti i dati di input XML in memoria e non produce set di record completi prima di inviare dati a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="12869-105">XML Bulk Load does not load the entire XML input data into memory, and does not produce complete record sets before sending data to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="12869-106">Ciò è dovuto al fatto che i dati di input XML possono essere costituiti da un documento di grandi dimensioni, il cui caricamento in memoria può risultare dispendioso.</span><span class="sxs-lookup"><span data-stu-id="12869-106">This is because XML input data can be a large document and loading the entire document in memory can be expensive.</span></span> <span data-ttu-id="12869-107">Al contrario, il caricamento bulk XML esegue le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="12869-107">Instead, XML Bulk Load does the following:</span></span>  
  
1.  <span data-ttu-id="12869-108">Analizza lo schema di mapping e prepara il piano di esecuzione necessario.</span><span class="sxs-lookup"><span data-stu-id="12869-108">Analyzes the mapping schema and prepares the necessary execution plan.</span></span>  
  
2.  <span data-ttu-id="12869-109">Applica il piano di esecuzione ai dati nel flusso di input.</span><span class="sxs-lookup"><span data-stu-id="12869-109">Applies the execution plan to the data in the input stream.</span></span>  
  
 <span data-ttu-id="12869-110">Questa elaborazione sequenziale rende essenziale fornire i dati di input XML in un modo specifico.</span><span class="sxs-lookup"><span data-stu-id="12869-110">This sequential processing makes it important to provide the XML input data in a specific way.</span></span> <span data-ttu-id="12869-111">È necessario comprendere il modo in cui il caricamento bulk XML analizza lo schema di mapping e la modalità di esecuzione del processo di generazione di record.</span><span class="sxs-lookup"><span data-stu-id="12869-111">You must understand how XML Bulk Load analyzes the mapping schema and how the record generation process occurs.</span></span> <span data-ttu-id="12869-112">Una volta compresi questi elementi, è possibile fornire uno schema di mapping al caricamento bulk XML che produca i risultati desiderati.</span><span class="sxs-lookup"><span data-stu-id="12869-112">With this understanding, you can provide a mapping schema to XML Bulk Load that produces the results you want.</span></span>  
  
 <span data-ttu-id="12869-113">Il caricamento bulk XML gestisce annotazioni dello schema di mapping, inclusi i mapping di colonne e tabelle (specificati in modo esplicito utilizzando annotazioni o in modo implicito tramite il mapping predefinito), e relazioni di join comuni.</span><span class="sxs-lookup"><span data-stu-id="12869-113">XML Bulk Load handles common mapping schema annotations, including column and table mappings (specified explicitly by using annotations or implicitly through the default mapping), and join relationships.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="12869-114">Si presuppone una certa familiarità con gli schemi di mapping XSD o XDR con annotazioni.</span><span class="sxs-lookup"><span data-stu-id="12869-114">It is assumed that you are familiar with annotated XSD or XDR mapping schemas.</span></span> <span data-ttu-id="12869-115">Per ulteriori informazioni sugli schemi, vedere [Introduzione agli schemi XSD con Annotazioni &#40;sqlxml 4,0&#41;](../../sqlxml/annotated-xsd-schemas/introduction-to-annotated-xsd-schemas-sqlxml-4-0.md) o [schemi XDR con annotazioni &#40;deprecati in SQLXML 4,0&#41;](../../sqlxml/annotated-xsd-schemas/annotated-xdr-schemas-deprecated-in-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="12869-115">For more information about schemas, see [Introduction to Annotated XSD Schemas &#40;SQLXML 4.0&#41;](../../sqlxml/annotated-xsd-schemas/introduction-to-annotated-xsd-schemas-sqlxml-4-0.md) or [Annotated XDR Schemas &#40;Deprecated in SQLXML 4.0&#41;](../../sqlxml/annotated-xsd-schemas/annotated-xdr-schemas-deprecated-in-sqlxml-4-0.md).</span></span>  
  
 <span data-ttu-id="12869-116">La comprensione della generazione di record richiede una certa familiarità con i concetti seguenti:</span><span class="sxs-lookup"><span data-stu-id="12869-116">Understanding record generation requires understanding the following concepts:</span></span>  
  
-   <span data-ttu-id="12869-117">Ambito di un nodo</span><span class="sxs-lookup"><span data-stu-id="12869-117">Scope of a node</span></span>  
  
-   <span data-ttu-id="12869-118">Regola di generazione di record</span><span class="sxs-lookup"><span data-stu-id="12869-118">Record Generation Rule</span></span>  
  
-   <span data-ttu-id="12869-119">Subset di record e regola di ordinamento delle chiavi</span><span class="sxs-lookup"><span data-stu-id="12869-119">Record subset and the Key Ordering Rule</span></span>  
  
-   <span data-ttu-id="12869-120">Eccezioni alla regola di generazione di record</span><span class="sxs-lookup"><span data-stu-id="12869-120">Exceptions to the Record Generation Rule</span></span>  
  
## <a name="scope-of-a-node"></a><span data-ttu-id="12869-121">Ambito di un nodo</span><span class="sxs-lookup"><span data-stu-id="12869-121">Scope of a Node</span></span>  
 <span data-ttu-id="12869-122">Un nodo (un elemento o un attributo) in un documento XML entra *nell'ambito* quando il caricamento bulk XML lo rileva nel flusso di dati di input XML.</span><span class="sxs-lookup"><span data-stu-id="12869-122">A node (an element or an attribute) in an XML document enters *into scope* when XML Bulk Load encounters it in the XML input data stream.</span></span> <span data-ttu-id="12869-123">Per un nodo elemento, il tag di inizio dell'elemento inserisce l'elemento nell'ambito.</span><span class="sxs-lookup"><span data-stu-id="12869-123">For an element node, the start tag of the element brings the element in scope.</span></span> <span data-ttu-id="12869-124">Per un nodo attributo, il nome di attributo inserisce l'attributo nell'ambito.</span><span class="sxs-lookup"><span data-stu-id="12869-124">For an attribute node, the attribute name brings the attribute in scope.</span></span>  
  
 <span data-ttu-id="12869-125">Un nodo abbandona l'ambito quando non include più dati in corrispondenza del tag di fine (nel caso di un nodo elemento) o alla fine di un valore di attributo (nel caso di un nodo attributo).</span><span class="sxs-lookup"><span data-stu-id="12869-125">A node leaves scope when there is no more data for it: either at the end tag (in the case of an element node) or at the end of an attribute value (in the case of an attribute node).</span></span>  
  
## <a name="record-generation-rule"></a><span data-ttu-id="12869-126">Regola di generazione di record</span><span class="sxs-lookup"><span data-stu-id="12869-126">Record Generation Rule</span></span>  
 <span data-ttu-id="12869-127">Quando un nodo (elemento o attributo) entra nell'ambito, è possibile che venga generato un record dal nodo.</span><span class="sxs-lookup"><span data-stu-id="12869-127">When a node (element or attribute) enters into scope, there is a potential for generating a record from that node.</span></span> <span data-ttu-id="12869-128">Il record dura fino a quando il nodo associato resta nell'ambito.</span><span class="sxs-lookup"><span data-stu-id="12869-128">The record lives as long as the associated node is in scope.</span></span> <span data-ttu-id="12869-129">Quando il nodo abbandona l'ambito, il caricamento bulk XML considera completo il record generato (con i dati) e lo invia a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] per l'inserimento.</span><span class="sxs-lookup"><span data-stu-id="12869-129">When the node goes out of scope, XML Bulk Load considers the generated record complete (with data) and sends it to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] for insertion.</span></span>  
  
 <span data-ttu-id="12869-130">Si consideri ad esempio il seguente frammento di schema XSD:</span><span class="sxs-lookup"><span data-stu-id="12869-130">For example, consider the following XSD schema fragment:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:element name="Customer" sql:relation="Customers" >  
   <xsd:complexType>  
     <xsd:attribute name="CustomerID" type="xsd:string" />  
     <xsd:attribute name="CompanyName" type="xsd:string" />  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="12869-131">Lo schema specifica un **\<Customer>** elemento con gli attributi **CustomerID** e **CompanyName** .</span><span class="sxs-lookup"><span data-stu-id="12869-131">The schema specifies a **\<Customer>** element with **CustomerID** and **CompanyName** attributes.</span></span> <span data-ttu-id="12869-132">L' `sql:relation` annotazione esegue il mapping dell' **\<Customer>** elemento alla tabella Customers.</span><span class="sxs-lookup"><span data-stu-id="12869-132">The `sql:relation` annotation maps the **\<Customer>** element to the Customers table.</span></span>  
  
 <span data-ttu-id="12869-133">Si consideri il frammento seguente di un documento XML:</span><span class="sxs-lookup"><span data-stu-id="12869-133">Consider this fragment of an XML document:</span></span>  
  
```  
<Customer CustomerID="1" CompanyName="xyz" />  
<Customer CustomerID="2" CompanyName="abc" />  
...  
```  
  
 <span data-ttu-id="12869-134">Quando il caricamento bulk XML riceve lo schema descritto nei paragrafi precedenti e i dati XML come input, elabora i nodi (elementi e attributi) nei dati di origine nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="12869-134">When XML Bulk Load is provided with the schema described in the preceding paragraphs and XML data as input, it processes the nodes (elements and attributes) in the source data as follows:</span></span>  
  
-   <span data-ttu-id="12869-135">Il tag di inizio del primo **\<Customer>** elemento porta l'elemento nell'ambito.</span><span class="sxs-lookup"><span data-stu-id="12869-135">The start tag of the first **\<Customer>** element brings that element in scope.</span></span> <span data-ttu-id="12869-136">Questo nodo viene mappato alla tabella Customers.</span><span class="sxs-lookup"><span data-stu-id="12869-136">This node maps to the Customers table.</span></span> <span data-ttu-id="12869-137">Il caricamento bulk XML genera pertanto un record per la tabella Customers.</span><span class="sxs-lookup"><span data-stu-id="12869-137">Therefore, XML Bulk Load generates a record for the Customers table.</span></span>  
  
-   <span data-ttu-id="12869-138">Nello schema tutti gli attributi dell'elemento vengono **\<Customer>** mappati alle colonne della tabella Customers.</span><span class="sxs-lookup"><span data-stu-id="12869-138">In the schema, all attributes of the **\<Customer>** element map to columns of the Customers table.</span></span> <span data-ttu-id="12869-139">Poiché questi attributi entrano nell'ambito, il caricamento bulk XML ne copia i valori nel record del cliente già generato dall'ambito padre.</span><span class="sxs-lookup"><span data-stu-id="12869-139">As these attributes enter into scope, XML Bulk Load copies their values to the customer record that is already generated by the parent scope.</span></span>  
  
-   <span data-ttu-id="12869-140">Quando il caricamento bulk XML raggiunge il tag di fine per l' **\<Customer>** elemento, l'elemento esce dall'ambito.</span><span class="sxs-lookup"><span data-stu-id="12869-140">When XML Bulk Load reaches the end tag for the **\<Customer>** element, the element goes out of scope.</span></span> <span data-ttu-id="12869-141">Di conseguenza, il caricamento bulk XML considera il record completo e lo invia a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="12869-141">This causes XML Bulk Load to consider the record complete and send it to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="12869-142">Il caricamento bulk XML segue questo processo per ogni **\<Customer>** elemento successivo.</span><span class="sxs-lookup"><span data-stu-id="12869-142">XML Bulk Load follows this process for each subsequent **\<Customer>** element.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="12869-143">In questo modello, poiché viene inserito un record quando viene raggiunto il tag di fine (o il nodo è esterno all'ambito), è necessario definire tutti i dati associati al record all'interno dell'ambito del nodo.</span><span class="sxs-lookup"><span data-stu-id="12869-143">In this model, because a record is inserted when the end tag is reached (or the node is out of scope), you must define all of the data that is associated with the record within the scope of the node.</span></span>  
  
## <a name="record-subset-and-the-key-ordering-rule"></a><span data-ttu-id="12869-144">Subset di record e regola di ordinamento delle chiavi</span><span class="sxs-lookup"><span data-stu-id="12869-144">Record Subset and the Key Ordering Rule</span></span>  
 <span data-ttu-id="12869-145">Quando si specifica uno schema di mapping che utilizza `<sql:relationship>`, il termine subset si riferisce al set di record generato sul lato esterno della relazione.</span><span class="sxs-lookup"><span data-stu-id="12869-145">When you specify a mapping schema that uses `<sql:relationship>`, the subset term refers to the set of records that is generated on the foreign side of the relationship.</span></span> <span data-ttu-id="12869-146">Nell'esempio seguente i record CustOrder sono sul lato esterno, `<sql:relationship>`.</span><span class="sxs-lookup"><span data-stu-id="12869-146">In the following example, the CustOrder records are on the foreign side, `<sql:relationship>`.</span></span>  
  
 <span data-ttu-id="12869-147">Si supponga, ad esempio, un database contenente le tabelle seguenti:</span><span class="sxs-lookup"><span data-stu-id="12869-147">For example, suppose a database contains the following tables:</span></span>  
  
-   <span data-ttu-id="12869-148">Cust (CustomerID, CompanyName, City)</span><span class="sxs-lookup"><span data-stu-id="12869-148">Cust (CustomerID, CompanyName, City)</span></span>  
  
-   <span data-ttu-id="12869-149">CustOrder (CustomerID, OrderID)</span><span class="sxs-lookup"><span data-stu-id="12869-149">CustOrder (CustomerID, OrderID)</span></span>  
  
 <span data-ttu-id="12869-150">CustomerID nella tabella CustOrder è una chiave esterna che fa riferimento alla chiave primaria CustomerID nella tabella Cust.</span><span class="sxs-lookup"><span data-stu-id="12869-150">The CustomerID in the CustOrder table is a foreign key that refers to the CustomerID primary key in the Cust table.</span></span>  
  
 <span data-ttu-id="12869-151">Si consideri a questo punto la vista XML specificata nello schema XSD con annotazioni seguente.</span><span class="sxs-lookup"><span data-stu-id="12869-151">Now, consider the XML view as specified in the following annotated XSD schema.</span></span> <span data-ttu-id="12869-152">Questo schema utilizza `<sql:relationship>` per specificare la relazione tra le tabelle Cust e CustOrder.</span><span class="sxs-lookup"><span data-stu-id="12869-152">This schema uses `<sql:relationship>` to specify the relationship between the Cust and CustOrder tables.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
<xsd:annotation>  
  <xsd:appinfo>  
    <sql:relationship name="CustCustOrder"  
          parent="Cust"  
          parent-key="CustomerID"  
          child="CustOrder"  
          child-key="CustomerID" />  
  </xsd:appinfo>  
</xsd:annotation>  
  
  <xsd:element name="Customers" sql:relation="Cust" >  
   <xsd:complexType>  
     <xsd:sequence>  
       <xsd:element name="CustomerID"  type="xsd:integer" />  
       <xsd:element name="CompanyName" type="xsd:string" />  
       <xsd:element name="City"        type="xsd:string" />  
       <xsd:element name="Order"   
                          sql:relation="CustOrder"  
                          sql:relationship="CustCustOrder" >  
         <xsd:complexType>  
          <xsd:attribute name="OrderID" type="xsd:integer" />  
         </xsd:complexType>  
       </xsd:element>  
     </xsd:sequence>  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="12869-153">I dati XML di esempio e la procedura per creare un esempio reale vengono forniti di seguito.</span><span class="sxs-lookup"><span data-stu-id="12869-153">The sample XML data and the steps to create a working sample are given below.</span></span>  
  
-   <span data-ttu-id="12869-154">Quando un **\<Customer>** nodo di elemento nel file di dati XML entra nell'ambito, il caricamento bulk XML genera un record per la tabella Cust.</span><span class="sxs-lookup"><span data-stu-id="12869-154">When a **\<Customer>** element node in the XML data file enters into scope, XML Bulk Load generates a record for the Cust table.</span></span> <span data-ttu-id="12869-155">Il caricamento bulk XML copia quindi i valori di colonna necessari (CustomerID, CompanyName e City) dagli **\<CustomerID>** **\<CompanyName>** elementi, e **\<City>** figlio quando questi elementi entrano nell'ambito.</span><span class="sxs-lookup"><span data-stu-id="12869-155">XML Bulk Load then copies the necessary column values (CustomerID, CompanyName, and City) from the **\<CustomerID>**, **\<CompanyName>**, and the **\<City>** child elements as these elements enter into scope.</span></span>  
  
-   <span data-ttu-id="12869-156">Quando un **\<Order>** nodo elemento entra nell'ambito, il caricamento bulk XML genera un record per la tabella CustOrder.</span><span class="sxs-lookup"><span data-stu-id="12869-156">When an **\<Order>** element node enters into scope, XML Bulk Load generates a record for the CustOrder table.</span></span> <span data-ttu-id="12869-157">Il caricamento bulk XML copia il valore dell'attributo **OrderID** in questo record.</span><span class="sxs-lookup"><span data-stu-id="12869-157">XML Bulk Load copies the value of the **OrderID** attribute to this record.</span></span> <span data-ttu-id="12869-158">Il valore richiesto per la colonna CustomerID viene ottenuto dall' **\<CustomerID>** elemento figlio dell' **\<Customer>** elemento.</span><span class="sxs-lookup"><span data-stu-id="12869-158">The value required for the CustomerID column is obtained from the **\<CustomerID>** child element of the **\<Customer>** element.</span></span> <span data-ttu-id="12869-159">Il caricamento bulk XML utilizza le informazioni specificate in `<sql:relationship>` per ottenere il valore della chiave esterna CustomerID per questo record, a meno che non sia stato specificato l'attributo **CustomerID** nell' **\<Order>** elemento.</span><span class="sxs-lookup"><span data-stu-id="12869-159">XML Bulk Load uses the information that is specified in `<sql:relationship>` to obtain the CustomerID foreign key value for this record, unless the **CustomerID** attribute was specified in the **\<Order>** element.</span></span> <span data-ttu-id="12869-160">La regola generale prevede che se l'elemento specifica in modo esplicito un valore per l'attributo chiave esterna, il caricamento bulk XML utilizza tale valore e non ottiene il valore dall'elemento padre tramite l'annotazione `<sql:relationship>` specificata.</span><span class="sxs-lookup"><span data-stu-id="12869-160">The general rule is that if the child element explicitly specifies a value for the foreign key attribute, XML Bulk Load uses that value and does not obtain the value from the parent element by using the specified `<sql:relationship>`.</span></span> <span data-ttu-id="12869-161">Poiché il **\<Order>** nodo di questo elemento esula dall'ambito, il caricamento bulk XML Invia il record a, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] quindi elabora tutti i **\<Order>** nodi elemento successivi nello stesso modo.</span><span class="sxs-lookup"><span data-stu-id="12869-161">As this **\<Order>** element node goes out of scope, XML Bulk Load sends the record to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] and then processes all the subsequent **\<Order>** element nodes in the same manner.</span></span>  
  
-   <span data-ttu-id="12869-162">Infine, il **\<Customer>** nodo dell'elemento esce dall'ambito.</span><span class="sxs-lookup"><span data-stu-id="12869-162">Finally, the **\<Customer>** element node goes out of scope.</span></span> <span data-ttu-id="12869-163">A questo punto, il caricamento bulk XML invia il record del cliente a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="12869-163">At that time, XML Bulk Load sends the customer record to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="12869-164">Il caricamento bulk XML segue questo processo per tutti i clienti successivi nel flusso di dati XML.</span><span class="sxs-lookup"><span data-stu-id="12869-164">XML Bulk Load follows this process for all the subsequent customers in the XML data stream.</span></span>  
  
 <span data-ttu-id="12869-165">Di seguito sono riportate due osservazioni sullo schema di mapping:</span><span class="sxs-lookup"><span data-stu-id="12869-165">Here are two observations about the mapping schema:</span></span>  
  
-   <span data-ttu-id="12869-166">Quando lo schema soddisfa la regola di "contenimento", ad esempio quando tutti i dati associati al cliente e all'ordine vengono definiti all'interno dell'ambito dei **\<Customer>** nodi elemento e associati **\<Order>** , il caricamento bulk ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="12869-166">When the schema satisfies the "containment" rule (for example, all data that is associated with the customer and the order is defined within the scope of the associated **\<Customer>** and **\<Order>** element nodes), the bulk load succeeds.</span></span>  
  
-   <span data-ttu-id="12869-167">Per descrivere l' **\<Customer>** elemento, i relativi elementi figlio vengono specificati nell'ordine appropriato.</span><span class="sxs-lookup"><span data-stu-id="12869-167">In describing the **\<Customer>** element, its child elements are specified in the appropriate order.</span></span> <span data-ttu-id="12869-168">In questo caso, l' **\<CustomerID>** elemento figlio viene specificato prima dell' **\<Order>** elemento figlio.</span><span class="sxs-lookup"><span data-stu-id="12869-168">In this case, the **\<CustomerID>** child element is specified before the **\<Order>** child element.</span></span> <span data-ttu-id="12869-169">Ciò significa che nel file di dati XML di input il **\<CustomerID>** valore dell'elemento è disponibile come valore di chiave esterna quando l' **\<Order>** elemento entra nell'ambito.</span><span class="sxs-lookup"><span data-stu-id="12869-169">This means that in the input XML data file, the **\<CustomerID>** element value is available as the foreign key value when the **\<Order>** element enters into scope.</span></span> <span data-ttu-id="12869-170">Gli attributi chiave vengono specificati per primi. Questo comportamento è denominato "regola di ordinamento delle chiavi".</span><span class="sxs-lookup"><span data-stu-id="12869-170">The key attributes are specified first; this is the "Key Ordering Rule."</span></span>  
  
     <span data-ttu-id="12869-171">Se si specifica l' **\<CustomerID>** elemento figlio dopo l' **\<Order>** elemento figlio, il valore non è disponibile quando l' **\<Order>** elemento entra nell'ambito.</span><span class="sxs-lookup"><span data-stu-id="12869-171">If you specify the **\<CustomerID>** child element after the **\<Order>** child element, the value is not available when the **\<Order>** element enters into scope.</span></span> <span data-ttu-id="12869-172">Quando il **\</Order>** tag di fine viene letto, il record per la tabella CustOrder viene considerato completo e viene inserito nella tabella CustOrder con un valore null per la colonna CustomerID, che non è il risultato desiderato.</span><span class="sxs-lookup"><span data-stu-id="12869-172">When the **\</Order>** end tag is then read, the record for CustOrder table is considered complete and is inserted in the CustOrder table with a NULL value for the CustomerID column, which is not the desired result.</span></span>  
  
#### <a name="to-create-a-working-sample"></a><span data-ttu-id="12869-173">Per creare un esempio reale</span><span class="sxs-lookup"><span data-stu-id="12869-173">To create a working sample</span></span>  
  
1.  <span data-ttu-id="12869-174">Salvare lo schema fornito in questo esempio come SampleSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="12869-174">Save the schema that is provided in this example as SampleSchema.xml.</span></span>  
  
2.  <span data-ttu-id="12869-175">Creare le tabelle seguenti:</span><span class="sxs-lookup"><span data-stu-id="12869-175">Create these tables:</span></span>  
  
    ```  
    CREATE TABLE Cust (  
                  CustomerID     int         PRIMARY KEY,  
                  CompanyName    varchar(20) NOT NULL,  
                  City           varchar(20) DEFAULT 'Seattle')  
    GO  
    CREATE TABLE CustOrder (  
                 OrderID        int         PRIMARY KEY,  
                 CustomerID     int         FOREIGN KEY REFERENCES                                          Cust(CustomerID))  
    GO  
    ```  
  
3.  <span data-ttu-id="12869-176">Salvare i dati di input XML di esempio seguenti come file SampleXMLData.xml:</span><span class="sxs-lookup"><span data-stu-id="12869-176">Save the following sample XML input data as SampleXMLData.xml:</span></span>  
  
    ```  
    <ROOT>  
      <Customers>  
        <CustomerID>1111</CustomerID>  
        <CompanyName>Hanari Carnes</CompanyName>  
        <City>NY</City>   
        <Order OrderID="1" />  
        <Order OrderID="2" />  
      </Customers>  
  
      <Customers>  
        <CustomerID>1112</CustomerID>  
        <CompanyName>Toms Spezialitten</CompanyName>  
        <City>LA</City>  
        <Order OrderID="3" />  
      </Customers>  
      <Customers>  
        <CustomerID>1113</CustomerID>  
        <CompanyName>Victuailles en stock</CompanyName>  
        <Order OrderID="4" />  
    </Customers>  
    </ROOT>  
    ```  
  
4.  <span data-ttu-id="12869-177">Per eseguire il caricamento bulk XML, salvare ed eseguire l'esempio (BulkLoad.vbs) di [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic, Scripting Edition (VBScript) seguente:</span><span class="sxs-lookup"><span data-stu-id="12869-177">To execute XML Bulk Load, save and execute the following [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic Scripting Edition (VBScript) example (BulkLoad.vbs):</span></span>  
  
    ```  
    set objBL = CreateObject("SQLXMLBulkLoad.SQLXMLBulkload.4.0")  
    objBL.ConnectionString = "provider=SQLOLEDB;data source=localhost;database=tempdb;integrated security=SSPI"  
    objBL.ErrorLogFile = "c:\error.log"  
    objBL.CheckConstraints = True  
    objBL.Execute "c:\SampleSchema.xml", "c:\SampleXMLData.xml"  
    set objBL=Nothing  
    ```  
  
## <a name="exceptions-to-the-record-generation-rule"></a><span data-ttu-id="12869-178">Eccezioni alla regola di generazione di record</span><span class="sxs-lookup"><span data-stu-id="12869-178">Exceptions to the Record Generation Rule</span></span>  
 <span data-ttu-id="12869-179">Il caricamento bulk XML non genera un record per un nodo quando entra nell'ambito se il nodo è un tipo IDREF o IDREFS.</span><span class="sxs-lookup"><span data-stu-id="12869-179">XML Bulk Load does not generate a record for a node when it enters into scope if that node is either an IDREF or IDREFS type.</span></span> <span data-ttu-id="12869-180">È necessario verificare che sia presente una descrizione completa del record in un punto dello schema.</span><span class="sxs-lookup"><span data-stu-id="12869-180">You must make sure that a complete description of the record occurs at some place in the schema.</span></span> <span data-ttu-id="12869-181">Le annotazioni `dt:type="nmtokens"` vengono ignorate, come viene ignorato il tipo IDREFS.</span><span class="sxs-lookup"><span data-stu-id="12869-181">The `dt:type="nmtokens"` annotations are ignored just as the IDREFS type is ignored.</span></span>  
  
 <span data-ttu-id="12869-182">Si consideri, ad esempio, lo schema XSD seguente che descrive **\<Customer>** **\<Order>** gli elementi e.</span><span class="sxs-lookup"><span data-stu-id="12869-182">For example, consider the following XSD schema that describes **\<Customer>** and **\<Order>** elements.</span></span> <span data-ttu-id="12869-183">L' **\<Customer>** elemento include un attributo **ordery** del tipo IDREFS.</span><span class="sxs-lookup"><span data-stu-id="12869-183">The **\<Customer>** element includes an **OrderList** attribute of the IDREFS type.</span></span> <span data-ttu-id="12869-184">Il tag `<sql:relationship>` specifica la relazione uno-a-molti tra il cliente e l'elenco di ordini.</span><span class="sxs-lookup"><span data-stu-id="12869-184">The `<sql:relationship>` tag specifies the one-to-many relationship between the customer and list of orders.</span></span>  
  
 <span data-ttu-id="12869-185">Lo schema è il seguente:</span><span class="sxs-lookup"><span data-stu-id="12869-185">This is the schema:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
<xsd:annotation>  
  <xsd:appinfo>  
    <sql:relationship name="CustCustOrder"  
                 parent="Cust"  
                 parent-key="CustomerID"  
                 child="CustOrder"  
                 child-key="CustomerID" />  
  </xsd:appinfo>  
</xsd:annotation>  
  
  <xsd:element name="Customers" sql:relation="Cust" >  
   <xsd:complexType>  
    <xsd:attribute name="CustomerID" type="xsd:integer" />  
    <xsd:attribute name="CompanyName" type="xsd:string" />  
    <xsd:attribute name="City" type="xsd:string" />  
    <xsd:attribute name="OrderList"   
                       type="xsd:IDREFS"   
                       sql:relation="CustOrder"   
                       sql:field="OrderID"  
                       sql:relationship="CustCustOrder" >  
    </xsd:attribute>  
  </xsd:complexType>  
 </xsd:element>  
  
  <xsd:element name="Order" sql:relation="CustOrder" >  
   <xsd:complexType>  
    <xsd:attribute name="OrderID" type="xsd:string" />  
    <xsd:attribute name="CustomerID" type="xsd:integer" />  
    <xsd:attribute name="OrderDate" type="xsd:date" />  
  </xsd:complexType>  
 </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="12869-186">Poiché il caricamento bulk ignora i nodi di tipo IDREFS, non esiste alcuna generazione di record quando il nodo dell'attributo **ordery** entra nell'ambito.</span><span class="sxs-lookup"><span data-stu-id="12869-186">Because Bulk Load ignores the nodes of IDREFS type, there is no record generation when the **OrderList** attribute node enters into scope.</span></span> <span data-ttu-id="12869-187">Se pertanto si desidera che i record relativi agli ordini vengano aggiunti alla tabella Orders, è necessario descrivere tali ordini in un punto dello schema.</span><span class="sxs-lookup"><span data-stu-id="12869-187">Therefore, if you want the order records added to the Orders table, you must describe those orders somewhere in the schema.</span></span> <span data-ttu-id="12869-188">In questo schema, specificando l' **\<Order>** elemento si garantisce che il caricamento bulk XML aggiunga i record degli ordini alla tabella Orders.</span><span class="sxs-lookup"><span data-stu-id="12869-188">In this schema, specifying the **\<Order>** element ensures that XML Bulk Load adds the order records to the Orders table.</span></span> <span data-ttu-id="12869-189">L' **\<Order>** elemento descrive tutti gli attributi necessari per riempire il record per la tabella CustOrder.</span><span class="sxs-lookup"><span data-stu-id="12869-189">The **\<Order>** element describes all the attributes that are required to fill the record for the CustOrder table.</span></span>  
  
 <span data-ttu-id="12869-190">È necessario assicurarsi che i valori **CustomerID** e **OrderID** nell' **\<Customer>** elemento corrispondano ai valori nell' **\<Order>** elemento.</span><span class="sxs-lookup"><span data-stu-id="12869-190">You must ensure that the **CustomerID** and **OrderID** values in the **\<Customer>** element match the values in the **\<Order>** element.</span></span> <span data-ttu-id="12869-191">L'utente è responsabile del mantenimento dell'integrità referenziale.</span><span class="sxs-lookup"><span data-stu-id="12869-191">You are responsible for maintaining referential integrity.</span></span>  
  
#### <a name="to-test-a-working-sample"></a><span data-ttu-id="12869-192">Per testare un esempio reale</span><span class="sxs-lookup"><span data-stu-id="12869-192">To test a working sample</span></span>  
  
1.  <span data-ttu-id="12869-193">Creare le tabelle seguenti:</span><span class="sxs-lookup"><span data-stu-id="12869-193">Create these tables:</span></span>  
  
    ```  
    CREATE TABLE Cust (  
                  CustomerID     int          PRIMARY KEY,  
                  CompanyName    varchar(20)  NOT NULL,  
                  City           varchar(20)  DEFAULT 'Seattle')  
    GO  
    CREATE TABLE CustOrder (  
                  OrderID        varchar(10) PRIMARY KEY,  
                  CustomerID     int         FOREIGN KEY REFERENCES                                          Cust(CustomerID),  
                  OrderDate      datetime DEFAULT '2000-01-01')  
    GO  
    ```  
  
2.  <span data-ttu-id="12869-194">Salvare lo schema di mapping fornito in questo esempio come file SampleSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="12869-194">Save the mapping schema provided in this example as SampleSchema.xml.</span></span>  
  
3.  <span data-ttu-id="12869-195">Salvare i dati XML di esempio seguenti come file SampleXMLData.xml:</span><span class="sxs-lookup"><span data-stu-id="12869-195">Save the following sample XML data as SampleXMLData.xml:</span></span>  
  
    ```  
    <ROOT>  
      <Customers CustomerID="1111" CompanyName="Sean Chai" City="NY"  
                 OrderList="Ord1 Ord2" />  
      <Customers CustomerID="1112" CompanyName="Dont Know" City="LA"  
                 OrderList="Ord3 Ord4" />  
      <Order OrderID="Ord1" CustomerID="1111" OrderDate="1999-01-01" />  
      <Order OrderID="Ord2" CustomerID="1111" OrderDate="1999-02-01" />  
      <Order OrderID="Ord3" CustomerID="1112" OrderDate="1999-03-01" />  
      <Order OrderID="Ord4" CustomerID="1112" OrderDate="1999-04-01" />  
    </ROOT>  
    ```  
  
4.  <span data-ttu-id="12869-196">Per eseguire il caricamento bulk XML, salvare ed eseguire l'esempio (SampleVB.vbs) di VBScript seguente:</span><span class="sxs-lookup"><span data-stu-id="12869-196">To execute XML Bulk Load, save and execute this VBScript example (SampleVB.vbs):</span></span>  
  
    ```  
    set objBL = CreateObject("SQLXMLBulkLoad.SQLXMLBulkload.4.0")  
    objBL.ConnectionString = "provider=SQLOLEDB;data source=localhost;database=tempdb;integrated security=SSPI"  
    objBL.ErrorLogFile = "c:\error.log"  
    objBL.CheckConstraints=True  
    objBL.Execute "c:\SampleSchema.xml", "c:\SampleXMLData.xml"  
    set objBL=Nothing  
    ```  
  
  
