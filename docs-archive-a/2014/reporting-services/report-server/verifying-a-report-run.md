---
title: Verifica dell'esecuzione di un report | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- auditing [Reporting Services]
- verifying report execution
- logs [Reporting Services], verifying report run
- report execution data [Reporting Services]
- status information [Reporting Services]
- report processing [Reporting Services], verifying execution
- checking report execution
ms.assetid: 18a98f2f-6b40-454e-9b37-568ed1a96458
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c11c57f7c5f67b2557f5637ad10658abc9f80606
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628320"
---
# <a name="verifying-a-report-run"></a><span data-ttu-id="3ef84-102">Verifica dell'esecuzione di un report</span><span class="sxs-lookup"><span data-stu-id="3ef84-102">Verifying a Report Run</span></span>
  <span data-ttu-id="3ef84-103">Per visualizzare informazioni sullo stato di elaborazione di un report, è possibile utilizzare i file di log oppure controllare le informazioni sullo stato visualizzate con il report in Gestione report.</span><span class="sxs-lookup"><span data-stu-id="3ef84-103">To view information about the status of report processing, you can use log files or refer to status information that is displayed with the report in Report Manager.</span></span>  
  
## <a name="sources-of-report-execution-data"></a><span data-ttu-id="3ef84-104">Origini dei dati per l'esecuzione del report</span><span class="sxs-lookup"><span data-stu-id="3ef84-104">Sources of Report Execution Data</span></span>  
 <span data-ttu-id="3ef84-105">I log di esecuzione di un report contengono tutte le informazioni sull'esecuzione del report, tra cui il nome del report, il nome dell'utente che lo ha eseguito, la data e l'ora di esecuzione e l'estensione per il recapito utilizzata per distribuire il report.</span><span class="sxs-lookup"><span data-stu-id="3ef84-105">The report execution logs provide comprehensive information about report execution, including the name of the report, the name of the user who ran the report, report execution time, and the delivery extension used to distribute the report.</span></span> <span data-ttu-id="3ef84-106">Per visualizzare e analizzare questi dati, è possibile copiare il log di esecuzione del report in tabelle di database, in modo che sia più semplice eseguire query e creare report sui dati di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="3ef84-106">To view and analyze this data, you can copy the report execution log into database tables that are easy to query and report on.</span></span>  
  
 <span data-ttu-id="3ef84-107">I file di log contengono numerose voci sull'esecuzione dei report e su altre attività del server.</span><span class="sxs-lookup"><span data-stu-id="3ef84-107">Log files contain many entries about report execution and other server activity.</span></span> <span data-ttu-id="3ef84-108">Dato che i file di log contengono una così grande quantità di dati, è consigliabile utilizzare Gestione report se si desidera verificare unicamente quando è avvenuta l'ultima esecuzione del report.</span><span class="sxs-lookup"><span data-stu-id="3ef84-108">Because log files contain so much data, you may want to use Report Manager if you only want to verify when the report last ran.</span></span> <span data-ttu-id="3ef84-109">Se sono necessarie informazioni aggiuntive, è necessario visualizzare i file di log.</span><span class="sxs-lookup"><span data-stu-id="3ef84-109">If you require additional information, you must view the log files.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3ef84-110">In Gestione report non vengono visualizzate la data e l'ora di elaborazione dei report eseguiti su richiesta.</span><span class="sxs-lookup"><span data-stu-id="3ef84-110">Report Manager does not show the processing times of reports that run on demand.</span></span>  
  
 <span data-ttu-id="3ef84-111">Nella tabella seguente viene descritto come visualizzare la data e l'ora di elaborazione per vari tipi di report.</span><span class="sxs-lookup"><span data-stu-id="3ef84-111">The following table describes how to view the processing date and time for various types of reports.</span></span>  
  
