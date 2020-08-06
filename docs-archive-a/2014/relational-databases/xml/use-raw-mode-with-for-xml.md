---
title: Usare la modalità RAW con FOR XML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- FOR XML RAW mode
- XMLSCHEMA option
- FOR XML clause, RAW mode
- RAW FOR XML mode
- ELEMENTS directive
- RAW mode
- XMLDATA option
ms.assetid: 02c1bc0b-760c-4589-9ab1-6927c6d9c734
author: rothja
ms.author: jroth
ms.openlocfilehash: b2908a98336ec8a6e12029ad471f22a33d7a4dcf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722607"
---
# <a name="use-raw-mode-with-for-xml"></a><span data-ttu-id="daa9a-102">Utilizzo della modalità RAW con FOR XML</span><span class="sxs-lookup"><span data-stu-id="daa9a-102">Use RAW Mode with FOR XML</span></span>
  <span data-ttu-id="daa9a-103">Nella modalità RAW ogni riga del set di risultati della query viene trasformata in un elemento XML al quale è assegnato l'identificatore generico \<row> o il nome di elemento specificato facoltativamente.</span><span class="sxs-lookup"><span data-stu-id="daa9a-103">RAW mode transforms each row in the query result set into an XML element that has the generic identifier \<row>, or the optionally provided element name.</span></span> <span data-ttu-id="daa9a-104">Per impostazione predefinita, viene eseguito il mapping di ogni valore di colonna del set di righe diverso da NULL a un attributo dell'elemento \<row>.</span><span class="sxs-lookup"><span data-stu-id="daa9a-104">By default, each column value in the rowset that is not NULL is mapped to an attribute of the \<row> element.</span></span> <span data-ttu-id="daa9a-105">Se alla clausola FOR XML viene aggiunta la direttiva ELEMENTS, viene eseguito il mapping di ogni valore di colonna a un sottoelemento dell'elemento \<row>.</span><span class="sxs-lookup"><span data-stu-id="daa9a-105">If the ELEMENTS directive is added to the FOR XML clause, each column value is mapped to a subelement of the \<row> element.</span></span> <span data-ttu-id="daa9a-106">Insieme alla direttiva ELEMENTS è possibile specificare facoltativamente l'opzione XSINIL per eseguire il mapping dei valori di colonna NULL del set di risultati a un elemento con l'attributo xsi:nil=`"`true`"`.</span><span class="sxs-lookup"><span data-stu-id="daa9a-106">Together with the ELEMENTS directive, you can optionally specify the XSINIL option to map NULL column values in the result set to an element that has the attribute, xsi:nil=`"`true`"`.</span></span>  
  
 <span data-ttu-id="daa9a-107">È possibile richiedere uno schema per il codice XML risultante.</span><span class="sxs-lookup"><span data-stu-id="daa9a-107">You can request a schema for the resulting XML.</span></span> <span data-ttu-id="daa9a-108">Se si specifica l'opzione XMLDATA, verrà restituito uno schema XDR inline.</span><span class="sxs-lookup"><span data-stu-id="daa9a-108">Specifying the XMLDATA option returns an in-line XDR schema.</span></span> <span data-ttu-id="daa9a-109">Se si specifica l'opzione XMLSCHEMA, verrà restituito uno schema XDS inline.</span><span class="sxs-lookup"><span data-stu-id="daa9a-109">Specifying the XMLSCHEMA option returns an in-line XSD schema.</span></span> <span data-ttu-id="daa9a-110">che viene visualizzato all'inizio dei dati.</span><span class="sxs-lookup"><span data-stu-id="daa9a-110">The schema appears at the start of the data.</span></span> <span data-ttu-id="daa9a-111">Nel risultato, il riferimento allo spazio dei nomi dello schema viene ripetuto in ogni elemento di livello principale.</span><span class="sxs-lookup"><span data-stu-id="daa9a-111">In the result, the schema namespace reference is repeated for every top-level element.</span></span>  
  
 <span data-ttu-id="daa9a-112">Per restituire i dati binari nel formato con codifica Base64, è necessario specificare l'opzione BINARY BASE64 nella clausola FOR XML.</span><span class="sxs-lookup"><span data-stu-id="daa9a-112">The BINARY BASE64 option must be specified in the FOR XML clause to return the binary data in base64-encoded format.</span></span> <span data-ttu-id="daa9a-113">Se si recuperano dati binari nella modalità RAW senza specificare l'opzione BINARY BASE64, verrà generato un errore.</span><span class="sxs-lookup"><span data-stu-id="daa9a-113">In RAW mode, retrieving binary data without specifying the BINARY BASE64 option will result in an error.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="daa9a-114">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="daa9a-114">In This Section</span></span>  
 <span data-ttu-id="daa9a-115">Questa sezione contiene gli esempi seguenti:</span><span class="sxs-lookup"><span data-stu-id="daa9a-115">This section contains the following examples:</span></span>  
  
