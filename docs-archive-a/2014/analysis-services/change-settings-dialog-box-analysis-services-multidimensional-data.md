---
title: Finestra di dialogo Cambia impostazioni (Analysis Services-Dati multidimensionali) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.process.batchsettingsdialog.f1
ms.assetid: 0041e042-d7ce-48f9-a690-a6dc65471ff3
author: minewiskan
ms.author: owend
ms.openlocfilehash: e2649195e3aff4e17d378e54c4b1d656361dfe3a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626412"
---
# <a name="change-settings-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="37a10-102">Finestra di dialogo Cambia impostazioni (Analysis Services - Dati multidimensionali)</span><span class="sxs-lookup"><span data-stu-id="37a10-102">Change Settings Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="37a10-103">Utilizzare la finestra di dialogo **Cambia impostazioni** in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] e in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] per cambiare le impostazioni mediante le quali viene controllata l'elaborazione degli oggetti elencati nella finestra di dialogo **Elabora** .</span><span class="sxs-lookup"><span data-stu-id="37a10-103">Use the **Change Settings** dialog box in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] and [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to change the settings that govern the processing of objects listed in the **Process** dialog box.</span></span> <span data-ttu-id="37a10-104">Per visualizzare la finestra di dialogo **Cambia impostazioni** , è possibile fare clic su **Cambia impostazioni** nella finestra di dialogo **Elabora** .</span><span class="sxs-lookup"><span data-stu-id="37a10-104">You can display the **Change Settings** dialog box by clicking **Change Settings** on the **Process** dialog box.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="37a10-105"> Le impostazioni specificate in questa finestra di dialogo sostituiscono le impostazioni predefinite ereditate dal database di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] relative agli oggetti elencati nella finestra di dialogo **Elabora** .</span><span class="sxs-lookup"><span data-stu-id="37a10-105">Settings specified in this dialog box override default settings inherited from the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database for the objects listed in the **Process** dialog box.</span></span>  
  
## <a name="options"></a><span data-ttu-id="37a10-106">Opzioni</span><span class="sxs-lookup"><span data-stu-id="37a10-106">Options</span></span>  
 <span data-ttu-id="37a10-107">**Opzioni di elaborazione**</span><span class="sxs-lookup"><span data-stu-id="37a10-107">**Processing options**</span></span>  
 <span data-ttu-id="37a10-108">Utilizzare questa scheda per modificare le impostazioni relative all'ordine di elaborazione, alla tabella writeback e agli oggetti interessati nell'ambito dell'operazione di elaborazione.</span><span class="sxs-lookup"><span data-stu-id="37a10-108">Use this tab to modify settings related to the processing order, writeback table, and affected objects for the processing operation.</span></span> <span data-ttu-id="37a10-109">Nella scheda sono incluse le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="37a10-109">The tab contains the following options:</span></span>  
  
 <span data-ttu-id="37a10-110">**Parallel**</span><span class="sxs-lookup"><span data-stu-id="37a10-110">**Parallel**</span></span>  
 <span data-ttu-id="37a10-111">Fare clic su questa opzione per elaborare gli oggetti in parallelo.</span><span class="sxs-lookup"><span data-stu-id="37a10-111">Click to process the objects in parallel.</span></span>  
  
 <span data-ttu-id="37a10-112">**Numero massimo attività parallele**</span><span class="sxs-lookup"><span data-stu-id="37a10-112">**Maximum parallel tasks**</span></span>  
 <span data-ttu-id="37a10-113">Consente di selezionare il numero massimo di attività eseguite in parallelo nell'ambito dell'operazione di elaborazione o di scegliere **Dipendente dal server** per consentire a [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] di selezionare il numero ottimale di attività parallele.</span><span class="sxs-lookup"><span data-stu-id="37a10-113">Select the maximum number of tasks to execute in parallel by the processing operation, or choose **Let the server decide** to allow [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] to select an optimal number of parallel tasks.</span></span>  
  
 <span data-ttu-id="37a10-114">**Sequenziale**</span><span class="sxs-lookup"><span data-stu-id="37a10-114">**Sequential**</span></span>  
 <span data-ttu-id="37a10-115">Fare clic su questa opzione per elaborare gli oggetti in modo sequenziale.</span><span class="sxs-lookup"><span data-stu-id="37a10-115">Click to process the objects sequentially.</span></span>  
  
 <span data-ttu-id="37a10-116">**Modalità transazione**</span><span class="sxs-lookup"><span data-stu-id="37a10-116">**Transaction mode**</span></span>  
 <span data-ttu-id="37a10-117">Consente di scegliere la modalità di transazione utilizzata quando gli oggetti vengono elaborati in ordine sequenziale.</span><span class="sxs-lookup"><span data-stu-id="37a10-117">Choose the transaction mode that is used when objects are processed in sequential order:</span></span>  
  
