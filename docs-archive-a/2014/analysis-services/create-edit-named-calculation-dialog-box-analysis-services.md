---
title: Finestra di dialogo Crea calcolo denominato (Analysis Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.dsveditor.createnamedcalculation.f1
helpviewer_keywords:
- Named Calculation dialog box
ms.assetid: 66fb30ae-f5c5-4bfc-80ca-8c8a3a9bb30d
author: minewiskan
ms.author: owend
ms.openlocfilehash: 0b6777feb47a1ce6b601d0190e413b4baae35f1f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623611"
---
# <a name="create-edit-named-calculation-dialog-box-analysis-services"></a><span data-ttu-id="3e2df-102">Finestra di dialogo Crea calcolo denominato (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="3e2df-102">Create-Edit Named Calculation Dialog Box (Analysis Services)</span></span>
  <span data-ttu-id="3e2df-103">Usare la finestra di dialogo **Crea calcolo denominato o Modifica calcolo denominato** in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] per definire o modificare un calcolo denominato per una tabella in una vista origine dati.</span><span class="sxs-lookup"><span data-stu-id="3e2df-103">Use the **Create/Edit Named Calculation** dialog box in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] to define or modify a named calculation for a table in a data source view.</span></span> <span data-ttu-id="3e2df-104">Per visualizzare la finestra di dialogo **Crea calcolo denominato o Modifica calcolo denominato** è possibile:</span><span class="sxs-lookup"><span data-stu-id="3e2df-104">You can display the **Create/Edit Named Calculation** dialog box by:</span></span>  
  
-   <span data-ttu-id="3e2df-105">Fare clic su **Nuovo calcolo denominato** nel riquadro **Barra degli strumenti** di **Progettazione Vista origine dati**.</span><span class="sxs-lookup"><span data-stu-id="3e2df-105">Clicking **New Named Calculation** in the **Toolbar** pane of **Data Source View Designer**.</span></span>  
  
-   <span data-ttu-id="3e2df-106">Fare clic con il pulsante destro del mouse su una tabella nel riquadro **Tabelle** o **Diagramma**di **Progettazione vista origine dati** e scegliere **Nuovo calcolo denominato**.</span><span class="sxs-lookup"><span data-stu-id="3e2df-106">Right-clicking a table in either the **Tables** or **Diagram** pane of **Data Source View Designer** and selecting **New Named Calculation**.</span></span>  
  
-   <span data-ttu-id="3e2df-107">Fare clic con il pulsante destro del mouse sul nome di un calcolo denominato nel riquadro **Diagramma** di **Progettazione vista origine dati** e scegliere **Modifica calcolo denominato**.</span><span class="sxs-lookup"><span data-stu-id="3e2df-107">Right-clicking the name of a named calculation in the **Diagram** pane of **Data Source View Designer** and selecting **Edit Named Calculation**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="3e2df-108">Opzioni</span><span class="sxs-lookup"><span data-stu-id="3e2df-108">Options</span></span>  
 <span data-ttu-id="3e2df-109">**Nome colonna**</span><span class="sxs-lookup"><span data-stu-id="3e2df-109">**Column Name**</span></span>  
 <span data-ttu-id="3e2df-110">Consente di digitare il nome del calcolo denominato.</span><span class="sxs-lookup"><span data-stu-id="3e2df-110">Type the name of the named calculation.</span></span>  
  
 <span data-ttu-id="3e2df-111">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="3e2df-111">**Description**</span></span>  
 <span data-ttu-id="3e2df-112">Consente di digitare la descrizione facoltativa del calcolo denominato.</span><span class="sxs-lookup"><span data-stu-id="3e2df-112">Type the optional description of the named calculation.</span></span>  
  
 <span data-ttu-id="3e2df-113">**Espressione**</span><span class="sxs-lookup"><span data-stu-id="3e2df-113">**Expression**</span></span>  
 <span data-ttu-id="3e2df-114">Consente di digitare un'espressione SQL valida che restituisce un valore scalare.</span><span class="sxs-lookup"><span data-stu-id="3e2df-114">Type a valid SQL expression that returns a scalar value.</span></span> <span data-ttu-id="3e2df-115">L'espressione viene inviata al provider e convalidata nell'espressione seguente:</span><span class="sxs-lookup"><span data-stu-id="3e2df-115">The expression is sent to the provider, and validated in the following expression:</span></span>  
  
```  
SELECT <Table Name in Data Source>.* , <Expression> AS <Column Name> FROM <Table Name in Data Source>AS <Table Name in Data Source View>  
```  
  
 <span data-ttu-id="3e2df-116">L'espressione può contenere riferimenti ad altre tabelle specificati mediante un'istruzione sub-SELECT.</span><span class="sxs-lookup"><span data-stu-id="3e2df-116">The expression can contain references to other tables, by means of a sub-select statement.</span></span> <span data-ttu-id="3e2df-117">If the expression would require parentheses in a SELECT statement, the expression entered must be enclosed between parentheses.</span><span class="sxs-lookup"><span data-stu-id="3e2df-117">If the expression would require parentheses in a SELECT statement, the expression entered must be enclosed between parentheses.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e2df-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3e2df-118">See Also</span></span>  
 <span data-ttu-id="3e2df-119">[Finestre di progettazione e finestre di dialogo Analysis Services &#40;dati multidimensionali&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="3e2df-119">[Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="3e2df-120">Progettazione vista origine dati &#40;Analysis Services - Dati multidimensionali&#41;</span><span class="sxs-lookup"><span data-stu-id="3e2df-120">Data Source View Designer &#40;Analysis Services - Multidimensional Data&#41;</span></span>](data-source-view-designer-analysis-services-multidimensional-data.md)  
  
  
