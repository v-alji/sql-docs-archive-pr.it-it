---
title: Valutare i criteri della gestione basata su criteri da quei criteri | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Policy-Based Management, evaluate policy
ms.assetid: 0b3214bd-d0ab-45ab-9281-3d95507abe54
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 207c86f1465c49238fc9b50ee75489b43d956caf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87634986"
---
# <a name="evaluate-a-policy-based-management-policy-from-that-policy"></a><span data-ttu-id="f7599-102">Valutare i criteri della gestione basata su criteri da quei criteri</span><span class="sxs-lookup"><span data-stu-id="f7599-102">Evaluate a Policy-Based Management Policy from That Policy</span></span>
  <span data-ttu-id="f7599-103">In questo argomento verrà descritto come valutare i criteri utilizzandoli in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f7599-103">This topic describes how to evaluate a policy using that policy in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="f7599-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="f7599-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="f7599-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="f7599-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="f7599-106">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="f7599-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="f7599-107">**Per valutare i criteri tramite:**</span><span class="sxs-lookup"><span data-stu-id="f7599-107">**To evaluate a policy, using:**</span></span>  
  
     [<span data-ttu-id="f7599-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f7599-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="f7599-109">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="f7599-109">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="f7599-110">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="f7599-110">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="f7599-111">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="f7599-111">Permissions</span></span>  
 <span data-ttu-id="f7599-112">È necessaria l'appartenenza al ruolo PolicyAdministratorRole nel database msdb.</span><span class="sxs-lookup"><span data-stu-id="f7599-112">Requires membership in the PolicyAdministratorRole role in the msdb database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="f7599-113">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f7599-113">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-evaluate-a-policy"></a><span data-ttu-id="f7599-114">Per valutare i criteri</span><span class="sxs-lookup"><span data-stu-id="f7599-114">To evaluate a policy</span></span>  
  
1.  <span data-ttu-id="f7599-115">In **Esplora oggetti**fare clic sul segno più per espandere il server contenente i criteri da valutare.</span><span class="sxs-lookup"><span data-stu-id="f7599-115">In **Object Explorer**, click the plus sign to expand the server that contains the policy that you want to evaluate.</span></span>  
  
2.  <span data-ttu-id="f7599-116">Fare clic sul segno più per espandere la cartella **Gestione** .</span><span class="sxs-lookup"><span data-stu-id="f7599-116">Click the plus sign to expand the **Management** folder.</span></span>  
  
3.  <span data-ttu-id="f7599-117">Fare clic sul segno più per espandere la cartella **Gestione criteri**.</span><span class="sxs-lookup"><span data-stu-id="f7599-117">Click the plus sign to expand **Policy Management**.</span></span>  
  
4.  <span data-ttu-id="f7599-118">Fare clic sul segno più per espandere la cartella **Criteri** .</span><span class="sxs-lookup"><span data-stu-id="f7599-118">Click the plus sign to expand the **Policies** folder.</span></span>  
  
5.  <span data-ttu-id="f7599-119">Fare clic con il pulsante destro del mouse sui criteri da valutare e scegliere **Valuta**.</span><span class="sxs-lookup"><span data-stu-id="f7599-119">Right-click the policy that you want to evaluate and select **Evaluate**.</span></span>  
  
6.  <span data-ttu-id="f7599-120">Nella finestra di dialogo **Risultati valutazione**  verranno visualizzati i risultati della valutazione dei criteri.</span><span class="sxs-lookup"><span data-stu-id="f7599-120">In the **Evaluate Results**  dialog box, you see the results of the policy evaluation.</span></span> <span data-ttu-id="f7599-121">Per le destinazioni non conformi ai criteri e con proprietà che possono essere riconfigurate tramite gestione basata su criteri, è possibile applicare la conformità facendo clic su **Applica**.</span><span class="sxs-lookup"><span data-stu-id="f7599-121">For targets that do not comply with the policy and have properties that can be reconfigured by Policy-Based Management, you can enforce compliance by clicking **Apply**.</span></span> <span data-ttu-id="f7599-122">Per ulteriori informazioni sulle opzioni disponibili nella finestra di dialogo **Valuta criteri** , vedere [Evaluate Policies Dialog Box, Policy Selection Page](evaluate-policies-dialog-box-policy-selection-page.md) e [Evaluate Policies Dialog Box, Evaluation Results Page](evaluate-policies-dialog-box-evaluation-results-page.md).</span><span class="sxs-lookup"><span data-stu-id="f7599-122">For more information on the available options in the **Evaluate Policies** dialog box, see [Evaluate Policies Dialog Box, Policy Selection Page](evaluate-policies-dialog-box-policy-selection-page.md) and [Evaluate Policies Dialog Box, Evaluation Results Page](evaluate-policies-dialog-box-evaluation-results-page.md).</span></span>  
  
7.  <span data-ttu-id="f7599-123">Al termine, fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="f7599-123">When finished, click **Close**.</span></span>  
  
  
