---
title: Impostazione informazioni origine (creazione guidata partizione) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.partitionwizard.specifydsvandfacttables.f1
ms.assetid: b6c13587-c690-45d9-af90-b3d652afc55b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 088a8abf7b143b68766f22af37f8ff4fa2065d65
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635758"
---
# <a name="specify-source-information-partition-wizard"></a><span data-ttu-id="59ae3-102">Impostazione informazioni origine (Creazione guidata partizione)</span><span class="sxs-lookup"><span data-stu-id="59ae3-102">Specify Source Information (Partition Wizard)</span></span>
  <span data-ttu-id="59ae3-103">Utilizzare la pagina **Impostazione informazioni origine** per selezionare il gruppo di misure in cui creare la partizione, nonché la vista origine dati e le tabelle di filtro per la partizione.</span><span class="sxs-lookup"><span data-stu-id="59ae3-103">Use the **Specify Source Information** page to select the measure group in which to create the partition, and also the data source view and filter tables for your partition.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="59ae3-104"> Se in **Tabelle disponibili** si seleziona una tabella utilizzata da un'altra partizione, sarà necessario specificare una query nella pagina **Limitazione righe** per evitare il rischio di duplicazioni di dati nel cubo.</span><span class="sxs-lookup"><span data-stu-id="59ae3-104">If you specify a table in **Available Tables** that is used by another partition, you must provide a query in the **Restrict Rows** page or risk duplicating data in the cube.</span></span>  
  
## <a name="options"></a><span data-ttu-id="59ae3-105">Opzioni</span><span class="sxs-lookup"><span data-stu-id="59ae3-105">Options</span></span>  
 <span data-ttu-id="59ae3-106">**Gruppo di misure**</span><span class="sxs-lookup"><span data-stu-id="59ae3-106">**Measure group**</span></span>  
 <span data-ttu-id="59ae3-107">Consente di selezionare un gruppo di misure per la partizione.</span><span class="sxs-lookup"><span data-stu-id="59ae3-107">Select a measure group for this partition.</span></span>  
  
 <span data-ttu-id="59ae3-108">**Cerca in**</span><span class="sxs-lookup"><span data-stu-id="59ae3-108">**Look in**</span></span>  
 <span data-ttu-id="59ae3-109">Consente di selezionare l'origine dei dati o la vista origine dati contenente le tabelle di origine per la partizione.</span><span class="sxs-lookup"><span data-stu-id="59ae3-109">Select the data source or data source view that contains the source tables for this partition.</span></span> <span data-ttu-id="59ae3-110">Per impostazione predefinita, è selezionata la vista origine dati utilizzata dal gruppo di misure.</span><span class="sxs-lookup"><span data-stu-id="59ae3-110">The data source view used by the measure group is selected by default.</span></span>  
  
 <span data-ttu-id="59ae3-111">**Filtro tabelle**</span><span class="sxs-lookup"><span data-stu-id="59ae3-111">**Filter tables**</span></span>  
 <span data-ttu-id="59ae3-112">Digitare la stringa usata per limitare le tabelle visualizzate in **Tabelle disponibili**per nome tabella.</span><span class="sxs-lookup"><span data-stu-id="59ae3-112">Type the string used to restrict, by table name, the tables displayed in **Available tables**.</span></span>  
  
 <span data-ttu-id="59ae3-113">**Trovare le tabelle**</span><span class="sxs-lookup"><span data-stu-id="59ae3-113">**Find tables**</span></span>  
 <span data-ttu-id="59ae3-114">Selezionare questa opzione per aggiornare l'elenco delle tabelle in **Tabelle disponibili**e per ridurre ulteriormente l'elenco, se in **Filtro tabelle**è stata specificata una stringa.</span><span class="sxs-lookup"><span data-stu-id="59ae3-114">Select to refresh the list of tables in **Available tables**, further restricting the list if a string was specified in **Filter tables**.</span></span>  
  
 <span data-ttu-id="59ae3-115">**Tabelle disponibili**</span><span class="sxs-lookup"><span data-stu-id="59ae3-115">**Available tables**</span></span>  
 <span data-ttu-id="59ae3-116">Consente di selezionare le tabelle da utilizzare come tabelle di origine per le partizioni.</span><span class="sxs-lookup"><span data-stu-id="59ae3-116">Select the tables to use as source tables for partitions.</span></span> <span data-ttu-id="59ae3-117">La **Creazione guidata partizione** crea una partizione per ogni tabella selezionata in **Tabelle disponibili**.</span><span class="sxs-lookup"><span data-stu-id="59ae3-117">The **Partition Wizard** creates one partition for each table selected in **Available tables**.</span></span>  
  
 <span data-ttu-id="59ae3-118">Se in **Filtro tabelle**non è indicato alcun filtro, questa opzione consentirà di visualizzare l'elenco di tutte le tabelle nell'origine dati o nella vista origine dati specificata in **Cerca in** , simili per struttura alla tabella dei fatti utilizzata dal gruppo di misure selezionato in **Gruppo di misure**.</span><span class="sxs-lookup"><span data-stu-id="59ae3-118">If no filter is specified in **Filter tables**, this option lists all tables in the data source or data source view that are specified in **Look in** and that are similar in structure to the fact table used by the measure group specified in **Measure group**.</span></span>  
  
 <span data-ttu-id="59ae3-119">Se in **Filtro tabelle**è specificato un filtro, l'elenco verrà ulteriormente ridotto tramite un confronto del filtro con i nomi di tabella che soddisfano i criteri precedenti.</span><span class="sxs-lookup"><span data-stu-id="59ae3-119">If a filter is specified in **Filter tables**, the list is further restricted by comparing the filter against the table names that meet the previous criteria.</span></span> <span data-ttu-id="59ae3-120">Verranno visualizzate solo le tabelle che contengono la stringa specificata in **Filtro tabelle** .</span><span class="sxs-lookup"><span data-stu-id="59ae3-120">Only those tables that contain the string specified in **Filter tables** are displayed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="59ae3-121">Se sono selezionate più tabelle, non sarà possibile visualizzare la pagina **Limitazione righe** , né ridurre le righe per le partizioni create dalle tabelle specificate.</span><span class="sxs-lookup"><span data-stu-id="59ae3-121">If more than one table is selected, the **Restrict Rows** page cannot be displayed and rows cannot be restricted for the partitions created from the selected tables.</span></span> <span data-ttu-id="59ae3-122">Per limitare le righe per ogni partizione, eseguire la Creazione guidata partizione una volta per ogni tabella da cui deve essere creata la partizione.</span><span class="sxs-lookup"><span data-stu-id="59ae3-122">To restrict rows for each partition, run the Partition Wizard once for each table from which a partition is to be created.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59ae3-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="59ae3-123">See Also</span></span>  
 [<span data-ttu-id="59ae3-124">Partizioni &#40;Analysis Services - Dati multidimensionali&#41;</span><span class="sxs-lookup"><span data-stu-id="59ae3-124">Partitions &#40;Analysis Services - Multidimensional Data&#41;</span></span>](multidimensional-models-olap-logical-cube-objects/partitions-analysis-services-multidimensional-data.md)  
  
  
