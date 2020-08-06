---
title: Trasformazione Esporta colonna | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.exportcolumntrans.f1
helpviewer_keywords:
- exporting data
- append options [Integration Services]
- Export Column transformation [Integration Services]
- columns [Integration Services], exporting
- inserting data
- truncate options [Integration Services]
ms.assetid: 678d2dfc-e40c-4fbb-b2cc-42fffc44478a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a7ed2bef02d75b72870514e2333d2fa58720fb60
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625486"
---
# <a name="export-column-transformation"></a><span data-ttu-id="798b7-102">Trasformazione Esporta colonna</span><span class="sxs-lookup"><span data-stu-id="798b7-102">Export Column Transformation</span></span>
  <span data-ttu-id="798b7-103">La trasformazione Esporta colonna legge dati in un flusso di dati e li inserisce in un file.</span><span class="sxs-lookup"><span data-stu-id="798b7-103">The Export Column transformation reads data in a data flow and inserts the data into a file.</span></span> <span data-ttu-id="798b7-104">Se ad esempio il flusso di dati contiene informazioni sui prodotti, ad esempio l'immagine di ogni prodotto, è possibile utilizzare la trasformazione Esporta colonna per salvare tali immagini in uno o più file.</span><span class="sxs-lookup"><span data-stu-id="798b7-104">For example, if the data flow contains product information, such as a picture of each product, you could use the Export Column transformation to save the images to files.</span></span>  
  
## <a name="append-and-truncate-options"></a><span data-ttu-id="798b7-105">Opzioni Accoda e tronca</span><span class="sxs-lookup"><span data-stu-id="798b7-105">Append and Truncate Options</span></span>  
 <span data-ttu-id="798b7-106">Nella tabella seguente vengono descritti gli effetti delle impostazioni delle opzioni relative all'accodamento e al troncamento sui risultati.</span><span class="sxs-lookup"><span data-stu-id="798b7-106">The following table describes how the settings for the append and truncate options affect results.</span></span>  
  
