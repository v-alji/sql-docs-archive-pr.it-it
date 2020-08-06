---
title: Dimensioni abilitate per la scrittura | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- write-enabled dimensions [Analysis Services]
- dimensions [Analysis Services], write-enabled
- dimension writeback [Analysis Services]
- write-enabled cubes [Analysis Services]
- writeback [Analysis Services], dimensions
ms.assetid: 0bac050d-cd3b-427b-884a-65a91be89500
author: minewiskan
ms.author: owend
ms.openlocfilehash: f8f0f1c959d44b4d3e133e5676e9aca9365a628d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629644"
---
# <a name="write-enabled-dimensions"></a><span data-ttu-id="52941-102">Dimensioni abilitate per la scrittura</span><span class="sxs-lookup"><span data-stu-id="52941-102">Write-Enabled Dimensions</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepNextAvoid](../../includes/ssnotedepnextavoid-md.md)]  
  
 <span data-ttu-id="52941-103">I dati di una dimensione sono in genere di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="52941-103">The data in a dimension is generally read-only.</span></span> <span data-ttu-id="52941-104">In determinati scenari, tuttavia, può rivelarsi utile abilitare una dimensione per la scrittura.</span><span class="sxs-lookup"><span data-stu-id="52941-104">However, for certain scenarios, you may want to write-enable a dimension.</span></span> <span data-ttu-id="52941-105">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , l'abilitazione per la scrittura di una dimensione consente agli utenti aziendali di modificare il contenuto della dimensione e di visualizzare l'effetto immediato delle modifiche sulle gerarchie della dimensione.</span><span class="sxs-lookup"><span data-stu-id="52941-105">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], write-enabling a dimension enables business users to modify the contents of the dimension and see the immediate affect of changes on the hierarchies of the dimension.</span></span> <span data-ttu-id="52941-106">È possibile abilitare per la scrittura qualsiasi dimensione basata su una singola tabella.</span><span class="sxs-lookup"><span data-stu-id="52941-106">Any dimension that is based on a single table can be write-enabled.</span></span> <span data-ttu-id="52941-107">In una dimensione abilitata per la scrittura, gli amministratori e gli utenti aziendali possono modificare, spostare, aggiungere ed eliminare membri all'interno della dimensione.</span><span class="sxs-lookup"><span data-stu-id="52941-107">In a write-enabled dimension, business users and administrators can change, move, add, and delete attribute members within the dimension.</span></span> <span data-ttu-id="52941-108">Tali operazioni di aggiornamento vengono definite collettivamente come *writeback della dimensione*.</span><span class="sxs-lookup"><span data-stu-id="52941-108">These updates are referred to collectively as *dimension writeback*.</span></span>  
  
 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="52941-109">supporta il writeback della dimensione in tutti gli attributi della dimensione e in qualsiasi membro di una dimensione che sia possibile modificare.</span><span class="sxs-lookup"><span data-stu-id="52941-109">supports dimension writeback on all dimension attributes and any member of a dimension may be modified.</span></span> <span data-ttu-id="52941-110">Per una partizione o un cubo abilitato per la scrittura, gli aggiornamenti vengono archiviati in una tabella writeback separata dalle tabelle di origine del cubo.</span><span class="sxs-lookup"><span data-stu-id="52941-110">For a write-enabled cube or partition, updates are stored in a writeback table separate from the cube's source tables.</span></span> <span data-ttu-id="52941-111">Per una dimensione abilitata per la scrittura, tuttavia, le modifiche vengono registrate direttamente nella tabella della dimensione.</span><span class="sxs-lookup"><span data-stu-id="52941-111">However, for a write-enabled dimension, updates are recorded directly in the dimension's table.</span></span> <span data-ttu-id="52941-112">Inoltre, se la dimensione abilitata per la scrittura è inclusa in un cubo con più partizioni in cui alcune o tutte le origini dei dati contengono copie della tabella della dimensione, durante un processo di writeback verrà aggiornata solo la tabella della dimensione originale.</span><span class="sxs-lookup"><span data-stu-id="52941-112">Also, if the write-enabled dimension is included in a cube with multiple partitions where some or all their data sources have copies of the dimension table, only the original dimension table is updated during a writeback process.</span></span>  
  
 <span data-ttu-id="52941-113">Le dimensioni e i cubi abilitati per la scrittura hanno caratteristiche diverse ma complementari.</span><span class="sxs-lookup"><span data-stu-id="52941-113">Write-enabled dimensions and write-enabled cubes have different but complementary features.</span></span> <span data-ttu-id="52941-114">Una dimensione abilitata per la scrittura consente agli utenti aziendali di aggiornare i membri, mentre un cubo abilitato per la scrittura consente loro di aggiornare i valori delle celle.</span><span class="sxs-lookup"><span data-stu-id="52941-114">A write-enabled dimension gives business users the ability to update members, whereas a write-enabled cube gives them the ability to update cell values.</span></span> <span data-ttu-id="52941-115">Sebbene queste due caratteristiche siano complementari, non è necessario utilizzarle in combinazione.</span><span class="sxs-lookup"><span data-stu-id="52941-115">Although these two features are complementary, you do not have to use both features in combination.</span></span> <span data-ttu-id="52941-116">Per l'esecuzione del writeback della dimensione non è necessario che una dimensione venga inclusa in un cubo.</span><span class="sxs-lookup"><span data-stu-id="52941-116">A dimension does not have to be included in a cube for dimension writeback to occur.</span></span> <span data-ttu-id="52941-117">Una dimensione abilitata per la scrittura può anche essere inclusa in un cubo non abilitato per la scrittura.</span><span class="sxs-lookup"><span data-stu-id="52941-117">A write-enabled dimension can also be included in a cube that is not write-enabled.</span></span> <span data-ttu-id="52941-118">Le procedure utilizzate per abilitare per la scrittura le dimensioni e i cubi e per gestirne la sicurezza sono diverse.</span><span class="sxs-lookup"><span data-stu-id="52941-118">You use different procedures to write-enable dimensions and cubes, and to maintain their security.</span></span>  
  
 <span data-ttu-id="52941-119">Al writeback della dimensione vengono applicate le restrizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="52941-119">The following restrictions apply to dimension writeback:</span></span>  
  
