---
title: Nuovo profilo agente | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.profiles.newperfprofile.f1
helpviewer_keywords:
- New Agent Profile dialog box
ms.assetid: ebf59330-a421-45a5-9020-0484a96852bc
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1d7848e44585fd35a5b5a33cf431e15de96c9375
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721342"
---
# <a name="new-agent-profile"></a><span data-ttu-id="e904f-102">Nuovo profilo agente</span><span class="sxs-lookup"><span data-stu-id="e904f-102">New Agent Profile</span></span>
  <span data-ttu-id="e904f-103">La finestra di dialogo **Nuovo profilo agente** consente di creare un nuovo profilo.</span><span class="sxs-lookup"><span data-stu-id="e904f-103">Use the **New Agent Profile** dialog box to create a new profile.</span></span> <span data-ttu-id="e904f-104">I nuovi profili sono sempre basati su profili esistenti, ma possono essere modificati in base ai requisiti delle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="e904f-104">New profiles are always based on existing profiles, but they can be modified to meet application requirements.</span></span> <span data-ttu-id="e904f-105">Dopo aver creato un profilo, è possibile applicarlo a processi agente esistenti e creati in un secondo momento nella finestra di dialogo **Profili agente** .</span><span class="sxs-lookup"><span data-stu-id="e904f-105">After a profile has been created, it can be applied to existing and future agent jobs in the **Agent Profiles** dialog box.</span></span> <span data-ttu-id="e904f-106">I valori dei parametri degli agenti possono essere modificati nella finestra di dialogo \<**AgentProfileName>Proprietà \*\*.</span><span class="sxs-lookup"><span data-stu-id="e904f-106">Agent parameter values can be edited in the \<**AgentProfileName> Properties\*\* dialog box.</span></span>  
  
## <a name="options"></a><span data-ttu-id="e904f-107">Opzioni</span><span class="sxs-lookup"><span data-stu-id="e904f-107">Options</span></span>  
 <span data-ttu-id="e904f-108">**Nome**</span><span class="sxs-lookup"><span data-stu-id="e904f-108">**Name**</span></span>  
 <span data-ttu-id="e904f-109">Consente di immettere un nome per il profilo.</span><span class="sxs-lookup"><span data-stu-id="e904f-109">Enter a name for the profile.</span></span>  
  
 <span data-ttu-id="e904f-110">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="e904f-110">**Description**</span></span>  
 <span data-ttu-id="e904f-111">Consente di immettere una descrizione per il profilo.</span><span class="sxs-lookup"><span data-stu-id="e904f-111">Enter a description for the profile.</span></span>  
  
 <span data-ttu-id="e904f-112">**Parametro**</span><span class="sxs-lookup"><span data-stu-id="e904f-112">**Parameter**</span></span>  
 <span data-ttu-id="e904f-113">I parametri degli agenti inclusi nel profilo.</span><span class="sxs-lookup"><span data-stu-id="e904f-113">The agent parameters included in the profile.</span></span> <span data-ttu-id="e904f-114">Il profilo su cui è basato il nuovo profilo non contiene necessariamente un valore per ogni parametro.</span><span class="sxs-lookup"><span data-stu-id="e904f-114">The profile on which the new profile is based does not necessarily specify a value for each parameter.</span></span> <span data-ttu-id="e904f-115">Per visualizzare tutti i parametri validi per un determinato agente, deselezionare la casella di controllo **Mostra solo i parametri utilizzati in questo profilo** .</span><span class="sxs-lookup"><span data-stu-id="e904f-115">To see all parameters that are valid for a given agent, clear the **Show only parameters used in this profile** check box.</span></span> <span data-ttu-id="e904f-116">Per una descrizione dei singoli parametri, vedere:</span><span class="sxs-lookup"><span data-stu-id="e904f-116">For descriptions of each parameter, see:</span></span>  
  
-   [<span data-ttu-id="e904f-117">Replication Snapshot Agent</span><span class="sxs-lookup"><span data-stu-id="e904f-117">Replication Snapshot Agent</span></span>](agents/replication-snapshot-agent.md)  
  
-   [<span data-ttu-id="e904f-118">Agente lettura log repliche</span><span class="sxs-lookup"><span data-stu-id="e904f-118">Replication Log Reader Agent</span></span>](agents/replication-log-reader-agent.md)  
  
-   [<span data-ttu-id="e904f-119">Replication Distribution Agent</span><span class="sxs-lookup"><span data-stu-id="e904f-119">Replication Distribution Agent</span></span>](agents/replication-distribution-agent.md)  
  
-   [<span data-ttu-id="e904f-120">Replication Merge Agent</span><span class="sxs-lookup"><span data-stu-id="e904f-120">Replication Merge Agent</span></span>](agents/replication-merge-agent.md)  
  
-   [<span data-ttu-id="e904f-121">Agente di lettura coda repliche</span><span class="sxs-lookup"><span data-stu-id="e904f-121">Replication Queue Reader Agent</span></span>](agents/replication-queue-reader-agent.md)  
  
 <span data-ttu-id="e904f-122">**Valore predefinito**</span><span class="sxs-lookup"><span data-stu-id="e904f-122">**Default Value**</span></span>  
 <span data-ttu-id="e904f-123">Il valore predefinito per ogni parametro degli agenti.</span><span class="sxs-lookup"><span data-stu-id="e904f-123">The default value for each agent parameter.</span></span>  
  
 <span data-ttu-id="e904f-124">**Valore**</span><span class="sxs-lookup"><span data-stu-id="e904f-124">**Value**</span></span>  
 <span data-ttu-id="e904f-125">Il valore specificato per il parametro nel profilo su cui è basato il nuovo profilo.</span><span class="sxs-lookup"><span data-stu-id="e904f-125">The value specified for the parameter in the profile on which the new profile is based.</span></span> <span data-ttu-id="e904f-126">Modificare questo campo per qualsiasi valore di parametro che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="e904f-126">Edit this field for any parameter values you want to change.</span></span>  
  
 <span data-ttu-id="e904f-127">**Mostra solo i parametri utilizzati in questo profilo**</span><span class="sxs-lookup"><span data-stu-id="e904f-127">**Show only parameters used in this profile**</span></span>  
 <span data-ttu-id="e904f-128">Deselezionare questa casella di controllo per mostrare tutti i parametri validi per un determinato agente.</span><span class="sxs-lookup"><span data-stu-id="e904f-128">Clear to show all valid parameters for a given agent.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e904f-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e904f-129">See Also</span></span>  
 <span data-ttu-id="e904f-130">[Usare i profili agenti di replica](agents/work-with-replication-agent-profiles.md) </span><span class="sxs-lookup"><span data-stu-id="e904f-130">[Work with Replication Agent Profiles](agents/work-with-replication-agent-profiles.md) </span></span>  
 <span data-ttu-id="e904f-131">[Panoramica degli agenti di replica](agents/replication-agents-overview.md) </span><span class="sxs-lookup"><span data-stu-id="e904f-131">[Replication Agents Overview](agents/replication-agents-overview.md) </span></span>  
 [<span data-ttu-id="e904f-132">Profili degli agenti di replica</span><span class="sxs-lookup"><span data-stu-id="e904f-132">Replication Agent Profiles</span></span>](agents/replication-agent-profiles.md)  
  
  
