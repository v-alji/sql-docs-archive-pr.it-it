---
title: Caratteri non validi e regole di escape | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- FOR XML clause, invalid characters
- FOR XML clause, escape rules
ms.assetid: f2e9b997-f400-4963-b225-59d46c6b93e8
author: rothja
ms.author: jroth
ms.openlocfilehash: 8624a31dea4e97e05da6d86c3c0c518b9c4d0aba
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725340"
---
# <a name="invalid-characters-and-escape-rules"></a><span data-ttu-id="7ae5c-102">Caratteri non validi e regole di escape</span><span class="sxs-lookup"><span data-stu-id="7ae5c-102">Invalid Characters and Escape Rules</span></span>
  <span data-ttu-id="7ae5c-103">Questo argomento descrive il modo in cui i caratteri XML non validi vengono gestiti dalla clausola FOR XML ed elenca le regole di escape per i caratteri non validi nei nomi XML.</span><span class="sxs-lookup"><span data-stu-id="7ae5c-103">This topic describes how invalid XML characters are handled by the FOR XML clause, and lists the escape rules for characters that are invalid in XML names.</span></span>  
  
## <a name="for-xml-and-invalid-characters"></a><span data-ttu-id="7ae5c-104">Per i caratteri XML non validi</span><span class="sxs-lookup"><span data-stu-id="7ae5c-104">For XML and Invalid Characters</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="7ae5c-105">sostituisce caratteri XML non validi con entità quando vengono restituiti all'interno di query FOR XML che non usano la direttiva TYPE.</span><span class="sxs-lookup"><span data-stu-id="7ae5c-105">entitizes invalid XML characters when they are returned within FOR XML queries that do not use the TYPE directive.</span></span>  
  
 <span data-ttu-id="7ae5c-106">Nei parser conformi a XML 1.0 vengono generati errori di analisi indipendentemente dal fatto che tali caratteri vengano sostituiti o meno con entità, tuttavia la forma con entità è maggiormente conforme a XML 1.1</span><span class="sxs-lookup"><span data-stu-id="7ae5c-106">Although XML 1.0 conformant parsers raise parse errors regardless of whether these characters are entitized or not, the entitized form is better aligned with XML 1.1.</span></span> <span data-ttu-id="7ae5c-107">ed è potenzialmente conforme alle versioni future dello standard XML.</span><span class="sxs-lookup"><span data-stu-id="7ae5c-107">The entitized form is also potentially better aligned with future versions of the XML standard.</span></span> <span data-ttu-id="7ae5c-108">Semplifica inoltre il debug perché il punto di codice del carattere non valido diventa visibile.</span><span class="sxs-lookup"><span data-stu-id="7ae5c-108">Additionally, it makes debugging simpler, because the code point of the invalid character becomes visible.</span></span>  
  
 <span data-ttu-id="7ae5c-109">Per gli utenti degli strumenti XML non è necessaria alcuna soluzione alternativa, perché il parser XML genererà in ogni caso un errore in corrispondenza dei caratteri non validi nel flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="7ae5c-109">For users of XML tools, no workaround is required, because the XML parser will fail either way at the point where the invalid characters occur in the data stream.</span></span> <span data-ttu-id="7ae5c-110">Se si utilizzano strumenti non XML potrebbe essere necessario aggiornare la logica di programmazione in modo che sia in grado di cercare i caratteri come valori sostituiti con entità.</span><span class="sxs-lookup"><span data-stu-id="7ae5c-110">If you use non-XML tools, this change can require you to update your programming logic to search for these characters as entitized values.</span></span>  
  
 <span data-ttu-id="7ae5c-111">I caratteri spazi vuoti indicati di seguito vengono sostituiti da entità diverse nelle query FOR XML per mantenerne la presenza in sequenze di andata e ritorno:</span><span class="sxs-lookup"><span data-stu-id="7ae5c-111">The following white space characters are entitized differently in FOR XML queries to preserve their presence through round-tripping:</span></span>  
  
-   <span data-ttu-id="7ae5c-112">Nel contenuto e negli attributi di un elemento: **hex(0D)** (ritorno a capo)</span><span class="sxs-lookup"><span data-stu-id="7ae5c-112">In element content and attributes: **hex(0D)** (carriage return)</span></span>  
  
-   <span data-ttu-id="7ae5c-113">Nel contenuto di un attributo: **hex(09)** (tabulazione), **hex(0A)** (avanzamento di riga)</span><span class="sxs-lookup"><span data-stu-id="7ae5c-113">In attribute content: **hex(09)** (tab), **hex(0A)** (line feed)</span></span>  
  
 <span data-ttu-id="7ae5c-114">Questi caratteri vengono mantenuti nell'output e non verranno normalizzati da un parser.</span><span class="sxs-lookup"><span data-stu-id="7ae5c-114">These characters are preserved in output, and a parser will not normalize them.</span></span>  
  
