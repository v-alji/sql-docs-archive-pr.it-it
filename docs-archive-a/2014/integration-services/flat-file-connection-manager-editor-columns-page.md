---
title: Editor gestione connessione file flat (pagina colonne) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.ffileconnection.columns.f1
helpviewer_keywords:
- Flat File Connection Manager Editor
ms.assetid: 40ce7537-abd0-4973-97fd-6ccb90fddfa0
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f6ce579f73922d2eaa2c48e98a98f52cd5836f5b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624859"
---
# <a name="flat-file-connection-manager-editor-columns-page"></a><span data-ttu-id="fed6d-102">Editor gestione connessione file flat (pagina Colonne)</span><span class="sxs-lookup"><span data-stu-id="fed6d-102">Flat File Connection Manager Editor (Columns Page)</span></span>
  <span data-ttu-id="fed6d-103">Utilizzare la pagina **Colonne** della finestra di dialogo **Editor gestione connessione file flat** per specificare le informazioni di riga e di colonna e per visualizzare un'anteprima del file.</span><span class="sxs-lookup"><span data-stu-id="fed6d-103">Use the **Columns** page of the **Flat File Connection Manager Editor** dialog box to specify the row and column information, and to preview the file.</span></span>  
  
 <span data-ttu-id="fed6d-104">Per ulteriori informazioni sull'Editor gestione connessione file flat, vedere [Flat File Connection Manager](connection-manager/file-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="fed6d-104">To learn more about the Flat File connection manager, see [Flat File Connection Manager](connection-manager/file-connection-manager.md).</span></span>  
  
