---
title: Usare sottoscrizioni personali | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- subscriptions [Reporting Services], My Subscriptions page
- My Subscriptions page [Reporting Services]
ms.assetid: e96623ba-677e-4748-8787-f32bed3b5c12
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f3378a65637ad04151cc517fd9047363af954c31
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723292"
---
# <a name="use-my-subscriptions"></a><span data-ttu-id="314d8-102">Utilizzare Sottoscrizioni personali</span><span class="sxs-lookup"><span data-stu-id="314d8-102">Use My Subscriptions</span></span>
  [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)]<span data-ttu-id="314d8-103">Gestione report include una pagina **sottoscrizioni personali** che consente di organizzare tutte le sottoscrizioni in un'unica posizione.</span><span class="sxs-lookup"><span data-stu-id="314d8-103">Report Manager includes a **My Subscriptions** page that organizes all of your subscriptions into one place.</span></span> <span data-ttu-id="314d8-104">La pagina Sottoscrizioni personali consente infatti di visualizzare, modificare ed eliminare le sottoscrizioni esistenti.</span><span class="sxs-lookup"><span data-stu-id="314d8-104">You can use My Subscriptions to view, modify, and delete existing subscriptions.</span></span> <span data-ttu-id="314d8-105">Non è tuttavia possibile utilizzarla per creare sottoscrizioni.</span><span class="sxs-lookup"><span data-stu-id="314d8-105">However, you cannot use it to create subscriptions.</span></span>  
  
