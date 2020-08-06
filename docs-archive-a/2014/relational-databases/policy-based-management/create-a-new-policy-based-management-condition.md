---
title: Creare una nuova condizione della gestione basata su criteri | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Policy-Based Management, creating policy conditions
ms.assetid: 8a612f7e-6c70-49db-a4de-48431e097cc5
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: e4fe206c9a82b69101508f6f0a760ca9c1bc423d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629380"
---
# <a name="create-a-new-policy-based-management-condition"></a><span data-ttu-id="0f4f2-102">Creare una nuova condizione della gestione basata su criteri</span><span class="sxs-lookup"><span data-stu-id="0f4f2-102">Create a New Policy-Based Management Condition</span></span>
  <span data-ttu-id="0f4f2-103">In questo argomento verrà descritto come creare una condizione della gestione basata su criteri in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0f4f2-103">This topic describes how to create a Policy-based Management condition in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="0f4f2-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="0f4f2-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="0f4f2-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="0f4f2-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="0f4f2-106">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="0f4f2-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="0f4f2-107">**Per creare una condizione tramite:**</span><span class="sxs-lookup"><span data-stu-id="0f4f2-107">**To create a condition, using:**</span></span>  
  
     [<span data-ttu-id="0f4f2-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="0f4f2-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="0f4f2-109">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="0f4f2-109">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="0f4f2-110">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="0f4f2-110">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="0f4f2-111">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="0f4f2-111">Permissions</span></span>  
 <span data-ttu-id="0f4f2-112">È necessaria l'appartenenza al ruolo PolicyAdministratorRole nel database msdb.</span><span class="sxs-lookup"><span data-stu-id="0f4f2-112">Requires membership in the PolicyAdministratorRole role in the msdb database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="0f4f2-113">Con SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="0f4f2-113">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-condition"></a><span data-ttu-id="0f4f2-114">Per creare una condizione</span><span class="sxs-lookup"><span data-stu-id="0f4f2-114">To create a condition</span></span>  
  
1.  <span data-ttu-id="0f4f2-115">In **Esplora oggetti**fare clic sul segno più per espandere il server in cui creare una condizione della gestione basata su criteri.</span><span class="sxs-lookup"><span data-stu-id="0f4f2-115">In **Object Explorer**, click the plus sign to expand the server where you want to create a Policy-based Management condition.</span></span>  
  
2.  <span data-ttu-id="0f4f2-116">Fare clic sul segno più per espandere la cartella **Gestione** .</span><span class="sxs-lookup"><span data-stu-id="0f4f2-116">Click the plus sign to expand the **Management** folder.</span></span>  
  
3.  <span data-ttu-id="0f4f2-117">Fare clic sul segno più per espandere la cartella **Gestione criteri**.</span><span class="sxs-lookup"><span data-stu-id="0f4f2-117">Click the plus sign to expand **Policy Management**.</span></span>  
  
4.  <span data-ttu-id="0f4f2-118">Fare clic sul segno più per espandere la cartella **Facet** .</span><span class="sxs-lookup"><span data-stu-id="0f4f2-118">Click the plus sign to expand the **Facets** folder.</span></span>  
  
5.  <span data-ttu-id="0f4f2-119">Fare clic con il pulsante destro del mouse sul facet nel quale creare una nuova condizione e selezionare **Nuova condizione**.</span><span class="sxs-lookup"><span data-stu-id="0f4f2-119">Right-click the facet in which you want to create a new condition and select **New Condition**.</span></span>  
  
6.  <span data-ttu-id="0f4f2-120">Nella casella **Nome** della finestra di dialogo **Crea nuova condizione** digitare il nome della nuova condizione.</span><span class="sxs-lookup"><span data-stu-id="0f4f2-120">In the **Create New Condition** dialog box, in the **Name** box, type the name of the new condition.</span></span>  
  
7.  <span data-ttu-id="0f4f2-121">Confermare il facet corretto nell'elenco **Facet** oppure selezionare un facet diverso.</span><span class="sxs-lookup"><span data-stu-id="0f4f2-121">Confirm the correct facet in the **Facet** list, or select a different facet.</span></span>  
  
8.  <span data-ttu-id="0f4f2-122">In **Espressione**creare le espressioni della condizione selezionando una proprietà facet nella casella **Campo** , insieme all'operatore e al valore associati.</span><span class="sxs-lookup"><span data-stu-id="0f4f2-122">Under **Expression**, construct condition expressions by selecting a facet property in the **Field** box, together with its associated operator and value.</span></span> <span data-ttu-id="0f4f2-123">Se si aggiungono più espressioni, è possibile crearne un join utilizzando **And** oppure **Or**.</span><span class="sxs-lookup"><span data-stu-id="0f4f2-123">When you add multiple expressions, the expressions can be joined by using **And** or **Or**.</span></span> <span data-ttu-id="0f4f2-124">Per altre informazioni sulle opzioni disponibili in questa finestra di dialogo, vedere [Finestra di dialogo Crea nuova condizione o Apri condizione, pagina Generale](../../integration-services/general-page-of-integration-services-designers-options.md), [Finestra di dialogo Crea nuova condizione o Apri condizione, pagina Descrizione](create-new-condition-or-open-condition-dialog-box-description-page.md)[Finestra di dialogo Modifica avanzata &#40;Condizione&#41;](advanced-edit-condition-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="0f4f2-124">For more information on the available options in this dialog box, see [Create New Condition or Open Condition Dialog Box, General Page](../../integration-services/general-page-of-integration-services-designers-options.md), [Create New Condition or Open Condition Dialog Box, Description Page](create-new-condition-or-open-condition-dialog-box-description-page.md), and [Advanced Edit &#40;Condition&#41; Dialog Box](advanced-edit-condition-dialog-box.md).</span></span>  
  
9. <span data-ttu-id="0f4f2-125">Al termine, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="0f4f2-125">When finished, click **OK**.</span></span>  
  
  
