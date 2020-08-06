---
title: Destinazione file non elaborato | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.rawfiledest.f1
helpviewer_keywords:
- append options [Integration Services]
- destinations [Integration Services], Raw File
- raw data [Integration Services]
- writing raw data
- Raw File destination
ms.assetid: d311b458-aefc-4b4d-b1a1-4c0ebbb34214
author: chugugrace
ms.author: chugu
ms.openlocfilehash: fc5ce99be6e467ba323137ef885cbb13bfb328ce
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626169"
---
# <a name="raw-file-destination"></a><span data-ttu-id="7245b-102">file non elaborato - destinazione</span><span class="sxs-lookup"><span data-stu-id="7245b-102">Raw File Destination</span></span>
  <span data-ttu-id="7245b-103">La destinazione file non elaborato scrive dati non elaborati in un file.</span><span class="sxs-lookup"><span data-stu-id="7245b-103">The Raw File destination writes raw data to a file.</span></span> <span data-ttu-id="7245b-104">Poiché il formato dei dati è nativo della destinazione, non è necessaria alcuna conversione e quasi nessuna analisi dei dati.</span><span class="sxs-lookup"><span data-stu-id="7245b-104">Because the format of the data is native to the destination, the data requires no translation and little parsing.</span></span> <span data-ttu-id="7245b-105">Questo significa che la destinazione file non elaborato è in grado di scrivere i dati più rapidamente rispetto ad altre destinazioni, quali le destinazioni file flat e OLE DB.</span><span class="sxs-lookup"><span data-stu-id="7245b-105">This means that the Raw File destination can write data more quickly than other destinations such as the Flat File and the OLE DB destinations.</span></span>  
  
 <span data-ttu-id="7245b-106">Oltre alla scrittura di dati non elaborati in un file, la destinazione file non elaborato può essere utilizzata anche per generare un file non elaborato vuoto contenente solo le colonne (file di soli metadati), senza dover eseguire il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="7245b-106">In addition to writing raw data to a file, you can also use the Raw File destination to generate an empty raw file that contains only the columns (metadata-only file), without having to run the package.</span></span> <span data-ttu-id="7245b-107">Si utilizza l'origine file non elaborato per recuperare dati non elaborati scritti in precedenza dalla destinazione.</span><span class="sxs-lookup"><span data-stu-id="7245b-107">You use the Raw File source to retrieve raw data that was previously written by the destination.</span></span> <span data-ttu-id="7245b-108">È anche possibile puntare l'origine file non elaborato al file di soli metadati.</span><span class="sxs-lookup"><span data-stu-id="7245b-108">You can also point the Raw File source to the metadata-only file.</span></span>  
  
 <span data-ttu-id="7245b-109">Nel formato di file non elaborato sono contenute informazioni di ordinamento.</span><span class="sxs-lookup"><span data-stu-id="7245b-109">The raw file format contains sort information.</span></span> <span data-ttu-id="7245b-110">Con la destinazione file non elaborato è possibile salvare tutte le informazioni di ordinamento in cui sono inclusi i flag di confronto per le colonne stringa.</span><span class="sxs-lookup"><span data-stu-id="7245b-110">The Raw File Destination saves all the sort information including the comparison flags for string columns.</span></span> <span data-ttu-id="7245b-111">Con l'origine file non elaborato è possibile leggere e riconoscere le informazioni di ordinamento.</span><span class="sxs-lookup"><span data-stu-id="7245b-111">The Raw File source reads and honors the sort information.</span></span> <span data-ttu-id="7245b-112">È possibile configurare l'origine file non elaborato in modo da ignorare i flag di ordinamento nel file utilizzando l'editor avanzato.</span><span class="sxs-lookup"><span data-stu-id="7245b-112">You do have the option of configuring the Raw File Source to ignore the sort flags in the file, using the Advanced Editor.</span></span> <span data-ttu-id="7245b-113">Per altre informazioni sui flag di confronto, vedere [Confronto di dati stringa](comparing-string-data.md).</span><span class="sxs-lookup"><span data-stu-id="7245b-113">For more information about comparison flags, see [Comparing String Data](comparing-string-data.md).</span></span>  
  
 <span data-ttu-id="7245b-114">Per configurare la destinazione file non elaborato, procedere nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="7245b-114">You can configure the Raw File destination in the following ways:</span></span>  
  
