---
title: Finestra di dialogo Modello denominazione livelli (Analysis Services-Dati multidimensionali) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.levelnamingtemplatedialog.f1
helpviewer_keywords:
- Level Naming Template dialog box
ms.assetid: 96cad715-213e-4eac-9003-130a2f5fc985
author: minewiskan
ms.author: owend
ms.openlocfilehash: 4dd704e619e49f0dd1adb8fed8f1e743b61309af
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727255"
---
# <a name="level-naming-template-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="bee5e-102">Finestra di dialogo Modello denominazione livelli (Analysis Services - Dati multidimensionali)</span><span class="sxs-lookup"><span data-stu-id="bee5e-102">Level Naming Template Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="bee5e-103">Usare la finestra di dialogo **Modello denominazione livelli** in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] per creare il modello di denominazione dei livelli per un attributo padre in una dimensione.</span><span class="sxs-lookup"><span data-stu-id="bee5e-103">Use the **Level Naming Template** dialog box in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] to construct the level naming template for a parent attribute in a dimension.</span></span> <span data-ttu-id="bee5e-104">Per altre informazioni sui modelli di denominazione dei livelli, vedere [Elemento NamingTemplate &#40;ASSL&#41;](https://docs.microsoft.com/bi-reference/assl/properties/namingtemplate-element-assl).</span><span class="sxs-lookup"><span data-stu-id="bee5e-104">For more information about level naming templates, see [NamingTemplate Element &#40;ASSL&#41;](https://docs.microsoft.com/bi-reference/assl/properties/namingtemplate-element-assl).</span></span> <span data-ttu-id="bee5e-105">Per visualizzare la finestra di dialogo **Modello denominazione livelli** è possibile fare clic sul pulsante con i puntini di sospensione (**...**) sul `NamingTemplate` valore di una traduzione per un attributo nel riquadro **Dettagli traduzione** della scheda **traduzioni** di **Progettazione dimensioni**.</span><span class="sxs-lookup"><span data-stu-id="bee5e-105">You can display the **Level Naming Template** dialog box by clicking the ellipsis button (**...**) on the `NamingTemplate` value of a translation for an attribute in the **Translation Details** pane on the **Translations** tab of **Dimension Designer**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="bee5e-106">Opzioni</span><span class="sxs-lookup"><span data-stu-id="bee5e-106">Options</span></span>  
  
|<span data-ttu-id="bee5e-107">Termine</span><span class="sxs-lookup"><span data-stu-id="bee5e-107">Term</span></span>|<span data-ttu-id="bee5e-108">Definizione</span><span class="sxs-lookup"><span data-stu-id="bee5e-108">Definition</span></span>|  
|----------|----------------|  
|<span data-ttu-id="bee5e-109">**Definire il modello di livello**</span><span class="sxs-lookup"><span data-stu-id="bee5e-109">**Define the level template**</span></span>|<span data-ttu-id="bee5e-110">Consente di visualizzare una griglia in cui è possibile progettare la gerarchia di livelli nell'attributo padre.</span><span class="sxs-lookup"><span data-stu-id="bee5e-110">Displays a grid in which you can design the hierarchy of levels in the parent attribute.</span></span> <span data-ttu-id="bee5e-111">La griglia include le colonne seguenti:</span><span class="sxs-lookup"><span data-stu-id="bee5e-111">The grid contains the following columns:</span></span><br /><br /> <span data-ttu-id="bee5e-112">**Level**: Visualizza la posizione ordinale del livello per il quale viene usato il nome specificato in **nome** .</span><span class="sxs-lookup"><span data-stu-id="bee5e-112">**Level**: Displays the ordinal position of the level for which the name specified in **Name** is used.</span></span> <span data-ttu-id="bee5e-113">Per aggiungere un nuovo modello di denominazione per un livello, selezionare **Nome** nella riga contenente un asterisco (\*) in **Livello**.</span><span class="sxs-lookup"><span data-stu-id="bee5e-113">To add a new naming template for a level, select **Name** on the row that contains an asterisk (\*) in **Level**.</span></span><br /><br /> <span data-ttu-id="bee5e-114">**Nome**: contiene il modello di denominazione utilizzato per il livello indicato in **Level**.</span><span class="sxs-lookup"><span data-stu-id="bee5e-114">**Name**: Contains the naming template used for the level indicated in **Level**.</span></span> <span data-ttu-id="bee5e-115">Per aggiungere un segnaposto per la posizione ordinale del livello nel modello di denominazione, aggiungere un asterisco (\*).</span><span class="sxs-lookup"><span data-stu-id="bee5e-115">To add a placeholder for the level ordinal position in the naming template, add a single asterisk (\*).</span></span> <span data-ttu-id="bee5e-116">Per aggiungere un asterisco come parte del nome creato dal modello di denominazione, aggiungere due asterischi ( \* \* ).</span><span class="sxs-lookup"><span data-stu-id="bee5e-116">To add an asterisk as part of the name created by the naming template, add two asterisks (\*\*).</span></span>|  
|<span data-ttu-id="bee5e-117">**Cancella tutto**</span><span class="sxs-lookup"><span data-stu-id="bee5e-117">**Clear All**</span></span>|<span data-ttu-id="bee5e-118">Selezionare questa opzione per rimuovere tutte le righe in **Definire il modello di livello**.</span><span class="sxs-lookup"><span data-stu-id="bee5e-118">Select to remove all rows in **Define the level template**.</span></span>|  
|<span data-ttu-id="bee5e-119">**Risultato**</span><span class="sxs-lookup"><span data-stu-id="bee5e-119">**Result**</span></span>|<span data-ttu-id="bee5e-120">Consente di visualizzare il modello di denominazione dei livelli creato nella finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="bee5e-120">Displays the level naming template constructed by the dialog box.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bee5e-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bee5e-121">See Also</span></span>  
 <span data-ttu-id="bee5e-122">[Finestre di progettazione e finestre di dialogo Analysis Services &#40;dati multidimensionali&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="bee5e-122">[Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="bee5e-123">Traduzioni &#40;Progettazione dimensioni&#41; &#40;Analysis Services Dati multidimensionali&#41;</span><span class="sxs-lookup"><span data-stu-id="bee5e-123">Translations &#40;Dimension Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;</span></span>](translations-dimension-designer-analysis-services-multidimensional-data.md)  
  
  
