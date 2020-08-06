---
title: 'Attività 3: pulizia dei dati rispetto alla Knowledge Base Suppliers | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 647c924a-9b91-4294-8d96-e81416e4e90e
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 13201a8b904a5fc5232b9fa860710e4e39cce67a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720412"
---
# <a name="task-3-cleansing-data-against-the-suppliers-knowledge-base"></a><span data-ttu-id="0792d-102">Attività 3: Pulizia dei dati fornitore rispetto alla Knowledge Base Suppliers</span><span class="sxs-lookup"><span data-stu-id="0792d-102">Task 3: Cleansing Data against the Suppliers Knowledge Base</span></span>
  <span data-ttu-id="0792d-103">In questa attività viene eseguito il processo di pulizia computerizzato.</span><span class="sxs-lookup"><span data-stu-id="0792d-103">In this task, you run the computer-assisted cleansing process.</span></span> <span data-ttu-id="0792d-104">In DQS vengono utilizzati algoritmi e livelli di probabilità avanzati basati sui valori soglia specificati per analizzare i dati rispetto alla Knowledge Base selezionata e procedere quindi alla relativa pulizia.</span><span class="sxs-lookup"><span data-stu-id="0792d-104">DQS uses advanced algorithms and confidence levels based on the threshold values specified to analyze the data against the selected knowledge base, and then cleanse it.</span></span> <span data-ttu-id="0792d-105">Per ulteriori informazioni, vedere [pulizia dei dati tramite la Knowledge Base DQS (interna)](https://msdn.microsoft.com/library/hh213061.aspx) .</span><span class="sxs-lookup"><span data-stu-id="0792d-105">See [Cleansing Data Using DQS (Internal) Knowledge](https://msdn.microsoft.com/library/hh213061.aspx) for more details.</span></span>

1.  <span data-ttu-id="0792d-106">Fare clic su **Avvia** per avviare il processo di pulizia computerizzato.</span><span class="sxs-lookup"><span data-stu-id="0792d-106">Click **Start** to start the computer-assisted cleansing process.</span></span>

     <span data-ttu-id="0792d-107">![Pagina Pulisci del processo di pulizia](../../2014/tutorials/media/et-cleansingdataagainstthesupplierkb-01.jpg "Pagina Pulisci del processo di pulizia")</span><span class="sxs-lookup"><span data-stu-id="0792d-107">![Cleanse Page of the Cleansing Process](../../2014/tutorials/media/et-cleansingdataagainstthesupplierkb-01.jpg "Cleanse Page of the Cleansing Process")</span></span>

2.  <span data-ttu-id="0792d-108">Al termine del processo di pulizia, verificare le **statistiche** nella scheda **Profiler** . Le statistiche di origine forniscono il numero di record elaborati, il numero di record risultanti corretti, il numero di record corretti da DQS, il numero di record che presentano modifiche suggerite da DQS e il numero di record non validi.</span><span class="sxs-lookup"><span data-stu-id="0792d-108">When the cleansing process is completed, review **statistics** in the **Profiler** tab. The Source Statistics provide the number of records processed, number of records that are found to be correct, number of records that DQS corrects, number of records that have changes suggested by DQS, and the number of records that are invalid.</span></span> <span data-ttu-id="0792d-109">Nella casella di riepilogo a destra è possibile visualizzare i valori corretti, quelli suggeriti, nonché la completezza (l'entità della presenza dei dati) e l'accuratezza (la misura entro cui i dati possono essere utilizzati per gli scopi previsti) dei valori per ogni dominio interessato dal processo di pulizia.</span><span class="sxs-lookup"><span data-stu-id="0792d-109">In the list box to the right, you can see the corrected values, suggested values, and the completeness (the extent to which the data is present) and accuracy (the extent to which the data can be used for intended purposes) of values for each domain involved in the cleansing process.</span></span>

     <span data-ttu-id="0792d-110">![Risultati della pulizia](../../2014/tutorials/media/et-cleansingdataagainstthesupplierkb-02.jpg "Risultati della pulizia")</span><span class="sxs-lookup"><span data-stu-id="0792d-110">![Cleansing Results](../../2014/tutorials/media/et-cleansingdataagainstthesupplierkb-02.jpg "Cleansing Results")</span></span>

3.  <span data-ttu-id="0792d-111">Fare clic su **Avanti** per passare alla pagina **Gestisci e visualizza risultati** .</span><span class="sxs-lookup"><span data-stu-id="0792d-111">Click **Next** to switch to **Manage and View Results** page.</span></span>

## <a name="next-step"></a><span data-ttu-id="0792d-112">passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="0792d-112">Next Step</span></span>
 [<span data-ttu-id="0792d-113">Attività 4: Gestione e visualizzazione dei risultati</span><span class="sxs-lookup"><span data-stu-id="0792d-113">Task 4: Manaing and Viewing Results</span></span>](../../2014/tutorials/task-4-manaing-and-viewing-results.md)


