---
title: Generazione di XML da set di righe con FOR XML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- FOR XML clause, generating XML from rowsets
ms.assetid: d061c0f1-3de9-4ad1-bbca-ce45d064b6c8
author: rothja
ms.author: jroth
ms.openlocfilehash: dcf9feb4dab9ad1149ab433c9d9b4999c96c1cdd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726739"
---
# <a name="generate-xml-from-rowsets-with-for-xml"></a><span data-ttu-id="4e853-102">Generazione di XML da set di righe con FOR XML</span><span class="sxs-lookup"><span data-stu-id="4e853-102">Generate XML from Rowsets with FOR XML</span></span>
  <span data-ttu-id="4e853-103">È possibile generare un' `xml` istanza del tipo di dati da un set di righe utilizzando for XML con la nuova direttiva **Type** .</span><span class="sxs-lookup"><span data-stu-id="4e853-103">You can generate an `xml` data type instance from a rowset by using FOR XML with the new **TYPE** directive.</span></span>  
  
 <span data-ttu-id="4e853-104">Il risultato può essere assegnato a una `xml` colonna, a una variabile o a un parametro del tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="4e853-104">The result can be assigned to an `xml` data type column, variable, or parameter.</span></span> <span data-ttu-id="4e853-105">L'istruzione FOR XML può essere inoltre nidificata, consentendo di creare qualsiasi tipo di struttura gerarchica.</span><span class="sxs-lookup"><span data-stu-id="4e853-105">Also, FOR XML can be nested to generate any hierarchical structure.</span></span> <span data-ttu-id="4e853-106">Le istruzioni FOR XML nidificate sono molto più facili da scrivere rispetto a FOR XML EXPLICIT, ma forniscono prestazioni inferiori in caso di gerarchie con numerosi livelli.</span><span class="sxs-lookup"><span data-stu-id="4e853-106">This makes nested FOR XML much more convenient to write than FOR XML EXPLICIT, but it may not perform as well for deep hierarchies.</span></span> <span data-ttu-id="4e853-107">L'istruzione FOR XML introduce inoltre una nuova modalità PATH,</span><span class="sxs-lookup"><span data-stu-id="4e853-107">FOR XML also introduces a new PATH mode.</span></span> <span data-ttu-id="4e853-108">che specifica il percorso dell'albero XML in cui compare un determinato valore di colonna.</span><span class="sxs-lookup"><span data-stu-id="4e853-108">This new mode specifies the path in the XML tree where a column's value appears.</span></span>  
  
 <span data-ttu-id="4e853-109">La nuova direttiva **FOR XML TYPE** consente di definire visualizzazioni XML in sola lettura su dati relazionali con la sintassi SQL.</span><span class="sxs-lookup"><span data-stu-id="4e853-109">The new **FOR XML TYPE** directive can be used to define read-only XML views over relational data with SQL syntax.</span></span> <span data-ttu-id="4e853-110">Su tale vista è possibile eseguire query utilizzando istruzioni SQL e istruzioni XQuery incorporate, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="4e853-110">The view can be queried with SQL statements and embedded XQuery, as shown in the following example.</span></span> <span data-ttu-id="4e853-111">È possibile fare riferimento a tali viste SQL anche nelle stored procedure.</span><span class="sxs-lookup"><span data-stu-id="4e853-111">You can also refer to these SQL views in stored procedures.</span></span>  
  
## <a name="example-sql-view-returning-generated-xml-data-type"></a><span data-ttu-id="4e853-112">Esempio: Visualizzazione SQL che restituisce un tipo di dati xml generato</span><span class="sxs-lookup"><span data-stu-id="4e853-112">Example: SQL View Returning Generated xml Data Type</span></span>  
 <span data-ttu-id="4e853-113">La definizione di vista SQL seguente crea una visualizzazione XML su una colonna relazionale, utilizzando la chiave primaria e gli autori dei libri recuperati da una colonna XML:</span><span class="sxs-lookup"><span data-stu-id="4e853-113">The following SQL view definition creates an XML view over a relational column, pk, and book authors retrieved from an XML column:</span></span>  
  
```  
CREATE VIEW V (xmlVal) AS  
SELECT pk, xCol.query('/book/author')  
FROM   T  
FOR XML AUTO, TYPE  
```  
  
 <span data-ttu-id="4e853-114">La vista V contiene una singola riga con un singolo nome xmlVal e di tipo XML su `.` cui è possibile eseguire query come un' `xml` istanza del tipo di dati normale.</span><span class="sxs-lookup"><span data-stu-id="4e853-114">The V view contains a single row with a single columnxmlVal of XML type`.` It can be queried like a regular `xml` data type instance.</span></span> <span data-ttu-id="4e853-115">La query seguente, ad esempio, restituisce il nome dell'autore, "David":</span><span class="sxs-lookup"><span data-stu-id="4e853-115">For example, the following query returns the author whose first name is "David":</span></span>  
  
```  
SELECT xmlVal.query('//author[first-name = "David"]')  
FROM   V  
```  
  
 <span data-ttu-id="4e853-116">Le definizioni delle viste SQL sono analoghe alle visualizzazioni XML create utilizzando schemi con annotazioni,</span><span class="sxs-lookup"><span data-stu-id="4e853-116">SQL view definitions are somewhat similar to XML views that are created by using annotated schemas.</span></span> <span data-ttu-id="4e853-117">ma esistono alcune differenze importanti.</span><span class="sxs-lookup"><span data-stu-id="4e853-117">However, there are important differences.</span></span> <span data-ttu-id="4e853-118">La definizione della vista SQL è in modalità di sola lettura e deve essere modificata tramite istruzioni XQuery incorporate.</span><span class="sxs-lookup"><span data-stu-id="4e853-118">The SQL view definition is read-only and must be manipulated with embedded XQuery.</span></span> <span data-ttu-id="4e853-119">Le viste XML vengono create utilizzando schemi con annotazioni.</span><span class="sxs-lookup"><span data-stu-id="4e853-119">The XML views are created by using annotated schema.</span></span> <span data-ttu-id="4e853-120">Inoltre, in una vista SQL il risultato XML viene materializzato prima di applicare l'espressione XQuery, mentre le query XPath sulle viste XML restituiscono query SQL sulle tabelle sottostanti.</span><span class="sxs-lookup"><span data-stu-id="4e853-120">Additionally, the SQL view materializes the XML result before applying the XQuery expression, while the XPath queries on XML views evaluate SQL queries on the underlying tables.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e853-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4e853-121">See Also</span></span>  
 [<span data-ttu-id="4e853-122">FOR XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="4e853-122">FOR XML &#40;SQL Server&#41;</span></span>](for-xml-sql-server.md)  
  
  
