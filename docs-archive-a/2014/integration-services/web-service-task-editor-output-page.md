---
title: Editor attività servizio Web (pagina output) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.webservicestask.output.f1
helpviewer_keywords:
- Web Service Task Editor
ms.assetid: 73c83969-7b0e-479d-a436-0a46b2068d01
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6ad034ae78a096ebe5998ac2c3d2573fe7c3bfd4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636774"
---
# <a name="web-service-task-editor-output-page"></a><span data-ttu-id="04a00-102">Editor attività Servizio Web (pagina Output)</span><span class="sxs-lookup"><span data-stu-id="04a00-102">Web Service Task Editor (Output Page)</span></span>
  <span data-ttu-id="04a00-103">Usare la pagina **Output** della finestra di dialogo **Editor attività Servizio Web** per specificare la posizione in cui archiviare il risultato restituito dal metodo Web.</span><span class="sxs-lookup"><span data-stu-id="04a00-103">Use the **Output** page of the **Web Service Task Editor** dialog box to specify where to store the result returned by the Web method.</span></span>  
  
 <span data-ttu-id="04a00-104">Per altre informazioni su questa attività, vedere [Attività Servizio Web](control-flow/web-service-task.md).</span><span class="sxs-lookup"><span data-stu-id="04a00-104">To learn about this task, see [Web Service Task](control-flow/web-service-task.md).</span></span>  
  
## <a name="static-options"></a><span data-ttu-id="04a00-105">Opzioni statiche</span><span class="sxs-lookup"><span data-stu-id="04a00-105">Static Options</span></span>  
 <span data-ttu-id="04a00-106">**OutputType**</span><span class="sxs-lookup"><span data-stu-id="04a00-106">**OutputType**</span></span>  
 <span data-ttu-id="04a00-107">Consente di selezionare il tipo di archiviazione da utilizzare per l'archiviazione dei risultati.</span><span class="sxs-lookup"><span data-stu-id="04a00-107">Select the storage type to use when storing the results.</span></span> <span data-ttu-id="04a00-108">Per questa proprietà sono disponibili le opzioni elencate nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="04a00-108">This property has the options listed in the following table.</span></span>  
  
|<span data-ttu-id="04a00-109">valore</span><span class="sxs-lookup"><span data-stu-id="04a00-109">Value</span></span>|<span data-ttu-id="04a00-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="04a00-110">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="04a00-111">**File Connection**</span><span class="sxs-lookup"><span data-stu-id="04a00-111">**File Connection**</span></span>|<span data-ttu-id="04a00-112">Consente di archiviare i risultati in un file.</span><span class="sxs-lookup"><span data-stu-id="04a00-112">Store the results in a file.</span></span> <span data-ttu-id="04a00-113">La selezione di questo valore determina la visualizzazione dell'opzione dinamica **File**.</span><span class="sxs-lookup"><span data-stu-id="04a00-113">Selecting this value displays the dynamic option, **File**.</span></span>|  
|<span data-ttu-id="04a00-114">**Variabile**</span><span class="sxs-lookup"><span data-stu-id="04a00-114">**Variable**</span></span>|<span data-ttu-id="04a00-115">Consente di archiviare i risultati in una variabile.</span><span class="sxs-lookup"><span data-stu-id="04a00-115">Store the results in a variable.</span></span> <span data-ttu-id="04a00-116">La selezione di questo valore determina la visualizzazione dell'opzione dinamica **Variabile**.</span><span class="sxs-lookup"><span data-stu-id="04a00-116">Selecting this value displays the dynamic option, **Variable**.</span></span>|  
  
## <a name="outputtype-dynamic-options"></a><span data-ttu-id="04a00-117">Opzioni dinamiche di OutputType</span><span class="sxs-lookup"><span data-stu-id="04a00-117">OutputType Dynamic Options</span></span>  
  
### <a name="outputtype--file-connection"></a><span data-ttu-id="04a00-118">OutputType = Connessione file</span><span class="sxs-lookup"><span data-stu-id="04a00-118">OutputType = File Connection</span></span>  
 <span data-ttu-id="04a00-119">**File**</span><span class="sxs-lookup"><span data-stu-id="04a00-119">**File**</span></span>  
 <span data-ttu-id="04a00-120">Selezionare una gestione connessione file nell'elenco oppure fare clic su \<**New Connection...**> per creare una nuova gestione connessione.</span><span class="sxs-lookup"><span data-stu-id="04a00-120">Select a File connection manager in the list or click \<**New Connection...**> to create a new connection manager.</span></span>  
  
 <span data-ttu-id="04a00-121">**Argomenti correlati:** [Gestione connessione file](connection-manager/file-connection-manager.md), [Editor gestione connessione file](../../2014/integration-services/file-connection-manager-editor.md)</span><span class="sxs-lookup"><span data-stu-id="04a00-121">**Related Topics:** [File Connection Manager](connection-manager/file-connection-manager.md), [File Connection Manager Editor](../../2014/integration-services/file-connection-manager-editor.md)</span></span>  
  
### <a name="outputtype--variable"></a><span data-ttu-id="04a00-122">OutputType = Variabile</span><span class="sxs-lookup"><span data-stu-id="04a00-122">OutputType = Variable</span></span>  
 <span data-ttu-id="04a00-123">**Variabile**</span><span class="sxs-lookup"><span data-stu-id="04a00-123">**Variable**</span></span>  
 <span data-ttu-id="04a00-124">Selezionare una variabile nell'elenco oppure fare clic su \<**New Variable...**> per crearne una nuova.</span><span class="sxs-lookup"><span data-stu-id="04a00-124">Select a variable in the list or click \<**New Variable...**> to create a new variable.</span></span>  
  
 <span data-ttu-id="04a00-125">**Argomenti correlati:**  [Variabili di Integration Services &#40;SSIS&#41;](integration-services-ssis-variables.md), [Aggiungere una variabile](../../2014/integration-services/add-variable.md)</span><span class="sxs-lookup"><span data-stu-id="04a00-125">**Related Topics:**  [Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md), [Add Variable](../../2014/integration-services/add-variable.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04a00-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="04a00-126">See Also</span></span>  
 <span data-ttu-id="04a00-127">[Guida di riferimento ai messaggi e agli errori di Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="04a00-127">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="04a00-128">[Editor attività servizio Web &#40;pagina generale&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="04a00-128">[Web Service Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="04a00-129">[Editor attività servizio Web &#40;pagina di input&#41;](../../2014/integration-services/web-service-task-editor-input-page.md) </span><span class="sxs-lookup"><span data-stu-id="04a00-129">[Web Service Task Editor &#40;Input Page&#41;](../../2014/integration-services/web-service-task-editor-input-page.md) </span></span>  
 [<span data-ttu-id="04a00-130">Pagina Espressioni</span><span class="sxs-lookup"><span data-stu-id="04a00-130">Expressions Page</span></span>](expressions/expressions-page.md)  
  
  
