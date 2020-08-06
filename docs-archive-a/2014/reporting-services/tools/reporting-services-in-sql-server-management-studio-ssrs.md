---
title: Reporting Services in SQL Server Management Studio (SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- report servers [Reporting Services], how-to topics
ms.assetid: 60685458-9108-47bf-820a-5e7db454d408
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 3f4083d8b288c8816925723f4cfaef4342dd0298
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721042"
---
# <a name="reporting-services-in-sql-server-management-studio-ssrs"></a><span data-ttu-id="191ab-102">Reporting Services di SQL Server Management Studio (SSRS)</span><span class="sxs-lookup"><span data-stu-id="191ab-102">Reporting Services in SQL Server Management Studio (SSRS)</span></span>
  <span data-ttu-id="191ab-103">Gli amministratori del server di report possono usare [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] per:</span><span class="sxs-lookup"><span data-stu-id="191ab-103">Report server administrators can use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to:</span></span>  
  
-   <span data-ttu-id="191ab-104">Abilitare le funzionalità, impostare le impostazioni predefinite del server e gestire processi in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="191ab-104">Enable features, set server defaults, and manage running jobs.</span></span>  
  
-   <span data-ttu-id="191ab-105">Visualizzare e creare report personalizzati.</span><span class="sxs-lookup"><span data-stu-id="191ab-105">View and create custom reports.</span></span> <span data-ttu-id="191ab-106">Molti nodi di Esplora oggetti visualizzano un set di report standard installati con [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="191ab-106">In Object Explorer, many nodes display a set of standard reports that are installed with [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span> <span data-ttu-id="191ab-107">È necessario disporre di autorizzazioni di amministratore.</span><span class="sxs-lookup"><span data-stu-id="191ab-107">You must have administrator permissions.</span></span> <span data-ttu-id="191ab-108">Lo schema di un report personalizzato deve corrispondere allo schema dei report installati.</span><span class="sxs-lookup"><span data-stu-id="191ab-108">The schema of a custom report must match the schema of the installed reports.</span></span> <span data-ttu-id="191ab-109">Per altre informazioni, vedere [Report personalizzati in Management Studio](../../ssms/object/custom-reports-in-management-studio.md) e [Individuare la versione dello schema di definizione del report &#40;SSRS&#41;](../reports/find-the-report-definition-schema-version-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="191ab-109">For more information, see [Custom Reports in Management Studio](../../ssms/object/custom-reports-in-management-studio.md) and [Find the Report Definition Schema Version &#40;SSRS&#41;](../reports/find-the-report-definition-schema-version-ssrs.md).</span></span>  
  
 <span data-ttu-id="191ab-110">Gli autori di report possono utilizzare [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] per:</span><span class="sxs-lookup"><span data-stu-id="191ab-110">Report authors can use [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] to:</span></span>  
  
-   <span data-ttu-id="191ab-111">Visualizzare i dati spaziali da un set di risultati della query per un report mappa.</span><span class="sxs-lookup"><span data-stu-id="191ab-111">Visualize spatial data from a query result set for a map report.</span></span> <span data-ttu-id="191ab-112">Dopo l'esecuzione di una query, usare la scheda **Risultati spaziali** nel riquadro del set di risultati.</span><span class="sxs-lookup"><span data-stu-id="191ab-112">After you run the query, use the **Spatial results** tab in the result set pane.</span></span> <span data-ttu-id="191ab-113">Per altre informazioni, vedere [Visualizzazione di dati spaziali in Esplora oggetti](../../relational-databases/scripting/view-spatial-data-in-object-explorer.md).</span><span class="sxs-lookup"><span data-stu-id="191ab-113">For more information, see [View Spatial Data in Object Explorer](../../relational-databases/scripting/view-spatial-data-in-object-explorer.md).</span></span>  
  
 <span data-ttu-id="191ab-114">In questa sezione sono disponibili istruzioni dettagliate per l'esecuzione di varie attività con i report usando [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="191ab-114">This section contains step-by-step instructions for performing various reporting tasks using [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span> <span data-ttu-id="191ab-115">La creazione e la gestione di pianificazioni condivise possono essere inoltre eseguiti utilizzando Gestione report.</span><span class="sxs-lookup"><span data-stu-id="191ab-115">Creating and managing shared schedules can also be performed using Report Manager.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="191ab-116">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="191ab-116">In This Section</span></span>  
  
-   [<span data-ttu-id="191ab-117">Eseguire la connessione a un server di report in Management Studio</span><span class="sxs-lookup"><span data-stu-id="191ab-117">Connect to a Report Server in Management Studio</span></span>](connect-to-a-report-server-in-management-studio.md)  
  
-   [<span data-ttu-id="191ab-118">Impostare le proprietà di un server di report &#40;Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="191ab-118">Set Report Server Properties &#40;Management Studio&#41;</span></span>](set-report-server-properties-management-studio.md)  
  
-   [<span data-ttu-id="191ab-119">Creare, eliminare o modificare un ruolo &#40;Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="191ab-119">Create, Delete, or Modify a Role &#40;Management Studio&#41;</span></span>](../security/role-definitions-create-delete-or-modify.md)  
  
-   [<span data-ttu-id="191ab-120">Eliminare un elemento &#40;Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="191ab-120">Delete an Item &#40;Management Studio&#41;</span></span>](delete-an-item-management-studio.md)  
  
-   [<span data-ttu-id="191ab-121">Annulla processi server di report &#40;Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="191ab-121">Cancel Report Server Jobs &#40;Management Studio&#41;</span></span>](cancel-report-server-jobs-management-studio.md)  
  
## <a name="see-also"></a><span data-ttu-id="191ab-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="191ab-122">See Also</span></span>  
 <span data-ttu-id="191ab-123">[Guida sensibile al contesto del server di report Management Studio](report-server-in-management-studio-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="191ab-123">[Report Server in Management Studio F1 Help](report-server-in-management-studio-f1-help.md) </span></span>  
 [<span data-ttu-id="191ab-124">Introduzione a SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="191ab-124">Introducing SQL Server Management Studio</span></span>](../../ssms/sql-server-management-studio-ssms.md)  
  
  
