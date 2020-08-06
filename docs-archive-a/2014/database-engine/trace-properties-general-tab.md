---
title: Proprietà traccia (scheda generale) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- sql12.pro.traceproperties.general.f1
helpviewer_keywords:
- Trace Properties dialog box
ms.assetid: 25227268-143b-477e-aac9-8268bcaf2078
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 30de30c88db35a41f8f118b6545d56a78b2dec79
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724896"
---
# <a name="trace-properties-general-tab"></a><span data-ttu-id="06134-102">Proprietà traccia (scheda Generale)</span><span class="sxs-lookup"><span data-stu-id="06134-102">Trace Properties (General Tab)</span></span>
  <span data-ttu-id="06134-103">Usare la scheda **Generale** della finestra di dialogo **Proprietà traccia** per visualizzare o specificare le proprietà di una traccia.</span><span class="sxs-lookup"><span data-stu-id="06134-103">Use the **General** tab of the **Trace Properties** dialog box to view or specify properties of a trace.</span></span>  
  
## <a name="options"></a><span data-ttu-id="06134-104">Opzioni</span><span class="sxs-lookup"><span data-stu-id="06134-104">Options</span></span>  
 <span data-ttu-id="06134-105">**Nome traccia**</span><span class="sxs-lookup"><span data-stu-id="06134-105">**Trace name**</span></span>  
 <span data-ttu-id="06134-106">Consente di specificare il nome della traccia.</span><span class="sxs-lookup"><span data-stu-id="06134-106">Specify the name of the trace.</span></span>  
  
 <span data-ttu-id="06134-107">**Nome provider di traccia**</span><span class="sxs-lookup"><span data-stu-id="06134-107">**Trace provider name**</span></span>  
 <span data-ttu-id="06134-108">Visualizza il nome dell'istanza di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] da inserire nella traccia.</span><span class="sxs-lookup"><span data-stu-id="06134-108">Shows the name of the instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] that will be traced.</span></span> <span data-ttu-id="06134-109">In questo campo viene inserito automaticamente il nome del server specificato al momento della connessione.</span><span class="sxs-lookup"><span data-stu-id="06134-109">This field is populated automatically with the name of the server that you specified when you connected.</span></span> <span data-ttu-id="06134-110">Per modificare il nome del provider di traccia, fare clic su **Annulla** per chiudere la finestra di dialogo e avviare una nuova traccia.</span><span class="sxs-lookup"><span data-stu-id="06134-110">To change the name of the trace provider, click **Cancel** to close the dialog box, and start a new trace.</span></span>  
  
 <span data-ttu-id="06134-111">**Tipo provider di traccia**</span><span class="sxs-lookup"><span data-stu-id="06134-111">**Trace provider type**</span></span>  
 <span data-ttu-id="06134-112">Visualizza il tipo di server che fornisce la traccia.</span><span class="sxs-lookup"><span data-stu-id="06134-112">Shows the server type that is providing the trace.</span></span> <span data-ttu-id="06134-113">Il campo **Tipo provider di traccia** viene popolato automaticamente dal file di definizione della traccia.</span><span class="sxs-lookup"><span data-stu-id="06134-113">The trace definition file populates the **Trace provider type** field automatically.</span></span> <span data-ttu-id="06134-114">Questo campo non può essere modificato.</span><span class="sxs-lookup"><span data-stu-id="06134-114">You cannot modify this field.</span></span>  
  
 <span data-ttu-id="06134-115">**version**</span><span class="sxs-lookup"><span data-stu-id="06134-115">**version**</span></span>  
 <span data-ttu-id="06134-116">Visualizza la versione del server che fornisce la traccia.</span><span class="sxs-lookup"><span data-stu-id="06134-116">Shows the version of the server that is providing the trace.</span></span> <span data-ttu-id="06134-117">Il campo **Versione** viene popolato automaticamente dal file di definizione della traccia.</span><span class="sxs-lookup"><span data-stu-id="06134-117">The trace definition file populates the **Version** field automatically.</span></span> <span data-ttu-id="06134-118">Questo campo non può essere modificato.</span><span class="sxs-lookup"><span data-stu-id="06134-118">You cannot modify this field.</span></span>  
  
 <span data-ttu-id="06134-119">**Modello**</span><span class="sxs-lookup"><span data-stu-id="06134-119">**Use the template**</span></span>  
 <span data-ttu-id="06134-120">Consente di selezionare un modello dalla directory dei modelli.</span><span class="sxs-lookup"><span data-stu-id="06134-120">Select a template from the template directory.</span></span> <span data-ttu-id="06134-121">Questa directory viene popolata con i modelli predefiniti ed eventuali modelli definiti dall'utente creati per il tipo di provider di traccia corrente.</span><span class="sxs-lookup"><span data-stu-id="06134-121">The directory is populated with the default templates and any user-defined templates created for the current trace provider type.</span></span>  
  
 <span data-ttu-id="06134-122">**Salva nel file**</span><span class="sxs-lookup"><span data-stu-id="06134-122">**Save to file**</span></span>  
 <span data-ttu-id="06134-123">Consente di acquisire i dati di traccia in un file trc.</span><span class="sxs-lookup"><span data-stu-id="06134-123">Capture the trace data to a .trc file.</span></span> <span data-ttu-id="06134-124">Il salvataggio dei dati di traccia risulta utile per eseguire analisi e controlli successivi.</span><span class="sxs-lookup"><span data-stu-id="06134-124">Saving trace data is useful for later review and analysis.</span></span>  
  
 <span data-ttu-id="06134-125">**Dimensioni massime del file (MB)**</span><span class="sxs-lookup"><span data-stu-id="06134-125">**Set maximum file size (MB)**</span></span>  
 <span data-ttu-id="06134-126">Se si sceglie di salvare i dati di traccia in un file, è necessario specificare le dimensioni massime del file di traccia.</span><span class="sxs-lookup"><span data-stu-id="06134-126">If you choose to save the trace data to a file, you must specify the maximum size of the trace file.</span></span> <span data-ttu-id="06134-127">Il valore predefinito è 5 megabyte (MB).</span><span class="sxs-lookup"><span data-stu-id="06134-127">The default is 5 megabytes (MB).</span></span> <span data-ttu-id="06134-128">Le dimensioni massime sono limitate solo dal file system (NTFS, FAT) in cui viene salvato il file.</span><span class="sxs-lookup"><span data-stu-id="06134-128">The maximum size is limited only by the file system (NTFS, FAT) where the file is saved.</span></span>  
  
 <span data-ttu-id="06134-129">\<Graphic>**Salva con nome**</span><span class="sxs-lookup"><span data-stu-id="06134-129">\<Graphic> **Save As**</span></span>  
 <span data-ttu-id="06134-130">Se si è scelto di eseguire il salvataggio, è possibile fare clic su questa icona per modificare il nome del file.</span><span class="sxs-lookup"><span data-stu-id="06134-130">After you have selected to save, you can select this icon to change the file name.</span></span>  
  
 <span data-ttu-id="06134-131">**Consenti rollover dei file**</span><span class="sxs-lookup"><span data-stu-id="06134-131">**Enable file rollover**</span></span>  
 <span data-ttu-id="06134-132">Selezionare questa opzione per abilitare la creazione di file aggiuntivi in cui acquisire i dati di traccia al raggiungimento delle dimensioni massime del file.</span><span class="sxs-lookup"><span data-stu-id="06134-132">Select to enable the creation of additional files to accept the trace data when the maximum file size is reached.</span></span> <span data-ttu-id="06134-133">Il nome di ogni nuovo file è composto dal nome del file trc originale e da un numero progressivo.</span><span class="sxs-lookup"><span data-stu-id="06134-133">Each new file name consists of the original .trc file name, numbered sequentially.</span></span> <span data-ttu-id="06134-134">Quando vengono ad esempio raggiunte le dimensioni massime del file **NewTrace.trc** , quest'ultimo viene chiuso e viene aperto un nuovo file, **NewTrace_1.trc**, seguito a sua volta da **NewTrace_2.trc**e così via.</span><span class="sxs-lookup"><span data-stu-id="06134-134">For example, once it reaches maximum file size, **NewTrace.trc** closes, and a new file, **NewTrace_1.trc**, opens, followed by **NewTrace_2.trc**, and so on.</span></span> <span data-ttu-id="06134-135">Quando si salva una traccia in un file, il rollover dei file è abilitato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="06134-135">File rollover is enabled by default when you save a trace to a file.</span></span>  
  
 <span data-ttu-id="06134-136">**Dati di traccia elaborati dal server**</span><span class="sxs-lookup"><span data-stu-id="06134-136">**Server processes trace data**</span></span>  
 <span data-ttu-id="06134-137">Consente di specificare che l'elaborazione dei dati di traccia deve essere eseguita dal server che esegue la traccia.</span><span class="sxs-lookup"><span data-stu-id="06134-137">Specify that the server running the trace should process the trace data.</span></span> <span data-ttu-id="06134-138">Questa opzione consente di limitare l'overhead delle prestazioni causata dalla traccia.</span><span class="sxs-lookup"><span data-stu-id="06134-138">Using this option reduces the performance overhead incurred by tracing.</span></span> <span data-ttu-id="06134-139">Se questa casella di controllo è selezionata nessun evento viene ignorato, anche in condizioni di sovraccarico.</span><span class="sxs-lookup"><span data-stu-id="06134-139">If selected, no events are skipped even under stress conditions.</span></span> <span data-ttu-id="06134-140">Se questa casella di controllo è deselezionata, l'elaborazione viene eseguita da SQL Server Profiler ed è possibile che alcuni eventi non vengano tracciati in condizioni di sovraccarico.</span><span class="sxs-lookup"><span data-stu-id="06134-140">If this check box is cleared, processing is performed by SQL Server Profiler, and there is a possibility that some events are not traced under stress conditions.</span></span>  
  
 <span data-ttu-id="06134-141">**Salva nella tabella**</span><span class="sxs-lookup"><span data-stu-id="06134-141">**Save to table**</span></span>  
 <span data-ttu-id="06134-142">Consente di memorizzare i dati di traccia in una tabella di database.</span><span class="sxs-lookup"><span data-stu-id="06134-142">Capture the trace data to a database table.</span></span> <span data-ttu-id="06134-143">Il salvataggio dei dati di traccia risulta utile per eseguire analisi e controlli successivi.</span><span class="sxs-lookup"><span data-stu-id="06134-143">Saving trace data is useful for later review and analysis.</span></span> <span data-ttu-id="06134-144">Tuttavia il salvataggio dei dati di traccia in una tabella può causare un notevole overhead nel server in cui viene salvata la traccia.</span><span class="sxs-lookup"><span data-stu-id="06134-144">However, saving trace data to a table can incur significant overhead on the server where the trace is being saved.</span></span> <span data-ttu-id="06134-145">Se possibile, non salvare la tabella di traccia sullo stesso server tracciato.</span><span class="sxs-lookup"><span data-stu-id="06134-145">If possible, do not save the trace table on the same server that is being traced.</span></span>  
  
 <span data-ttu-id="06134-146">\<Graphic>**Tabella di destinazione**</span><span class="sxs-lookup"><span data-stu-id="06134-146">\<Graphic> **Destination Table**</span></span>  
 <span data-ttu-id="06134-147">Se si è scelto di eseguire il salvataggio dei dati della traccia in una tabella di database, è possibile fare clic su questa icona per modificare il nome della tabella.</span><span class="sxs-lookup"><span data-stu-id="06134-147">After you have selected to save the trace data to a database table, you can select this icon to change the table name.</span></span>  
  
 <span data-ttu-id="06134-148">**Numero massimo di righe (in migliaia)**</span><span class="sxs-lookup"><span data-stu-id="06134-148">**Set maximum rows (in thousands)**</span></span>  
 <span data-ttu-id="06134-149">Consente di specificare il numero massimo di righe in cui salvare i dati.</span><span class="sxs-lookup"><span data-stu-id="06134-149">Specify the largest number of rows in which to save data.</span></span> <span data-ttu-id="06134-150">Il valore predefinito è 1000 righe.</span><span class="sxs-lookup"><span data-stu-id="06134-150">The default is 1000 rows.</span></span>  
  
 <span data-ttu-id="06134-151">**Data e ora di arresto della traccia**</span><span class="sxs-lookup"><span data-stu-id="06134-151">**Enable trace stop time**</span></span>  
 <span data-ttu-id="06134-152">Consente di impostare la data e l'ora di interruzione della traccia e la relativa chiusura.</span><span class="sxs-lookup"><span data-stu-id="06134-152">Set the date and time for the trace to end and close itself.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06134-153">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="06134-153">See Also</span></span>  
 [<span data-ttu-id="06134-154">Creare una traccia &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="06134-154">Create a Trace &#40;SQL Server Profiler&#41;</span></span>](../tools/sql-server-profiler/create-a-trace-sql-server-profiler.md)  
  
  
