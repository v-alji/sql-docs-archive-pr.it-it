---
title: Caricare dati XML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- XML data [SQL Server], loading
- loading XML data
ms.assetid: d1741e8d-f44e-49ec-9f14-10208b5468a7
author: rothja
ms.author: jroth
ms.openlocfilehash: c48d1d6feccb7df9fec9801ee56abcab99884754
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87717544"
---
# <a name="load-xml-data"></a><span data-ttu-id="ec650-102">Caricamento dati XML</span><span class="sxs-lookup"><span data-stu-id="ec650-102">Load XML Data</span></span>
  <span data-ttu-id="ec650-103">È possibile trasferire dati XML in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] in diversi modi.</span><span class="sxs-lookup"><span data-stu-id="ec650-103">You can transfer XML data into [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] in several ways.</span></span> <span data-ttu-id="ec650-104">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="ec650-104">For example:</span></span>  
  
-   <span data-ttu-id="ec650-105">Se i dati si trovano in una colonna di tipo [n]text o image in un database di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , è possibile importare la tabella utilizzando [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ec650-105">If you have your data in an [n]text or image column in a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database, you can import the table by using [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span></span> <span data-ttu-id="ec650-106">Modificare il tipo di colonna in XML utilizzando l'istruzione ALTER TABLE.</span><span class="sxs-lookup"><span data-stu-id="ec650-106">Change the column type to XML by using the ALTER TABLE statement.</span></span>  
  
-   <span data-ttu-id="ec650-107">È possibile eseguire una copia bulk dei dati da un altro database di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usando bcp out e quindi eseguire un inserimento bulk dei dati nel database di una versione successiva usando bcp in.</span><span class="sxs-lookup"><span data-stu-id="ec650-107">You can bulk copy your data from another [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database by using bcp out, and then bulk insert the data into the later version database by using bcp in.</span></span>  
  
-   <span data-ttu-id="ec650-108">Se i dati si trovano in colonne relazionali in un database di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , creare una nuova tabella con una colonna di tipo [n]text e, facoltativamente, una colonna chiave primaria per un identificatore di riga.</span><span class="sxs-lookup"><span data-stu-id="ec650-108">If you have data in relational columns in a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database, create a new table with an [n]text column and, optionally, a primary key column for a row identifier.</span></span> <span data-ttu-id="ec650-109">Utilizzare la programmazione sul lato client per recuperare i dati XML generati nel server con FOR XML e scriverli nella colonna `[n]text`.</span><span class="sxs-lookup"><span data-stu-id="ec650-109">Use client-side programming to retrieve the XML that is generated at the server with FOR XML and write it into the `[n]text` column.</span></span> <span data-ttu-id="ec650-110">Usare quindi le tecniche illustrate in precedenza per trasferire i dati in un database di una versione successiva.</span><span class="sxs-lookup"><span data-stu-id="ec650-110">Then, use the previously mentioned techniques to transfer data to a later version database.</span></span> <span data-ttu-id="ec650-111">È possibile scegliere di scrivere i dati XML direttamente in una colonna XML nel database di una versione successiva.</span><span class="sxs-lookup"><span data-stu-id="ec650-111">You can choose to write the XML into an XML column in the later version database directly.</span></span>  
  
## <a name="bulk-loading-xml-data"></a><span data-ttu-id="ec650-112">Caricamento bulk di dati XML</span><span class="sxs-lookup"><span data-stu-id="ec650-112">Bulk loading XML data</span></span>  
 <span data-ttu-id="ec650-113">È possibile eseguire un caricamento bulk dei dati XML nel server utilizzando le funzionalità per il caricamento bulk disponibili in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], ad esempio bcp.</span><span class="sxs-lookup"><span data-stu-id="ec650-113">You can bulk load XML data into the server by using the bulk loading capabilities of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], such as bcp.</span></span> <span data-ttu-id="ec650-114">OPENROWSET consente di caricare dati in una colonna XML da uno o più file,</span><span class="sxs-lookup"><span data-stu-id="ec650-114">OPENROWSET allows you to load data into an XML column from files.</span></span> <span data-ttu-id="ec650-115">come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="ec650-115">The following example illustrates this point.</span></span>  
  
