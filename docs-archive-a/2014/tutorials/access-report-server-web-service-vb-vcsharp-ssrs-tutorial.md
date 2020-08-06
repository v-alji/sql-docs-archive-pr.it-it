---
title: Accesso al servizio Web ReportServer utilizzando Visual Basic o Visual C# (esercitazione su SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
dev_langs:
- VB
helpviewer_keywords:
- walkthroughs [Reporting Services]
- Reporting Services, Web service
- Web service [Reporting Services], tutorials
ms.assetid: cf688163-4ac0-475b-b6dd-6f2f05b553c6
author: markingmyname
ms.author: maghan
manager: kfile
ms.openlocfilehash: 3dc2599b4fafe682d74089d637918e04db9ed219
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720562"
---
# <a name="accessing-the-report-server-web-service-using-visual-basic-or-visual-c-ssrs-tutorial"></a><span data-ttu-id="0e146-102">Accesso al servizio Web ReportServer con Visual Basic o Visual C# (esercitazione SSRS)</span><span class="sxs-lookup"><span data-stu-id="0e146-102">Accessing the Report Server Web Service Using Visual Basic or Visual C# (SSRS Tutorial)</span></span>
  <span data-ttu-id="0e146-103">Nell'esercitazione seguente viene illustrato come accedere al servizio Web ReportServer da un'applicazione creata con [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] o [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[csprcs](../includes/csprcs-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0e146-103">The following tutorial shows you how to access the Report Server Web service from an application created with [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] or [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[csprcs](../includes/csprcs-md.md)].</span></span>  
  
## <a name="what-you-will-learn"></a><span data-ttu-id="0e146-104">Lezioni dell'esercitazione</span><span class="sxs-lookup"><span data-stu-id="0e146-104">What You Will Learn</span></span>  
 <span data-ttu-id="0e146-105">Durante questa esercitazione verranno eseguite le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="0e146-105">During the course of this tutorial, you will complete the following:</span></span>  
  
-   <span data-ttu-id="0e146-106">Creare un'applicazione client usando il [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vs_dev10_long](../includes/vs-dev10-long-md.md)] modello di progetto applicazione console.</span><span class="sxs-lookup"><span data-stu-id="0e146-106">Create a client application using the [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vs_dev10_long](../includes/vs-dev10-long-md.md)] Console Application project template.</span></span>  
  
-   <span data-ttu-id="0e146-107">Aggiunta di un riferimento Web al servizio Web ReportServer.</span><span class="sxs-lookup"><span data-stu-id="0e146-107">Add a Web reference for the Report Server Web service.</span></span>  
  
-   <span data-ttu-id="0e146-108">Scrittura di codice per l'accesso al servizio Web.</span><span class="sxs-lookup"><span data-stu-id="0e146-108">Write code to access the Web service.</span></span>  
  
-   <span data-ttu-id="0e146-109">Esecuzione dell'applicazione console in modalità debug.</span><span class="sxs-lookup"><span data-stu-id="0e146-109">Run the console application in debug mode.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0e146-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0e146-110">Requirements</span></span>  
 <span data-ttu-id="0e146-111">Per eseguire l'esercitazione, occorre:</span><span class="sxs-lookup"><span data-stu-id="0e146-111">To complete the tutorial, you must have the following:</span></span>  
  
-   [!INCLUDE[msCoName](../includes/msconame-md.md)] <span data-ttu-id="0e146-112">[!INCLUDE[ssSQL11](../includes/sssql11-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0e146-112">[!INCLUDE[ssSQL11](../includes/sssql11-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)].</span></span>  
  
-   [!INCLUDE[msCoName](../includes/msconame-md.md)]<span data-ttu-id="0e146-113">[!INCLUDE[vs_dev10_long](../includes/vs-dev10-long-md.md)]o una simile [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] -strumento di sviluppo compatibile con.</span><span class="sxs-lookup"><span data-stu-id="0e146-113">[!INCLUDE[vs_dev10_long](../includes/vs-dev10-long-md.md)] or a similar [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)]-compatible development tool.</span></span>  
  
-   <span data-ttu-id="0e146-114">Autorizzazioni sufficienti per l'accesso al servizio Web ReportServer di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] nel computer in cui è installato il server di report.</span><span class="sxs-lookup"><span data-stu-id="0e146-114">Sufficient permissions to be able to access the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Report Server Web service on the computer where your report server is located.</span></span>  
  
-   <span data-ttu-id="0e146-115">Un report installato nel server di report.</span><span class="sxs-lookup"><span data-stu-id="0e146-115">A report installed on your report server.</span></span> <span data-ttu-id="0e146-116">In questa esercitazione viene utilizzato il report di esempio Company Sales.</span><span class="sxs-lookup"><span data-stu-id="0e146-116">This tutorial uses the sample report, Company Sales.</span></span> <span data-ttu-id="0e146-117">Per ulteriori informazioni sui report di esempio, vedere [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889).</span><span class="sxs-lookup"><span data-stu-id="0e146-117">For more information about sample reports, see [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0e146-118">Gli esempi non vengono installati automaticamente durante l'installazione, ma possono essere installati in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="0e146-118">The samples are not installed automatically during setup, but you can install them at any time.</span></span> <span data-ttu-id="0e146-119">Per informazioni sugli esempi, vedere [SQL Server Product Samples](https://go.microsoft.com/fwlink/?LinkId=182887).</span><span class="sxs-lookup"><span data-stu-id="0e146-119">For information about samples, see [SQL Server Product Samples](https://go.microsoft.com/fwlink/?LinkId=182887).</span></span>  
  
 <span data-ttu-id="0e146-120">**Tempo stimato per il completamento dell'esercitazione:** 60 minuti</span><span class="sxs-lookup"><span data-stu-id="0e146-120">**Estimated time to complete the tutorial:** 60 minutes</span></span>  
  
## <a name="tasks"></a><span data-ttu-id="0e146-121">Attività</span><span class="sxs-lookup"><span data-stu-id="0e146-121">Tasks</span></span>  
 [<span data-ttu-id="0e146-122">Lezione 1: Creazione del progetto client per il servizio Web</span><span class="sxs-lookup"><span data-stu-id="0e146-122">Lesson 1: Creating the Web Service Client Project</span></span>](../../2014/tutorials/lesson-1-creating-the-web-service-client-project.md)  
  
 [<span data-ttu-id="0e146-123">Lezione 2: Aggiunta di un riferimento Web</span><span class="sxs-lookup"><span data-stu-id="0e146-123">Lesson 2: Adding a Web Reference</span></span>](../../2014/tutorials/lesson-2-adding-a-web-reference.md)  
  
 [<span data-ttu-id="0e146-124">Lezione 3: Accesso al servizio Web</span><span class="sxs-lookup"><span data-stu-id="0e146-124">Lesson 3: Accessing the Web Service</span></span>](../../2014/tutorials/lesson-3-accessing-the-web-service.md)  
  
 [<span data-ttu-id="0e146-125">Lezione 4: esecuzione dell'applicazione &#40;VB-VC&#35;&#41;</span><span class="sxs-lookup"><span data-stu-id="0e146-125">Lesson 4: Running the Application &#40;VB-VC&#35;&#41;</span></span>](../../2014/tutorials/lesson-4-running-the-application-vb-vcsharp.md)  
  
  
