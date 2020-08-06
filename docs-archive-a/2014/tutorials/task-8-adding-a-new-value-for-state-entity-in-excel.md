---
title: "Attività 8: aggiunta di un nuovo valore per l'entità state in Excel | Microsoft Docs"
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: a763d76b-06a3-4d51-9614-01fc9fb1c158
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: cace99419997e48088420c331a823cdf3639a3ad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719002"
---
# <a name="task-8-adding-a-new-value-for-state-entity-in-excel"></a><span data-ttu-id="a5344-102">Attività 8: Aggiunta di un nuovo valore per l'entità State in Excel</span><span class="sxs-lookup"><span data-stu-id="a5344-102">Task 8: Adding a New Value for State Entity in Excel</span></span>
  <span data-ttu-id="a5344-103">In questa attività viene aggiunto un valore per l'entità State in Excel e viene pubblicata la modifica nel server MDS.</span><span class="sxs-lookup"><span data-stu-id="a5344-103">In this task, you add a value for the State entity in Excel and publish the change to the MDS server.</span></span>  
  
1.  <span data-ttu-id="a5344-104">Per aggiungere un **foglio di lavoro** in Excel, fare clic sulla scheda nuovo nella parte inferiore.</span><span class="sxs-lookup"><span data-stu-id="a5344-104">Add a **work sheet** in Excel by clicking the new tab at the bottom.</span></span>  
  
     <span data-ttu-id="a5344-105">![Excel - Scheda Nuovo foglio di lavoro](../../2014/tutorials/media/et-addinganewvalueforstateentityinexcel-01.jpg "Excel - Scheda Nuovo foglio di lavoro")</span><span class="sxs-lookup"><span data-stu-id="a5344-105">![Excel - New Worksheet Tab](../../2014/tutorials/media/et-addinganewvalueforstateentityinexcel-01.jpg "Excel - New Worksheet Tab")</span></span>  
  
2.  <span data-ttu-id="a5344-106">In **Excel**fare clic sulla scheda **dati master** nel menu, quindi fare clic su **Mostra Esplora** sulla barra multifunzione.</span><span class="sxs-lookup"><span data-stu-id="a5344-106">In **Excel**, click the **Master Data** tab on the menu, and then click **Show Explorer** on the ribbon.</span></span>  
  
3.  <span data-ttu-id="a5344-107">Nel **Esplora dati master**selezionare **Suppliers** per **modello**.</span><span class="sxs-lookup"><span data-stu-id="a5344-107">In the **Master Data Explorer**, select **Suppliers** for **Model**.</span></span> <span data-ttu-id="a5344-108">Verranno visualizzate due entità: **Supplier** e **state** nell'elenco di entità.</span><span class="sxs-lookup"><span data-stu-id="a5344-108">You should see two entities: **Supplier** and **State** in the entity list.</span></span>  
  
4.  <span data-ttu-id="a5344-109">Fare doppio clic su **stato** nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="a5344-109">Double-click **State** in the list.</span></span> <span data-ttu-id="a5344-110">Tutti i membri dell'entità **stato** da MDS devono essere visualizzati nel foglio di foglio.</span><span class="sxs-lookup"><span data-stu-id="a5344-110">All the members of the **State** entity from MDS should be displayed in the worksheet.</span></span>  
  
5.  <span data-ttu-id="a5344-111">A questo punto, aggiungere una riga alla fine con i valori seguenti: **North Carolina** per **nome** e **NC** per il **codice**.</span><span class="sxs-lookup"><span data-stu-id="a5344-111">Now, add a row at the end with the following values: **North Carolina** for **Name** and **NC** for **Code**.</span></span> <span data-ttu-id="a5344-112">La codifica tramite colori consente di differenziare tutti i record nuovi/aggiornati dagli altri record.</span><span class="sxs-lookup"><span data-stu-id="a5344-112">The color coding differentiates any new/updated records from the other records.</span></span>  
  
     <span data-ttu-id="a5344-113">![Excel - Aggiungi Nord Carolina agli Stati](../../2014/tutorials/media/et-addinganewvalueforstateentityinexcel-02.jpg "Excel - Aggiungi Nord Carolina agli Stati")</span><span class="sxs-lookup"><span data-stu-id="a5344-113">![Excel - Add North Carolina to States](../../2014/tutorials/media/et-addinganewvalueforstateentityinexcel-02.jpg "Excel - Add North Carolina to States")</span></span>  
  
