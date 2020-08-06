---
title: Editor trasformazione Esportazione colonna (pagina colonne) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.fileextractortransformation.columns.f1
helpviewer_keywords:
- Export Column Transformation Editor
ms.assetid: b659a5c2-5509-4b5b-9c82-136c971d5c7f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 404b404e2328228049ae46fb1c3089b0b4089f0a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626827"
---
# <a name="export-column-transformation-editor-columns-page"></a><span data-ttu-id="cf879-102">Editor trasformazione Esportazione colonna (pagina Colonne)</span><span class="sxs-lookup"><span data-stu-id="cf879-102">Export Column Transformation Editor (Columns Page)</span></span>
  <span data-ttu-id="cf879-103">Utilizzare la pagina **Colonne** della finestra di dialogo **Editor trasformazione Esportazione colonna** per specificare le colonne nel flusso di dati da estrarre in file.</span><span class="sxs-lookup"><span data-stu-id="cf879-103">Use the **Columns** page of the **Export Column Transformation Editor** dialog box to specify columns in the data flow to extract to files.</span></span> <span data-ttu-id="cf879-104">È possibile indicare se la trasformazione Esporta colonna deve accodare i dati a un file oppure sovrascrivere un file esistente.</span><span class="sxs-lookup"><span data-stu-id="cf879-104">You can specify whether the Export Column transformation appends data to a file or overwrites an existing file.</span></span>  
  
 <span data-ttu-id="cf879-105">Per ulteriori informazioni sulla trasformazione Esportazione colonna, vedere [Export Column Transformation](data-flow/transformations/export-column-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="cf879-105">To learn more about the Export Column transformation, see [Export Column Transformation](data-flow/transformations/export-column-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="cf879-106">Opzioni</span><span class="sxs-lookup"><span data-stu-id="cf879-106">Options</span></span>  
 <span data-ttu-id="cf879-107">**Colonna estrazione**</span><span class="sxs-lookup"><span data-stu-id="cf879-107">**Extract Column**</span></span>  
 <span data-ttu-id="cf879-108">Consente di eseguire una selezione dall'elenco di colonne di input contenenti dati di tipo text o image.</span><span class="sxs-lookup"><span data-stu-id="cf879-108">Select from the list of input columns that contain text or image data.</span></span> <span data-ttu-id="cf879-109">In tutte le righe devono essere presenti definizioni per **Colonna estrazione** e **Colonna percorso file**.</span><span class="sxs-lookup"><span data-stu-id="cf879-109">All rows should have definitions for **Extract Column** and **File Path Column**.</span></span>  
  
 <span data-ttu-id="cf879-110">**Colonna percorso file**</span><span class="sxs-lookup"><span data-stu-id="cf879-110">**File Path Column**</span></span>  
 <span data-ttu-id="cf879-111">Consente di eseguire una selezione dall'elenco di colonne di input contenenti nomi e percorsi di file.</span><span class="sxs-lookup"><span data-stu-id="cf879-111">Select from the list of input columns that contain file paths and file names.</span></span> <span data-ttu-id="cf879-112">In tutte le righe devono essere presenti definizioni per **Colonna estrazione** e **Colonna percorso file**.</span><span class="sxs-lookup"><span data-stu-id="cf879-112">All rows should have definitions for **Extract Column** and **File Path Column**.</span></span>  
  
 <span data-ttu-id="cf879-113">**Consenti accodamento**</span><span class="sxs-lookup"><span data-stu-id="cf879-113">**Allow Append**</span></span>  
 <span data-ttu-id="cf879-114">Consente di indicare se la trasformazione accoderà i dati ai file esistenti.</span><span class="sxs-lookup"><span data-stu-id="cf879-114">Specify whether the transformation appends data to existing files.</span></span> <span data-ttu-id="cf879-115">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="cf879-115">The default is `false`.</span></span>  
  
 <span data-ttu-id="cf879-116">**Forza troncamento**</span><span class="sxs-lookup"><span data-stu-id="cf879-116">**Force Truncate**</span></span>  
 <span data-ttu-id="cf879-117">Consente di indicare se la trasformazione eliminerà il contenuto di file esistenti prima di scrivere i dati.</span><span class="sxs-lookup"><span data-stu-id="cf879-117">Specify whether the transformation deletes the contents of existing files before writing data.</span></span> <span data-ttu-id="cf879-118">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="cf879-118">The default is `false`.</span></span>  
  
 <span data-ttu-id="cf879-119">**Scrivi indicatore ordine byte**</span><span class="sxs-lookup"><span data-stu-id="cf879-119">**Write BOM**</span></span>  
 <span data-ttu-id="cf879-120">Consente di specificare se scrivere un indicatore ordine byte (BOM) nel file.</span><span class="sxs-lookup"><span data-stu-id="cf879-120">Specify whether to write a byte-order mark (BOM) to the file.</span></span> <span data-ttu-id="cf879-121">L'indicatore dell'ordine byte viene scritto solo se i dati hanno tipo di dati `DT_NTEXT` o DT_WSTR e non sono accodati a un file di dati esistente.</span><span class="sxs-lookup"><span data-stu-id="cf879-121">A BOM is only written if the data has the `DT_NTEXT` or DT_WSTR data type and is not appended to an existing data file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf879-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cf879-122">See Also</span></span>  
 <span data-ttu-id="cf879-123">[Guida di riferimento ai messaggi e agli errori di Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="cf879-123">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="cf879-124">Editor trasformazione Esportazione colonna &#40;pagina Output degli errori&#41;</span><span class="sxs-lookup"><span data-stu-id="cf879-124">Export Column Transformation Editor &#40;Error Output Page&#41;</span></span>](../../2014/integration-services/export-column-transformation-editor-error-output-page.md)  
  
  
