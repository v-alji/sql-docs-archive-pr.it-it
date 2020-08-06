---
title: Guida sensibile al contesto della creazione guidata partizione (Analysis Services-Dati multidimensionali) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Partition Wizard
ms.assetid: 3b6d7053-aeef-4d9e-af70-f5b40256e859
author: minewiskan
ms.author: owend
ms.openlocfilehash: fa8c0e94c2b18ffbd1228752bd7cb4ad4f684acb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626350"
---
# <a name="partition-wizard-f1-help-analysis-services---multidimensional-data"></a><span data-ttu-id="f7937-102">Guida sensibile al contesto della Creazione guidata partizione (Analysis Services - Dati multidimensionali)</span><span class="sxs-lookup"><span data-stu-id="f7937-102">Partition Wizard F1 Help (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="f7937-103">La Creazione guidata partizione può essere utilizzata per definire le partizioni per un gruppo di misure in un cubo.</span><span class="sxs-lookup"><span data-stu-id="f7937-103">You can use the Partition Wizard to define partitions for a measure group in a cube.</span></span> <span data-ttu-id="f7937-104">Per impostazione predefinita, viene definita un'unica partizione per ogni gruppo di misure in un cubo.</span><span class="sxs-lookup"><span data-stu-id="f7937-104">By default, a single partition is defined for each measure group in a cube.</span></span> <span data-ttu-id="f7937-105">Ciò può avere tuttavia ripercussioni negative sulle prestazioni di accesso ed elaborazione nel caso di partizioni di dimensioni elevate.</span><span class="sxs-lookup"><span data-stu-id="f7937-105">Access and processing performance, however, can degrade for large partitions.</span></span> <span data-ttu-id="f7937-106">La creazione di più partizioni, contenenti ciascuna una parte dei dati per un gruppo di misure, consente di migliorare le prestazioni di accesso ed elaborazione di tale gruppo di misure.</span><span class="sxs-lookup"><span data-stu-id="f7937-106">By creating multiple partitions, each containing a portion of the data for a measure group, you can improve the access and processing performance for that measure group.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="f7937-107">L'inclusione di righe duplicate nella pagina **Impostazione informazioni origine** o nella pagina **Limitazione righe** può comportare la creazione di partizioni contenenti dati non corretti.</span><span class="sxs-lookup"><span data-stu-id="f7937-107">It is possible to create partitions that may contain incorrect data by including duplicate rows in the **Specify Source Information** or **Restrict Rows** pages.</span></span>  
  
 <span data-ttu-id="f7937-108">La Creazione guidata partizione consente di eseguire in modo semplificato i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="f7937-108">The Partition Wizard guides you through the following steps:</span></span>  
  
-   <span data-ttu-id="f7937-109">Selezionare la vista origine dati per la partizione.</span><span class="sxs-lookup"><span data-stu-id="f7937-109">Selecting the data source view for the partition.</span></span>  
  
-   <span data-ttu-id="f7937-110">Creare un filtro per i record inclusi nella partizione.</span><span class="sxs-lookup"><span data-stu-id="f7937-110">Creating a filter for the records included in the partition.</span></span>  
  
-   <span data-ttu-id="f7937-111">Impostare le posizioni di elaborazione e di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="f7937-111">Setting the processing and storage locations.</span></span>  
  
-   <span data-ttu-id="f7937-112">Denominare e salvare la partizione.</span><span class="sxs-lookup"><span data-stu-id="f7937-112">Naming and saving the partition.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f7937-113">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="f7937-113">In This Section</span></span>  
  
-   [<span data-ttu-id="f7937-114">Impostazione &#40;partizione guidata informazioni origine&#41;</span><span class="sxs-lookup"><span data-stu-id="f7937-114">Specify Source Information &#40;Partition Wizard&#41;</span></span>](specify-source-information-partition-wizard.md)  
  
-   [<span data-ttu-id="f7937-115">Limitazione delle righe &#40;creazione guidata partizione&#41;</span><span class="sxs-lookup"><span data-stu-id="f7937-115">Restrict Rows &#40;Partition Wizard&#41;</span></span>](restrict-rows-partition-wizard.md)  
  
-   [<span data-ttu-id="f7937-116">Posizioni di elaborazione e archiviazione &#40;creazione guidata partizione&#41;</span><span class="sxs-lookup"><span data-stu-id="f7937-116">Processing and Storage Locations &#40;Partition Wizard&#41;</span></span>](processing-and-storage-locations-partition-wizard.md)  
  
-   [<span data-ttu-id="f7937-117">Completamento procedura guidata &#40;partizione guidata&#41;</span><span class="sxs-lookup"><span data-stu-id="f7937-117">Completing the Wizard &#40;Partition Wizard&#41;</span></span>](completing-the-wizard-partition-wizard.md)  
  
-   [<span data-ttu-id="f7937-118">Finestra di dialogo Cerca cartella remota &#40;Analysis Services-Dati multidimensionali&#41;</span><span class="sxs-lookup"><span data-stu-id="f7937-118">Browse for Remote Folder Dialog Box &#40;Analysis Services - Multidimensional Data&#41;</span></span>](browse-for-remote-folder-dialog-box-analysis-services-multidimensional-data.md)  
  
## <a name="see-also"></a><span data-ttu-id="f7937-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f7937-119">See Also</span></span>  
 [<span data-ttu-id="f7937-120">Partizioni &#40;Analysis Services - Dati multidimensionali&#41;</span><span class="sxs-lookup"><span data-stu-id="f7937-120">Partitions &#40;Analysis Services - Multidimensional Data&#41;</span></span>](multidimensional-models-olap-logical-cube-objects/partitions-analysis-services-multidimensional-data.md)  
  
  
