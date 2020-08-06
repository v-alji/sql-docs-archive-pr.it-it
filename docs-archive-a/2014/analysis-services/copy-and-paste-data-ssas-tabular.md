---
title: Copiare e incollare dati (SSAS tabulare) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.pastepreviewdb.f1
ms.assetid: 2f8d8b3d-810b-4c31-98f2-341015e13da8
author: minewiskan
ms.author: owend
ms.openlocfilehash: 30df733377f3cb6f7583d380fbb8e92a0ea69e88
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625701"
---
# <a name="copy-and-paste-data-ssas-tabular"></a><span data-ttu-id="83337-102">Copiare e incollare dati (SSAS tabulare)</span><span class="sxs-lookup"><span data-stu-id="83337-102">Copy and Paste Data (SSAS Tabular)</span></span>
  <span data-ttu-id="83337-103">È possibile copiare i dati delle tabelle da applicazioni esterne e incollarli in una tabella nuova o esistente in Progettazione modelli.</span><span class="sxs-lookup"><span data-stu-id="83337-103">You can copy table data from external applications and paste it into a new or existing table in the model designer.</span></span> <span data-ttu-id="83337-104">I dati incollati dagli Appunti devono essere in formato HTML, come i dati copiati da Excel o Word.</span><span class="sxs-lookup"><span data-stu-id="83337-104">The data that you paste from the Clipboard must be in HTML format, for example, data that is copied from Excel or Word.</span></span> <span data-ttu-id="83337-105">Progettazione modelli rileverà e applicherà automaticamente i tipi di dati ai dati incollati.</span><span class="sxs-lookup"><span data-stu-id="83337-105">The model designer will automatically detect and apply data types to the pasted data.</span></span> <span data-ttu-id="83337-106">È anche possibile modificare manualmente il tipo di dati o la formattazione di visualizzazione di una colonna.</span><span class="sxs-lookup"><span data-stu-id="83337-106">You can also manually modify the data type or display formatting of a column.</span></span>  
  
 <span data-ttu-id="83337-107">A differenza delle tabelle con una connessione all'origine dati, nelle tabelle incollate non è disponibile una proprietà Nome connessione oppure Origine dati.</span><span class="sxs-lookup"><span data-stu-id="83337-107">Unlike tables with a data source connection, pasted tables do not have a Connection Name or Source Data property.</span></span> <span data-ttu-id="83337-108">I dati incollati sono persistenti nel file Model.bim.</span><span class="sxs-lookup"><span data-stu-id="83337-108">Pasted data is persisted in the Model.bim file.</span></span> <span data-ttu-id="83337-109">Quando il progetto o il file Model.bim viene salvato, anche i dati incollati vengono salvati.</span><span class="sxs-lookup"><span data-stu-id="83337-109">When the project or Model.bim file is saved, the pasted data is also saved.</span></span>  
  
 <span data-ttu-id="83337-110">Quando viene distribuito un modello, anche i dati incollati saranno distribuiti, indipendentemente dal fatto che il modello venga elaborato con la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="83337-110">When a model is deployed, pasted data will also be deployed with it regardless if the model is processed with the deployment.</span></span>  
  
 <span data-ttu-id="83337-111">Sezioni dell'argomento:</span><span class="sxs-lookup"><span data-stu-id="83337-111">Sections in this topic:</span></span>  
  
