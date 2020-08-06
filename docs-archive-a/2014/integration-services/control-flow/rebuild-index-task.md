---
title: Attività Ricompila indice | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.rebuildindextask.f1
helpviewer_keywords:
- rebuilding indexes
- indexes [Integration Services]
- Rebuild Index task
ms.assetid: 021884dd-e72d-47b2-99e8-b741410509c3
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 33bbe25bc8c47f4f749f95dbb7096c3a76c25297
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629965"
---
# <a name="rebuild-index-task"></a><span data-ttu-id="522cc-102">Ricompila indice - attività</span><span class="sxs-lookup"><span data-stu-id="522cc-102">Rebuild Index Task</span></span>
  <span data-ttu-id="522cc-103">L'attività Ricompila indice consente di ricompilare indici nelle tabelle e nelle viste dei database di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="522cc-103">The Rebuild Index task rebuilds indexes in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database tables and views.</span></span> <span data-ttu-id="522cc-104">Per altre informazioni sulla frammentazione degli indici, vedere [Riorganizzare e ricompilare gli indici](../../relational-databases/indexes/reorganize-and-rebuild-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="522cc-104">For more information about managing indexes, see [Reorganize and Rebuild Indexes](../../relational-databases/indexes/reorganize-and-rebuild-indexes.md).</span></span>  
  
 <span data-ttu-id="522cc-105">Tramite l'attività Ricompila indice un pacchetto può ricompilare gli indici in uno o più database.</span><span class="sxs-lookup"><span data-stu-id="522cc-105">By using the Rebuild Index task, a package can rebuild indexes in a single database or multiple databases.</span></span> <span data-ttu-id="522cc-106">Se si utilizza l'attività per ricompilare gli indici di un singolo database, sarà possibile scegliere le viste e le tabelle di cui ricompilare gli indici.</span><span class="sxs-lookup"><span data-stu-id="522cc-106">If the task rebuilds only the indexes in a single database, you can choose the views and tables whose indexes the task rebuilds.</span></span>  
  
 <span data-ttu-id="522cc-107">L'attività incapsula un'istruzione ALTER INDEX REBUILD con le opzioni di ricompilazione degli indici seguenti:</span><span class="sxs-lookup"><span data-stu-id="522cc-107">This task encapsulates an ALTER INDEX REBUILD statement with the following index rebuild options:</span></span>  
  
-   <span data-ttu-id="522cc-108">Per l'opzione FILLFACTOR è possibile specificare un valore percentuale o utilizzare il valore originale.</span><span class="sxs-lookup"><span data-stu-id="522cc-108">Specify a FILLFACTOR percentage or use the original FILLFACTOR amount.</span></span>  
  
-   <span data-ttu-id="522cc-109">Impostare PAD_INDEX = ON per allocare alle pagine di livello intermedio dell'indice lo spazio disponibile specificato dall'opzione FILLFACTOR.</span><span class="sxs-lookup"><span data-stu-id="522cc-109">Set PAD_INDEX = ON to allocate the free space specified by FILLFACTOR to the intermediate-level pages of the index.</span></span>  
  
-   <span data-ttu-id="522cc-110">Impostare SORT_IN_TEMPDB = ON per archiviare in tempdb i risultati intermedi dell'ordinamento utilizzati per la ricompilazione dell'indice.</span><span class="sxs-lookup"><span data-stu-id="522cc-110">Set SORT_IN_TEMPDB = ON to store the intermediate sort result used to rebuild the index in tempdb.</span></span> <span data-ttu-id="522cc-111">Quando l'opzione relativa al risultato intermedio dell'ordinamento è impostata su OFF, il risultato viene archiviato nello stesso database dell'indice.</span><span class="sxs-lookup"><span data-stu-id="522cc-111">When the intermediate sort result is set to OFF, the result is stored in the same database as the index.</span></span>  
  
-   <span data-ttu-id="522cc-112">Impostare IGNORE_DUP_KEY = ON per consentire alle operazioni di inserimento di più righe che includono record che violano i vincoli UNIQUE di inserire i record che non violano tali vincoli.</span><span class="sxs-lookup"><span data-stu-id="522cc-112">Set IGNORE_DUP_KEY = ON to allow a multirow insert operation that includes records that violate unique constraints to insert the records that do not violate the unique constraints.</span></span>  
  
