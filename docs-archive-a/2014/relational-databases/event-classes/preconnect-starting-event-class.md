---
title: Classe di evento PreConnect:Starting | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
topic_type:
- apiref
helpviewer_keywords:
- PreConnect:Starting Event Class
ms.assetid: d43ed0ad-3dbd-42e0-9cef-8320b8d87497
author: stevestein
ms.author: sstein
ms.openlocfilehash: 67b642d369c73cc144af31f835786613766045f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635020"
---
# <a name="preconnectstarting-event-class"></a><span data-ttu-id="caeea-102">Classe di evento PreConnect:Starting</span><span class="sxs-lookup"><span data-stu-id="caeea-102">PreConnect:Starting Event Class</span></span>
  <span data-ttu-id="caeea-103">La classe di evento PreConnect:Starting indica l'avvio dell'esecuzione di un trigger LOGON o di una funzione di classificazione di Resource Governor.</span><span class="sxs-lookup"><span data-stu-id="caeea-103">The PreConnect:Starting event class indicates when a LOGON trigger or the Resource Governor classifier function starts execution.</span></span>  
  
## <a name="preconnectstarting-event-class-data-columns"></a><span data-ttu-id="caeea-104">Colonne di dati della classe di evento PreConnect:Starting</span><span class="sxs-lookup"><span data-stu-id="caeea-104">PreConnect:Starting Event Class Data Columns</span></span>  
  
|<span data-ttu-id="caeea-105">Nome colonna di dati</span><span class="sxs-lookup"><span data-stu-id="caeea-105">Data column name</span></span>|<span data-ttu-id="caeea-106">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="caeea-106">Data type</span></span>|<span data-ttu-id="caeea-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="caeea-107">Description</span></span>|<span data-ttu-id="caeea-108">ID colonna</span><span class="sxs-lookup"><span data-stu-id="caeea-108">Column ID</span></span>|<span data-ttu-id="caeea-109">Filtrabile</span><span class="sxs-lookup"><span data-stu-id="caeea-109">Filterable</span></span>|  
|----------------------|---------------|-----------------|---------------|----------------|  
|<span data-ttu-id="caeea-110">EventClass</span><span class="sxs-lookup"><span data-stu-id="caeea-110">EventClass</span></span>|`int`|<span data-ttu-id="caeea-111">215</span><span class="sxs-lookup"><span data-stu-id="caeea-111">215</span></span>|<span data-ttu-id="caeea-112">27</span><span class="sxs-lookup"><span data-stu-id="caeea-112">27</span></span>|<span data-ttu-id="caeea-113">No</span><span class="sxs-lookup"><span data-stu-id="caeea-113">No</span></span>|  
|<span data-ttu-id="caeea-114">SPID</span><span class="sxs-lookup"><span data-stu-id="caeea-114">SPID</span></span>|`int`|<span data-ttu-id="caeea-115">ID del processo del server che genera l'evento.</span><span class="sxs-lookup"><span data-stu-id="caeea-115">The ID of server process that fires this event.</span></span>|<span data-ttu-id="caeea-116">12</span><span class="sxs-lookup"><span data-stu-id="caeea-116">12</span></span>|<span data-ttu-id="caeea-117">Sì</span><span class="sxs-lookup"><span data-stu-id="caeea-117">Yes</span></span>|  
|<span data-ttu-id="caeea-118">EventSubClass</span><span class="sxs-lookup"><span data-stu-id="caeea-118">EventSubClass</span></span>|`int`|<span data-ttu-id="caeea-119">1 per la funzione di classificazione definita dall'utente.</span><span class="sxs-lookup"><span data-stu-id="caeea-119">1 for the user-defined classifier function.</span></span>|<span data-ttu-id="caeea-120">21</span><span class="sxs-lookup"><span data-stu-id="caeea-120">21</span></span>|<span data-ttu-id="caeea-121">Sì</span><span class="sxs-lookup"><span data-stu-id="caeea-121">Yes</span></span>|  
|<span data-ttu-id="caeea-122">StartTime</span><span class="sxs-lookup"><span data-stu-id="caeea-122">StartTime</span></span>|`datetime`|<span data-ttu-id="caeea-123">Ora di avvio della funzione di classificazione definita dall'utente.</span><span class="sxs-lookup"><span data-stu-id="caeea-123">The time when the user-defined classifier function starts.</span></span>|<span data-ttu-id="caeea-124">14</span><span class="sxs-lookup"><span data-stu-id="caeea-124">14</span></span>|<span data-ttu-id="caeea-125">Sì</span><span class="sxs-lookup"><span data-stu-id="caeea-125">Yes</span></span>|  
|<span data-ttu-id="caeea-126">ObjectID</span><span class="sxs-lookup"><span data-stu-id="caeea-126">ObjectID</span></span>|`int`|<span data-ttu-id="caeea-127">ID dell'oggetto di classificazione definito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="caeea-127">The ID of the user-defined classifier object.</span></span>|<span data-ttu-id="caeea-128">22</span><span class="sxs-lookup"><span data-stu-id="caeea-128">22</span></span>|<span data-ttu-id="caeea-129">Sì</span><span class="sxs-lookup"><span data-stu-id="caeea-129">Yes</span></span>|  
|<span data-ttu-id="caeea-130">ObjectName</span><span class="sxs-lookup"><span data-stu-id="caeea-130">ObjectName</span></span>|`nvarchar(256)`|<span data-ttu-id="caeea-131">Nome in due parti della funzione di classificazione definita dall'utente,</span><span class="sxs-lookup"><span data-stu-id="caeea-131">The two-part name of the classifier user-defined function.</span></span> <span data-ttu-id="caeea-132">ad esempio dbo.classifier.</span><span class="sxs-lookup"><span data-stu-id="caeea-132">For example, dbo.classifier.</span></span>|<span data-ttu-id="caeea-133">34</span><span class="sxs-lookup"><span data-stu-id="caeea-133">34</span></span>|<span data-ttu-id="caeea-134">Sì</span><span class="sxs-lookup"><span data-stu-id="caeea-134">Yes</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="caeea-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="caeea-135">See Also</span></span>  
 <span data-ttu-id="caeea-136">[Eventi estesi](../extended-events/extended-events.md) </span><span class="sxs-lookup"><span data-stu-id="caeea-136">[Extended Events](../extended-events/extended-events.md) </span></span>  
 <span data-ttu-id="caeea-137">[Classe di evento PreConnect: Completed](preconnect-completed-event-class.md) </span><span class="sxs-lookup"><span data-stu-id="caeea-137">[PreConnect:Completed Event Class](preconnect-completed-event-class.md) </span></span>  
 [<span data-ttu-id="caeea-138">Resource Governor</span><span class="sxs-lookup"><span data-stu-id="caeea-138">Resource Governor</span></span>](../resource-governor/resource-governor.md)  
  
  
