---
title: Barra di divisione CDC | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.designer.cdcsplitter.f1
ms.assetid: 167bc5c6-fa36-439d-987c-b20acd1a77e2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 45dd16602625b28d2ca7e16f2fa6b0d62294fe81
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629951"
---
# <a name="cdc-splitter"></a><span data-ttu-id="10ca6-102">CDC Splitter</span><span class="sxs-lookup"><span data-stu-id="10ca6-102">CDC Splitter</span></span>
  <span data-ttu-id="10ca6-103">La barra di divisione CDC suddivide un singolo flusso di righe delle modifiche da un flusso di dati dell'origine CDC in diversi flussi di dati per operazioni di inserimento, aggiornamento ed eliminazione.</span><span class="sxs-lookup"><span data-stu-id="10ca6-103">The CDC splitter splits a single flow of change rows from a CDC source data flow into different data flows for Insert, Update and Delete operations.</span></span> <span data-ttu-id="10ca6-104">Il flusso di dati viene suddiviso in base alla colonna obbligatoria `__$operation` e ai relativi valori standard nelle tabelle delle modifiche di [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="10ca6-104">The data flow is split based on the required column `__$operation` and its standard values in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] change tables.</span></span>  
  
|<span data-ttu-id="10ca6-105">Valore dell'operazione</span><span class="sxs-lookup"><span data-stu-id="10ca6-105">Value of Operation</span></span>|<span data-ttu-id="10ca6-106">Output</span><span class="sxs-lookup"><span data-stu-id="10ca6-106">Output</span></span>|<span data-ttu-id="10ca6-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="10ca6-107">Description</span></span>|  
|------------------------|------------|-----------------|  
|<span data-ttu-id="10ca6-108">1</span><span class="sxs-lookup"><span data-stu-id="10ca6-108">1</span></span>|<span data-ttu-id="10ca6-109">Delete</span><span class="sxs-lookup"><span data-stu-id="10ca6-109">Delete</span></span>|<span data-ttu-id="10ca6-110">Riga eliminata</span><span class="sxs-lookup"><span data-stu-id="10ca6-110">Deleted Row</span></span>|  
|<span data-ttu-id="10ca6-111">2</span><span class="sxs-lookup"><span data-stu-id="10ca6-111">2</span></span>|<span data-ttu-id="10ca6-112">Inserimento</span><span class="sxs-lookup"><span data-stu-id="10ca6-112">Insert</span></span>|<span data-ttu-id="10ca6-113">Riga inserita (non disponibile quando si usa la modalità CDC **Net with Merge** (Rete con unione))</span><span class="sxs-lookup"><span data-stu-id="10ca6-113">Inserted row (not available when using **Net with Merge** CDC mode)</span></span>|  
|<span data-ttu-id="10ca6-114">3</span><span class="sxs-lookup"><span data-stu-id="10ca6-114">3</span></span>|<span data-ttu-id="10ca6-115">Aggiornamento</span><span class="sxs-lookup"><span data-stu-id="10ca6-115">Update</span></span>|<span data-ttu-id="10ca6-116">Riga prima dell'aggiornamento (disponibile solo quando si usa la modalità CDC **All with Old Values** (Tutto con valori precedenti))</span><span class="sxs-lookup"><span data-stu-id="10ca6-116">Before-update row (available only when using **All with Old Values** CDC mode)</span></span>|  
|<span data-ttu-id="10ca6-117">4</span><span class="sxs-lookup"><span data-stu-id="10ca6-117">4</span></span>|<span data-ttu-id="10ca6-118">Aggiornamento</span><span class="sxs-lookup"><span data-stu-id="10ca6-118">Update</span></span>|<span data-ttu-id="10ca6-119">Riga dopo l'aggiornamento (segue l'operazione prima dell'aggiornamento)</span><span class="sxs-lookup"><span data-stu-id="10ca6-119">After-update row (follows the Before-update)</span></span>|  
|<span data-ttu-id="10ca6-120">5</span><span class="sxs-lookup"><span data-stu-id="10ca6-120">5</span></span>|<span data-ttu-id="10ca6-121">Aggiornamento</span><span class="sxs-lookup"><span data-stu-id="10ca6-121">Update</span></span>|<span data-ttu-id="10ca6-122">Unione della riga (disponibile solo quando si usa la modalità CDC **Net with Merge** (Rete con unione))</span><span class="sxs-lookup"><span data-stu-id="10ca6-122">Merge row (available only when using **Net with Merge** CDC mode)</span></span>|  
|<span data-ttu-id="10ca6-123">Altri</span><span class="sxs-lookup"><span data-stu-id="10ca6-123">Other</span></span>|<span data-ttu-id="10ca6-124">Errore</span><span class="sxs-lookup"><span data-stu-id="10ca6-124">Error</span></span>||  
  
 <span data-ttu-id="10ca6-125">È possibile utilizzare la barra di divisione per connettersi ad output INSERT, DELETE e UPDATE predefiniti per l'ulteriore elaborazione.</span><span class="sxs-lookup"><span data-stu-id="10ca6-125">You can use the splitter to connect to pre-defined INSERT, DELETE, and UPDATE outputs for further processing.</span></span>  
  
 <span data-ttu-id="10ca6-126">La trasformazione CDC Splitter include un input normale e un output degli errori.</span><span class="sxs-lookup"><span data-stu-id="10ca6-126">The CDC Splitter transformation has one regular input and one error output.</span></span>  
  
