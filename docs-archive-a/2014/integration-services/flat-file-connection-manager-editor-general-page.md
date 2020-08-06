---
title: Editor gestione connessione file flat (pagina generale) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.ffileconnection.general.f1
helpviewer_keywords:
- Flat File Connection Manager Editor
ms.assetid: 77296024-5c1a-4f6a-9665-0b50d45d744c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 478c7bcf56e300b47af93862bf66409a3c94b5f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624861"
---
# <a name="flat-file-connection-manager-editor-general-page"></a><span data-ttu-id="9c7f9-102">Editor gestione connessione file flat (pagina Generale)</span><span class="sxs-lookup"><span data-stu-id="9c7f9-102">Flat File Connection Manager Editor (General Page)</span></span>
  <span data-ttu-id="9c7f9-103">Utilizzare la pagina **Generale** della finestra di dialogo **Editor gestione connessione file flat** per selezionare un file e un formato di dati.</span><span class="sxs-lookup"><span data-stu-id="9c7f9-103">Use the **General** page of the **Flat File Connection Manager Editor** dialog box to select a file and data format.</span></span> <span data-ttu-id="9c7f9-104">Una connessione file flat consente a un pacchetto di connettersi a un file di testo.</span><span class="sxs-lookup"><span data-stu-id="9c7f9-104">A flat file connection enables a package to connect to a text file.</span></span>  
  
 <span data-ttu-id="9c7f9-105">Per ulteriori informazioni sull'Editor gestione connessione file flat, vedere [Flat File Connection Manager](connection-manager/file-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="9c7f9-105">To learn more about the Flat File connection manager, see [Flat File Connection Manager](connection-manager/file-connection-manager.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="9c7f9-106">Opzioni</span><span class="sxs-lookup"><span data-stu-id="9c7f9-106">Options</span></span>  
 <span data-ttu-id="9c7f9-107">**Nome gestione connessione**</span><span class="sxs-lookup"><span data-stu-id="9c7f9-107">**Connection manager name**</span></span>  
 <span data-ttu-id="9c7f9-108">Consente di specificare un nome univoco per la connessione file flat nel flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="9c7f9-108">Provide a unique name for the flat file connection in the workflow.</span></span> <span data-ttu-id="9c7f9-109">Il nome specificato verrà visualizzato in Progettazione [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9c7f9-109">The name provided will be displayed within [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="9c7f9-110">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="9c7f9-110">**Description**</span></span>  
 <span data-ttu-id="9c7f9-111">Consente di aggiungere una descrizione per la connessione.</span><span class="sxs-lookup"><span data-stu-id="9c7f9-111">Describe the connection.</span></span> <span data-ttu-id="9c7f9-112">È consigliabile includere nella descrizione informazioni sugli scopi della connessione, in modo da ottenere pacchetti autodocumentati e semplificarne quindi la gestione.</span><span class="sxs-lookup"><span data-stu-id="9c7f9-112">As a best practice, describe the connection in terms of its purpose, to make packages self-documenting and easier to maintain.</span></span>  
  
 <span data-ttu-id="9c7f9-113">**Nome file**</span><span class="sxs-lookup"><span data-stu-id="9c7f9-113">**File name**</span></span>  
 <span data-ttu-id="9c7f9-114">Consente di digitare il percorso e il nome del file da utilizzare nella connessione file flat.</span><span class="sxs-lookup"><span data-stu-id="9c7f9-114">Type the path and file name to use in the flat file connection.</span></span>  
  
 <span data-ttu-id="9c7f9-115">**Sfoglia**</span><span class="sxs-lookup"><span data-stu-id="9c7f9-115">**Browse**</span></span>  
 <span data-ttu-id="9c7f9-116">Consente di individuare il nome del file da utilizzare nella connessione file flat.</span><span class="sxs-lookup"><span data-stu-id="9c7f9-116">Locate the file name to use in the flat file connection.</span></span>  
  
 <span data-ttu-id="9c7f9-117">**Impostazioni locali**</span><span class="sxs-lookup"><span data-stu-id="9c7f9-117">**Locale**</span></span>  
 <span data-ttu-id="9c7f9-118">Consente di specificare le impostazioni locali specifiche di una lingua per l'ordinamento e i formati di data e ora.</span><span class="sxs-lookup"><span data-stu-id="9c7f9-118">Specify the locale to provide language-specific information for ordering and for date and time formats.</span></span>  
  
 <span data-ttu-id="9c7f9-119">**Unicode**</span><span class="sxs-lookup"><span data-stu-id="9c7f9-119">**Unicode**</span></span>  
 <span data-ttu-id="9c7f9-120">Indica se utilizzare il formato Unicode.</span><span class="sxs-lookup"><span data-stu-id="9c7f9-120">Indicate whether to use Unicode.</span></span> <span data-ttu-id="9c7f9-121">Se si utilizza il formato Unicode, non è possibile specificare una tabella codici.</span><span class="sxs-lookup"><span data-stu-id="9c7f9-121">If you use Unicode, you cannot specify a code page.</span></span>  
  
 <span data-ttu-id="9c7f9-122">**Tabella codici**</span><span class="sxs-lookup"><span data-stu-id="9c7f9-122">**Code page**</span></span>  
 <span data-ttu-id="9c7f9-123">Consente di specificare la tabella codici per il testo non Unicode.</span><span class="sxs-lookup"><span data-stu-id="9c7f9-123">Specify the code page for non-Unicode text.</span></span>  
  
 <span data-ttu-id="9c7f9-124">**Formato**</span><span class="sxs-lookup"><span data-stu-id="9c7f9-124">**Format**</span></span>  
 <span data-ttu-id="9c7f9-125">Consente di indicare se il file utilizza il tipo di formattazione delimitato, a larghezza fissa o non allineato a destra.</span><span class="sxs-lookup"><span data-stu-id="9c7f9-125">Indicate whether the file uses delimited, fixed width, or ragged right formatting.</span></span>  
  
|<span data-ttu-id="9c7f9-126">Valore</span><span class="sxs-lookup"><span data-stu-id="9c7f9-126">Value</span></span>|<span data-ttu-id="9c7f9-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9c7f9-127">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="9c7f9-128">Delimitato</span><span class="sxs-lookup"><span data-stu-id="9c7f9-128">Delimited</span></span>|<span data-ttu-id="9c7f9-129">Le colonne sono separate dai delimitatori specificati nella pagina **Colonne** .</span><span class="sxs-lookup"><span data-stu-id="9c7f9-129">Columns are separated by delimiters, specified on the **Columns** page.</span></span>|  
|<span data-ttu-id="9c7f9-130">File a larghezza fissa</span><span class="sxs-lookup"><span data-stu-id="9c7f9-130">Fixed width</span></span>|<span data-ttu-id="9c7f9-131">Le colonne hanno una larghezza fissa.</span><span class="sxs-lookup"><span data-stu-id="9c7f9-131">Columns have a fixed width.</span></span>|  
|<span data-ttu-id="9c7f9-132">Non allineato a destra</span><span class="sxs-lookup"><span data-stu-id="9c7f9-132">Ragged right</span></span>|<span data-ttu-id="9c7f9-133">I file non allineati a destra sono file in cui ogni colonna ha una larghezza fissa, ad eccezione dell'ultima.</span><span class="sxs-lookup"><span data-stu-id="9c7f9-133">Ragged right files are files in which every column has a fixed width, except for the last column.</span></span> <span data-ttu-id="9c7f9-134">L'ultima colonna è delimitata dal delimitatore di riga.</span><span class="sxs-lookup"><span data-stu-id="9c7f9-134">It is delimited by the row delimiter.</span></span>|  
  
 <span data-ttu-id="9c7f9-135">**Qualificatore di testo**</span><span class="sxs-lookup"><span data-stu-id="9c7f9-135">**Text qualifier**</span></span>  
 <span data-ttu-id="9c7f9-136">Consente di specificare il qualificatore di testo da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="9c7f9-136">Specify the text qualifier to use.</span></span> <span data-ttu-id="9c7f9-137">Ad esempio, è possibile specificare che i campi di testo siano racchiusi tra virgolette.</span><span class="sxs-lookup"><span data-stu-id="9c7f9-137">For example, you can specify that text fields are enclosed in quotation marks.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9c7f9-138">Dopo aver selezionato un qualificatore di testo non è possibile selezionare di nuovo l'opzione **Nessuno** .</span><span class="sxs-lookup"><span data-stu-id="9c7f9-138">After you select a text qualifier, you cannot re-select the **None** option.</span></span> <span data-ttu-id="9c7f9-139">Digitare **Nessuno** per deselezionare il qualificatore di testo.</span><span class="sxs-lookup"><span data-stu-id="9c7f9-139">Type **None** to de-select the text qualifier.</span></span>  
  
 <span data-ttu-id="9c7f9-140">**Delimitatore riga di intestazione**</span><span class="sxs-lookup"><span data-stu-id="9c7f9-140">**Header row delimiter**</span></span>  
 <span data-ttu-id="9c7f9-141">Consente di selezionare il delimitatore per la riga di intestazione nell'elenco dei delimitatori disponibili oppure di immettere il testo per il delimitatore.</span><span class="sxs-lookup"><span data-stu-id="9c7f9-141">Select from the list of delimiters for header rows, or enter the delimiter text.</span></span>  
  
|<span data-ttu-id="9c7f9-142">Valore</span><span class="sxs-lookup"><span data-stu-id="9c7f9-142">Value</span></span>|<span data-ttu-id="9c7f9-143">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9c7f9-143">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="9c7f9-144">**{CR}{LF}**</span><span class="sxs-lookup"><span data-stu-id="9c7f9-144">**{CR}{LF}**</span></span>|<span data-ttu-id="9c7f9-145">La riga di intestazione è delimitata dalla combinazione di caratteri ritorno a capo/avanzamento riga.</span><span class="sxs-lookup"><span data-stu-id="9c7f9-145">The header row is delimited by a carriage return-line feed combination.</span></span>|  
|<span data-ttu-id="9c7f9-146">**{CR}**</span><span class="sxs-lookup"><span data-stu-id="9c7f9-146">**{CR}**</span></span>|<span data-ttu-id="9c7f9-147">La riga di intestazione è delimitata da un carattere di ritorno a capo.</span><span class="sxs-lookup"><span data-stu-id="9c7f9-147">The header row is delimited by a carriage return.</span></span>|  
|<span data-ttu-id="9c7f9-148">**{LF}**</span><span class="sxs-lookup"><span data-stu-id="9c7f9-148">**{LF}**</span></span>|<span data-ttu-id="9c7f9-149">La riga di intestazione è delimitata da un carattere di avanzamento riga.</span><span class="sxs-lookup"><span data-stu-id="9c7f9-149">The header row is delimited by a line feed.</span></span>|  
|<span data-ttu-id="9c7f9-150">**Punto e virgola {;}**</span><span class="sxs-lookup"><span data-stu-id="9c7f9-150">**Semicolon {;}**</span></span>|<span data-ttu-id="9c7f9-151">La riga di intestazione è delimitata da un carattere punto e virgola.</span><span class="sxs-lookup"><span data-stu-id="9c7f9-151">The header row is delimited by a semicolon.</span></span>|  
|<span data-ttu-id="9c7f9-152">**Due punti {:}**</span><span class="sxs-lookup"><span data-stu-id="9c7f9-152">**Colon {:}**</span></span>|<span data-ttu-id="9c7f9-153">La riga di intestazione è delimitata da un carattere due punti.</span><span class="sxs-lookup"><span data-stu-id="9c7f9-153">The header row is delimited by a colon.</span></span>|  
|<span data-ttu-id="9c7f9-154">**Virgola {,}**</span><span class="sxs-lookup"><span data-stu-id="9c7f9-154">**Comma {,}**</span></span>|<span data-ttu-id="9c7f9-155">La riga di intestazione è delimitata da una virgola.</span><span class="sxs-lookup"><span data-stu-id="9c7f9-155">The header row is delimited by a comma.</span></span>|  
|<span data-ttu-id="9c7f9-156">**Tabulazione {t}**</span><span class="sxs-lookup"><span data-stu-id="9c7f9-156">**Tab {t}**</span></span>|<span data-ttu-id="9c7f9-157">La riga di intestazione è delimitata da un carattere di tabulazione.</span><span class="sxs-lookup"><span data-stu-id="9c7f9-157">The header row is delimited by a tab.</span></span>|  
|<span data-ttu-id="9c7f9-158">**Barra verticale {&#124;}**</span><span class="sxs-lookup"><span data-stu-id="9c7f9-158">**Vertical bar {&#124;}**</span></span>|<span data-ttu-id="9c7f9-159">La riga di intestazione è delimitata da una barra verticale.</span><span class="sxs-lookup"><span data-stu-id="9c7f9-159">The header row is delimited by a vertical bar.</span></span>|  
  
 <span data-ttu-id="9c7f9-160">**Righe di intestazione da ignorare**</span><span class="sxs-lookup"><span data-stu-id="9c7f9-160">**Header rows to skip**</span></span>  
 <span data-ttu-id="9c7f9-161">Consente di specificare il numero di eventuali righe di intestazione o righe di dati iniziali da ignorare.</span><span class="sxs-lookup"><span data-stu-id="9c7f9-161">Specify the number of header rows or initial data rows to skip, if any.</span></span>  
  
 <span data-ttu-id="9c7f9-162">**Nomi di colonne nella prima riga di dati**</span><span class="sxs-lookup"><span data-stu-id="9c7f9-162">**Column names in the first data row**</span></span>  
 <span data-ttu-id="9c7f9-163">Consente di indicare se prevedere o fornire nomi di colonne nella prima riga di dati.</span><span class="sxs-lookup"><span data-stu-id="9c7f9-163">Indicate whether to expect or provide column names in the first data row.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c7f9-164">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9c7f9-164">See Also</span></span>  
 <span data-ttu-id="9c7f9-165">[Guida di riferimento ai messaggi e agli errori di Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="9c7f9-165">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="9c7f9-166">[Editor gestione connessione file flat &#40;pagina colonne&#41;](../../2014/integration-services/flat-file-connection-manager-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="9c7f9-166">[Flat File Connection Manager Editor &#40;Columns Page&#41;](../../2014/integration-services/flat-file-connection-manager-editor-columns-page.md) </span></span>  
 <span data-ttu-id="9c7f9-167">[Editor gestione connessione file flat &#40;pagina avanzate&#41;](../../2014/integration-services/flat-file-connection-manager-editor-advanced-page.md) </span><span class="sxs-lookup"><span data-stu-id="9c7f9-167">[Flat File Connection Manager Editor &#40;Advanced Page&#41;](../../2014/integration-services/flat-file-connection-manager-editor-advanced-page.md) </span></span>  
 [<span data-ttu-id="9c7f9-168">Editor gestione connessione file flat &#40;pagina Anteprima&#41;</span><span class="sxs-lookup"><span data-stu-id="9c7f9-168">Flat File Connection Manager Editor &#40;Preview Page&#41;</span></span>](../../2014/integration-services/flat-file-connection-manager-editor-preview-page.md)  
  
  
