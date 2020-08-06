---
title: Proprietà report Power View (SSAS tabulare) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 51205c2d-b6ce-4b92-afd2-58e399a81691
author: minewiskan
ms.author: owend
ms.openlocfilehash: e85d91578e5c3f4b47f56eeb86aa738e37e8f59b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712455"
---
# <a name="power-view-reporting-properties-ssas-tabular"></a><span data-ttu-id="fb0d6-102">Proprietà report Power View (SSAS tabulare)</span><span class="sxs-lookup"><span data-stu-id="fb0d6-102">Power View Reporting Properties (SSAS Tabular)</span></span>
  [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)] <span data-ttu-id="fb0d6-103">fornisce intuitive funzionalità di report ad hoc per utenti aziendali quali analisti dei dati, decisori aziendali e Information Worker.</span><span class="sxs-lookup"><span data-stu-id="fb0d6-103">provides intuitive ad-hoc reporting for business users such as data analysts, business decision makers, and information workers.</span></span> <span data-ttu-id="fb0d6-104">Questi utenti potranno creare e interagire con facilità con le visualizzazioni dei dati da modelli tabulari basati su cartelle di lavoro di PowerPivot pubblicate in un raccolta PowerPivot o da modelli tabulari creati utilizzando [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] e distribuiti nelle istanze di [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="fb0d6-104">They can easily create and interact with views of data from tabular models based on PowerPivot workbooks published in a PowerPivot Gallery, or tabular models authored by using [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] and then deployed to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Analysis Services instances.</span></span> [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)] <span data-ttu-id="fb0d6-105">è un'applicazione Silverlight basata su browser avviata da SharePoint Server 2010 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="fb0d6-105">is a browser-based Silverlight application launched from SharePoint Server 2010 or later.</span></span>  
  
 <span data-ttu-id="fb0d6-106">Quando si creano progetti di modelli tabulari in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], è possibile configurare determinate proprietà del report univoche dei report [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fb0d6-106">When authoring tabular model projects in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], you can configure certain reporting properties unique to [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)] reports.</span></span> <span data-ttu-id="fb0d6-107">Negli argomenti di questa sezione viene spiegata la modalità di ottimizzazione di un modello per migliorare l'esperienza di creazione dei report in [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fb0d6-107">Topics in this section describe how to optimize a model to improve the reporting experience in [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)].</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="fb0d6-108">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="fb0d6-108">Related Tasks</span></span>  
  
|<span data-ttu-id="fb0d6-109">Argomento</span><span class="sxs-lookup"><span data-stu-id="fb0d6-109">Topic</span></span>|<span data-ttu-id="fb0d6-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fb0d6-110">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="fb0d6-111">Configurare il set di campi predefiniti per i report Power View &#40;SSAS tabulare&#41;</span><span class="sxs-lookup"><span data-stu-id="fb0d6-111">Configure Default Field Set for Power View Reports &#40;SSAS Tabular&#41;</span></span>](power-view-configure-default-field-set-for-reports.md)|<span data-ttu-id="fb0d6-112">Si illustra come configurare un set di campi predefinito, ovvero un elenco predefinito di colonne e misure che vengono aggiunte automaticamente all'area di disegno di un report [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)] quando viene selezionata la tabella nell'elenco dei campi del report.</span><span class="sxs-lookup"><span data-stu-id="fb0d6-112">Describes how to configure a Default Field Set; a predefined list of columns and measures that are automatically added to a [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)] report canvas when the table is selected in the report field list.</span></span>|  
|[<span data-ttu-id="fb0d6-113">Configurare le proprietà Comportamento tabella per i report Power View &#40;SSAS tabulare&#41;</span><span class="sxs-lookup"><span data-stu-id="fb0d6-113">Configure Table Behavior Properties for Power View Reports &#40;SSAS Tabular&#41;</span></span>](power-view-configure-table-behavior-properties-for-reports.md)|<span data-ttu-id="fb0d6-114">Si illustra come configurare le proprietà del comportamento della tabella che espongono righe di dettaglio a un livello più granulare.</span><span class="sxs-lookup"><span data-stu-id="fb0d6-114">Describes how to configure table behavior properties that expose detail rows at a more granular level.</span></span> <span data-ttu-id="fb0d6-115">L'impostazione delle proprietà del comportamento delle tabelle comporta la modifica del comportamento di raggruppamento delle righe di dettaglio e offre una posizione predefinita migliore per le informazioni di identificazione nei layout di sezioni, schede e grafici.</span><span class="sxs-lookup"><span data-stu-id="fb0d6-115">Setting table behavior properties changes the grouping behavior of detail rows and produces a better default placement of identifying information in tile, card, and chart layouts.</span></span>|  
  
  