|<span data-ttu-id="798b7-107">Accoda</span><span class="sxs-lookup"><span data-stu-id="798b7-107">Append</span></span>|<span data-ttu-id="798b7-108">Truncate</span><span class="sxs-lookup"><span data-stu-id="798b7-108">Truncate</span></span>|<span data-ttu-id="798b7-109">File esistente</span><span class="sxs-lookup"><span data-stu-id="798b7-109">File exists</span></span>|<span data-ttu-id="798b7-110">Risultati</span><span class="sxs-lookup"><span data-stu-id="798b7-110">Results</span></span>|  
|------------|--------------|-----------------|-------------|  
|<span data-ttu-id="798b7-111">False</span><span class="sxs-lookup"><span data-stu-id="798b7-111">False</span></span>|<span data-ttu-id="798b7-112">False</span><span class="sxs-lookup"><span data-stu-id="798b7-112">False</span></span>|<span data-ttu-id="798b7-113">No</span><span class="sxs-lookup"><span data-stu-id="798b7-113">No</span></span>|<span data-ttu-id="798b7-114">La trasformazione crea un nuovo file e vi scrive i dati.</span><span class="sxs-lookup"><span data-stu-id="798b7-114">The transformation creates a new file and writes the data to the file.</span></span>|  
|<span data-ttu-id="798b7-115">True</span><span class="sxs-lookup"><span data-stu-id="798b7-115">True</span></span>|<span data-ttu-id="798b7-116">False</span><span class="sxs-lookup"><span data-stu-id="798b7-116">False</span></span>|<span data-ttu-id="798b7-117">No</span><span class="sxs-lookup"><span data-stu-id="798b7-117">No</span></span>|<span data-ttu-id="798b7-118">La trasformazione crea un nuovo file e vi scrive i dati.</span><span class="sxs-lookup"><span data-stu-id="798b7-118">The transformation creates a new file and writes the data to the file.</span></span>|  
|<span data-ttu-id="798b7-119">False</span><span class="sxs-lookup"><span data-stu-id="798b7-119">False</span></span>|<span data-ttu-id="798b7-120">True</span><span class="sxs-lookup"><span data-stu-id="798b7-120">True</span></span>|<span data-ttu-id="798b7-121">No</span><span class="sxs-lookup"><span data-stu-id="798b7-121">No</span></span>|<span data-ttu-id="798b7-122">La trasformazione crea un nuovo file e vi scrive i dati.</span><span class="sxs-lookup"><span data-stu-id="798b7-122">The transformation creates a new file and writes the data to the file.</span></span>|  
|<span data-ttu-id="798b7-123">True</span><span class="sxs-lookup"><span data-stu-id="798b7-123">True</span></span>|<span data-ttu-id="798b7-124">True</span><span class="sxs-lookup"><span data-stu-id="798b7-124">True</span></span>|<span data-ttu-id="798b7-125">No</span><span class="sxs-lookup"><span data-stu-id="798b7-125">No</span></span>|<span data-ttu-id="798b7-126">La trasformazione non supera la convalida in fase di progettazione.</span><span class="sxs-lookup"><span data-stu-id="798b7-126">The transformation fails design time validation.</span></span> <span data-ttu-id="798b7-127">Non è consentito impostare su `true` entrambe le proprietà.</span><span class="sxs-lookup"><span data-stu-id="798b7-127">It is not valid to set both properties to `true`.</span></span>|  
|<span data-ttu-id="798b7-128">False</span><span class="sxs-lookup"><span data-stu-id="798b7-128">False</span></span>|<span data-ttu-id="798b7-129">False</span><span class="sxs-lookup"><span data-stu-id="798b7-129">False</span></span>|<span data-ttu-id="798b7-130">Sì</span><span class="sxs-lookup"><span data-stu-id="798b7-130">Yes</span></span>|<span data-ttu-id="798b7-131">Viene generato un errore di run-time.</span><span class="sxs-lookup"><span data-stu-id="798b7-131">A run-time error occurs.</span></span> <span data-ttu-id="798b7-132">Il file esiste ma la trasformazione non è in grado di scrivervi.</span><span class="sxs-lookup"><span data-stu-id="798b7-132">The file exists, but the transformation cannot write to it.</span></span>|  
|<span data-ttu-id="798b7-133">False</span><span class="sxs-lookup"><span data-stu-id="798b7-133">False</span></span>|<span data-ttu-id="798b7-134">True</span><span class="sxs-lookup"><span data-stu-id="798b7-134">True</span></span>|<span data-ttu-id="798b7-135">Sì</span><span class="sxs-lookup"><span data-stu-id="798b7-135">Yes</span></span>|<span data-ttu-id="798b7-136">La trasformazione elimina e ricrea il file e vi scrive i dati.</span><span class="sxs-lookup"><span data-stu-id="798b7-136">The transformation deletes and re-creates the file and writes the data to the file.</span></span>|  
|<span data-ttu-id="798b7-137">True</span><span class="sxs-lookup"><span data-stu-id="798b7-137">True</span></span>|<span data-ttu-id="798b7-138">False</span><span class="sxs-lookup"><span data-stu-id="798b7-138">False</span></span>|<span data-ttu-id="798b7-139">Sì</span><span class="sxs-lookup"><span data-stu-id="798b7-139">Yes</span></span>|<span data-ttu-id="798b7-140">La trasformazione apre il file e scrive i dati alla fine.</span><span class="sxs-lookup"><span data-stu-id="798b7-140">The transformation opens the file and writes the data at the end of the file.</span></span>|  
|<span data-ttu-id="798b7-141">True</span><span class="sxs-lookup"><span data-stu-id="798b7-141">True</span></span>|<span data-ttu-id="798b7-142">True</span><span class="sxs-lookup"><span data-stu-id="798b7-142">True</span></span>|<span data-ttu-id="798b7-143">Sì</span><span class="sxs-lookup"><span data-stu-id="798b7-143">Yes</span></span>|<span data-ttu-id="798b7-144">La trasformazione non supera la convalida in fase di progettazione.</span><span class="sxs-lookup"><span data-stu-id="798b7-144">The transformation fails design time validation.</span></span> <span data-ttu-id="798b7-145">Non è consentito impostare su `true` entrambe le proprietà.</span><span class="sxs-lookup"><span data-stu-id="798b7-145">It is not valid to set both properties to `true`.</span></span>|  
  
## <a name="configuration-of-the-export-column-transformation"></a><span data-ttu-id="798b7-146">Configurazione della trasformazione Esporta colonna</span><span class="sxs-lookup"><span data-stu-id="798b7-146">Configuration of the Export Column Transformation</span></span>  
 <span data-ttu-id="798b7-147">Per configurare la trasformazione Esporta colonna, procedere nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="798b7-147">You can configure the Export Column transformation in the following ways:</span></span>  
  
-   <span data-ttu-id="798b7-148">Specificare le colonne di dati e le colonne contenenti i percorsi dei file in cui scrivere i dati.</span><span class="sxs-lookup"><span data-stu-id="798b7-148">Specify the data columns and the columns that contain the path of files to which to write the data.</span></span>  
  
