---
title: Convalida sottoscrizione | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.validate.validateandresynch.f1
helpviewer_keywords:
- Validate Subscription dialog box
ms.assetid: 74bdf5e1-b886-4284-b5fb-332bf79ae083
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 010b5b2e9778ccf37133b0a84796373c012290f7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626624"
---
# <a name="validate-subscription"></a><span data-ttu-id="b56ec-102">Convalida sottoscrizione</span><span class="sxs-lookup"><span data-stu-id="b56ec-102">Validate Subscription</span></span>
  <span data-ttu-id="b56ec-103">Utilizzare la finestra di dialogo **Convalida sottoscrizione** per specificare che una sottoscrizione di una pubblicazione di tipo merge deve essere convalidata alla successiva esecuzione dell'agente di merge per la sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="b56ec-103">Use the **Validate Subscription** dialog box to specify that a subscription to a merge publication should be validated the next time the Merge Agent for the subscription runs.</span></span> <span data-ttu-id="b56ec-104">I risultati della convalida vengono visualizzati in Monitoraggio replica.</span><span class="sxs-lookup"><span data-stu-id="b56ec-104">The results of validation are displayed in Replication Monitor.</span></span> <span data-ttu-id="b56ec-105">Per altre informazioni, vedere [Validate Data at the Subscriber](validate-data-at-the-subscriber.md).</span><span class="sxs-lookup"><span data-stu-id="b56ec-105">For more information, see [Validate Data at the Subscriber](validate-data-at-the-subscriber.md).</span></span>  
  
 <span data-ttu-id="b56ec-106">Per convalidare tutte le sottoscrizioni di una pubblicazione di tipo merge è inoltre possibile fare clic con il pulsante destro del mouse su una pubblicazione in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] e scegliere **Convalida tutte le sottoscrizioni**.</span><span class="sxs-lookup"><span data-stu-id="b56ec-106">It is also possible to validate all subscriptions to a merge publication by right-clicking a publication in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] and clicking **Validate All Subscriptions**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="b56ec-107">Opzioni</span><span class="sxs-lookup"><span data-stu-id="b56ec-107">Options</span></span>  
 <span data-ttu-id="b56ec-108">**Data ultimo tentativo di convalida**</span><span class="sxs-lookup"><span data-stu-id="b56ec-108">**Date of the last attempted validation**</span></span>  
 <span data-ttu-id="b56ec-109">Data dell'ultima sessione dell'agente di merge che prevedeva la convalida della sottoscrizione, indipendentemente dal fatto che la convalida sia stata completata o meno.</span><span class="sxs-lookup"><span data-stu-id="b56ec-109">The date of the last Merge Agent session that included subscription validation, whether or not that validation was successful.</span></span>  
  
 <span data-ttu-id="b56ec-110">**Data ultima convalida**</span><span class="sxs-lookup"><span data-stu-id="b56ec-110">**Date of the last successful validation**</span></span>  
 <span data-ttu-id="b56ec-111">Data dell'ultima sessione dell'agente di merge che prevedeva una convalida della sottoscrizione completata.</span><span class="sxs-lookup"><span data-stu-id="b56ec-111">The date of the last Merge Agent session that included a successful subscription validation.</span></span>  
  
 <span data-ttu-id="b56ec-112">**Convalida la sottoscrizione**</span><span class="sxs-lookup"><span data-stu-id="b56ec-112">**Validate this subscription**</span></span>  
 <span data-ttu-id="b56ec-113">Selezionare questa opzione per convalidare la sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="b56ec-113">Select to validate the subscription.</span></span>  
  
 <span data-ttu-id="b56ec-114">**Opzioni**</span><span class="sxs-lookup"><span data-stu-id="b56ec-114">**Options**</span></span>  
 <span data-ttu-id="b56ec-115">Fare clic su questo pulsante per accedere alla finestra di dialogo **Opzioni di convalida delle sottoscrizioni** nella quale è possibile specificare se utilizzare la convalida mediante il conteggio delle righe oppure la convalida mediante checksum binario.</span><span class="sxs-lookup"><span data-stu-id="b56ec-115">Click to access the **Subscription Validation Options** dialog box, which allows you to specify whether to use row count validation or binary checksum validation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b56ec-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b56ec-116">See Also</span></span>  
 [<span data-ttu-id="b56ec-117">Convalidare i dati replicati</span><span class="sxs-lookup"><span data-stu-id="b56ec-117">Validate Replicated Data</span></span>](validate-data-at-the-subscriber.md)  
  
  
