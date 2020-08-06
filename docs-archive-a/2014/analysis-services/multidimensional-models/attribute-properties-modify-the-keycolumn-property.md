---
title: Modificare la proprietà della colonna di colonna di un attributo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- binding attributes [Analysis Services]
- attributes [Analysis Services], binding
- key columns [Analysis Services]
ms.assetid: a2643be4-8123-4cc3-baf9-e5ec54a1669d
author: minewiskan
ms.author: owend
ms.openlocfilehash: 3367a7aec84ba59efd118a56745bb76fc5266061
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725112"
---
# <a name="modify-the-keycolumn-property-of-an-attribute"></a><span data-ttu-id="fff94-102">Modificare la proprietà KeyColumn di un attributo</span><span class="sxs-lookup"><span data-stu-id="fff94-102">Modify the KeyColumn Property of an Attribute</span></span>
  <span data-ttu-id="fff94-103">È possibile modificare la proprietà **KeyColumns** di un attributo.</span><span class="sxs-lookup"><span data-stu-id="fff94-103">You can modify the **KeyColumns** property of an attribute.</span></span> <span data-ttu-id="fff94-104">Ad esempio, è possibile specificare una chiave composta anziché una chiave semplice come chiave dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="fff94-104">For example, you might want to specify a composite key instead of a single key as the key for the attribute.</span></span>  
  
### <a name="to-modify-the-keycolumns-property-of-an-attribute"></a><span data-ttu-id="fff94-105">Per modificare la proprietà KeyColumns di un attributo</span><span class="sxs-lookup"><span data-stu-id="fff94-105">To modify the KeyColumns property of an attribute</span></span>  
  
1.  <span data-ttu-id="fff94-106">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]aprire il progetto nel quale si vuole modificare la proprietà **KeyColumns** .</span><span class="sxs-lookup"><span data-stu-id="fff94-106">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the project in which you want to modify the **KeyColumns** property.</span></span>  
  
2.  <span data-ttu-id="fff94-107">Aprire Progettazione dimensioni effettuando una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="fff94-107">Open Dimension Designer by doing one of the following procedures:</span></span>  
  
    -   <span data-ttu-id="fff94-108">In **Esplora soluzioni**fare clic con il pulsante destro del mouse sulla dimensione nella cartella **Dimensioni** e quindi scegliere **Apri** o **Progettazione viste**.</span><span class="sxs-lookup"><span data-stu-id="fff94-108">In **Solution Explorer**, right-click the dimension in the **Dimensions** folder, and then either click **Open** or **View Designer**.</span></span>  
  
         <span data-ttu-id="fff94-109">-oppure-</span><span class="sxs-lookup"><span data-stu-id="fff94-109">-or-</span></span>  
  
    -   <span data-ttu-id="fff94-110">Nella scheda **Struttura cubo** di Progettazione cubi espandere la dimensione del cubo nel riquadro **dimensioni** e fare clic su \*\*modifica \<dimension> \*\*.</span><span class="sxs-lookup"><span data-stu-id="fff94-110">In Cube Designer, on the **Cube Structure** tab, expand the cube dimension in the **Dimensions** pane and click **Edit \<dimension>**.</span></span>  
  
3.  <span data-ttu-id="fff94-111">Nel riquadro **Attributi** della scheda **Struttura dimensione** fare clic sull'attributo per il quale si vuole modificare la proprietà **KeyColumns** .</span><span class="sxs-lookup"><span data-stu-id="fff94-111">On the **Dimension Structure** tab, in the **Attributes** pane, click the attribute whose **KeyColumns** property you want to modify.</span></span>  
  
4.  <span data-ttu-id="fff94-112">Nella finestra **Proprietà** fare clic sul valore della proprietà **KeyColumns** .</span><span class="sxs-lookup"><span data-stu-id="fff94-112">In the **Properties** window, click the value for the **KeyColumns** property.</span></span>  
  
5.  <span data-ttu-id="fff94-113">Fare clic sul pulsante di ricerca ( **...** ) che viene visualizzato nella cella del valore della casella delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="fff94-113">Click the browse **(...)** button that appears in the value cell of the property box.</span></span>  
  
     <span data-ttu-id="fff94-114">Verrà visualizzata la finestra di dialogo **Colonne chiave** .</span><span class="sxs-lookup"><span data-stu-id="fff94-114">The **Key Columns** dialog box opens.</span></span>  
  
6.  <span data-ttu-id="fff94-115">Per rimuovere una colonna chiave esistente, nell'elenco **Colonne chiave** selezionare la colonna e quindi fare clic sul pulsante **\<** .</span><span class="sxs-lookup"><span data-stu-id="fff94-115">To remove an existing key column, in the **Key Columns** list, select the column, and then click the **\<** button.</span></span>  
  
7.  <span data-ttu-id="fff94-116">Per aggiungere una colonna chiave, nell'elenco **Colonne disponibili** selezionare la colonna e quindi fare clic sul pulsante **>** .</span><span class="sxs-lookup"><span data-stu-id="fff94-116">To add a key column, in the **Available Columns** list, select the column, and then click the **>** button.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="fff94-117">Se si definiscono più colonne chiave, l'ordine di visualizzazione di tali colonne nell'elenco **Colonne chiave** influisce sull'ordine visualizzato.</span><span class="sxs-lookup"><span data-stu-id="fff94-117">If you define multiple key columns, the order in which those columns appear in the **Key Columns** list affects the display order.</span></span> <span data-ttu-id="fff94-118">Ad esempio, l'attributo mese ha due colonne chiave: mese ed anno.</span><span class="sxs-lookup"><span data-stu-id="fff94-118">For example, a month attribute has two key columns: month and year.</span></span> <span data-ttu-id="fff94-119">Se la colonna anno è visualizzata nell'elenco prima della colonna mese, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] ordina per anno e quindi per mese.</span><span class="sxs-lookup"><span data-stu-id="fff94-119">If the year column appears in the list before the month column, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] will sort by year and then by month.</span></span> <span data-ttu-id="fff94-120">Se la colonna mese appare prima della colonna anno, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] ordina per mese e quindi per anno.</span><span class="sxs-lookup"><span data-stu-id="fff94-120">If the month column appears before the year column, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] will sort by month and then by year.</span></span>  
  
8.  <span data-ttu-id="fff94-121">Per modificare l'ordine delle colonne chiave, selezionare una colonna e quindi fare clic sul pulsante **Su** o **Giù** .</span><span class="sxs-lookup"><span data-stu-id="fff94-121">To change the order of key columns, select a column, and then click the **Up** or **Down** button.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fff94-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fff94-122">See Also</span></span>  
 [<span data-ttu-id="fff94-123">Riferimento alle proprietà degli attributo delle dimensioni</span><span class="sxs-lookup"><span data-stu-id="fff94-123">Dimension Attribute Properties Reference</span></span>](dimension-attribute-properties-reference.md)  
  
  
