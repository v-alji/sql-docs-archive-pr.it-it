---
title: 'Esercitazione: Uso del tipo di dati hierarchyid | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- tutorials [hierarchyid]
- hierarchyid [Database Engine], tutorial
ms.assetid: 5a7f7cfd-7faf-439f-8085-8fd6bf7db355
author: stevestein
ms.author: sstein
ms.openlocfilehash: a735b4c2b51e1c680c8129647733ce1efd9f9984
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626617"
---
# <a name="tutorial-using-the-hierarchyid-data-type"></a><span data-ttu-id="ad079-102">Esercitazione: Utilizzo del tipo di dati hierarchyid</span><span class="sxs-lookup"><span data-stu-id="ad079-102">Tutorial: Using the hierarchyid Data Type</span></span>
  <span data-ttu-id="ad079-103">Questa esercitazione è destinata agli utenti che hanno esperienza nell'utilizzo di [!INCLUDE[tsql](../../includes/tsql-md.md)], ma che sono nuovi al tipo di dati `hierarchyid`.</span><span class="sxs-lookup"><span data-stu-id="ad079-103">This tutorial is intended for users who are experienced with [!INCLUDE[tsql](../../includes/tsql-md.md)], but are new to the `hierarchyid` data type.</span></span>  
  
## <a name="what-you-will-learn"></a><span data-ttu-id="ad079-104">Lezioni dell'esercitazione</span><span class="sxs-lookup"><span data-stu-id="ad079-104">What You Will Learn</span></span>  
 <span data-ttu-id="ad079-105">L'esercitazione è suddivisa in due lezioni:</span><span class="sxs-lookup"><span data-stu-id="ad079-105">This tutorial is divided into two lessons:</span></span>  
  
 [<span data-ttu-id="ad079-106">Lezione 1: Conversione di una tabella in una struttura gerarchica</span><span class="sxs-lookup"><span data-stu-id="ad079-106">Lesson 1: Converting a Table to a Hierarchical Structure</span></span>](lesson-1-converting-a-table-to-a-hierarchical-structure.md)  
 <span data-ttu-id="ad079-107">In questa lezione, si prende in considerazione una tabella del dipendente esistente strutturata come una gerarchia padre/figlio e si spostano i dati nella nuova tabella che rappresenta la gerarchia utilizzando il tipo di dati `hierarchyid`.</span><span class="sxs-lookup"><span data-stu-id="ad079-107">In this lesson, you take an existing employee table that is structured as a parent/child hierarchy and move the data into a new table that represents the hierarchy by using the `hierarchyid` data type.</span></span> <span data-ttu-id="ad079-108">Questa lezione richiede il database di esempio [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ad079-108">This lesson requires the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database.</span></span>  
  
 [<span data-ttu-id="ad079-109">Lezione 2: Creazione e gestione di dati in una tabella gerarchica</span><span class="sxs-lookup"><span data-stu-id="ad079-109">Lesson 2: Creating and Managing Data in a Hierarchical Table</span></span>](lesson-2-creating-and-managing-data-in-a-hierarchical-table.md)  
 <span data-ttu-id="ad079-110">In questa lezione, viene creata una tabella utilizzando il tipo di dati `hierarchyid` per rappresentare la struttura della gerarchia.</span><span class="sxs-lookup"><span data-stu-id="ad079-110">In this lesson, you create a table by using the `hierarchyid` data type to represent the hierarchy structure.</span></span> <span data-ttu-id="ad079-111">Pertanto, si modificano i dati della tabella utilizzando i metodi gerarchici.</span><span class="sxs-lookup"><span data-stu-id="ad079-111">Then, you manipulate the data in the table by using the hierarchical methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ad079-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ad079-112">Requirements</span></span>  
 <span data-ttu-id="ad079-113">È necessario che nel sistema siano installati i componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="ad079-113">Your system must have the following installed:</span></span>  
  
-   <span data-ttu-id="ad079-114">Qualsiasi edizione di [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="ad079-114">Any edition of [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] or later.</span></span>  
  
-   <span data-ttu-id="ad079-115">[!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] Express.</span><span class="sxs-lookup"><span data-stu-id="ad079-115">Either [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] Express.</span></span>  
  
-   <span data-ttu-id="ad079-116">Internet Explorer 6 o versioni successive.</span><span class="sxs-lookup"><span data-stu-id="ad079-116">Internet Explorer 6 or a later version.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad079-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ad079-117">See Also</span></span>  
 <span data-ttu-id="ad079-118">[Esercitazione: Introduzione con l'motore di database](../tutorial-getting-started-with-the-database-engine.md) </span><span class="sxs-lookup"><span data-stu-id="ad079-118">[Tutorial: Getting Started with the Database Engine](../tutorial-getting-started-with-the-database-engine.md) </span></span>  
 <span data-ttu-id="ad079-119">[Esercitazione: scrittura di istruzioni Transact-SQL](../../t-sql/tutorial-writing-transact-sql-statements.md) </span><span class="sxs-lookup"><span data-stu-id="ad079-119">[Tutorial: Writing Transact-SQL Statements](../../t-sql/tutorial-writing-transact-sql-statements.md) </span></span>  
 <span data-ttu-id="ad079-120">[Riferimento al metodo con tipo di dati hierarchyid](/sql/t-sql/data-types/hierarchyid-data-type-method-reference) </span><span class="sxs-lookup"><span data-stu-id="ad079-120">[hierarchyid Data Type Method Reference](/sql/t-sql/data-types/hierarchyid-data-type-method-reference) </span></span>  
 <span data-ttu-id="ad079-121">[Dati gerarchici &#40;SQL Server&#41;](../hierarchical-data-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="ad079-121">[Hierarchical Data &#40;SQL Server&#41;](../hierarchical-data-sql-server.md) </span></span>  
 [<span data-ttu-id="ad079-122">hierarchyid &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ad079-122">hierarchyid &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/hierarchyid-data-type-method-reference)  
  
  
