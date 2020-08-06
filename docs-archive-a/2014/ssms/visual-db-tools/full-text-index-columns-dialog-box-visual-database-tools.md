---
title: Finestra di dialogo Colonne indice full-text (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdt.dlgbox.fulltextcolumn
ms.assetid: a6f41c5c-d950-4d64-9e42-d062925917b6
author: stevestein
ms.author: sstein
ms.openlocfilehash: 7f1cd2c94739a13e1820d8c05b338abd91d8a908
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725211"
---
# <a name="full-text-index-columns-dialog-box-visual-database-tools"></a><span data-ttu-id="08318-102">Finestra di dialogo Colonne indice full-text (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="08318-102">Full-Text Index Columns Dialog Box (Visual Database Tools)</span></span>
  <span data-ttu-id="08318-103">In questa finestra di dialogo sono elencate le colonne utilizzate nell'indice full-text per la tabella aperta in Progettazione tabelle.</span><span class="sxs-lookup"><span data-stu-id="08318-103">This dialog box lists the columns participating in the full-text index for the table open in Table Designer.</span></span> <span data-ttu-id="08318-104">Per accedere a tale finestra di dialogo, fare clic con il pulsante destro del mouse sulla tabella in Progettazione tabelle, scegliere **Indice full-text** e nella finestra di dialogo **Indice full-text** fare clic sull'indice con le colonne da visualizzare o modificare, nel campo **Colonne** nella griglia a destra e infine sui puntini di sospensione ( **...** ).</span><span class="sxs-lookup"><span data-stu-id="08318-104">To access this dialog box, right-click the table in Table Designer, choose **Full-Text Index**, and in the **Full-Text Index** dialog box, click the index with columns you want to view or edit, click the **Columns** field in the grid to the right, and click the ellipses (**...**).</span></span>  
  
## <a name="options"></a><span data-ttu-id="08318-105">Opzioni</span><span class="sxs-lookup"><span data-stu-id="08318-105">Options</span></span>  
 <span data-ttu-id="08318-106">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="08318-106">**Column**</span></span>  
 <span data-ttu-id="08318-107">Visualizza i nomi delle colonne utilizzate nell'indice full-text.</span><span class="sxs-lookup"><span data-stu-id="08318-107">Shows the names of columns participating in the full-text index.</span></span> <span data-ttu-id="08318-108">Per aggiungere una colonna, fare clic sulla prima cella vuota e selezionare la colonna desiderata nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="08318-108">To add a column, click in the first empty cell and choose a column from the drop-down list.</span></span> <span data-ttu-id="08318-109">Risulteranno accessibili solo le colonne con tipo di dati testo o image.</span><span class="sxs-lookup"><span data-stu-id="08318-109">Only columns with either text-based or image data types will be accessible.</span></span>  
  
 <span data-ttu-id="08318-110">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="08318-110">**Data Type**</span></span>  
 <span data-ttu-id="08318-111">Visualizza il tipo di dati di ogni colonna.</span><span class="sxs-lookup"><span data-stu-id="08318-111">Shows the data type for each column.</span></span> <span data-ttu-id="08318-112">Questa proprietà è di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="08318-112">This is a read-only property.</span></span> <span data-ttu-id="08318-113">Per cambiare tipo di dati, aprire la tabella in Progettazione tabelle, fare clic sulla colonna e cambiare il tipo di dati nella scheda **Proprietà colonne** .</span><span class="sxs-lookup"><span data-stu-id="08318-113">To change a data type, open the table in Table Designer, click the column, and edit the data type in the **Column Properties** tab.</span></span>  
  
 <span data-ttu-id="08318-114">**Tipizzato per colonna**</span><span class="sxs-lookup"><span data-stu-id="08318-114">**Typed by Column**</span></span>  
 <span data-ttu-id="08318-115">Si applica solo alle colonne con tipo di dati `image`.</span><span class="sxs-lookup"><span data-stu-id="08318-115">Applies only to columns with the data type `image`.</span></span> <span data-ttu-id="08318-116">Nell'elenco a discesa è possibile selezionare quali altre colonne rappresentano il tipo di dati della colonna in questione.</span><span class="sxs-lookup"><span data-stu-id="08318-116">Provides a drop-down list from which you can choose which of the other columns represent the data type of this column.</span></span> <span data-ttu-id="08318-117">Se tale colonna non ha un tipo di dati `image`, il valore sarà Nessuno.</span><span class="sxs-lookup"><span data-stu-id="08318-117">If this column is not of the `image` data type the value will be None.</span></span>  
  
 <span data-ttu-id="08318-118">Le colonne con tipo di dati `image` possono contenere file di Microsoft Office (con estensione doc, xls e ppt), file di testo (con estensione txt) e file HTML (con estensione htm). Pertanto, impostando su image il tipo di dati della colonna, sarà possibile eseguire la ricerca full-text nel contenuto dei file.</span><span class="sxs-lookup"><span data-stu-id="08318-118">Columns with the data type `image` can contain Microsoft Office files (.doc, .xls, and .ppt files), text files (.txt files), and HTML files (.htm files), and setting the data type of that column to image allows the full-text search to search the contents of the files.</span></span>  
  
 <span data-ttu-id="08318-119">**Lingua**</span><span class="sxs-lookup"><span data-stu-id="08318-119">**Language**</span></span>  
 <span data-ttu-id="08318-120">Elenca tutte le lingue disponibili.</span><span class="sxs-lookup"><span data-stu-id="08318-120">Lists available languages.</span></span> <span data-ttu-id="08318-121">Selezionare nell'elenco a discesa la lingua appropriata per i dati inclusi nella colonna.</span><span class="sxs-lookup"><span data-stu-id="08318-121">Choose the language from the drop-down list appropriate for your column data.</span></span> <span data-ttu-id="08318-122">Se, ad esempio, si utilizza un sistema operativo in lingua inglese, ma si desidera indicizzare una colonna contenente testo in lingua tedesca, selezionare l'opzione corrispondente al tedesco nell'elenco a discesa per migliorare le prestazioni dell'indice.</span><span class="sxs-lookup"><span data-stu-id="08318-122">For example, if you are using an English operating system, but you want to index a column that contains German text, choose German from the drop-down list to improve the index's performance.</span></span>  
  
 <span data-ttu-id="08318-123">**Semantica statistica**</span><span class="sxs-lookup"><span data-stu-id="08318-123">**Statistical Semantics**</span></span>  
 <span data-ttu-id="08318-124">Consente di selezionare se abilitare l'indicizzazione semantica per la colonna selezionata.</span><span class="sxs-lookup"><span data-stu-id="08318-124">Select whether to enable semantic indexing for the selected column.</span></span> <span data-ttu-id="08318-125">Per altre informazioni, vedere [Ricerca semantica &#40;SQL Server&#41;](../../relational-databases/search/semantic-search-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="08318-125">For more information, see [Semantic Search &#40;SQL Server&#41;](../../relational-databases/search/semantic-search-sql-server.md).</span></span>  
  
 <span data-ttu-id="08318-126">Se si seleziona una lingua in **Lingua** prima di selezionare **Semantica statistica**e alla lingua selezionata non è associato alcun modello di lingua semantico, la casella di controllo **Semantica statistica** è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="08318-126">If you select a **Language** prior to selecting **Statistical Semantics**, and the selected language does not have an associated Semantic Language Model, then the **Statistical Semantics** checkbox is disabled.</span></span> <span data-ttu-id="08318-127">Se si seleziona **Semantica statistica** prima di selezionare una lingua in **Lingua**, le lingue disponibili nella casella combinata a discesa saranno limitate a quelle per cui è disponibile un modello di lingua semantico.</span><span class="sxs-lookup"><span data-stu-id="08318-127">If you select **Statistical Semantics** prior to selecting a **Language**, the languages available in the drop-down combo box will be restricted to those for which there is Semantic Language Model support.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08318-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="08318-128">See Also</span></span>  
 [<span data-ttu-id="08318-129">Finestra di dialogo Indice full-text &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="08318-129">Full-Text Index Dialog Box &#40;Visual Database Tools&#41;</span></span>](visual-database-tools.md)  
  
  