-   <span data-ttu-id="52941-120">Quando si crea un nuovo membro, è necessario includere ogni attributo di una dimensione.</span><span class="sxs-lookup"><span data-stu-id="52941-120">When you create a new member, you must include every attribute in a dimension.</span></span> <span data-ttu-id="52941-121">Non è possibile inserire un membro senza specificare un valore per l'attributo chiave della dimensione.</span><span class="sxs-lookup"><span data-stu-id="52941-121">You cannot insert a member without specifying a value for the key attribute of the dimension.</span></span> <span data-ttu-id="52941-122">La creazione di membri è pertanto soggetta a tutti i vincoli, ad esempio valori di chiave non Null, definiti nella tabella della dimensione.</span><span class="sxs-lookup"><span data-stu-id="52941-122">Therefore, creating members is subject to any constraints (such as non-null key values) that are defined on the dimension table.</span></span>  
  
-   <span data-ttu-id="52941-123">Il writeback della dimensione è supportato solo per gli schemi star.</span><span class="sxs-lookup"><span data-stu-id="52941-123">Dimension writeback is supported only for star schemas.</span></span> <span data-ttu-id="52941-124">In altre parole, una dimensione deve essere basata su un'unica tabella della dimensione correlata direttamente a una tabella dei fatti.</span><span class="sxs-lookup"><span data-stu-id="52941-124">In other words, a dimension must be based on a single dimension table directly related to a fact table.</span></span> <span data-ttu-id="52941-125">Dopo avere abilitato per la scrittura una dimensione, in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] questi requisiti vengono convalidati quando si esegue la distribuzione a un database di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] esistente o quando si compila un progetto di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="52941-125">After you write-enable a dimension, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] validates this requirement when you deploy to an existing [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database or when you build an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project.</span></span>  
  
 <span data-ttu-id="52941-126">È possibile modificare o eliminare qualsiasi membro esistente di una dimensione writeback.</span><span class="sxs-lookup"><span data-stu-id="52941-126">Any existing member of a writeback dimension can be modified or deleted.</span></span> <span data-ttu-id="52941-127">Quando un membro viene eliminato, l'eliminazione viene propagata a tutti i membri figlio.</span><span class="sxs-lookup"><span data-stu-id="52941-127">When a member is deleted, the deletion cascades to all child members.</span></span> <span data-ttu-id="52941-128">In una dimensione Customer contenente gli attributi CountryRegion, Province, City e Customer, l'eliminazione di un paese/regione provocherebbe, ad esempio, l'eliminazione di tutte le province e città e di tutti i clienti appartenenti al paese/regione eliminato.</span><span class="sxs-lookup"><span data-stu-id="52941-128">For example, in a Customer dimension that contains CountryRegion, Province, City, and Customer attributes, deleting a country/region would delete all provinces, cities, and customers that belong to the deleted country/region.</span></span> <span data-ttu-id="52941-129">Se un paese/regione include una sola provincia, eliminando tale provincia verrebbe eliminato anche il paese/regione.</span><span class="sxs-lookup"><span data-stu-id="52941-129">If a country/region has only one province, deleting that province would delete the country/region also.</span></span>  
  
 <span data-ttu-id="52941-130">I membri di una dimensione writeback possono essere spostati solo all'interno dello stesso livello.</span><span class="sxs-lookup"><span data-stu-id="52941-130">Members of a writeback dimension can only be moved within the same level.</span></span> <span data-ttu-id="52941-131">Una città, ad esempio, può essere spostata al livello City in un diverso paese/regione o provincia, ma non può essere spostata al livello Province o CountryRegion.</span><span class="sxs-lookup"><span data-stu-id="52941-131">For example, a city could be moved to the City level in a different country/region or province, but a city cannot be moved to the Province or CountryRegion level.</span></span> <span data-ttu-id="52941-132">In una gerarchia padre-figlio tutti i membri sono membri foglia e pertanto un membro può essere spostato in qualsiasi livello ad esclusione del livello `(All)`.</span><span class="sxs-lookup"><span data-stu-id="52941-132">In a parent-child hierarchy, all members are leaf members, and therefore a member may be moved to any level other than the `(All)` level.</span></span>  
  
 <span data-ttu-id="52941-133">Se un membro di una gerarchia padre-figlio viene eliminato, i figli del membro vengono spostati nell'elemento padre del membro.</span><span class="sxs-lookup"><span data-stu-id="52941-133">If a member of a parent-child hierarchy is deleted, the member's children are moved to the member's parent.</span></span> <span data-ttu-id="52941-134">Nel membro eliminato sono necessarie le autorizzazioni di aggiornamento per la tabella relazionale, mentre nei membri spostati non è richiesta alcuna autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="52941-134">Update permissions on the relational table are required on the deleted member, but no permissions are required on the moved members.</span></span> <span data-ttu-id="52941-135">Quando tramite un'applicazione viene spostato un membro in una gerarchia padre-figlio, nell'operazione UPDATE è possibile specificare se i discendenti del membro devono essere spostati con il membro oppure spostati nell'elemento padre del membro.</span><span class="sxs-lookup"><span data-stu-id="52941-135">When an application moves a member in a parent-child hierarchy, the application can specify in the UPDATE operation whether descendents of the member are moved with the member or are moved to the member's parent.</span></span> <span data-ttu-id="52941-136">Per eliminare in modo ricorsivo un membro in una gerarchia padre-figlio, è necessario che l'utente disponga delle autorizzazioni di aggiornamento per la tabella relazionale sia per il membro che per tutti i relativi discendenti.</span><span class="sxs-lookup"><span data-stu-id="52941-136">To recursively delete a member in a parent-child hierarchy, a user must have update permissions on the relational table for the member and all the member's descendants.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="52941-137">Gli aggiornamenti all'attributo padre in una gerarchia padre-figlio non devono includere aggiornamenti ad altre proprietà o altri attributi.</span><span class="sxs-lookup"><span data-stu-id="52941-137">Updates to the parent attribute in a parent-child hierarchy must not include updates to any other properties or attributes.</span></span>  
  
 <span data-ttu-id="52941-138">Tutte le modifiche a una dimensione provocano la modifica della struttura della dimensione.</span><span class="sxs-lookup"><span data-stu-id="52941-138">All changes to a dimension cause the dimension structure to be modified.</span></span> <span data-ttu-id="52941-139">Ogni modifica a una dimensione viene considerata come transazione singola, che necessita di elaborazione incrementale per l'aggiornamento della struttura della dimensione.</span><span class="sxs-lookup"><span data-stu-id="52941-139">Each change to a dimension is considered a single transaction, requiring incremental processing to update the dimension structure.</span></span> <span data-ttu-id="52941-140">Le dimensioni abilitate per la scrittura hanno gli stessi requisiti di elaborazione delle altre dimensioni.</span><span class="sxs-lookup"><span data-stu-id="52941-140">Write-enabled dimensions have the same processing requirements as any other dimension.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="52941-141">Il writeback della dimensione non è supportato dalle dimensioni collegate.</span><span class="sxs-lookup"><span data-stu-id="52941-141">Dimension writeback is not supported by linked dimensions.</span></span>  
  
