---
title: Creare una gerarchia esplicita (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- creating explicit hierarchies [Master Data Services]
- explicit hierarchies, creating
ms.assetid: ba768393-6990-4eda-8cb0-d58cb3cfc2e2
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: aebf95e68f210fe5a573aed092231670c10fa188
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635091"
---
# <a name="create-an-explicit-hierarchy-master-data-services"></a><span data-ttu-id="bd4f1-102">Creare una gerarchia esplicita (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="bd4f1-102">Create an Explicit Hierarchy (Master Data Services)</span></span>
  <span data-ttu-id="bd4f1-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]creare una gerarchia esplicita quando è necessaria una gerarchia incompleta nella quale possono esistere membri a qualsiasi livello.</span><span class="sxs-lookup"><span data-stu-id="bd4f1-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], create an explicit hierarchy when you need a ragged hierarchy in which members can exist at any level.</span></span> <span data-ttu-id="bd4f1-104">Nelle gerarchie esplicite sono inclusi membri da una singola entità.</span><span class="sxs-lookup"><span data-stu-id="bd4f1-104">Explicit hierarchies contain members from a single entity.</span></span>  
  
 <span data-ttu-id="bd4f1-105">Dopo aver creato una gerarchia esplicita, è possibile aggiungervi membri nell'area funzionale **Esplora** .</span><span class="sxs-lookup"><span data-stu-id="bd4f1-105">After you create an explicit hierarchy, you can add members to it in the **Explorer** functional area.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="bd4f1-106">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="bd4f1-106">Prerequisites</span></span>  
 <span data-ttu-id="bd4f1-107">Per eseguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="bd4f1-107">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="bd4f1-108">È necessario disporre di autorizzazione per accedere all'area funzionale **Amministrazione sistema** .</span><span class="sxs-lookup"><span data-stu-id="bd4f1-108">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="bd4f1-109">È necessario essere un amministratore del modello.</span><span class="sxs-lookup"><span data-stu-id="bd4f1-109">You must be a model administrator.</span></span> <span data-ttu-id="bd4f1-110">Per ulteriori informazioni, vedere [amministratori &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="bd4f1-110">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="bd4f1-111">È necessario abilitare l'entità per le gerarchie esplicite e le raccolte.</span><span class="sxs-lookup"><span data-stu-id="bd4f1-111">The entity must be enabled for explicit hierarchies and collections.</span></span> <span data-ttu-id="bd4f1-112">Per altre informazioni, vedere [abilitare un'entità per gerarchie esplicite e raccolte &#40;Master Data Services&#41;](../../2014/master-data-services/enable-an-entity-for-explicit-hierarchies-and-collections-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="bd4f1-112">For more information, see [Enable an Entity for Explicit Hierarchies and Collections &#40;Master Data Services&#41;](../../2014/master-data-services/enable-an-entity-for-explicit-hierarchies-and-collections-master-data-services.md).</span></span>  
  
### <a name="to-create-an-explicit-hierarchy"></a><span data-ttu-id="bd4f1-113">Per creare una gerarchia esplicita</span><span class="sxs-lookup"><span data-stu-id="bd4f1-113">To create an explicit hierarchy</span></span>  
  
1.  <span data-ttu-id="bd4f1-114">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], fare clic su **Amministrazione sistema**.</span><span class="sxs-lookup"><span data-stu-id="bd4f1-114">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="bd4f1-115">Nella pagina **Vista modelli** scegliere **Gestisci** dalla barra dei menu, quindi fare clic su **Entità**.</span><span class="sxs-lookup"><span data-stu-id="bd4f1-115">On the **Model View** page, from the menu bar, point to **Manage** and click **Entities**.</span></span>  
  
3.  <span data-ttu-id="bd4f1-116">Nella pagina **Gestione entità** selezionare un modello dall'elenco **Modello** .</span><span class="sxs-lookup"><span data-stu-id="bd4f1-116">On the **Entity Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="bd4f1-117">Selezionare la riga relativa all'entità per la quale si desidera creare una gerarchia esplicita.</span><span class="sxs-lookup"><span data-stu-id="bd4f1-117">Select the row for the entity that you want to create an explicit hierarchy for.</span></span>  
  