-   <span data-ttu-id="7245b-115">Specificare una modalità di accesso, ovvero il nome del file o una variabile contenente il nome del file in cui la destinazione file non elaborato dovrà scrivere.</span><span class="sxs-lookup"><span data-stu-id="7245b-115">Specify an access mode which is either the name of the file or a variable that contains the name of the file to which the Raw File destination writes.</span></span>  
  
-   <span data-ttu-id="7245b-116">Indicare se la destinazione file non elaborato deve creare un nuovo file o accodare i dati a un file esistente con lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="7245b-116">Indicate whether the Raw File destination appends data to an existing file that has the same name or creates a new file.</span></span>  
  
 <span data-ttu-id="7245b-117">La destinazione file non elaborato viene frequentemente utilizzata per scrivere risultati intermedi di dati parzialmente elaborati durante l'esecuzione dei pacchetti.</span><span class="sxs-lookup"><span data-stu-id="7245b-117">The Raw File destination is frequently used to write intermediary results of partly processed data between package executions.</span></span> <span data-ttu-id="7245b-118">Se si archiviano i dati non elaborati, sarà possibile rileggerli rapidamente tramite un'origine file non elaborato e quindi trasformarli ulteriormente prima di caricarli nella destinazione finale.</span><span class="sxs-lookup"><span data-stu-id="7245b-118">Storing raw data means that the data can be read quickly by a Raw File source and then further transformed before it is loaded into its final destination.</span></span> <span data-ttu-id="7245b-119">È ad esempio possibile eseguire più volte un pacchetto che a ogni esecuzione scrive dati non elaborati in uno o più file</span><span class="sxs-lookup"><span data-stu-id="7245b-119">For example, a package might run several times, and each time write raw data to files.</span></span> <span data-ttu-id="7245b-120">e successivamente eseguire un altro pacchetto che utilizza l'origine file non elaborato per leggere i dati da ogni file, utilizza una trasformazione Unione input multipli per unire i dati in un unico set di dati, quindi applica ulteriori trasformazioni che riepilogano i dati prima di caricarli nella destinazione finale, ad esempio una tabella di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7245b-120">Later, a different package can use the Raw File source to read from each file, use a Union All transformation to merge the data into one data set, and then apply additional transformations that summarize the data before loading the data into its final destination such as a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7245b-121">La destinazione file non elaborato supporta dati Null ma non dati BLOB (Binary Large Object).</span><span class="sxs-lookup"><span data-stu-id="7245b-121">The Raw File destination supports null data but not binary large object (BLOB) data.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7245b-122">La destinazione file non elaborato non utilizza alcuna gestione connessione.</span><span class="sxs-lookup"><span data-stu-id="7245b-122">The Raw File destination does not use a connection manager.</span></span>  
  
 <span data-ttu-id="7245b-123">Questa origine include un solo input regolare.</span><span class="sxs-lookup"><span data-stu-id="7245b-123">This source has one regular input.</span></span> <span data-ttu-id="7245b-124">Non supporta un output degli errori.</span><span class="sxs-lookup"><span data-stu-id="7245b-124">It does not support an error output.</span></span>  
  