##### <a name="example-loading-xml-from-files"></a><span data-ttu-id="ec650-116">Esempio: Caricamento di dati XML da un file</span><span class="sxs-lookup"><span data-stu-id="ec650-116">Example: Loading XML from Files</span></span>  
 <span data-ttu-id="ec650-117">In questo esempio viene illustrato l'inserimento di una riga nella tabella T. Il valore della colonna XML viene caricato dal file C:\MyFile\xmlfile.xml come CLOB e alla colonna di tipo integer viene fornito il valore 10.</span><span class="sxs-lookup"><span data-stu-id="ec650-117">This example shows how to insert a row in table T. The value of the XML column is loaded from file C:\MyFile\xmlfile.xml as CLOB, and the integer column is supplied the value 10.</span></span>  
  
```  
INSERT INTO T  
SELECT 10, xCol  
FROM    (SELECT *      
    FROM OPENROWSET (BULK 'C:\MyFile\xmlfile.xml', SINGLE_CLOB)   
 AS xCol) AS R(xCol)  
```  
  
## <a name="text-encoding"></a><span data-ttu-id="ec650-118">Codifica testo</span><span class="sxs-lookup"><span data-stu-id="ec650-118">Text Encoding</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="ec650-119">archivia i dati XML in formato Unicode (UTF-16).</span><span class="sxs-lookup"><span data-stu-id="ec650-119">stores XML data in Unicode (UTF-16).</span></span> <span data-ttu-id="ec650-120">I dati XML recuperati dal server vengono restituiti con la codifica UTF-16.</span><span class="sxs-lookup"><span data-stu-id="ec650-120">XML data retrieved from the server comes out in UTF-16 encoding.</span></span> <span data-ttu-id="ec650-121">Se si desidera una codifica diversa, sarà necessario eseguire la conversione appropriata sui dati recuperati.</span><span class="sxs-lookup"><span data-stu-id="ec650-121">If you want a different encoding, you have to perform the required conversion on the retrieved data.</span></span> <span data-ttu-id="ec650-122">Per i dati XML viene talvolta utilizzata una codifica diversa.</span><span class="sxs-lookup"><span data-stu-id="ec650-122">Sometimes, the XML data may be in a different encoding.</span></span> <span data-ttu-id="ec650-123">In questo caso è necessario prestare particolare attenzione durante il caricamento dei dati.</span><span class="sxs-lookup"><span data-stu-id="ec650-123">If it is, you have to use care during data loading.</span></span> <span data-ttu-id="ec650-124">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="ec650-124">For example:</span></span>  
  
-   <span data-ttu-id="ec650-125">Se il testo XML è in formato Unicode (UCS-2, UTF-16), sarà possibile assegnarlo senza problemi a una colonna, una variabile o un parametro XML.</span><span class="sxs-lookup"><span data-stu-id="ec650-125">If your text XML is in Unicode (UCS-2, UTF-16), you can assign it to an XML column, variable, or parameter  without any problems.</span></span>  
  
-   <span data-ttu-id="ec650-126">Se viene utilizzata una codifica implicita diversa da Unicode, a causa della tabella codici di origine, la tabella codici per le stringhe nel database dovrà essere uguale o compatibile con i punti di codice da caricare.</span><span class="sxs-lookup"><span data-stu-id="ec650-126">If the encoding is not Unicode and is implicit, because of the source code page, the string code page in the database should be the same as or compatible with the code points that you want to load.</span></span> <span data-ttu-id="ec650-127">Se necessario, utilizzare COLLATE.</span><span class="sxs-lookup"><span data-stu-id="ec650-127">If required, use COLLATE.</span></span> <span data-ttu-id="ec650-128">Se tale tabella codici non esiste sul server, sarà necessario aggiungere una dichiarazione XML esplicita con la codifica appropriata.</span><span class="sxs-lookup"><span data-stu-id="ec650-128">If no such server code page exists, you have to add an explicit XML declaration with the correct encoding.</span></span>  
  
-   <span data-ttu-id="ec650-129">Per utilizzare una codifica esplicita utilizzare il tipo di dati `varbinary()`, che non interagisce in alcun modo con le tabelle codici, oppure utilizzare un tipo stringa della tabella codici appropriata.</span><span class="sxs-lookup"><span data-stu-id="ec650-129">To use an explicit encoding, use either the `varbinary()` type, which has no interaction with code pages, or use a string type of the appropriate code page.</span></span> <span data-ttu-id="ec650-130">Assegnare quindi i dati a una colonna, a una variabile o a un parametro XML.</span><span class="sxs-lookup"><span data-stu-id="ec650-130">Then, assign the data to an XML column, variable, or parameter.</span></span>  
  
