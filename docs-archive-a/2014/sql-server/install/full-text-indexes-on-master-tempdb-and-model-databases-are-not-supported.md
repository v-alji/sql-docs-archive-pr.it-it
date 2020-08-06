---
title: Gli indici full-text nei database master, tempdb e modello non sono supportati | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- full-text indexes
ms.assetid: f7992965-42c1-4eb8-a7fb-afb38b67c740
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: fbd5e3133ed87fed9bdaf6d668df62c6471df766
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87638254"
---
# <a name="full-text-indexes-on-master-tempdb-and-model-databases-are-not-supported"></a><span data-ttu-id="b091f-102">Gli indici full-text nei database master, tempdb e model non sono supportati</span><span class="sxs-lookup"><span data-stu-id="b091f-102">Full-text indexes on master, tempdb and model databases are not supported</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="b091f-103">non consente indici full-text in un database di sistema.</span><span class="sxs-lookup"><span data-stu-id="b091f-103">does not allow full-text indexes on any system database.</span></span>  
  
## <a name="description"></a><span data-ttu-id="b091f-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b091f-104">Description</span></span>  
 <span data-ttu-id="b091f-105">In [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] gli indici full-text sono supportati nei database master, tempdb e model.</span><span class="sxs-lookup"><span data-stu-id="b091f-105">In [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], full-text indexes were supported on the master, tempdb, and model databases.</span></span>  
  
 <span data-ttu-id="b091f-106">Eventuali cataloghi full-text nei database master, tempdb e modello vengono rimossi durante l'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="b091f-106">Any full-text catalogs in the master, tempdb, and model databases are removed during the upgrade.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b091f-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b091f-107">See Also</span></span>  
 [<span data-ttu-id="b091f-108">Uso di Preparazione aggiornamento</span><span class="sxs-lookup"><span data-stu-id="b091f-108">Working with Upgrade Advisor</span></span>](../../../2014/sql-server/install/working-with-upgrade-advisor.md)  
  
  