## <a name="append-and-new-file-options"></a><span data-ttu-id="7245b-125">Opzioni Accoda e Nuovo file</span><span class="sxs-lookup"><span data-stu-id="7245b-125">Append and New File Options</span></span>  
 <span data-ttu-id="7245b-126">La proprietà WriteOption include opzioni per accodare dati a un file esistente o crearne uno nuovo.</span><span class="sxs-lookup"><span data-stu-id="7245b-126">The WriteOption property includes options to append data to an existing file or create a new file.</span></span>  
  
 <span data-ttu-id="7245b-127">La tabella seguente descrive le opzioni disponibili per la proprietà WriteOption.</span><span class="sxs-lookup"><span data-stu-id="7245b-127">The following table describes the available options for the WriteOption property.</span></span>  
  
|<span data-ttu-id="7245b-128">Opzione</span><span class="sxs-lookup"><span data-stu-id="7245b-128">Option</span></span>|<span data-ttu-id="7245b-129">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7245b-129">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="7245b-130">Accoda</span><span class="sxs-lookup"><span data-stu-id="7245b-130">Append</span></span>|<span data-ttu-id="7245b-131">Accoda i dati a un file esistente.</span><span class="sxs-lookup"><span data-stu-id="7245b-131">Appends data to an existing file.</span></span> <span data-ttu-id="7245b-132">I metadati dei dati accodati devono corrispondere al formato del file.</span><span class="sxs-lookup"><span data-stu-id="7245b-132">The metadata of the appended data must match the file format.</span></span>|  
|<span data-ttu-id="7245b-133">Crea sempre</span><span class="sxs-lookup"><span data-stu-id="7245b-133">Create always</span></span>|<span data-ttu-id="7245b-134">Crea sempre un nuovo file.</span><span class="sxs-lookup"><span data-stu-id="7245b-134">Always creates a new file.</span></span>|  
|<span data-ttu-id="7245b-135">Crea una sola volta</span><span class="sxs-lookup"><span data-stu-id="7245b-135">Create once</span></span>|<span data-ttu-id="7245b-136">Crea un nuovo file.</span><span class="sxs-lookup"><span data-stu-id="7245b-136">Creates a new file.</span></span> <span data-ttu-id="7245b-137">Se il file esiste, il componente ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="7245b-137">If the file exists, the component fails.</span></span>|  
|<span data-ttu-id="7245b-138">Tronca e accoda</span><span class="sxs-lookup"><span data-stu-id="7245b-138">Truncate and append</span></span>|<span data-ttu-id="7245b-139">Tronca un file esistente e quindi vi scrive i dati.</span><span class="sxs-lookup"><span data-stu-id="7245b-139">Truncates an existing file and then writes the data to the file.</span></span> <span data-ttu-id="7245b-140">I metadati dei dati accodati devono corrispondere al formato del file.</span><span class="sxs-lookup"><span data-stu-id="7245b-140">The metadata of the appended data must match the file format.</span></span>|  
  
 <span data-ttu-id="7245b-141">Di seguito sono riportati elementi importanti relativi all'accodamento dei dati:</span><span class="sxs-lookup"><span data-stu-id="7245b-141">The following are important items about appending data:</span></span>  
  
-   <span data-ttu-id="7245b-142">L'accodamento dei dati in un file non elaborato esistente non comporta il riordinamento dei dati.</span><span class="sxs-lookup"><span data-stu-id="7245b-142">Appending data to an existing raw file does not re-sort the data.</span></span>  
  
     <span data-ttu-id="7245b-143">È necessario assicurarsi che le chiavi ordinate rimangano nell'ordine corretto.</span><span class="sxs-lookup"><span data-stu-id="7245b-143">You need to make certain that the sorted keys remain in the correct order.</span></span>  
  