### <a name="example-explicitly-specifying-an-encoding"></a><span data-ttu-id="ec650-131">Esempio: Impostazione di una codifica in modo esplicito</span><span class="sxs-lookup"><span data-stu-id="ec650-131">Example: Explicitly Specifying an Encoding</span></span>  
 <span data-ttu-id="ec650-132">Si consideri un documento XML di nome vcdoc, archiviato come `varchar(max)` e che non include una dichiarazione XML esplicita.</span><span class="sxs-lookup"><span data-stu-id="ec650-132">Assume that you have an XML document, vcdoc, stored as `varchar(max)` that does not have an explicit XML declaration.</span></span> <span data-ttu-id="ec650-133">L'istruzione seguente aggiunge una dichiarazione XML con la codifica "iso8859-1", concatena il documento XML, esegue il cast del risultato a `varbinary(max)`, in modo da mantenere la rappresentazione dei byte e infine esegue il cast al tipo di dati XML.</span><span class="sxs-lookup"><span data-stu-id="ec650-133">The following statement adds an XML declaration with the encoding "iso8859-1", concatenates the XML document, casts the result to `varbinary(max)` so that the byte representation is preserved, and then finally casts it to XML.</span></span> <span data-ttu-id="ec650-134">Questo consente al processore XML di analizzare i dati in base alla codifica specificata, "iso8859-1", e di generare la rappresentazione UTF-16 corrispondente per i valori stringa.</span><span class="sxs-lookup"><span data-stu-id="ec650-134">This enables the XML processor to parse the data according to the specified encoding "iso8859-1" and generate the corresponding UTF-16 representation for string values.</span></span>  
  
```  
SELECT CAST(   
CAST (('<?xml version="1.0" encoding="iso8859-1"?>'+ vcdoc) AS VARBINARY (MAX))   
 AS XML)  
```  
  
### <a name="string-encoding-incompatibilities"></a><span data-ttu-id="ec650-135">Stringa che codifica le incompatibilità</span><span class="sxs-lookup"><span data-stu-id="ec650-135">String Encoding Incompatibilities</span></span>  
 <span data-ttu-id="ec650-136">Se si copia e si incolla XML come un valore letterale stringa nella finestra dell'editor di query di [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], potrebbero verificarsi incompatibilità di codifica delle stringhe [N]VARCHAR,</span><span class="sxs-lookup"><span data-stu-id="ec650-136">If you copy and paste XML as a string literal into the Query Editor window in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], you might experience [N]VARCHAR string encoding incompatibilities.</span></span> <span data-ttu-id="ec650-137">che dipendono dalla codifica dell'istanza XML utilizzata.</span><span class="sxs-lookup"><span data-stu-id="ec650-137">This will depend on the encoding of your XML instance.</span></span> <span data-ttu-id="ec650-138">In molti casi, è possibile rimuovere la dichiarazione XML.</span><span class="sxs-lookup"><span data-stu-id="ec650-138">In many cases, you may want to remove the XML declaration.</span></span> <span data-ttu-id="ec650-139">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="ec650-139">For example:</span></span>  
  
```  
<?xml version="1.0" encoding="UTF-8"?>  
  <xsd:schema ...  
```  
  
 <span data-ttu-id="ec650-140">È quindi consigliabile inserire una N per rendere l'istanza XML un'istanza di Unicode.</span><span class="sxs-lookup"><span data-stu-id="ec650-140">You should then include an N to make the XML instance an instance of Unicode.</span></span> <span data-ttu-id="ec650-141">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="ec650-141">For example:</span></span>  
  
```  
-- Assign XML instance to a variable.  
DECLARE @X XML  
SET @X = N'...'  
-- Insert XML instance into an xml type column.  
INSERT INTO T VALUES (N'...')  
-- Create an XML schema collection  
CREATE XML SCHEMA COLLECTION XMLCOLL1 AS N'<xsd:schema ... '  
```  
  
## <a name="see-also"></a><span data-ttu-id="ec650-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ec650-142">See Also</span></span>  
 [<span data-ttu-id="ec650-143">Dati XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ec650-143">XML Data &#40;SQL Server&#41;</span></span>](xml-data-sql-server.md)  
  
  