||  
|-|  
|<span data-ttu-id="314d8-106">**[!INCLUDE[applies](../../includes/applies-md.md)]**  Modalità nativa di [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="314d8-106">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] Native mode</span></span>|  
  
 <span data-ttu-id="314d8-107">Nella pagina Sottoscrizioni personali è possibile ordinare le sottoscrizioni per cartella, report, descrizione, trigger, data di ultima esecuzione o stato.</span><span class="sxs-lookup"><span data-stu-id="314d8-107">Within My Subscriptions, you can sort subscriptions by folder, report, description, trigger, last run, or status.</span></span> <span data-ttu-id="314d8-108">Tutti i valori sono in ordine alfabetico, ad eccezione di quelli del campo Ultima esecuzione, che sono in ordine cronologico.</span><span class="sxs-lookup"><span data-stu-id="314d8-108">All values are sorted alphabetically except for Last Run, which is in chronological order.</span></span>  
  
 <span data-ttu-id="314d8-109">Nella pagina Sottoscrizioni personali sono visualizzate solo le sottoscrizioni create dall'utente che vi accede.</span><span class="sxs-lookup"><span data-stu-id="314d8-109">My Subscriptions shows only the subscriptions that you create.</span></span> <span data-ttu-id="314d8-110">Non sono elencate né sottoscrizioni di proprietà di altri utenti, nemmeno se questi sono sottoscrittori delle sottoscrizioni elencate, né sottoscrizioni guidate dai dati.</span><span class="sxs-lookup"><span data-stu-id="314d8-110">It does not list subscriptions that are owned by other users, even if you are added as a subscriber to those subscriptions, nor does it show data-driven subscriptions.</span></span>  
  
 <span data-ttu-id="314d8-111">Non è possibile individuare una sottoscrizione eseguendo ricerche per nome o altri tipi di ricerche, ad esempio in base al trigger, alle informazioni di stato e così via.</span><span class="sxs-lookup"><span data-stu-id="314d8-111">You cannot search for subscriptions by name, nor can you search for subscriptions based on trigger information, status information, and so forth.</span></span> <span data-ttu-id="314d8-112">Per ulteriori informazioni, vedere [creare, modificare ed eliminare sottoscrizioni Standard &#40;Reporting Services in modalità nativa&#41;](create-and-manage-subscriptions-for-native-mode-report-servers.md).</span><span class="sxs-lookup"><span data-stu-id="314d8-112">For more information, see [Create, Modify, and Delete Standard Subscriptions &#40;Reporting Services in Native Mode&#41;](create-and-manage-subscriptions-for-native-mode-report-servers.md).</span></span>  
  
## <a name="how-to-use-my-subscriptions"></a><span data-ttu-id="314d8-113">Come utilizzare la pagina Sottoscrizioni personali</span><span class="sxs-lookup"><span data-stu-id="314d8-113">How to Use My Subscriptions</span></span>  
 <span data-ttu-id="314d8-114">La pagina Sottoscrizioni personali è disponibile attraverso Gestione report.</span><span class="sxs-lookup"><span data-stu-id="314d8-114">My Subscriptions is available through Report Manager.</span></span> <span data-ttu-id="314d8-115">Per accedere alle sottoscrizioni personali, fare clic su **sottoscrizioni personali** nella gestione report barra degli strumenti globale.</span><span class="sxs-lookup"><span data-stu-id="314d8-115">To access My Subscriptions, click **My Subscriptions** on the Report Manager global toolbar.</span></span>  
  
## <a name="use-windows-powershell-to-list-mysubscriptions"></a><span data-ttu-id="314d8-116">Utilizzare Windows PowerShell per elencare MySubscriptions</span><span class="sxs-lookup"><span data-stu-id="314d8-116">Use Windows PowerShell to list MySubscriptions</span></span>  
 <span data-ttu-id="314d8-117">![Contenuto correlato di PowerShell](../media/rs-powershellicon.jpg "Contenuto correlato di PowerShell")</span><span class="sxs-lookup"><span data-stu-id="314d8-117">![PowerShell related content](../media/rs-powershellicon.jpg "PowerShell related content")</span></span>  
  
 <span data-ttu-id="314d8-118">Tramite il seguente script di PowerShell verrà restituito l'elenco delle sottoscrizioni e delle proprietà di sottoscrizione per l'utente corrente.</span><span class="sxs-lookup"><span data-stu-id="314d8-118">The following PowerShell script will return the list of subscriptions and subscription properties for the current user.</span></span> <span data-ttu-id="314d8-119">Per altre informazioni, vedere [Metodo ReportingService2010.ListMySubscriptions](https://technet.microsoft.com/library/reportservice2010.reportingservice2010.listmysubscriptions.aspx).</span><span class="sxs-lookup"><span data-stu-id="314d8-119">For more information, see [ReportingService2010.ListMySubscriptions Method](https://technet.microsoft.com/library/reportservice2010.reportingservice2010.listmysubscriptions.aspx).</span></span>  
  
```powershell
#server -  all subscriptions of the current user at the given server or site  
$server="[server name]/reportserver"  
$rs2010 = New-WebServiceProxy -Uri "http://$server/ReportService2010.asmx" -Namespace SSRS.ReportingService2010 -UseDefaultCredential ;  
  
$subscriptions=ListMySubscriptions(ItemPathOrSiteURL)  
$subscriptions | select Path, report, Description, Owner, SubscriptionID, lastexecuted,Status  
#uncomment the following to list all the subscription properties  
#$subscriptions
```  
  
## <a name="see-also"></a><span data-ttu-id="314d8-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="314d8-120">See Also</span></span>  
 <span data-ttu-id="314d8-121">[Data-Driven Subscriptions](data-driven-subscriptions.md) </span><span class="sxs-lookup"><span data-stu-id="314d8-121">[Data-Driven Subscriptions](data-driven-subscriptions.md) </span></span>  
 <span data-ttu-id="314d8-122">[Sottoscrizioni e recapito &#40;Reporting Services&#41;](subscriptions-and-delivery-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="314d8-122">[Subscriptions and Delivery &#40;Reporting Services&#41;](subscriptions-and-delivery-reporting-services.md) </span></span>  
 [<span data-ttu-id="314d8-123">Creare e gestire sottoscrizioni per server di report in modalità nativa</span><span class="sxs-lookup"><span data-stu-id="314d8-123">Create and Manage Subscriptions for Native Mode Report Servers</span></span>](../create-manage-subscriptions-native-mode-report-servers.md)  