-   [<span data-ttu-id="daa9a-116">Esempio: Recupero delle informazioni relative al modello del prodotto in formato XML</span><span class="sxs-lookup"><span data-stu-id="daa9a-116">Example: Retrieving Product Model Information as XML</span></span>](example-retrieving-product-model-information-as-xml.md)  
  
-   [<span data-ttu-id="daa9a-117">Esempio: Specifica di XSINIL con la direttiva ELEMENTS</span><span class="sxs-lookup"><span data-stu-id="daa9a-117">Example: Specifying XSINIL with the ELEMENTS Directive</span></span>](example-specifying-xsinil-with-the-elements-directive.md)  
  
-   [<span data-ttu-id="daa9a-118">Esempio: richiesta di schemi di risultato mediante le opzioni XMLDATA e XMLSCHEMA</span><span class="sxs-lookup"><span data-stu-id="daa9a-118">Example: Requesting Schemas as Results with the XMLDATA and XMLSCHEMA Options</span></span>](example-requesting-schemas-as-results-with-the-xmldata-and-xmlschema-options.md)  
  
-   [<span data-ttu-id="daa9a-119">Esempio: Recupero di dati binari</span><span class="sxs-lookup"><span data-stu-id="daa9a-119">Example: Retrieving Binary Data</span></span>](example-retrieving-binary-data.md)  
  
-   [<span data-ttu-id="daa9a-120">Esempio: Ridenominazione dell'elemento &#60;row&#62;</span><span class="sxs-lookup"><span data-stu-id="daa9a-120">Example: Renaming the &#60;row&#62; Element</span></span>](example-renaming-the-row-element.md)  
  
-   [<span data-ttu-id="daa9a-121">Esempio: Specifica di un elemento radice per codice XML generato da FOR XML</span><span class="sxs-lookup"><span data-stu-id="daa9a-121">Example: Specifying a Root Element for the XML Generated by FOR XML</span></span>](example-specifying-a-root-element-for-the-xml-generated-by-for-xml.md)  
  
-   [<span data-ttu-id="daa9a-122">Esempio: Esecuzione di query sulle colonne di tipo XML</span><span class="sxs-lookup"><span data-stu-id="daa9a-122">Example: Querying XMLType Columns</span></span>](example-querying-xmltype-columns.md)  
  
## <a name="see-also"></a><span data-ttu-id="daa9a-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="daa9a-123">See Also</span></span>  
 <span data-ttu-id="daa9a-124">[Aggiungere spazi dei nomi alle query con WITH XMLNAMESPACES](add-namespaces-to-queries-with-with-xmlnamespaces.md) </span><span class="sxs-lookup"><span data-stu-id="daa9a-124">[Add Namespaces to Queries with WITH XMLNAMESPACES](add-namespaces-to-queries-with-with-xmlnamespaces.md) </span></span>  
 <span data-ttu-id="daa9a-125">[Utilizzo della modalità AUTO con FOR XML](use-auto-mode-with-for-xml.md) </span><span class="sxs-lookup"><span data-stu-id="daa9a-125">[Use AUTO Mode with FOR XML](use-auto-mode-with-for-xml.md) </span></span>  
 <span data-ttu-id="daa9a-126">[Utilizzo della modalità EXPLICIT con FOR XML](use-explicit-mode-with-for-xml.md) </span><span class="sxs-lookup"><span data-stu-id="daa9a-126">[Use EXPLICIT Mode with FOR XML](use-explicit-mode-with-for-xml.md) </span></span>  
 <span data-ttu-id="daa9a-127">[Utilizzare la modalità PATH con FOR XML](use-path-mode-with-for-xml.md) </span><span class="sxs-lookup"><span data-stu-id="daa9a-127">[Use PATH Mode with FOR XML](use-path-mode-with-for-xml.md) </span></span>  
 <span data-ttu-id="daa9a-128">[SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="daa9a-128">[SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql) </span></span>  
 [<span data-ttu-id="daa9a-129">FOR XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="daa9a-129">FOR XML &#40;SQL Server&#41;</span></span>](../xml/for-xml-sql-server.md)  
  
  