## <a name="error-handling"></a><span data-ttu-id="10ca6-127">Gestione degli errori</span><span class="sxs-lookup"><span data-stu-id="10ca6-127">Error Handling</span></span>  
 <span data-ttu-id="10ca6-128">La trasformazione CDC Splitter include un output degli errori.</span><span class="sxs-lookup"><span data-stu-id="10ca6-128">The CDC Splitter transformation has an error output.</span></span> <span data-ttu-id="10ca6-129">Le righe di input con un valore non valido della colonna $operation vengono considerate errate e vengono gestite in base alla proprietà **ErrorRowDisposition** dell'input.</span><span class="sxs-lookup"><span data-stu-id="10ca6-129">Input rows with an invalid value of the $operation column are considered erroneous and are handled according to the **ErrorRowDisposition** property of the input.</span></span>  
  
 <span data-ttu-id="10ca6-130">L'output degli errori del componente include le colonne di output seguenti:</span><span class="sxs-lookup"><span data-stu-id="10ca6-130">The component error output includes the following output columns:</span></span>  
  
-   <span data-ttu-id="10ca6-131">**Error Code**: impostare su 1.</span><span class="sxs-lookup"><span data-stu-id="10ca6-131">**Error Code**: Set to 1.</span></span>  
  
-   <span data-ttu-id="10ca6-132">**Error Column**(Colonna errore): colonna di origine che provoca l'errore (per gli errori di conversione).</span><span class="sxs-lookup"><span data-stu-id="10ca6-132">**Error Column**: The source column causing the error (for conversion errors).</span></span>  
  
-   <span data-ttu-id="10ca6-133">**Error Row Columns**: colonne di input della riga che ha provocato l'errore.</span><span class="sxs-lookup"><span data-stu-id="10ca6-133">**Error Row Columns**: The input columns of the row that caused the error.</span></span>  
  
## <a name="configuring-the-cdc-splitter"></a><span data-ttu-id="10ca6-134">Configurazione della barra di divisione CDC</span><span class="sxs-lookup"><span data-stu-id="10ca6-134">Configuring the CDC Splitter</span></span>  
 <span data-ttu-id="10ca6-135">Non sono disponibili proprietà configurabili per la barra di divisione CDC.</span><span class="sxs-lookup"><span data-stu-id="10ca6-135">There are no configurable properties for the CDC splitter.</span></span>  
  
 <span data-ttu-id="10ca6-136">Per ulteriori informazioni sull'utilizzo della barra di divisione CDC, vedere Componenti CDC per Microsoft SQL Server Integration Services.</span><span class="sxs-lookup"><span data-stu-id="10ca6-136">For more information about using the CDC splitter, see CDC Components for Microsoft SQL Server Integration Services.</span></span>  
  
 <span data-ttu-id="10ca6-137">La finestra di dialogo **Editor avanzato** contiene le proprietà che è possibile impostare a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="10ca6-137">The **Advanced Editor** dialog box contains the properties that can be set programmatically.</span></span>  
  
 <span data-ttu-id="10ca6-138">Per aprire la finestra di dialogo **Editor avanzato** :</span><span class="sxs-lookup"><span data-stu-id="10ca6-138">To open the **Advanced Editor** dialog box:</span></span>  
  
-   <span data-ttu-id="10ca6-139">Nella schermata **Flusso di dati** del progetto di [!INCLUDE[ssISCurrent](../../includes/ssiscurrent-md.md)] fare clic con il pulsante destro del mouse sulla barra di divisione CDC e scegliere **Visualizza editor avanzato**.</span><span class="sxs-lookup"><span data-stu-id="10ca6-139">In the **Data Flow** screen of your [!INCLUDE[ssISCurrent](../../includes/ssiscurrent-md.md)] project, right click the CDC splitter and select **Show Advanced Editor**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10ca6-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="10ca6-140">See Also</span></span>  
 [<span data-ttu-id="10ca6-141">Indirizzare il flusso CDC in base al tipo di modifica</span><span class="sxs-lookup"><span data-stu-id="10ca6-141">Direct the CDC Stream According to the Type of Change</span></span>](direct-the-cdc-stream-according-to-the-type-of-change.md)  
  
  
