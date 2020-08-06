---
title: Creare e gestire partizioni di modelli tabulari (SSAS tabulare) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: dab72cf0-95bc-4b63-95dc-505b5cd881c1
author: minewiskan
ms.author: owend
ms.openlocfilehash: 58c408c712d6ac4b6bd590bd0f8c895dc1a88700
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635736"
---
# <a name="create-and-manage-tabular-model-partitions-ssas-tabular"></a><span data-ttu-id="42eed-102">Creare e gestire partizioni di modelli tabulari (SSAS tabulare)</span><span class="sxs-lookup"><span data-stu-id="42eed-102">Create and Manage Tabular Model Partitions (SSAS Tabular)</span></span>
  <span data-ttu-id="42eed-103">Le partizioni consentono di dividere una tabella in parti logiche.</span><span class="sxs-lookup"><span data-stu-id="42eed-103">Partitions divide a table into logical parts.</span></span> <span data-ttu-id="42eed-104">Ogni partizione può quindi essere elaborata (aggiornata) indipendentemente dalle altre.</span><span class="sxs-lookup"><span data-stu-id="42eed-104">Each partition can then be processed (Refreshed) independent of other partitions.</span></span> <span data-ttu-id="42eed-105">Le partizioni definite per un modello durante la relativa creazione vengono duplicate in un modello distribuito.</span><span class="sxs-lookup"><span data-stu-id="42eed-105">Partitions defined for a model during model authoring are duplicated in a deployed model.</span></span> <span data-ttu-id="42eed-106">Una volta distribuite, tali partizioni possono essere gestite tramite la finestra di dialogo **Partizioni** in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o tramite uno script.</span><span class="sxs-lookup"><span data-stu-id="42eed-106">Once deployed, you can manage those partitions by using the **Partitions** dialog box in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or by using a script.</span></span> <span data-ttu-id="42eed-107">Nelle attività presentate in questo argomento viene descritto come creare e gestire partizioni per un modello distribuito.</span><span class="sxs-lookup"><span data-stu-id="42eed-107">Tasks provided in this topic describe how to create and manage partitions for a deployed model.</span></span>  
  
 <span data-ttu-id="42eed-108">In questo argomento sono incluse le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="42eed-108">This topic includes the following tasks:</span></span>  
  
