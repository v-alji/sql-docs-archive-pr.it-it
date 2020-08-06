---
title: Finestra di dialogo colonne chiave (Analysis Services-Dati multidimensionali) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql.asvs.dimensiondesigner.dbv.dataitemCollection.f1
helpviewer_keywords:
- DataItem Collection dialog box
ms.assetid: 585f27f2-d5eb-4516-b29a-2084010b7d51
author: minewiskan
ms.author: owend
ms.openlocfilehash: 8a72a9e137700ddee822e68901bfde971637d07f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625660"
---
# <a name="key-columns-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="b9767-102">Finestra di dialogo Colonne chiave (Analysis Services - Dati multidimensionali)</span><span class="sxs-lookup"><span data-stu-id="b9767-102">Key Columns Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="b9767-103">Usare la finestra di dialogo **Colonne chiave** per modificare la proprietà **KeyColumns** di un attributo.</span><span class="sxs-lookup"><span data-stu-id="b9767-103">Use the **Key Columns** dialog box to change the **KeyColumns** property of an attribute.</span></span> <span data-ttu-id="b9767-104">Per altre informazioni, vedere [Modificare la proprietà KeyColumn di un attributo](multidimensional-models/attribute-properties-modify-the-keycolumn-property.md).</span><span class="sxs-lookup"><span data-stu-id="b9767-104">For more information, see [Modify the KeyColumn Property of an Attribute](multidimensional-models/attribute-properties-modify-the-keycolumn-property.md).</span></span>  
  
 <span data-ttu-id="b9767-105">**Per visualizzare la finestra di dialogo Colonne chiave**</span><span class="sxs-lookup"><span data-stu-id="b9767-105">**To display the Key Columns dialog box**</span></span>  
  
-   <span data-ttu-id="b9767-106">In [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] o in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], selezionare un attributo e nella finestra **Proprietà** fare clic sul pulsante con i puntini di sospensione (**...**) associato alla proprietà **KeyColumns** di quell'attributo.</span><span class="sxs-lookup"><span data-stu-id="b9767-106">In [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] or [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], select an attribute, and in the **Properties** window, click the ellipsis button (**...**) associated with the **KeyColumns** property of that attribute.</span></span>  
  