-   <span data-ttu-id="37a10-118">**Una sola transazione** elabora tutti gli oggetti nella medesima transazione.</span><span class="sxs-lookup"><span data-stu-id="37a10-118">**One Transaction** processes all objects in the same transaction.</span></span>  
  
-   <span data-ttu-id="37a10-119">**Transazioni separate** elabora tutti gli oggetti, inclusi quelli dipendenti, in transazioni separate.</span><span class="sxs-lookup"><span data-stu-id="37a10-119">**Separate Transactions** processes all objects, including dependent objects, in separate transactions.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="37a10-120"> Questa opzione è attivata solo se si seleziona **Sequenziale** .</span><span class="sxs-lookup"><span data-stu-id="37a10-120">This option is enabled only if **Sequential** is selected.</span></span>  
  
 <span data-ttu-id="37a10-121">**Opzione tabella writeback**</span><span class="sxs-lookup"><span data-stu-id="37a10-121">**Writeback table option**</span></span>  
 <span data-ttu-id="37a10-122">Selezionare l'opzione utilizzata per gestire una tabella writeback:</span><span class="sxs-lookup"><span data-stu-id="37a10-122">Choose the option used to manage a writeback table:</span></span>  
  
-   <span data-ttu-id="37a10-123">**Crea** determina la creazione di una tabella writeback nel caso questa non esista</span><span class="sxs-lookup"><span data-stu-id="37a10-123">**Create** creates a writeback table if it does not exist.</span></span> <span data-ttu-id="37a10-124">Se esiste già una tabella writeback, si verifica un errore.</span><span class="sxs-lookup"><span data-stu-id="37a10-124">An error occurs if a writeback table already exists.</span></span>  
  
-   <span data-ttu-id="37a10-125">**Crea sempre** crea una tabella writeback nel caso questa non esista oppure sovrascrive quella esistente.</span><span class="sxs-lookup"><span data-stu-id="37a10-125">**Create always** creates a writeback table if it does not exist, or overwrites the existing writeback table if it does exist.</span></span>  
  
