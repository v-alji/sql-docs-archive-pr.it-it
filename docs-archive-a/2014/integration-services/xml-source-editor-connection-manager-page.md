---
title: Editor origine XML (pagina Gestione connessione) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.xmlsourceadapter.connectionmanager.f1
helpviewer_keywords:
- XML Source Editor
ms.assetid: e6507403-a3ce-4b6f-91fc-a7de9f7b6283
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0e40ca6ef2d8fbcd10b756a2ce15f33730c367d1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637416"
---
# <a name="xml-source-editor-connection-manager-page"></a><span data-ttu-id="f6401-102">Editor origine XML (pagina Gestione connessione)</span><span class="sxs-lookup"><span data-stu-id="f6401-102">XML Source Editor (Connection Manager Page)</span></span>
  <span data-ttu-id="f6401-103">Utilizzare la pagina **Gestione connessione** di **Editor origine XML** per specificare un file XML e il file XSD che trasforma i dati XML.</span><span class="sxs-lookup"><span data-stu-id="f6401-103">Use the **Connection Manager** page of the **XML Source Editor** to specify an XML file and the XSD that transforms the XML data.</span></span>  
  
 <span data-ttu-id="f6401-104">Per ulteriori informazioni sull'origine XML, vedere [XML Source](data-flow/xml-source.md).</span><span class="sxs-lookup"><span data-stu-id="f6401-104">For more information about the XML source, see [XML Source](data-flow/xml-source.md).</span></span>  
  
## <a name="static-options"></a><span data-ttu-id="f6401-105">Opzioni statiche</span><span class="sxs-lookup"><span data-stu-id="f6401-105">Static Options</span></span>  
 <span data-ttu-id="f6401-106">**Modalità di accesso ai dati**</span><span class="sxs-lookup"><span data-stu-id="f6401-106">**Data access mode**</span></span>  
 <span data-ttu-id="f6401-107">Consente di specificare il metodo per la selezione dei dati dall'origine.</span><span class="sxs-lookup"><span data-stu-id="f6401-107">Specify the method for selecting data from the source.</span></span>  
  
|<span data-ttu-id="f6401-108">Valore</span><span class="sxs-lookup"><span data-stu-id="f6401-108">Value</span></span>|<span data-ttu-id="f6401-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f6401-109">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="f6401-110">Percorso file XML</span><span class="sxs-lookup"><span data-stu-id="f6401-110">XML file location</span></span>|<span data-ttu-id="f6401-111">Consente di recuperare i dati da un file XML.</span><span class="sxs-lookup"><span data-stu-id="f6401-111">Retrieve data from an XML file.</span></span>|  
|<span data-ttu-id="f6401-112">File XML da variabile</span><span class="sxs-lookup"><span data-stu-id="f6401-112">XML file from variable</span></span>|<span data-ttu-id="f6401-113">Consente di specificare il nome del file XML in una variabile.</span><span class="sxs-lookup"><span data-stu-id="f6401-113">Specify the XML file name in a variable.</span></span><br /><br /> <span data-ttu-id="f6401-114">**Informazioni correlate**: [Uso di variabili nei pacchetti](../../2014/integration-services/use-variables-in-packages.md)</span><span class="sxs-lookup"><span data-stu-id="f6401-114">**Related information**: [Use Variables in Packages](../../2014/integration-services/use-variables-in-packages.md)</span></span>|  
|<span data-ttu-id="f6401-115">Dati XML da variabile</span><span class="sxs-lookup"><span data-stu-id="f6401-115">XML data from variable</span></span>|<span data-ttu-id="f6401-116">Consente di recuperare i dati XML da una variabile.</span><span class="sxs-lookup"><span data-stu-id="f6401-116">Retrieve XML data from a variable.</span></span>|  
  
 <span data-ttu-id="f6401-117">**Usa schema inline**</span><span class="sxs-lookup"><span data-stu-id="f6401-117">**Use inline schema**</span></span>  
 <span data-ttu-id="f6401-118">Consente di specificare se i dati di origine XML contengono lo schema XSD che ne definisce e ne convalida la struttura e i dati.</span><span class="sxs-lookup"><span data-stu-id="f6401-118">Specify whether the XML source data itself contains the XSD schema that defines and validates its structure and data.</span></span>  
  
 <span data-ttu-id="f6401-119">**Percorso XSD**</span><span class="sxs-lookup"><span data-stu-id="f6401-119">**XSD location**</span></span>  
 <span data-ttu-id="f6401-120">Consente di digitare il percorso e il nome del file dello schema XSD o di individuare il file selezionando **Sfoglia**.</span><span class="sxs-lookup"><span data-stu-id="f6401-120">Type the path and file name of the XSD schema file, or locate the file by clicking **Browse**.</span></span>  
  
 <span data-ttu-id="f6401-121">**Sfoglia**</span><span class="sxs-lookup"><span data-stu-id="f6401-121">**Browse**</span></span>  
 <span data-ttu-id="f6401-122">Usare la finestra di dialogo **Apri** per individuare il file di schema XSD.</span><span class="sxs-lookup"><span data-stu-id="f6401-122">Use the **Open** dialog box to locate the XSD schema file.</span></span>  
  
 <span data-ttu-id="f6401-123">**Genera XSD**</span><span class="sxs-lookup"><span data-stu-id="f6401-123">**Generate XSD**</span></span>  
 <span data-ttu-id="f6401-124">Usare la finestra di dialogo **Salva con nome** per selezionare un percorso per il file di schema XSD creato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="f6401-124">Use the **Save As** dialog box to select a location for the auto-generated XSD schema file.</span></span> <span data-ttu-id="f6401-125">L'editor deduce lo schema dalla struttura dei dati XML.</span><span class="sxs-lookup"><span data-stu-id="f6401-125">The editor infers the schema from the structure of the XML data.</span></span>  
  
