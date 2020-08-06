---
title: Aggiornamento dei pacchetti (aggiornamento guidato pacchetti SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.is.upgradewizard.upgradingpackage.f1
ms.assetid: cdb842e3-2e59-4ede-b127-be4fde46875c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d13228dabc1566b592733da4afd8ebde3671ee0d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625445"
---
# <a name="upgrading-the-packages-ssis-package-upgrade-wizard"></a><span data-ttu-id="ad2c4-102">Aggiornamento pacchetti (Aggiornamento guidato pacchetti SSIS)</span><span class="sxs-lookup"><span data-stu-id="ad2c4-102">Upgrading the Packages (SSIS Package Upgrade Wizard)</span></span>
  <span data-ttu-id="ad2c4-103">Utilizzare la pagina **Aggiornamento pacchetti** per visualizzare lo stato dell'aggiornamento dei pacchetti e per interrompere l'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="ad2c4-103">Use the **Upgrading the Packages** page to view the progress of package upgrade and to interrupt the upgrade process.</span></span> <span data-ttu-id="ad2c4-104">L'Aggiornamento guidato pacchetti [!INCLUDE[ssIS](../includes/ssis-md.md)] consente di aggiornare uno per uno i pacchetti selezionati.</span><span class="sxs-lookup"><span data-stu-id="ad2c4-104">The [!INCLUDE[ssIS](../includes/ssis-md.md)] Package Upgrade Wizard upgrades the selected packages one by one.</span></span>  
  
 <span data-ttu-id="ad2c4-105">**Per visualizzare i pacchetti aggiornati salvati in un database SQL Server o nell'archivio pacchetti**</span><span class="sxs-lookup"><span data-stu-id="ad2c4-105">**To view upgraded packages that were saved to a SQL Server database or to the package store**</span></span>  
  
-   <span data-ttu-id="ad2c4-106">In [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], in Esplora oggetti connettersi a un'istanza locale di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], quindi espandere il nodo **Pacchetti archiviati** per visualizzare i pacchetti aggiornati.</span><span class="sxs-lookup"><span data-stu-id="ad2c4-106">In [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], in Object Explorer, connect to the local instance of [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], and then expand the **Stored Packages** node to see the packages that were upgraded.</span></span>  
  
 <span data-ttu-id="ad2c4-107">**Per visualizzare i pacchetti aggiornati da SQL Server Data Tools**</span><span class="sxs-lookup"><span data-stu-id="ad2c4-107">**To view upgraded packages that were upgraded from SQL Server Data Tools**</span></span>  
  
-   <span data-ttu-id="ad2c4-108">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], in Esplora soluzioni aprire il progetto [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , quindi espandere il nodo **Pacchetti SSIS** per visualizzare i pacchetti aggiornati.</span><span class="sxs-lookup"><span data-stu-id="ad2c4-108">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], in Solution Explorer, open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project, and then expand the **SSIS Packages** node to see the upgraded packages.</span></span>  
  
## <a name="options"></a><span data-ttu-id="ad2c4-109">Opzioni</span><span class="sxs-lookup"><span data-stu-id="ad2c4-109">Options</span></span>  
 <span data-ttu-id="ad2c4-110">**Riquadro messaggi**</span><span class="sxs-lookup"><span data-stu-id="ad2c4-110">**Message pane**</span></span>  
 <span data-ttu-id="ad2c4-111">Consente di visualizzare messaggi di stato e informazioni di riepilogo durante il processo di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="ad2c4-111">Displays progress messages and summary information during the upgrade process.</span></span>  
  
 <span data-ttu-id="ad2c4-112">**Azione**</span><span class="sxs-lookup"><span data-stu-id="ad2c4-112">**Action**</span></span>  
 <span data-ttu-id="ad2c4-113">Consente di visualizzare le azioni incluse nell'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="ad2c4-113">View the actions in the upgrade.</span></span>  
  
 <span data-ttu-id="ad2c4-114">**Status**</span><span class="sxs-lookup"><span data-stu-id="ad2c4-114">**Status**</span></span>  
 <span data-ttu-id="ad2c4-115">Consente di visualizzare il risultato di ogni azione.</span><span class="sxs-lookup"><span data-stu-id="ad2c4-115">View the result of each action.</span></span>  
  
 <span data-ttu-id="ad2c4-116">**Message**</span><span class="sxs-lookup"><span data-stu-id="ad2c4-116">**Message**</span></span>  
 <span data-ttu-id="ad2c4-117">Consente di visualizzare i messaggi di errore generati da ogni azione.</span><span class="sxs-lookup"><span data-stu-id="ad2c4-117">View the error messages that each action generates.</span></span>  
  
 <span data-ttu-id="ad2c4-118">**Stop**</span><span class="sxs-lookup"><span data-stu-id="ad2c4-118">**Stop**</span></span>  
 <span data-ttu-id="ad2c4-119">Consente di arrestare l'aggiornamento del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="ad2c4-119">Stop the package upgrade.</span></span>  
  
 <span data-ttu-id="ad2c4-120">**Report**</span><span class="sxs-lookup"><span data-stu-id="ad2c4-120">**Report**</span></span>  
 <span data-ttu-id="ad2c4-121">Selezionare le operazioni da eseguire nel report che contiene i risultati dell'aggiornamento del pacchetto:</span><span class="sxs-lookup"><span data-stu-id="ad2c4-121">Select what you want to do with the report that contains the results of the package upgrade:</span></span>  
  
-   <span data-ttu-id="ad2c4-122">Visualizzare il report online.</span><span class="sxs-lookup"><span data-stu-id="ad2c4-122">View the report online.</span></span>  
  
-   <span data-ttu-id="ad2c4-123">Salvare il report in un file.</span><span class="sxs-lookup"><span data-stu-id="ad2c4-123">Save the report to a file.</span></span>  
  
-   <span data-ttu-id="ad2c4-124">Copiare il report negli Appunti</span><span class="sxs-lookup"><span data-stu-id="ad2c4-124">Copy the report to the Clipboard</span></span>  
  
-   <span data-ttu-id="ad2c4-125">Inviare il report come messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="ad2c4-125">Send the report as an e-mail message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad2c4-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ad2c4-126">See Also</span></span>  
 [<span data-ttu-id="ad2c4-127">Aggiornare pacchetti di Integration Services</span><span class="sxs-lookup"><span data-stu-id="ad2c4-127">Upgrade Integration Services Packages</span></span>](install-windows/upgrade-integration-services-packages.md)  
  
  