-   <span data-ttu-id="37a10-126">**Usa tabella esistente** utilizza la tabella writeback esistente.</span><span class="sxs-lookup"><span data-stu-id="37a10-126">**Use existing** uses the existing writeback table if it exists.</span></span> <span data-ttu-id="37a10-127">Se non esiste alcuna tabella writeback, si verifica un errore.</span><span class="sxs-lookup"><span data-stu-id="37a10-127">An error occurs if a writeback table does not exist.</span></span>  
  
 <span data-ttu-id="37a10-128">**Elabora oggetti interessati**</span><span class="sxs-lookup"><span data-stu-id="37a10-128">**Process affected objects**</span></span>  
 <span data-ttu-id="37a10-129">Selezionare questa opzione per includere ed elaborare gli oggetti dipendenti da oggetti inclusi nell'operazione di elaborazione.</span><span class="sxs-lookup"><span data-stu-id="37a10-129">Select to include and process objects that depend on objects included in the processing operation.</span></span>  
  
 <span data-ttu-id="37a10-130">**Errori chiave dimensione**</span><span class="sxs-lookup"><span data-stu-id="37a10-130">**Dimension key errors**</span></span>  
 <span data-ttu-id="37a10-131">Utilizzare questa scheda per modificare le impostazioni relative alla configurazione degli errori per l'operazione di elaborazione.</span><span class="sxs-lookup"><span data-stu-id="37a10-131">Use this tab to modify settings related to the error configuration for the processing operation.</span></span> <span data-ttu-id="37a10-132">Nella scheda sono incluse le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="37a10-132">The tab contains the following options:</span></span>  
  
 <span data-ttu-id="37a10-133">**Usa configurazione errori predefinita**</span><span class="sxs-lookup"><span data-stu-id="37a10-133">**Use default error configuration**</span></span>  
 <span data-ttu-id="37a10-134">Selezionare questa opzione per utilizzare la configurazione errori predefinita per gli oggetti nell'operazione di elaborazione.</span><span class="sxs-lookup"><span data-stu-id="37a10-134">Select to use the default error configuration for objects in the processing operation.</span></span>  
  
 <span data-ttu-id="37a10-135">**Usa configurazione errori personalizzata**</span><span class="sxs-lookup"><span data-stu-id="37a10-135">**Use custom error configuration**</span></span>  
 <span data-ttu-id="37a10-136">Selezionare questa opzione per definire la configurazione degli errori relativa agli oggetti inclusi nell'operazione di elaborazione.</span><span class="sxs-lookup"><span data-stu-id="37a10-136">Select to define the error configuration for objects in the processing operation.</span></span>  
  
 <span data-ttu-id="37a10-137">**Azione per errore chiave**</span><span class="sxs-lookup"><span data-stu-id="37a10-137">**Key error action**</span></span>  
 <span data-ttu-id="37a10-138">Consente di scegliere una delle azioni seguenti da eseguire quando viene rilevata una nuova chiave che non può essere ricercata durante l'elaborazione:</span><span class="sxs-lookup"><span data-stu-id="37a10-138">Choose one of the following actions that occur when a new key is encountered during processing that cannot be looked up:</span></span>  
  
-   <span data-ttu-id="37a10-139">**Converti in sconosciuta** aggrega le informazioni relative al record nel membro sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="37a10-139">**Convert to unknown** aggregates the information for the record into the unknown member.</span></span>  
  
-   <span data-ttu-id="37a10-140">**Scarta record** esclude le informazioni relative al record dall'elaborazione dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="37a10-140">**Discard record** excludes the information for the record from being processed with the object.</span></span>  
  
 <span data-ttu-id="37a10-141">**Ignora conteggio errori**</span><span class="sxs-lookup"><span data-stu-id="37a10-141">**Ignore errors count**</span></span>  
 <span data-ttu-id="37a10-142">Fare clic su questa opzione per ignorare qualsiasi eventuale errore che si verifichi durante l'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="37a10-142">Click to ignore any errors that occur when processing.</span></span>  
  
 <span data-ttu-id="37a10-143">**Arresta in caso di errore**</span><span class="sxs-lookup"><span data-stu-id="37a10-143">**Stop on error**</span></span>  
 <span data-ttu-id="37a10-144">Fare clic su questa opzione per arrestare l'elaborazione in caso di errori.</span><span class="sxs-lookup"><span data-stu-id="37a10-144">Click to stop processing when errors occur.</span></span> <span data-ttu-id="37a10-145">Questa opzione implica l'attivazione delle impostazioni **Numero di errori** e **Azione in caso di errore** .</span><span class="sxs-lookup"><span data-stu-id="37a10-145">This option enables the **Number of errors** and the **On error action** options.</span></span>  
  
 <span data-ttu-id="37a10-146">**Numero di errori**</span><span class="sxs-lookup"><span data-stu-id="37a10-146">**Number of errors**</span></span>  
 <span data-ttu-id="37a10-147">Consente di immettere il numero di errori che verranno ignorati prima di arrestare l'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="37a10-147">Type the number of errors that are ignored before processing stops.</span></span>  
  
 <span data-ttu-id="37a10-148">**Azione in caso di errore**</span><span class="sxs-lookup"><span data-stu-id="37a10-148">**On error action**</span></span>  
 <span data-ttu-id="37a10-149">Consente di scegliere una delle azioni seguenti da eseguire se il numero di errori supera il valore impostato in **Numero di errori**:</span><span class="sxs-lookup"><span data-stu-id="37a10-149">Choose one of the following actions to be taken when the number of errors exceeds the value in **Number of errors**:</span></span>  
  
