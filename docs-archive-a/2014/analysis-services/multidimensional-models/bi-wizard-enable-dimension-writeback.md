---
title: Abilitare il writeback della dimensione | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- modifying dimensions
- writeback [Analysis Services], setting up
- dimensions [Analysis Services], Business Intelligence enhancements
- Business Intelligence enhancements [Analysis Services], writeback
- dimensions [Analysis Services], writeback
- writeback [Analysis Services]
- dimensions [Analysis Services], modifying
- manual dimension structure modifications
ms.assetid: a4b5eb5a-366d-4fc8-ad0d-5bdb8e7b4163
author: minewiskan
ms.author: owend
ms.openlocfilehash: cba4a54e8a51d022c6f84a4c81d32f359a95692a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626365"
---
# <a name="enable-dimension-writeback"></a><span data-ttu-id="5b660-102">Attivazione writeback della dimensione</span><span class="sxs-lookup"><span data-stu-id="5b660-102">Enable Dimension Writeback</span></span>
  <span data-ttu-id="5b660-103">Aggiungere a un cubo o a una dimensione la funzionalità avanzata di writeback della dimensione per consentire agli utenti di modificare manualmente la struttura e i membri della dimensione.</span><span class="sxs-lookup"><span data-stu-id="5b660-103">Add the dimension writeback enhancement to a cube or dimension to allow users to manually modify the dimension structure and members.</span></span> <span data-ttu-id="5b660-104">Gli aggiornamenti di una dimensione abilitata per la scrittura vengono registrati direttamente nella tabella della dimensione.</span><span class="sxs-lookup"><span data-stu-id="5b660-104">Updates to a write-enabled dimension are recorded directly in the dimension table.</span></span> <span data-ttu-id="5b660-105">Questa funzionalità avanzata modifica l'impostazione della proprietà `WriteEnabled` per una dimensione.</span><span class="sxs-lookup"><span data-stu-id="5b660-105">This enhancement changes the `WriteEnabled` property setting for a dimension.</span></span>  
  
 <span data-ttu-id="5b660-106">Per aggiungere il writeback della dimensione, usare Configurazione guidata funzionalità di Business Intelligence e selezionare l'opzione **Abilitazione writeback della dimensione** nella pagina **Scelta funzionalità avanzata** .</span><span class="sxs-lookup"><span data-stu-id="5b660-106">To add dimension writeback, you use the Business Intelligence Wizard, and select the **Enable dimension writeback** option on the **Choose Enhancement** page.</span></span> <span data-ttu-id="5b660-107">Questa procedura guidata consente di eseguire in modo semplificato i passaggi per la selezione di una dimensione alla quale si desidera applicare il writeback della dimensione e per l'impostazione di questa opzione per la dimensione selezionata.</span><span class="sxs-lookup"><span data-stu-id="5b660-107">This wizard then guides you through the steps of selecting a dimension to which you want to apply dimension writeback and setting this option for the selected dimension.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5b660-108">Il writeback è supportato solo per i database relazionali e i data mart di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5b660-108">Writeback is supported for SQL Server relational databases and data marts only.</span></span>  
  
## <a name="selecting-a-dimension"></a><span data-ttu-id="5b660-109">Selezione di una dimensione</span><span class="sxs-lookup"><span data-stu-id="5b660-109">Selecting a Dimension</span></span>  
 <span data-ttu-id="5b660-110">Nella prima pagina della procedura guidata **Abilitazione writeback della dimensione** specificare la dimensione alla quale si desidera applicare il writeback della dimensione.</span><span class="sxs-lookup"><span data-stu-id="5b660-110">On the first **Enable Dimension Writeback** page of the wizard, you specify the dimension to which you want to apply dimension writeback.</span></span> <span data-ttu-id="5b660-111">La funzionalità avanzata di writeback della dimensione aggiunta alla dimensione selezionata risulterà tra le modifiche apportate alla dimensione.</span><span class="sxs-lookup"><span data-stu-id="5b660-111">The dimension writeback enhancement added to this selected dimension will result in changes to the dimension.</span></span> <span data-ttu-id="5b660-112">Tali modifiche verranno ereditate da tutti i cubi che includono la dimensione selezionata.</span><span class="sxs-lookup"><span data-stu-id="5b660-112">These changes will be inherited by all cubes that include the selected dimension.</span></span>  
  
