---
title: Procedura di visualizzazione delle proprietà dell'istanza di CDC | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 4bce9b82-7bbd-41df-b3f4-4b40b8bad474
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 86fa298b0e02a16ddbaea220ef7f3d9f6172bf85
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716560"
---
# <a name="how-to-view-the-cdc-instance-properties"></a><span data-ttu-id="ebfc2-102">Procedura di visualizzazione delle proprietà dell'istanza di CDC</span><span class="sxs-lookup"><span data-stu-id="ebfc2-102">How to View the CDC Instance Properties</span></span>
  <span data-ttu-id="ebfc2-103">In questa procedura viene descritto come utilizzare CDC Designer Console per visualizzare le informazioni relative alle istanze create per gestire l'operazione delle istanze.</span><span class="sxs-lookup"><span data-stu-id="ebfc2-103">This procedure describes how to use the CDC Designer Console to view information about the instances that you create to help manage the operation of the instances.</span></span>  
  
### <a name="to-view-information-about-a-specific-instance"></a><span data-ttu-id="ebfc2-104">Per visualizzare informazioni su un'istanza specifica</span><span class="sxs-lookup"><span data-stu-id="ebfc2-104">To view information about a specific instance</span></span>  
  
1.  <span data-ttu-id="ebfc2-105">Scegliere **CDC Designer Console** dal menu **Start**.</span><span class="sxs-lookup"><span data-stu-id="ebfc2-105">From the **Start** menu, select the **CDC Designer Console**.</span></span>  
  
2.  <span data-ttu-id="ebfc2-106">Nel riquadro sinistro espandere **Change Data Capture** , quindi espandere il servizio che contiene l'istanza che si desidera visualizzare.</span><span class="sxs-lookup"><span data-stu-id="ebfc2-106">In the left pane, expand **Change Data Capture** then expand the service that contains the instance you want to view.</span></span>  
  
3.  <span data-ttu-id="ebfc2-107">Selezionare il nome di un'istanza che si desidera utilizzare.</span><span class="sxs-lookup"><span data-stu-id="ebfc2-107">Select the name of an instance you want to work with.</span></span>  
  
     <span data-ttu-id="ebfc2-108">Le informazioni relative all'istanza vengono visualizzate nella parte centrale di CDC Designer Console.</span><span class="sxs-lookup"><span data-stu-id="ebfc2-108">The information about the instance is displayed in the center part of the CDC Designer Console.</span></span> <span data-ttu-id="ebfc2-109">È suddivisa in quattro schede.</span><span class="sxs-lookup"><span data-stu-id="ebfc2-109">It is divided into four tabs.</span></span> <span data-ttu-id="ebfc2-110">Tutte le schede sono in sola lettura.</span><span class="sxs-lookup"><span data-stu-id="ebfc2-110">All of the tabs are read only.</span></span>  
  
     <span data-ttu-id="ebfc2-111">**Status**</span><span class="sxs-lookup"><span data-stu-id="ebfc2-111">**Status**</span></span>  
     <span data-ttu-id="ebfc2-112">In questa scheda vengono visualizzate le informazioni relative allo stato corrente di Change Data Capture per l'istanza.</span><span class="sxs-lookup"><span data-stu-id="ebfc2-112">This tab displays the information about the current status of the change data capture for the instance.</span></span> <span data-ttu-id="ebfc2-113">Per informazioni sul contenuto di questa scheda, vedere la sezione **Schede del visualizzatore** in [Manage a CDC Instance](manage-a-cdc-instance.md).</span><span class="sxs-lookup"><span data-stu-id="ebfc2-113">For information about what is displayed in this tab, see the **Viewer Tabs** section in [Manage a CDC Instance](manage-a-cdc-instance.md).</span></span>  
  
     <span data-ttu-id="ebfc2-114">**Oracle**</span><span class="sxs-lookup"><span data-stu-id="ebfc2-114">**Oracle**</span></span>  
     <span data-ttu-id="ebfc2-115">In questa scheda vengono visualizzate informazioni sull'istanza di CDC e sul database di origine Oracle.</span><span class="sxs-lookup"><span data-stu-id="ebfc2-115">This tab displays general information about the CDC instance and the Oracle source database.</span></span> <span data-ttu-id="ebfc2-116">Per informazioni sul contenuto di questa scheda, vedere [Edit the Oracle Database Properties](edit-the-oracle-database-properties.md).</span><span class="sxs-lookup"><span data-stu-id="ebfc2-116">For information about what is displayed in this tab, see [Edit the Oracle Database Properties](edit-the-oracle-database-properties.md).</span></span>  
  
     <span data-ttu-id="ebfc2-117">**Tabelle**</span><span class="sxs-lookup"><span data-stu-id="ebfc2-117">**Tables**</span></span>  
     <span data-ttu-id="ebfc2-118">In questa scheda vengono visualizzate le informazioni relative alle tabelle incluse in Change Data Capture.</span><span class="sxs-lookup"><span data-stu-id="ebfc2-118">This tab displays information about the tables included in the change data capture.</span></span> <span data-ttu-id="ebfc2-119">Vengono anche elencate le colonne acquisite.</span><span class="sxs-lookup"><span data-stu-id="ebfc2-119">It also lists the columns that are captured.</span></span> <span data-ttu-id="ebfc2-120">Per informazioni sul contenuto di questa scheda, vedere [Edit Tables](edit-tables.md).</span><span class="sxs-lookup"><span data-stu-id="ebfc2-120">For information about what is displayed in this tab, see [Edit Tables](edit-tables.md).</span></span>  
  
     <span data-ttu-id="ebfc2-121">**Funzionalità avanzate**</span><span class="sxs-lookup"><span data-stu-id="ebfc2-121">**Advanced**</span></span>  
     <span data-ttu-id="ebfc2-122">In questa scheda viene visualizzato un elenco delle proprietà avanzate definite nell'editor delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="ebfc2-122">This tab displays a list of advanced properties that you define in the properties editor.</span></span> <span data-ttu-id="ebfc2-123">Per informazioni sul contenuto di questa scheda, vedere [Edit the Advanced Properties](edit-the-advanced-properties.md).</span><span class="sxs-lookup"><span data-stu-id="ebfc2-123">For information about what is displayed in this tab, see [Edit the Advanced Properties](edit-the-advanced-properties.md).</span></span>  
  
  
