---
title: Convalida tutte le sottoscrizioni | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.validate.allsubscriptions.f1
helpviewer_keywords:
- Validate All Subscriptions dialog box
ms.assetid: 32e31469-36e4-42d9-a57a-12388bfd229d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 27a7a4f5e5c3c303d5a1cbe257c0a0e9b531e824
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635475"
---
# <a name="validate-all-subscriptions"></a><span data-ttu-id="62b07-102">Convalida tutte le sottoscrizioni</span><span class="sxs-lookup"><span data-stu-id="62b07-102">Validate All Subscriptions</span></span>
  <span data-ttu-id="62b07-103">Utilizzare la finestra di dialogo **Convalida tutte le sottoscrizioni** per specificare che tutte le sottoscrizioni di una pubblicazione di tipo merge devono essere convalidate all'esecuzione successiva dell'agente di merge per ogni sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="62b07-103">Use the **Validate All Subscriptions** dialog box to specify that all subscriptions to a merge publication should be validated the next time the Merge Agent for each subscription runs.</span></span> <span data-ttu-id="62b07-104">I risultati della convalida vengono visualizzati in Monitoraggio replica.</span><span class="sxs-lookup"><span data-stu-id="62b07-104">The results of validation are displayed in Replication Monitor.</span></span> <span data-ttu-id="62b07-105">Per altre informazioni, vedere [Validate Data at the Subscriber](validate-data-at-the-subscriber.md).</span><span class="sxs-lookup"><span data-stu-id="62b07-105">For more information, see [Validate Data at the Subscriber](validate-data-at-the-subscriber.md).</span></span>  
  
 <span data-ttu-id="62b07-106">È inoltre possibile convalidare una singola sottoscrizione facendo clic con il pulsante destro del mouse su una sottoscrizione in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , quindi scegliendo **Convalida sottoscrizione**.</span><span class="sxs-lookup"><span data-stu-id="62b07-106">It is also possible to validate a single subscription by right-clicking a subscription in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] and clicking **Validate Subscription**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="62b07-107">Opzioni</span><span class="sxs-lookup"><span data-stu-id="62b07-107">Options</span></span>  
 <span data-ttu-id="62b07-108">**Verifica solo il conteggio delle righe**</span><span class="sxs-lookup"><span data-stu-id="62b07-108">**Verify the row counts only**</span></span>  
 <span data-ttu-id="62b07-109">Consente di verificare che la tabella nel Sottoscrittore abbia lo stesso numero di righe della tabella nel server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="62b07-109">Select to validate whether the table at the Subscriber has the same number of rows as the table at the Publisher.</span></span> <span data-ttu-id="62b07-110">Questa opzione non convalida la corrispondenza del contenuto delle righe.</span><span class="sxs-lookup"><span data-stu-id="62b07-110">This method does not validate that the content of the rows matches.</span></span> <span data-ttu-id="62b07-111">La convalida del conteggio delle righe è un controllo non approfondito che consente comunque di evidenziare eventuali problemi dei dati.</span><span class="sxs-lookup"><span data-stu-id="62b07-111">Row count validation provides a lightweight approach to validation that can make you aware of issues with your data.</span></span>  
  
 <span data-ttu-id="62b07-112">**Verifica il conteggio delle righe e confronta i valori di checksum per la verifica dei dati delle righe**</span><span class="sxs-lookup"><span data-stu-id="62b07-112">**Verify the row counts and compare checksums to verify the row data**</span></span>  
 <span data-ttu-id="62b07-113">Oltre al conteggio delle righe nel server di pubblicazione e nel Sottoscrittore, viene calcolato un checksum di tutti i dati utilizzando l'algoritmo di checksum binario.</span><span class="sxs-lookup"><span data-stu-id="62b07-113">In addition to taking a count of rows at the Publisher and Subscriber, a checksum of all the data is calculated using the binary checksum algorithm.</span></span> <span data-ttu-id="62b07-114">In caso di esito negativo durante il conteggio delle righe il checksum non viene eseguito.</span><span class="sxs-lookup"><span data-stu-id="62b07-114">If the row count fails, the checksum is not performed.</span></span> <span data-ttu-id="62b07-115">Questa opzione non è valida per [!INCLUDE[ssEW](../../includes/ssew-md.md)].</span><span class="sxs-lookup"><span data-stu-id="62b07-115">This option is not valid for [!INCLUDE[ssEW](../../includes/ssew-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62b07-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="62b07-116">See Also</span></span>  
 [<span data-ttu-id="62b07-117">Convalidare i dati replicati</span><span class="sxs-lookup"><span data-stu-id="62b07-117">Validate Replicated Data</span></span>](validate-data-at-the-subscriber.md)  
  
  
