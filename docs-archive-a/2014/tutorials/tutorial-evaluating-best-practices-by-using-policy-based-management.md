---
title: 'Esercitazione: valutazione delle procedure consigliate tramite la gestione basata su criteri | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- best practices analyzer
- Policy-Based Management, best practices policies
- Best Practices [Database Engine]
- Policy-Based Management, evaluating policies
- BPA
- tutorials [Policy-Based Management]
- Policy-Based Management, tutorials
ms.assetid: c7867f9b-7acc-4fae-bde1-63808c403ebc
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 42e6b505c71abecce7b56b5cb2544b4e9f4e8f71
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87717045"
---
# <a name="tutorial-evaluating-best-practices-by-using-policy-based-management"></a><span data-ttu-id="ffc6e-102">Esercitazione: Valutazione di procedure consigliate tramite la gestione basata su criteri</span><span class="sxs-lookup"><span data-stu-id="ffc6e-102">Tutorial: Evaluating Best Practices by Using Policy-Based Management</span></span>
  <span data-ttu-id="ffc6e-103">Questa esercitazione per la valutazione di procedure consigliate tramite la gestione basata su criteri</span><span class="sxs-lookup"><span data-stu-id="ffc6e-103">Welcome to the Evaluating Best Practices by Using Policy-Based Management tutorial.</span></span> <span data-ttu-id="ffc6e-104">è destinata agli utenti che hanno una certa familiarità con [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], ma non con la gestione basata su criteri.</span><span class="sxs-lookup"><span data-stu-id="ffc6e-104">This tutorial is intended for users who are familiar with [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], but new to Policy-Based Management.</span></span> <span data-ttu-id="ffc6e-105">La gestione basata su criteri è un sistema per definire i criteri che possono essere utilizzati per applicare gli standard di amministrazione del sito.</span><span class="sxs-lookup"><span data-stu-id="ffc6e-105">Policy-Based Management is a system for defining policies that can be used enforce site administration standards.</span></span> <span data-ttu-id="ffc6e-106">In questa gestione è incluso un set di criteri per procedure consigliate utilizzabili per analizzare un'istanza di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] in modo da poter determinare se l'istanza soddisfa le linee guida e le indicazioni delle procedure consigliate.</span><span class="sxs-lookup"><span data-stu-id="ffc6e-106">Policy-Based Management includes a set of best practices policies that you can use to analyze an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] to determine whether the instance meets best practices guidelines and recommendations.</span></span>  
  
## <a name="what-you-will-learn"></a><span data-ttu-id="ffc6e-107">Lezioni dell'esercitazione</span><span class="sxs-lookup"><span data-stu-id="ffc6e-107">What You Will Learn</span></span>  
 <span data-ttu-id="ffc6e-108">In questa esercitazione verrà illustrato come valutare i criteri per procedure consigliate per il [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)] su richiesta (o "ad hoc") oppure in base a una pianificazione specifica.</span><span class="sxs-lookup"><span data-stu-id="ffc6e-108">In this tutorial, you will learn how to evaluate best practices policies for the [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)] on an on-demand (or "ad hoc") basis, or on a scheduled basis.</span></span>  
  
 <span data-ttu-id="ffc6e-109">L'esercitazione è suddivisa in due lezioni:</span><span class="sxs-lookup"><span data-stu-id="ffc6e-109">This tutorial is divided into two lessons:</span></span>  
  
 [<span data-ttu-id="ffc6e-110">Lezione 1: Valutazione delle procedure consigliate su richiesta</span><span class="sxs-lookup"><span data-stu-id="ffc6e-110">Lesson 1: Evaluate Best Practices on an On-Demand Basis</span></span>](../../2014/tutorials/lesson-1-evaluate-best-practices-on-an-on-demand-basis.md)  
 <span data-ttu-id="ffc6e-111">In questa lezione si eseguirà una valutazione su richiesta dei criteri in una o più istanze di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ffc6e-111">In this lesson, you perform an on-demand evaluation of the policies against one or more instances of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="ffc6e-112">Lezione 2: Valutazione di criteri per procedure consigliate in base a una pianificazione</span><span class="sxs-lookup"><span data-stu-id="ffc6e-112">Lesson 2: Evaluate Best Practices Policies on a Scheduled Basis</span></span>](../../2014/tutorials/lesson-2-evaluate-best-practices-policies-on-a-scheduled-basis.md)  
 <span data-ttu-id="ffc6e-113">In questa lezione verranno configurati i criteri per procedure consigliate da eseguire in base a una pianificazione specifica.</span><span class="sxs-lookup"><span data-stu-id="ffc6e-113">In this lesson, you configure best practices policies to run on a scheduled basis.</span></span> <span data-ttu-id="ffc6e-114">Inoltre, nella lezione viene mostrato come configurare criteri pianificati in un'istanza singola, nonché come distribuire i criteri pianificati da una posizione principale in più istanze di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ffc6e-114">The lesson shows how to configure scheduled policies on a single instance, and how to deploy scheduled policies from a central location to multiple instances of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ffc6e-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ffc6e-115">Requirements</span></span>  
 <span data-ttu-id="ffc6e-116">Questa lezione richiede una conoscenza di base dei concetti relativi ai database e una certa familiarità con [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ffc6e-116">This lesson requires basic database knowledge and a basic understanding of [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="ffc6e-117">Per utilizzare l'esercitazione è necessario che nel server sia installato [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ffc6e-117">To use this tutorial, the server must have [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] installed.</span></span>  
  
## <a name="start-the-tutorial"></a><span data-ttu-id="ffc6e-118">Avviare l'esercitazione</span><span class="sxs-lookup"><span data-stu-id="ffc6e-118">Start the Tutorial</span></span>  
 [<span data-ttu-id="ffc6e-119">Lezione 1: Valutazione delle procedure consigliate su richiesta</span><span class="sxs-lookup"><span data-stu-id="ffc6e-119">Lesson 1: Evaluate Best Practices on an On-Demand Basis</span></span>](../../2014/tutorials/lesson-1-evaluate-best-practices-on-an-on-demand-basis.md)  
  
## <a name="see-also"></a><span data-ttu-id="ffc6e-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ffc6e-120">See Also</span></span>  
 [<span data-ttu-id="ffc6e-121">Amministrazione di server tramite la gestione basata su criteri</span><span class="sxs-lookup"><span data-stu-id="ffc6e-121">Administer Servers by Using Policy-Based Management</span></span>](../relational-databases/policy-based-management/administer-servers-by-using-policy-based-management.md)  
  
  
