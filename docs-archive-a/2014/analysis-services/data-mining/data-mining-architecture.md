---
title: Architettura di data mining | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 105f52e1-ad3b-4cd0-b67b-06dbb451c304
author: minewiskan
ms.author: owend
ms.openlocfilehash: a372972fd7fa39f7bcfd2e10abbc4fbf8f8c10aa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636481"
---
# <a name="data-mining-architecture"></a><span data-ttu-id="62b11-102">Architettura di data mining</span><span class="sxs-lookup"><span data-stu-id="62b11-102">Data Mining Architecture</span></span>
  <span data-ttu-id="62b11-103">In questa sezione viene descritta l'architettura delle soluzioni di data mining ospitate in un'istanza di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="62b11-103">This section describes the architecture of data mining solutions that are hosted in an instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="62b11-104">Negli argomenti di questa sezione viene descritta l'architettura logica e fisica di un'istanza di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] che supporta il data mining e vengono fornite informazioni su client, provider e protocolli che è possibile usare per comunicare con i server di data mining e per usare oggetti di data mining in modalità locale o remota.</span><span class="sxs-lookup"><span data-stu-id="62b11-104">The topics in this section describe the logical and physical architecture of an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance that supports data mining, and also provide information about the clients, providers, and protocols that can be used to communicate with data mining servers, and to work with data mining objects either locally or remotely.</span></span>  
  
 <span data-ttu-id="62b11-105">In generale, Data mining di SQL Server funziona come servizio fornito come parte di un'istanza di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] in esecuzione in modalità multidimensionale; pertanto, si consiglia di rivedere anche le sezioni seguenti della Documentazione online in cui vengono descritti il funzionamento, la gestione e la configurazione delle soluzioni multidimensionale di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="62b11-105">In general, SQL Server Data Mining operates as a service that is provided as part of an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance running in multidimensional mode; therefore, we recommend that you also review the following sections of Books Online that describe the operation, maintenance, and configuration of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] multidimensional solutions.</span></span>  
  
 [<span data-ttu-id="62b11-106">Elaborazione di oggetti del modello multidimensionale</span><span class="sxs-lookup"><span data-stu-id="62b11-106">Multidimensional Model Object Processing</span></span>](../multidimensional-models/processing-a-multidimensional-model-analysis-services.md)  
  
 [<span data-ttu-id="62b11-107">Connetti ad Analysis Services</span><span class="sxs-lookup"><span data-stu-id="62b11-107">Connect to Analysis Services</span></span>](../instances/connect-to-analysis-services.md)  
  
 [<span data-ttu-id="62b11-108">Percorso di archiviazione dei database</span><span class="sxs-lookup"><span data-stu-id="62b11-108">Database Storage Location</span></span>](../multidimensional-models/database-storage-location.md)  
  
 [<span data-ttu-id="62b11-109">Passare un database di Analysis Services tra le modalità ReadOnly e ReadWrite</span><span class="sxs-lookup"><span data-stu-id="62b11-109">Switch an Analysis Services database between ReadOnly and ReadWrite modes</span></span>](../multidimensional-models/switch-an-analysis-services-database-between-readonly-and-readwrite-modes.md)  
  
 <span data-ttu-id="62b11-110">Per altre informazioni sulla modalità in cui è possibile implementare di data mining nella soluzione di Business Intelligence, vedere la sezione relativa alle guide alle soluzioni di MSDN Library.</span><span class="sxs-lookup"><span data-stu-id="62b11-110">For more information about how you can implement data mining in your business intelligence solution, see the Solution Guides section of the MSDN Library.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="62b11-111">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="62b11-111">In This Section</span></span>  
 [<span data-ttu-id="62b11-112">Architettura logica &#40;Analysis Services - Data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="62b11-112">Logical Architecture &#40;Analysis Services - Data Mining&#41;</span></span>](logical-architecture-analysis-services-data-mining.md)  
  
 [<span data-ttu-id="62b11-113">Architettura fisica &#40;Analysis Services - Data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="62b11-113">Physical Architecture &#40;Analysis Services - Data Mining&#41;</span></span>](physical-architecture-analysis-services-data-mining.md)  
  
 [<span data-ttu-id="62b11-114">Servizi di data mining e origini dati</span><span class="sxs-lookup"><span data-stu-id="62b11-114">Data Mining Services and Data Sources</span></span>](data-mining-services-and-data-sources.md)  
  
 [<span data-ttu-id="62b11-115">Gestione degli oggetti e delle soluzioni di data mining</span><span class="sxs-lookup"><span data-stu-id="62b11-115">Management of Data Mining Solutions and Objects</span></span>](management-of-data-mining-solutions-and-objects.md)  
  
 [<span data-ttu-id="62b11-116">Panoramica della sicurezza &#40;data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="62b11-116">Security Overview &#40;Data Mining&#41;</span></span>](security-overview-data-mining.md)  
  
## <a name="see-also"></a><span data-ttu-id="62b11-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="62b11-117">See Also</span></span>  
 <span data-ttu-id="62b11-118">[Programmazione di modelli multidimensionali](../multidimensional-models/multidimensional-model-programming.md) </span><span class="sxs-lookup"><span data-stu-id="62b11-118">[Multidimensional Model Programming](../multidimensional-models/multidimensional-model-programming.md) </span></span>  
 [<span data-ttu-id="62b11-119">Programmazione di data mining</span><span class="sxs-lookup"><span data-stu-id="62b11-119">Data Mining Programming</span></span>](../dev-guide/data-mining-programming.md)  
  
  
