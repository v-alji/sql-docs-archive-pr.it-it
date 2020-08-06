---
title: Editor origine file flat (pagina Gestione connessione) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.flatfilesourceadapter.connection.f1
helpviewer_keywords:
- Flat File Source Editor
ms.assetid: 2efd6baa-ed75-4f3f-b667-514024cebdb8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 03c1693c001dad2c8e90211b065eda208c42a07b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624849"
---
# <a name="flat-file-source-editor-connection-manager-page"></a><span data-ttu-id="531a3-102">Editor origine file flat (pagina Gestione connessione)</span><span class="sxs-lookup"><span data-stu-id="531a3-102">Flat File Source Editor (Connection Manager Page)</span></span>
  <span data-ttu-id="531a3-103">Utilizzare la pagina **Gestione connessione** della finestra di dialogo **Editor origine file flat** per selezionare la gestione connessione file flat per l'origine da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="531a3-103">Use the **Connection Manager** page of the **Flat File Source Editor** dialog box to select the connection manager that the Flat File source will use.</span></span> <span data-ttu-id="531a3-104">L'origine file flat legge i dati da un file di testo. I dati possono essere in formato delimitato, a larghezza fissa o misto.</span><span class="sxs-lookup"><span data-stu-id="531a3-104">The Flat File source reads data from a text file, which can be in a delimited, fixed width, or mixed format.</span></span>  
  
 <span data-ttu-id="531a3-105">Un'origine file flat può utilizzare uno dei tipi seguenti di gestione connessione:</span><span class="sxs-lookup"><span data-stu-id="531a3-105">A Flat File source can use one of the following types of connection managers:</span></span>  
  
-   <span data-ttu-id="531a3-106">Gestione connessione file flat se l'origine è un singolo file flat.</span><span class="sxs-lookup"><span data-stu-id="531a3-106">A Flat File connection manager if the source is a single flat file.</span></span> <span data-ttu-id="531a3-107">Per ulteriori informazioni, vedere [Flat File Connection Manager](connection-manager/file-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="531a3-107">For more information, see [Flat File Connection Manager](connection-manager/file-connection-manager.md).</span></span>  
  
-   <span data-ttu-id="531a3-108">Gestione connessione per più file flat se l'origine è data da più file flat e l'attività Flusso di dati si trova in un contenitore Ciclo, ad esempio il contenitore Ciclo For.</span><span class="sxs-lookup"><span data-stu-id="531a3-108">A Multiple Flat Files connection manager if the source is multiple flat files and the Data Flow task is inside a loop container, such as the For Loop container.</span></span> <span data-ttu-id="531a3-109">In ogni ciclo del contenitore, l'origine file flat carica dati dal nome file successivo fornito dalla gestione connessione per più file.</span><span class="sxs-lookup"><span data-stu-id="531a3-109">On each loop of the container, the Flat File source loads data from the next file name that the Multiple Flat Files connection manager provides.</span></span> <span data-ttu-id="531a3-110">Per ulteriori informazioni, vedere [Multiple Flat Files Connection Manager](connection-manager/multiple-flat-files-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="531a3-110">For more information, see [Multiple Flat Files Connection Manager](connection-manager/multiple-flat-files-connection-manager.md).</span></span>  
  
 <span data-ttu-id="531a3-111">Per ulteriori informazioni sull'origine file flat, vedere [Flat File Source](data-flow/flat-file-source.md).</span><span class="sxs-lookup"><span data-stu-id="531a3-111">To learn more about the Flat File source, see [Flat File Source](data-flow/flat-file-source.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="531a3-112">Opzioni</span><span class="sxs-lookup"><span data-stu-id="531a3-112">Options</span></span>  
 <span data-ttu-id="531a3-113">**Gestione connessione file flat**</span><span class="sxs-lookup"><span data-stu-id="531a3-113">**Flat file connection manager**</span></span>  
 <span data-ttu-id="531a3-114">Consente di selezionare una gestione connessione esistente nell'elenco o di creare una nuova gestione connessione facendo clic su **Nuova**.</span><span class="sxs-lookup"><span data-stu-id="531a3-114">Select an existing connection manager from the list, or create a new connection manager by clicking **New**.</span></span>  
  
 <span data-ttu-id="531a3-115">**Nuovo**</span><span class="sxs-lookup"><span data-stu-id="531a3-115">**New**</span></span>  
 <span data-ttu-id="531a3-116">Consente di creare una nuova gestione connessione usando la finestra di dialogo **Editor gestione connessione file flat** .</span><span class="sxs-lookup"><span data-stu-id="531a3-116">Create a new connection manager by using the **Flat File Connection Manager Editor** dialog box.</span></span>  
  
 <span data-ttu-id="531a3-117">**Mantieni i valori Null dell'origine come valori Null nel flusso di dati**</span><span class="sxs-lookup"><span data-stu-id="531a3-117">**Retain null values from the source as null values in the data flow**</span></span>  
 <span data-ttu-id="531a3-118">Consente di specificare se mantenere i valori Null durante l'estrazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="531a3-118">Specify whether to keep null values when data is extracted.</span></span> <span data-ttu-id="531a3-119">Il valore predefinito della proprietà è **false**.</span><span class="sxs-lookup"><span data-stu-id="531a3-119">The default value of this property is **false**.</span></span> <span data-ttu-id="531a3-120">Quando questo valore è f`alse`, l'origine del file flat sostituisce i valori Null dai dati di origine con i valori predefiniti corretti per ogni colonna, ad esempio stringhe vuote per colonne con stringhe e zero per colonne numeriche.</span><span class="sxs-lookup"><span data-stu-id="531a3-120">When this value is f`alse`, the Flat File source replaces null values from the source data with appropriate default values for each column, such as empty strings for string columns and zero for numeric columns.</span></span>  
  
 <span data-ttu-id="531a3-121">**Anteprima**</span><span class="sxs-lookup"><span data-stu-id="531a3-121">**Preview**</span></span>  
 <span data-ttu-id="531a3-122">Consente di visualizzare in anteprima i risultati nella finestra di dialogo **Vista dati** .</span><span class="sxs-lookup"><span data-stu-id="531a3-122">Preview results by using the **Data View** dialog box.</span></span> <span data-ttu-id="531a3-123">L'anteprima supporta la visualizzazione di un massimo di 200 righe.</span><span class="sxs-lookup"><span data-stu-id="531a3-123">Preview can display up to 200 rows.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="531a3-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="531a3-124">See Also</span></span>  
 <span data-ttu-id="531a3-125">[Guida di riferimento ai messaggi e agli errori di Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="531a3-125">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="531a3-126">[Editor origine file flat &#40;pagina colonne&#41;](../../2014/integration-services/flat-file-source-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="531a3-126">[Flat File Source Editor &#40;Columns Page&#41;](../../2014/integration-services/flat-file-source-editor-columns-page.md) </span></span>  
 <span data-ttu-id="531a3-127">[Editor origine file flat &#40;pagina output degli errori&#41;](../../2014/integration-services/flat-file-source-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="531a3-127">[Flat File Source Editor &#40;Error Output Page&#41;](../../2014/integration-services/flat-file-source-editor-error-output-page.md) </span></span>  
 [<span data-ttu-id="531a3-128">Gestione connessione file flat</span><span class="sxs-lookup"><span data-stu-id="531a3-128">Flat File Connection Manager</span></span>](connection-manager/file-connection-manager.md)  
  
  