## <a name="security"></a><span data-ttu-id="52941-142">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="52941-142">Security</span></span>  
 <span data-ttu-id="52941-143">Gli unici utenti aziendali autorizzati ad aggiornare una dimensione abilitata per la scrittura sono quelli inclusi nei ruoli del database di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] a cui sono state concesse le autorizzazioni di lettura/scrittura nella dimensione.</span><span class="sxs-lookup"><span data-stu-id="52941-143">The only business users who can update a write-enabled dimension are those in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database roles that have been granted read/write permission to the dimension.</span></span> <span data-ttu-id="52941-144">Per ogni ruolo, è possibile impostare i membri che possono o meno essere aggiornati.</span><span class="sxs-lookup"><span data-stu-id="52941-144">For each role, you can control which members can and cannot be updated.</span></span> <span data-ttu-id="52941-145">Affinché gli utenti aziendali possano aggiornare le dimensioni abilitate per la scrittura, è necessario che le applicazioni client utilizzate supportino questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="52941-145">For business users to update write-enabled dimensions, their client application must support this capability.</span></span> <span data-ttu-id="52941-146">Per tali utenti, è necessario che la dimensione abilitata per la scrittura sia inclusa in un cubo elaborato dopo l'ultima modifica della dimensione.</span><span class="sxs-lookup"><span data-stu-id="52941-146">For such users, a write-enabled dimension must be included in a cube that was processed since the dimension last changed.</span></span> <span data-ttu-id="52941-147">Per altre informazioni, vedere [Autorizzazione dell'accesso a oggetti e operazioni &#40;Analysis Services&#41;](../multidimensional-models/authorizing-access-to-objects-and-operations-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="52941-147">For more information, see [Authorizing access to objects and operations &#40;Analysis Services&#41;](../multidimensional-models/authorizing-access-to-objects-and-operations-analysis-services.md).</span></span>  
  
 <span data-ttu-id="52941-148">Gli utenti e i gruppi inclusi nel ruolo Administrators possono aggiornare i membri degli attributi di una dimensione abilitata per la scrittura, anche se la dimensione non è inclusa in un cubo.</span><span class="sxs-lookup"><span data-stu-id="52941-148">Users and groups included in the Administrators role can update the attribute members of a write-enabled dimension, even if the dimension is not included in a cube.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52941-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="52941-149">See Also</span></span>  
 <span data-ttu-id="52941-150">[Proprietà delle dimensioni del database](database-dimension-properties.md) </span><span class="sxs-lookup"><span data-stu-id="52941-150">[Database Dimension Properties](database-dimension-properties.md) </span></span>  
 <span data-ttu-id="52941-151">[Partizioni abilitate per la scrittura](../multidimensional-models-olap-logical-cube-objects/partitions-write-enabled-partitions.md) </span><span class="sxs-lookup"><span data-stu-id="52941-151">[Write-Enabled Partitions](../multidimensional-models-olap-logical-cube-objects/partitions-write-enabled-partitions.md) </span></span>  
 [<span data-ttu-id="52941-152">Dimensioni &#40;Analysis Services - Dati multidimensionali&#41;</span><span class="sxs-lookup"><span data-stu-id="52941-152">Dimensions &#40;Analysis Services - Multidimensional Data&#41;</span></span>](dimensions-analysis-services-multidimensional-data.md)  
  
  