---
title: Impostare formule personalizzate membro per gli attributi in una dimensione | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Business Intelligence enhancements [Analysis Services], custom member formulas
- member formulas [Analysis Services]
- dimensions [Analysis Services], Business Intelligence enhancements
- custom member formulas [Analysis Services]
- CustomRollupColumn property
ms.assetid: c4467b08-ce59-4de7-a2d9-c22e246bdd52
author: minewiskan
ms.author: owend
ms.openlocfilehash: 112f8944bd20b2b6a464b0d84fb8ac1a0e89d976
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626367"
---
# <a name="set-custom-member-formulas-for-attributes-in-a-dimension"></a><span data-ttu-id="f854d-102">Impostare formule personalizzate membro per gli attributi in una dimensione</span><span class="sxs-lookup"><span data-stu-id="f854d-102">Set Custom Member Formulas for Attributes in a Dimension</span></span>
  <span data-ttu-id="f854d-103">L'aggiunta della funzionalità avanzata delle formule personalizzate membro a un cubo o a una dimensione consente di sostituire la funzione di aggregazione predefinita associata a un membro della dimensione con i risultati di un'espressione MDX (Multidimensional Expressions).</span><span class="sxs-lookup"><span data-stu-id="f854d-103">Add a custom member formula enhancement to a cube or dimension to replace the default aggregation that is associated with a dimension member with the results of a Multidimensional Expressions (MDX) expression.</span></span> <span data-ttu-id="f854d-104">Questa funzionalità avanzata imposta la proprietà `CustomRollupColumn` di un attributo specifico in una dimensione.</span><span class="sxs-lookup"><span data-stu-id="f854d-104">(This enhancement sets the `CustomRollupColumn` property on a specified attribute in a dimension.)</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f854d-105">Una formula personalizzata membro è disponibile solo per le dimensioni basate su origini dei dati esistenti.</span><span class="sxs-lookup"><span data-stu-id="f854d-105">A custom member formula is available only for dimensions that are based on existing data sources.</span></span> <span data-ttu-id="f854d-106">Per le dimensioni create senza l'utilizzo di un'origine dei dati è necessario eseguire Generazione guidata schema per creare una vista origine dati prima di aggiungere una formula personalizzata membro.</span><span class="sxs-lookup"><span data-stu-id="f854d-106">For dimensions that were created without using a data source, you must run the Schema Generation Wizard to create a data source view before adding a custom member formula.</span></span>  
  
 <span data-ttu-id="f854d-107">Per aggiungere una formula personalizzata membro, usare Configurazione guidata funzionalità di Business Intelligence e selezionare l'opzione **Creazione formula personalizzata membro** nella pagina **Scelta funzionalità avanzata** .</span><span class="sxs-lookup"><span data-stu-id="f854d-107">To add a custom member formula, you use the Business Intelligence Wizard, and select the **Create a custom member formula** option on the **Choose Enhancement** page.</span></span> <span data-ttu-id="f854d-108">Questa procedura guidata consente di eseguire in modo semplificato i passaggi relativi alla selezione di una dimensione alla quale si desidera applicare una formula personalizzata membro e all'abilitazione della formula personalizzata membro specifica.</span><span class="sxs-lookup"><span data-stu-id="f854d-108">This wizard then guides you through the steps of selecting a dimension to which you want to apply a custom member formula and enabling the custom member formula.</span></span>  
  
## <a name="selecting-a-dimension"></a><span data-ttu-id="f854d-109">Selezione di una dimensione</span><span class="sxs-lookup"><span data-stu-id="f854d-109">Selecting a Dimension</span></span>  
 <span data-ttu-id="f854d-110">Nella prima pagina **Creazione formula personalizzata membro** della procedura guidata specificare la dimensione alla quale applicare una formula personalizzata membro.</span><span class="sxs-lookup"><span data-stu-id="f854d-110">On the first **Create a Custom Member Formula** page of the wizard, you specify the dimension to which you want to apply a custom member formula.</span></span> <span data-ttu-id="f854d-111">L'aggiunta della funzionalità avanzata della formula personalizzata membro alla dimensione selezionata implica modifiche alla dimensione.</span><span class="sxs-lookup"><span data-stu-id="f854d-111">The custom member formula enhancement added to this selected dimension will result in changes to the dimension.</span></span> <span data-ttu-id="f854d-112">Tali modifiche verranno ereditate da tutti i cubi che includono la dimensione selezionata.</span><span class="sxs-lookup"><span data-stu-id="f854d-112">These changes will be inherited by all cubes that include the selected dimension.</span></span>  
  
## <a name="enabling-a-custom-member-formula"></a><span data-ttu-id="f854d-113">Abilitazione di una formula personalizzata membro</span><span class="sxs-lookup"><span data-stu-id="f854d-113">Enabling a Custom Member Formula</span></span>  
 <span data-ttu-id="f854d-114">Nella seconda pagina **Creazione formula personalizzata membro** associare la colonna di origine contenente la formula personalizzata membro a uno o più attributi nella dimensione.</span><span class="sxs-lookup"><span data-stu-id="f854d-114">On the second **Create a Custom Member Formula** page, you associate the source column that contains the custom member formula with one or more attributes in the dimension.</span></span> <span data-ttu-id="f854d-115">Nella colonna **Attributo** selezionare la casella di controllo accanto all'attributo da associare alla colonna della formula personalizzata membro.</span><span class="sxs-lookup"><span data-stu-id="f854d-115">In the **Attribute** column, select the check box next to the attribute that you want to associate with the custom member formula column.</span></span> <span data-ttu-id="f854d-116">Dopo aver selezionato ogni attributo, viene visualizzata la finestra di dialogo **Seleziona colonna** .</span><span class="sxs-lookup"><span data-stu-id="f854d-116">After you select each attribute, the wizard displays the **Select a Column** dialog box.</span></span> <span data-ttu-id="f854d-117">In questa finestra di dialogo fare clic nella colonna della tabella della dimensione contenente la formula.</span><span class="sxs-lookup"><span data-stu-id="f854d-117">In this dialog box, click the column in the dimension table that contains the formula.</span></span> <span data-ttu-id="f854d-118">Se dopo aver chiuso la finestra di dialogo **Seleziona colonna** si desidera modificare una selezione, fare clic nella cella **Colonna di origine** da modificare e quindi sui puntini di sospensione (**...**) per visualizzare nuovamente la finestra di dialogo **Seleziona colonna** .</span><span class="sxs-lookup"><span data-stu-id="f854d-118">If you want to change a selection after you close the **Select a Column** dialog box, click the **Source Column** cell that you want to change, and then click the ellipsis (**...**) to open the **Select a Column** dialog box again.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f854d-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f854d-119">See Also</span></span>  
 [<span data-ttu-id="f854d-120">Utilizzare la Configurazione guidata funzionalità di Business Intelligence per migliorare le dimensioni</span><span class="sxs-lookup"><span data-stu-id="f854d-120">Use the Business Intelligence Wizard to Enhance Dimensions</span></span>](../use-the-business-intelligence-wizard-to-enhance-dimensions.md)  
  
  
