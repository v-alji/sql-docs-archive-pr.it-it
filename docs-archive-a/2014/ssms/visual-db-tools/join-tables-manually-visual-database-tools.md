---
title: Unire tabelle in modo manuale (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- manual joins [SQL Server]
- joins [SQL Server], manual
- joins [SQL Server], creating
ms.assetid: 9c785356-646b-4c87-82d4-25efd6051d9d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 83f7615be3f5f18164dd3ca0f62ef6cbd9167be3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711443"
---
# <a name="join-tables-manually-visual-database-tools"></a><span data-ttu-id="85fbb-102">Unione di tabelle in modo manuale (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="85fbb-102">Join Tables Manually (Visual Database Tools)</span></span>
  <span data-ttu-id="85fbb-103">Quando si aggiungono due o più tabelle a una query, in [Progettazione query e Progettazione viste](visual-database-tools.md) viene effettuato un tentativo per unirle in join sulla base dei dati comuni o delle informazioni archiviate nel database relative alla correlazione delle tabelle.</span><span class="sxs-lookup"><span data-stu-id="85fbb-103">When you add two (or more) tables to a query, the [Query and View Designer](visual-database-tools.md) attempts to join them based on common data or on information stored in the database about how tables are related.</span></span> <span data-ttu-id="85fbb-104">Per informazioni dettagliate, vedere [Unione di tabelle in modo automatico &#40;Visual Database Tools&#41;](join-tables-automatically-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="85fbb-104">For details, see [Join Tables Automatically &#40;Visual Database Tools&#41;](join-tables-automatically-visual-database-tools.md).</span></span> <span data-ttu-id="85fbb-105">Se tuttavia le tabelle non vengono unite in join automaticamente o se si desidera creare ulteriori condizioni di join tra le tabelle, sarà possibile il join manuale.</span><span class="sxs-lookup"><span data-stu-id="85fbb-105">However, if the Query and View Designer has not joined the tables automatically, or if you want to create additional join conditions between tables, you can join tables manually.</span></span>  
  
 <span data-ttu-id="85fbb-106">I join possono essere creati sulla base del confronto tra qualsiasi coppia di colonne, non solo delle colonne che contengono le stesse informazioni.</span><span class="sxs-lookup"><span data-stu-id="85fbb-106">You can create joins based on comparisons between any two columns, not just columns that contain the same information.</span></span> <span data-ttu-id="85fbb-107">Ad esempio, se il database contiene le tabelle `titles` e `roysched`, sarà possibile confrontare i valori nella colonna `ytd_sales` della tabella `titles` con le colonne `lorange` e `hirange` della tabella `roysched` .</span><span class="sxs-lookup"><span data-stu-id="85fbb-107">For example, if your database contains two tables, `titles` and `roysched`, you can compare values in the `ytd_sales` column of the `titles` table against the `lorange` and `hirange` columns in the `roysched` table.</span></span> <span data-ttu-id="85fbb-108">Creando questo join sarà possibile trovare i titoli le cui vendite annuali sono comprese nell'intervallo tra valori bassi e alti per il pagamento dei diritti d'autore.</span><span class="sxs-lookup"><span data-stu-id="85fbb-108">Creating this join would allow you to find titles for which the year-to-date sales falls between the low and high ranges for the royalty payments.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="85fbb-109">Le operazioni di join saranno più rapide se le colonne della condizione di join vengono indicizzate.</span><span class="sxs-lookup"><span data-stu-id="85fbb-109">Joins work fastest if the columns in the join condition have been indexed.</span></span> <span data-ttu-id="85fbb-110">In alcuni casi, la creazione di join su colonne non indicizzate può provocare un rallentamento della query.</span><span class="sxs-lookup"><span data-stu-id="85fbb-110">In some cases, joining on unindexed columns can result in a slow query.</span></span>  
  
### <a name="to-manually-join-tables-or-table-structured-objects"></a><span data-ttu-id="85fbb-111">Per unire in join manualmente tabelle o oggetti con struttura di tabella</span><span class="sxs-lookup"><span data-stu-id="85fbb-111">To manually join tables or table-structured objects</span></span>  
  
1.  <span data-ttu-id="85fbb-112">Aggiungere gli oggetti da unire in join al [riquadro diagramma](diagram-pane-visual-database-tools.md) .</span><span class="sxs-lookup"><span data-stu-id="85fbb-112">Add to the [Diagram pane](diagram-pane-visual-database-tools.md) the objects you want to join.</span></span>  
  
2.  <span data-ttu-id="85fbb-113">Trascinare il nome della colonna join nella prima tabella o nel primo oggetto con struttura di tabella e rilasciarlo nella colonna correlata nella seconda tabella o oggetto con struttura di tabella.</span><span class="sxs-lookup"><span data-stu-id="85fbb-113">Drag the name of the join column in the first table or table-structured object and drop it onto the related column in the second table or table-structured object.</span></span> <span data-ttu-id="85fbb-114">Non è possibile basare un join sulle colonne `text`, `ntext`, o i`mage`.</span><span class="sxs-lookup"><span data-stu-id="85fbb-114">You cannot base a join on `text`, `ntext`, or i`mage` columns.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="85fbb-115">Le colonne join devono avere tipi di dati uguali o compatibili.</span><span class="sxs-lookup"><span data-stu-id="85fbb-115">The join columns must be of the same (or compatible) data types.</span></span> <span data-ttu-id="85fbb-116">Se ad esempio la colonna join della prima tabella è una data, dovrà essere correlata a una colonna data nella seconda tabella.</span><span class="sxs-lookup"><span data-stu-id="85fbb-116">For example, if the join column in the first table is a date, you must relate it to a date column in the second table.</span></span> <span data-ttu-id="85fbb-117">D'altra parte, se la prima colonna join contiene un valore intero, anche la colonna join correlata dovrà contenere dati di un tipo intero, anche se di dimensioni diverse.</span><span class="sxs-lookup"><span data-stu-id="85fbb-117">On the other hand, if the first join column is an integer, the related join column must also be of an integer data type, but it can be a different size.</span></span> <span data-ttu-id="85fbb-118">In Progettazione query e Progettazione viste non verranno verificati i tipi di dati delle colonne utilizzati per creare un join, ma quando si eseguirà la query verrà visualizzato un errore qualora i tipi di dati non siano compatibili.</span><span class="sxs-lookup"><span data-stu-id="85fbb-118">The Query and View Designer will not check the data types of the columns you use to create a join, but when you execute the query, the database will display an error if the data types are not compatible.</span></span>  
  
3.  <span data-ttu-id="85fbb-119">Se necessario, cambiare l'operatore di join. L'operatore di join predefinito è il segno di uguale (=).</span><span class="sxs-lookup"><span data-stu-id="85fbb-119">If necessary, change the join operator; by default, the operator is an equal sign (=).</span></span> <span data-ttu-id="85fbb-120">Per informazioni dettagliate, vedere [Modifica di operatori di join &#40;Visual Database Tools&#41;](modify-join-operators-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="85fbb-120">For details, see [Modify Join Operators &#40;Visual Database Tools&#41;](modify-join-operators-visual-database-tools.md).</span></span>  
  
 <span data-ttu-id="85fbb-121">In Progettazione query e Progettazione viste verrà aggiunta una clausola INNER JOIN all'istruzione SQL nel [riquadro SQL](sql-pane-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="85fbb-121">The Query and View Designer adds an INNER JOIN clause to the SQL statement in the [SQL pane](sql-pane-visual-database-tools.md).</span></span> <span data-ttu-id="85fbb-122">È possibile trasformare il tipo in outer join.</span><span class="sxs-lookup"><span data-stu-id="85fbb-122">You can change the type to an outer join.</span></span> <span data-ttu-id="85fbb-123">Per informazioni dettagliate, vedere [Creazione di join esterni &#40;Visual Database Tools&#41;](create-outer-joins-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="85fbb-123">For details see [Create Outer Joins &#40;Visual Database Tools&#41;](create-outer-joins-visual-database-tools.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85fbb-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="85fbb-124">See Also</span></span>  
 [<span data-ttu-id="85fbb-125">Eseguire query con join &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="85fbb-125">Query with Joins &#40;Visual Database Tools&#41;</span></span>](query-with-joins-visual-database-tools.md)  
  
  
