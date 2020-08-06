---
title: Editor gestione connessione per più file flat (pagina colonne) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.multifile.columns.f1
helpviewer_keywords:
- Multiple Flat Files Connection Manager Editor
ms.assetid: ad0cb668-0df2-4d4e-9a20-d20692a0b67a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5a7f4936f0722754b414076820eda7dcf2dc8dc5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624801"
---
# <a name="multiple-flat-files-connection-manager-editor-columns-page"></a><span data-ttu-id="7817f-102">Editor gestione connessione per più file flat (pagina Colonne)</span><span class="sxs-lookup"><span data-stu-id="7817f-102">Multiple Flat Files Connection Manager Editor (Columns Page)</span></span>
  <span data-ttu-id="7817f-103">Utilizzare il nodo **Colonne** della finestra di dialogo **Editor gestione connessione per più file flat** per specificare informazioni sulla riga e la colonna e visualizzare l'anteprima del primo file selezionato.</span><span class="sxs-lookup"><span data-stu-id="7817f-103">Use the **Columns** node of the **Multiple Flat Files Connection Manager Editor** dialog box to specify the row and column information, and to preview the first selected file.</span></span>  
  
 <span data-ttu-id="7817f-104">Per ulteriori informazioni sulla gestione connessione per più file flat, vedere [Multiple Flat Files Connection Manager](connection-manager/multiple-flat-files-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="7817f-104">To learn more about the Multiple Flat Files connection manager, see [Multiple Flat Files Connection Manager](connection-manager/multiple-flat-files-connection-manager.md).</span></span>  
  
## <a name="static-options"></a><span data-ttu-id="7817f-105">Opzioni statiche</span><span class="sxs-lookup"><span data-stu-id="7817f-105">Static Options</span></span>  
 <span data-ttu-id="7817f-106">**Nome gestione connessione**</span><span class="sxs-lookup"><span data-stu-id="7817f-106">**Connection manager name**</span></span>  
 <span data-ttu-id="7817f-107">Consente di specificare un nome univoco per la connessione per più file flat nel flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="7817f-107">Provide a unique name for the Multiple Flat Files connection in the workflow.</span></span> <span data-ttu-id="7817f-108">Il nome specificato verrà visualizzato in Progettazione [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7817f-108">The name provided will be displayed within [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="7817f-109">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="7817f-109">**Description**</span></span>  
 <span data-ttu-id="7817f-110">Consente di aggiungere una descrizione per la connessione.</span><span class="sxs-lookup"><span data-stu-id="7817f-110">Describe the connection.</span></span> <span data-ttu-id="7817f-111">È consigliabile includere nella descrizione informazioni sugli scopi della connessione, in modo da ottenere pacchetti autodocumentati e semplificarne quindi la gestione.</span><span class="sxs-lookup"><span data-stu-id="7817f-111">As a best practice, describe the connection in terms of its purpose, to make packages self-documenting and easier to maintain.</span></span>  
  
## <a name="flat-file-format-dynamic-options"></a><span data-ttu-id="7817f-112">Opzioni dinamiche relative al formato file flat</span><span class="sxs-lookup"><span data-stu-id="7817f-112">Flat File Format Dynamic Options</span></span>  
  
### <a name="format--delimited"></a><span data-ttu-id="7817f-113">Formato = Delimitato</span><span class="sxs-lookup"><span data-stu-id="7817f-113">Format = Delimited</span></span>  
 <span data-ttu-id="7817f-114">**Delimitatore di riga**</span><span class="sxs-lookup"><span data-stu-id="7817f-114">**Row delimiter**</span></span>  
 <span data-ttu-id="7817f-115">Consente di selezionare il delimitatore di riga desiderato nell'elenco dei delimitatori disponibili oppure di immettere il testo per il delimitatore.</span><span class="sxs-lookup"><span data-stu-id="7817f-115">Select from the list of available row delimiters, or enter the delimiter text.</span></span>  
  
|<span data-ttu-id="7817f-116">Valore</span><span class="sxs-lookup"><span data-stu-id="7817f-116">Value</span></span>|<span data-ttu-id="7817f-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7817f-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="7817f-118">**{CR}{LF}**</span><span class="sxs-lookup"><span data-stu-id="7817f-118">**{CR}{LF}**</span></span>|<span data-ttu-id="7817f-119">Le righe sono delimitate dalla combinazione di caratteri ritorno a capo/avanzamento riga.</span><span class="sxs-lookup"><span data-stu-id="7817f-119">Rows are delimited by a carriage return-line feed combination.</span></span>|  
|<span data-ttu-id="7817f-120">**{CR}**</span><span class="sxs-lookup"><span data-stu-id="7817f-120">**{CR}**</span></span>|<span data-ttu-id="7817f-121">Le righe sono delimitate da un ritorno a capo.</span><span class="sxs-lookup"><span data-stu-id="7817f-121">Rows are delimited by a carriage return.</span></span>|  
|<span data-ttu-id="7817f-122">**{LF}**</span><span class="sxs-lookup"><span data-stu-id="7817f-122">**{LF}**</span></span>|<span data-ttu-id="7817f-123">Le righe sono delimitate da un avanzamento riga.</span><span class="sxs-lookup"><span data-stu-id="7817f-123">Rows are delimited by a line feed.</span></span>|  
|<span data-ttu-id="7817f-124">**Punto e virgola {;}**</span><span class="sxs-lookup"><span data-stu-id="7817f-124">**Semicolon {;}**</span></span>|<span data-ttu-id="7817f-125">Le righe sono delimitate da un punto e virgola.</span><span class="sxs-lookup"><span data-stu-id="7817f-125">Rows are delimited by a semicolon.</span></span>|  
|<span data-ttu-id="7817f-126">**Due punti {:}**</span><span class="sxs-lookup"><span data-stu-id="7817f-126">**Colon {:}**</span></span>|<span data-ttu-id="7817f-127">Le righe sono delimitate da un carattere due punti.</span><span class="sxs-lookup"><span data-stu-id="7817f-127">Rows are delimited by a colon.</span></span>|  
|<span data-ttu-id="7817f-128">**Virgola {,}**</span><span class="sxs-lookup"><span data-stu-id="7817f-128">**Comma {,}**</span></span>|<span data-ttu-id="7817f-129">Le righe sono delimitate da una virgola.</span><span class="sxs-lookup"><span data-stu-id="7817f-129">Rows are delimited by a comma.</span></span>|  
|<span data-ttu-id="7817f-130">**Tabulazione {t}**</span><span class="sxs-lookup"><span data-stu-id="7817f-130">**Tab {t}**</span></span>|<span data-ttu-id="7817f-131">Le righe sono delimitate da un carattere di tabulazione.</span><span class="sxs-lookup"><span data-stu-id="7817f-131">Rows are delimited by a tab.</span></span>|  
|<span data-ttu-id="7817f-132">**Barra verticale {&#124;}**</span><span class="sxs-lookup"><span data-stu-id="7817f-132">**Vertical bar {&#124;}**</span></span>|<span data-ttu-id="7817f-133">Le righe sono delimitate da una barra verticale.</span><span class="sxs-lookup"><span data-stu-id="7817f-133">Rows are delimited by a vertical bar.</span></span>|  
  
 <span data-ttu-id="7817f-134">**Delimitatore di colonna**</span><span class="sxs-lookup"><span data-stu-id="7817f-134">**Column delimiter**</span></span>  
 <span data-ttu-id="7817f-135">Consente di selezionare il delimitatore di colonna desiderato nell'elenco dei delimitatori disponibili oppure di immettere il testo per il delimitatore.</span><span class="sxs-lookup"><span data-stu-id="7817f-135">Select from the list of available column delimiters, or enter the delimiter text.</span></span>  
  
|<span data-ttu-id="7817f-136">Valore</span><span class="sxs-lookup"><span data-stu-id="7817f-136">Value</span></span>|<span data-ttu-id="7817f-137">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7817f-137">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="7817f-138">**{CR}{LF}**</span><span class="sxs-lookup"><span data-stu-id="7817f-138">**{CR}{LF}**</span></span>|<span data-ttu-id="7817f-139">Le colonne sono delimitate dalla combinazione di caratteri ritorno a capo/avanzamento riga.</span><span class="sxs-lookup"><span data-stu-id="7817f-139">Columns are delimited by a carriage return-line feed combination.</span></span>|  
|<span data-ttu-id="7817f-140">**{CR}**</span><span class="sxs-lookup"><span data-stu-id="7817f-140">**{CR}**</span></span>|<span data-ttu-id="7817f-141">Le colonne sono delimitate da un ritorno a capo.</span><span class="sxs-lookup"><span data-stu-id="7817f-141">Columns are delimited by a carriage return.</span></span>|  
|<span data-ttu-id="7817f-142">**{LF}**</span><span class="sxs-lookup"><span data-stu-id="7817f-142">**{LF}**</span></span>|<span data-ttu-id="7817f-143">Le colonne sono delimitate da un avanzamento riga.</span><span class="sxs-lookup"><span data-stu-id="7817f-143">Columns are delimited by a line feed.</span></span>|  
|<span data-ttu-id="7817f-144">**Punto e virgola {;}**</span><span class="sxs-lookup"><span data-stu-id="7817f-144">**Semicolon {;}**</span></span>|<span data-ttu-id="7817f-145">Le colonne sono delimitate da un punto e virgola.</span><span class="sxs-lookup"><span data-stu-id="7817f-145">Columns are delimited by a semicolon.</span></span>|  
|<span data-ttu-id="7817f-146">**Due punti {:}**</span><span class="sxs-lookup"><span data-stu-id="7817f-146">**Colon {:}**</span></span>|<span data-ttu-id="7817f-147">Le colonne sono delimitate da due punti.</span><span class="sxs-lookup"><span data-stu-id="7817f-147">Columns are delimited by a colon.</span></span>|  
|<span data-ttu-id="7817f-148">**Virgola {,}**</span><span class="sxs-lookup"><span data-stu-id="7817f-148">**Comma {,}**</span></span>|<span data-ttu-id="7817f-149">Le colonne sono delimitate da una virgola.</span><span class="sxs-lookup"><span data-stu-id="7817f-149">Columns are delimited by a comma.</span></span>|  
|<span data-ttu-id="7817f-150">**Tabulazione {t}**</span><span class="sxs-lookup"><span data-stu-id="7817f-150">**Tab {t}**</span></span>|<span data-ttu-id="7817f-151">Le colonne sono delimitate da una tabulazione.</span><span class="sxs-lookup"><span data-stu-id="7817f-151">Columns are delimited by a tab.</span></span>|  
|<span data-ttu-id="7817f-152">**Barra verticale {&#124;}**</span><span class="sxs-lookup"><span data-stu-id="7817f-152">**Vertical bar {&#124;}**</span></span>|<span data-ttu-id="7817f-153">Le colonne sono delimitate da una barra verticale.</span><span class="sxs-lookup"><span data-stu-id="7817f-153">Columns are delimited by a vertical bar.</span></span>|  
  
 <span data-ttu-id="7817f-154">**Reimposta colonne**</span><span class="sxs-lookup"><span data-stu-id="7817f-154">**Reset Columns**</span></span>  
 <span data-ttu-id="7817f-155">Il pulsante **Reimposta colonne**consente di rimuovere tutte le colonne tranne quelle originali.</span><span class="sxs-lookup"><span data-stu-id="7817f-155">Remove all but the original columns by clicking **Reset Columns**.</span></span>  
  
### <a name="format--fixed-width"></a><span data-ttu-id="7817f-156">Formato = A larghezza fissa</span><span class="sxs-lookup"><span data-stu-id="7817f-156">Format = Fixed Width</span></span>  
 <span data-ttu-id="7817f-157">**Carattere**</span><span class="sxs-lookup"><span data-stu-id="7817f-157">**Font**</span></span>  
 <span data-ttu-id="7817f-158">Consente di selezionare il tipo di carattere per la visualizzazione in anteprima dei dati.</span><span class="sxs-lookup"><span data-stu-id="7817f-158">Select the font in which to display the preview data.</span></span>  
  
 <span data-ttu-id="7817f-159">**Colonne dati di origine**</span><span class="sxs-lookup"><span data-stu-id="7817f-159">**Source data columns**</span></span>  
 <span data-ttu-id="7817f-160">Per modificare la larghezza della riga, trascinare l'indicatore di riga verticale, mentre per modificare la larghezza delle colonne, fare clic sul righello nella parte superiore della finestra di anteprima.</span><span class="sxs-lookup"><span data-stu-id="7817f-160">Adjust the width of the row by sliding the vertical row marker, and adjust the width of the columns by clicking the ruler at the top of the preview window</span></span>  
  
 <span data-ttu-id="7817f-161">**Larghezza riga**</span><span class="sxs-lookup"><span data-stu-id="7817f-161">**Row width**</span></span>  
 <span data-ttu-id="7817f-162">Consente di specificare la larghezza della riga prima dell'aggiunta dei delimitatori per le singole colonne.</span><span class="sxs-lookup"><span data-stu-id="7817f-162">Specify the length of the row before adding delimiters for individual columns.</span></span> <span data-ttu-id="7817f-163">In alternativa, trascinare la linea verticale nella finestra di anteprima per contrassegnare la fine della riga.</span><span class="sxs-lookup"><span data-stu-id="7817f-163">Or, drag the vertical line in the preview window to mark the end of the row.</span></span> <span data-ttu-id="7817f-164">Il valore relativo alla larghezza della riga viene aggiornato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="7817f-164">The row width value is automatically updated.</span></span>  
  
 <span data-ttu-id="7817f-165">**Reimposta colonne**</span><span class="sxs-lookup"><span data-stu-id="7817f-165">**Reset Columns**</span></span>  
 <span data-ttu-id="7817f-166">Il pulsante **Reimposta colonne**consente di rimuovere tutte le colonne tranne quelle originali.</span><span class="sxs-lookup"><span data-stu-id="7817f-166">Remove all but the original columns by clicking **Reset Columns**.</span></span>  
  
### <a name="format--ragged-right"></a><span data-ttu-id="7817f-167">Formato = Non allineato a destra</span><span class="sxs-lookup"><span data-stu-id="7817f-167">Format = Ragged Right</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7817f-168">Nei file con formato non allineato a destra, ogni colonna ha una larghezza fissa, ad eccezione dell'ultima colonna.</span><span class="sxs-lookup"><span data-stu-id="7817f-168">Ragged right files are those in which every column has a fixed width, except for the last column.</span></span> <span data-ttu-id="7817f-169">L'ultima colonna è delimitata dal delimitatore di riga.</span><span class="sxs-lookup"><span data-stu-id="7817f-169">It is delimited by the row delimiter.</span></span>  
  
 <span data-ttu-id="7817f-170">**Carattere**</span><span class="sxs-lookup"><span data-stu-id="7817f-170">**Font**</span></span>  
 <span data-ttu-id="7817f-171">Consente di selezionare il tipo di carattere per la visualizzazione in anteprima dei dati.</span><span class="sxs-lookup"><span data-stu-id="7817f-171">Select the font in which to display the preview data.</span></span>  
  
 <span data-ttu-id="7817f-172">**Colonne dati di origine**</span><span class="sxs-lookup"><span data-stu-id="7817f-172">**Source data columns**</span></span>  
 <span data-ttu-id="7817f-173">Per modificare la larghezza della riga, trascinare l'indicatore di riga verticale, mentre per modificare la larghezza delle colonne, fare clic sul righello nella parte superiore della finestra di anteprima.</span><span class="sxs-lookup"><span data-stu-id="7817f-173">Adjust the width of the row by sliding the vertical row marker, and adjust the width of the columns by clicking the ruler at the top of the preview window</span></span>  
  
 <span data-ttu-id="7817f-174">**Delimitatore di riga**</span><span class="sxs-lookup"><span data-stu-id="7817f-174">**Row delimiter**</span></span>  
 <span data-ttu-id="7817f-175">Consente di selezionare il delimitatore di riga desiderato nell'elenco dei delimitatori disponibili oppure di immettere il testo per il delimitatore.</span><span class="sxs-lookup"><span data-stu-id="7817f-175">Select from the list of available row delimiters, or enter the delimiter text.</span></span>  
  
|<span data-ttu-id="7817f-176">Valore</span><span class="sxs-lookup"><span data-stu-id="7817f-176">Value</span></span>|<span data-ttu-id="7817f-177">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7817f-177">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="7817f-178">**{CR}{LF}**</span><span class="sxs-lookup"><span data-stu-id="7817f-178">**{CR}{LF}**</span></span>|<span data-ttu-id="7817f-179">Le righe sono delimitate dalla combinazione di caratteri ritorno a capo/avanzamento riga.</span><span class="sxs-lookup"><span data-stu-id="7817f-179">Rows are delimited by a carriage return-line feed combination.</span></span>|  
|<span data-ttu-id="7817f-180">**{CR}**</span><span class="sxs-lookup"><span data-stu-id="7817f-180">**{CR}**</span></span>|<span data-ttu-id="7817f-181">Le righe sono delimitate da un ritorno a capo.</span><span class="sxs-lookup"><span data-stu-id="7817f-181">Rows are delimited by a carriage return.</span></span>|  
|<span data-ttu-id="7817f-182">**{LF}**</span><span class="sxs-lookup"><span data-stu-id="7817f-182">**{LF}**</span></span>|<span data-ttu-id="7817f-183">Le righe sono delimitate da un avanzamento riga.</span><span class="sxs-lookup"><span data-stu-id="7817f-183">Rows are delimited by a line feed.</span></span>|  
|<span data-ttu-id="7817f-184">**Punto e virgola {;}**</span><span class="sxs-lookup"><span data-stu-id="7817f-184">**Semicolon {;}**</span></span>|<span data-ttu-id="7817f-185">Le righe sono delimitate da un punto e virgola.</span><span class="sxs-lookup"><span data-stu-id="7817f-185">Rows are delimited by a semicolon.</span></span>|  
|<span data-ttu-id="7817f-186">**Due punti {:}**</span><span class="sxs-lookup"><span data-stu-id="7817f-186">**Colon {:}**</span></span>|<span data-ttu-id="7817f-187">Le righe sono delimitate da un carattere due punti.</span><span class="sxs-lookup"><span data-stu-id="7817f-187">Rows are delimited by a colon.</span></span>|  
|<span data-ttu-id="7817f-188">**Virgola {,}**</span><span class="sxs-lookup"><span data-stu-id="7817f-188">**Comma {,}**</span></span>|<span data-ttu-id="7817f-189">Le righe sono delimitate da una virgola.</span><span class="sxs-lookup"><span data-stu-id="7817f-189">Rows are delimited by a comma.</span></span>|  
|<span data-ttu-id="7817f-190">**Tabulazione {t}**</span><span class="sxs-lookup"><span data-stu-id="7817f-190">**Tab {t}**</span></span>|<span data-ttu-id="7817f-191">Le righe sono delimitate da un carattere di tabulazione.</span><span class="sxs-lookup"><span data-stu-id="7817f-191">Rows are delimited by a tab.</span></span>|  
|<span data-ttu-id="7817f-192">**Barra verticale {&#124;}**</span><span class="sxs-lookup"><span data-stu-id="7817f-192">**Vertical bar {&#124;}**</span></span>|<span data-ttu-id="7817f-193">Le righe sono delimitate da una barra verticale.</span><span class="sxs-lookup"><span data-stu-id="7817f-193">Rows are delimited by a vertical bar.</span></span>|  
  
 <span data-ttu-id="7817f-194">**Reimposta colonne**</span><span class="sxs-lookup"><span data-stu-id="7817f-194">**Reset Columns**</span></span>  
 <span data-ttu-id="7817f-195">Il pulsante **Reimposta colonne**consente di rimuovere tutte le colonne tranne quelle originali.</span><span class="sxs-lookup"><span data-stu-id="7817f-195">Remove all but the original columns by clicking **Reset Columns**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7817f-196">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7817f-196">See Also</span></span>  
 <span data-ttu-id="7817f-197">[Guida di riferimento ai messaggi e agli errori di Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="7817f-197">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="7817f-198">[Editor gestione connessione per più file flat &#40;pagina generale&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="7817f-198">[Multiple Flat Files Connection Manager Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="7817f-199">[Editor gestione connessione per più file flat &#40;pagina avanzate&#41;](../../2014/integration-services/multiple-flat-files-connection-manager-editor-advanced-page.md) </span><span class="sxs-lookup"><span data-stu-id="7817f-199">[Multiple Flat Files Connection Manager Editor &#40;Advanced Page&#41;](../../2014/integration-services/multiple-flat-files-connection-manager-editor-advanced-page.md) </span></span>  
 [<span data-ttu-id="7817f-200">Editor gestione connessione per più file flat &#40;pagina Anteprima&#41;</span><span class="sxs-lookup"><span data-stu-id="7817f-200">Multiple Flat Files Connection Manager Editor &#40;Preview Page&#41;</span></span>](../../2014/integration-services/multiple-flat-files-connection-manager-editor-preview-page.md)  
  
  