-   <span data-ttu-id="37a10-150">**Arresta elaborazione** termina l'operazione di elaborazione.</span><span class="sxs-lookup"><span data-stu-id="37a10-150">**Stop processing** ends the processing operation.</span></span>  
  
-   <span data-ttu-id="37a10-151">**Arresta registrazione** arresta la registrazione degli errori senza però interrompere l'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="37a10-151">**Stop logging** stops logging errors, but continues the processing operation.</span></span>  
  
 <span data-ttu-id="37a10-152">**Chiave non trovata**</span><span class="sxs-lookup"><span data-stu-id="37a10-152">**Key not found**</span></span>  
 <span data-ttu-id="37a10-153">Specificare una delle azioni seguenti da eseguire quando non viene trovata una chiave durante l'elaborazione di un oggetto:</span><span class="sxs-lookup"><span data-stu-id="37a10-153">Specify one of the following actions to be taken when a key is not found when an object is processed:</span></span>  
  
-   <span data-ttu-id="37a10-154">**Ignora errore** ignora l'errore.</span><span class="sxs-lookup"><span data-stu-id="37a10-154">**Ignore error** ignores the error.</span></span>  
  
-   <span data-ttu-id="37a10-155">**Segnala e continua** segnala l'errore e continua l'operazione di elaborazione.</span><span class="sxs-lookup"><span data-stu-id="37a10-155">**Report and continue** reports the error and continues the processing operation.</span></span>  
  
-   <span data-ttu-id="37a10-156">**Segnala e arresta** segnala l'errore e arresta l'operazione di elaborazione.</span><span class="sxs-lookup"><span data-stu-id="37a10-156">**Report and stop** reports the error and stops the processing operation.</span></span>  
  
 <span data-ttu-id="37a10-157">**Chiave duplicata**</span><span class="sxs-lookup"><span data-stu-id="37a10-157">**Duplicate key**</span></span>  
 <span data-ttu-id="37a10-158">Specificare una delle azioni seguenti da eseguire se viene trovata una chiave duplicata durante l'elaborazione di un oggetto:</span><span class="sxs-lookup"><span data-stu-id="37a10-158">Specify one of the following actions to be taken if a duplicate key is found when an object is processed:</span></span>  
  
-   <span data-ttu-id="37a10-159">**Ignora errore** ignora l'errore.</span><span class="sxs-lookup"><span data-stu-id="37a10-159">**Ignore error** ignores the error.</span></span>  
  
-   <span data-ttu-id="37a10-160">**Segnala e continua** segnala l'errore e continua l'operazione di elaborazione.</span><span class="sxs-lookup"><span data-stu-id="37a10-160">**Report and continue** reports the error and continues the processing operation.</span></span>  
  
-   <span data-ttu-id="37a10-161">**Segnala e arresta** segnala l'errore e arresta l'operazione di elaborazione.</span><span class="sxs-lookup"><span data-stu-id="37a10-161">**Report and stop** reports the error and stops the processing operation.</span></span>  
  
 <span data-ttu-id="37a10-162">**Chiave Null convertita in sconosciuta**</span><span class="sxs-lookup"><span data-stu-id="37a10-162">**Null key converted to unknown**</span></span>  
 <span data-ttu-id="37a10-163">Consente di specificare una delle azioni seguenti da eseguire se viene aggiunta una chiave membro Null a un membro sconosciuto durante l'elaborazione di un oggetto.</span><span class="sxs-lookup"><span data-stu-id="37a10-163">Specify one of the following actions to be taken when a null member key is added to the unknown member when an object is processed:</span></span>  
  
