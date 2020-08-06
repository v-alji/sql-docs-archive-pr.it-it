---
title: Tipo di sottoscrizione | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.newsubwizard.subscriptiontype.f1
ms.assetid: 9a50f588-ee45-4a87-826f-372ff0798587
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 614ff910b13706485ee9466c884243ff1c9027ea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715187"
---
# <a name="subscription-type"></a><span data-ttu-id="0d658-102">Tipo di sottoscrizione</span><span class="sxs-lookup"><span data-stu-id="0d658-102">Subscription Type</span></span>
  <span data-ttu-id="0d658-103">La replica di tipo merge offre due tipi di sottoscrizioni, ovvero server e client, definiti rispettivamente come globale e locale nelle versioni precedenti di [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0d658-103">Merge replication offers two subscription types: server and client (referred to in previous versions of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] as global and local, respectively).</span></span> <span data-ttu-id="0d658-104">I Sottoscrittori con una sottoscrizione di tipo server sono in grado di:</span><span class="sxs-lookup"><span data-stu-id="0d658-104">Subscribers with a server subscription can:</span></span>  
  
-   <span data-ttu-id="0d658-105">Ripubblicare i dati di altri Sottoscrittori.</span><span class="sxs-lookup"><span data-stu-id="0d658-105">Republish data to other Subscribers.</span></span>  
  
-   <span data-ttu-id="0d658-106">Fungere da partner di sottoscrizione alternativi.</span><span class="sxs-lookup"><span data-stu-id="0d658-106">Serve as alternate synchronization partners.</span></span>  
  
-   <span data-ttu-id="0d658-107">Risolvere conflitti in base alla priorità impostata.</span><span class="sxs-lookup"><span data-stu-id="0d658-107">Resolve conflicts according to a priority you set.</span></span>  
  
 <span data-ttu-id="0d658-108">La maggior parte dei Sottoscrittori non necessita di questa funzionalità ed è in grado di utilizzare una sottoscrizione client.</span><span class="sxs-lookup"><span data-stu-id="0d658-108">Most Subscribers do not require this functionality and can use a client subscription.</span></span> <span data-ttu-id="0d658-109">Le sottoscrizioni client consentono ancora il rilevamento e la risoluzione dei conflitti, ma ai Sottoscrittori non viene assegnata una priorità. In altre parole, il primo Sottoscrittore che inoltra una modifica al server di pubblicazione prevale nei conflitti eventualmente generati da tale modifica.</span><span class="sxs-lookup"><span data-stu-id="0d658-109">Client subscriptions still allow conflict detection and resolution, but Subscribers are not assigned a priority: the first Subscriber to submit a change to the Publisher wins any conflicts that might arise from that change.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0d658-110">Dopo aver creato la sottoscrizione non è possibile modificarne il tipo.</span><span class="sxs-lookup"><span data-stu-id="0d658-110">Subscription type cannot be changed after a subscription is created.</span></span>  
  
## <a name="options"></a><span data-ttu-id="0d658-111">Opzioni</span><span class="sxs-lookup"><span data-stu-id="0d658-111">Options</span></span>  
 <span data-ttu-id="0d658-112">**Proprietà sottoscrizione**</span><span class="sxs-lookup"><span data-stu-id="0d658-112">**Subscription properties**</span></span>  
 <span data-ttu-id="0d658-113">Per ogni Sottoscrittore, selezionare **Client** o **Server** nell'elenco a discesa nella colonna **Tipo di sottoscrizione** .</span><span class="sxs-lookup"><span data-stu-id="0d658-113">For each Subscriber, select **Client** or **Server** from the drop-down list box in the **Subscription Type** column.</span></span> <span data-ttu-id="0d658-114">Per i Sottoscrittori con sottoscrizioni server, immettere un numero compreso tra 0 e 99,99 nella colonna **Priorità per la risoluzione dei conflitti** . Maggiore è questo numero, più alta è la priorità per il Sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="0d658-114">For Subscribers with server subscriptions, enter a number between 0 and 99.99 in the **Priority for Conflict Resolution** column (the higher the number, the higher the priority for the Subscriber).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d658-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0d658-115">See Also</span></span>  
 <span data-ttu-id="0d658-116">[Create a Pull Subscription](create-a-pull-subscription.md) </span><span class="sxs-lookup"><span data-stu-id="0d658-116">[Create a Pull Subscription](create-a-pull-subscription.md) </span></span>  
 <span data-ttu-id="0d658-117">[Create a Push Subscription](create-a-push-subscription.md) </span><span class="sxs-lookup"><span data-stu-id="0d658-117">[Create a Push Subscription](create-a-push-subscription.md) </span></span>  
 [<span data-ttu-id="0d658-118">Sottoscrizione delle pubblicazioni</span><span class="sxs-lookup"><span data-stu-id="0d658-118">Subscribe to Publications</span></span>](subscribe-to-publications.md)  
  
  
