---
title: Finestra di dialogo Associazione oggetti | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql.asvs.dimensiondesigner.dbv.objectbinding.f1
helpviewer_keywords:
- Object Binding dialog box
ms.assetid: 2bb5ad7c-2962-4559-8c95-cf7148bd2e72
author: minewiskan
ms.author: owend
ms.openlocfilehash: a10c91e0222b826066aeede96aa665cc22540637
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630095"
---
# <a name="object-binding-dialog-box"></a><span data-ttu-id="52c83-102">Finestra di dialogo Associazione oggetto</span><span class="sxs-lookup"><span data-stu-id="52c83-102">Object Binding Dialog Box</span></span>
  <span data-ttu-id="52c83-103">Utilizzare la finestra di dialogo **Associazione oggetto** in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] per definire associazioni tra la proprietà di un oggetto [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] e una tabella o una colonna di una vista origine dati.</span><span class="sxs-lookup"><span data-stu-id="52c83-103">Use the **Object Binding** dialog box in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] to define bindings between the property of an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] object and a table or column in a data source view.</span></span> <span data-ttu-id="52c83-104">Per visualizzare la finestra di dialogo **Associazione oggetto** selezionare **(nuovo)** nell'elenco a discesa per il valore delle proprietà seguenti di un oggetto [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] nella finestra **Proprietà** di [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="52c83-104">You can display the **Object Binding** dialog box by selecting **(new)** from the drop-down list for the value of the following properties of an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] object in the **Properties** window of [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]:</span></span>  
  
-   <span data-ttu-id="52c83-105">NameColumn</span><span class="sxs-lookup"><span data-stu-id="52c83-105">NameColumn</span></span>  
  
-   <span data-ttu-id="52c83-106">ValueColumn</span><span class="sxs-lookup"><span data-stu-id="52c83-106">ValueColumn</span></span>  
  
-   <span data-ttu-id="52c83-107">CustomRollupColumn</span><span class="sxs-lookup"><span data-stu-id="52c83-107">CustomRollupColumn</span></span>  
  
-   <span data-ttu-id="52c83-108">CustomRollupPropertiesColumn</span><span class="sxs-lookup"><span data-stu-id="52c83-108">CustomRollupPropertiesColumn</span></span>  
  
-   <span data-ttu-id="52c83-109">UnaryOperatorColumn</span><span class="sxs-lookup"><span data-stu-id="52c83-109">UnaryOperatorColumn</span></span>  
  
## <a name="options"></a><span data-ttu-id="52c83-110">Opzioni</span><span class="sxs-lookup"><span data-stu-id="52c83-110">Options</span></span>  
 <span data-ttu-id="52c83-111">**Tipo di binding**</span><span class="sxs-lookup"><span data-stu-id="52c83-111">**Binding type**</span></span>  
 <span data-ttu-id="52c83-112">Consente di selezionare l'associazione da utilizzare per l'oggetto [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="52c83-112">Select the binding to use for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] object.</span></span> <span data-ttu-id="52c83-113">È possibile utilizzare i tipi di associazione seguenti:</span><span class="sxs-lookup"><span data-stu-id="52c83-113">The following types of binding can be used:</span></span>  
  
 <span data-ttu-id="52c83-114">Associazione colonna</span><span class="sxs-lookup"><span data-stu-id="52c83-114">Column binding</span></span>  
 <span data-ttu-id="52c83-115">Consente di associare l'oggetto a una tabella e a una colonna esistenti in una vista origine dati.</span><span class="sxs-lookup"><span data-stu-id="52c83-115">Binds the object to an existing table and column within a data source view.</span></span>  
  
 <span data-ttu-id="52c83-116">Genera colonna</span><span class="sxs-lookup"><span data-stu-id="52c83-116">Generate column</span></span>  
 <span data-ttu-id="52c83-117">Consente di indicare che è necessario definire una nuova colonna nella vista origine dati. Su tale colonna verrà quindi eseguita un'associazione colonna.</span><span class="sxs-lookup"><span data-stu-id="52c83-117">Indicates that a new column is to be defined in the data source view, and a column binding is then associated with it.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="52c83-118">Se questa opzione è selezionata è necessario eseguire la **Generazione guidata schema** prima di distribuire l'oggetto [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="52c83-118">If this option is selected, you must run the **Schema Generation Wizard** before deploying the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] object.</span></span>  
  
 <span data-ttu-id="52c83-119">Associazione righe</span><span class="sxs-lookup"><span data-stu-id="52c83-119">Row binding</span></span>  
 <span data-ttu-id="52c83-120">Consente di associare l'oggetto a una riga in una tabella dei fatti, in modo da semplificare le misure Distinct Count in base al numero di righe elaborate nella tabella dei fatti.</span><span class="sxs-lookup"><span data-stu-id="52c83-120">Binds the object to a row in a fact table and is used to facilitate count measures based on the number of rows processed in the fact table.</span></span>  
  
 <span data-ttu-id="52c83-121">**Tabella di origine**</span><span class="sxs-lookup"><span data-stu-id="52c83-121">**Source table**</span></span>  
 <span data-ttu-id="52c83-122">Consente di visualizzare un elenco di tabelle nella vista origine dati associate all'oggetto [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="52c83-122">Displays a list of tables in the data source view associated with the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] object.</span></span>  
  
 <span data-ttu-id="52c83-123">**Colonna di origine**</span><span class="sxs-lookup"><span data-stu-id="52c83-123">**Source column**</span></span>  
 <span data-ttu-id="52c83-124">Consente di visualizzare un elenco di colonne nella tabella selezionata in **Tabella di origine**.</span><span class="sxs-lookup"><span data-stu-id="52c83-124">Displays a list of columns in the table selected in **Source table**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52c83-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="52c83-125">See Also</span></span>  
 [<span data-ttu-id="52c83-126">Finestre di progettazione e finestre di dialogo Analysis Services &#40;dati multidimensionali&#41;</span><span class="sxs-lookup"><span data-stu-id="52c83-126">Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;</span></span>](analysis-services-designers-and-dialog-boxes-multidimensional-data.md)  
  
  