## <a name="static-options"></a><span data-ttu-id="fed6d-105">Opzioni statiche</span><span class="sxs-lookup"><span data-stu-id="fed6d-105">Static Options</span></span>  
 <span data-ttu-id="fed6d-106">**Nome gestione connessione**</span><span class="sxs-lookup"><span data-stu-id="fed6d-106">**Connection manager name**</span></span>  
 <span data-ttu-id="fed6d-107">Consente di specificare un nome univoco per la connessione del file flat nel flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="fed6d-107">Provide a unique name for the Flat File connection in the workflow.</span></span> <span data-ttu-id="fed6d-108">Il nome specificato verrà visualizzato in Progettazione [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fed6d-108">The name provided will be displayed within [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="fed6d-109">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="fed6d-109">**Description**</span></span>  
 <span data-ttu-id="fed6d-110">Consente di aggiungere una descrizione per la connessione.</span><span class="sxs-lookup"><span data-stu-id="fed6d-110">Describe the connection.</span></span> <span data-ttu-id="fed6d-111">È consigliabile includere nella descrizione informazioni sugli scopi della connessione, in modo da ottenere pacchetti autodocumentati e semplificarne quindi la gestione.</span><span class="sxs-lookup"><span data-stu-id="fed6d-111">As a best practice, describe the connection in terms of its purpose, to make packages self-documenting and easier to maintain.</span></span>  
  
## <a name="flat-file-format-dynamic-options"></a><span data-ttu-id="fed6d-112">Opzioni dinamiche relative al formato file flat</span><span class="sxs-lookup"><span data-stu-id="fed6d-112">Flat File Format Dynamic Options</span></span>  
  
### <a name="format--delimited"></a><span data-ttu-id="fed6d-113">Formato = Delimitato</span><span class="sxs-lookup"><span data-stu-id="fed6d-113">Format = Delimited</span></span>  
 <span data-ttu-id="fed6d-114">**Delimitatore di riga**</span><span class="sxs-lookup"><span data-stu-id="fed6d-114">**Row delimiter**</span></span>  
 <span data-ttu-id="fed6d-115">Consente di selezionare il delimitatore di riga desiderato nell'elenco dei delimitatori disponibili oppure di immettere il testo per il delimitatore.</span><span class="sxs-lookup"><span data-stu-id="fed6d-115">Select from the list of available row delimiters, or enter the delimiter text.</span></span>  
  
|<span data-ttu-id="fed6d-116">Valore</span><span class="sxs-lookup"><span data-stu-id="fed6d-116">Value</span></span>|<span data-ttu-id="fed6d-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fed6d-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="fed6d-118">**{CR}{LF}**</span><span class="sxs-lookup"><span data-stu-id="fed6d-118">**{CR}{LF}**</span></span>|<span data-ttu-id="fed6d-119">Le righe sono delimitate dalla combinazione di caratteri ritorno a capo/avanzamento riga.</span><span class="sxs-lookup"><span data-stu-id="fed6d-119">Rows are delimited by a carriage return-line feed combination.</span></span>|  
|<span data-ttu-id="fed6d-120">**{CR}**</span><span class="sxs-lookup"><span data-stu-id="fed6d-120">**{CR}**</span></span>|<span data-ttu-id="fed6d-121">Le righe sono delimitate da un ritorno a capo.</span><span class="sxs-lookup"><span data-stu-id="fed6d-121">Rows are delimited by a carriage return.</span></span>|  
|<span data-ttu-id="fed6d-122">**{LF}**</span><span class="sxs-lookup"><span data-stu-id="fed6d-122">**{LF}**</span></span>|<span data-ttu-id="fed6d-123">Le righe sono delimitate da un avanzamento riga.</span><span class="sxs-lookup"><span data-stu-id="fed6d-123">Rows are delimited by a line feed.</span></span>|  
|<span data-ttu-id="fed6d-124">**Punto e virgola {;}**</span><span class="sxs-lookup"><span data-stu-id="fed6d-124">**Semicolon {;}**</span></span>|<span data-ttu-id="fed6d-125">Le righe sono delimitate da un punto e virgola.</span><span class="sxs-lookup"><span data-stu-id="fed6d-125">Rows are delimited by a semicolon.</span></span>|  
|<span data-ttu-id="fed6d-126">**Due punti {:}**</span><span class="sxs-lookup"><span data-stu-id="fed6d-126">**Colon {:}**</span></span>|<span data-ttu-id="fed6d-127">Le righe sono delimitate da un carattere due punti.</span><span class="sxs-lookup"><span data-stu-id="fed6d-127">Rows are delimited by a colon.</span></span>|  
|<span data-ttu-id="fed6d-128">**Virgola {,}**</span><span class="sxs-lookup"><span data-stu-id="fed6d-128">**Comma {,}**</span></span>|<span data-ttu-id="fed6d-129">Le righe sono delimitate da una virgola.</span><span class="sxs-lookup"><span data-stu-id="fed6d-129">Rows are delimited by a comma.</span></span>|  
|<span data-ttu-id="fed6d-130">**Tabulazione {t}**</span><span class="sxs-lookup"><span data-stu-id="fed6d-130">**Tab {t}**</span></span>|<span data-ttu-id="fed6d-131">Le righe sono delimitate da un carattere di tabulazione.</span><span class="sxs-lookup"><span data-stu-id="fed6d-131">Rows are delimited by a tab.</span></span>|  
|<span data-ttu-id="fed6d-132">**Barra verticale {&#124;}**</span><span class="sxs-lookup"><span data-stu-id="fed6d-132">**Vertical bar {&#124;}**</span></span>|<span data-ttu-id="fed6d-133">Le righe sono delimitate da una barra verticale.</span><span class="sxs-lookup"><span data-stu-id="fed6d-133">Rows are delimited by a vertical bar.</span></span>|  
  
 <span data-ttu-id="fed6d-134">**Delimitatore di colonna**</span><span class="sxs-lookup"><span data-stu-id="fed6d-134">**Column delimiter**</span></span>  
 <span data-ttu-id="fed6d-135">Consente di selezionare il delimitatore di colonna desiderato nell'elenco dei delimitatori disponibili oppure di immettere il testo per il delimitatore.</span><span class="sxs-lookup"><span data-stu-id="fed6d-135">Select from the list of available column delimiters, or enter the delimiter text.</span></span>  
  
|<span data-ttu-id="fed6d-136">Valore</span><span class="sxs-lookup"><span data-stu-id="fed6d-136">Value</span></span>|<span data-ttu-id="fed6d-137">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fed6d-137">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="fed6d-138">**{CR}{LF}**</span><span class="sxs-lookup"><span data-stu-id="fed6d-138">**{CR}{LF}**</span></span>|<span data-ttu-id="fed6d-139">Le colonne sono delimitate dalla combinazione di caratteri ritorno a capo/avanzamento riga.</span><span class="sxs-lookup"><span data-stu-id="fed6d-139">Columns are delimited by a carriage return-line feed combination.</span></span>|  
|<span data-ttu-id="fed6d-140">**{CR}**</span><span class="sxs-lookup"><span data-stu-id="fed6d-140">**{CR}**</span></span>|<span data-ttu-id="fed6d-141">Le colonne sono delimitate da un ritorno a capo.</span><span class="sxs-lookup"><span data-stu-id="fed6d-141">Columns are delimited by a carriage return.</span></span>|  
|<span data-ttu-id="fed6d-142">**{LF}**</span><span class="sxs-lookup"><span data-stu-id="fed6d-142">**{LF}**</span></span>|<span data-ttu-id="fed6d-143">Le colonne sono delimitate da un avanzamento riga.</span><span class="sxs-lookup"><span data-stu-id="fed6d-143">Columns are delimited by a line feed.</span></span>|  
|<span data-ttu-id="fed6d-144">**Punto e virgola {;}**</span><span class="sxs-lookup"><span data-stu-id="fed6d-144">**Semicolon {;}**</span></span>|<span data-ttu-id="fed6d-145">Le colonne sono delimitate da un punto e virgola.</span><span class="sxs-lookup"><span data-stu-id="fed6d-145">Columns are delimited by a semicolon.</span></span>|  
|<span data-ttu-id="fed6d-146">**Due punti {:}**</span><span class="sxs-lookup"><span data-stu-id="fed6d-146">**Colon {:}**</span></span>|<span data-ttu-id="fed6d-147">Le colonne sono delimitate da due punti.</span><span class="sxs-lookup"><span data-stu-id="fed6d-147">Columns are delimited by a colon.</span></span>|  
|<span data-ttu-id="fed6d-148">**Virgola {,}**</span><span class="sxs-lookup"><span data-stu-id="fed6d-148">**Comma {,}**</span></span>|<span data-ttu-id="fed6d-149">Le colonne sono delimitate da una virgola.</span><span class="sxs-lookup"><span data-stu-id="fed6d-149">Columns are delimited by a comma.</span></span>|  
|<span data-ttu-id="fed6d-150">**Tabulazione {t}**</span><span class="sxs-lookup"><span data-stu-id="fed6d-150">**Tab {t}**</span></span>|<span data-ttu-id="fed6d-151">Le colonne sono delimitate da una tabulazione.</span><span class="sxs-lookup"><span data-stu-id="fed6d-151">Columns are delimited by a tab.</span></span>|  
|<span data-ttu-id="fed6d-152">**Barra verticale {&#124;}**</span><span class="sxs-lookup"><span data-stu-id="fed6d-152">**Vertical bar {&#124;}**</span></span>|<span data-ttu-id="fed6d-153">Le colonne sono delimitate da una barra verticale.</span><span class="sxs-lookup"><span data-stu-id="fed6d-153">Columns are delimited by a vertical bar.</span></span>|  
  
 <span data-ttu-id="fed6d-154">**Aggiorna**</span><span class="sxs-lookup"><span data-stu-id="fed6d-154">**Refresh**</span></span>  
 <span data-ttu-id="fed6d-155">Se si fa clic su **Aggiorna**è possibile visualizzare gli effetti delle modifiche ai delimitatori da ignorare.</span><span class="sxs-lookup"><span data-stu-id="fed6d-155">View the effect of changing the delimiters to skip by clicking **Refresh**.</span></span> <span data-ttu-id="fed6d-156">Questo pulsante viene visualizzato solo dopo la modifica di altre opzioni della connessione.</span><span class="sxs-lookup"><span data-stu-id="fed6d-156">This button only becomes visible after you have changed other connection options.</span></span>  
  
 <span data-ttu-id="fed6d-157">**Anteprima righe**</span><span class="sxs-lookup"><span data-stu-id="fed6d-157">**Preview rows**</span></span>  
 <span data-ttu-id="fed6d-158">Consente di visualizzare dati di esempio del file flat, suddivisi in righe e colonne in base alle opzioni selezionate.</span><span class="sxs-lookup"><span data-stu-id="fed6d-158">View sample data in the flat file, divided into columns and rows by using the options selected.</span></span>  
  
 <span data-ttu-id="fed6d-159">**Reimposta colonne**</span><span class="sxs-lookup"><span data-stu-id="fed6d-159">**Reset Columns**</span></span>  
 <span data-ttu-id="fed6d-160">Il pulsante **Reimposta colonne**consente di rimuovere tutte le colonne tranne quelle originali.</span><span class="sxs-lookup"><span data-stu-id="fed6d-160">Remove all but the original columns by clicking **Reset Columns**.</span></span>  
  
### <a name="format--fixed-width"></a><span data-ttu-id="fed6d-161">Formato = A larghezza fissa</span><span class="sxs-lookup"><span data-stu-id="fed6d-161">Format = Fixed Width</span></span>  
 <span data-ttu-id="fed6d-162">**Carattere**</span><span class="sxs-lookup"><span data-stu-id="fed6d-162">**Font**</span></span>  
 <span data-ttu-id="fed6d-163">Consente di selezionare il tipo di carattere per la visualizzazione in anteprima dei dati.</span><span class="sxs-lookup"><span data-stu-id="fed6d-163">Select the font in which to display the preview data.</span></span>  
  
 <span data-ttu-id="fed6d-164">**Colonne dati di origine**</span><span class="sxs-lookup"><span data-stu-id="fed6d-164">**Source data columns**</span></span>  
 <span data-ttu-id="fed6d-165">Per modificare la larghezza della riga, trascinare l'indicatore di riga rosso verticale. Per modificare la larghezza delle colonne, fare clic sul righello nella parte superiore della finestra di anteprima.</span><span class="sxs-lookup"><span data-stu-id="fed6d-165">Adjust the width of the row by sliding the vertical red row marker, and adjust the width of the columns by clicking the ruler at the top of the preview window</span></span>  
  
 <span data-ttu-id="fed6d-166">**Larghezza riga**</span><span class="sxs-lookup"><span data-stu-id="fed6d-166">**Row width**</span></span>  
 <span data-ttu-id="fed6d-167">Consente di specificare la larghezza della riga prima dell'aggiunta dei delimitatori per le singole colonne.</span><span class="sxs-lookup"><span data-stu-id="fed6d-167">Specify the length of the row before adding delimiters for individual columns.</span></span> <span data-ttu-id="fed6d-168">In alternativa, trascinare la linea rossa verticale nella finestra di anteprima per contrassegnare la fine della riga.</span><span class="sxs-lookup"><span data-stu-id="fed6d-168">Or, drag the vertical red line in the preview window to mark the end of the row.</span></span> <span data-ttu-id="fed6d-169">Il valore relativo alla larghezza della riga viene aggiornato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="fed6d-169">The row width value is automatically updated.</span></span>  
  
 <span data-ttu-id="fed6d-170">**Reimposta colonne**</span><span class="sxs-lookup"><span data-stu-id="fed6d-170">**Reset Columns**</span></span>  
 <span data-ttu-id="fed6d-171">Il pulsante **Reimposta colonne**consente di rimuovere tutte le colonne tranne quelle originali.</span><span class="sxs-lookup"><span data-stu-id="fed6d-171">Remove all but the original columns by clicking **Reset Columns**.</span></span>  
  
### <a name="format--ragged-right"></a><span data-ttu-id="fed6d-172">Formato = Non allineato a destra</span><span class="sxs-lookup"><span data-stu-id="fed6d-172">Format = Ragged Right</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fed6d-173">I file non allineati a destra sono file in cui ogni colonna ha una larghezza fissa, ad eccezione dell'ultima.</span><span class="sxs-lookup"><span data-stu-id="fed6d-173">Ragged right files are files in which every column has a fixed width, except for the last column.</span></span> <span data-ttu-id="fed6d-174">L'ultima colonna è delimitata dal delimitatore di riga.</span><span class="sxs-lookup"><span data-stu-id="fed6d-174">It is delimited by the row delimiter.</span></span>  
  
 <span data-ttu-id="fed6d-175">**Carattere**</span><span class="sxs-lookup"><span data-stu-id="fed6d-175">**Font**</span></span>  
 <span data-ttu-id="fed6d-176">Consente di selezionare il tipo di carattere per la visualizzazione in anteprima dei dati.</span><span class="sxs-lookup"><span data-stu-id="fed6d-176">Select the font in which to display the preview data.</span></span>  
  
 <span data-ttu-id="fed6d-177">**Colonne dati di origine**</span><span class="sxs-lookup"><span data-stu-id="fed6d-177">**Source data columns**</span></span>  
 <span data-ttu-id="fed6d-178">Per modificare la larghezza della riga, trascinare l'indicatore di riga rosso verticale. Per modificare la larghezza delle colonne, fare clic sul righello nella parte superiore della finestra di anteprima.</span><span class="sxs-lookup"><span data-stu-id="fed6d-178">Adjust the width of the row by sliding the vertical red row marker, and adjust the width of the columns by clicking the ruler at the top of the preview window</span></span>  
  
 <span data-ttu-id="fed6d-179">**Delimitatore di riga**</span><span class="sxs-lookup"><span data-stu-id="fed6d-179">**Row delimiter**</span></span>  
 <span data-ttu-id="fed6d-180">Consente di selezionare il delimitatore di riga desiderato nell'elenco dei delimitatori disponibili oppure di immettere il testo per il delimitatore.</span><span class="sxs-lookup"><span data-stu-id="fed6d-180">Select from the list of available row delimiters, or enter the delimiter text.</span></span>  
  
|<span data-ttu-id="fed6d-181">Valore</span><span class="sxs-lookup"><span data-stu-id="fed6d-181">Value</span></span>|<span data-ttu-id="fed6d-182">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fed6d-182">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="fed6d-183">**{CR}{LF}**</span><span class="sxs-lookup"><span data-stu-id="fed6d-183">**{CR}{LF}**</span></span>|<span data-ttu-id="fed6d-184">Le righe sono delimitate dalla combinazione di caratteri ritorno a capo/avanzamento riga.</span><span class="sxs-lookup"><span data-stu-id="fed6d-184">Rows are delimited by a carriage return-line feed combination.</span></span>|  
|<span data-ttu-id="fed6d-185">**{CR}**</span><span class="sxs-lookup"><span data-stu-id="fed6d-185">**{CR}**</span></span>|<span data-ttu-id="fed6d-186">Le righe sono delimitate da un ritorno a capo.</span><span class="sxs-lookup"><span data-stu-id="fed6d-186">Rows are delimited by a carriage return.</span></span>|  
|<span data-ttu-id="fed6d-187">**{LF}**</span><span class="sxs-lookup"><span data-stu-id="fed6d-187">**{LF}**</span></span>|<span data-ttu-id="fed6d-188">Le righe sono delimitate da un avanzamento riga.</span><span class="sxs-lookup"><span data-stu-id="fed6d-188">Rows are delimited by a line feed.</span></span>|  
|<span data-ttu-id="fed6d-189">**Punto e virgola {;}**</span><span class="sxs-lookup"><span data-stu-id="fed6d-189">**Semicolon {;}**</span></span>|<span data-ttu-id="fed6d-190">Le righe sono delimitate da un punto e virgola.</span><span class="sxs-lookup"><span data-stu-id="fed6d-190">Rows are delimited by a semicolon.</span></span>|  
|<span data-ttu-id="fed6d-191">**Due punti {:}**</span><span class="sxs-lookup"><span data-stu-id="fed6d-191">**Colon {:}**</span></span>|<span data-ttu-id="fed6d-192">Le righe sono delimitate da un carattere due punti.</span><span class="sxs-lookup"><span data-stu-id="fed6d-192">Rows are delimited by a colon.</span></span>|  
|<span data-ttu-id="fed6d-193">**Virgola {,}**</span><span class="sxs-lookup"><span data-stu-id="fed6d-193">**Comma {,}**</span></span>|<span data-ttu-id="fed6d-194">Le righe sono delimitate da una virgola.</span><span class="sxs-lookup"><span data-stu-id="fed6d-194">Rows are delimited by a comma.</span></span>|  
|<span data-ttu-id="fed6d-195">**Tabulazione {t}**</span><span class="sxs-lookup"><span data-stu-id="fed6d-195">**Tab {t}**</span></span>|<span data-ttu-id="fed6d-196">Le righe sono delimitate da un carattere di tabulazione.</span><span class="sxs-lookup"><span data-stu-id="fed6d-196">Rows are delimited by a tab.</span></span>|  
|<span data-ttu-id="fed6d-197">**Barra verticale {&#124;}**</span><span class="sxs-lookup"><span data-stu-id="fed6d-197">**Vertical bar {&#124;}**</span></span>|<span data-ttu-id="fed6d-198">Le righe sono delimitate da una barra verticale.</span><span class="sxs-lookup"><span data-stu-id="fed6d-198">Rows are delimited by a vertical bar.</span></span>|  
  
 <span data-ttu-id="fed6d-199">**Reimposta colonne**</span><span class="sxs-lookup"><span data-stu-id="fed6d-199">**Reset Columns**</span></span>  
 <span data-ttu-id="fed6d-200">Il pulsante **Reimposta colonne**consente di rimuovere tutte le colonne tranne quelle originali.</span><span class="sxs-lookup"><span data-stu-id="fed6d-200">Remove all but the original columns by clicking **Reset Columns**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fed6d-201">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fed6d-201">See Also</span></span>  
 <span data-ttu-id="fed6d-202">[Guida di riferimento ai messaggi e agli errori di Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="fed6d-202">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="fed6d-203">[Editor gestione connessione file flat &#40;pagina generale&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="fed6d-203">[Flat File Connection Manager Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="fed6d-204">[Editor gestione connessione file flat &#40;pagina avanzate&#41;](../../2014/integration-services/flat-file-connection-manager-editor-advanced-page.md) </span><span class="sxs-lookup"><span data-stu-id="fed6d-204">[Flat File Connection Manager Editor &#40;Advanced Page&#41;](../../2014/integration-services/flat-file-connection-manager-editor-advanced-page.md) </span></span>  
 [<span data-ttu-id="fed6d-205">Editor gestione connessione file flat &#40;pagina Anteprima&#41;</span><span class="sxs-lookup"><span data-stu-id="fed6d-205">Flat File Connection Manager Editor &#40;Preview Page&#41;</span></span>](../../2014/integration-services/flat-file-connection-manager-editor-preview-page.md)  
  
  
