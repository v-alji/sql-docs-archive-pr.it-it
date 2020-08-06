---
title: 'Specifica della profondità nelle relazioni ricorsive tramite SQL: max-depth | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- max-depth annotation
- XPath queries [SQLXML], recursive relationships
- depth in recursive relationships [SQLXML]
- annotated XSD schemas, recursive relationships
- relationships [SQLXML], recursive relationships
- self joins
- recursive relationships [SQLXML]
- recursion [SQLXML]
- sql:max-depth
- recursive joins [SQLXML]
ms.assetid: 0ffdd57d-dc30-44d9-a8a0-f21cadedb327
author: rothja
ms.author: jroth
ms.openlocfilehash: 5e3ccb2de9c7b2ac8f8702b52aa990d755620e46
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629750"
---
# <a name="specifying-depth-in-recursive-relationships-by-using-sqlmax-depth"></a><span data-ttu-id="7990d-102">Specifica del livello di nidificazione nelle relazioni ricorsive mediante sql:max-depth</span><span class="sxs-lookup"><span data-stu-id="7990d-102">Specifying Depth in Recursive Relationships by Using sql:max-depth</span></span>
  <span data-ttu-id="7990d-103">Quando nei database relazionali una tabella viene coinvolta in una relazione con sé stessa, si parla di relazione ricorsiva.</span><span class="sxs-lookup"><span data-stu-id="7990d-103">In relational databases, when a table is involved in a relationship with itself, it is called a recursive relationship.</span></span> <span data-ttu-id="7990d-104">In una relazione supervisore-supervisionato (supervisor-supervisee), ad esempio, una tabella in cui sono archiviati i record dei dipendenti è coinvolta in una relazione con sé stessa.</span><span class="sxs-lookup"><span data-stu-id="7990d-104">For example, in a supervisor-supervisee relationship, a table storing employee records is involved in a relationship with itself.</span></span> <span data-ttu-id="7990d-105">In questo caso, la stessa tabella dei dipendenti ricopre il ruolo di supervisore da un lato della relazione e di supervisionato dall'altro lato.</span><span class="sxs-lookup"><span data-stu-id="7990d-105">In this case, the employees table plays a role of supervisor on one side of the relationship, and the same table plays a role of supervisee on the other side.</span></span>  
  
 <span data-ttu-id="7990d-106">Gli schemi di mapping possono includere relazioni ricorsive nelle quali un elemento e il rispettivo predecessore sono dello stesso tipo.</span><span class="sxs-lookup"><span data-stu-id="7990d-106">Mapping schemas can include recursive relationships where an element and its ancestor are of the same type.</span></span>  
  
## <a name="example-a"></a><span data-ttu-id="7990d-107">Esempio A</span><span class="sxs-lookup"><span data-stu-id="7990d-107">Example A</span></span>  
 <span data-ttu-id="7990d-108">Si consideri la tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="7990d-108">Consider the following table:</span></span>  
  
```  
Emp (EmployeeID, FirstName, LastName, ReportsTo)  
```  
  
 <span data-ttu-id="7990d-109">Nella colonna ReportsTo di questa tabella viene archiviato l'ID dipendente del responsabile.</span><span class="sxs-lookup"><span data-stu-id="7990d-109">In this table, the ReportsTo column stores the employee ID of the manager.</span></span>  
  
 <span data-ttu-id="7990d-110">Si supponga di voler generare una gerarchia XML di dipendenti nella quale il dipendente responsabile si trova al primo posto e i dipendenti che sono sotto la supervisione del responsabile vengono visualizzati nella gerarchia corrispondente, come mostrato nel frammento XML di esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="7990d-110">Assume that you want to generate an XML hierarchy of employees in which the manager employee is at the top of the hierarchy, and in which the employees that report to that manager appear in the corresponding hierarchy as shown in the following sample XML fragment.</span></span> <span data-ttu-id="7990d-111">Questo frammento mostra l' *albero ricorsivo* per il dipendente 1.</span><span class="sxs-lookup"><span data-stu-id="7990d-111">What this fragment shows is the *recursive tree* for employee 1.</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8" ?>   
<root>  
  <Emp FirstName="Nancy" EmployeeID="1" LastName="Devolio">  
     <Emp FirstName="Andrew" EmployeeID="2" LastName="Fuller" />   
     <Emp FirstName="Janet" EmployeeID="3" LastName="Leverling">  
        <Emp FirstName="Margaret" EmployeeID="4" LastName="Peacock">  
          <Emp FirstName="Steven" EmployeeID="5" LastName="Devolio">  