## <a name="data-access-mode-dynamic-options"></a><span data-ttu-id="f6401-126">Opzioni dinamiche relative alla modalità di accesso ai dati</span><span class="sxs-lookup"><span data-stu-id="f6401-126">Data Access Mode Dynamic Options</span></span>  
  
### <a name="data-access-mode--xml-file-location"></a><span data-ttu-id="f6401-127">Modalità di accesso ai dati = Percorso file XML</span><span class="sxs-lookup"><span data-stu-id="f6401-127">Data access mode = XML file location</span></span>  
 <span data-ttu-id="f6401-128">**Percorso XML**</span><span class="sxs-lookup"><span data-stu-id="f6401-128">**XML location**</span></span>  
 <span data-ttu-id="f6401-129">Consente di digitare il percorso e il nome del file di dati XML o di individuare il file scegliendo **Sfoglia**.</span><span class="sxs-lookup"><span data-stu-id="f6401-129">Type the path and file name of the XML data file, or locate the file by clicking **Browse**.</span></span>  
  
 <span data-ttu-id="f6401-130">**Sfoglia**</span><span class="sxs-lookup"><span data-stu-id="f6401-130">**Browse**</span></span>  
 <span data-ttu-id="f6401-131">Usare la finestra di dialogo **Apri** per individuare il file di dati XML.</span><span class="sxs-lookup"><span data-stu-id="f6401-131">Use the **Open** dialog box to locate the XML data file.</span></span>  
  
### <a name="data-access-mode--xml-file-from-variable"></a><span data-ttu-id="f6401-132">Modalità di accesso ai dati = File XML da variabile</span><span class="sxs-lookup"><span data-stu-id="f6401-132">Data access mode = XML file from variable</span></span>  
 <span data-ttu-id="f6401-133">**Nome variabile**</span><span class="sxs-lookup"><span data-stu-id="f6401-133">**Variable name**</span></span>  
 <span data-ttu-id="f6401-134">Consente di selezionare la variabile contenente il percorso e il nome del file XML.</span><span class="sxs-lookup"><span data-stu-id="f6401-134">Select the variable that contains the path and file name of the XML file.</span></span>  
  
### <a name="data-access-mode--xml-data-from-variable"></a><span data-ttu-id="f6401-135">Modalità di accesso ai dati = Dati XML da variabile</span><span class="sxs-lookup"><span data-stu-id="f6401-135">Data access mode = XML data from variable</span></span>  
 <span data-ttu-id="f6401-136">**Nome variabile**</span><span class="sxs-lookup"><span data-stu-id="f6401-136">**Variable name**</span></span>  
 <span data-ttu-id="f6401-137">Consente di selezionare la variabile contenente i dati XML.</span><span class="sxs-lookup"><span data-stu-id="f6401-137">Select the variable that contains the XML data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6401-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f6401-138">See Also</span></span>  
 <span data-ttu-id="f6401-139">[Guida di riferimento ai messaggi e agli errori di Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="f6401-139">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="f6401-140">[Editor origine XML &#40;pagina colonne&#41;](../../2014/integration-services/xml-source-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="f6401-140">[XML Source Editor &#40;Columns Page&#41;](../../2014/integration-services/xml-source-editor-columns-page.md) </span></span>  
 <span data-ttu-id="f6401-141">[Editor origine XML &#40;pagina output degli errori&#41;](../../2014/integration-services/xml-source-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="f6401-141">[XML Source Editor &#40;Error Output Page&#41;](../../2014/integration-services/xml-source-editor-error-output-page.md) </span></span>  
 [<span data-ttu-id="f6401-142">Estrazione dei dati tramite l'origine XML</span><span class="sxs-lookup"><span data-stu-id="f6401-142">Extract Data by Using the XML Source</span></span>](data-flow/extract-data-by-using-the-xml-source.md)  
  
  