-   <span data-ttu-id="7245b-144">L'accodamento dei dati in un file non elaborato esistente non comporta la modifica dei metadati del file (informazioni sull'ordinamento).</span><span class="sxs-lookup"><span data-stu-id="7245b-144">Appending data to an existing raw file does not change the file metadata (sort information).</span></span>  
  
 <span data-ttu-id="7245b-145">Ad esempio, in un pacchetto vengono letti i dati ordinati sul ProductKey (PK).</span><span class="sxs-lookup"><span data-stu-id="7245b-145">For example, a package reads data sorted on the ProductKey (PK).</span></span> <span data-ttu-id="7245b-146">Con il flusso di dati del pacchetto, i dati vengono accodati in un file non elaborato esistente.</span><span class="sxs-lookup"><span data-stu-id="7245b-146">The package data flow appends the data to an existing raw file.</span></span> <span data-ttu-id="7245b-147">Alla prima esecuzione del pacchetto, vengono ricevute tre righe (PK 1000, 1100, 1200).</span><span class="sxs-lookup"><span data-stu-id="7245b-147">The first time the package runs, three rows are received (PK 1000, 1100, 1200).</span></span> <span data-ttu-id="7245b-148">Nel file non elaborato sono ora contenuti i dati riportati di seguito.</span><span class="sxs-lookup"><span data-stu-id="7245b-148">The raw file now contains the following data.</span></span>  
  
-   <span data-ttu-id="7245b-149">1000, productA</span><span class="sxs-lookup"><span data-stu-id="7245b-149">1000, productA</span></span>  
  
-   <span data-ttu-id="7245b-150">1100, productB</span><span class="sxs-lookup"><span data-stu-id="7245b-150">1100, productB</span></span>  
  
-   <span data-ttu-id="7245b-151">1200, productC</span><span class="sxs-lookup"><span data-stu-id="7245b-151">1200, productC</span></span>  
  
 <span data-ttu-id="7245b-152">Alla seconda esecuzione del pacchetto, vengono ricevute due nuove righe (PK 1001, 1300).</span><span class="sxs-lookup"><span data-stu-id="7245b-152">The second time the package runs, two new rows are received (PK 1001, 1300).</span></span> <span data-ttu-id="7245b-153">Nel file non elaborato sono ora contenuti i dati riportati di seguito.</span><span class="sxs-lookup"><span data-stu-id="7245b-153">The raw file now contains the following data.</span></span>  
  
-   <span data-ttu-id="7245b-154">1000, productA</span><span class="sxs-lookup"><span data-stu-id="7245b-154">1000, productA</span></span>  
  
-   <span data-ttu-id="7245b-155">1100, productB</span><span class="sxs-lookup"><span data-stu-id="7245b-155">1100, productB</span></span>  
  
-   <span data-ttu-id="7245b-156">1200, productC</span><span class="sxs-lookup"><span data-stu-id="7245b-156">1200, productC</span></span>  
  
-   <span data-ttu-id="7245b-157">1001, productD</span><span class="sxs-lookup"><span data-stu-id="7245b-157">1001, productD</span></span>  
  
-   <span data-ttu-id="7245b-158">1300, productE</span><span class="sxs-lookup"><span data-stu-id="7245b-158">1300, productE</span></span>  
  
 <span data-ttu-id="7245b-159">I nuovi dati vengono accodati alla fine del file non elaborato e le chiavi ordinate (PK) non sono disponibili.</span><span class="sxs-lookup"><span data-stu-id="7245b-159">The new data is appended to the end of the raw file, and the sorted keys (PK) are out of order.</span></span> <span data-ttu-id="7245b-160">Inoltre, l'operazione di accodamento non ha modificato i metadati del file (informazioni di ordinamento).</span><span class="sxs-lookup"><span data-stu-id="7245b-160">In addition, the append operation didn't change the file metadata (sort information).</span></span> <span data-ttu-id="7245b-161">Se il file viene letto utilizzando l'origine file non elaborato, tramite il componente viene indicato che il file è ancora ordinato su PK anche se i dati nel file non sono più nell'ordine corretto.</span><span class="sxs-lookup"><span data-stu-id="7245b-161">If you read the file by using the Raw File source, the component indicates that the file is still sorted on PK even though the data in the file is no longer in the correct order.</span></span>  
  
 <span data-ttu-id="7245b-162">Per mantenere le chiavi ordinate nell'ordine corretto mentre si accodano i dati, è possibile progettare il flusso di dati del pacchetto nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="7245b-162">To keep the sorted keys in the correct order while appending data, you can design the package data flow as follows:</span></span>  
  
