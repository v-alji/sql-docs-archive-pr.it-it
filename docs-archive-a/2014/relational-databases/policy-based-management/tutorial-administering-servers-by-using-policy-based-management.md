---
title: 'Esercitazione: Amministrazione di server tramite la gestione basata su criteri | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- tutorials [Policy-Based Management]
- Policy-Based Management, tutorials
ms.assetid: 7de96e7b-9fb8-4cc8-8d85-61345d68a1e8
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 9b707a5ecd362c6b3b54e853f89d79e25a9e1428
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626700"
---
# <a name="tutorial-administering-servers-by-using-policy-based-management"></a><span data-ttu-id="189eb-102">Esercitazione: Amministrazione di server tramite la gestione basata su criteri</span><span class="sxs-lookup"><span data-stu-id="189eb-102">Tutorial: Administering Servers by Using Policy-Based Management</span></span>
  <span data-ttu-id="189eb-103">Questa esercitazione sull'amministrazione di server tramite criteri della gestione basata su criteri</span><span class="sxs-lookup"><span data-stu-id="189eb-103">Welcome to the Administering Servers by Using Policy-Based Management Policies tutorial.</span></span> <span data-ttu-id="189eb-104">è destinata agli utenti che hanno familiarità con [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , ma che non conoscono i concetti relativi alla gestione basata su criteri.</span><span class="sxs-lookup"><span data-stu-id="189eb-104">This tutorial is intended for users who are familiar with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] but new to the Policy-Based Management.</span></span>  
  
## <a name="what-you-will-learn"></a><span data-ttu-id="189eb-105">Lezioni dell'esercitazione</span><span class="sxs-lookup"><span data-stu-id="189eb-105">What You Will Learn</span></span>  
 <span data-ttu-id="189eb-106">Questa esercitazione consente di creare criteri per amministrare il server e criteri che si applicano a un singolo database.</span><span class="sxs-lookup"><span data-stu-id="189eb-106">This tutorial creates a policy to administer your server and a policy that applies to a single database.</span></span> <span data-ttu-id="189eb-107">I criteri vengono eseguiti su richiesta per testare la conformità.</span><span class="sxs-lookup"><span data-stu-id="189eb-107">One policy is run on demand to test for compliance.</span></span> <span data-ttu-id="189eb-108">Gli altri criteri applicano la conformità successiva.</span><span class="sxs-lookup"><span data-stu-id="189eb-108">The other policy enforces future compliance.</span></span>  
  
 <span data-ttu-id="189eb-109">L'esercitazione è suddivisa in due lezioni:</span><span class="sxs-lookup"><span data-stu-id="189eb-109">This tutorial is divided into two lessons:</span></span>  
  
 [<span data-ttu-id="189eb-110">Lezione 1: Creare e applicare criteri Disattivata per impostazione predefinita</span><span class="sxs-lookup"><span data-stu-id="189eb-110">Lesson 1: Create and Apply an Off By Default Policy</span></span>](lesson-1-create-and-apply-an-off-by-default-policy.md)  
 <span data-ttu-id="189eb-111">In questa lezione vengono creati i criteri che consentono di specificare la disabilitazione di Posta elettronica database nel server.</span><span class="sxs-lookup"><span data-stu-id="189eb-111">This lesson creates a policy that specifies that Database Mail is not enabled on the server.</span></span> <span data-ttu-id="189eb-112">Viene quindi verificato se il server è conforme ai criteri e viene configurato il server disabilitando Posta elettronica database.</span><span class="sxs-lookup"><span data-stu-id="189eb-112">Then, it checks to see whether your server complies with the policy, and configures the server by disabling Database Mail.</span></span>  
  
 [<span data-ttu-id="189eb-113">Lezione 2: Creare e applicare criteri per gli standard di denominazione</span><span class="sxs-lookup"><span data-stu-id="189eb-113">Lesson 2: Create and Apply a Naming Standards Policy</span></span>](lesson-2-create-and-apply-a-naming-standards-policy.md)  
 <span data-ttu-id="189eb-114">Questa lezione consente di creare criteri che definiscono e applicano uno standard di denominazione per le tabelle.</span><span class="sxs-lookup"><span data-stu-id="189eb-114">This lesson creates a policy that defines and enforces a naming standard for tables.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="189eb-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="189eb-115">Requirements</span></span>  
 <span data-ttu-id="189eb-116">Questa lezione richiede una conoscenza di base dei concetti relativi ai database e una certa familiarità con [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="189eb-116">This lesson requires basic database knowledge and a basic understanding of [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="189eb-117">Per utilizzare l'esercitazione, è necessario che nel sistema sia installato [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="189eb-117">To use this tutorial, your system must have [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] installed.</span></span>  
  
## <a name="start-the-tutorial"></a><span data-ttu-id="189eb-118">Avviare l'esercitazione</span><span class="sxs-lookup"><span data-stu-id="189eb-118">Start the Tutorial</span></span>  
 [<span data-ttu-id="189eb-119">Lezione 1: Creare e applicare criteri Disattivata per impostazione predefinita</span><span class="sxs-lookup"><span data-stu-id="189eb-119">Lesson 1: Create and Apply an Off By Default Policy</span></span>](lesson-1-create-and-apply-an-off-by-default-policy.md)  
  
## <a name="see-also"></a><span data-ttu-id="189eb-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="189eb-120">See Also</span></span>  
 [<span data-ttu-id="189eb-121">Amministrazione di server tramite la gestione basata su criteri</span><span class="sxs-lookup"><span data-stu-id="189eb-121">Administer Servers by Using Policy-Based Management</span></span>](administer-servers-by-using-policy-based-management.md)  
  
  
