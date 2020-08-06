---
title: Modellazione multidimensionale (SSAS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 509df042-fdb3-4e2c-a6b8-86943ce1b0fc
author: minewiskan
ms.author: owend
ms.openlocfilehash: 7348a932eccb62f2e00c0b154ca9efc8086fcd1f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727251"
---
# <a name="multidimensional-modeling-ssas"></a><span data-ttu-id="4fe24-102">Modellazione multidimensionale (SSAS)</span><span class="sxs-lookup"><span data-stu-id="4fe24-102">Multidimensional Modeling (SSAS)</span></span>
  <span data-ttu-id="4fe24-103">Una soluzione multidimensionale Analysis Services utilizza strutture cubo per l'analisi dei dati aziendali in più dimensioni.</span><span class="sxs-lookup"><span data-stu-id="4fe24-103">An Analysis Services multidimensional solution uses cube structures for analyzing business data across multiple dimensions.</span></span> <span data-ttu-id="4fe24-104">La modalità multidimensionale è la modalità server predefinita di Analysis Services,</span><span class="sxs-lookup"><span data-stu-id="4fe24-104">Multidimensional mode is the default server mode of Analysis Services.</span></span> <span data-ttu-id="4fe24-105">in cui sono inclusi una query e un motore di calcolo per i dati OLAP, con modalità di archiviazione MOLAP, ROLAP e HOLAP per bilanciare prestazioni con requisiti di dati scalabili.</span><span class="sxs-lookup"><span data-stu-id="4fe24-105">It includes a query and calculation engine for OLAP data, with MOLAP, ROLAP, and HOLAP storage modes to balance performance with scalable data requirements.</span></span> <span data-ttu-id="4fe24-106">Il motore OLAP di Analysis Services è il server OLAP leader del settore che offre ottimi risultati con un'ampia gamma di strumenti di Business Intelligence.</span><span class="sxs-lookup"><span data-stu-id="4fe24-106">The Analysis Services OLAP engine is an industry leading OLAP server that works well with a broad range of BI tools.</span></span> <span data-ttu-id="4fe24-107">La maggior parte delle distribuzioni di Analysis Services viene installata come server OLAP classico.</span><span class="sxs-lookup"><span data-stu-id="4fe24-107">Most Analysis Services deployments are installed as classic OLAP servers.</span></span>  
  
## <a name="benefits-of-using-multidimensional-solutions"></a><span data-ttu-id="4fe24-108">Vantaggi dell'utilizzo di soluzioni multidimensionali</span><span class="sxs-lookup"><span data-stu-id="4fe24-108">Benefits of Using Multidimensional Solutions</span></span>  
 <span data-ttu-id="4fe24-109">Il motivo primario per la compilazione di un modello multidimensionale di Analysis Services è la realizzazione di prestazioni veloci delle query a hoc sui dati aziendali.</span><span class="sxs-lookup"><span data-stu-id="4fe24-109">The primary reason for building an Analysis Services multidimensional model is to achieve fast performance of ad hoc queries against business data.</span></span> <span data-ttu-id="4fe24-110">Un modello multidimensionale è costituito da cubi e dimensioni che possono essere annotati ed estesi per supportare costruzioni di query complesse.</span><span class="sxs-lookup"><span data-stu-id="4fe24-110">A multidimensional model is composed of cubes and dimensions that can be annotated and extended to support complex query constructions.</span></span> <span data-ttu-id="4fe24-111">Gli sviluppatori di soluzioni di Business Intelligence creano cubi per supportare tempi di risposta rapidi e fornire una sola origine dati per la creazione di report aziendali.</span><span class="sxs-lookup"><span data-stu-id="4fe24-111">BI developers create cubes to support fast response times, and to provide a single data source for business reporting.</span></span> <span data-ttu-id="4fe24-112">Data l'importanza crescente della Business Intelligence a tutti i livelli di un'organizzazione, la disponibilità una singola origine di dati analitici assicura che le discrepanze siano limitate al minimo, se non eliminate completamente.</span><span class="sxs-lookup"><span data-stu-id="4fe24-112">Given the growing importance of business intelligence across all levels of an organization, having a single source of analytical data ensures that discrepancies are kept to a minimum, if not eliminated entirely.</span></span>  
  
 <span data-ttu-id="4fe24-113">Un altro importante vantaggio all'utilizzo di database multidimensionali di Analysis Services è l'integrazione con gli strumenti di generazione report di BI di uso comune quali Excel, Reporting Services e PerformancePoint, nonché di applicazioni personalizzate e soluzioni di terze parti.</span><span class="sxs-lookup"><span data-stu-id="4fe24-113">Another important benefit to using Analysis Services multidimensional databases is integration with commonly used BI reporting tools such as Excel, Reporting Services, and PerformancePoint, as well as custom applications and third-party solutions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4fe24-114">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="4fe24-114">In This Section</span></span>  
 [<span data-ttu-id="4fe24-115">Soluzioni di modelli multidimensionali &#40;SSAS&#41;</span><span class="sxs-lookup"><span data-stu-id="4fe24-115">Multidimensional Model Solutions &#40;SSAS&#41;</span></span>](multidimensional-model-solutions-ssas.md)  
  
 [<span data-ttu-id="4fe24-116">Database modelli multidimensionali &#40;SSAS&#41;</span><span class="sxs-lookup"><span data-stu-id="4fe24-116">Multidimensional Model Databases &#40;SSAS&#41;</span></span>](multidimensional-model-databases-ssas.md)  
  
 [<span data-ttu-id="4fe24-117">Elaborazione di oggetti del modello multidimensionale</span><span class="sxs-lookup"><span data-stu-id="4fe24-117">Multidimensional Model Object Processing</span></span>](processing-a-multidimensional-model-analysis-services.md)  
  
 [<span data-ttu-id="4fe24-118">Ruoli e autorizzazioni &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="4fe24-118">Roles and Permissions &#40;Analysis Services&#41;</span></span>](roles-and-permissions-analysis-services.md)  
  
 [<span data-ttu-id="4fe24-119">Power View per i modelli multidimensionali</span><span class="sxs-lookup"><span data-stu-id="4fe24-119">Power View for Multidimensional Models</span></span>](power-view-for-multidimensional-models.md)  
  
 [<span data-ttu-id="4fe24-120">Gestione di assembly di modelli multidimensionali</span><span class="sxs-lookup"><span data-stu-id="4fe24-120">Multidimensional Model Assemblies Management</span></span>](multidimensional-model-assemblies-management.md)  
  
  
