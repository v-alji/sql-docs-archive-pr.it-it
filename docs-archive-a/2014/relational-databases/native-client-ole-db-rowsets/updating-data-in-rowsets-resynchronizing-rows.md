---
title: Risincronizzazione delle righe | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- synchronization [OLE DB]
- IRowsetResynch interface
- resynchronizing rows
- data updates [SQL Server], OLE DB
ms.assetid: d2d30505-a878-4aa9-b821-53d8118a45a5
author: rothja
ms.author: jroth
ms.openlocfilehash: 47c628ae583f3e635f422d5146f64508372a1114
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626078"
---
# <a name="resynchronizing-rows"></a><span data-ttu-id="1f38b-102">Risincronizzazione delle righe</span><span class="sxs-lookup"><span data-stu-id="1f38b-102">Resynchronizing Rows</span></span>
  <span data-ttu-id="1f38b-103">Il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native Client supporta solo **IRowsetResynch** nei [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] set di righe supportati dal cursore.</span><span class="sxs-lookup"><span data-stu-id="1f38b-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider supports **IRowsetResynch** on [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cursor-supported rowsets only.</span></span> <span data-ttu-id="1f38b-104">**IRowsetResynch** non è disponibile su richiesta.</span><span class="sxs-lookup"><span data-stu-id="1f38b-104">**IRowsetResynch** is not available on demand.</span></span> <span data-ttu-id="1f38b-105">Il consumer deve richiedere l'interfaccia prima di aprire il set di righe.</span><span class="sxs-lookup"><span data-stu-id="1f38b-105">The consumer must request the interface before opening the rowset.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f38b-106">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1f38b-106">See Also</span></span>  
 [<span data-ttu-id="1f38b-107">Aggiornamento dei dati dei set di righe</span><span class="sxs-lookup"><span data-stu-id="1f38b-107">Updating Data in Rowsets</span></span>](updating-data-in-rowsets.md)  
  
  
