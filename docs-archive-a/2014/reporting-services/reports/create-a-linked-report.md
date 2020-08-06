---
title: Creare un report collegato | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- linked reports [Reporting Services], creating
ms.assetid: 12be8341-cb57-45e8-a421-2bf66b50234d
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: ed5e70c9ff8179ae05186685e21303693fc9aed7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630274"
---
# <a name="create-a-linked-report"></a><span data-ttu-id="f0a23-102">Creare un report collegato</span><span class="sxs-lookup"><span data-stu-id="f0a23-102">Create a Linked Report</span></span>
  <span data-ttu-id="f0a23-103">Un report collegato è un elemento del server di report che fornisce un punto di accesso a un report esistente.</span><span class="sxs-lookup"><span data-stu-id="f0a23-103">A linked report is a report server item that provides an access point to an existing report.</span></span> <span data-ttu-id="f0a23-104">Tale elemento è concettualmente simile al collegamento a un programma utilizzato per l'esecuzione di un programma o per l'apertura di un file.</span><span class="sxs-lookup"><span data-stu-id="f0a23-104">Conceptually, it is similar to a program shortcut that you use to run a program or open a file.</span></span>

 <span data-ttu-id="f0a23-105">Un report collegato viene derivato da un report esistente e mantiene la definizione del report originale.</span><span class="sxs-lookup"><span data-stu-id="f0a23-105">A linked report is derived from an existing report and retains the original's report definition.</span></span> <span data-ttu-id="f0a23-106">Un report collegato, inoltre, eredita sempre il layout del report e le proprietà dell'origine dati del report originale.</span><span class="sxs-lookup"><span data-stu-id="f0a23-106">A linked report always inherits report layout and data source properties of the original report.</span></span> <span data-ttu-id="f0a23-107">Tutte le altre proprietà e impostazioni, ad esempio sicurezza, parametri, percorso, sottoscrizioni e pianificazioni, possono essere diverse da quelle del report originale.</span><span class="sxs-lookup"><span data-stu-id="f0a23-107">All other properties and settings can be different from those of the original report, including security, parameters, location, subscriptions, and schedules.</span></span>

 <span data-ttu-id="f0a23-108">È possibile creare un report collegato quando si desidera creare versioni aggiuntive di un report esistente.</span><span class="sxs-lookup"><span data-stu-id="f0a23-108">You can create a linked report when you want to create additional versions of an existing report.</span></span> <span data-ttu-id="f0a23-109">Un singolo report delle vendite regionali può essere utilizzato, ad esempio, per creare report specifici di una regione per tutti i territori di vendita.</span><span class="sxs-lookup"><span data-stu-id="f0a23-109">For example, you could use a single regional sales report to create region-specific reports for all of your sales territories.</span></span>

 <span data-ttu-id="f0a23-110">I report collegati sono in genere basati su report con parametri, sebbene questa condizione non costituisca un requisito.</span><span class="sxs-lookup"><span data-stu-id="f0a23-110">Although linked reports are typically based on parameterized reports, a parameterized report is not required.</span></span> <span data-ttu-id="f0a23-111">È possibile creare report collegati ogni volta che si desidera distribuire un report esistente con impostazioni diverse.</span><span class="sxs-lookup"><span data-stu-id="f0a23-111">You can create linked reports whenever you want to deploy an existing report with different settings.</span></span>

### <a name="to-create-a-linked-report"></a><span data-ttu-id="f0a23-112">Per creare un report collegato</span><span class="sxs-lookup"><span data-stu-id="f0a23-112">To create a linked report</span></span>

1.  <span data-ttu-id="f0a23-113">In Gestione report, passare alla cartella che contiene il report per il quale si vuole creare un collegamento, quindi aprire il menu delle opzioni e fare clic su **Crea report collegato**.</span><span class="sxs-lookup"><span data-stu-id="f0a23-113">In Report Manager, navigate to the folder containing the report that you want to link to, and then open the options menu can click **Create Linked Report**.</span></span>

