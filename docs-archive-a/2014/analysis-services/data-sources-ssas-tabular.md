---
title: Origini dati (SSAS tabulare) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 6908998b-9302-4a90-976e-770106b48d18
author: minewiskan
ms.author: owend
ms.openlocfilehash: d686d8100e30d7608e8d90f135022bdf46785723
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716960"
---
# <a name="data-sources-ssas-tabular"></a><span data-ttu-id="f9966-102">Origini dati (SSAS tabulare)</span><span class="sxs-lookup"><span data-stu-id="f9966-102">Data Sources (SSAS Tabular)</span></span>
  <span data-ttu-id="f9966-103">Le origini dati forniscono i dati da includere in una soluzione del modello tabulare.</span><span class="sxs-lookup"><span data-stu-id="f9966-103">Data sources provide the data to be included in a tabular model solution.</span></span> <span data-ttu-id="f9966-104">È possibile importare dati nel modello da diverse origini quali database relazionali, feed di dati, origini dati multidimensionali come un cubo di Analysis Services, nonché da file di testo quale una cartella di lavoro di Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="f9966-104">You can import data into your model from a wide variety of sources such as relational databases, data feeds, multidimensional data sources such as an Analysis Services cube, and from text files such as a Microsoft Excel workbook.</span></span> <span data-ttu-id="f9966-105">Negli argomenti contenuti in questa sezione vengono fornite informazioni sui tipi di origini dati da cui è possibile eseguire un'importazione, sui vari tipi di dati che è possibile importare, nonché sulle attività in cui viene descritto come importare i dati da tali origini.</span><span class="sxs-lookup"><span data-stu-id="f9966-105">Topics in this section provide information about the types of data sources you can import from, the various data types you can import, and tasks describing how to import data from those sources.</span></span>  
  
## <a name="related-topics-and-tasks"></a><span data-ttu-id="f9966-106">Attività e argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="f9966-106">Related Topics and Tasks</span></span>  
  
|<span data-ttu-id="f9966-107">Argomento</span><span class="sxs-lookup"><span data-stu-id="f9966-107">Topic</span></span>|<span data-ttu-id="f9966-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f9966-108">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="f9966-109">Origini dati supportate &#40;SSAS tabulare&#41;</span><span class="sxs-lookup"><span data-stu-id="f9966-109">Data Sources Supported &#40;SSAS Tabular&#41;</span></span>](tabular-models/data-sources-supported-ssas-tabular.md)|<span data-ttu-id="f9966-110">In questo argomento vengono fornite informazioni sulle origini dati diverse da cui è possibile eseguire un'importazione.</span><span class="sxs-lookup"><span data-stu-id="f9966-110">This topic provides information about the different data sources that you can import data from.</span></span>|  
|[<span data-ttu-id="f9966-111">Tipi di dati supportati &#40;SSAS tabulare&#41;</span><span class="sxs-lookup"><span data-stu-id="f9966-111">Data Types Supported &#40;SSAS Tabular&#41;</span></span>](tabular-models/data-types-supported-ssas-tabular.md)|<span data-ttu-id="f9966-112">In questo argomento vengono fornite informazioni sui vari tipi di dati supportati in un modello tabulare.</span><span class="sxs-lookup"><span data-stu-id="f9966-112">This topic provides information about the various data types that are supported in a Tabular Model.</span></span>|  
|[<span data-ttu-id="f9966-113">Rappresentazione &#40;SSAS tabulare&#41;</span><span class="sxs-lookup"><span data-stu-id="f9966-113">Impersonation &#40;SSAS Tabular&#41;</span></span>](tabular-models/impersonation-ssas-tabular.md)|<span data-ttu-id="f9966-114">In questo argomento sono contenute informazioni sulla rappresentazione, che fornisce le credenziali di accesso utilizzate da Analysis Services in caso di connessione a un'origine dati per importare e aggiornare dati.</span><span class="sxs-lookup"><span data-stu-id="f9966-114">This topic provides information about impersonation, which provides logon credentials that are used by Analysis Services when connecting to a data source to import and refresh data.</span></span>|  
|[<span data-ttu-id="f9966-115">Importare dati &#40;SSAS tabulare&#41;</span><span class="sxs-lookup"><span data-stu-id="f9966-115">Import Data &#40;SSAS Tabular&#41;</span></span>](import-data-ssas-tabular.md)|<span data-ttu-id="f9966-116">Nelle attività contenute in questa sezione viene descritto come importare dati da origini dati diverse.</span><span class="sxs-lookup"><span data-stu-id="f9966-116">Tasks in this section describe how to import data from different data sources.</span></span>|  
|[<span data-ttu-id="f9966-117">Elaborare dati &#40;SSAS tabulare&#41;</span><span class="sxs-lookup"><span data-stu-id="f9966-117">Process Data &#40;SSAS Tabular&#41;</span></span>](process-data-ssas-tabular.md)|<span data-ttu-id="f9966-118">Nelle attività contenute in questa sezione viene descritto come elaborare (aggiornare) o modificare dati che sono già stati importati in un modello.</span><span class="sxs-lookup"><span data-stu-id="f9966-118">Tasks in this section describe how to process (refresh) or change data that has already been imported into a model.</span></span>|  
|[<span data-ttu-id="f9966-119">Modificare una connessione all'origine dati esistente &#40;SSAS tabulare&#41;</span><span class="sxs-lookup"><span data-stu-id="f9966-119">Edit an Existing Data Source Connection &#40;SSAS Tabular&#41;</span></span>](edit-an-existing-data-source-connection-ssas-tabular.md)|<span data-ttu-id="f9966-120">Viene descritto come modificare una connessione all'origine dati già creata e utilizzata per importare dati da un'origine.</span><span class="sxs-lookup"><span data-stu-id="f9966-120">Describes how to edit a data source connection that has already been created and used to import data from a source.</span></span>|  
  
  