...  
...  
</root>  
```  
  
 <span data-ttu-id="7990d-112">In questo frammento il dipendente 5 è sotto la supervisione del dipendente 4, il dipendente 4 è sotto la supervisione del dipendente 3 e i dipendenti 3 e 2 sono sotto la supervisione del dipendente 1.</span><span class="sxs-lookup"><span data-stu-id="7990d-112">In this fragment, employee 5 reports to employee 4, employee 4 reports to employee 3, and employees 3 and 2 reports to employee 1.</span></span>  
  
 <span data-ttu-id="7990d-113">Per produrre questo risultato, è possibile utilizzare lo schema XSD seguente e specificare una query XPath in tale schema.</span><span class="sxs-lookup"><span data-stu-id="7990d-113">To produce this result, you can use the following XSD schema and specify an XPath query against it.</span></span> <span data-ttu-id="7990d-114">Lo schema descrive un **\<Emp>** elemento di tipo EmployeeType, costituito da un **\<Emp>** elemento figlio dello stesso tipo, EmployeeType.</span><span class="sxs-lookup"><span data-stu-id="7990d-114">The schema describes an **\<Emp>** element of type EmployeeType, consisting of an **\<Emp>** child element of the same type, EmployeeType.</span></span> <span data-ttu-id="7990d-115">Si tratta di una relazione ricorsiva (l'elemento e il rispettivo predecessore sono dello stesso tipo).</span><span class="sxs-lookup"><span data-stu-id="7990d-115">This is a recursive relationship (the element and its ancestor are of the same type).</span></span> <span data-ttu-id="7990d-116">Inoltre, lo schema utilizza un oggetto **\<sql:relationship>** per descrivere la relazione padre-figlio tra il supervisore e il supervisore.</span><span class="sxs-lookup"><span data-stu-id="7990d-116">In addition, the schema uses a **\<sql:relationship>** to describe the parent-child relationship between the supervisor and supervisee.</span></span> <span data-ttu-id="7990d-117">Si noti che in questo **\<sql:relationship>** , EMP rappresenta sia la tabella padre che la tabella figlio.</span><span class="sxs-lookup"><span data-stu-id="7990d-117">Note that in this **\<sql:relationship>**, Emp is both the parent and the child table.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:dt="urn:schemas-microsoft-com:datatypes"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:annotation>  
    <xsd:appinfo>  
      <sql:relationship name="SupervisorSupervisee"  
                                  parent="Emp"  
                                  parent-key="EmployeeID"  
                                  child="Emp"  
                                  child-key="ReportsTo" />  
    </xsd:appinfo>  
  </xsd:annotation>  
  <xsd:element name="Emp" type="EmployeeType"   
                          sql:relation="Emp"   
                          sql:key-fields="EmployeeID"   
                          sql:limit-field="ReportsTo" />  
  <xsd:complexType name="EmployeeType">  
    <xsd:sequence>  
      <xsd:element name="Emp" type="EmployeeType"   
                              sql:relation="Emp"   
                              sql:key-fields="EmployeeID"  
                              sql:relationship="SupervisorSupervisee"  
                              sql:max-depth="6" />  
    </xsd:sequence>   
    <xsd:attribute name="EmployeeID" type="xsd:ID" />  
    <xsd:attribute name="FirstName" type="xsd:string"/>  
    <xsd:attribute name="LastName" type="xsd:string"/>  
  </xsd:complexType>  
</xsd:schema>  
```  
  
 <span data-ttu-id="7990d-118">Dal momento che la relazione è ricorsiva, è necessario trovare un modo per specificare il livello di nidificazione della ricorsione nello schema.</span><span class="sxs-lookup"><span data-stu-id="7990d-118">Because the relationship is recursive, you need some way to specify the depth of recursion in the schema.</span></span> <span data-ttu-id="7990d-119">In caso contrario, il risultato sarà una ricorsione infinita (il dipendente che è sotto la supervisione del dipendente che, a sua volta è sotto la supervisione del dipendente e così via).</span><span class="sxs-lookup"><span data-stu-id="7990d-119">Otherwise, the result will be an endless recursion (employee reporting to employee reporting to employee, and so on).</span></span> <span data-ttu-id="7990d-120">L'annotazione `sql:max-depth` consente di specificare il livello di nidificazione da raggiungere nella ricorsione.</span><span class="sxs-lookup"><span data-stu-id="7990d-120">The `sql:max-depth` annotation allows you to specify how deep in the recursion to go.</span></span> <span data-ttu-id="7990d-121">In questo particolare esempio, per specificare un valore per `sql:max-depth`, è necessario conoscere il livello di nidificazione della gerarchia di gestione nella società.</span><span class="sxs-lookup"><span data-stu-id="7990d-121">In this particular example, to specify a value for `sql:max-depth`, you must know how deep the management hierarchy goes in the company.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7990d-122">Lo schema specifica l'annotazione `sql:limit-field` ma non specifica l'annotazione `sql:limit-value`.</span><span class="sxs-lookup"><span data-stu-id="7990d-122">The schema specifies the `sql:limit-field` annotation, but does not specify the `sql:limit-value` annotation.</span></span> <span data-ttu-id="7990d-123">Questa situazione limita il nodo principale nella gerarchia risultante ai soli dipendenti che non sono sottoposti ad alcuna supervisione</span><span class="sxs-lookup"><span data-stu-id="7990d-123">This limits the top node in the resulting hierarchy to only those employees who do not report to anyone.</span></span> <span data-ttu-id="7990d-124">(ReportsTo è NULL). Questa operazione viene eseguita specificando `sql:limit-field` e non specificando `sql:limit-value` l'annotazione, che per impostazione predefinita è null.</span><span class="sxs-lookup"><span data-stu-id="7990d-124">(ReportsTo is NULL.) Specifying `sql:limit-field` and not specifying `sql:limit-value` (which defaults to NULL) annotation accomplishes this.</span></span> <span data-ttu-id="7990d-125">Se si desidera che l'XML risultante includa ogni possibile albero gerarchico (l'albero gerarchico per ogni dipendente della tabella), rimuovere l'annotazione `sql:limit-field` dallo schema.</span><span class="sxs-lookup"><span data-stu-id="7990d-125">If you want the resulting XML to include every possible reporting tree (the reporting tree for every employee in the table), remove the `sql:limit-field` annotation from the schema.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7990d-126">Nella procedura riportata di seguito viene utilizzato il database tempdb.</span><span class="sxs-lookup"><span data-stu-id="7990d-126">The following procedure uses the tempdb database.</span></span>  
  
#### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="7990d-127">Per testare una query Xpath di esempio sullo schema</span><span class="sxs-lookup"><span data-stu-id="7990d-127">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="7990d-128">Creare una tabella di esempio chiamata Emp nel database tempdb al quale punta la radice virtuale.</span><span class="sxs-lookup"><span data-stu-id="7990d-128">Create a sample table called Emp in the tempdb database to which the virtual root points.</span></span>  
  
    ```  
    USE tempdb  
    CREATE TABLE Emp (  
           EmployeeID int primary key,   
           FirstName  varchar(20),   
           LastName   varchar(20),   
           ReportsTo int)  
    ```  
  
2.  <span data-ttu-id="7990d-129">Aggiungere i dati di esempio seguenti:</span><span class="sxs-lookup"><span data-stu-id="7990d-129">Add this sample data:</span></span>  
  
    ```  
    INSERT INTO Emp values (1, 'Nancy', 'Devolio',NULL)  
    INSERT INTO Emp values (2, 'Andrew', 'Fuller',1)  
    INSERT INTO Emp values (3, 'Janet', 'Leverling',1)  
    INSERT INTO Emp values (4, 'Margaret', 'Peacock',3)  
    INSERT INTO Emp values (5, 'Steven', 'Devolio',4)  
    INSERT INTO Emp values (6, 'Nancy', 'Buchanan',5)  
    INSERT INTO Emp values (7, 'Michael', 'Suyama',6)  
    ```  
  
3.  <span data-ttu-id="7990d-130">Copiare il codice dello schema precedente e incollarlo in un file di testo.</span><span class="sxs-lookup"><span data-stu-id="7990d-130">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="7990d-131">Salvare il file con il nome maxDepth.xml.</span><span class="sxs-lookup"><span data-stu-id="7990d-131">Save the file as maxDepth.xml.</span></span>  
  