-   <span data-ttu-id="522cc-113">Impostare ONLINE = ON per non mantenere i blocchi di tabella in modo da consentire l'esecuzione di aggiornamenti o query sulla tabella sottostante durante la ricostruzione dell'indice.</span><span class="sxs-lookup"><span data-stu-id="522cc-113">Set ONLINE = ON to not hold table locks so that queries or updates to the underlying table can proceed during re-indexing.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="522cc-114">Le operazioni sugli indici online sono disponibili solo in alcune edizioni di [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="522cc-114">Online index operations are not available in every edition of [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="522cc-115">Per un elenco delle funzionalità supportate dalle edizioni di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], vedere [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="522cc-115">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
 <span data-ttu-id="522cc-116">Per altre informazioni sull'istruzione ALTER INDEX e sulle opzioni di ricompilazione dell'indice, vedere [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="522cc-116">For more information about the ALTER INDEX statement and index rebuild options, see [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="522cc-117">Il tempo richiesto dall'attività per creare l'istruzione [!INCLUDE[tsql](../../includes/tsql-md.md)] da eseguire è proporzionale al numero degli indici da ricompilare.</span><span class="sxs-lookup"><span data-stu-id="522cc-117">The time the task takes to create the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement that the task runs is proportionate to the number of indexes the task rebuilds.</span></span> <span data-ttu-id="522cc-118">Se l'attività è configurata per la ricompilazione degli indici in tutte le tabelle e le viste di un database con un numero elevato di indici oppure per la ricompilazione degli indici in più database, la generazione dell'istruzione Transact-SQL potrebbe richiedere una quantità di tempo considerevole.</span><span class="sxs-lookup"><span data-stu-id="522cc-118">If the task is configured to rebuild indexes in all the tables and views in a database with a large number of indexes, or to rebuild indexes in multiple databases, the task can take a considerable amount of time to generate the Transact-SQL statement.</span></span>  
  
## <a name="configuration-of-the-rebuild-index-task"></a><span data-ttu-id="522cc-119">Configurazione dell'attività Ricompila indice</span><span class="sxs-lookup"><span data-stu-id="522cc-119">Configuration of the Rebuild Index Task</span></span>  
 <span data-ttu-id="522cc-120">È possibile impostare le proprietà tramite Progettazione [!INCLUDE[ssIS](../../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="522cc-120">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="522cc-121">Questa attività è disponibile nella sezione **Attività di manutenzione** della **casella degli strumenti** di Progettazione [!INCLUDE[ssIS](../../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="522cc-121">This task is in the **Maintenance Plan Tasks** section of the **Toolbox** in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="522cc-122">Per ulteriori informazioni sulle proprietà che è possibile impostare in Progettazione [!INCLUDE[ssIS](../../../includes/ssis-md.md)] , fare clic sull'argomento seguente:</span><span class="sxs-lookup"><span data-stu-id="522cc-122">For more information about the properties that you can set in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
 [<span data-ttu-id="522cc-123">Attività Ricompila indice &#40;Piano di manutenzione&#41;</span><span class="sxs-lookup"><span data-stu-id="522cc-123">Rebuild Index Task &#40;Maintenance Plan&#41;</span></span>](../../relational-databases/maintenance-plans/rebuild-index-task-maintenance-plan.md)  
  
## <a name="related-tasks"></a><span data-ttu-id="522cc-124">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="522cc-124">Related Tasks</span></span>  
 <span data-ttu-id="522cc-125">Per altre informazioni su come impostare queste proprietà nella finestra di Progettazione [!INCLUDE[ssIS](../../../includes/ssis-md.md)] , vedere [Impostazione delle proprietà di un'attività o di un contenitore](../set-the-properties-of-a-task-or-container.md).</span><span class="sxs-lookup"><span data-stu-id="522cc-125">For more about how to set these properties in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, see [Set the Properties of a Task or Container](../set-the-properties-of-a-task-or-container.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="522cc-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="522cc-126">See Also</span></span>  
 <span data-ttu-id="522cc-127">[Attività di Integration Services](integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="522cc-127">[Integration Services Tasks](integration-services-tasks.md) </span></span>  
 [<span data-ttu-id="522cc-128">Flusso di controllo</span><span class="sxs-lookup"><span data-stu-id="522cc-128">Control Flow</span></span>](control-flow.md)  
  
  