## <a name="escape-rules"></a><span data-ttu-id="7ae5c-115">Regole di escape</span><span class="sxs-lookup"><span data-stu-id="7ae5c-115">Escape Rules</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="7ae5c-116">nomi che includono caratteri non validi per i nomi XML, quali gli spazi, vengono convertiti in nomi XML in modo tale che i caratteri non validi vengano convertiti in codici numerici in sequenza escape.</span><span class="sxs-lookup"><span data-stu-id="7ae5c-116">names that contain characters that are invalid in XML names, such as spaces, are translated into XML names in a way in which the invalid characters are translated into escaped numeric entity encoding.</span></span>  
  
 <span data-ttu-id="7ae5c-117">In un nome XML possono essere presenti solo due caratteri non alfabetici, ovvero i due punti (:) e il carattere di sottolineatura (_).</span><span class="sxs-lookup"><span data-stu-id="7ae5c-117">There are only two non-alphabetic characters that can occur within an XML name: the colon (:) and the underscore (_).</span></span> <span data-ttu-id="7ae5c-118">Poiché il carattere di due punti è già riservato per gli spazi dei nomi, come carattere di escape viene utilizzato il carattere di sottolineatura.</span><span class="sxs-lookup"><span data-stu-id="7ae5c-118">Because the colon is already reserved for namespaces, the underscore is chosen as the escape character.</span></span> <span data-ttu-id="7ae5c-119">Di seguito vengono illustrate le regole di escape utilizzate per la codifica:</span><span class="sxs-lookup"><span data-stu-id="7ae5c-119">Following are the escape rules that are used for encoding:</span></span>  
  
-   <span data-ttu-id="7ae5c-120">Per i caratteri UCS-2 non validi per i nomi XML, in base alla specifica XML 1.0, vengono usati i caratteri di escape _xHHHH\_.</span><span class="sxs-lookup"><span data-stu-id="7ae5c-120">Any UCS-2 character that is not a valid XML name character, according to the XML 1.0 specification, is escaped as _xHHHH\_.</span></span> <span data-ttu-id="7ae5c-121">dove HHHH rappresenta il codice UCS-2 esadecimale a quattro cifre per il carattere in base all'ordine del primo bit più significativo.</span><span class="sxs-lookup"><span data-stu-id="7ae5c-121">The HHHH stands for the four-digit hexadecimal UCS-2 code for the character in the most significant bit-first order.</span></span> <span data-ttu-id="7ae5c-122">Ad esempio, il nome della tabella **Order Details** viene convertito in Order_x0020_Details.</span><span class="sxs-lookup"><span data-stu-id="7ae5c-122">For example, the table name **Order Details** is encoded as Order_x0020_Details.</span></span>  
  
-   <span data-ttu-id="7ae5c-123">I caratteri che non rientrano nelle specifiche UCS-2 (le aggiunte UCS-4 dell'intervallo da U+00010000 a U+0010FFFF) vengono convertiti in _xHHHHHHHH_,\_.</span><span class="sxs-lookup"><span data-stu-id="7ae5c-123">Characters that do not fit into the UCS-2 realm (the UCS-4 additions of the range U+00010000 to U+0010FFFF) are encoded as _xHHHHHHHH\_.</span></span> <span data-ttu-id="7ae5c-124">dove HHHHHHHH rappresenta la codifica UCS-4 esadecimale a otto cifre del carattere, se è attiva la compatibilità con le versioni precedenti con SQL Server 2000.</span><span class="sxs-lookup"><span data-stu-id="7ae5c-124">The HHHHHHHH stands for the eight-digit hexadecimal UCS-4 encoding of the character, if under SQL Server 2000 backward compatibility mode.</span></span> <span data-ttu-id="7ae5c-125">In caso contrario, i caratteri vengono convertiti in _xHHHHHH\_per la compatibilità con lo standard ISO.</span><span class="sxs-lookup"><span data-stu-id="7ae5c-125">Otherwise, the characters are encoded as_xHHHHHH\_, in order to align with the ISO standard.</span></span>  
  
-   <span data-ttu-id="7ae5c-126">Per il carattere di sottolineatura è necessario utilizzare caratteri di escape solo se è seguito dal carattere x.</span><span class="sxs-lookup"><span data-stu-id="7ae5c-126">The underscore character does not have to be escaped unless it is followed by the character x.</span></span> <span data-ttu-id="7ae5c-127">Ad esempio, il nome della tabella **Order_Details** non viene codificato.</span><span class="sxs-lookup"><span data-stu-id="7ae5c-127">For example, the table name **Order_Details** is not encoded.</span></span>  
  
-   <span data-ttu-id="7ae5c-128">Per il carattere dei due punti negli identificatori non vengono utilizzati caratteri di escape, in modo tale che l'elemento dello spazio dei nomi e i nomi degli attributi possano essere generati dalla query FOR XML.</span><span class="sxs-lookup"><span data-stu-id="7ae5c-128">The colon in identifiers is not escaped As a result, the namespace element and attribute names can be generated by the FOR XML query.</span></span> <span data-ttu-id="7ae5c-129">Ad esempio, la query seguente genera un attributo dello spazio dei nomi che include i due punti nel nome.</span><span class="sxs-lookup"><span data-stu-id="7ae5c-129">For example, the following query generates a namespace attribute that has a colon in the name:</span></span>  
  
    ```  
    SELECT 'namespace-urn' as 'xmlns:namespace',   
     1 as 'namespace:a'   
    FOR XML RAW  
    ```  
  
     <span data-ttu-id="7ae5c-130">Il risultato della query è il seguente:</span><span class="sxs-lookup"><span data-stu-id="7ae5c-130">The query produces this result:</span></span>  
  
    ```  
    <row xmlns:namespace="namespace-urn" namespace:a="1"/>  
    ```  
  
     <span data-ttu-id="7ae5c-131">Si noti che per aggiungere spazi dei nomi XML è consigliabile utilizzare WITH XMLNAMESPACES.</span><span class="sxs-lookup"><span data-stu-id="7ae5c-131">Note that WITH XMLNAMESPACES is the recommended way to add XML namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ae5c-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7ae5c-132">See Also</span></span>  
 [<span data-ttu-id="7ae5c-133">FOR XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="7ae5c-133">FOR XML &#40;SQL Server&#41;</span></span>](for-xml-sql-server.md)  
  
  
