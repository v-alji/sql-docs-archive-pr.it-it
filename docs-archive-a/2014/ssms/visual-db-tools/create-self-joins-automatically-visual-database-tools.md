---
title: Creare self-join in modo automatico (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- automatic joins
- self-joins
- joins [SQL Server], self
ms.assetid: f9ec90e8-3aad-415c-a5c4-8dfa9540e37f
author: stevestein
ms.author: sstein
ms.openlocfilehash: 4a428a44d33b5990e849772b43841df472ca7f6c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623703"
---
# <a name="create-self-joins-automatically-visual-database-tools"></a><span data-ttu-id="d1590-102">Creare self-join in modo automatico (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="d1590-102">Create Self-Joins Automatically (Visual Database Tools)</span></span>
  <span data-ttu-id="d1590-103">Se una tabella ha una relazione riflessiva nel database, sarà possibile metterla in join con se stessa automaticamente.</span><span class="sxs-lookup"><span data-stu-id="d1590-103">If a table has a reflexive relationship in the database, you can join it to itself automatically.</span></span>  
  
### <a name="to-create-a-self-join-automatically"></a><span data-ttu-id="d1590-104">Per creare automaticamente un self-join</span><span class="sxs-lookup"><span data-stu-id="d1590-104">To create a self-join automatically</span></span>  
  
1.  <span data-ttu-id="d1590-105">Aggiungere la tabella appropriata al [riquadro Diagramma](visual-database-tools.md) .</span><span class="sxs-lookup"><span data-stu-id="d1590-105">Add to the [Diagram pane](visual-database-tools.md) the table you want to work with.</span></span>  
  
2.  <span data-ttu-id="d1590-106">Aggiungere nuovamente la stessa tabella in modo che venga visualizzata due volte nel riquadro Diagramma.</span><span class="sxs-lookup"><span data-stu-id="d1590-106">Add the same table again, so that the Diagram pane shows the same table twice within the Diagram pane.</span></span>  
  
     <span data-ttu-id="d1590-107">In [Progettazione query e Progettazione viste](query-and-view-designer-tools-visual-database-tools.md) verrà assegnato un alias alla seconda istanza aggiungendo un numero sequenziale al nome della tabella.</span><span class="sxs-lookup"><span data-stu-id="d1590-107">The [Query and View Designer](query-and-view-designer-tools-visual-database-tools.md) assigns an alias to the second instance by adding a sequential number to the table name.</span></span> <span data-ttu-id="d1590-108">Inoltre, verrà inserita una linea di join tra i due rettangoli che rappresentano i due diversi tipi di partecipazione della tabella nella query.</span><span class="sxs-lookup"><span data-stu-id="d1590-108">In addition, the Query and View Designer creates a join line between the two rectangles representing the two different ways the table participates in the query.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1590-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d1590-109">See Also</span></span>  
 [<span data-ttu-id="d1590-110">Eseguire query con join &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="d1590-110">Query with Joins &#40;Visual Database Tools&#41;</span></span>](query-with-joins-visual-database-tools.md)  
  
  