-   <span data-ttu-id="37a10-164">**Ignora errore** ignora l'errore.</span><span class="sxs-lookup"><span data-stu-id="37a10-164">**Ignore error** ignores the error.</span></span>  
  
-   <span data-ttu-id="37a10-165">**Segnala e continua** segnala l'errore e continua l'operazione di elaborazione.</span><span class="sxs-lookup"><span data-stu-id="37a10-165">**Report and continue** reports the error and continues the processing operation.</span></span>  
  
-   <span data-ttu-id="37a10-166">**Segnala e arresta** segnala l'errore e arresta l'operazione di elaborazione.</span><span class="sxs-lookup"><span data-stu-id="37a10-166">**Report and stop** reports the error and stops the processing operation.</span></span>  
  
 <span data-ttu-id="37a10-167">**Chiave Null non consentita**</span><span class="sxs-lookup"><span data-stu-id="37a10-167">**Null key not allowed**</span></span>  
 <span data-ttu-id="37a10-168">Consente di specificare una delle azioni seguenti da eseguire se viene individuata una chiave Null non consentita durante l'elaborazione di un oggetto:</span><span class="sxs-lookup"><span data-stu-id="37a10-168">Specify one of the following actions to be taken when a null key is found, but not allowed, when an object is processed:</span></span>  
  
-   <span data-ttu-id="37a10-169">**Ignora errore** ignora l'errore.</span><span class="sxs-lookup"><span data-stu-id="37a10-169">**Ignore error** ignores the error.</span></span>  
  
-   <span data-ttu-id="37a10-170">**Segnala e continua** segnala l'errore e continua l'operazione di elaborazione.</span><span class="sxs-lookup"><span data-stu-id="37a10-170">**Report and continue** reports the error and continues the processing operation.</span></span>  
  
-   <span data-ttu-id="37a10-171">**Segnala e arresta** segnala l'errore e arresta l'operazione di elaborazione.</span><span class="sxs-lookup"><span data-stu-id="37a10-171">**Report and stop** reports the error and stops the processing operation.</span></span>  
  
 <span data-ttu-id="37a10-172">**Percorso log degli errori**</span><span class="sxs-lookup"><span data-stu-id="37a10-172">**Error log path**</span></span>  
 <span data-ttu-id="37a10-173">Consente di digitare il percorso completo e il nome del file di log degli errori.</span><span class="sxs-lookup"><span data-stu-id="37a10-173">Type the full path and file name for the error log file.</span></span>  
  
 <span data-ttu-id="37a10-174">**Sfoglia**</span><span class="sxs-lookup"><span data-stu-id="37a10-174">**Browse**</span></span>  
 <span data-ttu-id="37a10-175">Fare clic su questo pulsante per visualizzare la finestra di dialogo **Apri** e selezionare il nome e il percorso completo del file di log degli errori.</span><span class="sxs-lookup"><span data-stu-id="37a10-175">Click to open the **Open** dialog box and select the full path and file name for the error log file.</span></span>  
  
 <span data-ttu-id="37a10-176">**Elabora oggetti interessati**</span><span class="sxs-lookup"><span data-stu-id="37a10-176">**Process affected objects**</span></span>  
 <span data-ttu-id="37a10-177">Fare clic su questa opzione per elaborare gli oggetti dipendenti da altri oggetti selezionati nella finestra di dialogo **Elabora** .</span><span class="sxs-lookup"><span data-stu-id="37a10-177">Click to process the objects that have a dependency on the objects selected in the **Process** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37a10-178">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="37a10-178">See Also</span></span>  
 <span data-ttu-id="37a10-179">[Finestre di progettazione e finestre di dialogo Analysis Services &#40;dati multidimensionali&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="37a10-179">[Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="37a10-180">Finestra di dialogo elabora &#40;Analysis Services-Dati multidimensionali&#41;</span><span class="sxs-lookup"><span data-stu-id="37a10-180">Process Dialog Box &#40;Analysis Services - Multidimensional Data&#41;</span></span>](process-dialog-box-analysis-services-multidimensional-data.md)  
  
  
