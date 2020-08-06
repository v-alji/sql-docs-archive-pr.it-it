---
title: Aggiornamento di report mediante le classi generate dallo schema RDL (esercitazione su SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- RDL [Reporting Services], generating
- RDL [Reporting Services], tutorials
- RDL [Reporting Services], serializing
ms.assetid: 8f81d48f-7ab9-4ef8-bce0-7d16d9a47fbd
author: markingmyname
ms.author: maghan
manager: kfile
ms.openlocfilehash: f3972b8e1af6d50ccc6f5188c8f671fe333ebce8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625069"
---
# <a name="updating-reports-using-classes-generated-from-the-rdl-schema-ssrs-tutorial"></a><span data-ttu-id="37a59-102">Aggiornamento dei report mediante le classi generate dallo schema RDL (esercitazione SSRS)</span><span class="sxs-lookup"><span data-stu-id="37a59-102">Updating Reports Using Classes Generated from the RDL Schema (SSRS Tutorial)</span></span>
  <span data-ttu-id="37a59-103">In questa esercitazione viene illustrato come utilizzare lo strumento XML Schema Definition (Xsd.exe) per generare classi che consentono di serializzare e deserializzare i file di definizione dei report (con estensione rdl e rdlc) con la [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] <xref:System.Xml.Serialization.XmlSerializer> classe.</span><span class="sxs-lookup"><span data-stu-id="37a59-103">This tutorial illustrates how to use the XML Schema Definition Tool (Xsd.exe) to generate classes that allow you to serialize and deserialize report definition files (.rdl and .rdlc) with the [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] <xref:System.Xml.Serialization.XmlSerializer> class.</span></span>  
  
## <a name="what-you-will-learn"></a><span data-ttu-id="37a59-104">Lezioni dell'esercitazione</span><span class="sxs-lookup"><span data-stu-id="37a59-104">What You Will Learn</span></span>  
 <span data-ttu-id="37a59-105">Durante questa esercitazione verranno eseguite le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="37a59-105">During the course of this tutorial, you will complete the following activities:</span></span>  
  
-   <span data-ttu-id="37a59-106">Creare un'applicazione usando il [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] modello di progetto applicazione console.</span><span class="sxs-lookup"><span data-stu-id="37a59-106">Create an application using the [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] Console Application project template.</span></span>  
  
-   <span data-ttu-id="37a59-107">Generare classi dallo schema Report Definition Language (RDL) utilizzando lo strumento **xsd** .</span><span class="sxs-lookup"><span data-stu-id="37a59-107">Generate classes from the Report Definition Language (RDL) schema using the **xsd** tool.</span></span>  
  
-   <span data-ttu-id="37a59-108">Connessione a un server di report e recupero di una definizione del report.</span><span class="sxs-lookup"><span data-stu-id="37a59-108">Connect to a report server and retrieve a report definition.</span></span>  
  
-   <span data-ttu-id="37a59-109">Scrittura di codice per l'aggiornamento del file di definizione del report.</span><span class="sxs-lookup"><span data-stu-id="37a59-109">Write code to update the report definition file.</span></span>  
  
-   <span data-ttu-id="37a59-110">Salvataggio della definizione aggiornata del report nel server di report.</span><span class="sxs-lookup"><span data-stu-id="37a59-110">Save the updated report definition back to the report server.</span></span>  
  
-   <span data-ttu-id="37a59-111">Eseguire l'applicazione dello schema RDL (VB/C#).</span><span class="sxs-lookup"><span data-stu-id="37a59-111">Run the RDL Schema Application (VB/C#).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="37a59-112">Gli esempi di codice forniti in questa esercitazione potrebbero non funzionare per i report in cui non è disponibile alcuna descrizione.</span><span class="sxs-lookup"><span data-stu-id="37a59-112">The code samples provided in this tutorial might fail for reports having no description.</span></span> <span data-ttu-id="37a59-113">L'errore si verifica perché la proprietà di descrizione non è disponibile per i report privi di descrizione specificata.</span><span class="sxs-lookup"><span data-stu-id="37a59-113">The failure is because the description property does not exist for the reports with description not specified.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="37a59-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="37a59-114">Requirements</span></span>  
 <span data-ttu-id="37a59-115">Per eseguire l'esercitazione, occorre:</span><span class="sxs-lookup"><span data-stu-id="37a59-115">To complete the tutorial, you must have the following:</span></span>  
  
-   [!INCLUDE[msCoName](../includes/msconame-md.md)] <span data-ttu-id="37a59-116">[!INCLUDE[ssCurrentUI](../includes/sscurrentui-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="37a59-116">[!INCLUDE[ssCurrentUI](../includes/sscurrentui-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)].</span></span>  
  
-   [!INCLUDE[msCoName](../includes/msconame-md.md)] <span data-ttu-id="37a59-117">[!INCLUDE[vs_dev10_long](../includes/vs-dev10-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="37a59-117">[!INCLUDE[vs_dev10_long](../includes/vs-dev10-long-md.md)].</span></span>  
  
-   <span data-ttu-id="37a59-118">Autorizzazioni sufficienti per l'accesso al servizio Web ReportServer e la pubblicazione di report sul servizio nel computer in cui è installato il server di report.</span><span class="sxs-lookup"><span data-stu-id="37a59-118">Sufficient permissions to be able to access and publish reports to the Report Server Web service on the computer where your report server is located.</span></span>  
  
-   <span data-ttu-id="37a59-119">Il database di esempio [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] installato in un'istanza di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="37a59-119">The [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] sample database installed to an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="37a59-120">Un report installato nel server di report.</span><span class="sxs-lookup"><span data-stu-id="37a59-120">A report installed on your report server.</span></span> <span data-ttu-id="37a59-121">In questa esercitazione viene utilizzato il report di esempio Company Sales 2012.</span><span class="sxs-lookup"><span data-stu-id="37a59-121">This tutorial uses the sample report, Company Sales 2012.</span></span> <span data-ttu-id="37a59-122">Per ulteriori informazioni sui report di esempio, vedere [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889).</span><span class="sxs-lookup"><span data-stu-id="37a59-122">For more information about sample reports, see [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="37a59-123">Gli esempi non vengono installati automaticamente durante l'installazione, ma possono essere installati in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="37a59-123">The samples are not installed automatically during setup, but you can install them at any time.</span></span> <span data-ttu-id="37a59-124">Per informazioni sugli esempi, vedere [SQL Server Product Samples](https://go.microsoft.com/fwlink/?LinkId=182887).</span><span class="sxs-lookup"><span data-stu-id="37a59-124">For information about samples, see [SQL Server Product Samples](https://go.microsoft.com/fwlink/?LinkId=182887).</span></span>  
  
 <span data-ttu-id="37a59-125">**Tempo stimato per il completamento dell'esercitazione:** 30 minuti</span><span class="sxs-lookup"><span data-stu-id="37a59-125">**Estimated time to complete the tutorial:** 30 minutes</span></span>  
  
## <a name="tasks"></a><span data-ttu-id="37a59-126">Attività</span><span class="sxs-lookup"><span data-stu-id="37a59-126">Tasks</span></span>  
 [<span data-ttu-id="37a59-127">Lezione 1: Creare il progetto di Visual Studio per lo schema RDL</span><span class="sxs-lookup"><span data-stu-id="37a59-127">Lesson 1: Create the RDL Schema Visual Studio Project</span></span>](../../2014/tutorials/lesson-1-create-the-rdl-schema-visual-studio-project.md)  
  
 [<span data-ttu-id="37a59-128">Lezione 2: Generare classi dallo schema RDL con lo strumento xsd</span><span class="sxs-lookup"><span data-stu-id="37a59-128">Lesson 2: Generate Classes from the RDL Schema using the xsd Tool</span></span>](../../2014/tutorials/lesson-2-generate-classes-from-the-rdl-schema-using-the-xsd-tool.md)  
  
 [<span data-ttu-id="37a59-129">Lezione 3: Caricare la definizione di un report dal server di report</span><span class="sxs-lookup"><span data-stu-id="37a59-129">Lesson 3: Load a Report Definition from the Report Server</span></span>](../../2014/tutorials/lesson-3-load-a-report-definition-from-the-report-server.md)  
  
 [<span data-ttu-id="37a59-130">Lezione 4: Aggiornare la definizione del report a livello di programmazione</span><span class="sxs-lookup"><span data-stu-id="37a59-130">Lesson 4: Update the Report Definition Programmatically</span></span>](../../2014/tutorials/lesson-4-update-the-report-definition-programmatically.md)  
  
 [<span data-ttu-id="37a59-131">Lezione 5: Pubblicare la definizione del report nel server di report</span><span class="sxs-lookup"><span data-stu-id="37a59-131">Lesson 5: Publish the Report Definition to the Report Server</span></span>](../../2014/tutorials/lesson-5-publish-the-report-definition-to-the-report-server.md)  
  
 [<span data-ttu-id="37a59-132">Lezione 6: eseguire l'applicazione dello schema RDL &#40;VB-C&#35;&#41;</span><span class="sxs-lookup"><span data-stu-id="37a59-132">Lesson 6: Run the RDL Schema Application &#40;VB-C&#35;&#41;</span></span>](../../2014/tutorials/lesson-6-run-the-rdl-schema-application-vb-csharp.md)  
  
## <a name="see-also"></a><span data-ttu-id="37a59-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="37a59-133">See Also</span></span>  
 [<span data-ttu-id="37a59-134">Report Definition Language &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="37a59-134">Report Definition Language &#40;SSRS&#41;</span></span>](../reporting-services/reports/report-definition-language-ssrs.md)  
  
  
