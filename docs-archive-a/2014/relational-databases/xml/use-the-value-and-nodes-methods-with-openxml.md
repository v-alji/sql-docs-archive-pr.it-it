---
title: Usare i metodi value() e nodes() con OPENXML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- OpenXML method [XML in SQL Server]
- value method [XML in SQL Server]
- nodes method [XML in SQL Server]
ms.assetid: c73dbe55-d685-42eb-b0ee-9f3c5b9d97f3
author: rothja
ms.author: jroth
ms.openlocfilehash: 5dccf5a7ef626d1f1a42d011d22ba77807b34eba
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722583"
---
# <a name="use-the-value-and-nodes-methods-with-openxml"></a><span data-ttu-id="89f2c-102">Utilizzare i metodi value() e nodes() con OPENXML</span><span class="sxs-lookup"><span data-stu-id="89f2c-102">Use the value() and nodes() Methods with OPENXML</span></span>
  <span data-ttu-id="89f2c-103">È possibile usare più metodi **value ()** per il `xml` tipo di dati in una clausola **Select** per generare un set di righe di valori estratti.</span><span class="sxs-lookup"><span data-stu-id="89f2c-103">You can use multiple **value()** methods on `xml` data type in a **SELECT** clause to generate a rowset of extracted values.</span></span> <span data-ttu-id="89f2c-104">Il metodo **nodes()** crea un riferimento interno per ogni nodo selezionato, che può essere usato per altre query.</span><span class="sxs-lookup"><span data-stu-id="89f2c-104">The **nodes()** method yields an internal reference for each selected node that can be used for additional query.</span></span> <span data-ttu-id="89f2c-105">Se sono presenti numerose colonne e quando per la creazione del set di righe vengono usate espressioni di percorso complesse, si può usare una combinazione dei metodi **nodes()** e **value()** per generare il set di righe in modo più efficiente.</span><span class="sxs-lookup"><span data-stu-id="89f2c-105">The combination of the **nodes()** and **value()** methods can be more efficient in generating the rowset when it has several columns and, perhaps, when the path expressions used in its generation are complex.</span></span>  
  
 <span data-ttu-id="89f2c-106">Il metodo **Nodes ()** restituisce istanze di un `xml` tipo di dati speciale, ciascuno dei quali ha un contesto impostato su un nodo selezionato diverso.</span><span class="sxs-lookup"><span data-stu-id="89f2c-106">The **nodes()** method yields instances of a special `xml` data type, each of which has its context set to a different selected node.</span></span> <span data-ttu-id="89f2c-107">Questo tipo di istanza XML supporta i metodi **query()** , **value()** , **nodes()** e **exist()** e può essere usato nelle aggregazioni **count(\*)** .</span><span class="sxs-lookup"><span data-stu-id="89f2c-107">This kind of XML instance supports **query()**, **value()**, **nodes()**, and **exist()** methods and can be used in **count(\*)** aggregations.</span></span> <span data-ttu-id="89f2c-108">Tutti gli altri utilizzi generano un errore.</span><span class="sxs-lookup"><span data-stu-id="89f2c-108">All other uses cause an error.</span></span>  
  
## <a name="example-using-nodes"></a><span data-ttu-id="89f2c-109">Esempio: Utilizzo del metodo nodes()</span><span class="sxs-lookup"><span data-stu-id="89f2c-109">Example: Using nodes()</span></span>  
 <span data-ttu-id="89f2c-110">Si supponga di voler estrarre il nome e il cognome degli autori il cui nome è diverso da "David".</span><span class="sxs-lookup"><span data-stu-id="89f2c-110">Assume that you want to extract the first and last names of authors, and the first name is not "David".</span></span> <span data-ttu-id="89f2c-111">Si supponga inoltre di voler estrarre tali informazioni sotto forma di un set di righe contenente due colonne, FirstName e LastName.</span><span class="sxs-lookup"><span data-stu-id="89f2c-111">Additionally, you want to extract this information as a rowset that contains two columns, FirstName and LastName.</span></span> <span data-ttu-id="89f2c-112">A questo scopo si possono usare i metodi **nodes()** e **value()** , come mostrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="89f2c-112">By using **nodes()** and **value()** methods, you can accomplish this as shown in the following:</span></span>  
  
```  
SELECT nref.value('(first-name/text())[1]', 'nvarchar(50)') FirstName,  
       nref.value('(last-name/text())[1]', 'nvarchar(50)') LastName  
FROM   T CROSS APPLY xCol.nodes('//author') AS R(nref)  
WHERE  nref.exist('first-name[. != "David"]') = 1  
```  
  
 <span data-ttu-id="89f2c-113">In questo esempio `nodes('//author')` crea un set di righe di riferimenti agli elementi `<author>` per ogni istanza XML.</span><span class="sxs-lookup"><span data-stu-id="89f2c-113">In this example, `nodes('//author')` yields a rowset of references to `<author>` elements for each XML instance.</span></span> <span data-ttu-id="89f2c-114">I nomi e cognomi degli autori vengono ottenuti valutando i metodi **value()** in relazione a quei riferimenti.</span><span class="sxs-lookup"><span data-stu-id="89f2c-114">The first and last names of authors are obtained by evaluating **value()** methods relative to those references.</span></span>  
  
 <span data-ttu-id="89f2c-115">SQL Server 2000 consente di generare un set di righe da un'istanza XML usando **OpenXml()** .</span><span class="sxs-lookup"><span data-stu-id="89f2c-115">SQL Server 2000 provides the capability for generating a rowset from an XML instance by using **OpenXml()**.</span></span> <span data-ttu-id="89f2c-116">È possibile specificare lo schema relazionale del set di righe e il mapping tra i valori presenti nell'istanza XML e le colonne nel set di righe.</span><span class="sxs-lookup"><span data-stu-id="89f2c-116">You can specify the relational schema for the rowset and how values inside the XML instance map to columns in the rowset.</span></span>  
  
