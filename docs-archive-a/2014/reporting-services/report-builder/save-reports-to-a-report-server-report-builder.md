---
title: Salvare i report in un server di report (Generatore report) | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 48dfef01-ed8c-4f23-90c3-de67c90a97dd
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d80e35c447593e89d422e72ea31ec6be34c3619f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723516"
---
# <a name="save-reports-to-a-report-server-report-builder"></a><span data-ttu-id="df0c9-102">Salvare i report in un server di report (Generatore report)</span><span class="sxs-lookup"><span data-stu-id="df0c9-102">Save Reports to a Report Server (Report Builder)</span></span>
  <span data-ttu-id="df0c9-103">In Generatore report è possibile salvare una definizione del report in un server di report, operazione anche nota come pubblicazione di un report.</span><span class="sxs-lookup"><span data-stu-id="df0c9-103">In Report Builder, you can save a report definition to a report server (also known as publishing a report).</span></span> <span data-ttu-id="df0c9-104">Quando viene salvato in un server di report, il report può essere visualizzato anche da altri utenti.</span><span class="sxs-lookup"><span data-stu-id="df0c9-104">When the report is saved to a report server, other users can view the report.</span></span> <span data-ttu-id="df0c9-105">Ogni volta che si esegue il report pubblicato, verranno recuperati i dati più recenti.</span><span class="sxs-lookup"><span data-stu-id="df0c9-105">Each time you run the published report, you will retrieve the most current data.</span></span> <span data-ttu-id="df0c9-106">Per salvare una copia statica di un report visualizzabile, esportare il report in un formato di file diverso e salvarlo o utilizzare la caratteristica di cronologia dei report per salvare versioni di report visualizzabili.</span><span class="sxs-lookup"><span data-stu-id="df0c9-106">To save a static copy of a rendered report, export the report to a different file format and save it or use the report history feature to save versions of rendered reports.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="df0c9-107">Il percorso della definizione del report salvata non determina il tipo di elaborazione del report, sul server o in locale, quando il report viene visualizzato in anteprima.</span><span class="sxs-lookup"><span data-stu-id="df0c9-107">The location of the saved report definition does not affect whether the report is processed on the server or processed locally when you preview the report.</span></span>  
  
### <a name="to-save-a-report-to-a-report-server"></a><span data-ttu-id="df0c9-108">Per salvare un report in un server di report</span><span class="sxs-lookup"><span data-stu-id="df0c9-108">To save a report to a report server</span></span>  
  
1.  <span data-ttu-id="df0c9-109">Dal pulsante Generatore report fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="df0c9-109">From the Report Builder button, click **Save**.</span></span> <span data-ttu-id="df0c9-110">Verrà visualizzata la finestra **di dialogo Salva con nome** _\<Report Item\>_ .</span><span class="sxs-lookup"><span data-stu-id="df0c9-110">The **Save As**_\<Report Item\>_ dialog box opens.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="df0c9-111">Se si sta salvando di nuovo un report, questo viene automaticamente risalvato nel relativo percorso precedente.</span><span class="sxs-lookup"><span data-stu-id="df0c9-111">If you are resaving a report, it is automatically resaved to its previous location.</span></span> <span data-ttu-id="df0c9-112">Utilizzare l'opzione Salva con nome per modificare il percorso.</span><span class="sxs-lookup"><span data-stu-id="df0c9-112">Use the Save As option to change location.</span></span>  
  
2.  <span data-ttu-id="df0c9-113">Facoltativamente, fare clic su **Siti e server recenti** per visualizzare un elenco di server di report e di siti di SharePoint usati di recente.</span><span class="sxs-lookup"><span data-stu-id="df0c9-113">Optionally, click **Recent Sites and Servers** to show a list of recently used report servers and SharePoint sites.</span></span>  
  
3.  <span data-ttu-id="df0c9-114">Selezionare il percorso nel server di report in cui si desidera salvare il report.</span><span class="sxs-lookup"><span data-stu-id="df0c9-114">Browse to the report server location where you want to save the report.</span></span>  
  
4.  <span data-ttu-id="df0c9-115">In **Nome**digitare il nome del report.</span><span class="sxs-lookup"><span data-stu-id="df0c9-115">In **Name**, type the name of the report.</span></span>  
  
5.  <span data-ttu-id="df0c9-116">In **Elementi di tipo**selezionare il tipo di elemento del report da salvare.</span><span class="sxs-lookup"><span data-stu-id="df0c9-116">In **Items of type**, select the type of report item you are saving.</span></span> <span data-ttu-id="df0c9-117">Il tipo per i report è Report (\* .rdl).</span><span class="sxs-lookup"><span data-stu-id="df0c9-117">The type for reports is Reports(\*.rdl).</span></span>  
  
### <a name="to-save-a-report-as-a-different-name"></a><span data-ttu-id="df0c9-118">Per salvare un report con un altro nome</span><span class="sxs-lookup"><span data-stu-id="df0c9-118">To save a report as a different name</span></span>  
  
1.  <span data-ttu-id="df0c9-119">Fare clic sul pulsante Generatore report , quindi su **Salva con nome**.</span><span class="sxs-lookup"><span data-stu-id="df0c9-119">From the Report Builder button, click **Save As**.</span></span> <span data-ttu-id="df0c9-120">Verrà visualizzata la finestra **di dialogo Salva con nome** _\<Report Item\>_ .</span><span class="sxs-lookup"><span data-stu-id="df0c9-120">The **Save As**_\<Report Item\>_ dialog box opens.</span></span>  
  
2.  <span data-ttu-id="df0c9-121">Passare al percorso del server di report o alla condivisione file in cui si desidera salvare il report.</span><span class="sxs-lookup"><span data-stu-id="df0c9-121">Browse to the report server location or to the file share where you want to save the report.</span></span>  
  
3.  <span data-ttu-id="df0c9-122">In **Nome**digitare il nome del report.</span><span class="sxs-lookup"><span data-stu-id="df0c9-122">In **Name**, type the name of the report.</span></span>  
  
4.  <span data-ttu-id="df0c9-123">In **Elementi di tipo**selezionare il tipo di elemento del report da salvare.</span><span class="sxs-lookup"><span data-stu-id="df0c9-123">In **Items of type**, select the type of report item you are saving.</span></span> <span data-ttu-id="df0c9-124">Il tipo per i report è Report (\* .rdl).</span><span class="sxs-lookup"><span data-stu-id="df0c9-124">The type for reports is Reports(\*.rdl).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df0c9-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="df0c9-125">See Also</span></span>  
 <span data-ttu-id="df0c9-126">[Ricerca, visualizzazione e gestione dei report &#40;Generatore report e SSRS &#41;](finding-viewing-and-managing-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="df0c9-126">[Finding, Viewing, and Managing Reports &#40;Report Builder and SSRS &#41;](finding-viewing-and-managing-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="df0c9-127">[Esportazione di report &#40;Generatore report e SSRS&#41;](export-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="df0c9-127">[Exporting Reports &#40;Report Builder and SSRS&#41;](export-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="df0c9-128">[Salvataggio dei report &#40;Generatore report&#41;](saving-reports-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="df0c9-128">[Saving Reports &#40;Report Builder&#41;](saving-reports-report-builder.md) </span></span>  
 [<span data-ttu-id="df0c9-129">Esportare un report in un altro tipo di file &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="df0c9-129">Export a Report as Another File Type &#40;Report Builder and SSRS&#41;</span></span>](../export-a-report-as-another-file-type-report-builder-and-ssrs.md)  
  
  
