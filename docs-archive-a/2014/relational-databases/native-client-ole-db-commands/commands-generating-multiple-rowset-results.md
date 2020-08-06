---
title: Comandi che generano risultati con più set di righe | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- multiple rowsets
- rowsets [OLE DB], multiple
- SQL Server Native Client OLE DB provider, commands
- SQL Server Native Client OLE DB provider, multiple rowsets
- commands [OLE DB]
- multiple-rowset results
ms.assetid: 4567668d-35fd-4162-b61f-f7536862cdcb
author: rothja
ms.author: jroth
ms.openlocfilehash: 8b42a89c0b043e4c72e8b5634cf70e16b435167a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711912"
---
# <a name="commands-generating-multiple-rowset-results"></a><span data-ttu-id="585c1-102">Comandi che generano risultati con più set di righe</span><span class="sxs-lookup"><span data-stu-id="585c1-102">Commands Generating Multiple-Rowset Results</span></span>
  <span data-ttu-id="585c1-103">Il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native client può restituire più set di righe dalle [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] istruzioni.</span><span class="sxs-lookup"><span data-stu-id="585c1-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider can return multiple rowsets from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] statements.</span></span> <span data-ttu-id="585c1-104">Tramite le istruzioni di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] vengono restituiti più set di righe nelle condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="585c1-104">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] statements return multiple-rowset results under the following conditions:</span></span>  
  
-   <span data-ttu-id="585c1-105">Le istruzioni SQL in batch vengono inviate come singolo comando.</span><span class="sxs-lookup"><span data-stu-id="585c1-105">Batched SQL statements are submitted as a single command.</span></span>  
  
-   <span data-ttu-id="585c1-106">Le stored procedure consentono di implementare un batch di istruzioni SQL.</span><span class="sxs-lookup"><span data-stu-id="585c1-106">Stored procedures implement a batch of SQL statements.</span></span>  
  
## <a name="batches"></a><span data-ttu-id="585c1-107">Batch</span><span class="sxs-lookup"><span data-stu-id="585c1-107">Batches</span></span>  
 <span data-ttu-id="585c1-108">Il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native Client riconosce il carattere punto e virgola come delimitatore di batch per le istruzioni SQL:</span><span class="sxs-lookup"><span data-stu-id="585c1-108">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider recognizes the semicolon character as a batch delimiter for SQL statements:</span></span>  
  
```  
WCHAR*       wSQLString = L"SELECT * FROM Categories; "  
                          L"SELECT * FROM Products";  
```  
  
 <span data-ttu-id="585c1-109">L'invio di più istruzioni SQL in un batch è più efficiente dell'esecuzione separata delle singole istruzioni SQL.</span><span class="sxs-lookup"><span data-stu-id="585c1-109">Sending multiple SQL statements in one batch is more efficient than executing each SQL statement separately.</span></span> <span data-ttu-id="585c1-110">Questo tipo di invio riduce infatti i round trip in rete dal client al server.</span><span class="sxs-lookup"><span data-stu-id="585c1-110">Sending one batch reduces the network round trips from the client to the server.</span></span>  
  
## <a name="stored-procedures"></a><span data-ttu-id="585c1-111">Stored procedure</span><span class="sxs-lookup"><span data-stu-id="585c1-111">Stored Procedures</span></span>  
 <span data-ttu-id="585c1-112">Tramite [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] viene restituito un set di risultati per ogni istruzione di una stored procedure. Pertanto, dalla maggior parte delle stored procedure di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] vengono restituiti più set di risultati.</span><span class="sxs-lookup"><span data-stu-id="585c1-112">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] returns a result set for each statement in a stored procedure, so most [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] stored procedures return multiple result sets.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="585c1-113">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="585c1-113">In This Section</span></span>  
  
-   [<span data-ttu-id="585c1-114">Utilizzo dell'interfaccia IMultipleResults per elaborare più set di risultati</span><span class="sxs-lookup"><span data-stu-id="585c1-114">Using IMultipleResults to Process Multiple Result Sets</span></span>](using-imultipleresults-to-process-multiple-result-sets.md)  
  
## <a name="see-also"></a><span data-ttu-id="585c1-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="585c1-115">See Also</span></span>  
 [<span data-ttu-id="585c1-116">Comandi</span><span class="sxs-lookup"><span data-stu-id="585c1-116">Commands</span></span>](commands.md)  
  
  
