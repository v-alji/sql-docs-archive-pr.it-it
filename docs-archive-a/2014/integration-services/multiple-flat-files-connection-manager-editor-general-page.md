---
title: Editor gestione connessione per più file flat (pagina generale) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.multifile.general.f1
helpviewer_keywords:
- Multiple Flat Files Connection Manager Editor
ms.assetid: 00129d43-2772-413b-bdf8-ac5de81cf4a5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f30a422794723f216d30e05f0750fb1e974e0920
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721580"
---
# <a name="multiple-flat-files-connection-manager-editor-general-page"></a><span data-ttu-id="5c9c4-102">Editor gestione connessione per più file flat (pagina Generale)</span><span class="sxs-lookup"><span data-stu-id="5c9c4-102">Multiple Flat Files Connection Manager Editor (General Page)</span></span>
  <span data-ttu-id="5c9c4-103">Utilizzare la pagina **Generale** della finestra di dialogo **Editor gestione connessione per più file flat** per selezionare un gruppo di file con lo stesso formato di dati e per specificare il loro formato dei dati.</span><span class="sxs-lookup"><span data-stu-id="5c9c4-103">Use the **General** page of the **Multiple Flat Files Connection Manager Editor** dialog box to select a group of files that have the same data format, and to specify their data format.</span></span> <span data-ttu-id="5c9c4-104">Una connessione per più file flat consente la connessione di un pacchetto a un gruppo di file di testo aventi lo stesso formato.</span><span class="sxs-lookup"><span data-stu-id="5c9c4-104">A multiple flat files connection enables a package to connect to a group of text files that have the same format.</span></span>  
  
 <span data-ttu-id="5c9c4-105">Per ulteriori informazioni sulla gestione connessione per più file flat, vedere [Multiple Flat Files Connection Manager](connection-manager/multiple-flat-files-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="5c9c4-105">To learn more about the Multiple Flat Files connection manager, see [Multiple Flat Files Connection Manager](connection-manager/multiple-flat-files-connection-manager.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="5c9c4-106">Opzioni</span><span class="sxs-lookup"><span data-stu-id="5c9c4-106">Options</span></span>  
 <span data-ttu-id="5c9c4-107">**Nome gestione connessione**</span><span class="sxs-lookup"><span data-stu-id="5c9c4-107">**Connection manager name**</span></span>  
 <span data-ttu-id="5c9c4-108">Consente di specificare un nome univoco per la connessione per più file flat nel flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="5c9c4-108">Provide a unique name for the Multiple Flat Files connection in the workflow.</span></span> <span data-ttu-id="5c9c4-109">Il nome specificato verrà visualizzato in Progettazione [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5c9c4-109">The name provided will be displayed within [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="5c9c4-110">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="5c9c4-110">**Description**</span></span>  
 <span data-ttu-id="5c9c4-111">Consente di aggiungere una descrizione per la connessione.</span><span class="sxs-lookup"><span data-stu-id="5c9c4-111">Describe the connection.</span></span> <span data-ttu-id="5c9c4-112">È consigliabile includere nella descrizione informazioni sugli scopi della connessione, in modo da ottenere pacchetti autodocumentati e semplificarne quindi la gestione.</span><span class="sxs-lookup"><span data-stu-id="5c9c4-112">As a best practice, describe the connection in terms of its purpose, to make packages self-documenting and easier to maintain.</span></span>  
  
 <span data-ttu-id="5c9c4-113">**Nomi file**</span><span class="sxs-lookup"><span data-stu-id="5c9c4-113">**File names**</span></span>  
 <span data-ttu-id="5c9c4-114">Consente di digitare il percorso e i nomi dei file da utilizzare nella connessione per più flat file.</span><span class="sxs-lookup"><span data-stu-id="5c9c4-114">Type the path and file names to use in the Multiple Flat Files connection.</span></span> <span data-ttu-id="5c9c4-115">È possibile specificare più file usando caratteri jolly, ad esempio "C:\\*.txt", oppure il carattere barra verticale (|) per separare più nomi di file.</span><span class="sxs-lookup"><span data-stu-id="5c9c4-115">You can specify multiple files by using wildcard characters, as in the example "C:\\*.txt", or by using the vertical pipe character (|) to separate multiple file names.</span></span> <span data-ttu-id="5c9c4-116">Tutti i file devono avere lo stesso formato data.</span><span class="sxs-lookup"><span data-stu-id="5c9c4-116">All files must have the same data format.</span></span>  
  
 <span data-ttu-id="5c9c4-117">**Sfoglia**</span><span class="sxs-lookup"><span data-stu-id="5c9c4-117">**Browse**</span></span>  
 <span data-ttu-id="5c9c4-118">Consente di cercare i nomi dei file da utilizzare nella connessione per più file flat.</span><span class="sxs-lookup"><span data-stu-id="5c9c4-118">Browse the file names to use in the Multiple Flat Files connection.</span></span> <span data-ttu-id="5c9c4-119">È possibile selezionare più file.</span><span class="sxs-lookup"><span data-stu-id="5c9c4-119">You can select multiple files.</span></span> <span data-ttu-id="5c9c4-120">Tutti i file devono avere lo stesso formato data.</span><span class="sxs-lookup"><span data-stu-id="5c9c4-120">All files must have the same data format.</span></span>  
  
 <span data-ttu-id="5c9c4-121">**Impostazioni locali**</span><span class="sxs-lookup"><span data-stu-id="5c9c4-121">**Locale**</span></span>  
 <span data-ttu-id="5c9c4-122">Consente di specificare la località per specificare informazioni relative all'ordinamento e alla conversione di data e ora.</span><span class="sxs-lookup"><span data-stu-id="5c9c4-122">Specify the location to provide information for ordering and for date and time conversion.</span></span>  
  
 <span data-ttu-id="5c9c4-123">**Unicode**</span><span class="sxs-lookup"><span data-stu-id="5c9c4-123">**Unicode**</span></span>  
 <span data-ttu-id="5c9c4-124">Indica se utilizzare il formato Unicode.</span><span class="sxs-lookup"><span data-stu-id="5c9c4-124">Indicate whether to use Unicode.</span></span> <span data-ttu-id="5c9c4-125">L'utilizzo di Unicode impedisce di specificare una tabella codici.</span><span class="sxs-lookup"><span data-stu-id="5c9c4-125">Using Unicode precludes specifying a code page.</span></span>  
  
 <span data-ttu-id="5c9c4-126">**Tabella codici**</span><span class="sxs-lookup"><span data-stu-id="5c9c4-126">**Code page**</span></span>  
 <span data-ttu-id="5c9c4-127">Consente di specificare la tabella codici per il testo non Unicode.</span><span class="sxs-lookup"><span data-stu-id="5c9c4-127">Specify the code page for non-Unicode text.</span></span>  
  
 <span data-ttu-id="5c9c4-128">**Formato**</span><span class="sxs-lookup"><span data-stu-id="5c9c4-128">**Format**</span></span>  
 <span data-ttu-id="5c9c4-129">Consente di indicare se utilizzare la formattazione non allineata a destra, a larghezza fissa o delimitata.</span><span class="sxs-lookup"><span data-stu-id="5c9c4-129">Indicate whether to use delimited, fixed width, or ragged right formatting.</span></span> <span data-ttu-id="5c9c4-130">Tutti i file devono avere lo stesso formato data.</span><span class="sxs-lookup"><span data-stu-id="5c9c4-130">All files must have the same data format.</span></span>  
  
|<span data-ttu-id="5c9c4-131">Valore</span><span class="sxs-lookup"><span data-stu-id="5c9c4-131">Value</span></span>|<span data-ttu-id="5c9c4-132">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5c9c4-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="5c9c4-133">Delimitato</span><span class="sxs-lookup"><span data-stu-id="5c9c4-133">Delimited</span></span>|<span data-ttu-id="5c9c4-134">Le colonne sono separate dai delimitatori specificati nella pagina **Colonne** .</span><span class="sxs-lookup"><span data-stu-id="5c9c4-134">Columns are separated by delimiters, specified on the **Columns** page.</span></span>|  
|<span data-ttu-id="5c9c4-135">File a larghezza fissa</span><span class="sxs-lookup"><span data-stu-id="5c9c4-135">Fixed width</span></span>|<span data-ttu-id="5c9c4-136">Le colonne hanno una larghezza fissa, specificata trascinando le linee dei marcatori nella pagina **Colonne** .</span><span class="sxs-lookup"><span data-stu-id="5c9c4-136">Columns have a fixed width, specified by dragging marker lines on the **Columns** page.</span></span>|  
|<span data-ttu-id="5c9c4-137">Non allineato a destra</span><span class="sxs-lookup"><span data-stu-id="5c9c4-137">Ragged right</span></span>|<span data-ttu-id="5c9c4-138">I file non allineati a destra sono file in cui ogni colonna ha una larghezza fissa, ad eccezione dell'ultima colonna, delimitata dal delimitatore di riga, che viene specificato nella pagina **Colonne** .</span><span class="sxs-lookup"><span data-stu-id="5c9c4-138">Ragged right files are files in which every column has a fixed width, except for the last column, which is delimited by the row delimiter, specified on the **Columns** page.</span></span>|  
  
 <span data-ttu-id="5c9c4-139">**Qualificatore di testo**</span><span class="sxs-lookup"><span data-stu-id="5c9c4-139">**Text qualifier**</span></span>  
 <span data-ttu-id="5c9c4-140">Consente di specificare il qualificatore di testo da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="5c9c4-140">Specify the text qualifier to use.</span></span> <span data-ttu-id="5c9c4-141">È possibile, ad esempio, racchiudere il testo tra virgolette.</span><span class="sxs-lookup"><span data-stu-id="5c9c4-141">For example, you can specify to enclose text with quotation marks.</span></span>  
  
 <span data-ttu-id="5c9c4-142">**Delimitatore riga di intestazione**</span><span class="sxs-lookup"><span data-stu-id="5c9c4-142">**Header row delimiter**</span></span>  
 <span data-ttu-id="5c9c4-143">Consente di selezionare il delimitatore per la riga di intestazione nell'elenco dei delimitatori disponibili oppure di immettere il testo per il delimitatore.</span><span class="sxs-lookup"><span data-stu-id="5c9c4-143">Select from the list of delimiters for header rows, or enter the delimiter text.</span></span>  
  
|<span data-ttu-id="5c9c4-144">Valore</span><span class="sxs-lookup"><span data-stu-id="5c9c4-144">Value</span></span>|<span data-ttu-id="5c9c4-145">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5c9c4-145">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="5c9c4-146">**{CR}{LF}**</span><span class="sxs-lookup"><span data-stu-id="5c9c4-146">**{CR}{LF}**</span></span>|<span data-ttu-id="5c9c4-147">La riga di intestazione è delimitata dalla combinazione di caratteri ritorno a capo/avanzamento riga.</span><span class="sxs-lookup"><span data-stu-id="5c9c4-147">The header row is delimited by a carriage return-line feed combination.</span></span>|  
|<span data-ttu-id="5c9c4-148">**{CR}**</span><span class="sxs-lookup"><span data-stu-id="5c9c4-148">**{CR}**</span></span>|<span data-ttu-id="5c9c4-149">La riga di intestazione è delimitata da un carattere di ritorno a capo.</span><span class="sxs-lookup"><span data-stu-id="5c9c4-149">The header row is delimited by a carriage return.</span></span>|  
|<span data-ttu-id="5c9c4-150">**{LF}**</span><span class="sxs-lookup"><span data-stu-id="5c9c4-150">**{LF}**</span></span>|<span data-ttu-id="5c9c4-151">La riga di intestazione è delimitata da un carattere di avanzamento riga.</span><span class="sxs-lookup"><span data-stu-id="5c9c4-151">The header row is delimited by a line feed.</span></span>|  
|<span data-ttu-id="5c9c4-152">**Punto e virgola {;}**</span><span class="sxs-lookup"><span data-stu-id="5c9c4-152">**Semicolon {;}**</span></span>|<span data-ttu-id="5c9c4-153">La riga di intestazione è delimitata da un carattere punto e virgola.</span><span class="sxs-lookup"><span data-stu-id="5c9c4-153">The header row is delimited by a semicolon.</span></span>|  
|<span data-ttu-id="5c9c4-154">**Due punti {:}**</span><span class="sxs-lookup"><span data-stu-id="5c9c4-154">**Colon {:}**</span></span>|<span data-ttu-id="5c9c4-155">La riga di intestazione è delimitata da un carattere due punti.</span><span class="sxs-lookup"><span data-stu-id="5c9c4-155">The header row is delimited by a colon.</span></span>|  
|<span data-ttu-id="5c9c4-156">**Virgola {,}**</span><span class="sxs-lookup"><span data-stu-id="5c9c4-156">**Comma {,}**</span></span>|<span data-ttu-id="5c9c4-157">La riga di intestazione è delimitata da una virgola.</span><span class="sxs-lookup"><span data-stu-id="5c9c4-157">The header row is delimited by a comma.</span></span>|  
|<span data-ttu-id="5c9c4-158">**Tabulazione {t}**</span><span class="sxs-lookup"><span data-stu-id="5c9c4-158">**Tab {t}**</span></span>|<span data-ttu-id="5c9c4-159">La riga di intestazione è delimitata da un carattere di tabulazione.</span><span class="sxs-lookup"><span data-stu-id="5c9c4-159">The header row is delimited by a tab.</span></span>|  
|<span data-ttu-id="5c9c4-160">**Barra verticale {&#124;}**</span><span class="sxs-lookup"><span data-stu-id="5c9c4-160">**Vertical bar {&#124;}**</span></span>|<span data-ttu-id="5c9c4-161">La riga di intestazione è delimitata da una barra verticale.</span><span class="sxs-lookup"><span data-stu-id="5c9c4-161">The header row is delimited by a vertical bar.</span></span>|  
  
 <span data-ttu-id="5c9c4-162">**Righe di intestazione da ignorare**</span><span class="sxs-lookup"><span data-stu-id="5c9c4-162">**Header rows to skip**</span></span>  
 <span data-ttu-id="5c9c4-163">Consente di specificare il numero di righe di intestazione da ignorare, se presenti.</span><span class="sxs-lookup"><span data-stu-id="5c9c4-163">Specify the number of header rows to skip, if any.</span></span>  
  
 <span data-ttu-id="5c9c4-164">**Nomi di colonne nella prima riga di dati**</span><span class="sxs-lookup"><span data-stu-id="5c9c4-164">**Column names in the first data row**</span></span>  
 <span data-ttu-id="5c9c4-165">Consente di indicare se prevedere o fornire nomi di colonne nella prima riga di dati.</span><span class="sxs-lookup"><span data-stu-id="5c9c4-165">Indicate whether to expect or provide column names in the first data row.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c9c4-166">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5c9c4-166">See Also</span></span>  
 <span data-ttu-id="5c9c4-167">[Guida di riferimento ai messaggi e agli errori di Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="5c9c4-167">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="5c9c4-168">[Editor gestione connessione per più file flat &#40;pagina colonne&#41;](../../2014/integration-services/multiple-flat-files-connection-manager-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="5c9c4-168">[Multiple Flat Files Connection Manager Editor &#40;Columns Page&#41;](../../2014/integration-services/multiple-flat-files-connection-manager-editor-columns-page.md) </span></span>  
 <span data-ttu-id="5c9c4-169">[Editor gestione connessione per più file flat &#40;pagina avanzate&#41;](../../2014/integration-services/multiple-flat-files-connection-manager-editor-advanced-page.md) </span><span class="sxs-lookup"><span data-stu-id="5c9c4-169">[Multiple Flat Files Connection Manager Editor &#40;Advanced Page&#41;](../../2014/integration-services/multiple-flat-files-connection-manager-editor-advanced-page.md) </span></span>  
 [<span data-ttu-id="5c9c4-170">Editor gestione connessione per più file flat &#40;pagina Anteprima&#41;</span><span class="sxs-lookup"><span data-stu-id="5c9c4-170">Multiple Flat Files Connection Manager Editor &#40;Preview Page&#41;</span></span>](../../2014/integration-services/multiple-flat-files-connection-manager-editor-preview-page.md)  
  
  
