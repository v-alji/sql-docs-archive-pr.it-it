---
title: Finestra di dialogo Crea relazione o modifica relazione (Analysis Services-Dati multidimensionali) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.dsvdesigner.createrelationship.f1
helpviewer_keywords:
- Create Relationship dialog box
ms.assetid: da3c7074-623e-4ddf-a707-d3276a47cf1c
author: minewiskan
ms.author: owend
ms.openlocfilehash: 4edae3f78ac6b764d91e1be97787fe59d49421db
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626983"
---
# <a name="create-or-edit-relationship-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="3509c-102">Finestra di dialogo Crea relazione o Modifica relazione (Analysis Services - Dati multidimensionali)</span><span class="sxs-lookup"><span data-stu-id="3509c-102">Create or Edit Relationship Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="3509c-103">Usare la finestra di dialogo **Create/Edit Relationship** (Crea/Modifica relazione) in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] per definire o modificare una relazione in una vista origine dati.</span><span class="sxs-lookup"><span data-stu-id="3509c-103">Use the **Create/Edit Relationship** dialog box in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] to define or modify a relationship in a data source view.</span></span> <span data-ttu-id="3509c-104">È possibile visualizzare la finestra di dialogo **Create/Edit Relationship** (Crea/Modifica relazione) nei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="3509c-104">You can display the **Create/Edit Relationship** dialog box by:</span></span>  
  
-   <span data-ttu-id="3509c-105">Fare clic su **Nuova relazione** nel riquadro **Barra degli strumenti** di **Data Source View Designer**(Progettazione vista origine dati).</span><span class="sxs-lookup"><span data-stu-id="3509c-105">Clicking **New Relationship** in the **Toolbar** pane of **Data Source View Designer**.</span></span>  
  
-   <span data-ttu-id="3509c-106">Fare clic con il pulsante destro del mouse su una tabella nel riquadro **Tabelle** o nel riquadro **Diagramma** di **Data Source View Designer** (Progettazione vista origine dati) e selezionare **Nuova relazione**.</span><span class="sxs-lookup"><span data-stu-id="3509c-106">Right-clicking a table in either the **Tables** or **Diagram** pane of **Data Source View Designer** and selecting **New Relationship**.</span></span>  
  
-   <span data-ttu-id="3509c-107">Fare clic con il pulsante destro del mouse su una relazione nel riquadro **Diagramma** di **Data Source View Designer** (Progettazione vista origine dati) e selezionare **Modifica relazione**.</span><span class="sxs-lookup"><span data-stu-id="3509c-107">Right-clicking a relationship in the **Diagram** pane of **Data Source View Designer** and selecting **Edit Relationship**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3509c-108">In **Data Source View Designer** (Progettazione vista origine dati) è possibile creare relazioni che non esistono nell'origine dei dati sottostante e rimuovere le relazioni create tramite **Data Source View Designer** (Progettazione vista origine dati) dalle relazioni di chiave esterna esistenti nell'origine dei dati sottostante.</span><span class="sxs-lookup"><span data-stu-id="3509c-108">You can create relationships in **Data Source View Designer** that do not exist in the underlying data source, and remove relationships created by **Data Source View Designer** from existing foreign key relationships in the underlying data source.</span></span>  
  
## <a name="options"></a><span data-ttu-id="3509c-109">Opzioni</span><span class="sxs-lookup"><span data-stu-id="3509c-109">Options</span></span>  
 <span data-ttu-id="3509c-110">**Tabella di origine (chiave esterna)**</span><span class="sxs-lookup"><span data-stu-id="3509c-110">**Source (foreign key) table**</span></span>  
 <span data-ttu-id="3509c-111">Consente di selezionare la tabella o la query denominata contenente il riferimento a una o più colonne nella tabella di destinazione.</span><span class="sxs-lookup"><span data-stu-id="3509c-111">Select the table or named query that contains the reference to one or more columns in the destination table.</span></span>  
  
 <span data-ttu-id="3509c-112">**Tabella di destinazione (chiave primaria)**</span><span class="sxs-lookup"><span data-stu-id="3509c-112">**Destination (primary key) table**</span></span>  
 <span data-ttu-id="3509c-113">Consente di selezionare la tabella contenente una o più colonne a cui fa riferimento la tabella di origine.</span><span class="sxs-lookup"><span data-stu-id="3509c-113">Select the table that contains one or more columns referenced by the source table.</span></span> <span data-ttu-id="3509c-114">Per i self join, selezionare la stessa tabella selezionata in **Tabella di origine (chiave esterna)**.</span><span class="sxs-lookup"><span data-stu-id="3509c-114">For self-joins, select the same table selected in **Source (foreign key) table**.</span></span>  
  
 <span data-ttu-id="3509c-115">**Colonne di origine**</span><span class="sxs-lookup"><span data-stu-id="3509c-115">**Source columns**</span></span>  
 <span data-ttu-id="3509c-116">Consente di selezionare le colonne che fanno riferimento alle colonne nella tabella di destinazione.</span><span class="sxs-lookup"><span data-stu-id="3509c-116">Select the columns that reference columns in the destination table.</span></span>  
  
 <span data-ttu-id="3509c-117">**Colonne di destinazione**</span><span class="sxs-lookup"><span data-stu-id="3509c-117">**Destination columns**</span></span>  
 <span data-ttu-id="3509c-118">Consente di selezionare le colonne a cui fanno riferimento le colonne nella tabella di origine.</span><span class="sxs-lookup"><span data-stu-id="3509c-118">Select the columns that are referenced by columns in the source table.</span></span>  
  
 <span data-ttu-id="3509c-119">**Inverso**</span><span class="sxs-lookup"><span data-stu-id="3509c-119">**Reverse**</span></span>  
 <span data-ttu-id="3509c-120">Fare clic su questa opzione per invertire la direzione della relazione.</span><span class="sxs-lookup"><span data-stu-id="3509c-120">Click to reverse the direction of the relationship.</span></span>  
  
 <span data-ttu-id="3509c-121">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="3509c-121">**Description**</span></span>  
 <span data-ttu-id="3509c-122">Consente di digitare una descrizione facoltativa per la relazione.</span><span class="sxs-lookup"><span data-stu-id="3509c-122">Type an optional description for the relationship.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3509c-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3509c-123">See Also</span></span>  
 <span data-ttu-id="3509c-124">[Finestre di progettazione e finestre di dialogo Analysis Services &#40;dati multidimensionali&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="3509c-124">[Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="3509c-125">Progettazione vista origine dati &#40;Analysis Services - Dati multidimensionali&#41;</span><span class="sxs-lookup"><span data-stu-id="3509c-125">Data Source View Designer &#40;Analysis Services - Multidimensional Data&#41;</span></span>](data-source-view-designer-analysis-services-multidimensional-data.md)  
  
  
