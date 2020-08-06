---
title: Editor attività Esegui DDL Analysis Services (pagina DDL) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.asexecuteddltask.ddl.f1
helpviewer_keywords:
- Analysis Services Execute DDL Task Editor
ms.assetid: f21bf8d0-ec5f-4c18-9de0-8875addb927b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d207afe666e582c44f1014a6c80f4f4984fd5410
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626228"
---
# <a name="analysis-services-execute-ddl-task-editor-ddl-page"></a><span data-ttu-id="e43d0-102">Editor attività Esegui DDL Analysis Services (pagina DDL)</span><span class="sxs-lookup"><span data-stu-id="e43d0-102">Analysis Services Execute DDL Task Editor (DDL Page)</span></span>
  <span data-ttu-id="e43d0-103">La pagina **DDL** della finestra di dialogo **Editor attività Esegui DDL Analysis Services** consente di specificare una connessione a un progetto di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] o a un database di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] per offrire informazioni sull'origine delle istruzioni DDL (Data Definition Language).</span><span class="sxs-lookup"><span data-stu-id="e43d0-103">Use the **DDL** page of the **Analysis Services Execute DDL Task Editor** dialog box to specify a connection to an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project or an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database and to provide information about the source of data definition language (DDL) statements.</span></span>  
  
 <span data-ttu-id="e43d0-104">Per altre informazioni su questa attività, vedere [Attività Esegui DDL Analysis Services](control-flow/analysis-services-execute-ddl-task.md).</span><span class="sxs-lookup"><span data-stu-id="e43d0-104">To learn about this task, see [Analysis Services Execute DDL Task](control-flow/analysis-services-execute-ddl-task.md).</span></span>  
  
