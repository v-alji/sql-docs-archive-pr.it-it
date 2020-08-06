---
title: Creare relazioni riflessive (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- drawing reflexive relationships
- reflexive relationships
- database diagrams [SQL Server], relationships
ms.assetid: e218363f-faec-46d5-9904-a537fbcc994d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 8e5056b1a5d0d884edbc4fc818fe8c7ef5cc8ad4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630201"
---
# <a name="draw-reflexive-relationships-visual-database-tools"></a><span data-ttu-id="5404a-102">Creazione di relazioni riflessive (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="5404a-102">Draw Reflexive Relationships (Visual Database Tools)</span></span>
  <span data-ttu-id="5404a-103">Le relazioni riflessive consentono di collegare una o più colonne di una tabella con una o più colonne della stessa tabella.</span><span class="sxs-lookup"><span data-stu-id="5404a-103">You create a reflexive relationship to link a column or columns in a table with another column or columns in the same table.</span></span> <span data-ttu-id="5404a-104">Si supponga, ad esempio, che nella tabella `employee` sia presente una colonna `emp_id` e una colonna `mgr_id` .</span><span class="sxs-lookup"><span data-stu-id="5404a-104">For example, suppose the `employee` table has an `emp_id` column and a `mgr_id` column.</span></span> <span data-ttu-id="5404a-105">Poiché ogni responsabile è a sua volta anche un dipendente, è possibile correlare le due colonne tracciando una linea di relazione all'interno della stessa tabella.</span><span class="sxs-lookup"><span data-stu-id="5404a-105">Because each manager is also an employee, you relate these two columns by drawing a relationship line from the table to itself.</span></span> <span data-ttu-id="5404a-106">La relazione assicura che a ciascun ID responsabile aggiunto alla tabella corrisponda un ID dipendente esistente.</span><span class="sxs-lookup"><span data-stu-id="5404a-106">This relationship ensures each manager ID that is added to the table matches an existing employee ID.</span></span>  
  
 <span data-ttu-id="5404a-107">Prima di creare una relazione, è necessario definire una chiave primaria o un vincolo univoco per la tabella.</span><span class="sxs-lookup"><span data-stu-id="5404a-107">Before you create a relationship, you must first define a primary key or unique constraint for your table.</span></span> <span data-ttu-id="5404a-108">In seguito si correlerà la colonna chiave primaria con una colonna corrispondente.</span><span class="sxs-lookup"><span data-stu-id="5404a-108">You then relate the primary key column to a matching column.</span></span> <span data-ttu-id="5404a-109">Una volta creata la relazione, la colonna corrispondente diventerà una chiave esterna della tabella.</span><span class="sxs-lookup"><span data-stu-id="5404a-109">Once you create the relationship, the matching column becomes a foreign key of the table.</span></span>  
  
### <a name="to-draw-a-reflexive-relationship"></a><span data-ttu-id="5404a-110">Per disegnare una relazione riflessiva</span><span class="sxs-lookup"><span data-stu-id="5404a-110">To draw a reflexive relationship</span></span>  
  
1.  <span data-ttu-id="5404a-111">Nel diagramma del database fare clic sul selettore di riga della colonna di database che si desidera correlare a un'altra colonna e trascinare il puntatore all'esterno della tabella finché non viene visualizzata una linea.</span><span class="sxs-lookup"><span data-stu-id="5404a-111">In your database diagram, click the row selector for the database column that you want to relate to another column and drag the pointer outside the table until a line appears.</span></span>  
  
2.  <span data-ttu-id="5404a-112">Trascinare la linea di nuovo sulla tabella selezionata.</span><span class="sxs-lookup"><span data-stu-id="5404a-112">Drag the line back to the selected table.</span></span>  
  
3.  <span data-ttu-id="5404a-113">Rilasciare il pulsante del mouse.</span><span class="sxs-lookup"><span data-stu-id="5404a-113">Release the mouse button.</span></span> <span data-ttu-id="5404a-114">Verrà visualizzata la finestra di dialogo **Tabelle e colonne** .</span><span class="sxs-lookup"><span data-stu-id="5404a-114">The **Tables and Columns** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="5404a-115">Selezionare la colonna chiave esterna e la tabella e la colonna chiave primaria con cui si desidera creare una relazione.</span><span class="sxs-lookup"><span data-stu-id="5404a-115">Select the foreign key column and the primary key table and column with which you want form a relationship.</span></span>  
  
5.  <span data-ttu-id="5404a-116">Scegliere due volte **OK** per creare la relazione.</span><span class="sxs-lookup"><span data-stu-id="5404a-116">Choose **OK** twice to create the relationship.</span></span>  
  
 <span data-ttu-id="5404a-117">Quando si eseguono delle query su una tabella, è possibile utilizzare una relazione riflessiva per creare un self-join.</span><span class="sxs-lookup"><span data-stu-id="5404a-117">When you run queries against a table, you can use a reflexive relationship to create a self-join.</span></span> <span data-ttu-id="5404a-118">Per informazioni sull'esecuzione di query su tabelle con join, vedere [Eseguire query con join &#40;Visual Database Tools&#41;](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="5404a-118">For information about querying tables with joins, see [Query with Joins &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5404a-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5404a-119">See Also</span></span>  
 [<span data-ttu-id="5404a-120">Eseguire query con join &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="5404a-120">Query with Joins &#40;Visual Database Tools&#41;</span></span>](visual-database-tools.md)  
  
  
