---
title: Compilazione di una Knowledge Base | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 51eff161-6ecd-4ee4-8187-1dd8ef4814bd
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 03c9fc6c3a9168a66e8293c61db21a87fadc260f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624976"
---
# <a name="building-a-knowledge-base"></a><span data-ttu-id="1dacc-102">Compilazione di una Knowledge Base</span><span class="sxs-lookup"><span data-stu-id="1dacc-102">Building a Knowledge Base</span></span>
  <span data-ttu-id="1dacc-103">Una Knowledge Base in [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS) è un repository di informazioni sui dati che consente di comprenderli e mantenerne l'integrità.</span><span class="sxs-lookup"><span data-stu-id="1dacc-103">A knowledge base in [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS) is a repository of knowledge about your data that enables you to understand your data and maintain its integrity.</span></span> <span data-ttu-id="1dacc-104">Una Knowledge Base è costituita da domini ognuno dei quali rappresenta i dati in un campo dati.</span><span class="sxs-lookup"><span data-stu-id="1dacc-104">A knowledge base consists of domains, each of which represents the data in a data field.</span></span> <span data-ttu-id="1dacc-105">La Knowledge Base viene utilizzata da DQS per eseguire la pulizia dei dati e la deduplicazione su un database.</span><span class="sxs-lookup"><span data-stu-id="1dacc-105">The knowledge base is used by DQS to perform data cleansing and deduplication on a database.</span></span> <span data-ttu-id="1dacc-106">Per preparare la Knowledge Base per la pulizia dei dati, è possibile eseguire un'analisi computerizzata di un campione di dati e gestire in modo interattivo i valori nei domini.</span><span class="sxs-lookup"><span data-stu-id="1dacc-106">To prepare the knowledge base for data cleansing, you can run a computer-assisted analysis of a data sample, and interactively manage values in the domains.</span></span> <span data-ttu-id="1dacc-107">DQS consente di importare informazioni, creare regole e relazioni, modificare direttamente valori di dati e sfruttare un database predefinito.</span><span class="sxs-lookup"><span data-stu-id="1dacc-107">DQS enables you to import knowledge, create rules and relationships, change data values directly, and leverage a default database.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1dacc-108">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="1dacc-108">In This Section</span></span>  
 <span data-ttu-id="1dacc-109">In una Knowledge Base è possibile effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="1dacc-109">You can perform the following operations on a knowledge base:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1dacc-110">Creare una nuova Knowledge Base da zero, da una Knowledge Base esistente o da un file di dati DQS.</span><span class="sxs-lookup"><span data-stu-id="1dacc-110">Create a new knowledge base from scratch, from an existing knowledge base, or from a .dqs data file.</span></span>|[<span data-ttu-id="1dacc-111">Creare una Knowledge base</span><span class="sxs-lookup"><span data-stu-id="1dacc-111">Create a Knowledge Base</span></span>](../../2014/data-quality-services/create-a-knowledge-base.md)|  
|<span data-ttu-id="1dacc-112">Aprire una Knowledge Base esistente per eseguire l'individuazione delle informazioni e la gestione del dominio o per aggiungere i criteri di corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="1dacc-112">Open an existing knowledge base to perform knowledge discovery, domain management, or add a matching policy.</span></span>|[<span data-ttu-id="1dacc-113">Apertura di una Knowledge Base</span><span class="sxs-lookup"><span data-stu-id="1dacc-113">Open a Knowledge Base</span></span>](../../2014/data-quality-services/open-a-knowledge-base.md)|  
|<span data-ttu-id="1dacc-114">Eseguire azioni di gestione su una Knowledge Base, tra cui l'apertura, lo sblocco, l'annullamento delle modifiche apportatevi, la ridenominazione, l'eliminazione o la visualizzazione delle relative proprietà.</span><span class="sxs-lookup"><span data-stu-id="1dacc-114">Perform management actions on a knowledge base, including opening it, unlocking it, discarding your work on it, renaming it, deleting it, or viewing its properties.</span></span>|[<span data-ttu-id="1dacc-115">Gestire una Knowledge Base</span><span class="sxs-lookup"><span data-stu-id="1dacc-115">Manage a Knowledge Base</span></span>](../../2014/data-quality-services/manage-a-knowledge-base.md)|  
|<span data-ttu-id="1dacc-116">Aggiungere informazioni a una Knowledge Base tramite l'individuazione delle informazioni, la gestione dei valori di dominio, l'aggiunta di criteri di corrispondenza, l'importazione di informazioni, di un dominio o di valori oppure l'utilizzo della Knowledge Base predefinita, Dati DQS.</span><span class="sxs-lookup"><span data-stu-id="1dacc-116">Add knowledge to a knowledge base through knowledge discovery; domain value management; adding a matching policy; importing a knowledge, domain, or values; or using the default knowledge base, DQS Data.</span></span>|[<span data-ttu-id="1dacc-117">Aggiunta di informazioni a una Knowledge Base</span><span class="sxs-lookup"><span data-stu-id="1dacc-117">Adding Knowledge to a Knowledge Base</span></span>](../../2014/data-quality-services/adding-knowledge-to-a-knowledge-base.md)|  
|<span data-ttu-id="1dacc-118">Analizzare un campione di dati per i criteri di qualità dei dati.</span><span class="sxs-lookup"><span data-stu-id="1dacc-118">Analyze a data sample for data quality criteria.</span></span>|[<span data-ttu-id="1dacc-119">Esecuzione dell'individuazione delle informazioni</span><span class="sxs-lookup"><span data-stu-id="1dacc-119">Perform Knowledge Discovery</span></span>](../../2014/data-quality-services/perform-knowledge-discovery.md)|  
  
## <a name="related-tasks"></a><span data-ttu-id="1dacc-120">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="1dacc-120">Related Tasks</span></span>  
  
|<span data-ttu-id="1dacc-121">Descrizione dell'attività</span><span class="sxs-lookup"><span data-stu-id="1dacc-121">Task Description</span></span>|<span data-ttu-id="1dacc-122">Argomento</span><span class="sxs-lookup"><span data-stu-id="1dacc-122">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="1dacc-123">Importazione o esportazione di informazioni da una Knowledge Base.</span><span class="sxs-lookup"><span data-stu-id="1dacc-123">Importing knowledge into, or exporting it from, a knowledge base.</span></span>|[<span data-ttu-id="1dacc-124">Importazione ed esportazione delle informazioni</span><span class="sxs-lookup"><span data-stu-id="1dacc-124">Importing and Exporting Knowledge</span></span>](../../2014/data-quality-services/importing-and-exporting-knowledge.md)|  
|<span data-ttu-id="1dacc-125">Creazione di un singolo dominio e aggiunta di informazioni al dominio.</span><span class="sxs-lookup"><span data-stu-id="1dacc-125">Creating a single domain, and adding knowledge to the domain.</span></span>|[<span data-ttu-id="1dacc-126">Gestione di un dominio</span><span class="sxs-lookup"><span data-stu-id="1dacc-126">Managing a Domain</span></span>](../../2014/data-quality-services/managing-a-domain.md)|  
|<span data-ttu-id="1dacc-127">Creazione di un dominio composito e aggiunta di informazioni al dominio.</span><span class="sxs-lookup"><span data-stu-id="1dacc-127">Creating a composite domain, and adding knowledge to the domain.</span></span>|[<span data-ttu-id="1dacc-128">Gestione di un dominio composito</span><span class="sxs-lookup"><span data-stu-id="1dacc-128">Managing a Composite Domain</span></span>](../../2014/data-quality-services/managing-a-composite-domain.md)|  
  
  
