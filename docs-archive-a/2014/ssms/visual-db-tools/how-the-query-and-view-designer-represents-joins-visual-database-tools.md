---
title: Rappresentazione di join in Progettazione query e Progettazione viste (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL pane [Visual Database Tools]
- joins [SQL Server], Query and View Designer
- Diagram pane [Visual Database Tools]
ms.assetid: 20a99dcb-83bd-4aa6-9139-92e2e5ba4887
author: stevestein
ms.author: sstein
ms.openlocfilehash: 55fdea533436f9fa7c2a902667b3166085c27e99
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629684"
---
# <a name="how-the-query-and-view-designer-represents-joins-visual-database-tools"></a><span data-ttu-id="d2023-102">Rappresentazione di join in Progettazione query e Progettazione viste (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="d2023-102">How the Query and View Designer Represents Joins (Visual Database Tools)</span></span>
  <span data-ttu-id="d2023-103">Se due o più tabelle sono unite tramite join, in [Progettazione query e Progettazione viste](visual-database-tools.md) il join verrà rappresentato in forma grafica all'interno del [riquadro Diagramma](diagram-pane-visual-database-tools.md) e mediante la sintassi SQL all'interno del [riquadro SQL](sql-pane-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="d2023-103">If tables are joined, the [Query and View Designer](visual-database-tools.md) represents the join graphically in the [Diagram pane](diagram-pane-visual-database-tools.md) and by using SQL syntax in the [SQL pane](sql-pane-visual-database-tools.md).</span></span>  
  
## <a name="diagram-pane"></a><span data-ttu-id="d2023-104">Riquadro Diagramma</span><span class="sxs-lookup"><span data-stu-id="d2023-104">Diagram Pane</span></span>  
 <span data-ttu-id="d2023-105">Nel riquadro Diagramma verrà visualizzata una linea di join fra le colonne di dati coinvolte nel join.</span><span class="sxs-lookup"><span data-stu-id="d2023-105">In the Diagram pane the Query and View Designer displays a join line between the data columns involved in the join.</span></span> <span data-ttu-id="d2023-106">In Progettazione query e Progettazione viste verrà visualizzata una linea di join per ogni condizione di join.</span><span class="sxs-lookup"><span data-stu-id="d2023-106">The Query and View Designer displays one join line for each join condition.</span></span> <span data-ttu-id="d2023-107">La seguente figura mostra, ad esempio, una linea di join fra due tabelle unite in join:</span><span class="sxs-lookup"><span data-stu-id="d2023-107">For example, the following illustration shows a join line between two tables that are joined:</span></span>  
  
 <span data-ttu-id="d2023-108">![Linea di join che illustra la relazione tra le due tabelle](../../database-engine/media//dv3wbig.gif "Linea di join che illustra la relazione tra le due tabelle")</span><span class="sxs-lookup"><span data-stu-id="d2023-108">![Join line shows relationship between two tables](../../database-engine/media//dv3wbig.gif "Join line shows relationship between two tables")</span></span>  
  
 <span data-ttu-id="d2023-109">Se le tabelle sono unite da più condizioni di join, verranno visualizzate più linee di join, come nel seguente esempio:</span><span class="sxs-lookup"><span data-stu-id="d2023-109">If tables are joined using more than one join condition, the Query and View Designer displays multiple join lines, as in the following example:</span></span>  
  
 <span data-ttu-id="d2023-110">![Tabelle unite con più di una condizione di join](../../database-engine/media//dv3w9n1.gif "Tabelle unite con più di una condizione di join")</span><span class="sxs-lookup"><span data-stu-id="d2023-110">![Tables joined using more than one join condition](../../database-engine/media//dv3w9n1.gif "Tables joined using more than one join condition")</span></span>  
  
 <span data-ttu-id="d2023-111">Se le colonne di dati unite in join non vengono visualizzate, ad esempio perché il rettangolo che rappresenta la tabella o l'oggetto con struttura a tabella è ridotto a icona o il join utilizza un'espressione, in Progettazione query e Progettazione viste viene inserita la linea di join nella barra del titolo del rettangolo che rappresenta la tabella o l'oggetto con struttura a tabella.</span><span class="sxs-lookup"><span data-stu-id="d2023-111">If the joined data columns are not displayed (for example, the rectangle representing the table or table-structured object is minimized or the join involves an expression), the Query and View Designer places the join line at the title bar of the rectangle representing the table or table-structured object.</span></span>  
  
 <span data-ttu-id="d2023-112">La forma dell'icona al centro della linea di join indica come le tabelle o gli oggetti con struttura a tabella sono uniti in join.</span><span class="sxs-lookup"><span data-stu-id="d2023-112">The shape of the icon in the middle of the join line indicates how the tables or table-structured objects are joined.</span></span> <span data-ttu-id="d2023-113">Se la clausola di join utilizza un operatore diverso da uguale (=), tale operatore verrà visualizzato nell'icona della linea di join.</span><span class="sxs-lookup"><span data-stu-id="d2023-113">If the join clause uses an operator other than equal (=), the operator appears in the join line icon.</span></span> <span data-ttu-id="d2023-114">Nella seguente tabella sono elencate le icone visualizzate nella linea di join.</span><span class="sxs-lookup"><span data-stu-id="d2023-114">The following table lists the icons that appear in the join line.</span></span>  
  
|<span data-ttu-id="d2023-115">**Icona della linea di join**</span><span class="sxs-lookup"><span data-stu-id="d2023-115">**Join line icon**</span></span>|<span data-ttu-id="d2023-116">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="d2023-116">**Description**</span></span>|  
|------------------------|---------------------|  
|<span data-ttu-id="d2023-117">![Icona di Visual Database Tools](../../database-engine/media//dv3wbih.gif "Icona di Visual Database Tools")</span><span class="sxs-lookup"><span data-stu-id="d2023-117">![Visual Database Tools icon](../../database-engine/media//dv3wbih.gif "Visual Database Tools icon")</span></span>|<span data-ttu-id="d2023-118">Inner join (creato con il segno di uguale).</span><span class="sxs-lookup"><span data-stu-id="d2023-118">Inner join (created using an equal sign).</span></span>|  
|<span data-ttu-id="d2023-119">![Icona di Visual Database Tools](../../database-engine/media//dv3wbii.gif "Icona di Visual Database Tools")</span><span class="sxs-lookup"><span data-stu-id="d2023-119">![Visual Database Tools icon](../../database-engine/media//dv3wbii.gif "Visual Database Tools icon")</span></span>|<span data-ttu-id="d2023-120">Inner join basato sull'operatore "maggiore di".</span><span class="sxs-lookup"><span data-stu-id="d2023-120">Inner join based on the "greater than" operator.</span></span>|  
|<span data-ttu-id="d2023-121">![Icona di Visual Database Tools](../../database-engine/media//dv3wbij.gif "Icona di Visual Database Tools")</span><span class="sxs-lookup"><span data-stu-id="d2023-121">![Visual Database Tools icon](../../database-engine/media//dv3wbij.gif "Visual Database Tools icon")</span></span>|<span data-ttu-id="d2023-122">Outer join in cui verranno incluse tutte le righe della tabella rappresentata a sinistra, anche se non hanno alcuna corrispondenza nella tabella correlata.</span><span class="sxs-lookup"><span data-stu-id="d2023-122">Outer join in which all rows from the table represented on the left will be included, even if they do not have matches in the related table.</span></span>|  
|<span data-ttu-id="d2023-123">![Icona di Visual Database Tools](../../database-engine/media//dv3wbik.gif "Icona di Visual Database Tools")</span><span class="sxs-lookup"><span data-stu-id="d2023-123">![Visual Database Tools icon](../../database-engine/media//dv3wbik.gif "Visual Database Tools icon")</span></span>|<span data-ttu-id="d2023-124">Outer join in cui verranno incluse tutte le righe della tabella rappresentata a destra, anche se non hanno alcuna corrispondenza nella tabella correlata.</span><span class="sxs-lookup"><span data-stu-id="d2023-124">Outer join in which all rows from the table represented on the right will be included, even if they do not have matches in the related table.</span></span>|  
|<span data-ttu-id="d2023-125">![Icona di Visual Database Tools](../../database-engine/media//dv3wbil.gif "Icona di Visual Database Tools")</span><span class="sxs-lookup"><span data-stu-id="d2023-125">![Visual Database Tools icon](../../database-engine/media//dv3wbil.gif "Visual Database Tools icon")</span></span>|<span data-ttu-id="d2023-126">Full outer join in cui verranno incluse tutte le righe di entrambe le tabelle, anche se non hanno alcuna corrispondenza nella tabella correlata.</span><span class="sxs-lookup"><span data-stu-id="d2023-126">Full outer join in which all rows from both tables will be included, even if they do not have matches in the related table.</span></span>|  
  
 <span data-ttu-id="d2023-127">I simboli alle estremità della linea di join indicano il tipo di join.</span><span class="sxs-lookup"><span data-stu-id="d2023-127">The symbols on the ends of the join line indicate the type of join.</span></span> <span data-ttu-id="d2023-128">Nella seguente tabella sono elencati i tipi di join e le icone visualizzate alle estremità della linea di join.</span><span class="sxs-lookup"><span data-stu-id="d2023-128">The following table lists the types of joins and the icons displayed on the ends of the join line.</span></span>  
  
|<span data-ttu-id="d2023-129">**Icona alle estremità di una linea di join**</span><span class="sxs-lookup"><span data-stu-id="d2023-129">**Icon on ends of join line**</span></span>|<span data-ttu-id="d2023-130">**Tipo di join**</span><span class="sxs-lookup"><span data-stu-id="d2023-130">**Type of join**</span></span>|  
|-----------------------------------|----------------------|  
|<span data-ttu-id="d2023-131">![Icona di Visual Database Tools](../../database-engine/media//dv3wbim.gif "Icona di Visual Database Tools")</span><span class="sxs-lookup"><span data-stu-id="d2023-131">![Visual Database Tools icon](../../database-engine/media//dv3wbim.gif "Visual Database Tools icon")</span></span>|<span data-ttu-id="d2023-132">Join uno-a-uno.</span><span class="sxs-lookup"><span data-stu-id="d2023-132">One-to-one join.</span></span>|  
|<span data-ttu-id="d2023-133">![Icona di Visual Database Tools](../../database-engine/media//dv3wbin.gif "Icona di Visual Database Tools")</span><span class="sxs-lookup"><span data-stu-id="d2023-133">![Visual Database Tools icon](../../database-engine/media//dv3wbin.gif "Visual Database Tools icon")</span></span>|<span data-ttu-id="d2023-134">Join uno-a-molti.</span><span class="sxs-lookup"><span data-stu-id="d2023-134">One-to-many join.</span></span>|  
|<span data-ttu-id="d2023-135">![Icona di Visual Database Tools](../../database-engine/media//dv3wbio.gif "Icona di Visual Database Tools")</span><span class="sxs-lookup"><span data-stu-id="d2023-135">![Visual Database Tools icon](../../database-engine/media//dv3wbio.gif "Visual Database Tools icon")</span></span>|<span data-ttu-id="d2023-136">In Progettazione query e Progettazione viste non è possibile determinare il tipo di join.</span><span class="sxs-lookup"><span data-stu-id="d2023-136">Query and View Designer cannot determine the join type.</span></span> <span data-ttu-id="d2023-137">Questa situazione si verifica perlopiù con join creati manualmente.</span><span class="sxs-lookup"><span data-stu-id="d2023-137">This situation occurs most often when you have created a join manually.</span></span>|  
  
## <a name="sql-pane"></a><span data-ttu-id="d2023-138">riquadro SQL</span><span class="sxs-lookup"><span data-stu-id="d2023-138">SQL Pane</span></span>  
 <span data-ttu-id="d2023-139">Un join può essere rappresentato in vari modi all'interno di un'istruzione SQL.</span><span class="sxs-lookup"><span data-stu-id="d2023-139">A join can be expressed in a number of ways in an SQL statement.</span></span> <span data-ttu-id="d2023-140">La sintassi esatta dipende dal database utilizzato e dalla modalità di definizione del join.</span><span class="sxs-lookup"><span data-stu-id="d2023-140">The exact syntax depends on the database you are using and on how you have defined the join.</span></span>  
  
 <span data-ttu-id="d2023-141">Le opzioni della sintassi per il join di tabelle comprendono:</span><span class="sxs-lookup"><span data-stu-id="d2023-141">Syntax options for joining tables include:</span></span>  
  
-   <span data-ttu-id="d2023-142">**Qualificatore JOIN per la clausola FROM**.</span><span class="sxs-lookup"><span data-stu-id="d2023-142">**JOIN qualifier for the FROM clause**.</span></span>   <span data-ttu-id="d2023-143">Le parole chiave INNER e OUTER specificano il tipo di join.</span><span class="sxs-lookup"><span data-stu-id="d2023-143">The keywords INNER and OUTER specify the join type.</span></span> <span data-ttu-id="d2023-144">La sintassi è quella standard per ANSI 92 SQL.</span><span class="sxs-lookup"><span data-stu-id="d2023-144">This syntax is standard for ANSI 92 SQL.</span></span>  
  
     <span data-ttu-id="d2023-145">Se, ad esempio, si esegue il join delle tabelle `publishers` e `pub_info` in base alla colonna `pub_id` di ciascuna tabella, l'istruzione SQL risultante potrebbe essere simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="d2023-145">For example, if you join the `publishers` and `pub_info` tables based on the `pub_id` column in each table, the resulting SQL statement might look like this:</span></span>  
  
    ```  
    SELECT *  
    FROM publishers INNER JOIN pub_info ON  
       publishers.pub_id = pub_info.pub_id  
    ```  
  
     <span data-ttu-id="d2023-146">Se si crea un outer join, verranno utilizzate le parole LEFT OUTER o RIGHT OUTER al posto di INNER.</span><span class="sxs-lookup"><span data-stu-id="d2023-146">If you create an outer join, the words LEFT OUTER or RIGHT OUTER appear in place of the word INNER.</span></span>  
  
-   <span data-ttu-id="d2023-147">**Clausola WHERE che confronta colonne di entrambe le tabelle**.</span><span class="sxs-lookup"><span data-stu-id="d2023-147">**WHERE clause compares columns in both tables**.</span></span>   <span data-ttu-id="d2023-148">La clausola WHERE viene utilizzata quando il database non supporta la sintassi JOIN oppure in caso di immissione manuale.</span><span class="sxs-lookup"><span data-stu-id="d2023-148">A WHERE clause appears if the database does not support the JOIN syntax (or if you entered it yourself).</span></span> <span data-ttu-id="d2023-149">Se il join viene creato nella clausola WHERE, nella clausola FROM saranno indicati i nomi di entrambe le tabelle.</span><span class="sxs-lookup"><span data-stu-id="d2023-149">If the join is created in the WHERE clause, both table names appear in the FROM clause.</span></span>  
  
     <span data-ttu-id="d2023-150">Ad esempio, la seguente istruzione esegue il join delle tabelle `publishers` e `pub_info` .</span><span class="sxs-lookup"><span data-stu-id="d2023-150">For example, the following statement joins the `publishers` and `pub_info` tables.</span></span>  
  
    ```  
    SELECT *  
    FROM publishers, pub_info  
    WHERE publishers.pub_id = pub_info.pub_id  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="d2023-151">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d2023-151">See Also</span></span>  
 <span data-ttu-id="d2023-152">[Eseguire query con join &#40;Visual Database Tools&#41;](query-with-joins-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="d2023-152">[Query with Joins &#40;Visual Database Tools&#41;](query-with-joins-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="d2023-153">Finestra di dialogo Join &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="d2023-153">Join Dialog Box &#40;Visual Database Tools&#41;</span></span>](join-dialog-box-visual-database-tools.md)  
  
  
