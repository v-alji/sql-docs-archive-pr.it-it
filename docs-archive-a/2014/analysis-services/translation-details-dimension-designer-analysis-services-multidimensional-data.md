---
title: Dettagli traduzione (scheda Traduzioni, Progettazione dimensioni) (Analysis Services-Dati multidimensionali) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.dimensiondesigner.translations.translationpane.tranlationdetails.f1
ms.assetid: 0aa61df3-f2b0-4703-a63b-124da672dcc3
author: minewiskan
ms.author: owend
ms.openlocfilehash: a7cbe4a3c69111d0f82f96ff5125f80fe0c2c57f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723075"
---
# <a name="translation-details-translations-tab-dimension-designer-analysis-services---multidimensional-data"></a><span data-ttu-id="4869b-102">Dettagli di traduzione (Scheda traduzione, Progettazione dimensioni) (Analysis Services –Dati multidimensionali)</span><span class="sxs-lookup"><span data-stu-id="4869b-102">Translation Details (Translations Tab, Dimension Designer) (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="4869b-103">Usare il pannello **Dettagli di traduzione** nella scheda **Traduzioni** di Progettazione dimensioni per definire e gestire le traduzioni relative alla dimensione attualmente selezionata.</span><span class="sxs-lookup"><span data-stu-id="4869b-103">Use the **Translation Details** pane on the **Translations** tab of Dimension Designer to define and manage translations for the currently selected dimension.</span></span>  
  
 <span data-ttu-id="4869b-104">**Per visualizzare il riquadro Dettagli di traduzione**</span><span class="sxs-lookup"><span data-stu-id="4869b-104">**To display the Translations Details pane**</span></span>  
  
