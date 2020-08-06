---
title: Recuperare ed eseguire query su dati XML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- XML data [SQL Server], retrieving
- XML instance retrieval
ms.assetid: 24a28760-1225-42b3-9c89-c9c0332d9c51
author: rothja
ms.author: jroth
ms.openlocfilehash: d387d1b96a57dcc7100368779f8ec6078fad5c7e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713911"
---
# <a name="retrieve-and-query-xml-data"></a><span data-ttu-id="4fa16-102">Recuperare ed eseguire query su dati XML</span><span class="sxs-lookup"><span data-stu-id="4fa16-102">Retrieve and Query XML Data</span></span>
  <span data-ttu-id="4fa16-103">In questo argomento vengono descritte le opzioni query che è necessario specificare per eseguire query sui dati XML.</span><span class="sxs-lookup"><span data-stu-id="4fa16-103">This topic describes the query options that you have to specify to query XML data.</span></span> <span data-ttu-id="4fa16-104">Vengono inoltre descritte le parti di istanze XML che non vengono mantenute quando vengono archiviate nei database.</span><span class="sxs-lookup"><span data-stu-id="4fa16-104">It also describes the parts of XML instances that are not preserved when they are stored in databases.</span></span>  
  
##  <a name="features-of-an-xml-instance-that-are-not-preserved"></a><a name="features"></a> <span data-ttu-id="4fa16-105">Caratteristiche di un'istanza XML non mantenute</span><span class="sxs-lookup"><span data-stu-id="4fa16-105">Features of an XML Instance That Are Not Preserved</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="4fa16-106">mantiene il contenuto dell'istanza XML, ma non mantiene gli aspetti dell'istanza XML che non sono considerati significativi nel modello di dati XML.</span><span class="sxs-lookup"><span data-stu-id="4fa16-106">preserves the content of the XML instance, but does not preserve aspects of the XML instance that are not considered to be significant in the XML data model.</span></span> <span data-ttu-id="4fa16-107">Ciò significa che un'istanza XML recuperata potrebbe non essere identica all'istanza archiviata nel server, ma conterrà le stesse informazioni.</span><span class="sxs-lookup"><span data-stu-id="4fa16-107">This means that a retrieved XML instance might not be identical to the instance that was stored in the server, but will contain the same information.</span></span>  
  
### <a name="xml-declaration"></a><span data-ttu-id="4fa16-108">Dichiarazione XML</span><span class="sxs-lookup"><span data-stu-id="4fa16-108">XML Declaration</span></span>  
 <span data-ttu-id="4fa16-109">La dichiarazione XML in un'istanza non viene mantenuta quando l'istanza viene archiviata nel database.</span><span class="sxs-lookup"><span data-stu-id="4fa16-109">The XML declaration in an instance is not preserved when the instance is stored in the database.</span></span> <span data-ttu-id="4fa16-110">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="4fa16-110">For example:</span></span>  
  
```  
CREATE TABLE T1 (Col1 int primary key, Col2 xml)  
GO  
INSERT INTO T1 values (1, '<?xml version="1.0" encoding="windows-1252" ?><doc></doc>')  
GO  
SELECT Col2  
FROM T1  
```  
  
 <span data-ttu-id="4fa16-111">Il risultato è `<doc/>`.</span><span class="sxs-lookup"><span data-stu-id="4fa16-111">The result is `<doc/>`.</span></span>  
  
 <span data-ttu-id="4fa16-112">La dichiarazione XML, ad esempio `<?xml version='1.0'?>`, non è mantenuta quando si archiviano i dati XML in un'istanza del tipo di dati `xml`.</span><span class="sxs-lookup"><span data-stu-id="4fa16-112">The XML declaration, such as `<?xml version='1.0'?>`, is not preserved when storing XML data in an `xml` data type instance.</span></span> <span data-ttu-id="4fa16-113">Questo si verifica per motivi strutturali.</span><span class="sxs-lookup"><span data-stu-id="4fa16-113">This is by design.</span></span> <span data-ttu-id="4fa16-114">La dichiarazione XML () e i relativi attributi (version/encoding/stand-alone) vengono persi dopo la conversione dei dati nel tipo `xml` .</span><span class="sxs-lookup"><span data-stu-id="4fa16-114">The XML declaration () and its attributes (version/encoding/stand-alone) are lost after data is converted to type `xml`.</span></span> <span data-ttu-id="4fa16-115">La dichiarazione XML viene considerata come una direttiva per il parser XML.</span><span class="sxs-lookup"><span data-stu-id="4fa16-115">The XML declaration is treated as a directive to the XML parser.</span></span> <span data-ttu-id="4fa16-116">I dati XML vengono archiviati internamente come ucs-2.</span><span class="sxs-lookup"><span data-stu-id="4fa16-116">The XML data is stored internally as ucs-2.</span></span> <span data-ttu-id="4fa16-117">Tutte le altre PI nell'istanza XML vengono mantenute.</span><span class="sxs-lookup"><span data-stu-id="4fa16-117">All other PIs in the XML instance are preserved.</span></span>  
  
  