4.  <span data-ttu-id="7990d-132">Copiare il modello seguente e incollarlo in un file di testo.</span><span class="sxs-lookup"><span data-stu-id="7990d-132">Copy the following template and paste it into a text file.</span></span> <span data-ttu-id="7990d-133">Salvare il file con il nome maxDepthT.xml nella stessa directory nella quale è stato salvato maxDepth.xml.</span><span class="sxs-lookup"><span data-stu-id="7990d-133">Save the file as maxDepthT.xml in the same directory where you saved maxDepth.xml.</span></span> <span data-ttu-id="7990d-134">La query nel modello restituisce tutti i dipendenti della tabella Emp.</span><span class="sxs-lookup"><span data-stu-id="7990d-134">The query in the template returns all the employees in the Emp table.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="maxDepth.xml">  
        /Emp  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="7990d-135">Il percorso di directory specificato per lo schema di mapping (maxDepth.xml) è relativo alla directory nella quale viene salvato il modello.</span><span class="sxs-lookup"><span data-stu-id="7990d-135">The directory path specified for the mapping schema (maxDepth.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="7990d-136">È possibile specificare anche un percorso assoluto, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="7990d-136">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\maxDepth.xml"  
    ```  
  
5.  <span data-ttu-id="7990d-137">Creare e utilizzare lo script di test SQLXML 4.0 (Sqlxml4test.vbs) per eseguire il modello.</span><span class="sxs-lookup"><span data-stu-id="7990d-137">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span> <span data-ttu-id="7990d-138">Per ulteriori informazioni, vedere [utilizzo di ADO per eseguire query SQLXML 4,0](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="7990d-138">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="7990d-139">Risultato:</span><span class="sxs-lookup"><span data-stu-id="7990d-139">This is the result:</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8" ?>   
<root>  
  <Emp FirstName="Nancy" EmployeeID="1" LastName="Devolio">  
  <Emp FirstName="Andrew" EmployeeID="2" LastName="Fuller" />   
    <Emp FirstName="Janet" EmployeeID="3" LastName="Leverling">  
      <Emp FirstName="Margaret" EmployeeID="4" LastName="Peacock">  
        <Emp FirstName="Steven" EmployeeID="5" LastName="Devolio">  
          <Emp FirstName="Nancy" EmployeeID="6" LastName="Buchanan">  
            <Emp FirstName="Michael" EmployeeID="7" LastName="Suyama" />   
          </Emp>  
        </Emp>  
      </Emp>  
    </Emp>  
  </Emp>  
</root>  
```  
  
> [!NOTE]  
>  <span data-ttu-id="7990d-140">Per produrre livelli di nidificazione di gerarchie diverse nel risultato, modificare il valore dell'annotazione `sql:max-depth` nello schema ed eseguire nuovamente il modello dopo ogni modifica.</span><span class="sxs-lookup"><span data-stu-id="7990d-140">To produce different depths of hierarchies in the result, change the value of the `sql:max-depth` annotation in the schema and execute the template again after each change.</span></span>  
  
 <span data-ttu-id="7990d-141">Nello schema precedente tutti gli **\<Emp>** elementi hanno esattamente lo stesso set di attributi (**EmployeeID**, **FirstName**e **LastName**).</span><span class="sxs-lookup"><span data-stu-id="7990d-141">In the previous schema, all the **\<Emp>** elements had exactly the same set of attributes (**EmployeeID**, **FirstName**, and **LastName**).</span></span> <span data-ttu-id="7990d-142">Lo schema seguente è stato leggermente modificato per restituire un attributo **ReportsTo** aggiuntivo per tutti gli **\<Emp>** elementi che fanno rapporto a un responsabile.</span><span class="sxs-lookup"><span data-stu-id="7990d-142">The following schema has been slightly modified to return an additional **ReportsTo** attribute for all the **\<Emp>** elements that report to a manager.</span></span>  
  
 <span data-ttu-id="7990d-143">Questo frammento XML, ad esempio, mostra i subalterni del dipendente 1:</span><span class="sxs-lookup"><span data-stu-id="7990d-143">For example, this XML fragment shows the subordinates of employee 1:</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8" ?>   
<root>  
<Emp FirstName="Nancy" EmployeeID="1" LastName="Devolio">  
  <Emp FirstName="Andrew" EmployeeID="2"   
       ReportsTo="1" LastName="Fuller" />   
  <Emp FirstName="Janet" EmployeeID="3"   
       ReportsTo="1" LastName="Leverling">  
...  
...  
```  
  
 <span data-ttu-id="7990d-144">Questo è lo schema corretto:</span><span class="sxs-lookup"><span data-stu-id="7990d-144">This is the revised schema:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:dt="urn:schemas-microsoft-com:datatypes"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:annotation>  
    <xsd:documentation>  
      Customer-Order-Order Details Schema  
      Copyright 2000 Microsoft. All rights reserved.  
    </xsd:documentation>  
    <xsd:appinfo>  
      <sql:relationship name="SupervisorSupervisee"   
                  parent="Emp"  
                  parent-key="EmployeeID"  
                  child="Emp"  
                  child-key="ReportsTo" />  
    </xsd:appinfo>  
  </xsd:annotation>  
  <xsd:element name="Emp"   
                   type="EmpType"   
                   sql:relation="Emp"   
                   sql:key-fields="EmployeeID"   
                   sql:limit-field="ReportsTo" />  
  <xsd:complexType name="EmpType">  
    <xsd:sequence>  
       <xsd:element name="Emp"   
                    type="EmpType"   
                    sql:relation="Emp"   
                    sql:key-fields="EmployeeID"  
                    sql:relationship="SupervisorSupervisee"  
                    sql:max-depth="6"/>  
    </xsd:sequence>   
    <xsd:attribute name="EmployeeID" type="xsd:int" />  
    <xsd:attribute name="FirstName" type="xsd:string"/>  
    <xsd:attribute name="LastName" type="xsd:string"/>  
    <xsd:attribute name="ReportsTo" type="xsd:int" />  
  </xsd:complexType>  
</xsd:schema>  
```  
  
## <a name="sqlmax-depth-annotation"></a><span data-ttu-id="7990d-145">Annotazione sql:max-depth</span><span class="sxs-lookup"><span data-stu-id="7990d-145">sql:max-depth Annotation</span></span>  
 <span data-ttu-id="7990d-146">In un schema costituito da relazioni ricorsive il livello di nidificazione della ricorsione deve essere specificata in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="7990d-146">In a schema consisting of recursive relationships, the depth of recursion must be explicitly specified in the schema.</span></span> <span data-ttu-id="7990d-147">Questa operazione è necessaria per produrre correttamente la query FOR XML EXPLICIT corrispondente che restituisce i risultati richiesti.</span><span class="sxs-lookup"><span data-stu-id="7990d-147">This is required to successfully produce the corresponding FOR XML EXPLICIT query that returns the requested results.</span></span>  
  
 <span data-ttu-id="7990d-148">Utilizzare l'annotazione `sql:max-depth` nello schema per specificare il livello di nidificazione della ricorsione in una relazione ricorsiva descritta nello schema.</span><span class="sxs-lookup"><span data-stu-id="7990d-148">Use the `sql:max-depth` annotation in the schema to specify the depth of recursion in a recursive relationship that is described in the schema.</span></span> <span data-ttu-id="7990d-149">Il valore dell'annotazione `sql:max-depth` è un numero intero positivo (da 1 a 50) che indica il numero di ricorsioni: 1 arresta la ricorsione in corrispondenza dell'elemento per il quale è stata specificata l'annotazione `sql:max-depth`, 2 arresta la ricorsione al livello successivo rispetto all'elemento per il quale è stato specificato `sql:max-depth` e così via.</span><span class="sxs-lookup"><span data-stu-id="7990d-149">The value of the `sql:max-depth` annotation is a positive integer (1 to 50) that indicates the number of recursions:  A value of 1 stops the recursion at the element for which the `sql:max-depth` annotation is specified; a value of 2 stops the recursion at the next level from the element at which `sql:max-depth` is specified; and so on.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7990d-150">Nell'implementazione sottostante, una query XPath specificata su uno schema di mapping viene convertita in un oggetto SELECT... Query FOR XML EXPLICIT.</span><span class="sxs-lookup"><span data-stu-id="7990d-150">In the underlying implementation, an XPath query that is specified against a mapping schema is converted to a SELECT ... FOR XML EXPLICIT query.</span></span> <span data-ttu-id="7990d-151">Questa query richiede che venga specificato un livello di nidificazione limitato della ricorsione.</span><span class="sxs-lookup"><span data-stu-id="7990d-151">This query requires you to specify a finite depth of recursion.</span></span> <span data-ttu-id="7990d-152">Più alto è il valore specificato per `sql:max-depth`, più grande sarà la query FOR XML EXPLICIT che verrà generata,</span><span class="sxs-lookup"><span data-stu-id="7990d-152">The higher the value that you specify for `sql:max-depth`, the larger the FOR XML EXPLICIT query that is generated.</span></span> <span data-ttu-id="7990d-153">con un probabile rallentamento del tempo di recupero.</span><span class="sxs-lookup"><span data-stu-id="7990d-153">This might slow the retrieval time.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7990d-154">Gli updategram e il caricamento bulk XML ignorano l'annotazione max-depth,</span><span class="sxs-lookup"><span data-stu-id="7990d-154">Updategrams and XML Bulk Load ignore the max-depth annotation.</span></span> <span data-ttu-id="7990d-155">pertanto gli inserimenti o gli aggiornamenti ricorsivi si verificheranno indipendentemente dal valore specificato per max-depth.</span><span class="sxs-lookup"><span data-stu-id="7990d-155">This means, recursive updates or insertions will happen regardless of what value you specify for max-depth.</span></span>  
  
## <a name="specifying-sqlmax-depth-on-complex-elements"></a><span data-ttu-id="7990d-156">Specifica di sql:max-depth per gli elementi complessi</span><span class="sxs-lookup"><span data-stu-id="7990d-156">Specifying sql:max-depth on Complex Elements</span></span>  
 <span data-ttu-id="7990d-157">L'annotazione `sql:max-depth` può essere specificata su qualsiasi elemento di contenuto complesso.</span><span class="sxs-lookup"><span data-stu-id="7990d-157">The `sql:max-depth` annotation can be specified on any complex content element.</span></span>  
  
### <a name="recursive-elements"></a><span data-ttu-id="7990d-158">Elementi ricorsivi</span><span class="sxs-lookup"><span data-stu-id="7990d-158">Recursive Elements</span></span>  
 <span data-ttu-id="7990d-159">Se viene specificato un valore `sql:max-depth` sia per l'elemento padre che per l'elemento figlio in una relazione ricorsiva, l'annotazione `sql:max-depth` specificata per l'elemento padre ha la precedenza.</span><span class="sxs-lookup"><span data-stu-id="7990d-159">If `sql:max-depth` is specified on both the parent element and the child element in a recursive relationship, the `sql:max-depth` annotation specified on the parent takes precedence.</span></span> <span data-ttu-id="7990d-160">Nello schema seguente, ad esempio, l'annotazione `sql:max-depth` viene specificata per gli elementi dipendente sia padre che figlio.</span><span class="sxs-lookup"><span data-stu-id="7990d-160">For example, in the following schema, the `sql:max-depth` annotation is specified on both the parent and the child employee elements.</span></span> <span data-ttu-id="7990d-161">In questo caso,, `sql:max-depth=4` specificato nell' **\<Emp>** elemento padre (che svolge un ruolo di supervisore), ha la precedenza.</span><span class="sxs-lookup"><span data-stu-id="7990d-161">In this case, `sql:max-depth=4`, specified on the **\<Emp>** parent element (playing a role of supervisor), takes precedence.</span></span> <span data-ttu-id="7990d-162">Il valore `sql:max-depth` specificato per l' **\<Emp>** elemento figlio (che ricopre il ruolo di supervisore) viene ignorato.</span><span class="sxs-lookup"><span data-stu-id="7990d-162">The `sql:max-depth` specified on the child **\<Emp>** element (playing a role of supervisee) is ignored.</span></span>  
  
#### <a name="example-b"></a><span data-ttu-id="7990d-163">Esempio B</span><span class="sxs-lookup"><span data-stu-id="7990d-163">Example B</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:dt="urn:schemas-microsoft-com:datatypes"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:annotation>  
    <xsd:appinfo>  
      <sql:relationship name="SupervisorSupervisee"  
                                  parent="Emp"  
                                  parent-key="EmployeeID"  
                                  child="Emp"  
                                  child-key="ReportsTo" />  
    </xsd:appinfo>  
  </xsd:annotation>  
  <xsd:element name="Emp" type="EmployeeType"   
                          sql:relation="Emp"   
                          sql:key-fields="EmployeeID"   
                          sql:limit-field="ReportsTo"   
                          sql:max-depth="3" />  
  <xsd:complexType name="EmployeeType">  
    <xsd:sequence>  
      <xsd:element name="Emp" type="EmployeeType"   
                              sql:relation="Emp"   
                              sql:key-fields="EmployeeID"  
                              sql:relationship="SupervisorSupervisee"  
                              sql:max-depth="2" />  
    </xsd:sequence>   
    <xsd:attribute name="EmployeeID" type="xsd:ID" />  
    <xsd:attribute name="FirstName" type="xsd:string"/>  
    <xsd:attribute name="LastName" type="xsd:string"/>  
  </xsd:complexType>  
</xsd:schema>  
```  
  
 <span data-ttu-id="7990d-164">Per testare questo schema, seguire i passaggi forniti per il precedente esempio A in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="7990d-164">To test this schema, follow the steps provided for Sample A, earlier in this topic.</span></span>  
  
### <a name="nonrecursive-elements"></a><span data-ttu-id="7990d-165">Elementi non ricorsivi</span><span class="sxs-lookup"><span data-stu-id="7990d-165">Nonrecursive Elements</span></span>  
 <span data-ttu-id="7990d-166">Se l'annotazione `sql:max-depth` viene specificata per un elemento dello schema che non determina una ricorsione, viene ignorata.</span><span class="sxs-lookup"><span data-stu-id="7990d-166">If the `sql:max-depth` annotation is specified on an element in the schema that does not cause any recursion, it is ignored.</span></span> <span data-ttu-id="7990d-167">Nello schema seguente un elemento **\<Emp>** è costituito da un **\<Constant>** elemento figlio, che a sua volta include un **\<Emp>** elemento figlio.</span><span class="sxs-lookup"><span data-stu-id="7990d-167">In the following schema, an **\<Emp>** element consists of a **\<Constant>** child element, which, in turn, has an **\<Emp>** child element.</span></span>  
  
 <span data-ttu-id="7990d-168">In questo schema l' `sql:max-depth` annotazione specificata per l' **\<Constant>** elemento viene ignorata perché non esiste una ricorsione tra l' **\<Emp>** elemento padre e l' **\<Constant>** elemento figlio.</span><span class="sxs-lookup"><span data-stu-id="7990d-168">In this schema, the `sql:max-depth` annotation specified on the **\<Constant>** element is ignored because there is no recursion between the **\<Emp>** parent and the **\<Constant>** child element.</span></span> <span data-ttu-id="7990d-169">Tuttavia esiste una ricorsione tra il **\<Emp>** predecessore e l' **\<Emp>** elemento figlio.</span><span class="sxs-lookup"><span data-stu-id="7990d-169">But there is recursion between the **\<Emp>** ancestor and the **\<Emp>** child.</span></span> <span data-ttu-id="7990d-170">Lo schema specifica l'annotazione `sql:max-depth` per entrambi.</span><span class="sxs-lookup"><span data-stu-id="7990d-170">The schema specifies the `sql:max-depth` annotation on both.</span></span> <span data-ttu-id="7990d-171">Pertanto, l' `sql:max-depth` annotazione specificata nel predecessore ( **\<Emp>** nel ruolo Supervisore) ha la precedenza.</span><span class="sxs-lookup"><span data-stu-id="7990d-171">Therefore, the `sql:max-depth` annotation that is specified on the ancestor (**\<Emp>** in the supervisor role) takes precedence.</span></span>  
  
#### <a name="example-c"></a><span data-ttu-id="7990d-172">Esempio C</span><span class="sxs-lookup"><span data-stu-id="7990d-172">Example C</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:annotation>  
    <xsd:appinfo>  
      <sql:relationship name="SupervisorSupervisee"   
                  parent="Emp"   
                  child="Emp"   
                  parent-key="EmployeeID"   
                  child-key="ReportsTo"/>  
    </xsd:appinfo>  
  </xsd:annotation>  
  <xsd:element name="Emp"   
               sql:relation="Emp"   
               type="EmpType"  
               sql:limit-field="ReportsTo"  
               sql:max-depth="1" />  
    <xsd:complexType name="EmpType" >  
      <xsd:sequence>  
       <xsd:element name="Constant"   
                    sql:is-constant="1"   
                    sql:max-depth="20" >  
         <xsd:complexType >  
           <xsd:sequence>  
            <xsd:element name="Emp"   
                         sql:relation="Emp" type="EmpType"  
                         sql:relationship="SupervisorSupervisee"   
                         sql:max-depth="3" />  
         </xsd:sequence>  
         </xsd:complexType>  
         </xsd:element>  
      </xsd:sequence>  
      <xsd:attribute name="EmployeeID" type="xsd:int" />  
    </xsd:complexType>  
</xsd:schema>  
```  
  
 <span data-ttu-id="7990d-173">Per testare questo schema, seguire i passaggi forniti per il precedente esempio A in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="7990d-173">To test this schema, follow the steps provided for Example A, earlier in this topic.</span></span>  
  
## <a name="complex-types-derived-by-restriction"></a><span data-ttu-id="7990d-174">Tipi complessi derivati dalla restrizione</span><span class="sxs-lookup"><span data-stu-id="7990d-174">Complex Types Derived by Restriction</span></span>  
 <span data-ttu-id="7990d-175">Se si dispone di una derivazione di tipi complessi per **\<restriction>** , gli elementi del tipo complesso di base corrispondente non possono specificare l' `sql:max-depth` annotazione.</span><span class="sxs-lookup"><span data-stu-id="7990d-175">If you have a complex type derivation by **\<restriction>**, elements of the corresponding base complex type cannot specify the `sql:max-depth` annotation.</span></span> <span data-ttu-id="7990d-176">In questi casi, l'annotazione `sql:max-depth` può essere aggiunta all'elemento del tipo derivato.</span><span class="sxs-lookup"><span data-stu-id="7990d-176">In these cases, the `sql:max-depth` annotation can be added to the element of the derived type.</span></span>  
  
 <span data-ttu-id="7990d-177">D'altra parte, se si dispone di una derivazione di tipi complessi per **\<extension>** , gli elementi del tipo complesso di base corrispondente possono specificare l' `sql:max-depth` annotazione.</span><span class="sxs-lookup"><span data-stu-id="7990d-177">On the other hand, if you have a complex type derivation by **\<extension>**, the elements of the corresponding base complex type can specify the `sql:max-depth` annotation.</span></span>  
  
 <span data-ttu-id="7990d-178">Lo schema XSD seguente, ad esempio, genera un errore in quanto l'annotazione `sql:max-depth` viene specificata per il tipo di base.</span><span class="sxs-lookup"><span data-stu-id="7990d-178">For example, the following XSD schema generates an error because the `sql:max-depth` annotation is specified on the base type.</span></span> <span data-ttu-id="7990d-179">Questa annotazione non è supportata in un tipo derivato da **\<restriction>** da un altro tipo.</span><span class="sxs-lookup"><span data-stu-id="7990d-179">This annotation is not supported on a type that is derived by **\<restriction>** from another type.</span></span> <span data-ttu-id="7990d-180">Per correggere questo problema, è necessario modificare lo schema e specificare l'annotazione `sql:max-depth` per l'elemento nel tipo derivato.</span><span class="sxs-lookup"><span data-stu-id="7990d-180">To fix this problem, you must change the schema and specify the `sql:max-depth` annotation on element in the derived type.</span></span>  
  
#### <a name="example-d"></a><span data-ttu-id="7990d-181">Esempio D</span><span class="sxs-lookup"><span data-stu-id="7990d-181">Example D</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:dt="urn:schemas-microsoft-com:datatypes"  
            xmlns:msdata="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:complexType name="CustomerBaseType">   
    <xsd:sequence>  
       <xsd:element name="CID" msdata:field="CustomerID" />  
       <xsd:element name="CompanyName"/>  
       <xsd:element name="Customers" msdata:max-depth="3">  
         <xsd:annotation>  
           <xsd:appinfo>  
             <msdata:relationship  
                     parent="Customers"  
                     parent-key="CustomerID"  
                     child-key="CustomerID"  
                     child="Customers" />  
           </xsd:appinfo>  
         </xsd:annotation>  
       </xsd:element>  
    </xsd:sequence>  
  </xsd:complexType>  
  <xsd:element name="Customers" type="CustomerType"/>  
  <xsd:complexType name="CustomerType">  
    <xsd:complexContent>  
       <xsd:restriction base="CustomerBaseType">  
          <xsd:sequence>  
            <xsd:element name="CID"   
                         type="xsd:string"/>  
            <xsd:element name="CompanyName"   
                         type="xsd:string"  
                         msdata:field="CName" />  
            <xsd:element name="Customers"   
                         type="CustomerType" />  
          </xsd:sequence>  
       </xsd:restriction>  
    </xsd:complexContent>  
  </xsd:complexType>  
</xsd:schema>   
```  
  
 <span data-ttu-id="7990d-182">Nello schema `sql:max-depth` viene specificato per un tipo complesso `CustomerBaseType`.</span><span class="sxs-lookup"><span data-stu-id="7990d-182">In the schema, `sql:max-depth` is specified on a `CustomerBaseType` complex type.</span></span> <span data-ttu-id="7990d-183">Lo schema specifica anche un **\<Customer>** elemento di tipo `CustomerType` , che è derivato da `CustomerBaseType` .</span><span class="sxs-lookup"><span data-stu-id="7990d-183">The schema also specifies a **\<Customer>** element of type `CustomerType`, which is derived from `CustomerBaseType`.</span></span> <span data-ttu-id="7990d-184">Una query XPath specificata per tale schema genererà un errore, in quanto `sql:max-depth` non è supportato per un elemento definito in un tipo restriction di base.</span><span class="sxs-lookup"><span data-stu-id="7990d-184">An XPath query specified on such a schema will generate an error, because `sql:max-depth` is not supported on an element that is defined in a restriction base type.</span></span>  
  
## <a name="schemas-with-a-deep-hierarchy"></a><span data-ttu-id="7990d-185">Schemi con una gerarchia profonda</span><span class="sxs-lookup"><span data-stu-id="7990d-185">Schemas with a Deep Hierarchy</span></span>  
 <span data-ttu-id="7990d-186">Si potrebbe avere uno schema che include una gerarchia profonda nella quale un elemento contiene un elemento figlio che, a sua volta, contiene un altro elemento figlio e così via.</span><span class="sxs-lookup"><span data-stu-id="7990d-186">You might have a schema that includes a deep hierarchy in which an element contains a child element, which in turn contains another child element, and so on.</span></span> <span data-ttu-id="7990d-187">Se l'annotazione `sql:max-depth` specificata in uno schema di questo tipo genera un documento XML che include una gerarchia di più di 500 livelli (con l'elemento di livello superiore al livello 1, il rispettivo figlio al livello 2 e così via), viene restituito un errore.</span><span class="sxs-lookup"><span data-stu-id="7990d-187">If the `sql:max-depth` annotation specified in such a schema generates an XML document that includes a hierarchy of more than 500 levels (with top-level element at level 1, its child at level 2, and so on), an error is returned.</span></span>  
  
  