## <a name="setting-dimension-writeback-capability"></a><span data-ttu-id="5b660-113">Impostazione della funzionalità di writeback della dimensione</span><span class="sxs-lookup"><span data-stu-id="5b660-113">Setting Dimension Writeback Capability</span></span>  
 <span data-ttu-id="5b660-114">Nella seconda pagina della procedura guidata **Abilitazione writeback della dimensione** è possibile effettivamente impostare l'opzione **Consenti writeback della dimensione** .</span><span class="sxs-lookup"><span data-stu-id="5b660-114">On the second **Enable Dimension Writeback** page of the wizard, you actually set the **Enable writeback in the dimension** option.</span></span> <span data-ttu-id="5b660-115">Selezionando questa opzione, la proprietà `WriteEnabled` della dimensione viene impostata automaticamente su `True`.</span><span class="sxs-lookup"><span data-stu-id="5b660-115">Selecting this option automatically sets the `WriteEnabled` property of the dimension to `True`.</span></span> <span data-ttu-id="5b660-116">Deselezionando questa opzione la proprietà viene impostata automaticamente su `False`.</span><span class="sxs-lookup"><span data-stu-id="5b660-116">Clearing this option automatically sets the property to `False`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5b660-117">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="5b660-117">Remarks</span></span>  
 <span data-ttu-id="5b660-118">Quando si crea un nuovo membro, è necessario includere ogni attributo di una dimensione.</span><span class="sxs-lookup"><span data-stu-id="5b660-118">When you create a new member, you must include every attribute in a dimension.</span></span> <span data-ttu-id="5b660-119">Non è possibile inserire un membro senza specificare un valore per l'attributo chiave della dimensione.</span><span class="sxs-lookup"><span data-stu-id="5b660-119">You cannot insert a member without specifying a value for the key attribute of the dimension.</span></span> <span data-ttu-id="5b660-120">La creazione di membri è pertanto soggetta a tutti i vincoli, ad esempio valori di chiave non Null, definiti nella tabella della dimensione.</span><span class="sxs-lookup"><span data-stu-id="5b660-120">Therefore, creating members is subject to any constraints (such as non-null key values) that are defined on the dimension table.</span></span> <span data-ttu-id="5b660-121">È consigliabile considerare inoltre le colonne che possono essere specificate dalle proprietà della dimensione, ad esempio le colonne specificate nelle proprietà della dimensione `CustomRollupColumn`, `CustomRollupPropertiesColumn` o `UnaryOperatorColumn`.</span><span class="sxs-lookup"><span data-stu-id="5b660-121">You should also consider columns optionally specified by dimension properties, such as columns specified in the `CustomRollupColumn`, `CustomRollupPropertiesColumn` or the `UnaryOperatorColumn` dimension properties.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="5b660-122">Se si utilizza SQL Azure come origine dati per eseguire il writeback in un database di Analysis Services, l'operazione non viene completata.</span><span class="sxs-lookup"><span data-stu-id="5b660-122">If you use SQL Azure as a data source to perform writeback into an Analysis Services database, the operation fails.</span></span> <span data-ttu-id="5b660-123">Questo si verifica per motivi strutturali, dal momento che l'opzione provider che abilita il servizio MARS (Multiple Active Result Sets) non è abilitata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="5b660-123">This is by design, because the provider option that enables multiple active result sets (MARS) is not turned on by default.</span></span>  
>   
>  <span data-ttu-id="5b660-124">La soluzione alternativa consiste nell'aggiungere l'impostazione seguente nella stringa di connessione, per supportare il servizio MARS e abilitare il writeback:</span><span class="sxs-lookup"><span data-stu-id="5b660-124">The workaround is to add the following setting in the connection string, to support MARS and to enable writeback:</span></span>  
>   
>  `"MultipleActiveResultSets=True"`  
>   
>  <span data-ttu-id="5b660-125">Per ulteriori informazioni, vedere [utilizzo di più set di risultati attivi &#40;&#41;Mars ](../../relational-databases/native-client/features/using-multiple-active-result-sets-mars.md).</span><span class="sxs-lookup"><span data-stu-id="5b660-125">For more information see [Using Multiple Active Result Sets &#40;MARS&#41;](../../relational-databases/native-client/features/using-multiple-active-result-sets-mars.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b660-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5b660-126">See Also</span></span>  
 [<span data-ttu-id="5b660-127">Dimensioni abilitate per la scrittura</span><span class="sxs-lookup"><span data-stu-id="5b660-127">Write-Enabled Dimensions</span></span>](../multidimensional-models-olap-logical-dimension-objects/write-enabled-dimensions.md)  
  
  
