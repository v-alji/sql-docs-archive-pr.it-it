---
title: Impostare opzioni di traccia globali (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- global trace options [SQL Server]
ms.assetid: 2854608a-c3c7-4eb8-b567-034bfec4b1a9
author: stevestein
ms.author: sstein
ms.openlocfilehash: 2f0809ae11776e1bddf42c189b86f48689ff4859
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624485"
---
# <a name="set-global-trace-options-sql-server-profiler"></a><span data-ttu-id="8626f-102">Impostare opzioni di traccia globali (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="8626f-102">Set Global Trace Options (SQL Server Profiler)</span></span>
  <span data-ttu-id="8626f-103">In questo argomento viene illustrato come impostare opzioni applicabili a tutte le tracce create in un'istanza specifica di [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8626f-103">This topic describes how to set options that apply to all traces that are created with a specific instance of [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>  
  
### <a name="to-set-global-trace-options"></a><span data-ttu-id="8626f-104">Per impostare le opzioni di traccia globali</span><span class="sxs-lookup"><span data-stu-id="8626f-104">To set global trace options</span></span>  
  
1.  <span data-ttu-id="8626f-105">Scegliere **Opzioni** dal menu **Strumenti**.</span><span class="sxs-lookup"><span data-stu-id="8626f-105">On the **Tools** menu, click **Options**.</span></span>  
  
2.  <span data-ttu-id="8626f-106">Nella finestra di dialogo **Opzioni generali**fare clic su **Scegli carattere**per modificare le opzioni di visualizzazione e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="8626f-106">In the **General Options**dialog box, click **Choose Font**to modify the display options, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="8626f-107">Facoltativamente, selezionare l'opzione **Avvia traccia non appena viene stabilita una connessione**.</span><span class="sxs-lookup"><span data-stu-id="8626f-107">Optionally, select **Start tracing immediately after making connection**.</span></span>  
  
4.  <span data-ttu-id="8626f-108">Facoltativamente, selezionare l'opzione **Update trace definition when provider version changes**(Aggiorna la definizione di traccia in caso di modifica della versione del provider).</span><span class="sxs-lookup"><span data-stu-id="8626f-108">Optionally, select **Update trace definition when provider version changes**.</span></span> <span data-ttu-id="8626f-109">Questa è l'opzione consigliata ed è selezionata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="8626f-109">This option is recommended and is selected by default.</span></span> <span data-ttu-id="8626f-110">Quando questa opzione è selezionata, la definizione di traccia viene aggiornata automaticamente alla versione attuale del server quando si esegue la traccia.</span><span class="sxs-lookup"><span data-stu-id="8626f-110">When this option is selected, the trace definition is automatically updated to the current version of the server where tracing is performed.</span></span>  
  
5.  <span data-ttu-id="8626f-111">Facoltativamente, specificare la modalità di gestione dei file di rollover da parte del server:</span><span class="sxs-lookup"><span data-stu-id="8626f-111">Optionally, specify how the server should manage rollover files:</span></span>  
  
    -   <span data-ttu-id="8626f-112">Selezionare l'opzione **Carica tutti i file di rollover in sequenza senza chiedere conferma** per caricare automaticamente i file di rollover durante la riproduzione.</span><span class="sxs-lookup"><span data-stu-id="8626f-112">Select **Load all rollover files in sequence without prompting** to automatically load rollover files during replay.</span></span>  
  
    -   <span data-ttu-id="8626f-113">Selezionare l'opzione **Chiedi conferma prima di caricare file di rollover** per controllare i file di rollover durante la riproduzione.</span><span class="sxs-lookup"><span data-stu-id="8626f-113">Select **Prompt before loading rollover files** to control rollover files during replay.</span></span>  
  
    -   <span data-ttu-id="8626f-114">Selezionare l'opzione **Non caricare mai file di rollover successivi** per riprodurre solo un file alla volta.</span><span class="sxs-lookup"><span data-stu-id="8626f-114">Select **Never load subsequent rollover files** to replay only one file at a time.</span></span>  
  
6.  <span data-ttu-id="8626f-115">Se si desidera, impostare le opzioni di riproduzione:</span><span class="sxs-lookup"><span data-stu-id="8626f-115">Optionally, set replay options:</span></span>  
  
    -   <span data-ttu-id="8626f-116">L'opzione**Numero predefinito di thread di riproduzione** consente di controllare il numero di thread del processore da usare durante la riproduzione.</span><span class="sxs-lookup"><span data-stu-id="8626f-116">**Default number of replay threads** controls the number of processor threads to use during replay.</span></span> <span data-ttu-id="8626f-117">Un numero elevato di thread consente un completamento più rapido della riproduzione, ma provoca la riduzione delle prestazioni del server durante la riproduzione.</span><span class="sxs-lookup"><span data-stu-id="8626f-117">A higher number of threads causes replay to complete faster, but causes server performance to degrade during replay.</span></span> <span data-ttu-id="8626f-118">L'impostazione consigliata è **4**.</span><span class="sxs-lookup"><span data-stu-id="8626f-118">The recommended setting is **4**.</span></span> <span data-ttu-id="8626f-119">Nella tabella seguente sono elencate le opzioni disponibili:</span><span class="sxs-lookup"><span data-stu-id="8626f-119">The following table lists the available options:</span></span>  
  
        |<span data-ttu-id="8626f-120">valore</span><span class="sxs-lookup"><span data-stu-id="8626f-120">Value</span></span>|<span data-ttu-id="8626f-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8626f-121">Description</span></span>|  
        |-----------|-----------------|  
        |<span data-ttu-id="8626f-122">**2**</span><span class="sxs-lookup"><span data-stu-id="8626f-122">**2**</span></span>|<span data-ttu-id="8626f-123">Valore minimo.</span><span class="sxs-lookup"><span data-stu-id="8626f-123">Minimum value.</span></span> <span data-ttu-id="8626f-124">Per la riproduzione vengono utilizzati due thread.</span><span class="sxs-lookup"><span data-stu-id="8626f-124">Use two threads to replay.</span></span>|  
        |<span data-ttu-id="8626f-125">**4**</span><span class="sxs-lookup"><span data-stu-id="8626f-125">**4**</span></span>|<span data-ttu-id="8626f-126">Valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="8626f-126">Default value.</span></span>|  
        |<span data-ttu-id="8626f-127">**255**</span><span class="sxs-lookup"><span data-stu-id="8626f-127">**255**</span></span>|<span data-ttu-id="8626f-128">Valore massimo.</span><span class="sxs-lookup"><span data-stu-id="8626f-128">Maximum value.</span></span> <span data-ttu-id="8626f-129">L'impostazione di un valore massimo comporta una riduzione delle prestazioni degli altri processi.</span><span class="sxs-lookup"><span data-stu-id="8626f-129">Setting a maximum value will impede performance for other processes.</span></span>|  
  
    -   <span data-ttu-id="8626f-130">L'opzione**Intervallo di attesa predefinito Health Monitor (sec)** consente di impostare la quantità di tempo massima in secondi per cui un altro processo può essere bloccato da parte di un thread di riproduzione.</span><span class="sxs-lookup"><span data-stu-id="8626f-130">**Default health monitor wait interval (sec)** sets the maximum amount of time that a replay thread can block another process in seconds.</span></span> <span data-ttu-id="8626f-131">Nella tabella riportata di seguito vengono illustrati i valori consentiti.</span><span class="sxs-lookup"><span data-stu-id="8626f-131">The following table explains the values.</span></span>  
  
        |<span data-ttu-id="8626f-132">valore</span><span class="sxs-lookup"><span data-stu-id="8626f-132">Value</span></span>|<span data-ttu-id="8626f-133">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8626f-133">Description</span></span>|  
        |-----------|-----------------|  
        |<span data-ttu-id="8626f-134">**0**</span><span class="sxs-lookup"><span data-stu-id="8626f-134">**0**</span></span>|<span data-ttu-id="8626f-135">Valore minimo.</span><span class="sxs-lookup"><span data-stu-id="8626f-135">Minimum value.</span></span> <span data-ttu-id="8626f-136">Se si imposta il valore **0** , [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] non arresterà mai un processo di blocco.</span><span class="sxs-lookup"><span data-stu-id="8626f-136">A setting of **0** means that [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] will never stop a blocking process.</span></span>|  
        |<span data-ttu-id="8626f-137">**3600**</span><span class="sxs-lookup"><span data-stu-id="8626f-137">**3600**</span></span>|<span data-ttu-id="8626f-138">Valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="8626f-138">Default value.</span></span> <span data-ttu-id="8626f-139">Sono consentiti processi di blocco che non superano **3600** secondi, ovvero un'ora.</span><span class="sxs-lookup"><span data-stu-id="8626f-139">Allow blocking processes that do not exceed **3600** seconds, or one hour.</span></span>|  
        |<span data-ttu-id="8626f-140">**86400**</span><span class="sxs-lookup"><span data-stu-id="8626f-140">**86400**</span></span>|<span data-ttu-id="8626f-141">Valore massimo.</span><span class="sxs-lookup"><span data-stu-id="8626f-141">Maximum value.</span></span> <span data-ttu-id="8626f-142">Sono consentiti processi di blocco che non superano **86400** secondi, ovvero un giorno.</span><span class="sxs-lookup"><span data-stu-id="8626f-142">Allow blocking processes that do not exceed **86400** seconds, or one day.</span></span>|  
  
    -   <span data-ttu-id="8626f-143">L'opzione**Intervallo di polling predefinito Health Monitor (sec)** consente di impostare la frequenza del polling dei thread di riproduzione per i processi di blocco.</span><span class="sxs-lookup"><span data-stu-id="8626f-143">**Default health monitor poll interval (sec)** sets the frequency to poll replay threads for blocking processes.</span></span> <span data-ttu-id="8626f-144">Nella tabella riportata di seguito vengono illustrati i valori consentiti.</span><span class="sxs-lookup"><span data-stu-id="8626f-144">The following table explains the values.</span></span>  
  
        |<span data-ttu-id="8626f-145">valore</span><span class="sxs-lookup"><span data-stu-id="8626f-145">Value</span></span>|<span data-ttu-id="8626f-146">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8626f-146">Description</span></span>|  
        |-----------|-----------------|  
        |<span data-ttu-id="8626f-147">**1**</span><span class="sxs-lookup"><span data-stu-id="8626f-147">**1**</span></span>|<span data-ttu-id="8626f-148">Valore minimo.</span><span class="sxs-lookup"><span data-stu-id="8626f-148">Minimum value.</span></span> <span data-ttu-id="8626f-149">Se si imposta il valore **1** , [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] eseguirà il polling dei processi di blocco una volta al secondo.</span><span class="sxs-lookup"><span data-stu-id="8626f-149">A setting of **1** means [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] will poll for blocking processes once per second.</span></span>|  
        |<span data-ttu-id="8626f-150">**60**</span><span class="sxs-lookup"><span data-stu-id="8626f-150">**60**</span></span>|<span data-ttu-id="8626f-151">Valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="8626f-151">Default value.</span></span> <span data-ttu-id="8626f-152">Il polling dei processi di blocco viene eseguito una volta al minuto.</span><span class="sxs-lookup"><span data-stu-id="8626f-152">Poll for blocking processes once per minute.</span></span>|  
        |<span data-ttu-id="8626f-153">**86400**</span><span class="sxs-lookup"><span data-stu-id="8626f-153">**86400**</span></span>|<span data-ttu-id="8626f-154">Valore massimo.</span><span class="sxs-lookup"><span data-stu-id="8626f-154">Maximum value.</span></span> <span data-ttu-id="8626f-155">Il polling dei processi di blocco viene eseguito una volta ogni **86400** secondi, ovvero una volta al giorno.</span><span class="sxs-lookup"><span data-stu-id="8626f-155">Poll for blocking processes once per **86400** seconds, or one day.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8626f-156">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8626f-156">See Also</span></span>  
 <span data-ttu-id="8626f-157">[Impostare i valori predefiniti per la visualizzazione delle tracce &#40;SQL Server Profiler&#41;](sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="8626f-157">[Set Trace Display Defaults &#40;SQL Server Profiler&#41;](sql-server-profiler.md) </span></span>  
 [<span data-ttu-id="8626f-158">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="8626f-158">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
