---
title: Profili agenti | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.profiles.perfprofiles.f1
helpviewer_keywords:
- Agent Profiles dialog box
ms.assetid: 0422e99c-e688-419b-bb4c-c7bebeef1d8d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 7584670088da1ac7a9c81f1f8f0cbdce8b040c7b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626666"
---
# <a name="agent-profiles"></a><span data-ttu-id="d4d61-102">Profili agenti</span><span class="sxs-lookup"><span data-stu-id="d4d61-102">Agent Profiles</span></span>
  <span data-ttu-id="d4d61-103">Utilizzare la finestra di dialogo **Profili agenti** per gestire i profili degli agenti.</span><span class="sxs-lookup"><span data-stu-id="d4d61-103">Use the **Agent Profiles** dialog box to manage agent profiles.</span></span> <span data-ttu-id="d4d61-104">I profili agenti consentono di gestire facilmente i parametri di run-time per ogni agente.</span><span class="sxs-lookup"><span data-stu-id="d4d61-104">Agent profiles provide a convenient way to manage the runtime parameters for each agent.</span></span> <span data-ttu-id="d4d61-105">Ogni agente dispone di un profilo predefinito e alcuni agenti dispongono di profili predefiniti aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="d4d61-105">Each agent has a default profile, and some agents have additional predefined profiles.</span></span> <span data-ttu-id="d4d61-106">L'agente di merge, ad esempio, dispone di un profilo "collegamento lento" dedicato alle connessioni a larghezza di banda ridotta.</span><span class="sxs-lookup"><span data-stu-id="d4d61-106">For example, the Merge Agent has a "slow link" profile designed for low bandwidth connections.</span></span> <span data-ttu-id="d4d61-107">I profili predefiniti sono sufficienti per la maggior parte delle applicazioni, ma è possibile creare profili definiti dall'utente, che consentono di personalizzare il funzionamento degli agenti.</span><span class="sxs-lookup"><span data-stu-id="d4d61-107">Predefined profiles are sufficient for most applications, but you can also create user-defined profiles, allowing you to customize agent behavior.</span></span>  
  