|<span data-ttu-id="3ef84-112">Tipo di report</span><span class="sxs-lookup"><span data-stu-id="3ef84-112">For this type of report</span></span>|<span data-ttu-id="3ef84-113">Posizione delle informazioni sulla data e l'ora</span><span class="sxs-lookup"><span data-stu-id="3ef84-113">Date and time information is located here</span></span>|<span data-ttu-id="3ef84-114">Operazioni da eseguire per visualizzare le informazioni</span><span class="sxs-lookup"><span data-stu-id="3ef84-114">To view the information, do the following</span></span>|  
|-----------------------------|-----------------------------------------------|-----------------------------------------------|  
|<span data-ttu-id="3ef84-115">Report che viene eseguito come snapshot del report</span><span class="sxs-lookup"><span data-stu-id="3ef84-115">A report that runs as a report snapshot.</span></span>|<span data-ttu-id="3ef84-116">Pagina Contenuto.</span><span class="sxs-lookup"><span data-stu-id="3ef84-116">On the Contents page.</span></span> <span data-ttu-id="3ef84-117">Per altre informazioni, vedere [Pagina Contenuto &#40;Gestione report&#41;](../contents-page-report-manager.md).</span><span class="sxs-lookup"><span data-stu-id="3ef84-117">For more information, see [Contents Page &#40;Report Manager&#41;](../contents-page-report-manager.md).</span></span>|<span data-ttu-id="3ef84-118">1) Individuare la cartella che contiene il report.</span><span class="sxs-lookup"><span data-stu-id="3ef84-118">1) Locate the folder that contains the report.</span></span><br /><span data-ttu-id="3ef84-119">2) Impostare la visualizzazione Dettagli per la cartella.</span><span class="sxs-lookup"><span data-stu-id="3ef84-119">2) Set the folder in Details view.</span></span><br /><span data-ttu-id="3ef84-120">3) 3) prendere nota della data e dell'ora della colonna **durante l'esecuzione** .</span><span class="sxs-lookup"><span data-stu-id="3ef84-120">3) 3) Note the date and time in the **When Run** column.</span></span>|  
|<span data-ttu-id="3ef84-121">Snapshot della cronologia del report</span><span class="sxs-lookup"><span data-stu-id="3ef84-121">A snapshot in report history.</span></span>|<span data-ttu-id="3ef84-122">Pagina delle proprietà Cronologia.</span><span class="sxs-lookup"><span data-stu-id="3ef84-122">On the History Properties page.</span></span> <span data-ttu-id="3ef84-123">Per altre informazioni, vedere [Pagina delle proprietà Opzioni snapshot &#40;Gestione report&#41;](../snapshot-options-properties-page-report-manager.md).</span><span class="sxs-lookup"><span data-stu-id="3ef84-123">For more information, see [Snapshot Options Properties Page &#40;Report Manager&#41;](../snapshot-options-properties-page-report-manager.md).</span></span>|<span data-ttu-id="3ef84-124">1) Aprire il report.</span><span class="sxs-lookup"><span data-stu-id="3ef84-124">1) Open the report.</span></span><br /><span data-ttu-id="3ef84-125">2) Fare clic sulla pagina **Proprietà** .</span><span class="sxs-lookup"><span data-stu-id="3ef84-125">2) Click the **Properties** page.</span></span><br /><span data-ttu-id="3ef84-126">3) Fare clic sulla scheda **Cronologia** .</span><span class="sxs-lookup"><span data-stu-id="3ef84-126">3) Click the **History** tab.</span></span><br /><span data-ttu-id="3ef84-127">4) Osservare data e ora nella colonna **Data ultima esecuzione** .</span><span class="sxs-lookup"><span data-stu-id="3ef84-127">4) Note the date and time in the **When Run** column.</span></span>|  
|<span data-ttu-id="3ef84-128">Report memorizzato nella cache</span><span class="sxs-lookup"><span data-stu-id="3ef84-128">A cached report.</span></span>|<span data-ttu-id="3ef84-129">Pianificazione utilizzata per creare e aggiornare il report memorizzato nella cache.</span><span class="sxs-lookup"><span data-stu-id="3ef84-129">In the schedule used to create and refresh the cached report.</span></span>|<span data-ttu-id="3ef84-130">1) Aprire il report.</span><span class="sxs-lookup"><span data-stu-id="3ef84-130">1) Open the report.</span></span><br /><span data-ttu-id="3ef84-131">2) Fare clic sulla pagina **Proprietà** .</span><span class="sxs-lookup"><span data-stu-id="3ef84-131">2) Click the **Properties** page.</span></span><br /><span data-ttu-id="3ef84-132">3) Fare clic sulla scheda **Esecuzione** .</span><span class="sxs-lookup"><span data-stu-id="3ef84-132">3) Click the **Execution** tab.</span></span><br /><span data-ttu-id="3ef84-133">4) Aprire la pianificazione.</span><span class="sxs-lookup"><span data-stu-id="3ef84-133">4) Open the schedule.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3ef84-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3ef84-134">See Also</span></span>  
 <span data-ttu-id="3ef84-135">[File di log e origini di Reporting Services](../report-server/reporting-services-log-files-and-sources.md) </span><span class="sxs-lookup"><span data-stu-id="3ef84-135">[Reporting Services Log Files and Sources](../report-server/reporting-services-log-files-and-sources.md) </span></span>  
 <span data-ttu-id="3ef84-136">[Impostare proprietà di elaborazione dei report](set-report-processing-properties.md) </span><span class="sxs-lookup"><span data-stu-id="3ef84-136">[Set Report Processing Properties](set-report-processing-properties.md) </span></span>  
 [<span data-ttu-id="3ef84-137">Gestione report &#40;modalità nativa SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="3ef84-137">Report Manager  &#40;SSRS Native Mode&#41;</span></span>](../report-manager-ssrs-native-mode.md)  
  
  
