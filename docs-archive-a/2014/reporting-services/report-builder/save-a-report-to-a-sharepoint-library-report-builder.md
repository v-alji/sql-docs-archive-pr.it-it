---
title: Salvare un report in una raccolta di SharePoint (Report Builder) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 4daa1eee-78b7-43d0-8b22-4a98e8fa66ba
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 49878a0d7115a11e804382cb5139aa0ec7b3d254
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628481"
---
# <a name="save-a-report-to-a-sharepoint-library-report-builder"></a><span data-ttu-id="24417-102">Salvataggio di un report in una raccolta di SharePoint (Generatore report)</span><span class="sxs-lookup"><span data-stu-id="24417-102">Save a Report to a SharePoint Library (Report Builder)</span></span>
  <span data-ttu-id="24417-103">Per salvare un report in un server di report configurato per l'integrazione con SharePoint, è necessario accedere al server di SharePoint e stabilire una connessione con il server di report.</span><span class="sxs-lookup"><span data-stu-id="24417-103">To save a report to a report server configured for SharePoint integration, you must browse to the SharePoint server and establish a connection to the report server.</span></span> <span data-ttu-id="24417-104">Nella definizione del report tutti i riferimenti a elementi correlati al report devono utilizzare valori specifici di un server di report di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="24417-104">In the report definition, all references to items related to the report must use values that are specific to a SharePoint report server.</span></span> <span data-ttu-id="24417-105">Tra gli elementi correlati sono inclusi sottoreport, report drill-through e risorse quali immagini basate sul Web.</span><span class="sxs-lookup"><span data-stu-id="24417-105">Related items include subreports, drillthrough reports, and resources such as Web-based images.</span></span> <span data-ttu-id="24417-106">Per altre informazioni, vedere [Specifica di percorsi di elementi esterni &#40;Generatore report e SSRS&#41;](../report-design/specifying-paths-to-external-items-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="24417-106">For more information, see [Specifying Paths to External Items &#40;Report Builder and SSRS&#41;](../report-design/specifying-paths-to-external-items-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="24417-107">Per impostare le proprietà del progetto, è necessario disporre dell'autorizzazione **Membro** o **Proprietario** per il sito di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="24417-107">You must have **Member** or **Owner** permission on the SharePoint site to set the properties on the project.</span></span>  
  
### <a name="to-save-a-report-to-a-sharepoint-site"></a><span data-ttu-id="24417-108">Per salvare un report in un sito di SharePoint</span><span class="sxs-lookup"><span data-stu-id="24417-108">To save a report to a SharePoint site</span></span>  
  
1.  <span data-ttu-id="24417-109">Dal pulsante Generatore report fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="24417-109">From the Report Builder button, click **Save**.</span></span> <span data-ttu-id="24417-110">Verrà visualizzata la finestra **di dialogo Salva con nome** _\<Report Item>_ .</span><span class="sxs-lookup"><span data-stu-id="24417-110">The **Save As**_\<Report Item>_ dialog box opens.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="24417-111">Se si sta salvando di nuovo un report, questo viene automaticamente risalvato nel relativo percorso precedente.</span><span class="sxs-lookup"><span data-stu-id="24417-111">If you are resaving a report, it is automatically resaved to its previous location.</span></span> <span data-ttu-id="24417-112">Usare l'opzione **Salva con nome** per modificare il percorso.</span><span class="sxs-lookup"><span data-stu-id="24417-112">Use the **Save As** option to change location.</span></span>  
  
2.  <span data-ttu-id="24417-113">Facoltativamente, fare clic su **Siti e server recenti** per visualizzare un elenco di server di report e di siti di SharePoint usati di recente.</span><span class="sxs-lookup"><span data-stu-id="24417-113">Optionally, click **Recent Sites and Servers** to show a list of recently used report servers and SharePoint sites.</span></span>  
  
3.  <span data-ttu-id="24417-114">Passare al sito di SharePoint, quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="24417-114">Browse to the SharePoint site, and then click **Save**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="24417-115">Se si lascia un report modificato per più di 10 ore senza salvarlo, questo viene disconnesso dal server senza essere salvato.</span><span class="sxs-lookup"><span data-stu-id="24417-115">If you leave a changed report for more than 10 hours without saving it, it is disconnected from the server without being saved.</span></span> <span data-ttu-id="24417-116">In questo caso, nella barra di stato in basso a destra fare clic su **Disconnetti**, quindi su **Connetti**.</span><span class="sxs-lookup"><span data-stu-id="24417-116">If that happens, in the lower-right status bar, click **Disconnect**, and then click **Connect**.</span></span> <span data-ttu-id="24417-117">Il server più recente si troverà nell'elenco di server disponibili.</span><span class="sxs-lookup"><span data-stu-id="24417-117">The most recent server will be in the list of available servers.</span></span> <span data-ttu-id="24417-118">Selezionarlo e il report verrà riconnesso.</span><span class="sxs-lookup"><span data-stu-id="24417-118">Select it and the report will reconnect.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24417-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="24417-119">See Also</span></span>  
 [<span data-ttu-id="24417-120">Ricerca, visualizzazione e gestione dei report &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="24417-120">Finding, Viewing, and Managing Reports &#40;Report Builder and SSRS &#41;</span></span>](finding-viewing-and-managing-reports-report-builder-and-ssrs.md)  
  
  