## <a name="options"></a><span data-ttu-id="d4d61-108">Opzioni</span><span class="sxs-lookup"><span data-stu-id="d4d61-108">Options</span></span>  
 <span data-ttu-id="d4d61-109">**Selezione pagina**</span><span class="sxs-lookup"><span data-stu-id="d4d61-109">**Select a page**</span></span>  
 <span data-ttu-id="d4d61-110">Consente di selezionare un agente nel riquadro sinistro in modo da visualizzare i rispettivi profili in quello destro.</span><span class="sxs-lookup"><span data-stu-id="d4d61-110">Select an agent in the left pane, and the profiles for the agent are displayed in the right pane.</span></span>  
  
 <span data-ttu-id="d4d61-111">**Predefinito per i nuovi agenti**</span><span class="sxs-lookup"><span data-stu-id="d4d61-111">**Default for New**</span></span>  
 <span data-ttu-id="d4d61-112">Consente di selezionare il profilo che verrà utilizzato durante la creazione dei processi per un dato tipo di agente.</span><span class="sxs-lookup"><span data-stu-id="d4d61-112">Select the profile that will be used when jobs are created for an agent of a given type.</span></span> <span data-ttu-id="d4d61-113">Se ad esempio si creano varie sottoscrizioni a una pubblicazione di tipo merge, il processo dell'agente di merge per ogni sottoscrizione utilizzerà il profilo selezionato.</span><span class="sxs-lookup"><span data-stu-id="d4d61-113">For example, if you create a number of subscriptions to a merge publication, the Merge Agent job for each subscription will use the profile selected.</span></span> <span data-ttu-id="d4d61-114">Per modificare il profilo di processi esistenti, selezionare un profilo e quindi fare clic su **Modifica agenti esistenti**.</span><span class="sxs-lookup"><span data-stu-id="d4d61-114">If you want to change the profile for existing jobs, select a profile, and then click **Change Existing Agents**.</span></span>  
  
 <span data-ttu-id="d4d61-115">**Nome**</span><span class="sxs-lookup"><span data-stu-id="d4d61-115">**Name**</span></span>  
 <span data-ttu-id="d4d61-116">Nome del profilo.</span><span class="sxs-lookup"><span data-stu-id="d4d61-116">The name of the profile.</span></span>  
  
 <span data-ttu-id="d4d61-117">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="d4d61-117">**Type**</span></span>  
 <span data-ttu-id="d4d61-118">Tipo di profilo: **Utente** (definito dall'utente) o **Sistema** (predefinito).</span><span class="sxs-lookup"><span data-stu-id="d4d61-118">The type of profile: **User** (user-defined) or **System** (predefined).</span></span>  
  
 <span data-ttu-id="d4d61-119">**Proprietà (...)**</span><span class="sxs-lookup"><span data-stu-id="d4d61-119">**Properties (...)**</span></span>  
 <span data-ttu-id="d4d61-120">Fare clic su questo pulsante per visualizzare i valori utilizzati per ogni parametro nel profilo agente.</span><span class="sxs-lookup"><span data-stu-id="d4d61-120">Click to view the values used for each parameter in the agent profile.</span></span>  
  
 <span data-ttu-id="d4d61-121">**Nuovo**</span><span class="sxs-lookup"><span data-stu-id="d4d61-121">**New**</span></span>  
 <span data-ttu-id="d4d61-122">Fare clic su questo pulsante per creare un nuovo profilo.</span><span class="sxs-lookup"><span data-stu-id="d4d61-122">Click to create a new profile.</span></span>  
  
 <span data-ttu-id="d4d61-123">**Elimina**</span><span class="sxs-lookup"><span data-stu-id="d4d61-123">**Delete**</span></span>  
 <span data-ttu-id="d4d61-124">Selezionare un profilo definito dall'utente e quindi fare clic su **Elimina** per eliminarlo.</span><span class="sxs-lookup"><span data-stu-id="d4d61-124">Select a user-defined profile, and then click **Delete** to delete that profile.</span></span> <span data-ttu-id="d4d61-125">I profili predefiniti non possono essere eliminati.</span><span class="sxs-lookup"><span data-stu-id="d4d61-125">Predefined profiles cannot be deleted.</span></span>  
  
 <span data-ttu-id="d4d61-126">**Modifica agenti esistenti**</span><span class="sxs-lookup"><span data-stu-id="d4d61-126">**Change Existing Agents**</span></span>  
 <span data-ttu-id="d4d61-127">Selezionare un profilo e quindi fare clic su **Modifica agenti esistenti** per specificare che tutti i processi esistenti per un dato tipo di agente devono utilizzare il profilo selezionato.</span><span class="sxs-lookup"><span data-stu-id="d4d61-127">Select a profile, and then click **Change Existing Agents** to specify that all existing jobs for an agent of a given type should use the selected profile.</span></span> <span data-ttu-id="d4d61-128">Se ad esempio sono state create varie sottoscrizioni a una pubblicazione di tipo merge e si desidera modificare il profilo per specificare che il processo dell'agente di merge per ogni sottoscrizione deve utilizzare il **Profilo agente a collegamento lento**, selezionare tale profilo e quindi fare clic su **Modifica agenti esistenti**.</span><span class="sxs-lookup"><span data-stu-id="d4d61-128">For example, if you have created a number of subscriptions to a merge publication, and you want to change the profile to specify that the Merge Agent job for each of these subscriptions should use the **Slow link agent profile**, select that profile, and then click **Change Existing Agents**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4d61-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d4d61-129">See Also</span></span>  
 <span data-ttu-id="d4d61-130">[Usare i profili agenti di replica](agents/work-with-replication-agent-profiles.md) </span><span class="sxs-lookup"><span data-stu-id="d4d61-130">[Work with Replication Agent Profiles](agents/work-with-replication-agent-profiles.md) </span></span>  
 <span data-ttu-id="d4d61-131">[Panoramica degli agenti di replica](agents/replication-agents-overview.md) </span><span class="sxs-lookup"><span data-stu-id="d4d61-131">[Replication Agents Overview](agents/replication-agents-overview.md) </span></span>  
 [<span data-ttu-id="d4d61-132">Profili degli agenti di replica</span><span class="sxs-lookup"><span data-stu-id="d4d61-132">Replication Agent Profiles</span></span>](agents/replication-agent-profiles.md)  
  
  
