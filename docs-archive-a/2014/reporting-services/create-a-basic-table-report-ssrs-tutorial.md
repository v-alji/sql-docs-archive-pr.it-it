---
title: Creare un report tabella semplice (esercitazione su SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- walkthroughs [Reporting Services]
- tutorials [Reporting Services]
- reports [Reporting Services], creating
ms.assetid: 3b539b4b-26f2-4c0b-b506-80f175679a46
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 02e0f42869a3bfa88e0c6646fd447968c8ba3a10
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623051"
---
# <a name="create-a-basic-table-report-ssrs-tutorial"></a><span data-ttu-id="61c7d-102">Creare un report tabella semplice (esercitazione su SSRS)</span><span class="sxs-lookup"><span data-stu-id="61c7d-102">Create a Basic Table Report (SSRS Tutorial)</span></span>
  <span data-ttu-id="61c7d-103">Questa esercitazione è stata progettata per illustrare il processo di creazione di un report tabella semplice basato sul database [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] tramite Progettazione report.</span><span class="sxs-lookup"><span data-stu-id="61c7d-103">This tutorial is designed to help you create a basic table report based on the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] database using Report Designer.</span></span> <span data-ttu-id="61c7d-104">Per creare report è inoltre possibile utilizzare Generatore report o la Creazione guidata report.</span><span class="sxs-lookup"><span data-stu-id="61c7d-104">You can also use Report Builder or the Report Wizard to create reports.</span></span> <span data-ttu-id="61c7d-105">In questa esercitazione verranno illustrate le procedure per creare un progetto report, impostare le informazioni di connessione, definire una query, aggiungere un'area dati tabella, raggruppare alcuni campi e aggiungere totali, nonché visualizzare il report in anteprima.</span><span class="sxs-lookup"><span data-stu-id="61c7d-105">In this tutorial, you will create a report project, set up connection information, define a query, add a Table data region, group and total some fields, and preview the report.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="61c7d-106">Per completare l'esercitazione, è necessario eseguire [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] in modalità nativa.</span><span class="sxs-lookup"><span data-stu-id="61c7d-106">To complete this tutorial, you must be running [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] in native mode.</span></span> <span data-ttu-id="61c7d-107">Se [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] è eseguito in modalità di integrazione con SharePoint, i passaggi in cui verranno utilizzati URL di server di report non possono essere completati correttamente.</span><span class="sxs-lookup"><span data-stu-id="61c7d-107">If you are running [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] in SharePoint integrated mode, the steps that use report server URLs do not work.</span></span> <span data-ttu-id="61c7d-108">Per ulteriori informazioni sulle [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] modalità, vedere [Reporting Services server di report](reporting-services-report-server.md).</span><span class="sxs-lookup"><span data-stu-id="61c7d-108">For more information about [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] modes, see [Reporting Services Report Server](reporting-services-report-server.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="61c7d-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="61c7d-109">Requirements</span></span>  
 <span data-ttu-id="61c7d-110">Per utilizzare l'esercitazione è necessario che nel sistema siano installati i componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="61c7d-110">Your system must have the following installed to use this tutorial:</span></span>  
  
-   [!INCLUDE[msCoName](../includes/msconame-md.md)]<span data-ttu-id="61c7d-111">[!INCLUDE[ssCurrent](../includes/sscurrent-md.md)]motore di database.</span><span class="sxs-lookup"><span data-stu-id="61c7d-111">[!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] database engine.</span></span>  
  
-   <span data-ttu-id="61c7d-112">Database [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="61c7d-112">The [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] database.</span></span>  <span data-ttu-id="61c7d-113">Per ulteriori informazioni, vedere [Adventure Works per SQL Server 2012 (Adventure Works per SQL Server 2012)](https://go.microsoft.com/fwlink/?LinkId=245471) ( https://go.microsoft.com/fwlink/?LinkId=245471). .</span><span class="sxs-lookup"><span data-stu-id="61c7d-113">For more information, see [Adventure Works for SQL Server 2012 (Adventure Works for SQL Server 2012)](https://go.microsoft.com/fwlink/?LinkId=245471) (https://go.microsoft.com/fwlink/?LinkId=245471)..</span></span> <span data-ttu-id="61c7d-114">Per ulteriori informazioni sul supporto per i [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] database di esempio e il codice di esempio per [!INCLUDE[ssExpress](../includes/ssexpress-md.md)] , vedere [Cenni preliminari sui database e sugli esempi](https://go.microsoft.com/fwlink/?LinkId=110391) nel sito Web CodePlex.</span><span class="sxs-lookup"><span data-stu-id="61c7d-114">For more information about support for [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] sample databases and sample code for [!INCLUDE[ssExpress](../includes/ssexpress-md.md)], see [Databases and Samples Overview](https://go.microsoft.com/fwlink/?LinkId=110391) on the CodePlex Web site.</span></span>  
  
-   [!INCLUDE[ssRSCurrent](../includes/ssrscurrent-md.md)]<span data-ttu-id="61c7d-115">.</span><span class="sxs-lookup"><span data-stu-id="61c7d-115">.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] <span data-ttu-id="61c7d-116">[!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="61c7d-116">[!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
    > [!NOTE]  
    >  [!INCLUDE[ssNote64Samp](../includes/ssnote64samp-md.md)]  
  
 <span data-ttu-id="61c7d-117">Per il recupero dei dati dal database [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] è anche necessario avere autorizzazioni di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="61c7d-117">You must also have read-only permissions to retrieve data from the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] database.</span></span>  
  
## <a name="tasks"></a><span data-ttu-id="61c7d-118">Attività</span><span class="sxs-lookup"><span data-stu-id="61c7d-118">Tasks</span></span>  
 [<span data-ttu-id="61c7d-119">Lezione 1: Creazione di un progetto server report &#40;Reporting Services&#41;</span><span class="sxs-lookup"><span data-stu-id="61c7d-119">Lesson 1: Creating a Report Server Project &#40;Reporting Services&#41;</span></span>](lesson-1-creating-a-report-server-project-reporting-services.md)  
  
 [<span data-ttu-id="61c7d-120">Lezione 2: Specifica delle informazioni di connessione &#40;Reporting Services&#41;</span><span class="sxs-lookup"><span data-stu-id="61c7d-120">Lesson 2: Specifying Connection Information &#40;Reporting Services&#41;</span></span>](lesson-2-specifying-connection-information-reporting-services.md)  
  
 [<span data-ttu-id="61c7d-121">Lezione 3: Definizione di un set di dati per il report tabella &#40;Reporting Services&#41;</span><span class="sxs-lookup"><span data-stu-id="61c7d-121">Lesson 3: Defining a Dataset for the Table Report &#40;Reporting Services&#41;</span></span>](lesson-3-defining-a-dataset-for-the-table-report-reporting-services.md)  
  
 [<span data-ttu-id="61c7d-122">Lezione 4: Aggiunta di una tabella al report &#40;Reporting Services&#41;</span><span class="sxs-lookup"><span data-stu-id="61c7d-122">Lesson 4: Adding a Table to the Report &#40;Reporting Services&#41;</span></span>](lesson-4-adding-a-table-to-the-report-reporting-services.md)  
  
 [<span data-ttu-id="61c7d-123">Lezione 5: Formattazione di un report &#40;Reporting Services&#41;</span><span class="sxs-lookup"><span data-stu-id="61c7d-123">Lesson 5: Formatting a Report &#40;Reporting Services&#41;</span></span>](lesson-5-formatting-a-report-reporting-services.md)  
  
 [<span data-ttu-id="61c7d-124">Lezione 6: Aggiunta di gruppi e totali &#40;Reporting Services&#41;</span><span class="sxs-lookup"><span data-stu-id="61c7d-124">Lesson 6: Adding Grouping and Totals &#40;Reporting Services&#41;</span></span>](lesson-6-adding-grouping-and-totals-reporting-services.md)  
  
> [!NOTE]  
>  <span data-ttu-id="61c7d-125">Quando si esaminano le esercitazioni, è consigliabile aggiungere pulsanti **Avanti** e **indietro** alla barra degli strumenti del Visualizzatore di documenti.</span><span class="sxs-lookup"><span data-stu-id="61c7d-125">When reviewing tutorials, we recommend that you add **Next** and **Previous** buttons to the document viewer toolbar.</span></span> <span data-ttu-id="61c7d-126">Per altre informazioni, vedere</span><span class="sxs-lookup"><span data-stu-id="61c7d-126">For more information, see.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61c7d-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="61c7d-127">See Also</span></span>  
 [<span data-ttu-id="61c7d-128">Esercitazioni su Reporting Services &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="61c7d-128">Reporting Services Tutorials &#40;SSRS&#41;</span></span>](reporting-services-tutorials-ssrs.md)  
  
  