1.  <span data-ttu-id="7245b-163">Recuperare le nuove righe tramite l'origine A.</span><span class="sxs-lookup"><span data-stu-id="7245b-163">Retrieve new rows by using Source A.</span></span>  
  
2.  <span data-ttu-id="7245b-164">Recuperare le righe esistenti da RawFile1 utilizzando l'origine B.</span><span class="sxs-lookup"><span data-stu-id="7245b-164">Retrieve existing rows from RawFile1 using Source B.</span></span>  
  
3.  <span data-ttu-id="7245b-165">Combinare gli input delle origini A e B tramite la trasformazione Unione input multipli.</span><span class="sxs-lookup"><span data-stu-id="7245b-165">Combine the inputs from Source A and Source B by using the Union All transformation.</span></span>  
  
4.  <span data-ttu-id="7245b-166">Ordinare su PK.</span><span class="sxs-lookup"><span data-stu-id="7245b-166">Sort on PK.</span></span>  
  
5.  <span data-ttu-id="7245b-167">Scrivere in RawFile2 utilizzando la destinazione file non elaborato.</span><span class="sxs-lookup"><span data-stu-id="7245b-167">Write to RawFile2 by using the Raw File destination.</span></span>  
  
     <span data-ttu-id="7245b-168">RawFile1 viene bloccato perché ne viene eseguita la lettura nel flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="7245b-168">RawFile1 is locked because it's being read from, in the data flow.</span></span>  
  
6.  <span data-ttu-id="7245b-169">Sostituire RawFile1 con RawFile2.</span><span class="sxs-lookup"><span data-stu-id="7245b-169">Replace RawFile1 with RawFile2.</span></span>  
  
### <a name="using-the-raw-file-destination-in-a-loop"></a><span data-ttu-id="7245b-170">Utilizzo della destinazione file non elaborato in un ciclo</span><span class="sxs-lookup"><span data-stu-id="7245b-170">Using the Raw File Destination in a Loop</span></span>  
 <span data-ttu-id="7245b-171">Se il flusso di dati che utilizza la destinazione file non elaborato si trova in un ciclo, può rivelarsi utile creare il file una sola volta e quindi accodare i dati al file quando il ciclo viene ripetuto.</span><span class="sxs-lookup"><span data-stu-id="7245b-171">If the data flow that uses the Raw File destination is in a loop, you may want to create the file once and then append data to the file when the loop repeats.</span></span> <span data-ttu-id="7245b-172">Per accodare i dati al file, è necessario che i dati accodati corrispondano al formato del file esistente.</span><span class="sxs-lookup"><span data-stu-id="7245b-172">To append data to the file, the data that is appended must match the format of the existing file.</span></span>  
  
 <span data-ttu-id="7245b-173">Per creare il file nella prima iterazione del ciclo e quindi accodare righe nelle iterazioni successive, è necessario eseguire le operazioni seguenti in fase di progettazione:</span><span class="sxs-lookup"><span data-stu-id="7245b-173">To create the file in the first iteration of the loop, and then append rows in the subsequent iterations of the loop, you need to do the following at design time:</span></span>  
  
1.  <span data-ttu-id="7245b-174">Impostare la proprietà WriteOption su **CreateOnce** o **CreateAlways**ed eseguire un'iterazione del ciclo.</span><span class="sxs-lookup"><span data-stu-id="7245b-174">Set the WriteOption property to **CreateOnce** or **CreateAlways**and run one iteration of the loop.</span></span> <span data-ttu-id="7245b-175">Il file viene creato</span><span class="sxs-lookup"><span data-stu-id="7245b-175">The file is created.</span></span> <span data-ttu-id="7245b-176">e viene garantita così la corrispondenza tra i metadati dei dati accodati e il file.</span><span class="sxs-lookup"><span data-stu-id="7245b-176">This ensures that the metadata of appended data and the file matches.</span></span>  
  
