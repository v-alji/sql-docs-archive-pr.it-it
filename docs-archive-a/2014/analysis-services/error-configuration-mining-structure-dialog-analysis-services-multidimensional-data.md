---
title: Configurazione errori (finestra di dialogo struttura di data mining) (Analysis Services-Dati multidimensionali) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.miningstructuredialog.general.f1
ms.assetid: d9aa028b-bad9-49c7-a81c-c2150e4dd481
author: minewiskan
ms.author: owend
ms.openlocfilehash: 5eb41da36400271a9b058ecf275d26bd22d3ee53
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87638137"
---
# <a name="error-configuration-mining-structure-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="547e2-102">Configurazione errori (finestra di dialogo Struttura di data mining) (Analysis Services - Dati multidimensionali)</span><span class="sxs-lookup"><span data-stu-id="547e2-102">Error Configuration (Mining Structure Dialog Box) (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="547e2-103">La pagina **Configurazione errori** della finestra di dialogo **Proprietà struttura di data mining** in **SQL Server Management Studio** consente di impostare le proprietà di configurazione degli errori di una struttura di data mining in un database di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="547e2-103">Use the **Error Configuration** page of the **Mining Structure Properties** dialog box in **SQL Server Management Studio** to set the error configuration properties of a mining structure in an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database.</span></span>  
  
## <a name="options"></a><span data-ttu-id="547e2-104">Opzioni</span><span class="sxs-lookup"><span data-stu-id="547e2-104">Options</span></span>  
 <span data-ttu-id="547e2-105">**Usa configurazione errori predefinita**</span><span class="sxs-lookup"><span data-stu-id="547e2-105">**Use default error configuration**</span></span>  
 <span data-ttu-id="547e2-106">Selezionare questa opzione per utilizzare la configurazione errori predefinita per gli oggetti nell'operazione di elaborazione.</span><span class="sxs-lookup"><span data-stu-id="547e2-106">Select to use the default error configuration for objects in the processing operation.</span></span>  
  
 <span data-ttu-id="547e2-107">**Azione per errore chiave**</span><span class="sxs-lookup"><span data-stu-id="547e2-107">**Key error action**</span></span>  
 <span data-ttu-id="547e2-108">Consente di scegliere una delle azioni seguenti da eseguire quando viene rilevata una nuova chiave che non può essere ricercata durante l'elaborazione:</span><span class="sxs-lookup"><span data-stu-id="547e2-108">Choose one of the following actions that occur when a new key is encountered during processing that cannot be looked up:</span></span>  
  
-   <span data-ttu-id="547e2-109">**Converti in sconosciuta** aggrega le informazioni relative al record nel membro sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="547e2-109">**Convert to unknown** aggregates the information for the record into the unknown member.</span></span>  
  
-   <span data-ttu-id="547e2-110">**Scarta record** esclude le informazioni relative al record dall'elaborazione dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="547e2-110">**Discard record** excludes the information for the record from being processed with the object.</span></span>  
  
 <span data-ttu-id="547e2-111">**Ignora conteggio errori**</span><span class="sxs-lookup"><span data-stu-id="547e2-111">**Ignore errors count**</span></span>  
 <span data-ttu-id="547e2-112">Fare clic su questa opzione per ignorare qualsiasi eventuale errore che si verifichi durante l'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="547e2-112">Click to ignore any errors that occur when processing.</span></span>  
  
 <span data-ttu-id="547e2-113">**Arresta in caso di errore**</span><span class="sxs-lookup"><span data-stu-id="547e2-113">**Stop on error**</span></span>  
 <span data-ttu-id="547e2-114">Fare clic su questa opzione per arrestare l'elaborazione in caso di errori.</span><span class="sxs-lookup"><span data-stu-id="547e2-114">Click to stop processing when errors occur.</span></span> <span data-ttu-id="547e2-115">Questa opzione implica l'attivazione delle impostazioni **Numero di errori** e **Azione in caso di errore** .</span><span class="sxs-lookup"><span data-stu-id="547e2-115">This option enables the **Number of errors** and the **On error action** options.</span></span>  
  
 <span data-ttu-id="547e2-116">**Numero di errori**</span><span class="sxs-lookup"><span data-stu-id="547e2-116">**Number of errors**</span></span>  
 <span data-ttu-id="547e2-117">Consente di immettere il numero di errori che verranno ignorati prima di arrestare l'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="547e2-117">Type the number of errors that are ignored before processing stops.</span></span>  
  
 <span data-ttu-id="547e2-118">**Azione in caso di errore**</span><span class="sxs-lookup"><span data-stu-id="547e2-118">**On error action**</span></span>  
 <span data-ttu-id="547e2-119">Consente di scegliere una delle azioni seguenti da eseguire se il numero di errori supera il valore impostato in **Numero di errori**:</span><span class="sxs-lookup"><span data-stu-id="547e2-119">Choose one of the following actions to be taken when the number of errors exceeds the value in **Number of errors**:</span></span>  
  