5.  <span data-ttu-id="bd4f1-118">Fare clic su **Modifica entità selezionata**.</span><span class="sxs-lookup"><span data-stu-id="bd4f1-118">Click **Edit selected entity**.</span></span>  
  
6.  <span data-ttu-id="bd4f1-119">Nel riquadro **gerarchie esplicite** della pagina **Modifica entità** fare clic su **Aggiungi gerarchia esplicita**.</span><span class="sxs-lookup"><span data-stu-id="bd4f1-119">On the **Edit Entity** page, in the **Explicit hierarchies** pane, click **Add explicit hierarchy**.</span></span>  
  
7.  <span data-ttu-id="bd4f1-120">Nella pagina **Aggiungi gerarchia esplicita** , nella casella **nome gerarchia esplicita** , digitare un nome per la gerarchia.</span><span class="sxs-lookup"><span data-stu-id="bd4f1-120">On the **Add Explicit Hierarchy** page, in the **Explicit hierarchy name** box, type a name for the hierarchy.</span></span>  
  
8.  <span data-ttu-id="bd4f1-121">Facoltativamente, deselezionare la casella di controllo **Gerarchia obbligatoria** per creare una gerarchia come non obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="bd4f1-121">Optionally, clear the **Mandatory hierarchy** check box to create the hierarchy as a non-mandatory hierarchy.</span></span> <span data-ttu-id="bd4f1-122">Per altre informazioni sui tipi di gerarchia, vedere [Gerarchie esplicite &#40;Master Data Services&#41;](../../2014/master-data-services/explicit-hierarchies-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="bd4f1-122">For more information about hierarchy types, see [Explicit Hierarchies &#40;Master Data Services&#41;](../../2014/master-data-services/explicit-hierarchies-master-data-services.md).</span></span>  
  
9. <span data-ttu-id="bd4f1-123">Fare clic su **Salva gerarchia**.</span><span class="sxs-lookup"><span data-stu-id="bd4f1-123">Click **Save hierarchy**.</span></span>  
  
10. <span data-ttu-id="bd4f1-124">Nella pagina **Modifica entità** fare clic su **Salva entità**.</span><span class="sxs-lookup"><span data-stu-id="bd4f1-124">On the **Edit Entity** page, click **Save entity**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="bd4f1-125">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="bd4f1-125">Next Steps</span></span>  
  
-   [<span data-ttu-id="bd4f1-126">Creare membri consolidati &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="bd4f1-126">Create a Consolidated Member &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-consolidated-member-master-data-services.md)  
  
-   [<span data-ttu-id="bd4f1-127">Spostare i membri all'interno di una gerarchia &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="bd4f1-127">Move Members within a Hierarchy &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/move-members-within-a-hierarchy-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="bd4f1-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bd4f1-128">See Also</span></span>  
 <span data-ttu-id="bd4f1-129">[Gerarchie esplicite &#40;Master Data Services&#41;](../../2014/master-data-services/explicit-hierarchies-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="bd4f1-129">[Explicit Hierarchies &#40;Master Data Services&#41;](../../2014/master-data-services/explicit-hierarchies-master-data-services.md) </span></span>  
 <span data-ttu-id="bd4f1-130">[Gerarchie derivate con estremità esplicite &#40;Master Data Services&#41;](../../2014/master-data-services/derived-hierarchies-with-explicit-caps-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="bd4f1-130">[Derived Hierarchies with Explicit Caps &#40;Master Data Services&#41;](../../2014/master-data-services/derived-hierarchies-with-explicit-caps-master-data-services.md) </span></span>  
 [<span data-ttu-id="bd4f1-131">Modificare il nome di una gerarchia esplicita &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="bd4f1-131">Change an Explicit Hierarchy Name &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/change-an-explicit-hierarchy-name-master-data-services.md)  
  
  
