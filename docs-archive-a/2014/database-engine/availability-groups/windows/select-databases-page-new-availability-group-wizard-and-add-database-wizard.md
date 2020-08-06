---
title: Pagina Selezione database (creazione guidata gruppo di disponibilità-procedura guidata Aggiungi database) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.adddatabasewizard.selectdatabases.f1
- sql12.swb.newagwizard.selectdatabases.f1
ms.assetid: 929c5e15-d087-438d-b1f2-aa97c5f8bff8
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c626b8f0953f18a6dd4661124a09b7f542caeb82
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724212"
---
# <a name="select-databases-page-new-availability-group-wizard-add-database-wizard"></a><span data-ttu-id="2ae7e-102">Pagina Selezione database (creazione guidata gruppo di disponibilità-procedura guidata Aggiungi database)</span><span class="sxs-lookup"><span data-stu-id="2ae7e-102">Select Databases Page (New Availability Group Wizard-Add Database Wizard)</span></span>
  <span data-ttu-id="2ae7e-103">Questo argomento della Guida descrive le opzioni della pagina **Specifica database**.</span><span class="sxs-lookup"><span data-stu-id="2ae7e-103">This help topic describes the options of the **Specify Databases** page.</span></span> <span data-ttu-id="2ae7e-104">Questo argomento si applica alla [!INCLUDE[ssAoNewAgWiz](../../../includes/ssaonewagwiz-md.md)] e alla [!INCLUDE[ssAoAddDbWiz](../../../includes/ssaoadddbwiz-md.md)] di [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2ae7e-104">This topic applies to the [!INCLUDE[ssAoNewAgWiz](../../../includes/ssaonewagwiz-md.md)] and [!INCLUDE[ssAoAddDbWiz](../../../includes/ssaoadddbwiz-md.md)] of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span>  
  
##  <a name="select-databases-options"></a><a name="PageOptions"></a> <span data-ttu-id="2ae7e-105">Opzioni di selezione dei database</span><span class="sxs-lookup"><span data-stu-id="2ae7e-105">Select Databases Options</span></span>  
 <span data-ttu-id="2ae7e-106">Nella griglia **Database utente in questa istanza di SQL Server** è elencato ogni database utente locale.</span><span class="sxs-lookup"><span data-stu-id="2ae7e-106">The **User databases on this instance of SQL Server** grid lists every local user database.</span></span> <span data-ttu-id="2ae7e-107">Le colonne sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="2ae7e-107">The columns are as follows:</span></span>  
  
 <span data-ttu-id="2ae7e-108">**Nome**</span><span class="sxs-lookup"><span data-stu-id="2ae7e-108">**Name**</span></span>  
 <span data-ttu-id="2ae7e-109">Visualizza il nome di un database utente locale.</span><span class="sxs-lookup"><span data-stu-id="2ae7e-109">Displays the name of a local user database.</span></span>  
  
 <span data-ttu-id="2ae7e-110">**Dimensione**</span><span class="sxs-lookup"><span data-stu-id="2ae7e-110">**Size**</span></span>  
 <span data-ttu-id="2ae7e-111">Visualizza la dimensione del database, se è disponibile per la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="2ae7e-111">Displays the database size, if the size is available to the wizard.</span></span>  
  
 <span data-ttu-id="2ae7e-112">**Status**</span><span class="sxs-lookup"><span data-stu-id="2ae7e-112">**Status**</span></span>  
 <span data-ttu-id="2ae7e-113">Visualizza un collegamento ipertestuale il cui testo indica se un determinato database soddisfa i prerequisiti per l'aggiunta a un gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="2ae7e-113">Displays a hyperlink whose text that indicates whether a given database meets the prerequisites for being added to an availability group.</span></span> <span data-ttu-id="2ae7e-114">Se lo stato è "**Soddisfa i prerequisiti**" è possibile aggiungere il database al gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="2ae7e-114">If the status is "**Meets prerequisites**" you can add the database to the availability group.</span></span> <span data-ttu-id="2ae7e-115">Se un database non soddisfa tutti i prerequisiti, il collegamento ipertestuale **Stato** fornisce una breve spiegazione dei motivi per cui il database non è idoneo.</span><span class="sxs-lookup"><span data-stu-id="2ae7e-115">If a database does not meet all of the prerequisites, the **Status** hyperlink provides a brief explanation of why the database is ineligible.</span></span> <span data-ttu-id="2ae7e-116">Per ulteriori informazioni, fare clic sul collegamento ipertestuale.</span><span class="sxs-lookup"><span data-stu-id="2ae7e-116">For more information, click the hyperlink.</span></span>  
  
 <span data-ttu-id="2ae7e-117">È possibile lasciare la procedura guidata sulla pagina **Seleziona database** mentre si eseguono le operazioni necessari per soddisfare un prerequisito del database.</span><span class="sxs-lookup"><span data-stu-id="2ae7e-117">You can leave the wizard on the **Select Database** page while you take action on a database to meet a prerequisite.</span></span> <span data-ttu-id="2ae7e-118">Quando si torna alla pagina **Seleziona database** fare clic su **Aggiorna** per aggiornare la griglia.</span><span class="sxs-lookup"><span data-stu-id="2ae7e-118">When you return to the **Select Databases** page, click **Refresh** to update the grid.</span></span>  
  
 <span data-ttu-id="2ae7e-119">**Aggiorna**</span><span class="sxs-lookup"><span data-stu-id="2ae7e-119">**Refresh**</span></span>  
 <span data-ttu-id="2ae7e-120">Fare clic per aggiornare la griglia.</span><span class="sxs-lookup"><span data-stu-id="2ae7e-120">Click to refresh the grid.</span></span> <span data-ttu-id="2ae7e-121">Questa opzione è utile dopo avere eseguito un'operazione necessaria per soddisfare un prerequisito del database.</span><span class="sxs-lookup"><span data-stu-id="2ae7e-121">This is useful after you take action on a database to meet a prerequisite.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="2ae7e-122">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="2ae7e-122">Related Tasks</span></span>  
  
-   [<span data-ttu-id="2ae7e-123">Utilizzare la finestra di dialogo Nuovo gruppo di disponibilità &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="2ae7e-123">Use the New Availability Group Dialog Box &#40;SQL Server Management Studio&#41;</span></span>](use-the-new-availability-group-dialog-box-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="2ae7e-124">Usare la procedura guidata Aggiungi database a gruppo di disponibilità &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="2ae7e-124">Use the Add Database to Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](availability-group-add-database-to-group-wizard.md)  
  
## <a name="see-also"></a><span data-ttu-id="2ae7e-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2ae7e-125">See Also</span></span>  
 <span data-ttu-id="2ae7e-126">[Panoramica di Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="2ae7e-126">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="2ae7e-127">Prerequisiti, restrizioni e consigli per Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="2ae7e-127">Prerequisites, Restrictions, and Recommendations for AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](prereqs-restrictions-recommendations-always-on-availability.md)  
  
  