### <a name="order-of-attributes"></a><span data-ttu-id="4fa16-118">Ordine degli attributi</span><span class="sxs-lookup"><span data-stu-id="4fa16-118">Order of Attributes</span></span>  
 <span data-ttu-id="4fa16-119">L'ordine degli attributi in un'istanza XML non viene mantenuto.</span><span class="sxs-lookup"><span data-stu-id="4fa16-119">The order of attributes in an XML instance is not preserved.</span></span> <span data-ttu-id="4fa16-120">Quando si esegue una query nell'istanza XML archiviata nella colonna di tipo `xml`, l'ordine degli attributi nel codice XML risultante può essere diverso rispetto all'istanza XML originale.</span><span class="sxs-lookup"><span data-stu-id="4fa16-120">When you query the XML instance stored in the `xml` type column, the order of attributes in the resulting XML may be different from the original XML instance.</span></span>  
  
  
### <a name="quotation-marks-around-attribute-values"></a><span data-ttu-id="4fa16-121">Virgolette che racchiudono i valori attributo</span><span class="sxs-lookup"><span data-stu-id="4fa16-121">Quotation Marks Around Attribute Values</span></span>  
 <span data-ttu-id="4fa16-122">Le virgolette singole e le virgolette doppie che racchiudono i valori di attributi non vengono mantenute.</span><span class="sxs-lookup"><span data-stu-id="4fa16-122">Single quotation marks and double quotations marks around attribute values are not preserved.</span></span> <span data-ttu-id="4fa16-123">I valori degli attributi vengono archiviati nel database come una coppia di nome e valore,</span><span class="sxs-lookup"><span data-stu-id="4fa16-123">The attribute values are stored in the database as a name and value pair.</span></span> <span data-ttu-id="4fa16-124">senza le virgolette.</span><span class="sxs-lookup"><span data-stu-id="4fa16-124">The quotation marks are not stored.</span></span> <span data-ttu-id="4fa16-125">Quando viene eseguita una query XQuery su un'istanza XML, il codice XML risultante viene serializzato con i valori degli attributi racchiusi tra virgolette doppie.</span><span class="sxs-lookup"><span data-stu-id="4fa16-125">When an XQuery is executed against an XML instance, the resulting XML is serialized with double quotation marks around the attribute values.</span></span>  
  
```  
DECLARE @x xml  
-- Use double quotation marks.  
SET @x = '<root a="1" />'  
SELECT @x  
GO  
DECLARE @x xml  
-- Use single quotation marks.  
SET @x = '<root a=''1'' />'  
SELECT @x  
GO  
```  
  
 <span data-ttu-id="4fa16-126">Entrambe le query restituiscono = `<root a="1" />`.</span><span class="sxs-lookup"><span data-stu-id="4fa16-126">Both queries return = `<root a="1" />`.</span></span>  
  
  
### <a name="namespace-prefixes"></a><span data-ttu-id="4fa16-127">Prefissi degli spazi dei nomi</span><span class="sxs-lookup"><span data-stu-id="4fa16-127">Namespace Prefixes</span></span>  
 <span data-ttu-id="4fa16-128">I prefissi degli spazi dei nomi non vengono mantenuti.</span><span class="sxs-lookup"><span data-stu-id="4fa16-128">Namespace prefixes are not preserved.</span></span> <span data-ttu-id="4fa16-129">Quando si specifica XQuery su una colonna di tipo `xml`, il codice XML serializzato risultante può restituire prefissi dello spazio dei nomi diversi.</span><span class="sxs-lookup"><span data-stu-id="4fa16-129">When you specify XQuery against an `xml` type column, the serialized XML result may return different namespace prefixes.</span></span>  
  
```  
DECLARE @x xml  
SET @x = '<ns1:root xmlns:ns1="abc" xmlns:ns2="abc">  
            <ns2:SomeElement/>  
          </ns1:root>'  
SELECT @x  
SELECT @x.query('/*')  
GO  
```  
  
 <span data-ttu-id="4fa16-130">È possibile che il prefisso dello spazio dei nomi nel risultato sia diverso.</span><span class="sxs-lookup"><span data-stu-id="4fa16-130">The namespace prefix in the result may be different.</span></span> <span data-ttu-id="4fa16-131">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="4fa16-131">For example:</span></span>  
  
