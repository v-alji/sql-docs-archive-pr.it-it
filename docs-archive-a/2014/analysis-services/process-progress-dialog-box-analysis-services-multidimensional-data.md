---
title: Finestra di dialogo Stato elaborazione (Analysis Services-Dati multidimensionali) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.processprogress.f1
ms.assetid: f3bd5278-3a83-4fd9-9903-e81bdd4b6892
author: minewiskan
ms.author: owend
ms.openlocfilehash: 4e436eeab21a37ae174a5003c01e77c05240238b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725035"
---
# <a name="process-progress-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="ab9f8-102">Finestra di dialogo Stato elaborazione (Analysis Services - Dati multidimensionali)</span><span class="sxs-lookup"><span data-stu-id="ab9f8-102">Process Progress Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="ab9f8-103">Utilizzare la finestra di dialogo **Stato elaborazione** in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] e in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] per monitorare l'elaborazione in [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ab9f8-103">Use the **Process Progress** dialog box in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] and [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to monitor processing in [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="ab9f8-104">La finestra di dialogo **Stato elaborazione** viene visualizzata all'inizio dell'elaborazione in un oggetto [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ab9f8-104">The **Process Progress** dialog box appears when processing begins on an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] object.</span></span>  
  
## <a name="options"></a><span data-ttu-id="ab9f8-105">Opzioni</span><span class="sxs-lookup"><span data-stu-id="ab9f8-105">Options</span></span>  
 <span data-ttu-id="ab9f8-106">**Visualizzazione Albero stato**</span><span class="sxs-lookup"><span data-stu-id="ab9f8-106">**Status tree view**</span></span>  
 <span data-ttu-id="ab9f8-107">Consente di visualizzare i messaggi di stato dell'istanza di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] relativi agli oggetti in fase di elaborazione, tra cui l'ora di inizio, l'ora di arresto e le informazioni di stato.</span><span class="sxs-lookup"><span data-stu-id="ab9f8-107">Displays status messages from the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance regarding the objects being processed, including start time, stop time, and progress information.</span></span> <span data-ttu-id="ab9f8-108">Fare clic con il pulsante destro del mouse su un elemento e scegliere **Copia** per copiare i dettagli di un messaggio di stato negli Appunti oppure fare doppio clic su un elemento per visualizzare la finestra di dialogo **Visualizza dettagli**.</span><span class="sxs-lookup"><span data-stu-id="ab9f8-108">Right-click an item and select **Copy** to copy the details of a status message to the clipboard, or double-click an item to display the **View Details** dialog box.</span></span> <span data-ttu-id="ab9f8-109">Per altre informazioni sulla finestra di dialogo **Visualizza dettagli** vedere [Finestra di dialogo Visualizza dettagli &#40;Analysis Services - Dati multidimensionali&#41;](view-details-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="ab9f8-109">For more information about the **View Details** dialog box, see [View Details Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](view-details-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="ab9f8-110">**Descrizione dello stato**</span><span class="sxs-lookup"><span data-stu-id="ab9f8-110">**Status description**</span></span>  
 <span data-ttu-id="ab9f8-111">Consente di visualizzare lo stato corrente dell'operazione di elaborazione.</span><span class="sxs-lookup"><span data-stu-id="ab9f8-111">Displays the current status of the processing operation.</span></span>  
  
 <span data-ttu-id="ab9f8-112">**Stop**</span><span class="sxs-lookup"><span data-stu-id="ab9f8-112">**Stop**</span></span>  
 <span data-ttu-id="ab9f8-113">Fare clic su questo pulsante per arrestare l'operazione di elaborazione.</span><span class="sxs-lookup"><span data-stu-id="ab9f8-113">Click to stop the processing operation.</span></span>  
  
 <span data-ttu-id="ab9f8-114">**Rielabora**</span><span class="sxs-lookup"><span data-stu-id="ab9f8-114">**Reprocess**</span></span>  
 <span data-ttu-id="ab9f8-115">Fare clic su questo pulsante per ripetere l'operazione di elaborazione che ha determinato la visualizzazione della finestra di dialogo **Stato elaborazione** .</span><span class="sxs-lookup"><span data-stu-id="ab9f8-115">Click to repeat the processing operation that displayed the **Process Progress** dialog box.</span></span>  
  
 <span data-ttu-id="ab9f8-116">**Visualizza dettagli**</span><span class="sxs-lookup"><span data-stu-id="ab9f8-116">**View Details**</span></span>  
 <span data-ttu-id="ab9f8-117">Fare clic su questo pulsante per aprire la finestra di dialogo **Visualizza dettagli** e visualizzare i dettagli relativi all'elemento selezionato nella visualizzazione **Albero stato**.</span><span class="sxs-lookup"><span data-stu-id="ab9f8-117">Click to open the **View Details** dialog box and display details regarding the item selected in **Status tree view**.</span></span> <span data-ttu-id="ab9f8-118">Per altre informazioni sulla finestra di dialogo **Visualizza dettagli** vedere [Finestra di dialogo Visualizza dettagli &#40;Analysis Services - Dati multidimensionali&#41;](view-details-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="ab9f8-118">For more information about the **View Details** dialog box, see [View Details Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](view-details-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab9f8-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ab9f8-119">See Also</span></span>  
 <span data-ttu-id="ab9f8-120">[Finestre di progettazione e finestre di dialogo Analysis Services &#40;dati multidimensionali&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="ab9f8-120">[Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="ab9f8-121">Elaborazione di oggetti del modello multidimensionale</span><span class="sxs-lookup"><span data-stu-id="ab9f8-121">Multidimensional Model Object Processing</span></span>](multidimensional-models/processing-a-multidimensional-model-analysis-services.md)  
  
  