2.  <span data-ttu-id="f0a23-114">Digitare un nome per il nuovo report collegato.</span><span class="sxs-lookup"><span data-stu-id="f0a23-114">Type a name for the new linked report.</span></span> <span data-ttu-id="f0a23-115">Se lo si desidera, digitare una descrizione.</span><span class="sxs-lookup"><span data-stu-id="f0a23-115">Optionally type a description.</span></span>

3.  <span data-ttu-id="f0a23-116">Per selezionare una cartella diversa per il report, fare clic su **Cambia percorso**.</span><span class="sxs-lookup"><span data-stu-id="f0a23-116">To select a different folder for the report, click **Change Location**.</span></span> <span data-ttu-id="f0a23-117">Selezionare la cartella che si vuole usare o digitare il nome della cartella nella casella **Percorso** .</span><span class="sxs-lookup"><span data-stu-id="f0a23-117">Click the folder you want to use, or type the folder name in the **Location** box.</span></span> [!INCLUDE[clickOK](../../../includes/clickok-md.md)] <span data-ttu-id="f0a23-118">Se non è stata selezionata una cartella diversa, il report collegato viene creato nella cartella corrente (dove è archiviato il report su cui si basa).</span><span class="sxs-lookup"><span data-stu-id="f0a23-118">If you do not select a different folder, the linked report is created in the current folder (where the report it is based on is stored).</span></span>

4.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)] <span data-ttu-id="f0a23-119">Verrà aperto il report collegato.</span><span class="sxs-lookup"><span data-stu-id="f0a23-119">The linked report opens.</span></span>

     <span data-ttu-id="f0a23-120">L'icona di un report collegato è diversa da quella di altri elementi gestiti da un server di report.</span><span class="sxs-lookup"><span data-stu-id="f0a23-120">A linked report's icon differs from other items managed by a report server.</span></span> <span data-ttu-id="f0a23-121">L'icona seguente indica un report collegato:</span><span class="sxs-lookup"><span data-stu-id="f0a23-121">The following icon indicates a linked report:</span></span>

     <span data-ttu-id="f0a23-122">![Icona di report collegato](../media/hlp-16linked.gif "Icona di report collegato")</span><span class="sxs-lookup"><span data-stu-id="f0a23-122">![Linked report icon](../media/hlp-16linked.gif "Linked report icon")</span></span>

## <a name="see-also"></a><span data-ttu-id="f0a23-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f0a23-123">See Also</span></span>
 <span data-ttu-id="f0a23-124">[Aprire e chiudere un report &#40;Gestione report&#41;](../reports/open-and-close-a-report-report-manager.md) [pagina nuovo report collegato &#40;Gestione report&#41;](../new-linked-report-page-report-manager.md) [scegliere la pagina percorso elemento &#40;](../choose-item-location-page-report-manager.md) Gestione report&#41;[pagina delle proprietà generale, report &#40;](../general-properties-page-reports-report-manager.md) Gestione report&#41;Reporting Services [concetti &#40;SSRS&#41;](../reporting-services-concepts-ssrs.md) Gestione report &#40;[modalità nativa SSRS](../report-manager-ssrs-native-mode.md)&#41;</span><span class="sxs-lookup"><span data-stu-id="f0a23-124">[Open and Close a Report &#40;Report Manager&#41;](../reports/open-and-close-a-report-report-manager.md) [New Linked Report Page &#40;Report Manager&#41;](../new-linked-report-page-report-manager.md) [Choose Item Location Page &#40;Report Manager&#41;](../choose-item-location-page-report-manager.md) [General Properties Page, Reports &#40;Report Manager&#41;](../general-properties-page-reports-report-manager.md) [Reporting Services Concepts &#40;SSRS&#41;](../reporting-services-concepts-ssrs.md) [Report Manager  &#40;SSRS Native Mode&#41;](../report-manager-ssrs-native-mode.md)</span></span>


