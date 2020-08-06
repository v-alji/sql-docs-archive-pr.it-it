---
title: Supporto dello spazio dei nomi in modalità di PATH | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- PATH FOR XML mode, namespace support
- namespaces [XML in SQL Server]
ms.assetid: 5f128ea2-0ceb-4b23-bce7-c8b3fd615466
author: rothja
ms.author: jroth
ms.openlocfilehash: abd6cd1f5590bffcd841b07897c9685faed4726f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712832"
---
# <a name="namespace-support-in-path-mode"></a><span data-ttu-id="d71dc-102">Supporto dello spazio dei nomi in modalità di PATH</span><span class="sxs-lookup"><span data-stu-id="d71dc-102">Namespace Support in PATH Mode</span></span>
  <span data-ttu-id="d71dc-103">In questa versione, il supporto dello spazio dei nomi in modalità PATH è disponibile utilizzando WITH NAMESPACES.</span><span class="sxs-lookup"><span data-stu-id="d71dc-103">Namespace support in the PATH mode is provided by using WITH NAMESPACES.</span></span> <span data-ttu-id="d71dc-104">Ad esempio, nella query seguente viene illustrata la sintassi WITH NAMESPACES per la dichiarazione di uno spazio dei nomi ("a:") che è possibile utilizzare nell'istruzione SELECT successiva:</span><span class="sxs-lookup"><span data-stu-id="d71dc-104">For example, the following query demonstrates the WITH NAMESPACES syntax to declare a namespace ("a:") that can then be used in the subsequent SELECT statement:</span></span>  
  
```  
WITH XMLNAMESPACES('a' as a)  
SELECT 1 as 'a:b'  
FOR XML PATH  
```  
  
## <a name="examples"></a><span data-ttu-id="d71dc-105">Esempi</span><span class="sxs-lookup"><span data-stu-id="d71dc-105">Examples</span></span>  
 <span data-ttu-id="d71dc-106">In questi esempi viene illustrato l'utilizzo della modalità PATH nella generazione di codice XML da una query SELECT.</span><span class="sxs-lookup"><span data-stu-id="d71dc-106">These samples illustrate the use of PATH mode in generating XML from a SELECT query.</span></span> <span data-ttu-id="d71dc-107">Molte di queste query vengono specificate sui documenti XML di istruzioni per la produzione di biciclette archiviate nella colonna Instructions della tabella ProductModel.</span><span class="sxs-lookup"><span data-stu-id="d71dc-107">Many of these queries are specified against the bicycle manufacturing instructions XML documents that are stored in the Instructions column of the ProductModel table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d71dc-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d71dc-108">See Also</span></span>  
 [<span data-ttu-id="d71dc-109">Utilizzare la modalità PATH con FOR XML</span><span class="sxs-lookup"><span data-stu-id="d71dc-109">Use PATH Mode with FOR XML</span></span>](use-path-mode-with-for-xml.md)  
  
  