-   <span data-ttu-id="798b7-149">Specificare se durante l'operazione di inserimento dei dati in file esistenti i dati vengono troncati o accodati.</span><span class="sxs-lookup"><span data-stu-id="798b7-149">Specify whether the data-insertion operation appends or truncates existing files.</span></span>  
  
-   <span data-ttu-id="798b7-150">Specificare se scrivere un indicatore dell'ordine dei byte nel file.</span><span class="sxs-lookup"><span data-stu-id="798b7-150">Specify whether a byte-order mark (BOM) is written to the file.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="798b7-151">L'indicatore dell'ordine dei byte viene scritto solo se i dati non vengono accodati a un file esistente e hanno tipo di dati DT_NTEXT.</span><span class="sxs-lookup"><span data-stu-id="798b7-151">A BOM is written only when the data is not appended to an existing file and the data has the DT_NTEXT data type.</span></span>  
  
 <span data-ttu-id="798b7-152">La trasformazione utilizza coppie di colonne di input: una contenente un nome di file e una contenente i dati.</span><span class="sxs-lookup"><span data-stu-id="798b7-152">The transformation uses pairs of input columns: One column contains a file name, and the other column contains data.</span></span> <span data-ttu-id="798b7-153">Ogni riga nel set di dati può specificare un file diverso.</span><span class="sxs-lookup"><span data-stu-id="798b7-153">Each row in the data set can specify a different file.</span></span> <span data-ttu-id="798b7-154">A mano a mano che la trasformazione elabora una riga, i dati vengono inseriti nel file specificato.</span><span class="sxs-lookup"><span data-stu-id="798b7-154">As the transformation processes a row, the data is inserted into the specified file.</span></span> <span data-ttu-id="798b7-155">In fase di esecuzione la trasformazione crea i file, se non esistono ancora, e quindi vi scrive i dati.</span><span class="sxs-lookup"><span data-stu-id="798b7-155">At run time, the transformation creates the files, if they do not already exist, and then the transformation writes the data to the files.</span></span> <span data-ttu-id="798b7-156">I dati da scrivere devono avere tipo di dati DT_TEXT, DT_NTEXT o DT_IMAGE.</span><span class="sxs-lookup"><span data-stu-id="798b7-156">The data to be written must have a DT_TEXT, DT_NTEXT, or DT_IMAGE data type.</span></span> <span data-ttu-id="798b7-157">Per altre informazioni, vedere [Tipi di dati di Integration Services](../integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="798b7-157">For more information, see [Integration Services Data Types](../integration-services-data-types.md).</span></span>  
  
 <span data-ttu-id="798b7-158">Questa trasformazione include un input, un output e un output degli errori.</span><span class="sxs-lookup"><span data-stu-id="798b7-158">This transformation has one input, one output, and one error output.</span></span>  
  
 <span data-ttu-id="798b7-159">È possibile impostare le proprietà tramite Progettazione [!INCLUDE[ssIS](../../../includes/ssis-md.md)] o a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="798b7-159">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="798b7-160">Per altre informazioni sulle proprietà che è possibile impostare nella finestra di dialogo **Editor trasformazione Esportazione colonna**, vedere [Editor trasformazione Esportazione colonna &#40;pagina Colonne&#41;](../../export-column-transformation-editor-columns-page.md).</span><span class="sxs-lookup"><span data-stu-id="798b7-160">For more information about the properties that you can set in the **Export Column Transformation Editor** dialog box, see [Export Column Transformation Editor &#40;Columns Page&#41;](../../export-column-transformation-editor-columns-page.md).</span></span>  
  
 <span data-ttu-id="798b7-161">Nella finestra di dialogo **Editor avanzato** sono disponibili le proprietà che è possibile impostare a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="798b7-161">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="798b7-162">Per ulteriori informazioni sulle proprietà che è possibile impostare nella finestra di dialogo **Editor avanzato** o a livello di codice, fare clic su uno degli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="798b7-162">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="798b7-163">Proprietà comuni</span><span class="sxs-lookup"><span data-stu-id="798b7-163">Common Properties</span></span>](../../common-properties.md)  
  
-   [<span data-ttu-id="798b7-164">Proprietà personalizzate delle trasformazioni</span><span class="sxs-lookup"><span data-stu-id="798b7-164">Transformation Custom Properties</span></span>](transformation-custom-properties.md)  
  
 <span data-ttu-id="798b7-165">Per altre informazioni su come impostare le proprietà, vedere [Impostazione delle proprietà di un componente del flusso di dati](../set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="798b7-165">For more information about how to set properties, see [Set the Properties of a Data Flow Component](../set-the-properties-of-a-data-flow-component.md).</span></span>  
  
  
