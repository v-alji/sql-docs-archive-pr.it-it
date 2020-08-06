---
title: Importare da Analysis Services (SSAS tabulare) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: b9a21b23-3a06-4ef8-bc06-9c79cdc54870
author: minewiskan
ms.author: owend
ms.openlocfilehash: 7d6c3d226e46cdb4101bc8db52830046d27b0706
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712507"
---
# <a name="import-from-analysis-services-ssas-tabular"></a><span data-ttu-id="de98d-102">Importare da Analysis Services (SSAS tabulare)</span><span class="sxs-lookup"><span data-stu-id="de98d-102">Import from Analysis Services (SSAS Tabular)</span></span>
  <span data-ttu-id="de98d-103">In questo argomento viene descritto come creare un nuovo progetto di modello tabulare importando i metadati da un modello tabulare esistente tramite il modello di progetto Importa da server disponibile in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="de98d-103">This topic describes how to create a new tabular model project by importing the metadata from an existing tabular model by using the Import from Server project template in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
## <a name="create-a-new-model-by-importing-metadata-from-an-existing-model-in-analysis-services"></a><span data-ttu-id="de98d-104">Creare un nuovo modello importando i metadati da un modello esistente in Analysis Services</span><span class="sxs-lookup"><span data-stu-id="de98d-104">Create a new model by importing metadata from an existing model in Analysis Services</span></span>  
 <span data-ttu-id="de98d-105">È possibile utilizzare il modello di progetto Importa da server per creare un nuovo progetto di modello tabulare copiando i metadati da un modello tabulare esistente in un server Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="de98d-105">You can use the Import from Server project template to create a new tabular model project by copying the metadata from an existing tabular model on an Analysis Services server.</span></span> <span data-ttu-id="de98d-106">Il nuovo progetto sarà creato con le stesse connessioni all'origine dati, tabelle, relazioni, misure, indicatori KPI, ruoli, gerarchie, prospettive e partizioni del modello da cui è stato importato.</span><span class="sxs-lookup"><span data-stu-id="de98d-106">The new project will be created with the same data source connections, tables, relationships, measures, KPIs, roles, hierarchies, perspectives, and partitions as the model it was imported from.</span></span> <span data-ttu-id="de98d-107">Tuttavia, i dati non vengono copiati dal modello esistente nella nuova area di lavoro modello.</span><span class="sxs-lookup"><span data-stu-id="de98d-107">The data, however, is not copied from the existing model to the new model workspace.</span></span> <span data-ttu-id="de98d-108">Una volta completato il processo di importazione e creato il nuovo progetto di modello, è necessario fare clic su Elabora tutto per caricare i dati dalle origini dati nel nuovo database dell'area di lavoro del progetto modello.</span><span class="sxs-lookup"><span data-stu-id="de98d-108">Once the import process has completed, and the new model project created, you must run a Process All to load the data from the data sources into the new model project workspace database.</span></span>  
  
#### <a name="to-create-a-new-model-by-importing-metadata-from-an-existing-model"></a><span data-ttu-id="de98d-109">Per creare un nuovo modello importando metadati da un modello esistente</span><span class="sxs-lookup"><span data-stu-id="de98d-109">To create a new model by importing metadata from an existing model</span></span>  
  
1.  <span data-ttu-id="de98d-110">In [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)]scegliere **Nuovo** dal menu **File**, quindi fare clic su **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="de98d-110">In [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], on the **File** menu, click **New**, and then click **Project**.</span></span>  
  
2.  <span data-ttu-id="de98d-111">In **Modelli installati** della finestra di dialogo **Nuovo progetto**fare clic su **Business Intelligence**, quindi selezionare **Importa da server**.</span><span class="sxs-lookup"><span data-stu-id="de98d-111">In the **New Project** dialog box, under **Installed Templates**, click **Business Intelligence**, and then click **Import from Server**.</span></span>  
  
3.  <span data-ttu-id="de98d-112">In **Nome**digitare un nome per il progetto, quindi specificare un percorso e un nome per la soluzione e scegliere **OK**.</span><span class="sxs-lookup"><span data-stu-id="de98d-112">In **Name**, type a name for the project, then specify a location and solution name, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="de98d-113">In **Nome server** nella finestra di dialogo **Importa da Analysis Services**specificare il nome del server Analysis Services contenente i metadati del modello che si desidera importare.</span><span class="sxs-lookup"><span data-stu-id="de98d-113">In the **Import from Analysis Services** dialog box, in **Server Name**, specify the name of the Analysis Services server that contains the model metadata you want to import.</span></span>  
  
5.  <span data-ttu-id="de98d-114">In **Nome database**selezionare il database modello tabulare in cui sono contenuti i metadati del modello che si desidera importare e scegliere **OK**.</span><span class="sxs-lookup"><span data-stu-id="de98d-114">In **Database Name**, select the tabular model database that contains the model metadata you want to import, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de98d-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="de98d-115">See Also</span></span>  
 [<span data-ttu-id="de98d-116">Proprietà del progetto &#40;SSAS tabulare&#41;</span><span class="sxs-lookup"><span data-stu-id="de98d-116">Project Properties &#40;SSAS Tabular&#41;</span></span>](properties-ssas-tabular.md)  
  
  
