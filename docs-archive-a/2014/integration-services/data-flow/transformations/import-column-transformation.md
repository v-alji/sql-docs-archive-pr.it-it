---
title: Trasformazione Importa colonna | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.importcolumntrans.f1
helpviewer_keywords:
- Import Column transformation [Integration Services]
- columns [Integration Services], importing
- importing data, SSIS packages
- inserting data
ms.assetid: ac3b74c1-ef54-4297-8062-1734324fffcc
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f4330438614cce7892e74dc9a1dcbb6680b72972
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636311"
---
# <a name="import-column-transformation"></a><span data-ttu-id="94598-102">Trasformazione Importa colonna</span><span class="sxs-lookup"><span data-stu-id="94598-102">Import Column Transformation</span></span>
  <span data-ttu-id="94598-103">La trasformazione Importa colonna legge i dati dai file e li aggiunge alle colonne in un flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="94598-103">The Import Column transformation reads data from files and adds the data to columns in a data flow.</span></span> <span data-ttu-id="94598-104">Tramite questa trasformazione un pacchetto può aggiungere a un flusso di dati immagini e testo archiviati in file distinti.</span><span class="sxs-lookup"><span data-stu-id="94598-104">Using this transformation, a package can add text and images stored in separate files to a data flow.</span></span> <span data-ttu-id="94598-105">Un flusso di dati che carica dati in una tabella in cui sono archiviate informazioni sui prodotti può ad esempio includere la trasformazione Importa colonna per importare dai rispettivi file i commenti dei clienti su ogni prodotto e aggiungerli al flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="94598-105">For example, a data flow that loads data into a table that stores product information can include the Import Column transformation to import customer reviews of each product from files and add the reviews to the data flow.</span></span>  
  
 <span data-ttu-id="94598-106">Per configurare la trasformazione Importa colonna, procedere nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="94598-106">You can configure the Import Column transformation in the following ways:</span></span>  
  
-   <span data-ttu-id="94598-107">Specificare le colonne in cui devono essere aggiunti i dati.</span><span class="sxs-lookup"><span data-stu-id="94598-107">Specify the columns to which the transformation adds data.</span></span>  
  
-   <span data-ttu-id="94598-108">Specificare se la trasformazione prevede un indicatore dell'ordine dei byte.</span><span class="sxs-lookup"><span data-stu-id="94598-108">Specify whether the transformation expects a byte-order mark (BOM).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="94598-109">È previsto un indicatore dell'ordine dei byte solo se i dati sono di tipo DT_NTEXT.</span><span class="sxs-lookup"><span data-stu-id="94598-109">A BOM is only expected if the data has the DT_NTEXT data type.</span></span>  
  
 <span data-ttu-id="94598-110">I nomi dei file che contengono i dati si trovano in una colonna nell'input della trasformazione.</span><span class="sxs-lookup"><span data-stu-id="94598-110">A column in the transformation input contains the names of files that hold the data.</span></span> <span data-ttu-id="94598-111">Ogni riga nel set di dati può specificare un file diverso.</span><span class="sxs-lookup"><span data-stu-id="94598-111">Each row in the dataset can specify a different file.</span></span> <span data-ttu-id="94598-112">Quando la trasformazione Importa colonna elabora una riga, legge il nome del file, apre il file corrispondente nel file system e ne carica il contenuto in una colonna di output.</span><span class="sxs-lookup"><span data-stu-id="94598-112">When the Import Column transformation processes a row, it reads the file name, opens the corresponding file in the file system, and loads the file content into an output column.</span></span> <span data-ttu-id="94598-113">Il tipo di dati della colonna di output deve essere DT_TEXT, DT_NTEXT o DT_IMAGE.</span><span class="sxs-lookup"><span data-stu-id="94598-113">The data type of the output column must be DT_TEXT, DT_NTEXT, or DT_IMAGE.</span></span> <span data-ttu-id="94598-114">Per altre informazioni, vedere [Tipi di dati di Integration Services](../integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="94598-114">For more information, see [Integration Services Data Types](../integration-services-data-types.md).</span></span>  
  
 <span data-ttu-id="94598-115">Questa trasformazione include un input, un output e un output degli errori.</span><span class="sxs-lookup"><span data-stu-id="94598-115">This transformation has one input, one output, and one error output.</span></span>  
  
## <a name="configuration-of-the-import-column-transformation"></a><span data-ttu-id="94598-116">Configurazione della trasformazione Importa colonna</span><span class="sxs-lookup"><span data-stu-id="94598-116">Configuration of the Import Column Transformation</span></span>  
 <span data-ttu-id="94598-117">È possibile impostare le proprietà tramite Progettazione [!INCLUDE[ssIS](../../../includes/ssis-md.md)] o a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="94598-117">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="94598-118">Nella finestra di dialogo **Editor avanzato** sono disponibili le proprietà che è possibile impostare a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="94598-118">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="94598-119">Per ulteriori informazioni sulle proprietà che è possibile impostare nella finestra di dialogo **Editor avanzato** o a livello di codice, fare clic su uno degli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="94598-119">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="94598-120">Proprietà comuni</span><span class="sxs-lookup"><span data-stu-id="94598-120">Common Properties</span></span>](../../common-properties.md)  
  
-   [<span data-ttu-id="94598-121">Proprietà personalizzate delle trasformazioni</span><span class="sxs-lookup"><span data-stu-id="94598-121">Transformation Custom Properties</span></span>](transformation-custom-properties.md)  
  
## <a name="related-tasks"></a><span data-ttu-id="94598-122">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="94598-122">Related Tasks</span></span>  
 <span data-ttu-id="94598-123">Per informazioni su come impostare le proprietà del componente, vedere [Impostazione delle proprietà di un componente del flusso di dati](../set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="94598-123">For information about how to set properties of this component, see [Set the Properties of a Data Flow Component](../set-the-properties-of-a-data-flow-component.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94598-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="94598-124">See Also</span></span>  
 <span data-ttu-id="94598-125">[Trasformazione Esporta colonna](export-column-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="94598-125">[Export Column Transformation](export-column-transformation.md) </span></span>  
 <span data-ttu-id="94598-126">[Flusso di dati](../data-flow.md) </span><span class="sxs-lookup"><span data-stu-id="94598-126">[Data Flow](../data-flow.md) </span></span>  
 [<span data-ttu-id="94598-127">Trasformazioni di Integration Services</span><span class="sxs-lookup"><span data-stu-id="94598-127">Integration Services Transformations</span></span>](integration-services-transformations.md)  
  
  