-   [<span data-ttu-id="42eed-109">Per creare una nuova partizione</span><span class="sxs-lookup"><span data-stu-id="42eed-109">To create a new partition</span></span>](#bkmk_create_new)  
  
-   [<span data-ttu-id="42eed-110">Per copiare una partizione</span><span class="sxs-lookup"><span data-stu-id="42eed-110">To copy a partition</span></span>](#bkmk_copy)  
  
-   [<span data-ttu-id="42eed-111">Per unire due o più partizioni</span><span class="sxs-lookup"><span data-stu-id="42eed-111">To merge two or more partitions</span></span>](#bkmk_merge)  
  
-   [<span data-ttu-id="42eed-112">Per eliminare una partizione</span><span class="sxs-lookup"><span data-stu-id="42eed-112">To delete a partition</span></span>](#bkmk_delete)  
  
## <a name="tasks"></a><span data-ttu-id="42eed-113">Attività</span><span class="sxs-lookup"><span data-stu-id="42eed-113">Tasks</span></span>  
 <span data-ttu-id="42eed-114">Per creare e gestire partizioni per un database modello tabulare distribuito si utilizzerà la finestra di dialogo **Partizioni** in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="42eed-114">To create and manage partitions for a deployed tabular model database, you will use the **Partitions** dialog box in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="42eed-115">Per visualizzare la finestra di dialogo **Partizioni** , in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]fare clic con il pulsante destro del mouse su una tabella, quindi selezionare **Partizioni**.</span><span class="sxs-lookup"><span data-stu-id="42eed-115">To view the **Partitions** dialog box, in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], right-click on a table, and then click **Partitions**.</span></span>  
  
###  <a name="to-create-a-new-partition"></a><a name="bkmk_create_new"></a><span data-ttu-id="42eed-116">Per creare una nuova partizione</span><span class="sxs-lookup"><span data-stu-id="42eed-116">To create a new partition</span></span>  
  
1.  <span data-ttu-id="42eed-117">Nella finestra di dialogo **Partizioni** fare clic sul pulsante **Nuova** .</span><span class="sxs-lookup"><span data-stu-id="42eed-117">In the **Partitions** dialog box, click the **New** button.</span></span>  
  
2.  <span data-ttu-id="42eed-118">In **Nome partizione**digitare un nome per la partizione.</span><span class="sxs-lookup"><span data-stu-id="42eed-118">In **Partition Name**, type a name for the partition.</span></span> <span data-ttu-id="42eed-119">Per impostazione predefinita, il nome della partizione predefinita sarà numerato in modo incrementale per ogni nuova partizione.</span><span class="sxs-lookup"><span data-stu-id="42eed-119">By default, the name of the default partition will be incrementally numbered for each new partition.</span></span>  
  
3.  <span data-ttu-id="42eed-120">In **Istruzione SQL**digitare o incollare un'istruzione di query SQL che consente di definire le colonne e tutte le clausole che si desidera includere nella partizione nella finestra Query.</span><span class="sxs-lookup"><span data-stu-id="42eed-120">In **SQL Statement**, type or paste a SQL query statement that defines the columns and any clauses you want to include in the partition into the query window.</span></span>  
  
4.  <span data-ttu-id="42eed-121">Per convalidare l'istruzione, fare clic su **Controlla sintassi**.</span><span class="sxs-lookup"><span data-stu-id="42eed-121">To validate the statement, click **Check Syntax**.</span></span>  
  
###  <a name="to-copy-a-partition"></a><a name="bkmk_copy"></a><span data-ttu-id="42eed-122">Per copiare una partizione</span><span class="sxs-lookup"><span data-stu-id="42eed-122">To copy a partition</span></span>  
  
1.  <span data-ttu-id="42eed-123">Nell'elenco **Partizioni** della relativa finestra di dialogo selezionare la partizione che si desidera copiare, quindi fare clic sul pulsante **Copia** . \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="42eed-123">In the **Partitions** dialog box, in the **Partitions** list, select the partition you want to copy, and then click the **Copy** button.</span></span>  
  
2.  <span data-ttu-id="42eed-124">In **Nome partizione**digitare un nuovo nome per la partizione.</span><span class="sxs-lookup"><span data-stu-id="42eed-124">In **Partition Name**, type a new name for the partition.</span></span>  
  
3.  <span data-ttu-id="42eed-125">In **Istruzione SQL**modificare l'istruzione di query SQL.</span><span class="sxs-lookup"><span data-stu-id="42eed-125">In **SQL Statement**, edit the SQL query statement.</span></span>  
  
###  <a name="to-merge-two-or-more-partitions"></a><a name="bkmk_merge"></a> <span data-ttu-id="42eed-126">Per unire due o più partizioni</span><span class="sxs-lookup"><span data-stu-id="42eed-126">To merge two or more partitions</span></span>  
  
-   <span data-ttu-id="42eed-127">Nell'elenco **partizioni** della finestra di dialogo **partizioni** , utilizzare CTRL + clic per selezionare le partizioni che si desidera unire, quindi fare clic sul pulsante **Unisci** .</span><span class="sxs-lookup"><span data-stu-id="42eed-127">In the **Partitions** dialog box, in the **Partitions** list, use Ctrl+click to select the partitions you want to merge, and then click the **Merge** button.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="42eed-128">L'unione delle partizioni non consente di aggiornare i metadati della partizione.</span><span class="sxs-lookup"><span data-stu-id="42eed-128">Merging partitions does not update the partition metadata.</span></span> <span data-ttu-id="42eed-129">Gli amministratori devono modificare l'istruzione SQL per la partizione risultante per assicurare che tramite le operazioni di elaborazione vengano elaborati tutti i dati nella partizione unita.</span><span class="sxs-lookup"><span data-stu-id="42eed-129">Administrators must alter the SQL Statement for the resulting partition to make sure processing operations process all data in the merged partition.</span></span>  
  
###  <a name="to-delete-a-partition"></a><a name="bkmk_delete"></a><span data-ttu-id="42eed-130">Per eliminare una partizione</span><span class="sxs-lookup"><span data-stu-id="42eed-130">To delete a partition</span></span>  
  
-   <span data-ttu-id="42eed-131">Nell'elenco **Partizioni** della relativa finestra di dialogo selezionare la partizione che si desidera eliminare, quindi fare clic sul pulsante **Elimina** . \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="42eed-131">In the **Partitions** dialog box, in the **Partitions** list, select the partition you want to delete, and then click the **Delete** button.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42eed-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="42eed-132">See Also</span></span>  
 <span data-ttu-id="42eed-133">[Partizioni di modelli tabulari &#40;SSAS tabulare&#41;](partitions-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="42eed-133">[Tabular Model Partitions &#40;SSAS Tabular&#41;](partitions-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="42eed-134">Elaborare partizioni di modelli tabulari &#40;SSAS tabulare&#41;</span><span class="sxs-lookup"><span data-stu-id="42eed-134">Process Tabular Model Partitions &#40;SSAS Tabular&#41;</span></span>](process-tabular-model-partitions-ssas-tabular.md)  
  
  
