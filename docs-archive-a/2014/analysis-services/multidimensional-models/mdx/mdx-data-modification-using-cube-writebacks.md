---
title: Utilizzo di writeback di cubi (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- writeback [Analysis Services], cubes
- cubes [Analysis Services], modifying
- modifying cubes
- UPDATE CUBE statement
- cubes [Analysis Services], writeback
ms.assetid: ae2385fc-7fa0-4f8e-98d7-dcb0a5f0eeea
author: minewiskan
ms.author: owend
ms.openlocfilehash: 3ac43e9206619117c1fc090a594ca32ccbeeeb31
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627441"
---
# <a name="using-cube-writebacks-mdx"></a><span data-ttu-id="8eb10-102">Utilizzo dei writeback dei cubi (MDX)</span><span class="sxs-lookup"><span data-stu-id="8eb10-102">Using Cube Writebacks (MDX)</span></span>
  <span data-ttu-id="8eb10-103">È possibile aggiornare un cubo usando l'istruzione [UPDATE CUBE](/sql/mdx/mdx-data-manipulation-update-cube) .</span><span class="sxs-lookup"><span data-stu-id="8eb10-103">You update a cube by using the [UPDATE CUBE](/sql/mdx/mdx-data-manipulation-update-cube) statement.</span></span> <span data-ttu-id="8eb10-104">Tale istruzione consente di aggiornare una tupla con un valore specifico.</span><span class="sxs-lookup"><span data-stu-id="8eb10-104">This statement lets you update a tuple with a specific value.</span></span> <span data-ttu-id="8eb10-105">Per utilizzare in modo efficace l'istruzione UPDATE CUBE per l'aggiornamento di un cubo, è importante conoscere la sintassi dell'istruzione, le condizioni di errore che possono verificarsi e i possibili effetti degli aggiornamenti su un cubo.</span><span class="sxs-lookup"><span data-stu-id="8eb10-105">To effectively use the UPDATE CUBE statement to update a cube, you have to understand the syntax for the statement, the error conditions that can occur, and the affect that updates can have on a cube.</span></span>  
  
## <a name="update-cube-statement-syntax"></a><span data-ttu-id="8eb10-106">Sintassi dell'istruzione UPDATE CUBE</span><span class="sxs-lookup"><span data-stu-id="8eb10-106">UPDATE CUBE Statement Syntax</span></span>  
 <span data-ttu-id="8eb10-107">La sintassi dell'istruzione UPDATE CUBE è la seguente:</span><span class="sxs-lookup"><span data-stu-id="8eb10-107">The following syntax describes the UPDATE CUBE statement:</span></span>  
  
```  
UPDATE [CUBE] <Cube_Name> SET <tuple>.VALUE = <value> [,<tuple>.VALUE = <value>...]  
 [ USE_EQUAL_ALLOCATION | USE_EQUAL_INCREMENT |  
  USE_WEIGHTED_ALLOCATION [BY <weight value_expression>] |  
  USE_WEIGHTED_INCREMENT [BY <weight value_expression>] ]   
```  
  
 <span data-ttu-id="8eb10-108">Se per la tupla non è stato specificato un set completo di coordinate, per le coordinate non specificate verrà utilizzato il membro predefinito della gerarchia.</span><span class="sxs-lookup"><span data-stu-id="8eb10-108">If a full set of coordinates is not specified for the tuple, the unspecified coordinates will use the default member of the hierarchy.</span></span> <span data-ttu-id="8eb10-109">La tupla identificata deve fare riferimento a una cella aggregata tramite la funzione [Sum](/sql/mdx/sum-mdx) e non deve includere celle con coordinate costituite da membri calcolati.</span><span class="sxs-lookup"><span data-stu-id="8eb10-109">The tuple identified must reference a cell that is aggregated with the [Sum](/sql/mdx/sum-mdx) function, and must not use a calculated member as one of the cell's coordinates.</span></span>  
  
 <span data-ttu-id="8eb10-110">È possibile pensare all'istruzione UPDATE CUBE come a una subroutine che genera una serie di operazioni di writeback singole su celle atomiche.</span><span class="sxs-lookup"><span data-stu-id="8eb10-110">You can think of the UPDATE CUBE statement as a subroutine that generates a series of individual writeback operations to atomic cells.</span></span> <span data-ttu-id="8eb10-111">Tutte queste operazioni di writeback singole contribuiscono a generare la somma specificata.</span><span class="sxs-lookup"><span data-stu-id="8eb10-111">All these individual writeback operations then roll up into the specified sum.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8eb10-112">Quando celle aggiornate non si sovrappongono, la proprietà della stringa di connessione `Update Isolation Level` può essere utilizzata per migliorare le prestazioni di UPDATE CUBE.</span><span class="sxs-lookup"><span data-stu-id="8eb10-112">When updated cells do not overlap, the `Update Isolation Level` connection string property can be used to enhance performance for UPDATE CUBE.</span></span> <span data-ttu-id="8eb10-113">Per altre informazioni, vedere <xref:Microsoft.AnalysisServices.AdomdClient.AdomdConnection.ConnectionString%2A>.</span><span class="sxs-lookup"><span data-stu-id="8eb10-113">For more information, see <xref:Microsoft.AnalysisServices.AdomdClient.AdomdConnection.ConnectionString%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8eb10-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="8eb10-114">Example</span></span>  
 <span data-ttu-id="8eb10-115">È possibile eseguire il test di UPDATE CUBE con il gruppo di misure relativo agli obiettivi vendita nel cubo Adventure Works.</span><span class="sxs-lookup"><span data-stu-id="8eb10-115">You can test UPDATE CUBE using the Sales Targets measure group in the Adventure Works cube.</span></span> <span data-ttu-id="8eb10-116">Questo gruppo di misure è costituito da misure aggregate in base a SUM, vale a dire un requisito per UPDATE CUBE.</span><span class="sxs-lookup"><span data-stu-id="8eb10-116">This measure group consists of measures aggregated by SUM, which is a requirement for UPDATE CUBE.</span></span>  
  
1.  <span data-ttu-id="8eb10-117">Abilitare il writeback per il gruppo di misure relativo agli obiettivi vendita nel database Adventure Works.</span><span class="sxs-lookup"><span data-stu-id="8eb10-117">Enable writeback for the Sales Targets measure group in the Adventure Works database.</span></span> <span data-ttu-id="8eb10-118">In Management Studio fare clic con il pulsante destro del mouse su un gruppo di misure, scegliere **Opzioni writeback**, quindi **Abilita writeback**.</span><span class="sxs-lookup"><span data-stu-id="8eb10-118">In Management Studio, right-click a measure group, point to **Write Back Options**, choose **Enable Writeback**.</span></span>  
  
     <span data-ttu-id="8eb10-119">Viene visualizzata una nuova tabella writeback nella cartella Writeback.</span><span class="sxs-lookup"><span data-stu-id="8eb10-119">You should see a new writeback table in the Writeback folder.</span></span> <span data-ttu-id="8eb10-120">Il nome della tabella è WriteTable_Fact Sales Quota.</span><span class="sxs-lookup"><span data-stu-id="8eb10-120">The table name is WriteTable_Fact Sales Quota.</span></span>  
  
2.  <span data-ttu-id="8eb10-121">Aprire una finestra Query MDX.</span><span class="sxs-lookup"><span data-stu-id="8eb10-121">Open an MDX query window.</span></span> <span data-ttu-id="8eb10-122">Eseguire l'istruzione SELECT riportata di seguito per visualizzare il valore originale:</span><span class="sxs-lookup"><span data-stu-id="8eb10-122">Run the following select statement to view the original value:</span></span>  
  
    ```  
    SELECT [Measures].[Sales Amount Quota] on 0 ,  
    [Employee].[Employee Department].[Title].&[Sales Representative].children on 1  
    FROM [Adventure Works]  
  
    ```  
  
     <span data-ttu-id="8eb10-123">Vengono visualizzate le quote vendite di ogni rappresentante.</span><span class="sxs-lookup"><span data-stu-id="8eb10-123">You should see sales amount quotas for each representative.</span></span>  
  
3.  <span data-ttu-id="8eb10-124">Eseguire l'istruzione UPDATE CUBE per eseguire il writeback di un nuovo valore.</span><span class="sxs-lookup"><span data-stu-id="8eb10-124">Run the update cube statement to write back a new value.</span></span> <span data-ttu-id="8eb10-125">In questo esempio la quota vendite viene impostata su 0.</span><span class="sxs-lookup"><span data-stu-id="8eb10-125">In this example, we are setting the sales amount quota to 0.</span></span> <span data-ttu-id="8eb10-126">Poiché il nuovo valore è pari a 0, non specificare un metodo di allocazione.</span><span class="sxs-lookup"><span data-stu-id="8eb10-126">Because the new value is 0, do not specify an allocation method.</span></span>  
  
    ```  
    UPDATE CUBE [Adventure Works]   
    SET ([Measures].[Sales Amount Quota], [Employee].[Employee Department].[Department].&[Sales]) = 0  
  
    ```  
  
4.  <span data-ttu-id="8eb10-127">Eseguire nuovamente l'istruzione SELECT.</span><span class="sxs-lookup"><span data-stu-id="8eb10-127">Re-run the SELECT statement.</span></span> <span data-ttu-id="8eb10-128">A questo punto viene visualizzato zero per le quote.</span><span class="sxs-lookup"><span data-stu-id="8eb10-128">You should now see zero for the quotas.</span></span>  
  
 <span data-ttu-id="8eb10-129">Il valore writeback è vincolato alla sessione corrente.</span><span class="sxs-lookup"><span data-stu-id="8eb10-129">The writeback value is constrained to the current session.</span></span> <span data-ttu-id="8eb10-130">Per rendere persistente il valore negli utenti e nelle sessioni, elaborare la tabella writeback.</span><span class="sxs-lookup"><span data-stu-id="8eb10-130">To persist the value across users and sessions, process the writeback table.</span></span> <span data-ttu-id="8eb10-131">In Management Studio fare clic con il pulsante destro del mouse su WriteTable_Fact Sales Quota e scegliere **Elabora**.</span><span class="sxs-lookup"><span data-stu-id="8eb10-131">In Management Studio, right-click WriteTable_Fact Sales Quota and choose **Process**.</span></span>  
  
 <span data-ttu-id="8eb10-132">Per specificare un metodo di allocazione, il nuovo valore deve essere maggiore di zero.</span><span class="sxs-lookup"><span data-stu-id="8eb10-132">To specify an allocation method, the new value must be greater than zero.</span></span> <span data-ttu-id="8eb10-133">In questo esempio il nuovo valore di Sales Amount Quota è pari a due milioni e tramite il metodo di allocazione l'importo viene distribuito a tutti i rappresentanti.</span><span class="sxs-lookup"><span data-stu-id="8eb10-133">In this example, the new value for Sales Amount Quota is two million and the allocation method distributes the amount across all sales representatives.</span></span>  
  
```  
UPDATE CUBE [Adventure Works]   
SET ([Measures].[Sales Amount Quota], [Employee].[Employee Department].[Department].&[Sales]) = 2000000   
USE_EQUAL_ALLOCATION  
```  
  
## <a name="error-conditions"></a><span data-ttu-id="8eb10-134">Condizioni di errore</span><span class="sxs-lookup"><span data-stu-id="8eb10-134">Error Conditions</span></span>  
 <span data-ttu-id="8eb10-135">Nella tabella seguente vengono descritte le possibili cause di errore dei writeback e le conseguenze di tali errori.</span><span class="sxs-lookup"><span data-stu-id="8eb10-135">The following table describes both what can cause writebacks to fail and the result of those errors.</span></span>  
  
|<span data-ttu-id="8eb10-136">Condizione di errore</span><span class="sxs-lookup"><span data-stu-id="8eb10-136">Error Condition</span></span>|<span data-ttu-id="8eb10-137">Risultato</span><span class="sxs-lookup"><span data-stu-id="8eb10-137">Result</span></span>|  
|---------------------|------------|  
|<span data-ttu-id="8eb10-138">L'aggiornamento include membri incompatibili della stessa dimensione.</span><span class="sxs-lookup"><span data-stu-id="8eb10-138">Update includes members from the same dimension that do not exist with one another.</span></span>|<span data-ttu-id="8eb10-139">L'aggiornamento non verrà eseguito.</span><span class="sxs-lookup"><span data-stu-id="8eb10-139">Update will fail.</span></span> <span data-ttu-id="8eb10-140">lo spazio del cubo non conterrà la cella a cui è stato fatto riferimento.</span><span class="sxs-lookup"><span data-stu-id="8eb10-140">The cube space will not contain the referenced cell.</span></span>|  
|<span data-ttu-id="8eb10-141">L'aggiornamento include una misura originata da una misura di un tipo senza segno.</span><span class="sxs-lookup"><span data-stu-id="8eb10-141">Update includes a measure sourced to a measure of an unsigned type.</span></span>|<span data-ttu-id="8eb10-142">L'aggiornamento non verrà eseguito.</span><span class="sxs-lookup"><span data-stu-id="8eb10-142">Update will fail.</span></span> <span data-ttu-id="8eb10-143">Per gli incrementi è necessario che la misura possa contenere un valore negativo.</span><span class="sxs-lookup"><span data-stu-id="8eb10-143">Increments require that the measure be able to take a negative value.</span></span>|  
|<span data-ttu-id="8eb10-144">L'aggiornamento include una misura con un'aggregazione diversa dalla somma.</span><span class="sxs-lookup"><span data-stu-id="8eb10-144">Update includes a measure that aggregates other than sum.</span></span>|<span data-ttu-id="8eb10-145">Verrà generato un errore.</span><span class="sxs-lookup"><span data-stu-id="8eb10-145">An error is raised.</span></span>|  
|<span data-ttu-id="8eb10-146">È stato tentato un aggiornamento su un sottocubo.</span><span class="sxs-lookup"><span data-stu-id="8eb10-146">Update was tried on a subcube.</span></span>|<span data-ttu-id="8eb10-147">Verrà generato un errore.</span><span class="sxs-lookup"><span data-stu-id="8eb10-147">An error is raised.</span></span>|  
  
## <a name="affect-of-cube-changes"></a><span data-ttu-id="8eb10-148">Effetti delle modifiche al cubo</span><span class="sxs-lookup"><span data-stu-id="8eb10-148">Affect of Cube Changes</span></span>  
 <span data-ttu-id="8eb10-149">Le modifiche seguenti non hanno effetto su un writeback:</span><span class="sxs-lookup"><span data-stu-id="8eb10-149">The following changes will not have an effect on a writeback:</span></span>  
  
-   <span data-ttu-id="8eb10-150">Elaborazione di un cubo, dei gruppi di misure del cubo o delle dimensioni del cubo.</span><span class="sxs-lookup"><span data-stu-id="8eb10-150">Processing of a cube, the cube's measure groups, or the cube's dimensions.</span></span>  
  
-   <span data-ttu-id="8eb10-151">Aggiunta di attributi a una dimensione.</span><span class="sxs-lookup"><span data-stu-id="8eb10-151">Adding attributes to any dimension.</span></span>  
  
-   <span data-ttu-id="8eb10-152">Aggiunta di una nuova dimensione.</span><span class="sxs-lookup"><span data-stu-id="8eb10-152">Adding a new dimension.</span></span>  
  
-   <span data-ttu-id="8eb10-153">Eliminazione di una dimensione che non include il writeback.</span><span class="sxs-lookup"><span data-stu-id="8eb10-153">Deleting a dimension that does not include the writeback.</span></span>  
  
-   <span data-ttu-id="8eb10-154">Aggiunta, modifica o rimozione di una gerarchia.</span><span class="sxs-lookup"><span data-stu-id="8eb10-154">Adding, modifying, or removing a hierarchy.</span></span>  
  
-   <span data-ttu-id="8eb10-155">Aggiunta di una nuova misura.</span><span class="sxs-lookup"><span data-stu-id="8eb10-155">Adding a new measure.</span></span>  
  
 <span data-ttu-id="8eb10-156">Le modifiche seguenti non possono essere eseguite senza rimuovere i dati di writeback:</span><span class="sxs-lookup"><span data-stu-id="8eb10-156">The following changes cannot be made without removing the writeback data:</span></span>  
  
-   <span data-ttu-id="8eb10-157">Eliminazione di un attributo o della relativa gerarchia, se l'attributo è incluso nel writeback.</span><span class="sxs-lookup"><span data-stu-id="8eb10-157">Deleting an attribute, or its attribute hierarchy, if the attribute is included in the writeback.</span></span> <span data-ttu-id="8eb10-158">È inclusa la rimozione esplicita dell'attributo, o della relativa gerarchia, o la rimozione della dimensione padre dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="8eb10-158">This includes explicitly removing the attribute, or its attribute hierarchy, or removing the attribute's parent dimension.</span></span>  
  
-   <span data-ttu-id="8eb10-159">Eliminazione di una misura inclusa nel writeback.</span><span class="sxs-lookup"><span data-stu-id="8eb10-159">Deleting a measure included in the writeback.</span></span>  
  
-   <span data-ttu-id="8eb10-160">Aggiunta di un attributo privo del livello `(All)` a una dimensione inclusa nel writeback.</span><span class="sxs-lookup"><span data-stu-id="8eb10-160">Adding an attribute without an `(All)` level to a dimension included in the writeback.</span></span>  
  
-   <span data-ttu-id="8eb10-161">Modifica della granularità di una dimensione inclusa nel writeback.</span><span class="sxs-lookup"><span data-stu-id="8eb10-161">Changing the dimension granularity for a dimension included in the writeback.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8eb10-162">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8eb10-162">See Also</span></span>  
 [<span data-ttu-id="8eb10-163">Modifica dei dati &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="8eb10-163">Modifying Data &#40;MDX&#41;</span></span>](mdx-data-modification-modifying-data.md)  
  
  
