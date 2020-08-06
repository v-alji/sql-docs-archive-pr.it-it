---
title: Valutare i criteri della gestione basata su criteri da un oggetto | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Policy-Based Management, evaluate policy
ms.assetid: b9e9d646-4894-4dee-a02a-0c71a8dc020e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f0de02092c87a727b723a5940805f34a75052e5e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87634984"
---
# <a name="evaluate-a-policy-based-management-policy-from-an-object"></a><span data-ttu-id="3a069-102">Valutare i criteri della gestione basata su criteri da un oggetto</span><span class="sxs-lookup"><span data-stu-id="3a069-102">Evaluate a Policy-Based Management Policy from an Object</span></span>
  <span data-ttu-id="3a069-103">In questo argomento verrà descritto come valutare i criteri da un'istanza del server, un database o un oggetto di database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3a069-103">This topic describes how to evaluate a policy from a server instance, database, or database object in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="3a069-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="3a069-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="3a069-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="3a069-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="3a069-106">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="3a069-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="3a069-107">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="3a069-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="3a069-108">**Per valutare i criteri da un oggetto tramite:**</span><span class="sxs-lookup"><span data-stu-id="3a069-108">**To evaluate a policy from an object, using:**</span></span>  
  
     [<span data-ttu-id="3a069-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3a069-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="3a069-110">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="3a069-110">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="3a069-111">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="3a069-111">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="3a069-112">La modalità di esecuzione è definita come parte dei criteri e non può essere modificata nella finestra di dialogo **Valuta criteri** .</span><span class="sxs-lookup"><span data-stu-id="3a069-112">The execution mode is defined as part of the policy and cannot be changed in the **Evaluate Policies** dialog box.</span></span>  
  
-   <span data-ttu-id="3a069-113">Nella finestra di dialogo **Valuta criteri** vengono visualizzati solo i criteri appropriati per l'oggetto di database.</span><span class="sxs-lookup"><span data-stu-id="3a069-113">The **Evaluate Policies** dialog box only shows policies appropriate for the database object.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="3a069-114">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="3a069-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="3a069-115">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="3a069-115">Permissions</span></span>  
 <span data-ttu-id="3a069-116">È necessaria l'appartenenza al ruolo PolicyAdministratorRole nel database msdb.</span><span class="sxs-lookup"><span data-stu-id="3a069-116">Requires membership in the PolicyAdministratorRole role in the msdb database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="3a069-117">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3a069-117">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-evaluate-a-policy-from-an-object"></a><span data-ttu-id="3a069-118">Per valutare i criteri da un oggetto</span><span class="sxs-lookup"><span data-stu-id="3a069-118">To evaluate a policy from an object</span></span>  
  
1.  <span data-ttu-id="3a069-119">In Esplora oggetti fare clic con il pulsante destro del mouse su un'istanza del server, un database o un oggetto di database, scegliere **Criteri**, quindi selezionare **Valuta**.</span><span class="sxs-lookup"><span data-stu-id="3a069-119">In Object Explorer, right-click a server instance, a database, or a database object, point to **Policies**, and select **Evaluate**.</span></span>  
  
2.  <span data-ttu-id="3a069-120">Nella finestra di dialogo **Valuta criteri** selezionare uno o più criteri e fare clic su **Valuta** per eseguire i criteri in modalità di valutazione.</span><span class="sxs-lookup"><span data-stu-id="3a069-120">In the **Evaluate Policies** dialog box, select one or more policies and click **Evaluate** to run the policy in evaluation mode.</span></span> <span data-ttu-id="3a069-121">Verrà generato un report sulla conformità per il set di destinazioni, ma [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] non verrà riconfigurato, né verrà applicata la conformità successiva.</span><span class="sxs-lookup"><span data-stu-id="3a069-121">This generates a compliance report for the target set but does not reconfigure [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or enforce future compliance.</span></span> <span data-ttu-id="3a069-122">Per destinazioni non conformi ai criteri selezionati e in cui sono incluse proprietà che possono essere riconfigurate dalla gestione basata su criteri, è possibile applicare la conformità ai criteri facendo clic su **Applica**.</span><span class="sxs-lookup"><span data-stu-id="3a069-122">For targets that do not comply with the selected policies and have properties that can be reconfigured by Policy-Based Management, you can enforce policy compliance by clicking **Apply**.</span></span> <span data-ttu-id="3a069-123">Per ulteriori informazioni sulle opzioni disponibili nella finestra di dialogo **Valuta criteri** , vedere [Evaluate Policies Dialog Box, Policy Selection Page](evaluate-policies-dialog-box-policy-selection-page.md), [Evaluate Policies Dialog Box, Evaluation Results Page](evaluate-policies-dialog-box-evaluation-results-page.md)e [Results Detailed View Dialog Box](results-detailed-view-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="3a069-123">For more information on the available options in the **Evaluate Policies** dialog box, see [Evaluate Policies Dialog Box, Policy Selection Page](evaluate-policies-dialog-box-policy-selection-page.md), [Evaluate Policies Dialog Box, Evaluation Results Page](evaluate-policies-dialog-box-evaluation-results-page.md), and [Results Detailed View Dialog Box](results-detailed-view-dialog-box.md).</span></span>  
  
3.  <span data-ttu-id="3a069-124">Al termine, fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="3a069-124">When finished, click **Close**.</span></span>  
  
  
