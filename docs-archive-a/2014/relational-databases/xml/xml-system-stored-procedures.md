---
title: Stored procedure XML di sistema | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- system stored procedures [SQL Server], XML
- sp_xml_removedocument
- OPENXML statement, system stored procedures
- sp_xml_preparedocument
- XML [SQL Server], system stored procedures
ms.assetid: e60c7f85-6823-4d28-93d6-b053d08cc830
author: rothja
ms.author: jroth
ms.openlocfilehash: 2008294fe5bc532dfb6883656420b4189e4da7b0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630377"
---
# <a name="xml-system-stored-procedures"></a><span data-ttu-id="48826-102">Stored procedure XML di sistema</span><span class="sxs-lookup"><span data-stu-id="48826-102">XML System Stored Procedures</span></span>
  <span data-ttu-id="48826-103">In SQL Server sono disponibili le stored procedure di sistema seguenti, utilizzate insieme all'istruzione OPENXML:</span><span class="sxs-lookup"><span data-stu-id="48826-103">SQL Server provides the following system stored procedures that are used together with OPENXML:</span></span>  
  
-   [<span data-ttu-id="48826-104">sp_xml_preparedocument &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="48826-104">sp_xml_preparedocument &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-xml-preparedocument-transact-sql)  
  
-   [<span data-ttu-id="48826-105">sp_xml_removedocument &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="48826-105">sp_xml_removedocument &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-xml-removedocument-transact-sql)  
  
 <span data-ttu-id="48826-106">Per scrivere le query tramite l'istruzione OPENXML, è prima necessario creare una rappresentazione interna del documento XML chiamando la stored procedure **sp_xml_preparedocument**.</span><span class="sxs-lookup"><span data-stu-id="48826-106">To write queries by using OPENXML, you must first create an internal representation of the XML document by calling **sp_xml_preparedocument**.</span></span> <span data-ttu-id="48826-107">La stored procedure restituisce un handle per la rappresentazione interna del documento XML.</span><span class="sxs-lookup"><span data-stu-id="48826-107">The stored procedure returns a handle to the internal representation of the XML document.</span></span> <span data-ttu-id="48826-108">Tale handle viene quindi passato a OPENXML,</span><span class="sxs-lookup"><span data-stu-id="48826-108">This handle is then passed to OPENXML.</span></span> <span data-ttu-id="48826-109">che restituisce viste di set di righe del documento basate su query XPath.</span><span class="sxs-lookup"><span data-stu-id="48826-109">OPENXML provides rowset views of the document based on XPaths.</span></span> <span data-ttu-id="48826-110">In particolare, vengono restituiti un modello di riga e uno o più modelli di colonna.</span><span class="sxs-lookup"><span data-stu-id="48826-110">Specifically, this is one row pattern and one or more column patterns.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="48826-111">L'handle del documento restituito dalla stored procedure **sp_xml_preparedocument** è valido per l'intera durata della sessione.</span><span class="sxs-lookup"><span data-stu-id="48826-111">The document handle that is returned by **sp_xml_preparedocument** is valid for the duration of the session.</span></span>  
  
 <span data-ttu-id="48826-112">È possibile rimuovere la rappresentazione interna del documento XML dalla memoria chiamando la stored procedure di sistema **sp_xml_removedocument** .</span><span class="sxs-lookup"><span data-stu-id="48826-112">The internal representation of an XML document can be removed from memory by calling the **sp_xml_removedocument** system stored procedure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48826-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="48826-113">See Also</span></span>  
 <span data-ttu-id="48826-114">[OPENXML &#40;Transact-SQL&#41;](/sql/t-sql/functions/openxml-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="48826-114">[OPENXML &#40;Transact-SQL&#41;](/sql/t-sql/functions/openxml-transact-sql) </span></span>  
 [<span data-ttu-id="48826-115">OPENXML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="48826-115">OPENXML &#40;SQL Server&#41;</span></span>](../xml/openxml-sql-server.md)  
  
  
