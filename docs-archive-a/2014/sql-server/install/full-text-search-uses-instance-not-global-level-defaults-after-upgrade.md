---
title: Con l'aggiornamento, la ricerca full-text utilizzerà i Word breaker e i filtri a livello di istanza, non globali, per impostazione predefinita | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- filters [Full-Text Search]
- word breakers [Full-Text Search]
ms.assetid: 93ee8fcb-d11c-49fa-8fac-51ed31a8f008
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 0b6cea7ab63351fad25f0205a614e364328171a9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87638251"
---
# <a name="upgrading-will-cause-full-text-search-to-use-instance-level-not-global-word-breakers-and-filters-by-default"></a><span data-ttu-id="453f7-102">A seguito dell'aggiornamento, per la ricerca full-text verranno utilizzati per impostazione predefinita word breaker e filtri a livello di istanza, non globali</span><span class="sxs-lookup"><span data-stu-id="453f7-102">Upgrading will cause Full-Text Search to use instance-level, not global, word breakers and filters by default</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="453f7-103">consente la registrazione a livello di istanza per i nuovi word breaker e i nuovi filtri.</span><span class="sxs-lookup"><span data-stu-id="453f7-103">provides a way to allow instance-level registration of new word breakers and filters.</span></span>  
  
## <a name="component"></a><span data-ttu-id="453f7-104">Componente</span><span class="sxs-lookup"><span data-stu-id="453f7-104">Component</span></span>  
 <span data-ttu-id="453f7-105">Ricerca full-text</span><span class="sxs-lookup"><span data-stu-id="453f7-105">Full-Text Search</span></span>  
  
## <a name="description"></a><span data-ttu-id="453f7-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="453f7-106">Description</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="453f7-107">consente la registrazione a livello di istanza per i nuovi word breaker e i nuovi filtri.</span><span class="sxs-lookup"><span data-stu-id="453f7-107">allows the instance-level registration of new word breakers and filters.</span></span> <span data-ttu-id="453f7-108">La registrazione a livello di istanza garantisce un isolamento funzionale e la sicurezza delle istanze.</span><span class="sxs-lookup"><span data-stu-id="453f7-108">This instance-level registration provides functional and security isolation between instances.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="453f7-109">Azione correttiva</span><span class="sxs-lookup"><span data-stu-id="453f7-109">Corrective Action</span></span>  
 <span data-ttu-id="453f7-110">Dopo l'aggiornamento, utilizzare `sp_fulltext_service` per impostare la proprietà del servizio e `load_os_resources` che consente il caricamento dei componenti.</span><span class="sxs-lookup"><span data-stu-id="453f7-110">After upgrading, use the `sp_fulltext_service` to set the service property and `load_os_resources`, which allows the components to be loaded.</span></span> <span data-ttu-id="453f7-111">È necessario eseguire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="453f7-111">You must run the following:</span></span>  
  
 `sp_fulltext_service 'load_os_resources', 1`  
  
## <a name="see-also"></a><span data-ttu-id="453f7-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="453f7-112">See Also</span></span>  
 [<span data-ttu-id="453f7-113">Uso di Preparazione aggiornamento</span><span class="sxs-lookup"><span data-stu-id="453f7-113">Working with Upgrade Advisor</span></span>](../../../2014/sql-server/install/working-with-upgrade-advisor.md)  
  
  
