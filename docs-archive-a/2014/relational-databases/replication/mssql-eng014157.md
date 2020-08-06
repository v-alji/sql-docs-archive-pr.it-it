---
title: MSSQL_ENG014157 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG014157 error
ms.assetid: 1a0890cf-d977-43e0-a2ba-9c5ff1a8f856
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 0682d740d82c995d64427f56aabce24b8a48ca65
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627202"
---
# <a name="mssql_eng014157"></a><span data-ttu-id="bfe54-102">MSSQL_ENG014157</span><span class="sxs-lookup"><span data-stu-id="bfe54-102">MSSQL_ENG014157</span></span>
    
## <a name="message-details"></a><span data-ttu-id="bfe54-103">Dettagli messaggio</span><span class="sxs-lookup"><span data-stu-id="bfe54-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="bfe54-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="bfe54-104">Product Name</span></span>|<span data-ttu-id="bfe54-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="bfe54-105">SQL Server</span></span>|  
|<span data-ttu-id="bfe54-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="bfe54-106">Event ID</span></span>|<span data-ttu-id="bfe54-107">14157</span><span class="sxs-lookup"><span data-stu-id="bfe54-107">14157</span></span>|  
|<span data-ttu-id="bfe54-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="bfe54-108">Event Source</span></span>|<span data-ttu-id="bfe54-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="bfe54-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="bfe54-110">Componente</span><span class="sxs-lookup"><span data-stu-id="bfe54-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="bfe54-111">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="bfe54-111">Symbolic Name</span></span>||  
|<span data-ttu-id="bfe54-112">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="bfe54-112">Message Text</span></span>|<span data-ttu-id="bfe54-113">La sottoscrizione creata dal Sottoscrittore '%s' della pubblicazione '%s' è scaduta ed è stata eliminata.</span><span class="sxs-lookup"><span data-stu-id="bfe54-113">The subscription created by Subscriber '%s' to publication '%s' has expired and has been dropped.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="bfe54-114">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="bfe54-114">Explanation</span></span>  
 <span data-ttu-id="bfe54-115">Un Sottoscrittore deve eseguire la sincronizzazione con il server di pubblicazione durante l'intervallo di tempo specificato nel periodo di memorizzazione della pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="bfe54-115">A Subscriber must synchronize with the Publisher within the time specified in the publication retention period.</span></span> <span data-ttu-id="bfe54-116">Se la sincronizzazione non viene eseguita in tale intervallo, la sottoscrizione scade.</span><span class="sxs-lookup"><span data-stu-id="bfe54-116">If a Subscriber does not synchronize within this period, the subscription expires.</span></span> <span data-ttu-id="bfe54-117">Per altre informazioni, vedere [Subscription Expiration and Deactivation](subscription-expiration-and-deactivation.md).</span><span class="sxs-lookup"><span data-stu-id="bfe54-117">For more information, see [Subscription Expiration and Deactivation](subscription-expiration-and-deactivation.md).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="bfe54-118">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="bfe54-118">User Action</span></span>  
 <span data-ttu-id="bfe54-119">La sottoscrizione deve essere ricreata e inizializzata prima che il Sottoscrittore possa iniziare a ricevere nuovamente le modifiche ai dati:</span><span class="sxs-lookup"><span data-stu-id="bfe54-119">The subscription must be re-created and initialized before the Subscriber can begin receiving data changes again:</span></span>  
  
-   <span data-ttu-id="bfe54-120">Per informazioni sulla creazione di sottoscrizioni, vedere [Sottoscrivere le pubblicazioni](subscribe-to-publications.md).</span><span class="sxs-lookup"><span data-stu-id="bfe54-120">For information about creating subscriptions, see [Subscribe to Publications](subscribe-to-publications.md).</span></span>  
  
-   <span data-ttu-id="bfe54-121">Per informazioni sull'inizializzazione delle sottoscrizioni, vedere [Inizializzare una sottoscrizione](initialize-a-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="bfe54-121">For information about initializing subscriptions, see [Initialize a Subscription](initialize-a-subscription.md).</span></span>  
  
 <span data-ttu-id="bfe54-122">Se nel database di sottoscrizione sono contenute modifiche che non sono state sincronizzate con il server di pubblicazione, è possibile utilizzare la [tablediff Utility](../../tools/tablediff-utility.md) per determinare quali righe sono diverse nei database di pubblicazione e sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="bfe54-122">If the subscription database contains changes that have not been synchronized with the Publisher, you can use the [tablediff Utility](../../tools/tablediff-utility.md) to determine which rows are different in the publication and subscription databases.</span></span>  
  
 <span data-ttu-id="bfe54-123">Per evitare che le sottoscrizioni scadano, è possibile incrementare il periodo di memorizzazione della pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="bfe54-123">You can increase the publication retention period to avoid having subscriptions expire.</span></span> <span data-ttu-id="bfe54-124">Prestare attenzione quando si imposta un valore elevato poiché può determinare la memorizzazione di una quantità maggiore di dati e metadati, con una conseguente riduzione delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="bfe54-124">Use caution in setting a high value, because this can result in more data and metadata being stored, which affects performance.</span></span> <span data-ttu-id="bfe54-125">Per altre informazioni, vedere [Subscription Expiration and Deactivation](subscription-expiration-and-deactivation.md).</span><span class="sxs-lookup"><span data-stu-id="bfe54-125">For more information, see [Subscription Expiration and Deactivation](subscription-expiration-and-deactivation.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfe54-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bfe54-126">See Also</span></span>  
 [<span data-ttu-id="bfe54-127">Guida di riferimento a errori ed eventi &#40;replica&#41;</span><span class="sxs-lookup"><span data-stu-id="bfe54-127">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
