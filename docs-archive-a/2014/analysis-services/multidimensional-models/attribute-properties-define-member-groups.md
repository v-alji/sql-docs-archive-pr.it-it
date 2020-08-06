---
title: Definire gruppi di membri | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- member groups [Analysis Services]
- grouping members
- DiscretizationMethod property
ms.assetid: 006cc915-c499-4781-b9a7-01ad31bebf6a
author: minewiskan
ms.author: owend
ms.openlocfilehash: 95f9516c7a0077e97af348afa863fe15c8d4528b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725116"
---
# <a name="define-member-groups"></a><span data-ttu-id="725d7-102">Definire gruppi di membri</span><span class="sxs-lookup"><span data-stu-id="725d7-102">Define Member Groups</span></span>
  <span data-ttu-id="725d7-103">Se un attributo include un numero elevato di membri, è possibile scegliere di raggruppare tali membri in bucket, riducendo il numero di membri visualizzati dagli utenti durante la ricerca dei dati in una gerarchia.</span><span class="sxs-lookup"><span data-stu-id="725d7-103">If an attribute has a large number of members, you can choose to group those members into buckets, reducing the number of members that users see when they browse the data in a hierarchy.</span></span> <span data-ttu-id="725d7-104">È inoltre possibile determinare il numero di bucket in cui sono raggruppati i membri e impostare uno schema di denominazione per i bucket.</span><span class="sxs-lookup"><span data-stu-id="725d7-104">You can also determine the number of buckets in which the members are groups and set a naming scheme for the buckets.</span></span> <span data-ttu-id="725d7-105">Per altre informazioni, vedere [Raggruppare membri di attributo &#40;discretizzazione&#41;](attribute-properties-group-attribute-members.md).</span><span class="sxs-lookup"><span data-stu-id="725d7-105">For more information, see [Group Attribute Members &#40;Discretization&#41;](attribute-properties-group-attribute-members.md).</span></span>  
  
 <span data-ttu-id="725d7-106">I membri vengono raggruppati impostando la proprietà **DiscretizationMethod** , accessibile tramite la finestra **Proprietà** di [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="725d7-106">You group members by setting the **DiscretizationMethod** property, which is accessed through the **Properties** window in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="725d7-107">Durante la creazione di gruppi di membri, le modifiche apportate non sono disponibili per gli utenti fino a quando non è stata elaborata la dimensione.</span><span class="sxs-lookup"><span data-stu-id="725d7-107">When you create member groups, your changes are not available to users until you process the dimension.</span></span> <span data-ttu-id="725d7-108">Per ulteriori informazioni, vedere [elaborazione di oggetti del modello multidimensionale](processing-a-multidimensional-model-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="725d7-108">For more information, see [Multidimensional Model Object Processing](processing-a-multidimensional-model-analysis-services.md).</span></span>  
  
### <a name="to-create-member-groups"></a><span data-ttu-id="725d7-109">Per creare gruppi di membri</span><span class="sxs-lookup"><span data-stu-id="725d7-109">To create member groups</span></span>  
  
1.  <span data-ttu-id="725d7-110">Aprire la dimensione che si desidera utilizzare.</span><span class="sxs-lookup"><span data-stu-id="725d7-110">Open the dimension that you want to work with.</span></span> <span data-ttu-id="725d7-111">Per impostazione predefinita, verrà visualizzata la scheda **Struttura dimensione** .</span><span class="sxs-lookup"><span data-stu-id="725d7-111">The **Dimension Structure** tab opens by default.</span></span>  
  
2.  <span data-ttu-id="725d7-112">In **Attributi**fare clic con il pulsante destro del mouse sull'attributo di cui si vuole raggruppare i membri e quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="725d7-112">In **Attributes**, right-click the attribute whose members you want to group, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="725d7-113">Selezionare un metodo di raggruppamento dei membri nell'elenco a discesa accanto alla proprietà **DiscretizationMethod**.</span><span class="sxs-lookup"><span data-stu-id="725d7-113">From the drop-down list next to **DiscretizationMethod**, select a method by which to group the members.</span></span> <span data-ttu-id="725d7-114">Per altre informazioni sulle impostazioni della proprietà **DiscretizationMethod**, vedere [Raggruppare membri di attributo &#40;discretizzazione&#41;](attribute-properties-group-attribute-members.md).</span><span class="sxs-lookup"><span data-stu-id="725d7-114">For more information about **DiscretizationMethod** settings, see [Group Attribute Members &#40;Discretization&#41;](attribute-properties-group-attribute-members.md).</span></span>  
  
  
