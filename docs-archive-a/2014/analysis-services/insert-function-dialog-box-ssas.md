---
title: Finestra di dialogo Inserisci funzione (SSAS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- SQL12.ASVS.BIDTOOLSET.INSERTFUNCTIONDB.F1
ms.assetid: c4b36d8f-2328-45f7-8bd4-cc0111571e25
author: minewiskan
ms.author: owend
ms.openlocfilehash: 0d92dd34e671dc026215d79e7eaed88bebfac15f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629106"
---
# <a name="insert-function-dialog-box-ssas"></a><span data-ttu-id="4cfb0-102">Finestra di dialogo Inserisci funzione (SSAS)</span><span class="sxs-lookup"><span data-stu-id="4cfb0-102">Insert Function Dialog Box (SSAS)</span></span>
  <span data-ttu-id="4cfb0-103">La finestra di dialogo **Inserisci funzione** consente di scegliere da un elenco di funzioni utilizzabili quando si compilano formule.</span><span class="sxs-lookup"><span data-stu-id="4cfb0-103">The **Insert Function** dialog box enables you to choose from a list of functions that can be used when building formulas.</span></span> <span data-ttu-id="4cfb0-104">Per accedere a questa finestra di dialogo da Progettazione modelli, nella barra della formula sopra ogni tabella fare clic sul pulsante della funzione (**fx**).</span><span class="sxs-lookup"><span data-stu-id="4cfb0-104">To access this dialog box from the model designer, in the formula bar above each table, click the function (**fx**) button.</span></span> <span data-ttu-id="4cfb0-105">Per ulteriori informazioni sulla scelta di funzioni da utilizzare nelle formule, vedere le sezioni relative all'introduzione a DAX e alla compilazione di una formula.</span><span class="sxs-lookup"><span data-stu-id="4cfb0-105">For more information about choosing functions to use in formulas, see DAX Introduction and Build a Formula.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4cfb0-106">Elemento</span><span class="sxs-lookup"><span data-stu-id="4cfb0-106">Item</span></span>|<span data-ttu-id="4cfb0-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4cfb0-107">Description</span></span>|  
|<span data-ttu-id="4cfb0-108">**Seleziona una categoria**</span><span class="sxs-lookup"><span data-stu-id="4cfb0-108">**Select a category**</span></span>|<span data-ttu-id="4cfb0-109">Se si conosce a grandi linee il tipo di funzione necessario, scegliere una categoria dall'elenco o selezionare **Tutte** per visualizzare un elenco di funzioni in ordine alfabetico.</span><span class="sxs-lookup"><span data-stu-id="4cfb0-109">If you have a general idea which kind of function you need, choose a category from the list; or select **All** to view an alphabetical list of functions.</span></span>|  
|<span data-ttu-id="4cfb0-110">**Selezionare una funzione**</span><span class="sxs-lookup"><span data-stu-id="4cfb0-110">**Select a function**</span></span>|<span data-ttu-id="4cfb0-111">Consente di visualizzare un elenco delle funzioni nella categoria selezionata.</span><span class="sxs-lookup"><span data-stu-id="4cfb0-111">Displays a list of the functions in the selected category.</span></span>|  
|<span data-ttu-id="4cfb0-112">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="4cfb0-112">**Description**</span></span>|<span data-ttu-id="4cfb0-113">Consente di visualizzare una descrizione della funzione, insieme a tutti gli argomenti richiesti o facoltativi, ad esempio nomi di colonne ed espressioni.</span><span class="sxs-lookup"><span data-stu-id="4cfb0-113">Displays a description of what the function does, together with any required or optional arguments, such as column names and expressions.</span></span>|  
  
## <a name="function-categories"></a><span data-ttu-id="4cfb0-114">Categorie delle funzioni</span><span class="sxs-lookup"><span data-stu-id="4cfb0-114">Function Categories</span></span>  
 <span data-ttu-id="4cfb0-115">DAX (Data Analysis Expressions) offre i tipi di categorie di funzioni seguenti nella finestra di dialogo **Inserisci funzione** .</span><span class="sxs-lookup"><span data-stu-id="4cfb0-115">Data Analysis Expressions (DAX) provides the following types of function categories in the **Insert Functions** dialog box.</span></span>  
  
 <span data-ttu-id="4cfb0-116">Tutti</span><span class="sxs-lookup"><span data-stu-id="4cfb0-116">All</span></span>  
  
 <span data-ttu-id="4cfb0-117">Data e ora</span><span class="sxs-lookup"><span data-stu-id="4cfb0-117">Date & Time</span></span>  
  
 <span data-ttu-id="4cfb0-118">Filtro</span><span class="sxs-lookup"><span data-stu-id="4cfb0-118">Filter</span></span>  
  
 <span data-ttu-id="4cfb0-119">Logico</span><span class="sxs-lookup"><span data-stu-id="4cfb0-119">Logical</span></span>  
  
 <span data-ttu-id="4cfb0-120">Matematiche e trig</span><span class="sxs-lookup"><span data-stu-id="4cfb0-120">Math & Trig</span></span>  
  
 <span data-ttu-id="4cfb0-121">Statistica</span><span class="sxs-lookup"><span data-stu-id="4cfb0-121">Statistical</span></span>  
  
 <span data-ttu-id="4cfb0-122">Testo</span><span class="sxs-lookup"><span data-stu-id="4cfb0-122">Text</span></span>  
  
## <a name="measures-and-formulas"></a><span data-ttu-id="4cfb0-123">Misure e formule</span><span class="sxs-lookup"><span data-stu-id="4cfb0-123">Measures and Formulas</span></span>  
 <span data-ttu-id="4cfb0-124">La finestra di dialogo **Inserisci funzione** è disponibile solo quando si compila una formula.</span><span class="sxs-lookup"><span data-stu-id="4cfb0-124">The **Insert Function** dialog box is available only when you are building a formula.</span></span> <span data-ttu-id="4cfb0-125">È possibile creare i calcoli in una colonna calcolata o in una tabella o grafico pivot.</span><span class="sxs-lookup"><span data-stu-id="4cfb0-125">You can create calculations either in a calculated column, or in a PivotTable or PivotChart.</span></span> <span data-ttu-id="4cfb0-126">Le formule compilate espressamente per essere usate in una tabella pivot vengono chiamate anche *misure*.</span><span class="sxs-lookup"><span data-stu-id="4cfb0-126">Formulas that you build expressly for use in a PivotTable are also called *measures*.</span></span> <span data-ttu-id="4cfb0-127">Per altre informazioni, vedere [Creare una colonna calcolata &#40;SSAS tabulare&#41;](tabular-models/ssas-calculated-columns-create-a-calculated-column.md), [Creare e gestire misure &#40;SSAS tabulare&#41;](tabular-models/measures-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="4cfb0-127">For more information, see [Create a Calculated Column &#40;SSAS Tabular&#41;](tabular-models/ssas-calculated-columns-create-a-calculated-column.md) and [Create and Manage Measures &#40;SSAS Tabular&#41;](tabular-models/measures-ssas-tabular.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4cfb0-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4cfb0-128">See Also</span></span>  
 [<span data-ttu-id="4cfb0-129">Calcoli &#40;SSAS tabulare&#41;</span><span class="sxs-lookup"><span data-stu-id="4cfb0-129">Calculations &#40;SSAS Tabular&#41;</span></span>](tabular-models/calculations-ssas-tabular.md)  
  
  
