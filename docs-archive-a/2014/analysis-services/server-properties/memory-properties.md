---
title: Proprietà memoria | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- LowMemoryLimit property
- MinimumAllocatedMemory property
- MidMemoryPrice property
- MemoryHeapType property
- memory [Analysis Services]
- DefaultPagesCountToReuse property
- TotalMemoryLimit property
- SessionMemoryLimit property
- VirtualMemoryLimit property
- WaitCountIfHighMemory property
- HighMemoryPrice property
- HeapTypeForObjects property
ms.assetid: 085f5195-7b2c-411a-9813-0ff5c6066d13
author: minewiskan
ms.author: owend
ms.openlocfilehash: 6f2d2e56c9a951cee27752bd57d55d185a9b6618
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727163"
---
# <a name="memory-properties"></a><span data-ttu-id="69e95-102">Proprietà della memoria</span><span class="sxs-lookup"><span data-stu-id="69e95-102">Memory Properties</span></span>
  [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="69e95-103">supporta le proprietà della memoria del server elencate nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="69e95-103">supports the server memory properties listed in the following table.</span></span> <span data-ttu-id="69e95-104">Per le linee guida di impostazione di queste proprietà, vedere la [Guida operativa di SQL Server 2008 R2 Analysis Services](https://go.microsoft.com/fwlink/?LinkID=225539).</span><span class="sxs-lookup"><span data-stu-id="69e95-104">For guidance in setting these properties, see [SQL Server 2008 R2 Analysis Services Operations Guide](https://go.microsoft.com/fwlink/?LinkID=225539).</span></span>  
  
 <span data-ttu-id="69e95-105">I valori compresi tra 1 e 100 rappresentano le percentuali di **memoria fisica totale** o **spazio degli indirizzi virtuali**, a seconda di quale dei due elementi sia inferiore.</span><span class="sxs-lookup"><span data-stu-id="69e95-105">Values between 1 and 100 represent percentages of **Total Physical Memory** or **Virtual Address Space**, whichever is less.</span></span> <span data-ttu-id="69e95-106">I valori maggiori di 100 rappresentano limiti di memoria in byte.</span><span class="sxs-lookup"><span data-stu-id="69e95-106">Values over 100 represent memory limits in bytes.</span></span>  
  
 <span data-ttu-id="69e95-107">**Si applica a:** Modalità server multidimensionale e tabulare, se non specificato diversamente.</span><span class="sxs-lookup"><span data-stu-id="69e95-107">**Applies to:** Multidimensional and Tabular server mode, unless noted otherwise.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="69e95-108">Proprietà</span><span class="sxs-lookup"><span data-stu-id="69e95-108">Properties</span></span>  
 `LowMemoryLimit`  
 <span data-ttu-id="69e95-109">Proprietà con numero a virgola mobile e precisione doppia a 64 bit con segno che definisce il punto in cui il server sta esaurendo la memoria, espresso come percentuale della memoria fisica totale.</span><span class="sxs-lookup"><span data-stu-id="69e95-109">A signed 64-bit double-precision floating-point number property that defines the point at which the server is low on memory, expressed as percentage of total physical memory.</span></span> <span data-ttu-id="69e95-110">Quando viene raggiunto questo limite, verrà avviata la cancellazione della memoria delle cache da parte dell'istanza, chiudendo le sessioni scadute e scaricando i calcoli inusati.</span><span class="sxs-lookup"><span data-stu-id="69e95-110">When this limit is reached, the instance will start to slowly clear memory out of caches by closing expired sessions and unloading unused calculations.</span></span> <span data-ttu-id="69e95-111">Il server non rilascerà memoria al di sotto di questo limite.</span><span class="sxs-lookup"><span data-stu-id="69e95-111">The server will not release memory below this limit.</span></span> <span data-ttu-id="69e95-112">Il valore predefinito è 65 e indica che il limite inferiore della memoria è il 65% della memoria fisica o dello spazio di indirizzo virtuale, a seconda di quale dei due elementi sia inferiore.</span><span class="sxs-lookup"><span data-stu-id="69e95-112">The default value is 65; which indicates the low memory limit is 65% of physical memory or the virtual address space, whichever is less.</span></span>  
  
 `TotalMemoryLimit`  
 <span data-ttu-id="69e95-113">Definisce una soglia che, una volta raggiunta, induce il server a deallocare la memoria in maniera più drastica.</span><span class="sxs-lookup"><span data-stu-id="69e95-113">Defines a threshold that when reached, causes the server to deallocate memory more aggressively.</span></span> <span data-ttu-id="69e95-114">Il valore predefinito è 80% della memoria fisica o dello spazio di indirizzo virtuale, a seconda di quale dei due elementi sia inferiore.</span><span class="sxs-lookup"><span data-stu-id="69e95-114">The default value 80% of physical memory or the virtual address space, whichever is less.</span></span>  
  
 <span data-ttu-id="69e95-115">Si noti che `TotalMemoryLimit` deve essere sempre minore di `HardMemoryLimit`</span><span class="sxs-lookup"><span data-stu-id="69e95-115">Note that `TotalMemoryLimit` must always be less than `HardMemoryLimit`</span></span>  
  
 `HardMemoryLimit`  
 <span data-ttu-id="69e95-116">Specifica una soglia di memoria superata la quale le sessioni utente attive verranno immediatamente terminate dall'istanza per ridurre l'utilizzo della memoria.</span><span class="sxs-lookup"><span data-stu-id="69e95-116">Specifies a memory threshold after which the instance aggressively terminates active user sessions to reduce memory usage.</span></span> <span data-ttu-id="69e95-117">Per tutte le sessioni terminate verrà visualizzato un errore che indica l'annullamento a causa di un numero eccessivo di richieste di memoria.</span><span class="sxs-lookup"><span data-stu-id="69e95-117">All terminated sessions will receive an error about being cancelled by memory pressure.</span></span> <span data-ttu-id="69e95-118">Con il valore predefinito, ovvero zero (0), il limite `HardMemoryLimit` sarà impostato su un valore mediano tra `TotalMemoryLimit` e la memoria fisica totale del sistema; se quest'ultima è maggiore dello spazio di indirizzo virtuale del processo, per calcolare il limite `HardMemoryLimit` sarà invece usato lo spazio di indirizzo virtuale.</span><span class="sxs-lookup"><span data-stu-id="69e95-118">The default value, zero (0), means the `HardMemoryLimit` will be set to a midway value between `TotalMemoryLimit` and the total physical memory of the system; if the physical memory of the system is larger than the virtual address space of the process, then virtual address space will be used instead to calculate `HardMemoryLimit`.</span></span>  
  
 `VirtualMemoryLimit`  
 <span data-ttu-id="69e95-119">Proprietà avanzata che deve essere modificata solo sotto la supervisione del servizio di supporto tecnico [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="69e95-119">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `VertiPaqPagingPolicy`  
 <span data-ttu-id="69e95-120">Specifica il comportamento di paging nel caso in cui la memoria del server sia insufficiente.</span><span class="sxs-lookup"><span data-stu-id="69e95-120">Specifies the paging behavior in the event the server runs low on memory.</span></span> <span data-ttu-id="69e95-121">I valori validi sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="69e95-121">Valid values are as follows:</span></span>  
  
 <span data-ttu-id="69e95-122">Zero (**0**) Disabilita il paging.</span><span class="sxs-lookup"><span data-stu-id="69e95-122">Zero (**0**) disables paging.</span></span> <span data-ttu-id="69e95-123">Se la memoria è insufficiente, l'elaborazione ha esito negativo e provoca un errore memoria insufficiente.</span><span class="sxs-lookup"><span data-stu-id="69e95-123">If memory is insufficient, processing fails with an out-of-memory error.</span></span> <span data-ttu-id="69e95-124">Se si disabilita il paging, è necessario concedere i privilegi di Windows all'account del servizio.</span><span class="sxs-lookup"><span data-stu-id="69e95-124">If you disable paging, you must grant Windows privileges to the service account.</span></span> <span data-ttu-id="69e95-125">Per istruzioni, vedere [Configurare gli account del servizio &#40;Analysis Services&#41;](../instances/configure-service-accounts-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="69e95-125">See [Configure Service Accounts &#40;Analysis Services&#41;](../instances/configure-service-accounts-analysis-services.md) for instructions.</span></span>  
  
 <span data-ttu-id="69e95-126">Il valore predefinito è**1** .</span><span class="sxs-lookup"><span data-stu-id="69e95-126">**1** is the default.</span></span> <span data-ttu-id="69e95-127">Questa proprietà abilita il paging su disco utilizzando il file di paging del sistema operativo (pagefile.sys).</span><span class="sxs-lookup"><span data-stu-id="69e95-127">This property enables paging to disk using the operating system page file (pagefile.sys).</span></span>  
  
 <span data-ttu-id="69e95-128">Quando `VertiPaqPagingPolicy` è impostato su 1, è meno probabile che l'elaborazione non venga completata a causa di limitazioni di memoria perché il server tenterà di eseguire il paging su disco utilizzando il metodo specificato.</span><span class="sxs-lookup"><span data-stu-id="69e95-128">When `VertiPaqPagingPolicy` is set to 1, processing is less likely to fail due to memory constraints because the server will try to page to disk using the method that you specified.</span></span> <span data-ttu-id="69e95-129">L'impostazione della proprietà `VertiPaqPagingPolicy` non garantisce che non si verificheranno mai gli errori della memoria.</span><span class="sxs-lookup"><span data-stu-id="69e95-129">Setting the `VertiPaqPagingPolicy` property does not guarantee that memory errors will never happen.</span></span> <span data-ttu-id="69e95-130">Gli errori di memoria insufficiente si possono comunque verificare nelle condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="69e95-130">Out of memory errors can still occur under the following conditions:</span></span>  
  
-   <span data-ttu-id="69e95-131">Non c'è abbastanza memoria per tutti i dizionari.</span><span class="sxs-lookup"><span data-stu-id="69e95-131">There is not enough memory for all dictionaries.</span></span> <span data-ttu-id="69e95-132">Durante l'elaborazione, Analysis Services blocca i dizionari per ogni colonna in memoria e tutti i dizionari insieme non possono essere maggiori del valore specificato per `VertiPaqMemoryLimit`.</span><span class="sxs-lookup"><span data-stu-id="69e95-132">During processing, Analysis Services locks the dictionaries for each column in memory, and all of these together cannot be more than the value specified for `VertiPaqMemoryLimit`.</span></span>  
  
-   <span data-ttu-id="69e95-133">Lo spazio dell'indirizzo virtuale è insufficiente per il processo.</span><span class="sxs-lookup"><span data-stu-id="69e95-133">There is insufficient virtual address space to accommodate the process.</span></span>  
  
 <span data-ttu-id="69e95-134">Per risolvere gli errori di memoria insufficiente persistenti è possibile riprogettare il modello per ridurre la quantità di dati che devono essere elaborati oppure è possibile aggiungere più memoria fisica al computer.</span><span class="sxs-lookup"><span data-stu-id="69e95-134">To resolve persistent out of memory errors, you can either try to redesign the model to reduce the amount of data that needs processing, or you can add more physical memory to the computer.</span></span>  
  
 <span data-ttu-id="69e95-135">Questo metodo si applica solo in modalità server tabulare.</span><span class="sxs-lookup"><span data-stu-id="69e95-135">Applies to tabular server mode only.</span></span>  
  
 `VertiPaqMemoryLimit`  
 <span data-ttu-id="69e95-136">Se il paging su disco è consentito, questa proprietà consente di specificare il livello di consumo di memoria (come percentuale della memoria totale) da cui avrà inizio il paging.</span><span class="sxs-lookup"><span data-stu-id="69e95-136">If paging to disk is allowed, this property specifies the level of memory consumption (as a percentage of total memory) at which paging starts.</span></span> <span data-ttu-id="69e95-137">Il valore predefinito è 60.</span><span class="sxs-lookup"><span data-stu-id="69e95-137">The default is 60.</span></span> <span data-ttu-id="69e95-138">Se il consumo di memoria è inferiore al 60%, il server non eseguirà il paging su disco.</span><span class="sxs-lookup"><span data-stu-id="69e95-138">If memory consumption is less than 60 percent, the server will not page to disk.</span></span>  
  
 <span data-ttu-id="69e95-139">Questa proprietà dipende da `VertiPaqPagingPolicyProperty`che deve essere impostata su 1 affinché si verifichi il paging.</span><span class="sxs-lookup"><span data-stu-id="69e95-139">This property depends on the `VertiPaqPagingPolicyProperty`, which must be set to 1 in order for paging to occur.</span></span>  
  
 <span data-ttu-id="69e95-140">Questo metodo si applica solo in modalità server tabulare.</span><span class="sxs-lookup"><span data-stu-id="69e95-140">Applies to tabular server mode only.</span></span>  
  
 `HighMemoryPrice`  
 <span data-ttu-id="69e95-141">Proprietà avanzata che deve essere modificata solo sotto la supervisione del servizio di supporto tecnico [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="69e95-141">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `MemoryHeapType`  
 <span data-ttu-id="69e95-142">Proprietà avanzata che deve essere modificata solo sotto la supervisione del servizio di supporto tecnico [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="69e95-142">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="69e95-143">Questo metodo si applica solo in modalità server multidimensionale.</span><span class="sxs-lookup"><span data-stu-id="69e95-143">Applies to multidimensional server mode only.</span></span>  
  
 `HeapTypeForObjects`  
 <span data-ttu-id="69e95-144">Proprietà avanzata che deve essere modificata solo sotto la supervisione del servizio di supporto tecnico [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="69e95-144">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="69e95-145">Questo metodo si applica solo in modalità server multidimensionale.</span><span class="sxs-lookup"><span data-stu-id="69e95-145">Applies to multidimensional server mode only.</span></span>  
  
 `DefaultPagesCountToReuse`  
 <span data-ttu-id="69e95-146">Proprietà avanzata che deve essere modificata solo sotto la supervisione del servizio di supporto tecnico [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="69e95-146">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `HandleIA64AlignmentFaults`  
 <span data-ttu-id="69e95-147">Proprietà avanzata che deve essere modificata solo sotto la supervisione del servizio di supporto tecnico [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="69e95-147">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `MidMemoryPrice`  
 <span data-ttu-id="69e95-148">Proprietà avanzata che deve essere modificata solo sotto la supervisione del servizio di supporto tecnico [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="69e95-148">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `MinimumAllocatedMemory`  
 <span data-ttu-id="69e95-149">Proprietà avanzata che deve essere modificata solo sotto la supervisione del servizio di supporto tecnico [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="69e95-149">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `PreAllocate`  
 <span data-ttu-id="69e95-150">Proprietà avanzata che deve essere modificata solo sotto la supervisione del servizio di supporto tecnico [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="69e95-150">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `SessionMemoryLimit`  
 <span data-ttu-id="69e95-151">Proprietà avanzata che deve essere modificata solo sotto la supervisione del servizio di supporto tecnico [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="69e95-151">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `WaitCountIfHighMemory`  
 <span data-ttu-id="69e95-152">Proprietà avanzata che deve essere modificata solo sotto la supervisione del servizio di supporto tecnico [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="69e95-152">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69e95-153">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="69e95-153">See Also</span></span>  
 <span data-ttu-id="69e95-154">[Configurare le proprietà del server in Analysis Services](server-properties-in-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="69e95-154">[Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md) </span></span>  
 [<span data-ttu-id="69e95-155">Determinare la modalità server di un'istanza di Analysis Services</span><span class="sxs-lookup"><span data-stu-id="69e95-155">Determine the Server Mode of an Analysis Services Instance</span></span>](../instances/determine-the-server-mode-of-an-analysis-services-instance.md)  
  
  