6.  <span data-ttu-id="a5344-114">Fare clic su **pubblica** sulla barra multifunzione per pubblicare la modifica in MDS.</span><span class="sxs-lookup"><span data-stu-id="a5344-114">Click **Publish** on the ribbon to publish the change to MDS.</span></span>  
  
     <span data-ttu-id="a5344-115">![Excel - Pulsante Pubblica nella scheda Dati master](../../2014/tutorials/media/et-addinganewvalueforstateentityinexcel-03.jpg "Excel - Pulsante Pubblica nella scheda Dati master")</span><span class="sxs-lookup"><span data-stu-id="a5344-115">![Excel - Publish Button on Master Data Tab](../../2014/tutorials/media/et-addinganewvalueforstateentityinexcel-03.jpg "Excel - Publish Button on Master Data Tab")</span></span>  
  
7.  <span data-ttu-id="a5344-116">Nella finestra di dialogo **pubblica e annota** si noti che è selezionata l'opzione **Usa la stessa annotazione per tutte le modifiche** .</span><span class="sxs-lookup"><span data-stu-id="a5344-116">On the **Publish and Annotate** dialog box, notice that the **Use same annotation for all changes** is selected.</span></span> <span data-ttu-id="a5344-117">È possibile specificare una sola annotazione per tutte le modifiche apportate in questo punto.</span><span class="sxs-lookup"><span data-stu-id="a5344-117">You can enter a single annotation for all the changes here.</span></span>  
  
8.  <span data-ttu-id="a5344-118">Selezionare l'opzione **Controlla modifiche e fornisci annotazioni singolarmente** per specificare l'annotazione per ogni modifica (in questo caso, solo una).</span><span class="sxs-lookup"><span data-stu-id="a5344-118">Select **Review changes and provide annotations individually** option to provide annotation for each change (in this case, only one).</span></span>  
  
     <span data-ttu-id="a5344-119">![Excel - Finestra di dialogo Pubblicazione e annotazione](../../2014/tutorials/media/et-addinganewvalueforstateentityinexcel-04.jpg "Excel - Finestra di dialogo Pubblicazione e annotazione")</span><span class="sxs-lookup"><span data-stu-id="a5344-119">![Excel - Publish and Annotate Dialog Box](../../2014/tutorials/media/et-addinganewvalueforstateentityinexcel-04.jpg "Excel - Publish and Annotate Dialog Box")</span></span>  
  
9. <span data-ttu-id="a5344-120">Fare clic su **pubblica** per pubblicare i dati in MDS.</span><span class="sxs-lookup"><span data-stu-id="a5344-120">Click **Publish** to publish data to MDS.</span></span>  
  
10. <span data-ttu-id="a5344-121">Si noti che la **codifica a colori** per la riga con **North Carolina** come **stato** corrisponde a quella degli altri record ora.</span><span class="sxs-lookup"><span data-stu-id="a5344-121">Notice that **color coding** for the row with **North Carolina** as the **State** is same as other records now.</span></span>  
  
11. <span data-ttu-id="a5344-122">**Facoltativo:** Verificare che il nuovo membro (NC) venga aggiunto all'entità **state** utilizzando **esplora risorse** in **Gestione dati master**.</span><span class="sxs-lookup"><span data-stu-id="a5344-122">**Optional:** Verify that the new member (NC) is added to the **State** entity by using the **Explorer** in **Master Data Manager**.</span></span>  
  
12. <span data-ttu-id="a5344-123">In Excel, fare clic con il pulsante destro del mouse sul foglio di lavoro **stato** in basso e fare clic su **Elimina** per eliminare il foglio di lavoro.</span><span class="sxs-lookup"><span data-stu-id="a5344-123">In Excel, right-click the **State** worksheet at the bottom, and click **Delete** to delete the worksheet.</span></span> <span data-ttu-id="a5344-124">L'eliminazione del foglio di lavoro non comporta l'eliminazione dei dati dal server MDS.</span><span class="sxs-lookup"><span data-stu-id="a5344-124">Deleting the worksheet does not delete any data from the MDS server.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="a5344-125">passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="a5344-125">Next Step</span></span>  
 [<span data-ttu-id="a5344-126">Attività 9: Creazione di una gerarchia derivata tramite Gestione dati master</span><span class="sxs-lookup"><span data-stu-id="a5344-126">Task 9: Creating a Derived Hierarchy using Master Data Manager</span></span>](../../2014/tutorials/task-9-creating-a-derived-hierarchy-using-master-data-manager.md)  
  
  
