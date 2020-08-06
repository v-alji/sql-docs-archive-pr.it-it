---
title: Tipi di Sottoscrittore | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.newpubwizard.subscribertypes.f1
ms.assetid: a70656cb-21c9-4489-be77-ccd396747e3b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 4d356377dec1f5307fa136c94ea682c0824479a8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637246"
---
# <a name="subscriber-types"></a><span data-ttu-id="5e3c8-102">Tipi di Sottoscrittore</span><span class="sxs-lookup"><span data-stu-id="5e3c8-102">Subscriber Types</span></span>
  <span data-ttu-id="5e3c8-103">La replica di tipo merge consente di specificare i tipi di Sottoscrittore che si richiede vengano supportati da una pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="5e3c8-103">Merge replication allows you to specify the types of Subscribers that a publication must support.</span></span> <span data-ttu-id="5e3c8-104">La selezione dei tipi di Sottoscrittore causa l'impostazione del *livello di compatibilità della pubblicazione*, che determina le funzionalità utilizzabili da una pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="5e3c8-104">Selecting Subscriber types sets the *publication compatibility level*, which determines which features can be used by a publication.</span></span>  
  
 <span data-ttu-id="5e3c8-105">Dopo aver creato una pubblicazione snapshot, è possibile aumentare il livello di compatibilità della pubblicazione, rendendolo più restrittivo, nella pagina **Generale** della finestra di dialogo **Proprietà pubblicazione** . Non è possibile diminuire il livello di compatibilità.</span><span class="sxs-lookup"><span data-stu-id="5e3c8-105">After a publication snapshot is created, the publication compatibility level can be increased (made more restrictive) on the **General** page of the **Publication Properties** dialog box; the compatibility level cannot be decreased.</span></span>  
  
## <a name="options"></a><span data-ttu-id="5e3c8-106">Opzioni</span><span class="sxs-lookup"><span data-stu-id="5e3c8-106">Options</span></span>  
 <span data-ttu-id="5e3c8-107">Consente di selezionare i tipi di Sottoscrittore che devono essere supportati dalla pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="5e3c8-107">Select each Subscriber type that this publication must support.</span></span>  
  
 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]  
 <span data-ttu-id="5e3c8-108">La pubblicazione è in grado di utilizzare tutte le funzionalità.</span><span class="sxs-lookup"><span data-stu-id="5e3c8-108">The publication can use all features.</span></span>  
  
 [!INCLUDE[ssEW](../../includes/ssew-md.md)]  
 <span data-ttu-id="5e3c8-109">La pubblicazione richiede che i file di snapshot siano in formato carattere, gestito automaticamente dall'agente snapshot.</span><span class="sxs-lookup"><span data-stu-id="5e3c8-109">The publication requires snapshot files to be in character format (this is handled automatically by the Snapshot Agent).</span></span> [!INCLUDE[ssEW](../../includes/ssew-md.md)] <span data-ttu-id="5e3c8-110">prevede inoltre alcune limitazioni non correlate al livello di compatibilità.</span><span class="sxs-lookup"><span data-stu-id="5e3c8-110">also has a number of restrictions not related to compatibility level.</span></span>  
  
 <span data-ttu-id="5e3c8-111">Se si seleziona questa opzione, l'opzione per la sincronizzazione Web viene abilitata per la pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="5e3c8-111">If this option is selected, the Web synchronization option is enabled for the publication.</span></span> <span data-ttu-id="5e3c8-112">Per ulteriori informazioni sulla sincronizzazione Web, vedere [Web Synchronization for Merge Replication](web-synchronization-for-merge-replication.md).</span><span class="sxs-lookup"><span data-stu-id="5e3c8-112">For more information about Web synchronization, see [Web Synchronization for Merge Replication](web-synchronization-for-merge-replication.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e3c8-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5e3c8-113">See Also</span></span>  
 <span data-ttu-id="5e3c8-114">[Pubblicare dati e oggetti di database](publish/publish-data-and-database-objects.md) </span><span class="sxs-lookup"><span data-stu-id="5e3c8-114">[Publish Data and Database Objects](publish/publish-data-and-database-objects.md) </span></span>  
 <span data-ttu-id="5e3c8-115">[Create a Publication](publish/create-a-publication.md) </span><span class="sxs-lookup"><span data-stu-id="5e3c8-115">[Create a Publication](publish/create-a-publication.md) </span></span>  
 [<span data-ttu-id="5e3c8-116">Visualizzare e modificare le proprietà del server di pubblicazione e del database di distribuzione</span><span class="sxs-lookup"><span data-stu-id="5e3c8-116">View and Modify Distributor and Publisher Properties</span></span>](view-and-modify-distributor-and-publisher-properties.md)   

  
