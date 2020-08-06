---
title: Destinazione file flat | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.flatfiledest.f1
helpviewer_keywords:
- flat files
- Flat File destination
- text file writing [Integration Services]
- destinations [Integration Services], Flat File
ms.assetid: e0d6e356-8db4-48aa-ba66-029397f98f61
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a961b7528b13a4eaa3297343e91f1deaf2fa3226
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726099"
---
# <a name="flat-file-destination"></a><span data-ttu-id="7c9f8-102">file flat - destinazione</span><span class="sxs-lookup"><span data-stu-id="7c9f8-102">Flat File Destination</span></span>
  <span data-ttu-id="7c9f8-103">La destinazione file flat scrive dati in un file di testo</span><span class="sxs-lookup"><span data-stu-id="7c9f8-103">The Flat File destination writes data to a text file.</span></span> <span data-ttu-id="7c9f8-104">che può essere in formato delimitato, a larghezza fissa, a larghezza fissa con delimitatore di riga o non allineato a destra.</span><span class="sxs-lookup"><span data-stu-id="7c9f8-104">The text file can be in delimited, fixed width, fixed width with row delimiter, or ragged right format.</span></span>  
  
 <span data-ttu-id="7c9f8-105">Per configurare la destinazione file flat, procedere nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="7c9f8-105">You can configure the Flat File destination in the following ways:</span></span>  
  
-   <span data-ttu-id="7c9f8-106">Specificare un blocco di testo inserito nel file prima di iniziare a scrivere i dati.</span><span class="sxs-lookup"><span data-stu-id="7c9f8-106">Provide a block of text that is inserted in the file before any data is written.</span></span> <span data-ttu-id="7c9f8-107">Il testo può ad esempio contenere le intestazioni delle colonne.</span><span class="sxs-lookup"><span data-stu-id="7c9f8-107">The text can provide information such as column headings.</span></span>  
  