## <a name="options"></a><span data-ttu-id="b9767-107">Opzioni</span><span class="sxs-lookup"><span data-stu-id="b9767-107">Options</span></span>  
 <span data-ttu-id="b9767-108">**Tabella di origine**</span><span class="sxs-lookup"><span data-stu-id="b9767-108">**Source table**</span></span>  
 <span data-ttu-id="b9767-109">Selezionare la tabella di origine per la quale si vogliono selezionare le colonne chiave.</span><span class="sxs-lookup"><span data-stu-id="b9767-109">Select the source table for which you want to select its key columns.</span></span> <span data-ttu-id="b9767-110">È possibile selezionare la tabella di origine da un elenco di tutte le tabelle nella Vista origine dati.</span><span class="sxs-lookup"><span data-stu-id="b9767-110">You can select the source table from a list of all tables in the Data Source View.</span></span>  
  
 <span data-ttu-id="b9767-111">**Colonne disponibili**</span><span class="sxs-lookup"><span data-stu-id="b9767-111">**Available Columns**</span></span>  
 <span data-ttu-id="b9767-112">Selezionare le colonne da utilizzare come colonne chiave.</span><span class="sxs-lookup"><span data-stu-id="b9767-112">Select the columns that you want to use as key columns.</span></span> <span data-ttu-id="b9767-113">È possibile selezionare le colonne non ancora selezionate come colonne chiave da un elenco di colonne nella **Tabella di origine** specificata.</span><span class="sxs-lookup"><span data-stu-id="b9767-113">You can select the columns from a list of columns in the specified **Source table** that have not yet been selected as key columns.</span></span>  
  
 <span data-ttu-id="b9767-114">Per aggiungere le colonne selezionate all'elenco **Colonne chiave** fare clic sul pulsante **>** .</span><span class="sxs-lookup"><span data-stu-id="b9767-114">To add the selected columns to the **Key Columns** list, click the **>** button.</span></span>  
  
 <span data-ttu-id="b9767-115">**Colonne chiave**</span><span class="sxs-lookup"><span data-stu-id="b9767-115">**Key Columns**</span></span>  
 <span data-ttu-id="b9767-116">Definire l'ordine delle colonne chiave selezionate.</span><span class="sxs-lookup"><span data-stu-id="b9767-116">Define the order of the selected key columns.</span></span> <span data-ttu-id="b9767-117">L'ordine delle colonne chiave è importante nel definire la chiave composta corretta.</span><span class="sxs-lookup"><span data-stu-id="b9767-117">The order of the key columns is important in defining the correct composite key.</span></span> <span data-ttu-id="b9767-118">Per ordinare o riordinare l'elenco delle colonne chiave, selezionare una colonna, quindi fare clic sul pulsante **Su** o **Giù** .</span><span class="sxs-lookup"><span data-stu-id="b9767-118">To order or reorder the list of key columns, select a column, and then click the **Up** or **Down** buttons.</span></span>  
  
 <span data-ttu-id="b9767-119">Per rimuovere una colonna dall'elenco **Colonne chiave** , selezionare la colonna e fare click sul pulsante **\<** .</span><span class="sxs-lookup"><span data-stu-id="b9767-119">To remove a column from the **Key Columns** list, select the column and click the **\<** button.</span></span>  
  
 <span data-ttu-id="b9767-120">**Fino**</span><span class="sxs-lookup"><span data-stu-id="b9767-120">**Up**</span></span>  
 <span data-ttu-id="b9767-121">Fare clic per spostare verso l'alto di una posizione la colonna selezionata in **Colonne chiave** .</span><span class="sxs-lookup"><span data-stu-id="b9767-121">Click to move the column selected in **Key Columns** up one position.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b9767-122">Questa opzione è abilitata solo se l'elenco contiene più di una colonna e una colonna è selezionata.</span><span class="sxs-lookup"><span data-stu-id="b9767-122">This option is enabled only if the list contains more than one column and a column is selected.</span></span>  
  
 <span data-ttu-id="b9767-123">**Giù**</span><span class="sxs-lookup"><span data-stu-id="b9767-123">**Down**</span></span>  
 <span data-ttu-id="b9767-124">Fare clic per spostare verso il basso di una posizione la colonna selezionata in **Colonne chiave** .</span><span class="sxs-lookup"><span data-stu-id="b9767-124">Click to move the column selected in **Key Columns** down one position.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b9767-125">Questa opzione è abilitata solo se l'elenco contiene più di una colonna e una colonna è selezionata.</span><span class="sxs-lookup"><span data-stu-id="b9767-125">This option is enabled only if the list contains more than one column and a column is selected.</span></span>  
  
 **>**  
 <span data-ttu-id="b9767-126">Fare clic per aggiungere una nuova colonna alla fine delle colonne elencate in **Colonne chiave**.</span><span class="sxs-lookup"><span data-stu-id="b9767-126">Click to add a new column to the end of the columns listed in **Key Columns**.</span></span>  
  
 **<**  
 <span data-ttu-id="b9767-127">Fare clic per rimuovere la colonna selezionata dalle colonne elencate in **Colonne chiave**.</span><span class="sxs-lookup"><span data-stu-id="b9767-127">Click to remove the selected column from the columns listed in **Key Columns**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9767-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b9767-128">See Also</span></span>  
 [<span data-ttu-id="b9767-129">Finestre di progettazione e finestre di dialogo Analysis Services &#40;dati multidimensionali&#41;</span><span class="sxs-lookup"><span data-stu-id="b9767-129">Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;</span></span>](analysis-services-designers-and-dialog-boxes-multidimensional-data.md)  
  
  
