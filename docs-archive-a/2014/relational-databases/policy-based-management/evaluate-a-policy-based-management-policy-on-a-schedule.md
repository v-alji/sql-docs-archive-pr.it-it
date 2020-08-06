---
title: Valutare i criteri della gestione basata su criteri in una pianificazione | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Policy-Based Management, evaluate policy
ms.assetid: bea09522-ff47-4037-ab55-a98ea7c10099
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f1c6b1a7d13d14c02f4b4e537c2dbdb2df39d02c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715195"
---
# <a name="evaluate-a-policy-based-management-policy-on-a-schedule"></a><span data-ttu-id="02abe-102">Valutare i criteri della gestione basata su criteri in una pianificazione</span><span class="sxs-lookup"><span data-stu-id="02abe-102">Evaluate a Policy-Based Management Policy on a Schedule</span></span>
  <span data-ttu-id="02abe-103">In questo argomento verrà descritto come valutare i criteri della gestione basata su criteri in una pianificazione in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="02abe-103">This topic describes how to evaluate a Policy-Based Management policy on a schedule in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="02abe-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="02abe-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="02abe-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="02abe-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="02abe-106">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="02abe-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="02abe-107">**Per valutare i criteri in una pianificazione tramite:**</span><span class="sxs-lookup"><span data-stu-id="02abe-107">**To evaluate a policy on a schedule, using:**</span></span>  
  
     [<span data-ttu-id="02abe-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="02abe-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="02abe-109">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="02abe-109">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="02abe-110">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="02abe-110">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="02abe-111">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="02abe-111">Permissions</span></span>  
 <span data-ttu-id="02abe-112">È necessaria l'appartenenza al ruolo PolicyAdministratorRole nel database msdb.</span><span class="sxs-lookup"><span data-stu-id="02abe-112">Requires membership in the PolicyAdministratorRole role in the msdb database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="02abe-113">Con SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="02abe-113">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-evaluate-a-policy-on-a-schedule"></a><span data-ttu-id="02abe-114">Per valutare i criteri in una pianificazione</span><span class="sxs-lookup"><span data-stu-id="02abe-114">To evaluate a policy on a schedule</span></span>  
  
1.  <span data-ttu-id="02abe-115">In **Esplora oggetti**fare clic sul segno più per espandere il server contenente la pianificazione dei criteri da valutare.</span><span class="sxs-lookup"><span data-stu-id="02abe-115">In **Object Explorer**, click the plus sign to expand the server that contains the policy schedule that you want to evaluate.</span></span>  
  
2.  <span data-ttu-id="02abe-116">Fare clic sul segno più per espandere la cartella **Gestione** .</span><span class="sxs-lookup"><span data-stu-id="02abe-116">Click the plus sign to expand the **Management** folder.</span></span>  
  
3.  <span data-ttu-id="02abe-117">Fare clic sul segno più per espandere la cartella **Gestione criteri**.</span><span class="sxs-lookup"><span data-stu-id="02abe-117">Click the plus sign to expand **Policy Management**.</span></span>  
  
4.  <span data-ttu-id="02abe-118">Fare clic sul segno più per espandere la cartella **Criteri** .</span><span class="sxs-lookup"><span data-stu-id="02abe-118">Click the plus sign to expand the **Policies** folder.</span></span>  
  
5.  <span data-ttu-id="02abe-119">Fare clic con il pulsante destro del mouse sui criteri di cui si desidera valutare la pianificazione, quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="02abe-119">Right-click the policy whose schedule you what to evaluate and select **Properties**.</span></span>  
  
6.  <span data-ttu-id="02abe-120">Nella finestra di dialogo **Apri criteri -** _nome_criterio_ selezionare **Su pianificazione** nell'elenco **Modalità di valutazione**.</span><span class="sxs-lookup"><span data-stu-id="02abe-120">On the **Open Policy -**_policy_name_ dialog box, in the **Evaluation Mode** list, select **On schedule**.</span></span>  
  
7.  <span data-ttu-id="02abe-121">In **Pianificazione**fare clic su **Seleziona** per specificare una pianificazione esistente o su **Nuova** per creare una nuova pianificazione.</span><span class="sxs-lookup"><span data-stu-id="02abe-121">Under **Schedule**, click either **Pick** to specify an existing schedule or **New** to create a new schedule.</span></span>  
  
8.  <span data-ttu-id="02abe-122">Al termine, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="02abe-122">When finished, click **OK**.</span></span>  
  
  
