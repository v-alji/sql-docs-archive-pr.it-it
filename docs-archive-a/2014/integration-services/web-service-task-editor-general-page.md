---
title: Editor attività servizio Web (pagina generale) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.webservicestask.general.f1
helpviewer_keywords:
- Web Service Task Editor
ms.assetid: 4d7df283-430d-4f0f-9dd4-5909554cd5eb
author: chugugrace
ms.author: chugu
ms.openlocfilehash: dbacf2a2a867ab01039678ff4f43eebac839c11a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636779"
---
# <a name="web-service-task-editor-general-page"></a><span data-ttu-id="cbde8-102">Editor attività Servizio Web (pagina Generale)</span><span class="sxs-lookup"><span data-stu-id="cbde8-102">Web Service Task Editor (General Page)</span></span>
  <span data-ttu-id="cbde8-103">Usare la pagina **Generale** della finestra di dialogo **Editor attività Servizio Web** per specificare una gestione connessione HTTP e il percorso del file WSDL (Web Services Description Language) usato dall'attività Servizio Web, descrivere l'attività Servizio Web e scaricare il file WSDL.</span><span class="sxs-lookup"><span data-stu-id="cbde8-103">Use the **General** page of the **Web Services Task Editor** dialog box to specify an HTTP connection manager, specify the location of the Web Services Description Language (WSDL) file the Web Service task uses, describe the Web Services task, and download the WSDL file.</span></span>  
  
 <span data-ttu-id="cbde8-104">Per altre informazioni su questa attività, vedere [Attività Servizio Web](control-flow/web-service-task.md).</span><span class="sxs-lookup"><span data-stu-id="cbde8-104">For more information about this task, see [Web Service Task](control-flow/web-service-task.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="cbde8-105">Opzioni</span><span class="sxs-lookup"><span data-stu-id="cbde8-105">Options</span></span>  
 <span data-ttu-id="cbde8-106">**HTTPConnection**</span><span class="sxs-lookup"><span data-stu-id="cbde8-106">**HTTPConnection**</span></span>  
 <span data-ttu-id="cbde8-107">Selezionare una gestione connessione nell'elenco oppure fare clic su \<**New connection...**> per creare una nuova gestione connessione.</span><span class="sxs-lookup"><span data-stu-id="cbde8-107">Select a connection manager in the list, or click \<**New connection...**> to create a new connection manager.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="cbde8-108">La gestione connessione HTTP supporta solo l'autenticazione anonima e l'autenticazione di base.</span><span class="sxs-lookup"><span data-stu-id="cbde8-108">The HTTP connection manager supports only anonymous authentication and basic authentication.</span></span> <span data-ttu-id="cbde8-109">Non supporta l'autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="cbde8-109">It does not support Windows Authentication.</span></span>  
  
 <span data-ttu-id="cbde8-110">**Argomenti correlati:**  [Gestione connessione HTTP](connection-manager/http-connection-manager.md), [Editor gestione connessione HTTP &#40;pagina Server&#41;](../../2014/integration-services/http-connection-manager-editor-server-page.md)</span><span class="sxs-lookup"><span data-stu-id="cbde8-110">**Related Topics:**  [HTTP Connection Manager](connection-manager/http-connection-manager.md), [HTTP Connection Manager Editor &#40;Server Page&#41;](../../2014/integration-services/http-connection-manager-editor-server-page.md)</span></span>  
  
 <span data-ttu-id="cbde8-111">**WSDLFile**</span><span class="sxs-lookup"><span data-stu-id="cbde8-111">**WSDLFile**</span></span>  
 <span data-ttu-id="cbde8-112">Digitare il percorso completo di un file WSDL presente in locale nel computer oppure fare clic sul pulsante sfoglia **(...)** e individuare il file.</span><span class="sxs-lookup"><span data-stu-id="cbde8-112">Type the fully qualified path of a WSDL file that is local to the computer, or click the browse button **(...)** and locate this file.</span></span>  
  
 <span data-ttu-id="cbde8-113">Sezionare il file WSDL presente nel computer, se è già stato scaricato manualmente.</span><span class="sxs-lookup"><span data-stu-id="cbde8-113">If you have already manually downloaded the WSDL file to the computer, select this file.</span></span> <span data-ttu-id="cbde8-114">Se invece il file WSDL non è stato ancora scaricato, attenersi alla seguente procedura:</span><span class="sxs-lookup"><span data-stu-id="cbde8-114">However, if the WSDL file has not yet been downloaded, follow these steps:</span></span>  
  
-   <span data-ttu-id="cbde8-115">Creare un file vuoto con l'estensione di file "wsdl".</span><span class="sxs-lookup"><span data-stu-id="cbde8-115">Create an empty file that has the ".wsdl" file name extension.</span></span>  
  
-   <span data-ttu-id="cbde8-116">Selezionare questo file vuoto per l'opzione **WSDLFile** .</span><span class="sxs-lookup"><span data-stu-id="cbde8-116">Select this empty file for the **WSDLFile** option.</span></span>  
  
-   <span data-ttu-id="cbde8-117">Impostare il valore di **OverwriteWsdlFile** su `True` per consentire la sovrascrittura del file vuoto con il file WSDL effettivo.</span><span class="sxs-lookup"><span data-stu-id="cbde8-117">Set the value of **OverwriteWSDLFile** to `True` to enable the empty file to be overwritten with the actual WSDL file.</span></span>  
  
-   <span data-ttu-id="cbde8-118">Fare clic su **Scarica WSDL** per scaricare il file WSDL effettivo e sovrascrivere il file vuoto.</span><span class="sxs-lookup"><span data-stu-id="cbde8-118">Click **Download WSDL** to download the actual WSDL file and overwrite the empty file.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="cbde8-119">L'opzione **Scarica WSDL** non è abilitato fino a quando non si fornisce il nome di un file locale esistente nella casella **WSDLFile** .</span><span class="sxs-lookup"><span data-stu-id="cbde8-119">The **Download WSDL** option is not enabled until you provide the name of an existing local file in the **WSDLFile** box.</span></span>  
  
 <span data-ttu-id="cbde8-120">**OverwriteWSDLFile**</span><span class="sxs-lookup"><span data-stu-id="cbde8-120">**OverwriteWSDLFile**</span></span>  
 <span data-ttu-id="cbde8-121">Consente di specificare se il file WSDL per l'attività Servizio Web può essere sovrascritto.</span><span class="sxs-lookup"><span data-stu-id="cbde8-121">Indicate whether the WSDL file for the Web Service task can be overwritten.</span></span>  
  
 <span data-ttu-id="cbde8-122">Se si intende scaricare il file WSDL tramite il pulsante **Scarica WSDL** , impostare questo valore su `True` .</span><span class="sxs-lookup"><span data-stu-id="cbde8-122">If you intend to download the WSDL file by using the **Download WSDL** button, set this value to `True`.</span></span>  
  
 <span data-ttu-id="cbde8-123">**Nome**</span><span class="sxs-lookup"><span data-stu-id="cbde8-123">**Name**</span></span>  
 <span data-ttu-id="cbde8-124">Consente di specificare un nome univoco per l'attività Servizio Web.</span><span class="sxs-lookup"><span data-stu-id="cbde8-124">Provide a unique name for the Web Service task.</span></span> <span data-ttu-id="cbde8-125">Tale nome viene utilizzato come etichetta nell'icona dell'attività.</span><span class="sxs-lookup"><span data-stu-id="cbde8-125">This name is used as the label in the task icon.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cbde8-126">I nomi delle attività devono essere univoci all'interno di un pacchetto.</span><span class="sxs-lookup"><span data-stu-id="cbde8-126">Task names must be unique within a package.</span></span>  
  
 <span data-ttu-id="cbde8-127">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="cbde8-127">**Description**</span></span>  
 <span data-ttu-id="cbde8-128">Consente di digitare una descrizione dell'attività Servizio Web.</span><span class="sxs-lookup"><span data-stu-id="cbde8-128">Type a description of the Web Service task.</span></span>  
  
 <span data-ttu-id="cbde8-129">**Scarica WSDL**</span><span class="sxs-lookup"><span data-stu-id="cbde8-129">**Download WSDL**</span></span>  
 <span data-ttu-id="cbde8-130">Consente di scaricare il file WSDL.</span><span class="sxs-lookup"><span data-stu-id="cbde8-130">Download the WSDL file.</span></span>  
  
 <span data-ttu-id="cbde8-131">Questo pulsante non è attivato fino a quando non si fornisce il nome di un file locale esistente nella casella **WSDLFile** .</span><span class="sxs-lookup"><span data-stu-id="cbde8-131">This button is not enabled until you provide the name of an existing local file in the **WSDLFile** box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbde8-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cbde8-132">See Also</span></span>  
 <span data-ttu-id="cbde8-133">[Guida di riferimento ai messaggi e agli errori di Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="cbde8-133">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="cbde8-134">[Editor attività servizio Web &#40;pagina di input&#41;](../../2014/integration-services/web-service-task-editor-input-page.md) </span><span class="sxs-lookup"><span data-stu-id="cbde8-134">[Web Service Task Editor &#40;Input Page&#41;](../../2014/integration-services/web-service-task-editor-input-page.md) </span></span>  
 <span data-ttu-id="cbde8-135">[Editor attività servizio Web &#40;pagina output&#41;](../../2014/integration-services/web-service-task-editor-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="cbde8-135">[Web Service Task Editor &#40;Output Page&#41;](../../2014/integration-services/web-service-task-editor-output-page.md) </span></span>  
 [<span data-ttu-id="cbde8-136">Pagina Espressioni</span><span class="sxs-lookup"><span data-stu-id="cbde8-136">Expressions Page</span></span>](expressions/expressions-page.md)  
  
  
