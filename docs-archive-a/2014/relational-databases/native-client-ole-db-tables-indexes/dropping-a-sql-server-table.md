---
title: Eliminazione di una tabella di SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- tables [OLE DB]
- deleting tables
- SQL Server Native Client OLE DB provider, tables
- removing tables
- dropping tables
ms.assetid: b6d6c4de-43c6-473e-92aa-34ffddd58cbe
author: rothja
ms.author: jroth
ms.openlocfilehash: 4d7bea98a3afcd0022f66117b6bde2d968a866b7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629789"
---
# <a name="dropping-a-sql-server-table"></a><span data-ttu-id="f3dbf-102">Eliminazione di una tabella di SQL Server</span><span class="sxs-lookup"><span data-stu-id="f3dbf-102">Dropping a SQL Server Table</span></span>
  <span data-ttu-id="f3dbf-103">Il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native Client espone la funzione **ITableDefinition::D roptable** .</span><span class="sxs-lookup"><span data-stu-id="f3dbf-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider exposes the **ITableDefinition::DropTable** function.</span></span> <span data-ttu-id="f3dbf-104">Questo consente ai consumer di rimuovere una [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tabella da un database.</span><span class="sxs-lookup"><span data-stu-id="f3dbf-104">This allows consumers to remove a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table from a database.</span></span>  
  
 <span data-ttu-id="f3dbf-105">I consumer specificano il nome della tabella come stringa di caratteri Unicode nel membro *pwszName* dell'unione *uName* nel parametro *pTableID*.</span><span class="sxs-lookup"><span data-stu-id="f3dbf-105">Consumers specify the table name as a Unicode character string in the *pwszName* member of the *uName* union in the *pTableID* parameter.</span></span> <span data-ttu-id="f3dbf-106">Il membro *eKind* di*pTableID* deve essere DBKIND_NAME.</span><span class="sxs-lookup"><span data-stu-id="f3dbf-106">The *eKind* member of *pTableID* must be DBKIND_NAME.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3dbf-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f3dbf-107">See Also</span></span>  
 [<span data-ttu-id="f3dbf-108">Tabelle e indici</span><span class="sxs-lookup"><span data-stu-id="f3dbf-108">Tables and Indexes</span></span>](tables-and-indexes.md)  
  
  
