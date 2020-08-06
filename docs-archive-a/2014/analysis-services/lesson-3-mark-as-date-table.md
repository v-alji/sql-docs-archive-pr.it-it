---
title: 'Lezione 4: contrassegnare come tabella data | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: c32cc336-b7d8-4122-9d62-4936344d2315
author: minewiskan
ms.author: owend
ms.openlocfilehash: c3ccc57d770d954e9523196d2393fa9dc2ada5b7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630135"
---
# <a name="lesson-4-mark-as-date-table"></a><span data-ttu-id="73dd4-102">Lezione 4: Contrassegna come tabella data</span><span class="sxs-lookup"><span data-stu-id="73dd4-102">Lesson 4: Mark as Date Table</span></span>
  <span data-ttu-id="73dd4-103">Nella Lezione 2: Aggiungere dati è stata importata una tabella delle dimensioni denominata DimDate.</span><span class="sxs-lookup"><span data-stu-id="73dd4-103">In Lesson 2: Add Data, you imported a dimension table named DimDate.</span></span> <span data-ttu-id="73dd4-104">Nella Lezione 3: Rinominare colonne è stato quindi modificato il nome della tabella DimDate in Data.</span><span class="sxs-lookup"><span data-stu-id="73dd4-104">You then renamed the DimDate table, in Lesson 3: Rename Columns, to simply, Date.</span></span> <span data-ttu-id="73dd4-105">Mentre nel modello questa tabella è ora denominata Date, può anche essere nota come *tabella data*, in quanto sono contenuti dati relativi a data e ora.</span><span class="sxs-lookup"><span data-stu-id="73dd4-105">While in your model this table is now named Date, it can also be known as a *Date table*, in that it contains date and time data.</span></span>  
  
 <span data-ttu-id="73dd4-106">Ogni volta che si usano le funzioni di Business Intelligence per le gerarchie temporali nei calcoli, come accadrà più avanti per creare le misure, è necessario specificare le proprietà della tabella relativa alla data, tra cui una *tabella data* e un identificatore univoco *colonna data* in tale tabella.</span><span class="sxs-lookup"><span data-stu-id="73dd4-106">Whenever you use Time Intelligence functions in calculations, as you will do when you create measures a little later, you must specify date table properties, which include a *Date table* and a unique identifier *Date column* in that table.</span></span> <span data-ttu-id="73dd4-107">È quindi possibile creare relazioni valide tra altre tabelle e la tabella data, che sono necessarie per eseguire calcoli utilizzando le funzioni di Business Intelligence per le gerarchie temporali DAX.</span><span class="sxs-lookup"><span data-stu-id="73dd4-107">You can then create valid relationships between other tables and the Date table; necessary for calculations using DAX time intelligence functions.</span></span>  
  
 <span data-ttu-id="73dd4-108">In questa lezione si contrassegnerà la tabella data importata e rinominata come *tabella data* e la colonna data (nella tabella data) come *colonna data* (identificatore univoco).</span><span class="sxs-lookup"><span data-stu-id="73dd4-108">In this lesson, you will mark the imported and renamed Date table as the *Date table* and the Date column (in the Date table) as the *Date column* (unique identifier).</span></span> <span data-ttu-id="73dd4-109">L'uso della data Name può creare confusione, ma si otterrà presto un'idea.</span><span class="sxs-lookup"><span data-stu-id="73dd4-109">All the use of the name Date can get kind of confusing, but you'll soon get the idea.</span></span>  
  
 <span data-ttu-id="73dd4-110">Tempo stimato per il completamento della lezione: **3 minuti**</span><span class="sxs-lookup"><span data-stu-id="73dd4-110">Estimated time to complete this lesson: **3 minutes**</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="73dd4-111">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="73dd4-111">Prerequisites</span></span>  
 <span data-ttu-id="73dd4-112">Questo argomento fa parte di un'esercitazione sulla creazione di modelli tabulari, con lezioni che è consigliabile completare nell'ordine indicato.</span><span class="sxs-lookup"><span data-stu-id="73dd4-112">This topic is part of a tabular modeling tutorial, which should be completed in order.</span></span> <span data-ttu-id="73dd4-113">Prima di eseguire le attività in questa lezione è necessario aver completato la lezione precedente: [Lezione 3: Rinominare colonne](rename-columns.md).</span><span class="sxs-lookup"><span data-stu-id="73dd4-113">Before performing the tasks in this lesson, you should have completed the previous lesson: [Lesson 3: Rename Columns](rename-columns.md).</span></span>  
  
### <a name="to-set-mark-as-date-table"></a><span data-ttu-id="73dd4-114">Per impostare Contrassegna come tabella data</span><span class="sxs-lookup"><span data-stu-id="73dd4-114">To set Mark as Date Table</span></span>  
  
1.  <span data-ttu-id="73dd4-115">In Progettazione modelli fare clic sulla tabella (scheda) **Data** .</span><span class="sxs-lookup"><span data-stu-id="73dd4-115">In the model designer, click the **Date** table (tab).</span></span>  
  
2.  <span data-ttu-id="73dd4-116">Scegliere **Data**dal menu **tabella** , quindi fare clic su **Contrassegna come tabella data**.</span><span class="sxs-lookup"><span data-stu-id="73dd4-116">Click the **Table** menu, then click **Date**, and then click **Mark as Date Table**.</span></span>  
  
3.  <span data-ttu-id="73dd4-117">Nella casella di riepilogo **Data** della finestra di dialogo **Contrassegna come tabella data** selezionare la colonna **Data** come identificatore univoco.</span><span class="sxs-lookup"><span data-stu-id="73dd4-117">In the **Mark as Date Table** dialog box, in the **Date** listbox, select the **Date** column as the unique identifier.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="73dd4-118">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="73dd4-118">Next Steps</span></span>  
 <span data-ttu-id="73dd4-119">Per continuare questa esercitazione, passare alla lezione successiva: [Lezione 5: Creare relazioni](lesson-4-create-relationships.md).</span><span class="sxs-lookup"><span data-stu-id="73dd4-119">To continue this tutorial, go to the next lesson: [Lesson 5: Create Relationships](lesson-4-create-relationships.md).</span></span>  
  
  