-   [<span data-ttu-id="83337-112">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="83337-112">Prerequisites</span></span>](#bkmk_prerequisites)  
  
-   [<span data-ttu-id="83337-113">Incollare i dati</span><span class="sxs-lookup"><span data-stu-id="83337-113">Paste Data</span></span>](#bkmk_paste_data)  
  
-   [<span data-ttu-id="83337-114">Finestra di dialogo Anteprima Incolla</span><span class="sxs-lookup"><span data-stu-id="83337-114">Paste Preview Dialog Box</span></span>](#bkmk_paste_preview)  
  
##  <a name="prerequisites"></a><a name="bkmk_prerequisites"></a> <span data-ttu-id="83337-115">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="83337-115">Prerequisites</span></span>  
 <span data-ttu-id="83337-116">Quando si incollano dati si applicano alcune restrizioni:</span><span class="sxs-lookup"><span data-stu-id="83337-116">There are some restrictions when pasting data:</span></span>  
  
-   <span data-ttu-id="83337-117">Nelle tabelle incollate non possono essere presenti più di 10.000 righe.</span><span class="sxs-lookup"><span data-stu-id="83337-117">Pasted tables cannot have more than 10,000 rows.</span></span>  
  
-   <span data-ttu-id="83337-118">Non è possibile partizionare le tabelle incollate.</span><span class="sxs-lookup"><span data-stu-id="83337-118">Pasted tables cannot be partitioned.</span></span>  
  
-   <span data-ttu-id="83337-119">Le tabelle incollate non sono supportate nella modalità DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="83337-119">Pasted tables are not supported in DirectQuery mode.</span></span>  
  
-   <span data-ttu-id="83337-120">Le opzioni **Accoda il contenuto degli Appunti** e **Incolla e sostituisci** sono disponibili solo quando si usa una tabella inizialmente creata incollando i dati dagli Appunti.</span><span class="sxs-lookup"><span data-stu-id="83337-120">The **Paste Append** and **Paste Replace** options are only available when working with a table that was initially created by pasting data from the Clipboard.</span></span> <span data-ttu-id="83337-121">Non è possibile usare **Accoda il contenuto degli Appunti** o **Incolla e sostituisci** per aggiungere dati in una tabella di dati importati da un altro tipo di origine dati.</span><span class="sxs-lookup"><span data-stu-id="83337-121">You cannot use **Paste Append** or **Paste Replace** to add data into a table of imported data from another type of data source.</span></span>  
  
-   <span data-ttu-id="83337-122">Quando si usa l'opzione **Accoda il contenuto degli Appunti** o **Incolla e sostituisci**, nei nuovi dati deve essere contenuto esattamente lo stesso numero di colonne dei dati originali.</span><span class="sxs-lookup"><span data-stu-id="83337-122">When you use **Paste Append** or **Paste Replace**, the new data must contain exactly the same number of columns as the original data.</span></span> <span data-ttu-id="83337-123">Preferibilmente, i dati delle colonne che si incollano o si accodano devono essere dello stesso tipo o compatibili con quelli della tabella di destinazione.</span><span class="sxs-lookup"><span data-stu-id="83337-123">Preferably, the columns of data that you paste or append should also be of the same or compatible data type as those in the destination table.</span></span> <span data-ttu-id="83337-124">In alcuni casi è possibile usare un tipo di dati diverso, tuttavia potrebbe venire visualizzato un errore di **tipo non corrispondente** .</span><span class="sxs-lookup"><span data-stu-id="83337-124">In some cases you can use a different data type, but a **Type mismatch** error may be displayed.</span></span>  
  
##  <a name="paste-data"></a><a name="bkmk_paste_data"></a> <span data-ttu-id="83337-125">Incollare i dati</span><span class="sxs-lookup"><span data-stu-id="83337-125">Paste Data</span></span>  
  
#### <a name="to-paste-data-into-the-designer"></a><span data-ttu-id="83337-126">Per incollare dati nella finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="83337-126">To paste data into the designer</span></span>  
  
-   <span data-ttu-id="83337-127">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]fare clic sul menu **Modifica** e quindi scegliere una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="83337-127">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], click the **Edit** menu, and then clicke of the following:</span></span>  
  
    -   <span data-ttu-id="83337-128">Fare clic su **Incolla** per incollare il contenuto degli Appunti in una nuova tabella.</span><span class="sxs-lookup"><span data-stu-id="83337-128">Click **Paste** to paste the contents of the Clipboard into a new table.</span></span>  
  
    -   <span data-ttu-id="83337-129">Fare clic su **Accoda il contenuto degli Appunti** per incollare il contenuto degli Appunti come righe aggiuntive nella tabella selezionata.</span><span class="sxs-lookup"><span data-stu-id="83337-129">Click **Paste Append** to paste the contents of the Clipboard as additional rows into the selected table.</span></span> <span data-ttu-id="83337-130">Le nuove righe verranno aggiunte alla fine della tabella.</span><span class="sxs-lookup"><span data-stu-id="83337-130">The new rows will be added to the end of the table.</span></span>  
  
    -   <span data-ttu-id="83337-131">Fare clic su **Incolla e sostituisci** per sostituire la tabella selezionata con il contenuto degli Appunti.</span><span class="sxs-lookup"><span data-stu-id="83337-131">Click **Paste Replace** to replace the selected table with the contents of the Clipboard.</span></span> <span data-ttu-id="83337-132">Tutti i nomi delle intestazioni di colonna esistenti rimarranno nella tabella e le relazioni vengono mantenute.</span><span class="sxs-lookup"><span data-stu-id="83337-132">All existing column header names will remain in the table, and relationships are preserved.</span></span>  
  
##  <a name="paste-preview-dialog-box"></a><a name="bkmk_paste_preview"></a><span data-ttu-id="83337-133">Finestra di dialogo Anteprima Incolla</span><span class="sxs-lookup"><span data-stu-id="83337-133">Paste Preview Dialog Box</span></span>  
 <span data-ttu-id="83337-134">La finestra di dialogo **Anteprima Incolla** consente di visualizzare un'anteprima dei dati copiati nella finestra di progettazione e di assicurarsi che la copia dei dati sia eseguita correttamente.</span><span class="sxs-lookup"><span data-stu-id="83337-134">The **Paste Preview** dialog box enables you to see a preview of data that is copied into the designer window and to ensure that the data is copied correctly.</span></span> <span data-ttu-id="83337-135">Per accedere a questa finestra di dialogo, copiare negli Appunti i dati basati su tabelle in formato HTML, quindi nella finestra di progettazione fare clic sul menu **Modifica** e scegliere **Incolla**, **Accoda il contenuto degli Appunti**o **Incolla e sostituisci**.</span><span class="sxs-lookup"><span data-stu-id="83337-135">To access this dialog box, copy table-based data in the HTML format to the clipboard, and then in the designer, click on the **Edit** menu, and then click **Paste**, **Paste Append**, or **Paste Replace**.</span></span> <span data-ttu-id="83337-136">Le opzioni **Accoda il contenuto degli Appunti** e **Incolla e sostituisci** sono disponibili solo quando si aggiungono o si sostituiscono dati in una tabella creata tramite un'operazione di copia e incolla dagli Appunti.</span><span class="sxs-lookup"><span data-stu-id="83337-136">The **Paste Append** and **Paste Replace** options are only available when you add or replace data in a table that was created by copying and pasting from the Clipboard.</span></span> <span data-ttu-id="83337-137">Non è possibile usare **Accoda il contenuto degli Appunti** o **Incolla e sostituisci** per aggiungere dati in una tabella con dati importati.</span><span class="sxs-lookup"><span data-stu-id="83337-137">You cannot use **Paste Append** or **Paste Replace** to add data into a table of imported data.</span></span>  
  
 <span data-ttu-id="83337-138">Le opzioni per questa finestra di dialogo variano a seconda che i dati vengano incollati in una tabella completamente nuova o in una tabella esistente e quindi si sostituiscano i dati esistenti con i nuovi dati o che si aggiungano dati a una tabella esistente.</span><span class="sxs-lookup"><span data-stu-id="83337-138">The options for this dialog box are different depending on whether you paste data into a completely new table, paste data into an existing table and then replace the existing data with the new data, or whether you append data to an existing table.</span></span>  
  
### <a name="paste-to-new-table"></a><span data-ttu-id="83337-139">Incolla in nuova tabella</span><span class="sxs-lookup"><span data-stu-id="83337-139">Paste to New Table</span></span>  
 <span data-ttu-id="83337-140">**Nome tabella**</span><span class="sxs-lookup"><span data-stu-id="83337-140">**Table name**</span></span>  
 <span data-ttu-id="83337-141">Specificare il nome della tabella che verrà creata nella finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="83337-141">Specify the name of the table that will be created in the designer.</span></span>  
  
 <span data-ttu-id="83337-142">**Dati da incollare**</span><span class="sxs-lookup"><span data-stu-id="83337-142">**Data to be pasted**</span></span>  
 <span data-ttu-id="83337-143">Consente di visualizzare un esempio del contenuto degli Appunti che verrà aggiunto alla tabella di destinazione.</span><span class="sxs-lookup"><span data-stu-id="83337-143">Shows a sample of the Clipboard contents that will be added to the destination table.</span></span>  
  
### <a name="paste-append"></a><span data-ttu-id="83337-144">Accoda il contenuto degli Appunti</span><span class="sxs-lookup"><span data-stu-id="83337-144">Paste Append</span></span>  
 <span data-ttu-id="83337-145">**Dati esistenti nella tabella**</span><span class="sxs-lookup"><span data-stu-id="83337-145">**Existing data in the table**</span></span>  
 <span data-ttu-id="83337-146">Consente di visualizzare un esempio di dati esistenti nella tabella in modo da verificare le colonne, i tipi di dati ecc.</span><span class="sxs-lookup"><span data-stu-id="83337-146">Shows a sample of the existing data in the table so that you can verify the columns, data types, etc.</span></span>  
  
 <span data-ttu-id="83337-147">**Dati da incollare**</span><span class="sxs-lookup"><span data-stu-id="83337-147">**Data to be pasted**</span></span>  
 <span data-ttu-id="83337-148">Consente di visualizzare un esempio del contenuto degli Appunti.</span><span class="sxs-lookup"><span data-stu-id="83337-148">Shows a sample of the Clipboard contents.</span></span> <span data-ttu-id="83337-149">I dati esistenti saranno accodati da questi dati.</span><span class="sxs-lookup"><span data-stu-id="83337-149">The existing data will be appended by this data.</span></span>  
  
### <a name="paste-replace"></a><span data-ttu-id="83337-150">Incolla e sostituisci</span><span class="sxs-lookup"><span data-stu-id="83337-150">Paste Replace</span></span>  
 <span data-ttu-id="83337-151">**Dati esistenti nella tabella**</span><span class="sxs-lookup"><span data-stu-id="83337-151">**Existing data in the table**</span></span>  
 <span data-ttu-id="83337-152">Consente di visualizzare un esempio di dati esistenti nella tabella in modo da verificare le colonne, i tipi di dati ecc.</span><span class="sxs-lookup"><span data-stu-id="83337-152">Shows a sample of the existing data in the table so that you can verify the columns, data types, etc.</span></span>  
  
 <span data-ttu-id="83337-153">**Dati da incollare**</span><span class="sxs-lookup"><span data-stu-id="83337-153">**Data to be pasted**</span></span>  
 <span data-ttu-id="83337-154">Consente di visualizzare un esempio del contenuto degli Appunti.</span><span class="sxs-lookup"><span data-stu-id="83337-154">Shows a sample of the Clipboard contents.</span></span> <span data-ttu-id="83337-155">I dati esistenti nella tabella di destinazione saranno eliminati e le nuove righe saranno inserite nella tabella.</span><span class="sxs-lookup"><span data-stu-id="83337-155">The existing data in the destination table will be deleted and the new rows will be inserted into the table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83337-156">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="83337-156">See Also</span></span>  
 <span data-ttu-id="83337-157">[Importare dati &#40;SSAS tabulare&#41;](import-data-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="83337-157">[Import Data &#40;SSAS Tabular&#41;](import-data-ssas-tabular.md) </span></span>  
 <span data-ttu-id="83337-158">[Origini dati supportate &#40;SSAS tabulare&#41;](tabular-models/data-sources-supported-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="83337-158">[Data Sources Supported &#40;SSAS Tabular&#41;](tabular-models/data-sources-supported-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="83337-159">Impostare il tipo di dati di una colonna &#40;SSAS tabulare&#41;</span><span class="sxs-lookup"><span data-stu-id="83337-159">Set the Data Type of a Column &#40;SSAS Tabular&#41;</span></span>](tabular-models/set-the-data-type-of-a-column-ssas-tabular.md)  
  
  