-   <span data-ttu-id="547e2-120">**Arresta elaborazione** termina l'operazione di elaborazione.</span><span class="sxs-lookup"><span data-stu-id="547e2-120">**Stop processing** ends the processing operation.</span></span>  
  
-   <span data-ttu-id="547e2-121">**Arresta registrazione** arresta la registrazione degli errori senza però interrompere l'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="547e2-121">**Stop logging** stops logging errors, but continues the processing operation.</span></span>  
  
 <span data-ttu-id="547e2-122">**Chiave non trovata**</span><span class="sxs-lookup"><span data-stu-id="547e2-122">**Key not found**</span></span>  
 <span data-ttu-id="547e2-123">Specificare una delle azioni seguenti da eseguire quando non viene trovata una chiave durante l'elaborazione di un oggetto:</span><span class="sxs-lookup"><span data-stu-id="547e2-123">Specify one of the following actions to be taken when a key is not found when an object is processed:</span></span>  
  
-   <span data-ttu-id="547e2-124">**Ignora errore** ignora l'errore</span><span class="sxs-lookup"><span data-stu-id="547e2-124">**Ignore error** ignores the error</span></span>  
  
-   <span data-ttu-id="547e2-125">**Segnala e continua** segnala l'errore e continua l'operazione di elaborazione</span><span class="sxs-lookup"><span data-stu-id="547e2-125">**Report and continue** reports the error and continues the processing operation</span></span>  
  
-   <span data-ttu-id="547e2-126">**Segnala e arresta** segnala l'errore e arresta l'operazione di elaborazione.</span><span class="sxs-lookup"><span data-stu-id="547e2-126">**Report and stop** reports the error and stops the processing operation.</span></span>  
  
 <span data-ttu-id="547e2-127">**Chiave duplicata**</span><span class="sxs-lookup"><span data-stu-id="547e2-127">**Duplicate key**</span></span>  
 <span data-ttu-id="547e2-128">Specificare una delle azioni seguenti da eseguire se viene trovata una chiave duplicata durante l'elaborazione di un oggetto:</span><span class="sxs-lookup"><span data-stu-id="547e2-128">Specify one of the following actions to be taken if a duplicate key is found when an object is processed:</span></span>  
  
-   <span data-ttu-id="547e2-129">**Ignora errore** ignora l'errore</span><span class="sxs-lookup"><span data-stu-id="547e2-129">**Ignore error** ignores the error</span></span>  
  
-   <span data-ttu-id="547e2-130">**Segnala e continua** segnala l'errore e continua l'operazione di elaborazione</span><span class="sxs-lookup"><span data-stu-id="547e2-130">**Report and continue** reports the error and continues the processing operation</span></span>  
  
