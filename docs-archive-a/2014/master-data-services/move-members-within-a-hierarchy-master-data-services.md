---
title: Spostare membri all'interno di una gerarchia (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- hierarchies [Master Data Services], moving members
- explicit hierarchies, moving members
- derived hierarchies, moving members
- members [Master Data Services], moving
ms.assetid: 049c9a15-89c1-478c-8438-028fffc9e187
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 37167f76b965197dbf8e37e365778395ec640d38
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627295"
---
# <a name="move-members-within-a-hierarchy-master-data-services"></a><span data-ttu-id="04489-102">Spostare membri all'interno di una gerarchia (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="04489-102">Move Members within a Hierarchy (Master Data Services)</span></span>
  <span data-ttu-id="04489-103">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] è possibile spostare i membri all'interno di una gerarchia per modificarne l'assegnazione della posizione o dell'elemento padre.</span><span class="sxs-lookup"><span data-stu-id="04489-103">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], move members within a hierarchy to change their location or parent assignment.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="04489-104">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="04489-104">Prerequisites</span></span>  
 <span data-ttu-id="04489-105">Per eseguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="04489-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="04489-106">È necessario disporre dell'autorizzazione per accedere all'area funzionale **Esplora** .</span><span class="sxs-lookup"><span data-stu-id="04489-106">You must have permission to access the **Explorer** functional area.</span></span>  
  
-   <span data-ttu-id="04489-107">Per le gerarchie esplicite, è necessario disporre almeno dell'autorizzazione **aggiornamento** per l'entità.</span><span class="sxs-lookup"><span data-stu-id="04489-107">For explicit hierarchies, you must have a minimum of **Update** permission to the entity.</span></span>  
  
-   <span data-ttu-id="04489-108">Per le gerarchie derivate, è necessario disporre almeno dell' **aggiornamento** del modello e degli attributi basati su dominio utilizzati nella gerarchia.</span><span class="sxs-lookup"><span data-stu-id="04489-108">For derived hierarchies, you must have a minimum of **Update** to the model and to any domain-based attributes used in the hierarchy.</span></span>  
  
### <a name="to-move-members-within-a-hierarchy"></a><span data-ttu-id="04489-109">Per spostare membri in una gerarchia</span><span class="sxs-lookup"><span data-stu-id="04489-109">To move members within a hierarchy</span></span>  
  
1.  <span data-ttu-id="04489-110">Nella home page di [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] selezionare un modello nell'elenco **Modello** .</span><span class="sxs-lookup"><span data-stu-id="04489-110">On the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] home page, from the **Model** list, select a model.</span></span>  
  
2.  <span data-ttu-id="04489-111">Selezionare una versione dall'elenco **Versione** .</span><span class="sxs-lookup"><span data-stu-id="04489-111">From the **Version** list, select a version.</span></span>  
  
3.  <span data-ttu-id="04489-112">Fare clic su **Esplora**.</span><span class="sxs-lookup"><span data-stu-id="04489-112">Click **Explorer**.</span></span>  
  
4.  <span data-ttu-id="04489-113">Dalla barra dei menu scegliere **gerarchie** e fare clic su *hierarchy_name*.</span><span class="sxs-lookup"><span data-stu-id="04489-113">From the menu bar, point to **Hierarchies** and click *hierarchy_name*.</span></span>  
  
5.  <span data-ttu-id="04489-114">Nel riquadro **gerarchia** , in cui la gerarchia viene visualizzata in una struttura ad albero, fare clic sulla casella di controllo relativa a ogni membro che si desidera spostare.</span><span class="sxs-lookup"><span data-stu-id="04489-114">In the **Hierarchy** pane, where the hierarchy is displayed in a tree structure, click the check box for each member you want to move.</span></span>  
  
6.  <span data-ttu-id="04489-115">Nella parte superiore del riquadro **gerarchia** fare clic su **taglia**.</span><span class="sxs-lookup"><span data-stu-id="04489-115">At the top of the **Hierarchy** pane, click **Cut**.</span></span>  
  
7.  <span data-ttu-id="04489-116">Nel riquadro **gerarchia** fare clic sulla casella di controllo per il membro in cui si desidera spostare i membri.</span><span class="sxs-lookup"><span data-stu-id="04489-116">In the **Hierarchy** pane, click the check box for the member you want to move the members to.</span></span>  
  
8.  <span data-ttu-id="04489-117">Fare clic su **Incolla**.</span><span class="sxs-lookup"><span data-stu-id="04489-117">Click **Paste**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="04489-118">Nelle gerarchie derivate è possibile spostare i membri solo nello stesso livello.</span><span class="sxs-lookup"><span data-stu-id="04489-118">In derived hierarchies, you can move members to the same level only.</span></span> <span data-ttu-id="04489-119">Non è inoltre possibile modificare l'ordinamento dei membri.</span><span class="sxs-lookup"><span data-stu-id="04489-119">Also, you cannot change the sort order of members.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04489-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="04489-120">See Also</span></span>  
 <span data-ttu-id="04489-121">[Spostare membri di gerarchie esplicite tramite il processo di gestione temporanea &#40;Master Data Services&#41;](add-update-and-delete-data-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="04489-121">[Move Explicit Hierarchy Members by Using the Staging Process &#40;Master Data Services&#41;](add-update-and-delete-data-master-data-services.md) </span></span>  
 <span data-ttu-id="04489-122">[Gerarchie derivate &#40;Master Data Services&#41;](../../2014/master-data-services/derived-hierarchies-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="04489-122">[Derived Hierarchies &#40;Master Data Services&#41;](../../2014/master-data-services/derived-hierarchies-master-data-services.md) </span></span>  
 [<span data-ttu-id="04489-123">Gerarchie esplicite &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="04489-123">Explicit Hierarchies &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/explicit-hierarchies-master-data-services.md)  
  
  
