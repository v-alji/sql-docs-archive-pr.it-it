---
title: Modellazione tabulare (SSAS tabulare) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 80027288-c203-4667-a3e1-40fa572b4975
author: minewiskan
ms.author: owend
ms.openlocfilehash: 44f358f0f36e84ad903a0a4fcb0203291019e7aa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626315"
---
# <a name="tabular-modeling-ssas-tabular"></a><span data-ttu-id="0c19f-102">Modellazione tabulare (SSAS tabulare)</span><span class="sxs-lookup"><span data-stu-id="0c19f-102">Tabular Modeling (SSAS Tabular)</span></span>
  <span data-ttu-id="0c19f-103">I modelli tabulari sono database in memoria in Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="0c19f-103">Tabular models are in-memory databases in Analysis Services.</span></span> <span data-ttu-id="0c19f-104">Utilizzando un processore di query multithreading e algoritmi di compressione all'avanguardia, il motore di analisi in memoria xVelocity (VertiPaq) offre accesso rapido ai dati e agli oggetti del modello tabulare mediante applicazioni client di creazione di report quali Microsoft Excel e Microsoft [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0c19f-104">Using state-of-the-art compression algorithms and multi-threaded query processor, the xVelocity in-memory analytics engine (VertiPaq) delivers fast access to tabular model objects and data by reporting client applications such as Microsoft Excel and Microsoft [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)].</span></span>  
  
 <span data-ttu-id="0c19f-105">I modelli tabulari supportano l'accesso ai dati tramite due modalità, ovvero cache e DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="0c19f-105">Tabular models support data access through two modes: Cached mode and DirectQuery mode.</span></span> <span data-ttu-id="0c19f-106">In modalità cache, è possibile integrare i dati da più origini, tra cui database relazionali, feed di dati e file di testo.</span><span class="sxs-lookup"><span data-stu-id="0c19f-106">In cached mode, you can integrate data from multiple sources including relational databases, data feeds, and flat text files.</span></span> <span data-ttu-id="0c19f-107">In modalità DirectQuery, è possibile ignorare il modello in memoria, consentendo l'esecuzione di una query sui dati direttamente nell'origine (database relazionale di SQL Server) da parte delle applicazioni client.</span><span class="sxs-lookup"><span data-stu-id="0c19f-107">In DirectQuery mode, you can bypass the in-memory model, allowing client applications to query data directly at the (SQL Server relational) source.</span></span>  
  
 <span data-ttu-id="0c19f-108">I modelli tabulari vengono creati in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] utilizzando nuovi modelli relativi al modello di progetto tabulare.</span><span class="sxs-lookup"><span data-stu-id="0c19f-108">Tabular models are authored in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] using new tabular model project templates.</span></span> <span data-ttu-id="0c19f-109">È possibile importare i dati da più origini e migliorare il modello aggiungendo relazioni, colonne calcolate, misure, indicatori KPI e gerarchie.</span><span class="sxs-lookup"><span data-stu-id="0c19f-109">You can import data from multiple sources, and then enrich the model by adding relationships, calculated columns, measures, KPIs, and hierarchies.</span></span> <span data-ttu-id="0c19f-110">I modelli possono quindi essere distribuiti in un'istanza di Analysis Services dove, tramite applicazioni client di creazione di report, è possibile effettuare la connessione a tali modelli.</span><span class="sxs-lookup"><span data-stu-id="0c19f-110">Models can then be deployed to an instance of Analysis Services where client reporting applications can connect to them.</span></span> <span data-ttu-id="0c19f-111">I modelli distribuiti possono essere gestiti in SQL Server Management Studio solo come modelli multidimensionali.</span><span class="sxs-lookup"><span data-stu-id="0c19f-111">Deployed models can be managed in SQL Server Management Studio just like multidimensional models.</span></span> <span data-ttu-id="0c19f-112">Tali modelli, inoltre, possono essere partizionati per elaborazioni ottimizzate e protetti a livello di riga tramite ruoli basati sulla sicurezza.</span><span class="sxs-lookup"><span data-stu-id="0c19f-112">They can also be partitioned for optimized processing and secured to the row-level by using role based security.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0c19f-113">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="0c19f-113">In This Section</span></span>  
 [<span data-ttu-id="0c19f-114">Soluzioni di modelli tabulari &#40;SSAS tabulare&#41;</span><span class="sxs-lookup"><span data-stu-id="0c19f-114">Tabular Model Solutions &#40;SSAS Tabular&#41;</span></span>](../tabular-model-solutions-ssas-tabular.md)  
  
 [<span data-ttu-id="0c19f-115">Database modello tabulare &#40;SSAS tabulare&#41;</span><span class="sxs-lookup"><span data-stu-id="0c19f-115">Tabular Model Databases &#40;SSAS Tabular&#41;</span></span>](tabular-model-databases-ssas-tabular.md)  
  
 [<span data-ttu-id="0c19f-116">Accesso ai dati di modello tabulare</span><span class="sxs-lookup"><span data-stu-id="0c19f-116">Tabular Model Data Access</span></span>](tabular-model-data-access.md)  
  
  