1.  <span data-ttu-id="4869b-105">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]aprire il progetto [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , quindi aprire la dimensione che si desidera utilizzare.</span><span class="sxs-lookup"><span data-stu-id="4869b-105">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project, and then open the dimension that you want.</span></span>  
  
2.  <span data-ttu-id="4869b-106">Fare clic sulla scheda **Traduzioni** .</span><span class="sxs-lookup"><span data-stu-id="4869b-106">Click the **Translations** tab.</span></span>  
  
## <a name="options"></a><span data-ttu-id="4869b-107">Opzioni</span><span class="sxs-lookup"><span data-stu-id="4869b-107">Options</span></span>  
 <span data-ttu-id="4869b-108">**Lingua predefinita**</span><span class="sxs-lookup"><span data-stu-id="4869b-108">**Default Language**</span></span>  
 <span data-ttu-id="4869b-109">Consente di impostare i nomi degli oggetti dimensione nella lingua predefinita.</span><span class="sxs-lookup"><span data-stu-id="4869b-109">Sets the names of the dimension objects in the default language.</span></span>  
  
 <span data-ttu-id="4869b-110">**Tipo oggetto**</span><span class="sxs-lookup"><span data-stu-id="4869b-110">**Object Type**</span></span>  
 <span data-ttu-id="4869b-111">Consente di visualizzare la proprietà che verrà tradotta.</span><span class="sxs-lookup"><span data-stu-id="4869b-111">Displays the property that will be translated.</span></span> <span data-ttu-id="4869b-112">Possono essere tradotti soltanto oggetti e proprietà di cui sono stati specificati i valori.</span><span class="sxs-lookup"><span data-stu-id="4869b-112">Only objects and properties for which values have been specified can be translated.</span></span> <span data-ttu-id="4869b-113">È possibile tradurre le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="4869b-113">The following properties can be translated:</span></span>  
  
-   <span data-ttu-id="4869b-114">Dimension</span><span class="sxs-lookup"><span data-stu-id="4869b-114">Dimension</span></span>  
  
     <span data-ttu-id="4869b-115">Proprietà `Caption` e `AttributeAllMember`</span><span class="sxs-lookup"><span data-stu-id="4869b-115">`Caption` and `AttributeAllMember` properties</span></span>  
  
-   <span data-ttu-id="4869b-116">Attributo</span><span class="sxs-lookup"><span data-stu-id="4869b-116">Attribute</span></span>  
  
     <span data-ttu-id="4869b-117">Proprietà `Caption`, `AttributeHierarchyDisplayFolder` e `NamingTemplate`.</span><span class="sxs-lookup"><span data-stu-id="4869b-117">`Caption`, `AttributeHierarchyDisplayFolder`, and `NamingTemplate` properties</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4869b-118">La proprietà `NamingTemplate` è disponibile solo per gli attributi padre.</span><span class="sxs-lookup"><span data-stu-id="4869b-118">The `NamingTemplate` property is available only for parent attributes.</span></span>  
  
-   <span data-ttu-id="4869b-119">Gerarchia</span><span class="sxs-lookup"><span data-stu-id="4869b-119">Hierarchy</span></span>  
  
     <span data-ttu-id="4869b-120">Proprietà `Caption` e `AllMemberName`</span><span class="sxs-lookup"><span data-stu-id="4869b-120">`Caption` and `AllMemberName` properties</span></span>  
  
-   <span data-ttu-id="4869b-121">Level</span><span class="sxs-lookup"><span data-stu-id="4869b-121">Level</span></span>  
  
     <span data-ttu-id="4869b-122">Proprietà `Caption`</span><span class="sxs-lookup"><span data-stu-id="4869b-122">`Caption` property</span></span>  
  
 **\<Language>**  
 <span data-ttu-id="4869b-123">Consente di digitare o selezionare il valore della proprietà dell'oggetto dimensione nella lingua selezionata.</span><span class="sxs-lookup"><span data-stu-id="4869b-123">Type or select the property value of the dimension object in the selected language.</span></span> <span data-ttu-id="4869b-124">Fare clic sul pulsante con i puntini di sospensione (**...**) per visualizzare altre finestre di dialogo, a seconda della proprietà che si sta modificando:</span><span class="sxs-lookup"><span data-stu-id="4869b-124">Clicking the ellipsis button (**...**) opens additional dialog boxes, depending on the property being edited:</span></span>  
  
-   <span data-ttu-id="4869b-125">Proprietà `NamingTemplate`</span><span class="sxs-lookup"><span data-stu-id="4869b-125">`NamingTemplate` property</span></span>  
  
     <span data-ttu-id="4869b-126">Consente di visualizzare la [Finestra di dialogo Modello denominazione livelli &#40;Analysis Services - Dati multidimensionali&#41;](level-naming-template-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="4869b-126">Displays the [Level Naming Template Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](level-naming-template-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
-   <span data-ttu-id="4869b-127">Proprietà `Caption` (per attributi)</span><span class="sxs-lookup"><span data-stu-id="4869b-127">`Caption` property (for attributes)</span></span>  
  
     <span data-ttu-id="4869b-128">Consente di visualizzare la [Finestra di dialogo Traduzione dati attributo &#40;Analysis Services - Dati multidimensionali&#41;](attribute-data-translation-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="4869b-128">Displays the [Attribute Data Translation Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](attribute-data-translation-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
## <a name="shortcut-menu"></a><span data-ttu-id="4869b-129">Menu di scelta rapida</span><span class="sxs-lookup"><span data-stu-id="4869b-129">Shortcut Menu</span></span>  
 <span data-ttu-id="4869b-130">Se si fa clic con il pulsante destro del mouse su una traduzione nel riquadro **Dettagli di traduzione** , verrà visualizzato un menu di scelta rapida in cui sono disponibili le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="4869b-130">The following options are available in the shortcut menu displayed by right-clicking a translation in the **Translation Details** pane:</span></span>  
  
 <span data-ttu-id="4869b-131">**Nuova traduzione**</span><span class="sxs-lookup"><span data-stu-id="4869b-131">**New Translation**</span></span>  
 <span data-ttu-id="4869b-132">Selezionare questa opzione per visualizzare la finestra di dialogo **Seleziona lingua** e creare una nuova traduzione.</span><span class="sxs-lookup"><span data-stu-id="4869b-132">Select to display the **Select Language** dialog box and create a new translation.</span></span> <span data-ttu-id="4869b-133">La traduzione verrà visualizzata sotto forma di nuova colonna all'interno della griglia **Dettagli di traduzione** .</span><span class="sxs-lookup"><span data-stu-id="4869b-133">The translation will appear as a new column in the **Translation Details** grid.</span></span>  
  
 <span data-ttu-id="4869b-134">**Elimina traduzione**</span><span class="sxs-lookup"><span data-stu-id="4869b-134">**Delete Translation**</span></span>  
 <span data-ttu-id="4869b-135">Selezionare questa opzione per eliminare la traduzione selezionata.</span><span class="sxs-lookup"><span data-stu-id="4869b-135">Select to delete the selected translation.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4869b-136">Questa opzione è attivata solo se si fa clic con il pulsate destro del mouse su una cella per eliminare la traduzione.</span><span class="sxs-lookup"><span data-stu-id="4869b-136">The option is enabled only if you right-clicked a cell to delete the translation.</span></span>  
  
 <span data-ttu-id="4869b-137">**Nuova colonna didascalia**</span><span class="sxs-lookup"><span data-stu-id="4869b-137">**New Caption Column**</span></span>  
 <span data-ttu-id="4869b-138">Selezionare questa opzione per visualizzare la finestra di dialogo **Traduzione dati attributo** e definire una nuova colonna di didascalia durante la modifica di un attributo nella griglia **Dettagli di traduzione** .</span><span class="sxs-lookup"><span data-stu-id="4869b-138">Select to display the **Attribute Data Translation** dialog box and define a new caption column when you modify an attribute in the **Translation Details** grid.</span></span> <span data-ttu-id="4869b-139">Per abilitare questa opzione, è necessario selezionare una cella di una colonna per la traduzione relativa a un attributo nella griglia dettagli traduzione. \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="4869b-139">To enable this option, a cell in a translation column for an attribute must be selected in the **Translation Details** grid.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4869b-140">Questa opzione è attivata solo se si fa clic con il pulsante destro del mouse su una cella per eliminare la colonna per la traduzione di un attributo.</span><span class="sxs-lookup"><span data-stu-id="4869b-140">The option is enabled only if you right-clicked a cell to delete the translation column of an attribute.</span></span>  
  
 <span data-ttu-id="4869b-141">**Modifica colonna didascalia**</span><span class="sxs-lookup"><span data-stu-id="4869b-141">**Edit Caption Column**</span></span>  
 <span data-ttu-id="4869b-142">Selezionare per visualizzare la finestra di dialogo **Traduzione dati attributo** e per modificare una colonna di didascalia già esistente durante la modifica di un attributo nella griglia **Dettagli di traduzione** .</span><span class="sxs-lookup"><span data-stu-id="4869b-142">Select to display the **Attribute Data Translation** dialog box and modify an existing caption column when you modify an attribute in the **Translation Details** grid.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4869b-143"> Questa opzione è abilitata solo se nella griglia dei dettagli traduzione è selezionata una cella di una colonna per la traduzione contenente una colonna didascalia per un attributo.\ \*\*\**</span><span class="sxs-lookup"><span data-stu-id="4869b-143">The option is enabled only if a cell in a translation column that contains a caption column for an attribute must be selected in the **Translation Details** grid.</span></span>  
  
 <span data-ttu-id="4869b-144">**Elimina colonna didascalia**</span><span class="sxs-lookup"><span data-stu-id="4869b-144">**Delete Caption Column**</span></span>  
 <span data-ttu-id="4869b-145">Selezionare questa opzione per eliminare la colonna di didascalia per l'attributo selezionato nella griglia **Dettagli di traduzione** .</span><span class="sxs-lookup"><span data-stu-id="4869b-145">Select to delete the caption column for the selected attribute in the **Translation Details** grid.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4869b-146">Questa opzione è attivata solo se si fa clic con il pulsante destro del mouse su una cella di una colonna per la traduzione contenente una colonna didascalia per un attributo.</span><span class="sxs-lookup"><span data-stu-id="4869b-146">The option is enabled only if you right-clicked a cell in a translation column that contains a caption column for an attribute.</span></span>  
  
 <span data-ttu-id="4869b-147">**Mostra tutti gli attributi**</span><span class="sxs-lookup"><span data-stu-id="4869b-147">**Show All Attributes**</span></span>  
 <span data-ttu-id="4869b-148">Selezionare o deselezionare questa opzione per attivare o disabilitare la visualizzazione di tutti gli attributi definiti per la dimensione selezionata, inclusi gli attributi per i quali le gerarchie sono disattivate.</span><span class="sxs-lookup"><span data-stu-id="4869b-148">Select to toggle the display of all attributes defined for the selected dimension, including attributes for which attribute hierarchies are disabled.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4869b-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4869b-149">See Also</span></span>  
 [<span data-ttu-id="4869b-150">Traduzioni &#40;Progettazione dimensioni&#41; &#40;Analysis Services Dati multidimensionali&#41;</span><span class="sxs-lookup"><span data-stu-id="4869b-150">Translations &#40;Dimension Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;</span></span>](translations-dimension-designer-analysis-services-multidimensional-data.md)  
  
  