-   <span data-ttu-id="547e2-131">**Segnala e arresta** segnala l'errore e arresta l'operazione di elaborazione.</span><span class="sxs-lookup"><span data-stu-id="547e2-131">**Report and stop** reports the error and stops the processing operation.</span></span>  
  
 <span data-ttu-id="547e2-132">**Chiave Null convertita in sconosciuta**</span><span class="sxs-lookup"><span data-stu-id="547e2-132">**Null key converted to unknown**</span></span>  
 <span data-ttu-id="547e2-133">Consente di specificare una delle azioni seguenti da eseguire quando viene aggiunta una chiave membro Null al membro sconosciuto durante l'elaborazione di un oggetto.</span><span class="sxs-lookup"><span data-stu-id="547e2-133">Specify one of the following actions to be taken when a null member key is added to the unknown member when an object is processed.</span></span>  
  
-   <span data-ttu-id="547e2-134">**Ignora errore** ignora l'errore</span><span class="sxs-lookup"><span data-stu-id="547e2-134">**Ignore error** ignores the error</span></span>  
  
-   <span data-ttu-id="547e2-135">**Segnala e continua** segnala l'errore e continua l'operazione di elaborazione</span><span class="sxs-lookup"><span data-stu-id="547e2-135">**Report and continue** reports the error and continues the processing operation</span></span>  
  
-   <span data-ttu-id="547e2-136">**Segnala e arresta** segnala l'errore e arresta l'operazione di elaborazione.</span><span class="sxs-lookup"><span data-stu-id="547e2-136">**Report and stop** reports the error and stops the processing operation.</span></span>  
  
 <span data-ttu-id="547e2-137">**Chiave Null non consentita**</span><span class="sxs-lookup"><span data-stu-id="547e2-137">**Null key not allowed**</span></span>  
 <span data-ttu-id="547e2-138">Consente di specificare una delle azioni seguenti da eseguire quando viene trovata una chiave Null non consentita durante l'elaborazione di un oggetto.</span><span class="sxs-lookup"><span data-stu-id="547e2-138">Specify one of the following actions to be taken when a null key is found, but not allowed, when an object is processed.</span></span>  
  
-   <span data-ttu-id="547e2-139">**Ignora errore** ignora l'errore</span><span class="sxs-lookup"><span data-stu-id="547e2-139">**Ignore error** ignores the error</span></span>  
  
-   <span data-ttu-id="547e2-140">**Segnala e continua** segnala l'errore e continua l'operazione di elaborazione</span><span class="sxs-lookup"><span data-stu-id="547e2-140">**Report and continue** reports the error and continues the processing operation</span></span>  
  
-   <span data-ttu-id="547e2-141">**Segnala e arresta** segnala l'errore e arresta l'operazione di elaborazione.</span><span class="sxs-lookup"><span data-stu-id="547e2-141">**Report and stop** reports the error and stops the processing operation.</span></span>  
  
 <span data-ttu-id="547e2-142">**Percorso log degli errori**</span><span class="sxs-lookup"><span data-stu-id="547e2-142">**Error log path**</span></span>  
 <span data-ttu-id="547e2-143">Consente di digitare il percorso completo e il nome del file di log degli errori.</span><span class="sxs-lookup"><span data-stu-id="547e2-143">Type the full path and file name for the error log file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="547e2-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="547e2-144">See Also</span></span>  
 <span data-ttu-id="547e2-145">[Finestra di dialogo Proprietà struttura di data mining &#40;Analysis Services-&#41;di data mining](mining-structure-properties-dialog-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="547e2-145">[Mining Structure Properties Dialog &#40;Analysis Services - Data Mining&#41;](mining-structure-properties-dialog-analysis-services-data-mining.md) </span></span>  
 [<span data-ttu-id="547e2-146">&#40;finestra di dialogo struttura di data mining generale&#41; &#40;Analysis Services di data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="547e2-146">General &#40;Mining Structure Dialog Box&#41; &#40;Analysis Services - Data Mining&#41;</span></span>](general-mining-structure-dialog-box-analysis-services-data-mining.md)  
  
  
