---
title: Creazione di un report di Power View con un'origine dati multidimensionale | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: b9b6f4c9-7e1f-4f61-b657-8986e39a6af2
author: minewiskan
ms.author: owend
ms.openlocfilehash: 179bb9eed94cd0dbb579bdb06d630b213339d12f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721931"
---
# <a name="create-a-power-view-report-with-a-multidimensional-data-source"></a><span data-ttu-id="def09-102">Creare un report Power View con un'origine dati multidimensionale</span><span class="sxs-lookup"><span data-stu-id="def09-102">Create a Power View Report with a Multidimensional Data Source</span></span>
  <span data-ttu-id="def09-103">La creazione di un report Power View basato su un modello multidimensionale non è diversa dalla creazione di un report basato su una cartella di lavoro di PowerPivot o un modello tabulare di Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="def09-103">Creating a Power View report based on a multidimensional model is no different than creating a report based on a PowerPivot workbook or an Analysis Services Tabular model.</span></span> <span data-ttu-id="def09-104">I report Power View vengono creati da un file di connessione all'origine dati del report (con estensione rsds) in una raccolta di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="def09-104">Power View reports are created from a Report Data Source connection file (.rsds) in a SharePoint library.</span></span> <span data-ttu-id="def09-105">Per ulteriori informazioni sulla creazione di un file con estensione rsds, vedere [Create a Report Data Source](create-a-report-data-source.md).</span><span class="sxs-lookup"><span data-stu-id="def09-105">For more information about how to create an .rsds, see [Create a Report Data Source](create-a-report-data-source.md).</span></span>  
  
 <span data-ttu-id="def09-106">Prima di iniziare, è necessario conoscere:</span><span class="sxs-lookup"><span data-stu-id="def09-106">Before you begin, you need to know:</span></span>  
  
-   <span data-ttu-id="def09-107">Il nome e il percorso della raccolta di SharePoint che contiene una connessione all'origine dati del report condivisa (con estensione rsds) in un modello multidimensionale.</span><span class="sxs-lookup"><span data-stu-id="def09-107">The name and location of the SharePoint library that contains a shared report data source connection (.rsds) to a multidimensional model.</span></span>  
  
#### <a name="create-a-new-blank-power-view-report"></a><span data-ttu-id="def09-108">Creare un nuovo report Power View vuoto</span><span class="sxs-lookup"><span data-stu-id="def09-108">Create a new, blank Power View report</span></span>  
  
-   <span data-ttu-id="def09-109">Nella raccolta di SharePoint, fare clic sulla freccia accanto alla connessione all'origine dati del report condivisa (il file con estensione rsds che si connette a un modello multidimensionale) e fare clic su **Crea report Power View**.</span><span class="sxs-lookup"><span data-stu-id="def09-109">In the SharePoint library, click the arrow next to the .rsds shared report data source connection (the .rsds that connects to the multidimensional model), and then click **Create Power View Report**.</span></span>  
  
  
