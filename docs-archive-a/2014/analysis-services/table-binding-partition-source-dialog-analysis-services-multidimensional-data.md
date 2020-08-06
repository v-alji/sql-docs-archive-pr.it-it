---
title: Dettagli dell'associazione di tabella (finestra di dialogo origine partizione) (Analysis Services-Dati multidimensionali) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.cubeeditor.partitions.partitiontableselection.f1
ms.assetid: 67d05389-81ae-4a6b-947b-986d37ec72b1
author: minewiskan
ms.author: owend
ms.openlocfilehash: 10845e18a2b7c74a8ed3aeec42f710b9706dc94a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627424"
---
# <a name="table-binding-detail-partition-source-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="90dfc-102">Dettagli dell'associazione di tabella (finestra di dialogo Origine partizione) (Analysis Services - Dati multidimensionali)</span><span class="sxs-lookup"><span data-stu-id="90dfc-102">Table Binding Detail (Partition Source Dialog Box) (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="90dfc-103">Utilizzare l'opzione **Associazione tabella** della finestra di dialogo **Origine partizione** per specificare la tabella dei fatti che fornisce i dati per la partizione.</span><span class="sxs-lookup"><span data-stu-id="90dfc-103">Use the **Table Binding** option in the **Partition Source** dialog box to specify the fact table that provides the data for the partition.</span></span> <span data-ttu-id="90dfc-104">Per visualizzare questo riquadro è possibile selezionare **Associazione tabella** nell'opzione **Tipo di associazione** della finestra di dialogo **Origine partizione** .</span><span class="sxs-lookup"><span data-stu-id="90dfc-104">You can display this pane by selecting **Table Binding** from the **Binding type** option in the **Partition Source** dialog box.</span></span>  
  
## <a name="options"></a><span data-ttu-id="90dfc-105">Opzioni</span><span class="sxs-lookup"><span data-stu-id="90dfc-105">Options</span></span>  
 <span data-ttu-id="90dfc-106">**Gruppo di misure**</span><span class="sxs-lookup"><span data-stu-id="90dfc-106">**Measure group**</span></span>  
 <span data-ttu-id="90dfc-107">Consente di visualizzare il gruppo di misure per la partizione.</span><span class="sxs-lookup"><span data-stu-id="90dfc-107">Displays the measure group for this partition.</span></span>  
  
 <span data-ttu-id="90dfc-108">**Cerca in**</span><span class="sxs-lookup"><span data-stu-id="90dfc-108">**Look in**</span></span>  
 <span data-ttu-id="90dfc-109">Consente di selezionare l'origine dei dati o la vista origine dati contenente le tabelle di origine per la partizione.</span><span class="sxs-lookup"><span data-stu-id="90dfc-109">Select the data source or data source view that contains the source tables for this partition.</span></span> <span data-ttu-id="90dfc-110">La vista origine dati utilizzata dal gruppo di misure selezionato è selezionata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="90dfc-110">The data source view used by the selected measure group is selected by default.</span></span>  
  
 <span data-ttu-id="90dfc-111">**Filtro tabelle**</span><span class="sxs-lookup"><span data-stu-id="90dfc-111">**Filter tables**</span></span>  
 <span data-ttu-id="90dfc-112">Digitare la stringa usata per limitare le tabelle visualizzate in **Tabelle disponibili**per nome tabella.</span><span class="sxs-lookup"><span data-stu-id="90dfc-112">Type the string used to restrict, by table name, the tables displayed in **Available tables**.</span></span>  
  
 <span data-ttu-id="90dfc-113">**Trovare le tabelle**</span><span class="sxs-lookup"><span data-stu-id="90dfc-113">**Find tables**</span></span>  
 <span data-ttu-id="90dfc-114">Selezionare questa opzione per aggiornare l'elenco delle tabelle in **Tabelle disponibili**e per ridurre ulteriormente l'elenco, se in **Filtro tabelle**è stata specificata una stringa.</span><span class="sxs-lookup"><span data-stu-id="90dfc-114">Select to refresh the list of tables in **Available tables**, further restricting the list if a string was specified in **Filter tables**.</span></span>  
  
 <span data-ttu-id="90dfc-115">**Tabelle disponibili**</span><span class="sxs-lookup"><span data-stu-id="90dfc-115">**Available tables**</span></span>  
 <span data-ttu-id="90dfc-116">Fare clic per selezionare la tabella da utilizzare come tabella di origine per la partizione.</span><span class="sxs-lookup"><span data-stu-id="90dfc-116">Click to select the table to use as a source table for the partition.</span></span>  
  
 <span data-ttu-id="90dfc-117">Se non è stato specificato alcun filtro in **Filtro tabelle**, vengono elencate tutte le tabelle dell'origine dei dati o della vista origine dati specificata in **Cerca in** la cui struttura è simile a quella della tabella dei dati utilizzata dal gruppo di misure specificato in **Gruppo di misure** .</span><span class="sxs-lookup"><span data-stu-id="90dfc-117">If no filter is specified in **Filter tables**, all tables in the data source or data source view specified in **Look in** that are similar in structure to the fact table used by the measure group specified in **Measure group** are listed.</span></span>  
  
 <span data-ttu-id="90dfc-118">Se è stato specificato un filtro in **Filtro tabelle**, l'elenco viene ulteriormente limitato confrontando il filtro con i nomi delle tabelle che soddisfano il criterio specificato.</span><span class="sxs-lookup"><span data-stu-id="90dfc-118">If a filter is specified in **Filter tables**, the list is further restricted by comparing the filter against the table names that meet the above criteria.</span></span> <span data-ttu-id="90dfc-119">Verranno visualizzate solo le tabelle che contengono la stringa specificata in **Filtro tabelle** .</span><span class="sxs-lookup"><span data-stu-id="90dfc-119">Only those tables that contain the string specified in **Filter tables** are displayed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90dfc-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="90dfc-120">See Also</span></span>  
 [<span data-ttu-id="90dfc-121">Finestra di dialogo origine partizione &#40;Analysis Services-Dati multidimensionali&#41;</span><span class="sxs-lookup"><span data-stu-id="90dfc-121">Partition Source Dialog Box &#40;Analysis Services - Multidimensional Data&#41;</span></span>](partition-source-dialog-box-analysis-services-multidimensional-data.md)  
  
  
