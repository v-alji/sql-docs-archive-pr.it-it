---
title: Categoria di eventi Prestazioni | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
topic_type:
- apiref
helpviewer_keywords:
- SQL Server event classes, Performance event category
- Performance event category [SQL Server]
- event classes [SQL Server], Performance event category
ms.assetid: 708f3585-d8be-4980-bbff-672d7c59397e
author: stevestein
ms.author: sstein
ms.openlocfilehash: b0c076a4132298797313ecbf0874d9d2d4e453cd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635024"
---
# <a name="performance-event-category"></a><span data-ttu-id="21579-102">Categoria di eventi Prestazioni</span><span class="sxs-lookup"><span data-stu-id="21579-102">Performance Event Category</span></span>
  <span data-ttu-id="21579-103">Usare la categoria di eventi **Prestazioni** per monitorare le classi di evento **Showplan** e le classi di evento generate in seguito all'esecuzione degli operatori SQL DML (Data Manipulation Language).</span><span class="sxs-lookup"><span data-stu-id="21579-103">Use the **Performance** event category to monitor **Showplan** event classes and event classes that are produced from the execution of SQL data manipulation language (DML) operators.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="21579-104">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="21579-104">In This Section</span></span>  
  
|<span data-ttu-id="21579-105">Argomento</span><span class="sxs-lookup"><span data-stu-id="21579-105">Topic</span></span>|<span data-ttu-id="21579-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="21579-106">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="21579-107">Classe di evento Auto Stats</span><span class="sxs-lookup"><span data-stu-id="21579-107">Auto Stats Event Class</span></span>](auto-stats-event-class.md)|<span data-ttu-id="21579-108">Indica un aggiornamento automatico delle statistiche di indice e di colonna.</span><span class="sxs-lookup"><span data-stu-id="21579-108">Indicates that an automatic updating of index and column statistics has occurred.</span></span>|  
|[<span data-ttu-id="21579-109">Classe di evento Degree of Parallelism &#40;7.0 Insert&#41;</span><span class="sxs-lookup"><span data-stu-id="21579-109">Degree of Parallelism &#40;7.0 Insert&#41; Event Class</span></span>](degree-of-parallelism-7-0-insert-event-class.md)|<span data-ttu-id="21579-110">Indica che in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] è stata eseguita un'istruzione SELECT, INSERT, UPDATE o DELETE utilizzando un piano seriale o parallelo.</span><span class="sxs-lookup"><span data-stu-id="21579-110">Indicates that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has executed a SELECT, INSERT, UPDATE, or DELETE statement using either a serial or parallel plan.</span></span> <span data-ttu-id="21579-111">Viene anche riportato il numero di CPU utilizzato per eseguire l'operazione.</span><span class="sxs-lookup"><span data-stu-id="21579-111">The number of CPUs used to perform the operation is also reported.</span></span>|  
|[<span data-ttu-id="21579-112">Classe di evento Performance Statistics</span><span class="sxs-lookup"><span data-stu-id="21579-112">Performance Statistics Event Class</span></span>](performance-statistics-event-class.md)|<span data-ttu-id="21579-113">Esegue il monitoraggio delle prestazioni delle query in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="21579-113">Monitors performance of the queries that are being executed.</span></span>|  
|[<span data-ttu-id="21579-114">Classe di evento Showplan All</span><span class="sxs-lookup"><span data-stu-id="21579-114">Showplan All Event Class</span></span>](showplan-all-event-class.md)|<span data-ttu-id="21579-115">Identifica gli operatori **Showplan** in un'istruzione SQL.</span><span class="sxs-lookup"><span data-stu-id="21579-115">Identifies **Showplan** operators within a SQL statement.</span></span>|  
|[<span data-ttu-id="21579-116">Classe di evento Showplan All for Query Compile</span><span class="sxs-lookup"><span data-stu-id="21579-116">Showplan All for Query Compile Event Class</span></span>](showplan-all-for-query-compile-event-class.md)|<span data-ttu-id="21579-117">Visualizza i dati relativi al tempo di compilazione per gli operatori **Showplan** .</span><span class="sxs-lookup"><span data-stu-id="21579-117">Displays compile time data for **Showplan** operators.</span></span>|  
|[<span data-ttu-id="21579-118">Classe di evento Showplan Statistics Profile</span><span class="sxs-lookup"><span data-stu-id="21579-118">Showplan Statistics Profile Event Class</span></span>](showplan-statistics-profile-event-class.md)|<span data-ttu-id="21579-119">Visualizza il costo stimato di una query.</span><span class="sxs-lookup"><span data-stu-id="21579-119">Displays the estimated cost of a query.</span></span>|  
|[<span data-ttu-id="21579-120">Classe di evento Showplan XML</span><span class="sxs-lookup"><span data-stu-id="21579-120">Showplan XML Event Class</span></span>](showplan-xml-event-class.md)|<span data-ttu-id="21579-121">Identifica gli operatori **Showplan** in un'istruzione SQL.</span><span class="sxs-lookup"><span data-stu-id="21579-121">Identifies the **Showplan** operators in a SQL statement.</span></span> <span data-ttu-id="21579-122">La classe di evento archivia ogni evento in un documento XML specifico.</span><span class="sxs-lookup"><span data-stu-id="21579-122">The event class stores each event as a well defined XML document.</span></span>|  
|[<span data-ttu-id="21579-123">Classe di evento Showplan XML For Query Compile</span><span class="sxs-lookup"><span data-stu-id="21579-123">Showplan XML for Query Compile Event Class</span></span>](showplan-xml-for-query-compile-event-class.md)|<span data-ttu-id="21579-124">Visualizza i dati relativi al tempo di compilazione per gli operatori **Showplan** in formato XML.</span><span class="sxs-lookup"><span data-stu-id="21579-124">Displays compile time data for **Showplan** operators in XML format.</span></span>|  
|[<span data-ttu-id="21579-125">Classe di evento Showplan XML Statistics Profile</span><span class="sxs-lookup"><span data-stu-id="21579-125">Showplan XML Statistics Profile Event Class</span></span>](showplan-xml-statistics-profile-event-class.md)|<span data-ttu-id="21579-126">Identifica gli operatori **Showplan** associati a un'istruzione SQL.</span><span class="sxs-lookup"><span data-stu-id="21579-126">Identifies the **Showplan** operators associated with a SQL statement.</span></span> <span data-ttu-id="21579-127">L'output è rappresentato da un documento XML.</span><span class="sxs-lookup"><span data-stu-id="21579-127">The output is an XML document.</span></span>|  
|[<span data-ttu-id="21579-128">Classe di evento SQL:FullTextQuery</span><span class="sxs-lookup"><span data-stu-id="21579-128">SQL:FullTextQuery Event Class</span></span>](sql-fulltextquery-event-class.md)|<span data-ttu-id="21579-129">Indica che [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ha eseguito una query full-text.</span><span class="sxs-lookup"><span data-stu-id="21579-129">Indicates that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has executed a full-text query.</span></span>|  
|[<span data-ttu-id="21579-130">Classe di evento Plan Guide Successful</span><span class="sxs-lookup"><span data-stu-id="21579-130">Plan Guide Successful Event Class</span></span>](plan-guide-successful-event-class.md)|<span data-ttu-id="21579-131">Indica che in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] è stato correttamente eseguito un piano di esecuzione per una query o un batch contenente una guida di piano.</span><span class="sxs-lookup"><span data-stu-id="21579-131">Indicates that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] successfully produced an execution plan for a query or batch that contained a plan guide.</span></span>|  
|[<span data-ttu-id="21579-132">Classe di evento Plan Guide Unsuccessful</span><span class="sxs-lookup"><span data-stu-id="21579-132">Plan Guide Unsuccessful Event Class</span></span>](plan-guide-unsuccessful-event-class.md)|<span data-ttu-id="21579-133">Indica che in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] non è stato possibile creare un piano di esecuzione per una query o un batch contenente una guida di piano.</span><span class="sxs-lookup"><span data-stu-id="21579-133">Indicates that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] could not produce an execution plan for a query or batch that contained a plan guide.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="21579-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="21579-134">See Also</span></span>  
 [<span data-ttu-id="21579-135">Eventi estesi</span><span class="sxs-lookup"><span data-stu-id="21579-135">Extended Events</span></span>](../extended-events/extended-events.md)  
  
  