## <a name="example-using-openxml-on-the-xml-data-type"></a><span data-ttu-id="89f2c-117">Esempio: Utilizzo di OpenXml() sul tipo di dati XML</span><span class="sxs-lookup"><span data-stu-id="89f2c-117">Example: Using OpenXml() on the xml Data Type</span></span>  
 <span data-ttu-id="89f2c-118">È possibile riscrivere la query dell'esempio precedente usando **OpenXml()** come mostrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="89f2c-118">The query can be rewritten from the previous example by using **OpenXml()** as shown in the following.</span></span> <span data-ttu-id="89f2c-119">A tale scopo viene creato un cursore che legge ogni istanza XML in una variabile XML e quindi applica OpenXML alla variabile:</span><span class="sxs-lookup"><span data-stu-id="89f2c-119">This is done by creating a cursor that reads each XML instance into an XML variable and then applies OpenXML to it:</span></span>  
  
```  
DECLARE name_cursor CURSOR  
FOR  
   SELECT xCol   
   FROM   T  
OPEN name_cursor  
DECLARE @xmlVal XML  
DECLARE @idoc int  
FETCH NEXT FROM name_cursor INTO @xmlVal  
  
WHILE (@@FETCH_STATUS = 0)  
BEGIN  
   EXEC sp_xml_preparedocument @idoc OUTPUT, @xmlVal  
   SELECT   *  
   FROM   OPENXML (@idoc, '//author')  
          WITH (FirstName  varchar(50) 'first-name',  
                LastName   varchar(50) 'last-name') R  
   WHERE  R.FirstName != 'David'  
  
   EXEC sp_xml_removedocument @idoc  
   FETCH NEXT FROM name_cursor INTO @xmlVal  
END  
CLOSE name_cursor  
DEALLOCATE name_cursor   
```  
  
 <span data-ttu-id="89f2c-120">**OpenXml()** crea una rappresentazione in memoria e usa tabelle di lavoro anziché Query Processor.</span><span class="sxs-lookup"><span data-stu-id="89f2c-120">**OpenXml()** creates an in-memory representation and uses work tables instead of the query processor.</span></span> <span data-ttu-id="89f2c-121">Si basa inoltre sul processore XPath versione 1.0 di MSXML versione 3.0, piuttosto che sul motore XQuery.</span><span class="sxs-lookup"><span data-stu-id="89f2c-121">It relies on the XPath version 1.0 processor of MSXML version 3.0 instead of the XQuery engine.</span></span> <span data-ttu-id="89f2c-122">Le tabelle di lavoro non vengono condivise tra più chiamate a **OpenXml()** nemmeno sulla stessa istanza XML.</span><span class="sxs-lookup"><span data-stu-id="89f2c-122">The work tables are not shared among multiple calls to **OpenXml()**, even on the same XML instance.</span></span> <span data-ttu-id="89f2c-123">Questo limita la scalabilità del metodo.</span><span class="sxs-lookup"><span data-stu-id="89f2c-123">This limits its scalability.</span></span> <span data-ttu-id="89f2c-124">**OpenXml** consente di accedere a un formato di tabella edge per i dati XML quando non è specificata la clausola WITH</span><span class="sxs-lookup"><span data-stu-id="89f2c-124">**OpenXml()** allows you to access an edge table format for the XML data when the WITH clause is not specified.</span></span> <span data-ttu-id="89f2c-125">e di utilizzare il valore XML rimanente in una colonna di "overflow" separata.</span><span class="sxs-lookup"><span data-stu-id="89f2c-125">Also, it allows you to use the remaining XML value in a separate, "overflow" column.</span></span>  
  
 <span data-ttu-id="89f2c-126">La combinazione di funzioni **nodes()** e **value()** consente di usare gli indici XML in modo efficiente.</span><span class="sxs-lookup"><span data-stu-id="89f2c-126">The combination of **nodes()** and **value()** functions uses XML indexes effectively.</span></span> <span data-ttu-id="89f2c-127">e, di conseguenza, offre maggiore scalabilità rispetto a **OpenXml**.</span><span class="sxs-lookup"><span data-stu-id="89f2c-127">As a result, this combination can exhibit more scalability than **OpenXml**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89f2c-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="89f2c-128">See Also</span></span>  
 [<span data-ttu-id="89f2c-129">OPENXML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="89f2c-129">OPENXML &#40;SQL Server&#41;</span></span>](openxml-sql-server.md)  
  
  