2.  <span data-ttu-id="7245b-177">Reimpostare la proprietà WriteOption su **Append** e impostare la proprietà ValidateExternalMetadata su `False` .</span><span class="sxs-lookup"><span data-stu-id="7245b-177">Reset the WriteOption property to **Append** and set the ValidateExternalMetadata property to `False`.</span></span>  
  
 <span data-ttu-id="7245b-178">Se si usa l'opzione **TruncateAppend** invece di **Append** , le righe aggiunte in qualsiasi iterazione precedente verranno troncate e quindi verranno accodate nuove righe.</span><span class="sxs-lookup"><span data-stu-id="7245b-178">If you use the **TruncateAppend** option instead of the **Append** option, it will truncate rows that were added in any previous iteration, and then append new rows.</span></span> <span data-ttu-id="7245b-179">Per usare l'opzione **TruncateAppend** , è anche necessario che i dati corrispondano al formato del file.</span><span class="sxs-lookup"><span data-stu-id="7245b-179">Using the **TruncateAppend** option also requires that the data matches the file format.</span></span>  
  
## <a name="configuration-of-the-raw-file-destination"></a><span data-ttu-id="7245b-180">Configurazione della destinazione file non elaborato</span><span class="sxs-lookup"><span data-stu-id="7245b-180">Configuration of the Raw File Destination</span></span>  
 <span data-ttu-id="7245b-181">È possibile impostare le proprietà tramite Progettazione [!INCLUDE[ssIS](../../includes/ssis-md.md)] o a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="7245b-181">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="7245b-182">Nella finestra di dialogo **Editor avanzato** sono disponibili le proprietà che è possibile impostare a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="7245b-182">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="7245b-183">Per ulteriori informazioni sulle proprietà che è possibile impostare nella finestra di dialogo **Editor avanzato** o a livello di codice, fare clic su uno degli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="7245b-183">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="7245b-184">Proprietà comuni</span><span class="sxs-lookup"><span data-stu-id="7245b-184">Common Properties</span></span>](../common-properties.md)  
  
-   [<span data-ttu-id="7245b-185">Proprietà personalizzate del file non elaborato</span><span class="sxs-lookup"><span data-stu-id="7245b-185">Raw File Custom Properties</span></span>](raw-file-custom-properties.md)  
  
## <a name="related-tasks"></a><span data-ttu-id="7245b-186">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="7245b-186">Related Tasks</span></span>  
 <span data-ttu-id="7245b-187">Per informazioni su come impostare le proprietà del componente, vedere [Impostazione delle proprietà di un componente flusso di dati](set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="7245b-187">For information about how to set properties of the component, see [Set the Properties of a Data Flow Component](set-the-properties-of-a-data-flow-component.md).</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="7245b-188">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="7245b-188">Related Content</span></span>  
 <span data-ttu-id="7245b-189">Post di blog sugli [aspetti positivi dei file non elaborati](https://www.sqlservercentral.com/blogs/31-days-of-ssis-%e2%80%93-raw-files-are-awesome-131)nel sito Web sqlservercentral.com.</span><span class="sxs-lookup"><span data-stu-id="7245b-189">Blog entry, [Raw Files Are Awesome](https://www.sqlservercentral.com/blogs/31-days-of-ssis-%e2%80%93-raw-files-are-awesome-131), on sqlservercentral.com.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7245b-190">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7245b-190">See Also</span></span>  
 <span data-ttu-id="7245b-191">[Origine file non elaborato](raw-file-source.md) </span><span class="sxs-lookup"><span data-stu-id="7245b-191">[Raw File Source](raw-file-source.md) </span></span>  
 [<span data-ttu-id="7245b-192">Flusso di dati</span><span class="sxs-lookup"><span data-stu-id="7245b-192">Data Flow</span></span>](data-flow.md)  
  
  
