---
title: Eseguire il join di tabelle su più colonne (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- multiple column joins
- joins [SQL Server], multiple columns
ms.assetid: 56a158bc-a42a-4b78-baad-4721d2d22cd3
author: stevestein
ms.author: sstein
ms.openlocfilehash: dda52fe27b2034242c8cbf458dd010240c792146
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629128"
---
# <a name="join-tables-on-multiple-columns-visual-database-tools"></a><span data-ttu-id="e22c2-102">Join di tabelle su più colonne (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="e22c2-102">Join Tables on Multiple Columns (Visual Database Tools)</span></span>
  <span data-ttu-id="e22c2-103">È possibile unire in join tabelle tramite più colonne,</span><span class="sxs-lookup"><span data-stu-id="e22c2-103">You can join tables with multiple columns.</span></span> <span data-ttu-id="e22c2-104">ossia creare una query che crei una corrispondenza tra le righe di due tabelle solo se soddisfano più condizioni.</span><span class="sxs-lookup"><span data-stu-id="e22c2-104">That is, you can create a query that matches rows from the two tables only if they satisfy multiple conditions.</span></span> <span data-ttu-id="e22c2-105">Se il database contiene una relazione di corrispondenza tra una tabella con una chiave esterna formata da più colonne e una tabella con una chiave primaria di più colonne, sarà possibile utilizzare questa relazione per creare un join a più colonne.</span><span class="sxs-lookup"><span data-stu-id="e22c2-105">If the database contains a relationship matching multiple foreign-key columns in one table to a multicolumn primary key in the other table, you can use this relationship to create a multicolumn join.</span></span> <span data-ttu-id="e22c2-106">Per informazioni dettagliate, vedere [Unione di tabelle in modo automatico &#40;Visual Database Tools&#41;](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="e22c2-106">For details, see [Join Tables Automatically &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span>  
  
 <span data-ttu-id="e22c2-107">Anche se il database non contiene relazioni di chiave esterna su più colonne, sarà possibile creare il join manualmente.</span><span class="sxs-lookup"><span data-stu-id="e22c2-107">Even if the database contains no multi-column foreign-key relationship, you can create the join manually.</span></span>  
  
### <a name="to-manually-create-a-multicolumn-join"></a><span data-ttu-id="e22c2-108">Per creare manualmente un join su più colonne</span><span class="sxs-lookup"><span data-stu-id="e22c2-108">To manually create a multicolumn join</span></span>  
  
1.  <span data-ttu-id="e22c2-109">Aggiungere al [riquadro diagramma](diagram-pane-visual-database-tools.md) le tabelle da unire in join.</span><span class="sxs-lookup"><span data-stu-id="e22c2-109">Add to the [Diagram pane](diagram-pane-visual-database-tools.md) the tables you want to join.</span></span>  
  
2.  <span data-ttu-id="e22c2-110">Trascinare il nome della prima colonna join nella prima finestra di tabella e rilasciarlo nella colonna correlata nella seconda finestra di tabella.</span><span class="sxs-lookup"><span data-stu-id="e22c2-110">Drag the name of the first join column in the first table window and drop it onto the related column in the second table window.</span></span> <span data-ttu-id="e22c2-111">Non è possibile basare un join sulle colonne text, ntext o image.</span><span class="sxs-lookup"><span data-stu-id="e22c2-111">You cannot base a join on text, ntext, or image columns.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e22c2-112">In linea generale, le colonne join devono avere tipi di dati uguali o compatibili.</span><span class="sxs-lookup"><span data-stu-id="e22c2-112">In general, the join columns must be of the same (or compatible) data types.</span></span> <span data-ttu-id="e22c2-113">Se ad esempio la colonna join della prima tabella è una data, dovrà essere correlata a una colonna data nella seconda tabella.</span><span class="sxs-lookup"><span data-stu-id="e22c2-113">For example, if the join column in the first table is a date, you must relate it to a date column in the second table.</span></span> <span data-ttu-id="e22c2-114">D'altra parte, se la prima colonna join contiene un valore intero, anche la colonna join correlata dovrà contenere dati di un tipo intero, anche se di dimensioni diverse.</span><span class="sxs-lookup"><span data-stu-id="e22c2-114">On the other hand, if the first join column is an integer, the related join column must also be of an integer data type, but it can be a different size.</span></span> <span data-ttu-id="e22c2-115">In alcuni casi, tuttavia, è possibile unire in join colonne apparentemente incompatibili tramite la conversione implicita del tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="e22c2-115">However, there may be cases where implicit data type conversions can join seemingly incompatible columns will work.</span></span>  
    >   
    >  <span data-ttu-id="e22c2-116">In [Progettazione query e Progettazione viste](query-and-view-designer-tools-visual-database-tools.md) non verranno verificati i tipi di dati delle colonne usati per creare un join, ma quando si eseguirà la query verrà visualizzato un errore qualora i tipi di dati non siano compatibili.</span><span class="sxs-lookup"><span data-stu-id="e22c2-116">The [Query and View Designer](query-and-view-designer-tools-visual-database-tools.md) will not check the data types of the columns you use to create a join, but when you execute the query, the database will display an error if the data types are not compatible.</span></span>  
  
3.  <span data-ttu-id="e22c2-117">Trascinare il nome della seconda colonna join nella prima finestra di tabella e rilasciarlo nella colonna correlata nella seconda finestra di tabella.</span><span class="sxs-lookup"><span data-stu-id="e22c2-117">Drag the name of the second join column in the first table window and drop it onto the related column in the second table window.</span></span>  
  
4.  <span data-ttu-id="e22c2-118">Ripetere il passaggio 3 per ciascuna coppia di colonne join nelle due tabelle.</span><span class="sxs-lookup"><span data-stu-id="e22c2-118">Repeat step 3 for each additional pair of join columns in the two tables.</span></span>  
  
5.  <span data-ttu-id="e22c2-119">Consente di eseguire la query.</span><span class="sxs-lookup"><span data-stu-id="e22c2-119">Run the query.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e22c2-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e22c2-120">See Also</span></span>  
 [<span data-ttu-id="e22c2-121">Eseguire query con join &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="e22c2-121">Query with Joins &#40;Visual Database Tools&#41;</span></span>](query-with-joins-visual-database-tools.md)  
  
  
