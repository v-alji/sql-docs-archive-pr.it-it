---
title: Pagina Scegli collegamento (Gestione report) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: a89a555d-efa3-45d6-951e-db78ec6a2c8e
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: bc40fe726555babee8d9940e198a93577bd6a09f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626571"
---
# <a name="choose-link-page-report-manager"></a><span data-ttu-id="c81b9-102">Pagina Scegli collegamento (Gestione report)</span><span class="sxs-lookup"><span data-stu-id="c81b9-102">Choose Link Page (Report Manager)</span></span>
  <span data-ttu-id="c81b9-103">La pagina Scegli collegamento consente di selezionare un report diverso su cui basare il report collegato selezionato.</span><span class="sxs-lookup"><span data-stu-id="c81b9-103">Use the Choose Link page to choose a different report upon which to base the currently selected linked report.</span></span> <span data-ttu-id="c81b9-104">I report collegati sono basati su altri report già pubblicati in un server di report.</span><span class="sxs-lookup"><span data-stu-id="c81b9-104">Linked reports are based on other reports already published to a report server.</span></span> <span data-ttu-id="c81b9-105">Un report collegato utilizza il layout e i dati del report di base, ma dispone di pagine delle proprietà separate, in modo che sia possibile personalizzare le proprietà dei parametri, le impostazioni di sicurezza, il nome, la descrizione e il percorso.</span><span class="sxs-lookup"><span data-stu-id="c81b9-105">A linked report uses the layout and data of the base report, but has separate property pages so that you can customize parameter properties, security settings, name, description, and location.</span></span>  
  
 <span data-ttu-id="c81b9-106">La pagina Scegli collegamento consente di scegliere un report pubblicato diverso da utilizzare con il report collegato.</span><span class="sxs-lookup"><span data-stu-id="c81b9-106">Through the Choose Link page, you can choose a different published report to use with the linked report.</span></span> <span data-ttu-id="c81b9-107">La modifica delle informazioni di collegamento non ha effetti sulle altre impostazioni del report collegato, come le impostazioni di sicurezza e dei parametri.</span><span class="sxs-lookup"><span data-stu-id="c81b9-107">Other settings of the linked report (such as security and parameter settings) are unaffected by changes to the link information.</span></span> <span data-ttu-id="c81b9-108">Tramite il server di report non viene convalidata la selezione, pertanto è necessario assicurarsi di scegliere un report con parametri uguali a quelli specificati nel report collegato.</span><span class="sxs-lookup"><span data-stu-id="c81b9-108">The report server will not validate your selection, so be sure to choose a report that has the same parameters as those you specified on the linked report.</span></span>  
  
## <a name="navigation"></a><span data-ttu-id="c81b9-109">Spostamento</span><span class="sxs-lookup"><span data-stu-id="c81b9-109">Navigation</span></span>  
 <span data-ttu-id="c81b9-110">Utilizzare la procedura riportata di seguito per navigare fino a questo percorso nell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="c81b9-110">Use the following procedure to navigate to this location in the user interface (UI).</span></span>  
  
###### <a name="to-open-the-choose-link-page"></a><span data-ttu-id="c81b9-111">Per aprire la pagina Scegli collegamento</span><span class="sxs-lookup"><span data-stu-id="c81b9-111">To open the Choose Link page</span></span>  
  
1.  <span data-ttu-id="c81b9-112">Aprire Gestione report e individuare il report collegato che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="c81b9-112">Open Report Manager, and locate the linked report you want to change.</span></span>  
  
2.  <span data-ttu-id="c81b9-113">Passare con il puntatore del mouse sul report collegato, quindi fare clic sulla freccia a discesa.</span><span class="sxs-lookup"><span data-stu-id="c81b9-113">Hover over the linked report, and click the drop-down arrow.</span></span>  
  
3.  <span data-ttu-id="c81b9-114">Scegliere **Gestisci**dal menu a discesa.</span><span class="sxs-lookup"><span data-stu-id="c81b9-114">In the drop-down menu, click **Manage**.</span></span> <span data-ttu-id="c81b9-115">Viene visualizzata la pagina delle proprietà **Generale** per il report collegato.</span><span class="sxs-lookup"><span data-stu-id="c81b9-115">This opens the **General** properties page for the linked report.</span></span>  
  
4.  <span data-ttu-id="c81b9-116">Nella scheda **Generale** nella pagina delle proprietà fare clic su **Modifica collegamento**.</span><span class="sxs-lookup"><span data-stu-id="c81b9-116">On the **General** tab, on the properties page, click **Change Link**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="c81b9-117">Opzioni</span><span class="sxs-lookup"><span data-stu-id="c81b9-117">Options</span></span>  
 <span data-ttu-id="c81b9-118">**Posizione**</span><span class="sxs-lookup"><span data-stu-id="c81b9-118">**Location**</span></span>  
 <span data-ttu-id="c81b9-119">Specificare il nome completo del report pubblicato, incluso il percorso.</span><span class="sxs-lookup"><span data-stu-id="c81b9-119">Specify the full name of the published report, including the folder path and report name.</span></span> <span data-ttu-id="c81b9-120">È possibile digitare il nome completo del report oppure selezionare il report da utilizzare nella visualizzazione albero.</span><span class="sxs-lookup"><span data-stu-id="c81b9-120">You can type the full name of the report or use the tree view to navigate to the report you want to use.</span></span>  
  
 <span data-ttu-id="c81b9-121">**Visualizzazione ad albero**</span><span class="sxs-lookup"><span data-stu-id="c81b9-121">**Tree view**</span></span>  
 <span data-ttu-id="c81b9-122">Mostra tutte le cartelle nella gerarchia di cartelle nel server di report.</span><span class="sxs-lookup"><span data-stu-id="c81b9-122">Shows all of the folders in the report server folder hierarchy.</span></span> <span data-ttu-id="c81b9-123">Fare clic sul nome del report nella visualizzazione albero per inserire il nome e il percorso nel campo **Percorso** .</span><span class="sxs-lookup"><span data-stu-id="c81b9-123">To use the tree view to fill in the **Location** field, click the name of the report.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c81b9-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c81b9-124">See Also</span></span>  
 <span data-ttu-id="c81b9-125">[Pagina delle proprietà generale, report &#40;Gestione report&#41;](../../2014/reporting-services/general-properties-page-reports-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="c81b9-125">[General Properties Page, Reports &#40;Report Manager&#41;](../../2014/reporting-services/general-properties-page-reports-report-manager.md) </span></span>  
 <span data-ttu-id="c81b9-126">[Pagina nuovo report collegato &#40;Gestione report&#41;](../../2014/reporting-services/new-linked-report-page-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="c81b9-126">[New Linked Report Page &#40;Report Manager&#41;](../../2014/reporting-services/new-linked-report-page-report-manager.md) </span></span>  
 [<span data-ttu-id="c81b9-127">Guida sensibile al contesto di Gestione report</span><span class="sxs-lookup"><span data-stu-id="c81b9-127">Report Manager F1 Help</span></span>](../../2014/reporting-services/report-manager-f1-help.md)  
  
  
