---
title: 'Lezione 3: Convalida della sottoscrizione e misurazione della latenza | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- replication [SQL Server], tutorials
ms.assetid: 147f7b93-1804-4e0b-9e17-57a51d035b2a
author: rothja
ms.author: jroth
ms.openlocfilehash: e4893c054d25d131eb2f88f32291606b0b789af7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723692"
---
# <a name="lesson-3-validating-the-subscription-and-measuring-latency"></a><span data-ttu-id="c30d3-102">Lezione 3: Convalida della sottoscrizione e misurazione della latenza</span><span class="sxs-lookup"><span data-stu-id="c30d3-102">Lesson 3: Validating the Subscription and Measuring Latency</span></span>
  <span data-ttu-id="c30d3-103">In questa lezione verranno utilizzati token di traccia per verificare se le modifiche vengono replicate nel Sottoscrittore e per determinare la latenza, ovvero il tempo necessario affinché una modifica apportata nel server di pubblicazione appaia nel Sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="c30d3-103">In this lesson, you will use tracer tokens to verify that changes are being replicated to the Subscriber and to determine latency, the time it takes for a change made at the Publisher to appear to the Subscriber.</span></span> <span data-ttu-id="c30d3-104">Per eseguire questa lezione è necessario aver completato la lezione precedente [Lezione 2: Creazione di una sottoscrizione per una pubblicazione transazionale](lesson-2-creating-a-subscription-to-the-transactional-publication.md).</span><span class="sxs-lookup"><span data-stu-id="c30d3-104">This lesson requires that you have completed the previous lesson, [Lesson 2: Creating a Subscription to the Transactional Publication](lesson-2-creating-a-subscription-to-the-transactional-publication.md).</span></span>  
  
### <a name="to-insert-a-tracer-token-and-view-information-on-the-token"></a><span data-ttu-id="c30d3-105">Per inserire un token di traccia e visualizzarne le informazioni</span><span class="sxs-lookup"><span data-stu-id="c30d3-105">To insert a tracer token and view information on the token</span></span>  
  
1.  <span data-ttu-id="c30d3-106">Connettersi al server di pubblicazione in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], espandere il nodo del server, fare clic con il pulsante destro del mouse sulla cartella **Replica** e scegliere **Launch Replication Monitor**(Avvia Monitoraggio replica).</span><span class="sxs-lookup"><span data-stu-id="c30d3-106">Connect to the Publisher in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expand the server node, right-click the **Replication** folder, and then click **Launch Replication Monitor**.</span></span>  
  
     <span data-ttu-id="c30d3-107">Monitoraggio replica verrà avviato.</span><span class="sxs-lookup"><span data-stu-id="c30d3-107">Replication Monitor launches.</span></span>  
  
2.  <span data-ttu-id="c30d3-108">Espandere un gruppo del server di pubblicazione nel riquadro sinistro, espandere l'istanza del server di pubblicazione e fare clic sulla pubblicazione **AdvWorksProductTrans** .</span><span class="sxs-lookup"><span data-stu-id="c30d3-108">Expand a Publisher group in the left pane, expand the Publisher instance, and then click the **AdvWorksProductTrans** publication.</span></span>  
  
3.  <span data-ttu-id="c30d3-109">Fare clic sulla scheda **Token di traccia** .</span><span class="sxs-lookup"><span data-stu-id="c30d3-109">Click the **Tracer Tokens** tab.</span></span>  
  
4.  <span data-ttu-id="c30d3-110">Fare clic su **Inserisci utilità di traccia**.</span><span class="sxs-lookup"><span data-stu-id="c30d3-110">Click **Insert Tracer**.</span></span>  
  
5.  <span data-ttu-id="c30d3-111">Visualizzare il tempo trascorso per il token di traccia nelle colonne **Dal server di pubblicazione al server di distribuzione**, **Dal server di distribuzione al Sottoscrittore**e **Latenza totale**.</span><span class="sxs-lookup"><span data-stu-id="c30d3-111">View elapsed time for the tracer token in the following columns: **Publisher to Distributor**, **Distributor to Subscriber**, **Total Latency**.</span></span> <span data-ttu-id="c30d3-112">Il valore **in sospeso** indica che il token non ha raggiunto un determinato punto.</span><span class="sxs-lookup"><span data-stu-id="c30d3-112">A value of **Pending** indicates that the token has not reached a given point.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="c30d3-113">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="c30d3-113">Next Steps</span></span>  
 <span data-ttu-id="c30d3-114">In questa lezione sono stati utilizzati token di traccia per verificare che le modifiche apportate ai dati sono state replicate dal server di pubblicazione al Sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="c30d3-114">In this lesson, you successfully used tracer tokens to validate that data changes are being replicated from the Publisher to the Subscriber.</span></span> <span data-ttu-id="c30d3-115">È anche possibile inserire, aggiornare o eliminare dati nella tabella **Product** nel server di pubblicazione ed eseguire query nella tabella **Product** nel Sottoscrittore per visualizzare tali modifiche dopo la replica.</span><span class="sxs-lookup"><span data-stu-id="c30d3-115">You can also insert, update, or delete data in the **Product** table at the Publisher and query the **Product** table at the Subscriber to view these changes after they are replicated.</span></span>  
  
 <span data-ttu-id="c30d3-116">Questa lezione completa l'esercitazione Replica di dati tra server con connessione continua.</span><span class="sxs-lookup"><span data-stu-id="c30d3-116">This completes the Replicating Data Between Continuously Connected Servers tutorial.</span></span> <span data-ttu-id="c30d3-117">Per un'esercitazione simile che usa la replica di tipo merge, vedere [Esercitazione: Replica di dati con client mobili](tutorial-replicating-data-with-mobile-clients.md).</span><span class="sxs-lookup"><span data-stu-id="c30d3-117">For a similar tutorial that uses merge replication, see [Tutorial: Replicating Data with Mobile Clients](tutorial-replicating-data-with-mobile-clients.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c30d3-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c30d3-118">See Also</span></span>  
 [<span data-ttu-id="c30d3-119">Misurare la latenza e convalidare le connessioni per la replica transazionale</span><span class="sxs-lookup"><span data-stu-id="c30d3-119">Measure Latency and Validate Connections for Transactional Replication</span></span>](monitor/measure-latency-and-validate-connections-for-transactional-replication.md)  
  
  
