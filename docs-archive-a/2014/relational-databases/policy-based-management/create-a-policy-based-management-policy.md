---
title: Creare i criteri della gestione basata su criteri | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Policy-Based Management, creating policies
ms.assetid: b28bf963-89f9-4941-b6c1-6004fec347f1
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: e76b4dce17e00bae5e8ca4fcf071868c0641c786
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629375"
---
# <a name="create-a-policy-based-management-policy"></a><span data-ttu-id="e1d20-102">Creare i criteri della gestione basata su criteri</span><span class="sxs-lookup"><span data-stu-id="e1d20-102">Create a Policy-Based Management Policy</span></span>
  <span data-ttu-id="e1d20-103">In questo argomento verrà descritto come creare i criteri della gestione basata su criteri in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e1d20-103">This topic describes how to create a Policy-Based Management policy in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="e1d20-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="e1d20-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="e1d20-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="e1d20-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="e1d20-106">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="e1d20-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="e1d20-107">**Per creare i criteri tramite:**</span><span class="sxs-lookup"><span data-stu-id="e1d20-107">**To create a policy, using:**</span></span>  
  
     [<span data-ttu-id="e1d20-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e1d20-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="e1d20-109">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="e1d20-109">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="e1d20-110">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="e1d20-110">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="e1d20-111">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="e1d20-111">Permissions</span></span>  
 <span data-ttu-id="e1d20-112">È necessaria l'appartenenza al ruolo PolicyAdministratorRole nel database msdb.</span><span class="sxs-lookup"><span data-stu-id="e1d20-112">Requires membership in the PolicyAdministratorRole role in the msdb database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="e1d20-113">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e1d20-113">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-policy"></a><span data-ttu-id="e1d20-114">Per creare criteri</span><span class="sxs-lookup"><span data-stu-id="e1d20-114">To create a policy</span></span>  
  
1.  <span data-ttu-id="e1d20-115">In **Esplora oggetti**fare clic sul segno più per espandere il server in cui creare un nuovo criterio della gestione basata su criteri.</span><span class="sxs-lookup"><span data-stu-id="e1d20-115">In **Object Explorer**, click the plus sign to expand the server where you want to create a new a Policy-Based Management policy.</span></span>  
  
2.  <span data-ttu-id="e1d20-116">Fare clic sul segno più per espandere la cartella **Gestione** .</span><span class="sxs-lookup"><span data-stu-id="e1d20-116">Click the plus sign to expand the **Management** folder.</span></span>  
  
3.  <span data-ttu-id="e1d20-117">Fare clic sul segno più per espandere la cartella **Gestione criteri**.</span><span class="sxs-lookup"><span data-stu-id="e1d20-117">Click the plus sign to expand **Policy Management**.</span></span>  
  
4.  <span data-ttu-id="e1d20-118">Fare clic con il pulsante destro del mouse sulla cartella **Criteri** e scegliere **Nuovi criteri**.</span><span class="sxs-lookup"><span data-stu-id="e1d20-118">Right-click the **Policies** folder and select **New Policy**.</span></span>  
  
5.  <span data-ttu-id="e1d20-119">Nella casella **Nome** della finestra di dialogo **Crea nuovi criteri** digitare il nome dei nuovi criteri.</span><span class="sxs-lookup"><span data-stu-id="e1d20-119">In the **Create New Policy** dialog box, in the **Name** box, type the name of the new policy.</span></span>  
  
6.  <span data-ttu-id="e1d20-120">Se si desidera che i criteri siano abilitati non appena vengono creati, selezionare la casella di controllo **Abilitati** .</span><span class="sxs-lookup"><span data-stu-id="e1d20-120">If you want the policy to be enabled as soon as it is created, select the **Enabled** check box.</span></span> <span data-ttu-id="e1d20-121">Se la modalità di valutazione è **Su richiesta**, la casella di controllo **Abilitati** non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="e1d20-121">If the evaluation mode is **On demand**, the **Enabled** check box is not available.</span></span>  
  
7.  <span data-ttu-id="e1d20-122">Nell'elenco **Condizione di controllo** selezionare una delle condizioni esistenti oppure **Nuova condizione**.</span><span class="sxs-lookup"><span data-stu-id="e1d20-122">In the **Check condition** list, select one of the existing conditions, or select **New Condition**.</span></span> <span data-ttu-id="e1d20-123">Per modificare una condizione, selezionarla, quindi fare clic sui puntini di sospensione ( **...** ). Per altre informazioni, vedere [Creare una nuova condizione della gestione basata su criteri](create-a-new-policy-based-management-condition.md) o [Visualizzare o modificare le proprietà di una condizione della gestione basata su criteri](view-or-modify-the-properties-of-a-policy-based-management-condition.md).</span><span class="sxs-lookup"><span data-stu-id="e1d20-123">To edit a condition, select the condition and then click the ellipsis (**...**). For more information, see [Create a New Policy-Based Management Condition](create-a-new-policy-based-management-condition.md) or [View or Modify the Properties of a Policy-Based Management Condition](view-or-modify-the-properties-of-a-policy-based-management-condition.md).</span></span>  
  
8.  <span data-ttu-id="e1d20-124">Nella casella **In base alle destinazioni** selezionare uno o più tipi di destinazione per i criteri.</span><span class="sxs-lookup"><span data-stu-id="e1d20-124">In the **Against targets** box, select one or more target types for this policy.</span></span> <span data-ttu-id="e1d20-125">Alcune condizioni e facet possono essere applicati solo a determinati tipi di destinazioni.</span><span class="sxs-lookup"><span data-stu-id="e1d20-125">Some conditions and facets can only be applied to certain types of targets.</span></span> <span data-ttu-id="e1d20-126">I set di destinazioni disponibili vengono visualizzati nella casella associata.</span><span class="sxs-lookup"><span data-stu-id="e1d20-126">The available target sets appear in the associated box.</span></span> <span data-ttu-id="e1d20-127">Espandere **Ogni** per selezionare una condizione di filtro per tipi specifici delle destinazioni.</span><span class="sxs-lookup"><span data-stu-id="e1d20-127">Expand **Every** to select a filtering condition for some types of the targets.</span></span> <span data-ttu-id="e1d20-128">Se in questa casella non viene visualizzata alcuna destinazione, l'ambito della condizione è costituito dal livello server.</span><span class="sxs-lookup"><span data-stu-id="e1d20-128">If no targets appear in this box, the check condition is scoped at the server level.</span></span>  
  
9. <span data-ttu-id="e1d20-129">Nella casella **Modalità di valutazione** selezionare il comportamento dei criteri.</span><span class="sxs-lookup"><span data-stu-id="e1d20-129">In the **Evaluation Mode** box, select how this policy will behave.</span></span> <span data-ttu-id="e1d20-130">Condizioni diverse possono essere associate a diverse modalità di valutazione valide.</span><span class="sxs-lookup"><span data-stu-id="e1d20-130">Different conditions can have different valid evaluation modes.</span></span> <span data-ttu-id="e1d20-131">Per altre informazioni sulle modalità di valutazione valide, vedere [Amministrare server tramite la gestione basata su criteri](administer-servers-by-using-policy-based-management.md).</span><span class="sxs-lookup"><span data-stu-id="e1d20-131">For more information about which evaluation modes are valid, see [Administer Servers by Using Policy-Based Management](administer-servers-by-using-policy-based-management.md).</span></span>  
  
10. <span data-ttu-id="e1d20-132">Se i criteri verranno valutato in una pianificazione, impostare la modalità di valutazione su **Su pianificazione**e quindi fare clic su **Seleziona** per selezionare una pianificazione oppure su **Nuova** per crearne una nuova.</span><span class="sxs-lookup"><span data-stu-id="e1d20-132">If the policy will be evaluated on a schedule, set the evaluation mode to **On schedule**, and then click **Pick** to select a schedule, or click **New** to create a new schedule.</span></span>  
  
11. <span data-ttu-id="e1d20-133">Per limitare i criteri a un subset dei tipi di destinazione, nella casella **Restrizione server** selezionare le condizioni di restrizione oppure creare una nuova condizione.</span><span class="sxs-lookup"><span data-stu-id="e1d20-133">To limit the policy to subset of the target types, in the **Server restriction** box, select from limiting conditions or create a new condition.</span></span>  
  
     <span data-ttu-id="e1d20-134">Per ulteriori informazioni sulle opzioni disponibili nella finestra di dialogo **Crea nuovi criteri** , vedere [Finestra di dialogo Crea nuovi criteri o Apri criteri, pagina Generale](../../integration-services/general-page-of-integration-services-designers-options.md) o [Finestra di dialogo Crea nuovi criteri o Apri criteri, pagina Descrizione](create-new-policy-or-open-policy-dialog-box-description-page.md).</span><span class="sxs-lookup"><span data-stu-id="e1d20-134">For more information on the available options in the **Create New Policy** dialog box, see [Create New Policy or Open Policy Dialog Box, General Page](../../integration-services/general-page-of-integration-services-designers-options.md) or [Create New Policy or Open Policy Dialog Box, Description Page](create-new-policy-or-open-policy-dialog-box-description-page.md).</span></span>  
  
12. <span data-ttu-id="e1d20-135">Al termine, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="e1d20-135">When finished click **OK**.</span></span>  
  
  
