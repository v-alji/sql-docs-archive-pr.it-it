---
title: Proprietà server (pagina Esecuzione) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.swb.reportserver.serverproperties.execution.f1
ms.assetid: 53b77db1-b013-4dac-82dd-30c0de276639
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f0ec8725a0cec9e15cb6d8402f8d654320c38471
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629719"
---
# <a name="server-properties-execution-page"></a><span data-ttu-id="41ea7-102">Proprietà server (pagina Esecuzione)</span><span class="sxs-lookup"><span data-stu-id="41ea7-102">Server Properties (Execution Page)</span></span>
  <span data-ttu-id="41ea7-103">Utilizzare questa pagina per impostare un valore di timeout per l'esecuzione dei report.</span><span class="sxs-lookup"><span data-stu-id="41ea7-103">Use this page to set a timeout value for report execution.</span></span> <span data-ttu-id="41ea7-104">Questo valore si applica a tutti i report elaborati dall'istanza del server di report corrente,</span><span class="sxs-lookup"><span data-stu-id="41ea7-104">This value applies to all reports that are processed by the current report server instance.</span></span> <span data-ttu-id="41ea7-105">ma è possibile modificarlo a livello di singolo report.</span><span class="sxs-lookup"><span data-stu-id="41ea7-105">You can override this value for individual reports.</span></span> <span data-ttu-id="41ea7-106">Il valore specificato deve essere appropriato per tutte le elaborazioni dei report nel server di report, nonché per l'elaborazione delle query nel server di database quando il server di report recupera i dati utilizzati nel report.</span><span class="sxs-lookup"><span data-stu-id="41ea7-106">The value you specify must accommodate all report processing that occurs on the report server, plus query processing performed on the database server when the report server retrieves data that is used in the report.</span></span>  
  
 <span data-ttu-id="41ea7-107">Per aprire questa pagina, avviare [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connettersi a un'istanza del server di report, fare clic con il pulsante destro del mouse sul nome del server di report e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="41ea7-107">To open this page, start [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to a report server instance, right-click the report server name, and select **Properties**.</span></span> <span data-ttu-id="41ea7-108">Fare clic su **Esecuzione** per aprire la pagina.</span><span class="sxs-lookup"><span data-stu-id="41ea7-108">Click **Execution** to open this page.</span></span>  
  
## <a name="options"></a><span data-ttu-id="41ea7-109">Opzioni</span><span class="sxs-lookup"><span data-stu-id="41ea7-109">Options</span></span>  
 <span data-ttu-id="41ea7-110">**Nessun timeout per l'esecuzione del report**</span><span class="sxs-lookup"><span data-stu-id="41ea7-110">**Do not timeout report execution**</span></span>  
 <span data-ttu-id="41ea7-111">Consente a un server di report di completare l'elaborazione del report senza alcun limite di tempo.</span><span class="sxs-lookup"><span data-stu-id="41ea7-111">Allow a report server unlimited time to complete report processing.</span></span>  
  
 <span data-ttu-id="41ea7-112">**La durata dell'esecuzione del report non può superare il numero di secondi seguente**</span><span class="sxs-lookup"><span data-stu-id="41ea7-112">**Limit report execution to the following number of seconds**</span></span>  
 <span data-ttu-id="41ea7-113">Imposta un vincolo di tempo per l'esecuzione del report.</span><span class="sxs-lookup"><span data-stu-id="41ea7-113">Set a time constraint on report execution.</span></span> <span data-ttu-id="41ea7-114">Il periodo di tempo viene calcolato dal momento della richiesta del report.</span><span class="sxs-lookup"><span data-stu-id="41ea7-114">The time period starts when the report is requested.</span></span> <span data-ttu-id="41ea7-115">Se il tempo scade prima del completamento dell'elaborazione del report, il processo e ogni query in-process verranno annullati nelle origini dei dati esterne.</span><span class="sxs-lookup"><span data-stu-id="41ea7-115">If the time period ends before the report is fully processed, the report server cancels the process and any in-process queries to external data sources.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41ea7-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="41ea7-116">See Also</span></span>  
 <span data-ttu-id="41ea7-117">[Impostare le proprietà di un server di report &#40;Management Studio&#41;](set-report-server-properties-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="41ea7-117">[Set Report Server Properties &#40;Management Studio&#41;](set-report-server-properties-management-studio.md) </span></span>  
 <span data-ttu-id="41ea7-118">[Eseguire la connessione a un server di report in Management Studio](connect-to-a-report-server-in-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="41ea7-118">[Connect to a Report Server in Management Studio](connect-to-a-report-server-in-management-studio.md) </span></span>  
 <span data-ttu-id="41ea7-119">[Impostare proprietà di elaborazione dei report](../report-server/set-report-processing-properties.md) </span><span class="sxs-lookup"><span data-stu-id="41ea7-119">[Set Report Processing Properties](../report-server/set-report-processing-properties.md) </span></span>  
 <span data-ttu-id="41ea7-120">[Impostazione dei valori di timeout per l'elaborazione di report e di set di dati condivisi &#40;SSRS&#41;](../report-server/setting-time-out-values-for-report-and-shared-dataset-processing-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="41ea7-120">[Setting Time-out Values for Report and Shared Dataset Processing &#40;SSRS&#41;](../report-server/setting-time-out-values-for-report-and-shared-dataset-processing-ssrs.md) </span></span>  
 [<span data-ttu-id="41ea7-121">Guida sensibile al contesto del server di report in Management Studio</span><span class="sxs-lookup"><span data-stu-id="41ea7-121">Report Server in Management Studio F1 Help</span></span>](report-server-in-management-studio-f1-help.md)  
  
  
