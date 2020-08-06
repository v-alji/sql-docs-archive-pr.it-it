---
title: Creazione di un set di righe con IOpenRowset | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- IOpenRowset interface
- rowsets [OLE DB], creating
- SQL Server Native Client OLE DB provider, rowsets
- OLE DB rowsets, creating
ms.assetid: e8bc3de7-4b97-4de9-8df8-e11947d24045
author: rothja
ms.author: jroth
ms.openlocfilehash: bf74466a698d39f74b9531adaa54c79c75e50ef2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723771"
---
# <a name="creating-a-rowset-with-iopenrowset"></a><span data-ttu-id="5c255-102">Creazione di un set di righe con IOpenRowset</span><span class="sxs-lookup"><span data-stu-id="5c255-102">Creating a Rowset with IOpenRowset</span></span>
  <span data-ttu-id="5c255-103">Il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native Client supporta il metodo **IOpenRowset:: OPENROWSET** con le restrizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5c255-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider supports the **IOpenRowset::OpenRowset** method with the following restrictions:</span></span>  
  
-   <span data-ttu-id="5c255-104">Una vista o una tabella di base deve essere specificata in una struttura del database (DBID) a cui punta il parametro *pTableID*.</span><span class="sxs-lookup"><span data-stu-id="5c255-104">A base table or view must be specified in a database ID (DBID) structure that the *pTableID* parameter points to.</span></span>  
  
-   <span data-ttu-id="5c255-105">Il membro DBID *eKind* deve indicare DBKIND_NAME.</span><span class="sxs-lookup"><span data-stu-id="5c255-105">The DBID *eKind* member must indicate DBKIND_NAME.</span></span>  
  
-   <span data-ttu-id="5c255-106">Il membro DBID *uName* deve specificare il nome di una vista o di una tabella di base esistente come stringa di caratteri Unicode.</span><span class="sxs-lookup"><span data-stu-id="5c255-106">The DBID *uName* member must specify the name of an existing base table or a view as a Unicode character string.</span></span>  
  
-   <span data-ttu-id="5c255-107">Il parametro *pIndexID* di **OpenRowset** deve essere NULL.</span><span class="sxs-lookup"><span data-stu-id="5c255-107">The *pIndexID* parameter of **OpenRowset** must be NULL.</span></span>  
  
 <span data-ttu-id="5c255-108">Il set di risultati di **IOpenRowset::OpenRowset** contiene un solo set di righe.</span><span class="sxs-lookup"><span data-stu-id="5c255-108">The result set of **IOpenRowset::OpenRowset** contains a single rowset.</span></span> <span data-ttu-id="5c255-109">I set di risultati che contengono un singolo set di righe possono essere supportati dai [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cursori.</span><span class="sxs-lookup"><span data-stu-id="5c255-109">Result sets that contain a single rowset can be supported by [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cursors.</span></span> <span data-ttu-id="5c255-110">Il supporto del cursore consente allo sviluppatore di utilizzare i meccanismi di concorrenza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5c255-110">Cursor support allows the developer to use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] concurrency mechanisms.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c255-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5c255-111">See Also</span></span>  
 [<span data-ttu-id="5c255-112">Set di righe</span><span class="sxs-lookup"><span data-stu-id="5c255-112">Rowsets</span></span>](rowsets.md)  
  
  
