---
title: Gli indici full-text su colonne calcolate non salvate non sono consentiti | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- full-text indexes
ms.assetid: cba737f7-b187-47d0-8458-23dc18d18aca
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: de153d45e2f652bfea6e9dce68428af84be68b6c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87638253"
---
# <a name="full-text-indexes-on-nonpersisted-computed-columns-are-not-allowed"></a><span data-ttu-id="3ac47-102">Gli indici full-text su colonne calcolate non persistenti non sono consentiti</span><span class="sxs-lookup"><span data-stu-id="3ac47-102">Full-text indexes on nonpersisted, computed columns are not allowed</span></span>
  <span data-ttu-id="3ac47-103">Non è possibile creare indici full-text in colonne calcolate non deterministiche e imprecise.</span><span class="sxs-lookup"><span data-stu-id="3ac47-103">You cannot create full-text indexes on nondeterministic and imprecise computed columns.</span></span> <span data-ttu-id="3ac47-104">Non è possibile utilizzare tali colonne come colonne tipo o come colonne chiave full-text.</span><span class="sxs-lookup"><span data-stu-id="3ac47-104">Such columns cannot be used as type columns or as full-text key columns.</span></span>  
  
## <a name="description"></a><span data-ttu-id="3ac47-105">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3ac47-105">Description</span></span>  
 <span data-ttu-id="3ac47-106">In [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] è possibile creare un indice full-text utilizzando una colonna calcolata non deterministica e imprecisa come colonna tipo o come colonna chiave full-text.</span><span class="sxs-lookup"><span data-stu-id="3ac47-106">In [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], a full-text index can be created by using a nondeterministic and imprecise computed column as the type column or the full-text key column.</span></span> <span data-ttu-id="3ac47-107">Questa funzionalità non è supportata.</span><span class="sxs-lookup"><span data-stu-id="3ac47-107">This functionality is not supported.</span></span> <span data-ttu-id="3ac47-108">Quando si esegue l'aggiornamento, gli indici full-text precedenti, incompatibili e non supportati vengono disabilitati.</span><span class="sxs-lookup"><span data-stu-id="3ac47-108">When you upgrade, older, incompatible, and unsupported full-text indexes are disabled.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="3ac47-109">Azione correttiva</span><span class="sxs-lookup"><span data-stu-id="3ac47-109">Corrective Action</span></span>  
 <span data-ttu-id="3ac47-110">Per abilitare questi indici full-text, modificare le definizioni di colonna in modo che le colonne siano deterministiche e precise.</span><span class="sxs-lookup"><span data-stu-id="3ac47-110">To enable these full-text indexes, modify the column definitions so that the columns are deterministic and precise.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ac47-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3ac47-111">See Also</span></span>  
 [<span data-ttu-id="3ac47-112">Uso di Preparazione aggiornamento</span><span class="sxs-lookup"><span data-stu-id="3ac47-112">Working with Upgrade Advisor</span></span>](../../../2014/sql-server/install/working-with-upgrade-advisor.md)  
  
  
