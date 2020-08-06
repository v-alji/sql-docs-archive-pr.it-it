---
title: Posizioni di elaborazione e archiviazione (creazione guidata partizione) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.partitionwizard.specifyprocessingandstorage.f1
ms.assetid: dda2dc57-923d-4db9-93a7-38e95770f3df
author: minewiskan
ms.author: owend
ms.openlocfilehash: 00ab88bac184f57bd2b4dcfdb8d00909a85ece4f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725032"
---
# <a name="processing-and-storage-locations-partition-wizard"></a><span data-ttu-id="25c67-102">Posizioni di elaborazione e archiviazione (Creazione guidata partizione)</span><span class="sxs-lookup"><span data-stu-id="25c67-102">Processing and Storage Locations (Partition Wizard)</span></span>
  <span data-ttu-id="25c67-103">La pagina **Posizioni di elaborazione e archiviazione** consente di specificare l'istanza di [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] del cubo proprietario della partizione e l'istanza di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] in cui sono archiviati i dati per la partizione.</span><span class="sxs-lookup"><span data-stu-id="25c67-103">Use the **Processing and Storage Locations** page to specify the [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance of the cube that owns the partition, as well as the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance that stores the data for the partition.</span></span> <span data-ttu-id="25c67-104">La partizione può essere definita come partizione remota specificando un'istanza di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] remota o una posizione di archiviazione diversa da quella predefinita.</span><span class="sxs-lookup"><span data-stu-id="25c67-104">You can define a partition as a remote partition by specifying either a remote [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance or a storage location other than the default storage location.</span></span> <span data-ttu-id="25c67-105">Per altre informazioni sulle partizioni remote, vedere [Partizioni remote](multidimensional-models-olap-logical-cube-objects/partitions-remote-partitions.md).</span><span class="sxs-lookup"><span data-stu-id="25c67-105">For more information about remote partitions, see [Remote Partitions](multidimensional-models-olap-logical-cube-objects/partitions-remote-partitions.md).</span></span>  
  
## <a name="processing-location-options"></a><span data-ttu-id="25c67-106">Opzioni Posizione di elaborazione</span><span class="sxs-lookup"><span data-stu-id="25c67-106">Processing location Options</span></span>  
 <span data-ttu-id="25c67-107">**Istanza server corrente**</span><span class="sxs-lookup"><span data-stu-id="25c67-107">**Current server instance**</span></span>  
 <span data-ttu-id="25c67-108">Specifica l'istanza di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] corrente come responsabile dell'elaborazione della partizione.</span><span class="sxs-lookup"><span data-stu-id="25c67-108">Makes the current [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance responsible for processing the partition.</span></span>  
  
 <span data-ttu-id="25c67-109">**Origine dati remota di Analysis Services**</span><span class="sxs-lookup"><span data-stu-id="25c67-109">**Remote Analysis Services data source**</span></span>  
 <span data-ttu-id="25c67-110">Specifica l'istanza di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] remota come responsabile dell'elaborazione della partizione.</span><span class="sxs-lookup"><span data-stu-id="25c67-110">Makes a remote [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance responsible for processing this partition.</span></span>  
  
 <span data-ttu-id="25c67-111">Selezionare nell'elenco a discesa l'origine dei dati che rappresenta l'istanza di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] remota che sarà responsabile per l'elaborazione della partizione.</span><span class="sxs-lookup"><span data-stu-id="25c67-111">From the dropdown list, select the data source representing the remote [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance that will be responsible for processing the partition.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="25c67-112">Se si seleziona un'origine dei dati in cui la proprietà della stringa di connessione `Initial Catalog` non è impostata su un database di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] valido oppure se il database specificato nella proprietà della stringa di connessione `Initial Catalog` non supporta le partizioni remote (ovvero la proprietà `MasterDatasourceID` del database specificato non è impostata su un valore valido), si verifica un errore.</span><span class="sxs-lookup"><span data-stu-id="25c67-112">An error occurs if you select a data source in which the `Initial Catalog` connection string property is not set to a valid [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database, or if the database specified in the `Initial Catalog` connection string property does not support remote partitions (in other words, the `MasterDatasourceID` property of the specified database is not set to a valid value).</span></span>  
  
 <span data-ttu-id="25c67-113">**Nuovo**</span><span class="sxs-lookup"><span data-stu-id="25c67-113">**New**</span></span>  
 <span data-ttu-id="25c67-114">Consente di creare una nuova origine dei dati che rappresenta l'istanza di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] remota responsabile dell'elaborazione della partizione.</span><span class="sxs-lookup"><span data-stu-id="25c67-114">Creates a new data source representing the remote [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance responsible for processing the partition.</span></span>  
  
## <a name="storage-location-options"></a><span data-ttu-id="25c67-115">Opzioni Percorso di archiviazione</span><span class="sxs-lookup"><span data-stu-id="25c67-115">Storage location Options</span></span>  
 <span data-ttu-id="25c67-116">**Percorso server predefinito**</span><span class="sxs-lookup"><span data-stu-id="25c67-116">**Default server location**</span></span>  
 <span data-ttu-id="25c67-117">Specifica la cartella dati dell'istanza corrente di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] come percorso di archiviazione dei dati di aggregazione e indicizzazione per la partizione.</span><span class="sxs-lookup"><span data-stu-id="25c67-117">Makes the data folder of the current [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance the storage location of the aggregation and indexing data for the partition.</span></span>  
  
 <span data-ttu-id="25c67-118">**Cartella specificata**</span><span class="sxs-lookup"><span data-stu-id="25c67-118">**Specified folder**</span></span>  
 <span data-ttu-id="25c67-119">Specifica il percorso di archiviazione dei dati di aggregazione e indicizzazione per la partizione.</span><span class="sxs-lookup"><span data-stu-id="25c67-119">Specifies the storage location of the aggregation and indexing data for the partition.</span></span>  
  
 <span data-ttu-id="25c67-120">**...**</span><span class="sxs-lookup"><span data-stu-id="25c67-120">**...**</span></span>  
 <span data-ttu-id="25c67-121">Consente di visualizzare la finestra di dialogo **Cerca cartella remota** in cui è possibile selezionare una cartella per **Cartella specificata**.</span><span class="sxs-lookup"><span data-stu-id="25c67-121">Displays the **Browse for Remote Folder** dialog box in which you can select a folder for **Specified folder**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25c67-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="25c67-122">See Also</span></span>  
 <span data-ttu-id="25c67-123">[Guida sensibile al contesto della creazione guidata partizione &#40;Analysis Services-Dati multidimensionali&#41;](partition-wizard-f1-help-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="25c67-123">[Partition Wizard F1 Help &#40;Analysis Services - Multidimensional Data&#41;](partition-wizard-f1-help-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="25c67-124">[Partizioni &#40;Analysis Services Dati multidimensionali&#41;](multidimensional-models-olap-logical-cube-objects/partitions-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="25c67-124">[Partitions &#40;Analysis Services - Multidimensional Data&#41;](multidimensional-models-olap-logical-cube-objects/partitions-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="25c67-125">Finestra di dialogo Cerca cartella remota &#40;Analysis Services-Dati multidimensionali&#41;</span><span class="sxs-lookup"><span data-stu-id="25c67-125">Browse for Remote Folder Dialog Box &#40;Analysis Services - Multidimensional Data&#41;</span></span>](browse-for-remote-folder-dialog-box-analysis-services-multidimensional-data.md)  
  
  