## <a name="static-options"></a><span data-ttu-id="e43d0-105">Opzioni statiche</span><span class="sxs-lookup"><span data-stu-id="e43d0-105">Static Options</span></span>  
 <span data-ttu-id="e43d0-106">**Connection**</span><span class="sxs-lookup"><span data-stu-id="e43d0-106">**Connection**</span></span>  
 <span data-ttu-id="e43d0-107">Selezionare un progetto di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] o una gestione connessione [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] dall'elenco oppure fare clic su <\<**New connection...**> e usare la finestra di dialogo **Aggiungi gestione connessione Analysis Services** per creare una nuova connessione.</span><span class="sxs-lookup"><span data-stu-id="e43d0-107">Select an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project or an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] connection manager in the list, or click \<**New connection...**> and use the **Add Analysis Services Connection Manager** dialog box to create a new connection.</span></span>  
  
 <span data-ttu-id="e43d0-108">**Argomenti correlati:** [Riferimento all'interfaccia utente della finestra di dialogo Aggiungi gestione connessione Analysis Services](connection-manager/add-analysis-services-connection-manager-dialog-box-ui-reference.md), [Gestione connessione Analysis Services](connection-manager/analysis-services-connection-manager.md)</span><span class="sxs-lookup"><span data-stu-id="e43d0-108">**Related Topics:** [Add Analysis Services Connection Manager Dialog Box UI Reference](connection-manager/add-analysis-services-connection-manager-dialog-box-ui-reference.md), [Analysis Services Connection Manager](connection-manager/analysis-services-connection-manager.md)</span></span>  
  
 <span data-ttu-id="e43d0-109">**SourceType**</span><span class="sxs-lookup"><span data-stu-id="e43d0-109">**SourceType**</span></span>  
 <span data-ttu-id="e43d0-110">Consente di specificare il tipo di origine delle istruzioni DDL.</span><span class="sxs-lookup"><span data-stu-id="e43d0-110">Specify the source type of the DDL statements.</span></span> <span data-ttu-id="e43d0-111">Per questa proprietà sono disponibili le opzioni elencate nella tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="e43d0-111">This property has the options listed in the following table:</span></span>  
  
|<span data-ttu-id="e43d0-112">valore</span><span class="sxs-lookup"><span data-stu-id="e43d0-112">Value</span></span>|<span data-ttu-id="e43d0-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e43d0-113">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e43d0-114">**Direct Input**</span><span class="sxs-lookup"><span data-stu-id="e43d0-114">**Direct Input**</span></span>|<span data-ttu-id="e43d0-115">Consente di impostare l'origine sull'istruzione DDL archiviata nella casella di testo **SourceDirect** .</span><span class="sxs-lookup"><span data-stu-id="e43d0-115">Set the source to the DDL statement stored in the **SourceDirect** text box.</span></span> <span data-ttu-id="e43d0-116">Quando si seleziona questo valore vengono visualizzate le opzioni dinamiche illustrate nella sezione seguente.</span><span class="sxs-lookup"><span data-stu-id="e43d0-116">Selecting this value displays the dynamic options in the following section.</span></span>|  
|<span data-ttu-id="e43d0-117">**File Connection**</span><span class="sxs-lookup"><span data-stu-id="e43d0-117">**File Connection**</span></span>|<span data-ttu-id="e43d0-118">Consente di impostare l'origine su un file contenente l'istruzione DDL.</span><span class="sxs-lookup"><span data-stu-id="e43d0-118">Set the source to a file that contains the DDL statement.</span></span> <span data-ttu-id="e43d0-119">Quando si seleziona questo valore vengono visualizzate le opzioni dinamiche illustrate nella sezione seguente.</span><span class="sxs-lookup"><span data-stu-id="e43d0-119">Selecting this value displays the dynamic options in the following section.</span></span>|  
|<span data-ttu-id="e43d0-120">**Variabile**</span><span class="sxs-lookup"><span data-stu-id="e43d0-120">**Variable**</span></span>|<span data-ttu-id="e43d0-121">Consente di impostare l'origine su una variabile.</span><span class="sxs-lookup"><span data-stu-id="e43d0-121">Set the source to a variable.</span></span> <span data-ttu-id="e43d0-122">Quando si seleziona questo valore vengono visualizzate le opzioni dinamiche illustrate nella sezione seguente.</span><span class="sxs-lookup"><span data-stu-id="e43d0-122">Selecting this value displays the dynamic options in the following section.</span></span>|  
  
## <a name="dynamic-options"></a><span data-ttu-id="e43d0-123">Opzioni dinamiche</span><span class="sxs-lookup"><span data-stu-id="e43d0-123">Dynamic Options</span></span>  
  
### <a name="sourcetype--direct-input"></a><span data-ttu-id="e43d0-124">SourceType = Direct Input</span><span class="sxs-lookup"><span data-stu-id="e43d0-124">SourceType = Direct Input</span></span>  
 <span data-ttu-id="e43d0-125">**Origine**</span><span class="sxs-lookup"><span data-stu-id="e43d0-125">**Source**</span></span>  
 <span data-ttu-id="e43d0-126">Digitare le istruzioni DDL o fare clic sul pulsante con i puntini di sospensione **(...)** e quindi digitare le istruzioni nella finestra di dialogo **Istruzioni DDL**.</span><span class="sxs-lookup"><span data-stu-id="e43d0-126">Type the DDL statements or click the ellipsis **(...)** and then type the statements in the **DDL Statements** dialog box.</span></span>  
  
### <a name="sourcetype--file-connection"></a><span data-ttu-id="e43d0-127">SourceType = File Connection</span><span class="sxs-lookup"><span data-stu-id="e43d0-127">SourceType = File Connection</span></span>  
 <span data-ttu-id="e43d0-128">**Origine**</span><span class="sxs-lookup"><span data-stu-id="e43d0-128">**Source**</span></span>  
 <span data-ttu-id="e43d0-129">Selezionare una connessione file dall'elenco oppure fare clic su \<**New connection...**> e usare la finestra di dialogo **Gestione connessione file** per creare una nuova connessione.</span><span class="sxs-lookup"><span data-stu-id="e43d0-129">Select a File connection in the list, or click \<**New connection...**> and use the **File Connection Manager** dialog box to create a new connection.</span></span>  
  
 <span data-ttu-id="e43d0-130">**Argomenti correlati:** [Gestione connessione file](connection-manager/file-connection-manager.md)</span><span class="sxs-lookup"><span data-stu-id="e43d0-130">**Related Topics:** [File Connection Manager](connection-manager/file-connection-manager.md)</span></span>  
  
### <a name="sourcetype--variable"></a><span data-ttu-id="e43d0-131">SourceType = Variable</span><span class="sxs-lookup"><span data-stu-id="e43d0-131">SourceType = Variable</span></span>  
 <span data-ttu-id="e43d0-132">**Origine**</span><span class="sxs-lookup"><span data-stu-id="e43d0-132">**Source**</span></span>  
 <span data-ttu-id="e43d0-133">Selezionare una variabile dall'elenco oppure fare clic su \<**New variable...**> e usare la finestra di dialogo **Aggiungi variabile** per creare una nuova variabile.</span><span class="sxs-lookup"><span data-stu-id="e43d0-133">Select a variable in the list, or click \<**New variable...**> and use the **Add Variable** dialog box to create a new variable.</span></span>  
  
 <span data-ttu-id="e43d0-134">**Argomenti correlati:** [Variabili di Integration Services &#40;SSIS&#41;](integration-services-ssis-variables.md)</span><span class="sxs-lookup"><span data-stu-id="e43d0-134">**Related Topics:** [Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e43d0-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e43d0-135">See Also</span></span>  
 <span data-ttu-id="e43d0-136">[Guida di riferimento ai messaggi e agli errori di Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="e43d0-136">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="e43d0-137">[Analysis Services Editor attività Esegui DDL &#40;pagina generale&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="e43d0-137">[Analysis Services Execute DDL Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="e43d0-138">[Pagina Espressioni](expressions/expressions-page.md) </span><span class="sxs-lookup"><span data-stu-id="e43d0-138">[Expressions Page](expressions/expressions-page.md) </span></span>  
 <span data-ttu-id="e43d0-139">[Flusso di controllo](control-flow/control-flow.md) </span><span class="sxs-lookup"><span data-stu-id="e43d0-139">[Control Flow](control-flow/control-flow.md) </span></span>  
 <span data-ttu-id="e43d0-140">[Analysis Services linguaggio di scripting &#40;riferimento&#41; ASSL](https://docs.microsoft.com/bi-reference/assl/analysis-services-scripting-language-assl-for-xmla) </span><span class="sxs-lookup"><span data-stu-id="e43d0-140">[Analysis Services Scripting Language &#40;ASSL&#41; Reference](https://docs.microsoft.com/bi-reference/assl/analysis-services-scripting-language-assl-for-xmla) </span></span>  
 [<span data-ttu-id="e43d0-141">Guida di riferimento a XML for Analysis &#40;XMLA&#41;</span><span class="sxs-lookup"><span data-stu-id="e43d0-141">XML for Analysis  &#40;XMLA&#41; Reference</span></span>](https://docs.microsoft.com/bi-reference/xmla/xml-for-analysis-xmla-reference)  
  
  