-   <span data-ttu-id="7c9f8-108">Specificare se sovrascrivere i dati eventualmente presenti in un file di destinazione con lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="7c9f8-108">Specify whether to overwrite a data in a destination file that has the same name.</span></span>  
  
 <span data-ttu-id="7c9f8-109">Per accedere al file di testo, questa destinazione utilizza una gestione connessione file flat.</span><span class="sxs-lookup"><span data-stu-id="7c9f8-109">This destination uses a Flat File connection manager to access the text file.</span></span> <span data-ttu-id="7c9f8-110">Impostando le proprietà della gestione connessione file flat utilizzata dalla destinazione file flat è possibile specificare la modalità con cui la destinazione file flat deve formattare e scrivere il file di testo.</span><span class="sxs-lookup"><span data-stu-id="7c9f8-110">By setting properties on the Flat File connection manager that the Flat File destination uses, you can specify how the Flat File destination formats and writes the text file.</span></span> <span data-ttu-id="7c9f8-111">Durante la configurazione della gestione connessione file flat si specificano informazioni sul file e sulle singole colonne nel file.</span><span class="sxs-lookup"><span data-stu-id="7c9f8-111">When you configure the Flat File connection manager, you specify information about the file and about each column in the file.</span></span> <span data-ttu-id="7c9f8-112">È ad esempio possibile specificare i caratteri che delimitano le righe e le colonne del file, oltre al tipo di dati e alla lunghezza di ogni colonna.</span><span class="sxs-lookup"><span data-stu-id="7c9f8-112">For example, you specify the characters that delimit columns and rows in the file, and you specify the data type and the length of each column.</span></span> <span data-ttu-id="7c9f8-113">Per ulteriori informazioni, vedere [Flat File Connection Manager](../connection-manager/file-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="7c9f8-113">For more information, see [Flat File Connection Manager](../connection-manager/file-connection-manager.md).</span></span>  
  
 <span data-ttu-id="7c9f8-114">La destinazione file flat include la proprietà personalizzata Header,</span><span class="sxs-lookup"><span data-stu-id="7c9f8-114">The Flat File destination includes the Header custom property.</span></span> <span data-ttu-id="7c9f8-115">che può essere aggiornata da un'espressione di proprietà al caricamento del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="7c9f8-115">This property can be updated by a property expression when the package is loaded.</span></span> <span data-ttu-id="7c9f8-116">Per altre informazioni, vedere [Espressioni di Integration Services &#40;SSIS&#41;](../expressions/integration-services-ssis-expressions.md), [Utilizzo delle espressioni di proprietà nei pacchetti](../expressions/use-property-expressions-in-packages.md) e [Proprietà personalizzate del file flat](flat-file-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="7c9f8-116">For more information, see [Integration Services &#40;SSIS&#41; Expressions](../expressions/integration-services-ssis-expressions.md), [Use Property Expressions in Packages](../expressions/use-property-expressions-in-packages.md), and [Flat File Custom Properties](flat-file-custom-properties.md).</span></span>  
  
 <span data-ttu-id="7c9f8-117">Questa destinazione include un solo output.</span><span class="sxs-lookup"><span data-stu-id="7c9f8-117">This destination has one output.</span></span> <span data-ttu-id="7c9f8-118">Non supporta un output degli errori.</span><span class="sxs-lookup"><span data-stu-id="7c9f8-118">It does not support an error output.</span></span>  
  
## <a name="configuration-of-the-flat-file-destination"></a><span data-ttu-id="7c9f8-119">Configurazione della destinazione file flat</span><span class="sxs-lookup"><span data-stu-id="7c9f8-119">Configuration of the Flat File Destination</span></span>  
 <span data-ttu-id="7c9f8-120">È possibile impostare le proprietà tramite Progettazione [!INCLUDE[ssIS](../../includes/ssis-md.md)] o a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="7c9f8-120">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="7c9f8-121">Per altre informazioni sulle proprietà che è possibile impostare nella finestra di dialogo **Editor origine file flat**, fare clic su uno degli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="7c9f8-121">For more information about the properties that you can set in the **Flat File Source Editor** dialog box, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="7c9f8-122">Editor destinazione file flat &#40;pagina Gestione connessione&#41;</span><span class="sxs-lookup"><span data-stu-id="7c9f8-122">Flat File Destination Editor &#40;Connection Manager Page&#41;</span></span>](../flat-file-destination-editor-connection-manager-page.md)  
  
-   [<span data-ttu-id="7c9f8-123">Editor destinazione file flat &#40;pagina Mapping&#41;</span><span class="sxs-lookup"><span data-stu-id="7c9f8-123">Flat File Destination Editor &#40;Mappings Page&#41;</span></span>](../flat-file-destination-editor-mappings-page.md)  
  
 <span data-ttu-id="7c9f8-124">Nella finestra di dialogo **Editor avanzato** sono disponibili le proprietà che è possibile impostare a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="7c9f8-124">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="7c9f8-125">Per ulteriori informazioni sulle proprietà che è possibile impostare nella finestra di dialogo **Editor avanzato** o a livello di codice, fare clic su uno degli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="7c9f8-125">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="7c9f8-126">Proprietà comuni</span><span class="sxs-lookup"><span data-stu-id="7c9f8-126">Common Properties</span></span>](../common-properties.md)  
  
-   [<span data-ttu-id="7c9f8-127">Proprietà personalizzate del file flat</span><span class="sxs-lookup"><span data-stu-id="7c9f8-127">Flat File Custom Properties</span></span>](flat-file-custom-properties.md)  
  
## <a name="related-tasks"></a><span data-ttu-id="7c9f8-128">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="7c9f8-128">Related Tasks</span></span>  
 <span data-ttu-id="7c9f8-129">Per informazioni su come impostare le proprietà di un componente del flusso di dati, vedere [Impostazione delle proprietà di un componente del flusso di dati](set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="7c9f8-129">For information about how to set the properties of a data flow component, see [Set the Properties of a Data Flow Component](set-the-properties-of-a-data-flow-component.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c9f8-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7c9f8-130">See Also</span></span>  
 <span data-ttu-id="7c9f8-131">[Origine file flat](flat-file-source.md) </span><span class="sxs-lookup"><span data-stu-id="7c9f8-131">[Flat File Source](flat-file-source.md) </span></span>  
 [<span data-ttu-id="7c9f8-132">Flusso di dati</span><span class="sxs-lookup"><span data-stu-id="7c9f8-132">Data Flow</span></span>](data-flow.md)  
  
  