```  
<p1:root xmlns:p1="abc"><p1:SomeElement/></p1:root>  
```  
  
  
##  <a name="setting-required-query-options"></a><a name="query"></a> <span data-ttu-id="4fa16-132">Impostazione di opzioni query obbligatorie</span><span class="sxs-lookup"><span data-stu-id="4fa16-132">Setting Required Query Options</span></span>  
 <span data-ttu-id="4fa16-133">Quando si eseguono query `xml` su colonne o variabili `xml` di tipo utilizzando metodi con tipo di dati, è necessario impostare le opzioni seguenti come illustrato.</span><span class="sxs-lookup"><span data-stu-id="4fa16-133">When querying `xml` type columns or variables using `xml` data type methods, the following options must be set as shown.</span></span>  
  
|<span data-ttu-id="4fa16-134">Opzioni SET</span><span class="sxs-lookup"><span data-stu-id="4fa16-134">SET Options</span></span>|<span data-ttu-id="4fa16-135">Valori richiesti</span><span class="sxs-lookup"><span data-stu-id="4fa16-135">Required Values</span></span>|  
|-----------------|---------------------|  
|<span data-ttu-id="4fa16-136">ANSI_NULLS</span><span class="sxs-lookup"><span data-stu-id="4fa16-136">ANSI_NULLS</span></span>|<span data-ttu-id="4fa16-137">ON</span><span class="sxs-lookup"><span data-stu-id="4fa16-137">ON</span></span>|  
|<span data-ttu-id="4fa16-138">ANSI_PADDING</span><span class="sxs-lookup"><span data-stu-id="4fa16-138">ANSI_PADDING</span></span>|<span data-ttu-id="4fa16-139">ON</span><span class="sxs-lookup"><span data-stu-id="4fa16-139">ON</span></span>|  
|<span data-ttu-id="4fa16-140">ANSI_WARNINGS</span><span class="sxs-lookup"><span data-stu-id="4fa16-140">ANSI_WARNINGS</span></span>|<span data-ttu-id="4fa16-141">ON</span><span class="sxs-lookup"><span data-stu-id="4fa16-141">ON</span></span>|  
|<span data-ttu-id="4fa16-142">ARITHABORT</span><span class="sxs-lookup"><span data-stu-id="4fa16-142">ARITHABORT</span></span>|<span data-ttu-id="4fa16-143">ON</span><span class="sxs-lookup"><span data-stu-id="4fa16-143">ON</span></span>|  
|<span data-ttu-id="4fa16-144">CONCAT_NULL_YIELDS_NULL</span><span class="sxs-lookup"><span data-stu-id="4fa16-144">CONCAT_NULL_YIELDS_NULL</span></span>|<span data-ttu-id="4fa16-145">ON</span><span class="sxs-lookup"><span data-stu-id="4fa16-145">ON</span></span>|  
|<span data-ttu-id="4fa16-146">NUMERIC_ROUNDABORT</span><span class="sxs-lookup"><span data-stu-id="4fa16-146">NUMERIC_ROUNDABORT</span></span>|<span data-ttu-id="4fa16-147">OFF</span><span class="sxs-lookup"><span data-stu-id="4fa16-147">OFF</span></span>|  
|<span data-ttu-id="4fa16-148">QUOTED_IDENTIFIER</span><span class="sxs-lookup"><span data-stu-id="4fa16-148">QUOTED_IDENTIFIER</span></span>|<span data-ttu-id="4fa16-149">ON</span><span class="sxs-lookup"><span data-stu-id="4fa16-149">ON</span></span>|  
  
 <span data-ttu-id="4fa16-150">Se le opzioni non vengono impostate come indicato, le query e le modifiche sui `xml` metodi con tipo di dati avranno esito negativo.</span><span class="sxs-lookup"><span data-stu-id="4fa16-150">If the options are not set as shown, queries and modifications on `xml` data type methods will fail.</span></span>  
  
  
## <a name="see-also"></a><span data-ttu-id="4fa16-151">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4fa16-151">See Also</span></span>  
 [<span data-ttu-id="4fa16-152">Creare istanze di dati XML</span><span class="sxs-lookup"><span data-stu-id="4fa16-152">Create Instances of XML Data</span></span>](create-instances-of-xml-data.md)  
  
  
