---
title: Aggiungere un attributo a una dimensione | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- adding attributes
- automatic attribute creation
- attributes [Analysis Services], creating
- attributes [Analysis Services], adding
- manual attribute creation [Analysis Services]
ms.assetid: 25826ba1-2b38-4b34-bd3a-7eba116093ae
author: minewiskan
ms.author: owend
ms.openlocfilehash: 776591e94deedc679592cfe36d53fb1fea4093d4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637466"
---
# <a name="add-an--attribute-to-a-dimension"></a><span data-ttu-id="6cbcb-102">Aggiungere un attributo a una dimensione</span><span class="sxs-lookup"><span data-stu-id="6cbcb-102">Add an  Attribute to a Dimension</span></span>
  <span data-ttu-id="6cbcb-103">È possibile aggiungere un attributo a una dimensione in modo automatico o manuale [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6cbcb-103">You can add an attribute to a dimension either automatically or manually in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="6cbcb-104">Per creare un attributo automaticamente, nella scheda **Struttura dimensione** di Progettazione dimensioni, in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], selezionare la colonna di cui si vuole eseguire il mapping a un attributo e quindi trascinare tale colonna nel riquadro **Attributi** dal riquadro **Vista origine dati** .</span><span class="sxs-lookup"><span data-stu-id="6cbcb-104">To create an attribute automatically, on the **Dimension Structure** tab of Dimension Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], select the column that you want to map to an attribute, and then drag that column from the **Data Source View** pane to the **Attributes** pane.</span></span> <span data-ttu-id="6cbcb-105">Verrà creato un attributo di cui viene eseguito il mapping alla colonna al quale verrà assegnato lo stesso nome della colonna.</span><span class="sxs-lookup"><span data-stu-id="6cbcb-105">This creates an attribute that is mapped to the column, and assigns the same name to the attribute as the name of the column.</span></span> <span data-ttu-id="6cbcb-106">Se esiste già un attributo con lo stesso nome, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] aggiungerà al nome un suffisso composto da un numero ordinale, a partire da "1" per il primo nome duplicato.</span><span class="sxs-lookup"><span data-stu-id="6cbcb-106">If an attribute that uses that name already exists, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] adds an ordinal number suffix, starting with "1" for the first duplicate name.</span></span>  
  
 <span data-ttu-id="6cbcb-107">Per creare un attributo manualmente, attivare la visualizzazione griglia nel riquadro **Attributi** .</span><span class="sxs-lookup"><span data-stu-id="6cbcb-107">To create an attribute manually, set the **Attributes** pane to grid view.</span></span> <span data-ttu-id="6cbcb-108">Nella colonna nome dell'ultima riga della griglia fare clic sull' **\<new attribute>** elemento.</span><span class="sxs-lookup"><span data-stu-id="6cbcb-108">In the name column of the last row in the grid, click the **\<new attribute>** item.</span></span> <span data-ttu-id="6cbcb-109">Digitare un nome per il nuovo attributo.</span><span class="sxs-lookup"><span data-stu-id="6cbcb-109">Type a name for the new attribute.</span></span> <span data-ttu-id="6cbcb-110">Verrà creato un attributo di cui viene eseguito il mapping a una colonna con le impostazioni predefinite per tutte le proprietà.</span><span class="sxs-lookup"><span data-stu-id="6cbcb-110">This creates an attribute that is not mapped to a column and that has default settings for all its properties.</span></span> <span data-ttu-id="6cbcb-111">È possibile impostare il mapping nella finestra **Proprietà** di [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)] configurando la proprietà **KeyColumns** del nuovo attributo.</span><span class="sxs-lookup"><span data-stu-id="6cbcb-111">You can set the mapping in the **Properties** window of [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)] by configuring the **KeyColumns** property for the new attribute.</span></span>  
  
 <span data-ttu-id="6cbcb-112">Per altre informazioni, vedere [Definire automaticamente un nuovo attributo](attribute-properties-define-a-new-attribute-automatically.md), [Definire manualmente un nuovo attributo](../define-a-new-attribute-manually.md), [Associare un attributo a una colonna del nome](attribute-properties-bind-an-attribute-to-a-name-column.md)e [Modificare la proprietà KeyColumn di un attributo](attribute-properties-modify-the-keycolumn-property.md).</span><span class="sxs-lookup"><span data-stu-id="6cbcb-112">For more information, see [Define a New Attribute Automatically](attribute-properties-define-a-new-attribute-automatically.md), [Define a New Attribute Manually](../define-a-new-attribute-manually.md), [Bind an Attribute to a Name Column](attribute-properties-bind-an-attribute-to-a-name-column.md), and [Modify the KeyColumn Property of an Attribute](attribute-properties-modify-the-keycolumn-property.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6cbcb-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6cbcb-113">See Also</span></span>  
 [<span data-ttu-id="6cbcb-114">Riferimento alle proprietà degli attributo delle dimensioni</span><span class="sxs-lookup"><span data-stu-id="6cbcb-114">Dimension Attribute Properties Reference</span></span>](dimension-attribute-properties-reference.md)  
  
  
