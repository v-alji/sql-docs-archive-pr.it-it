---
title: Piani di manutenzione del database sostituiti | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- suspended database maintenance plans
- database maintenance plans [SQL Server Agent]
- maintenance plans [SQL Server Agent]
ms.assetid: efac127c-6c81-4c7a-a6c4-9aae5d15545d
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 3aea75cc4ecc94ccbaeb1f35cecd0b18ff3a65ff
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623748"
---
# <a name="database-maintenance-plans-superseded"></a><span data-ttu-id="7dc95-102">Piani di manutenzione del database sostituiti</span><span class="sxs-lookup"><span data-stu-id="7dc95-102">Database maintenance plans superseded</span></span>
    
## <a name="component"></a><span data-ttu-id="7dc95-103">Componente</span><span class="sxs-lookup"><span data-stu-id="7dc95-103">Component</span></span>  
 [!INCLUDE[msCoName](../../includes/msconame-md.md)]<span data-ttu-id="7dc95-104">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Agente di</span><span class="sxs-lookup"><span data-stu-id="7dc95-104">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent</span></span>  
  
## <a name="description"></a><span data-ttu-id="7dc95-105">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7dc95-105">Description</span></span>  
 <span data-ttu-id="7dc95-106">I piani di manutenzione del database esistenti sono stati aggiornati e continuano a funzionare.</span><span class="sxs-lookup"><span data-stu-id="7dc95-106">Existing database maintenance plans are upgraded and continue to work.</span></span> <span data-ttu-id="7dc95-107">Tuttavia, non sarà possibile creare nuovi piani di manutenzione del database utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7dc95-107">However, you will not be able to create new database maintenance plans by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="7dc95-108">Per visualizzare i piani di manutenzione in Esplora oggetti, espandere Gestione, quindi espandere Legacy.</span><span class="sxs-lookup"><span data-stu-id="7dc95-108">To view the maintenance plans in Object Explorer, expand Management, and then expand Legacy.</span></span> <span data-ttu-id="7dc95-109">È possibile eseguire la migrazione dei piani di manutenzione del database esistenti al nuovo formato selezionando **migrate** dal menu di scelta rapida per qualsiasi piano di manutenzione del database.</span><span class="sxs-lookup"><span data-stu-id="7dc95-109">You can migrate existing database maintenance plans to the new format by selecting **Migrate** from the context menu for any database maintenance plan.</span></span> <span data-ttu-id="7dc95-110">Poiché la nuova caratteristica del piano di manutenzione del database non è una sostituzione diretta dei piani di manutenzione del database, dopo la migrazione è possibile che alcune funzionalità vadano perse.</span><span class="sxs-lookup"><span data-stu-id="7dc95-110">Because the new maintenance plan feature is not a direct replacement of database maintenance plans, some functionality might be lost after migration.</span></span> <span data-ttu-id="7dc95-111">Poiché il piano precedente non viene eliminato con la migrazione di un piano di manutenzione del database, è possibile testarne la funzionalità prima di rimuoverlo.</span><span class="sxs-lookup"><span data-stu-id="7dc95-111">Migrating a database maintenance plan does not delete the old plan, so you can test its functionality as a maintenance plan before removing the old plan.</span></span>  
  
 <span data-ttu-id="7dc95-112">Le caratteristiche seguenti non sono più supportate all'interno di piani di manutenzione del database:</span><span class="sxs-lookup"><span data-stu-id="7dc95-112">The following features are no longer supported within database maintenance plans:</span></span>  
  
-   <span data-ttu-id="7dc95-113">Log shipping</span><span class="sxs-lookup"><span data-stu-id="7dc95-113">Log shipping</span></span>  
  
-   <span data-ttu-id="7dc95-114">**Tentativo di ripristinare eventuali problemi di minore entità** dell'attività **controllo integrità database**</span><span class="sxs-lookup"><span data-stu-id="7dc95-114">The **Attempt to repair any minor problems** option of the **Database Integrity Check** task</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="7dc95-115">Azione correttiva</span><span class="sxs-lookup"><span data-stu-id="7dc95-115">Corrective Action</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="7dc95-116">impedisce l'inserimento del log shipping in un piano di manutenzione del database.</span><span class="sxs-lookup"><span data-stu-id="7dc95-116">prevents log shipping from being included in a database maintenance plan.</span></span> <span data-ttu-id="7dc95-117">Per ulteriori informazioni, vedere "Log shipping" nella documentazione online di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7dc95-117">For more information, see "Log Shipping" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
  
