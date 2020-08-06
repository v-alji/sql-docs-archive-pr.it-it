---
title: Utilizzo del drill-through per recuperare i dati di origine (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- DRILLTHROUGH statement
- retrieving data
- queries [MDX], DRILLTHROUGH statement
- data retrieval [MDX]
ms.assetid: fe0ab170-25a9-45a8-a377-f71a67f77018
author: minewiskan
ms.author: owend
ms.openlocfilehash: 5601a3ddfa7075ed53330e12c260af88648db990
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629062"
---
# <a name="using-drillthrough-to-retrieve-source-data-mdx"></a><span data-ttu-id="2b804-102">Utilizzo dell'istruzione DRILLTHROUGH per il recupero di dati di origine (MDX)</span><span class="sxs-lookup"><span data-stu-id="2b804-102">Using DRILLTHROUGH to Retrieve Source Data (MDX)</span></span>
  <span data-ttu-id="2b804-103">Nel linguaggio MDX (Multidimensional Expressions) è disponibile l'istruzione [DRILLTHROUGH](/sql/mdx/mdx-data-manipulation-drillthrough), che consente di recuperare un set di righe dai dati di origine per una cella di un cubo.</span><span class="sxs-lookup"><span data-stu-id="2b804-103">Multidimensional Expressions (MDX) uses the [DRILLTHROUGH](/sql/mdx/mdx-data-manipulation-drillthrough)statement to retrieve a rowset from the source data for a cube cell.</span></span>  
  
 <span data-ttu-id="2b804-104">Per eseguire un'istruzione `DRILLTHROUGH` su un cubo, è necessario definire un'azione drill-through per tale cubo.</span><span class="sxs-lookup"><span data-stu-id="2b804-104">In order to run a `DRILLTHROUGH` statement on a cube, a drillthrough action must be defined for that cube.</span></span> <span data-ttu-id="2b804-105">Per definire un'azione drill-through, in Progettazione cubi di [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)]nel riquadro **Azioni** fare clic sul pulsante **Nuova azione drill-through**della barra degli strumenti.</span><span class="sxs-lookup"><span data-stu-id="2b804-105">To define a drillthrough action, in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], in Cube Designer, on the **Actions** pane, on the toolbar, click **New Drillthrough Action**.</span></span> <span data-ttu-id="2b804-106">Nella nuova azione drill-through specificare il nome, la destinazione e la condizione dell'azione, nonché le colonne restituite dall'istruzione `DRILLTHROUGH`.</span><span class="sxs-lookup"><span data-stu-id="2b804-106">In the new drillthrough action, specify the action name, target, condition, and the columns that are returned by a `DRILLTHROUGH` statement.</span></span>  
  
## <a name="drillthrough-statement-syntax"></a><span data-ttu-id="2b804-107">Sintassi dell'istruzione DRILLTHROUGH</span><span class="sxs-lookup"><span data-stu-id="2b804-107">DRILLTHROUGH Statement Syntax</span></span>  
 <span data-ttu-id="2b804-108">La sintassi dell'istruzione `DRILLTHROUGH` è la seguente:</span><span class="sxs-lookup"><span data-stu-id="2b804-108">The `DRILLTHROUGH` statement uses the following syntax:</span></span>  
  
```  
<drillthrough> ::= DRILLTHROUGH [<Max_Rows>] [<First_Rowset>] <MDX select> [<Return_Columns>]  
   < Max_Rows> ::= MAXROWS <positive number>  
   <First_Rowset> ::= FIRSTROWSET <positive number>  
   <Return_Columns> ::= RETURN <member or attribute> [, <member or attribute>]  
```  
  
 <span data-ttu-id="2b804-109">La clausola `SELECT` identifica la cella del cubo che contiene i dati di origine da recuperare.</span><span class="sxs-lookup"><span data-stu-id="2b804-109">The `SELECT` clause identifies the cube cell that contains the source data to be retrieved.</span></span> <span data-ttu-id="2b804-110">Questa clausola `SELECT` è identica a una normale istruzione `SELECT` MDX, con la differenza che in questo caso nella clausola `SELECT` è possibile specificare solo un membro per ogni asse.</span><span class="sxs-lookup"><span data-stu-id="2b804-110">This `SELECT` clause is the same to an ordinary MDX `SELECT` statement, except that in the `SELECT` clause only one member can be specified on each axis.</span></span> <span data-ttu-id="2b804-111">Se su un asse sono specificati più membri, verrà generato un errore.</span><span class="sxs-lookup"><span data-stu-id="2b804-111">If more than one member is specified on an axis, an error occurs.</span></span>  
  
 <span data-ttu-id="2b804-112">La sintassi `<Max_Rows>` specifica il numero massimo di righe in ogni set di righe restituito.</span><span class="sxs-lookup"><span data-stu-id="2b804-112">The `<Max_Rows>` syntax specifies the maximum number of the rows in each returned rowset.</span></span> <span data-ttu-id="2b804-113">Se il provider OLE DB utilizzato per connettersi all'origine dei dati non supporta `DBPROP_MAXROWS`, l'impostazione `<Max_Rows>` verrà ignorata.</span><span class="sxs-lookup"><span data-stu-id="2b804-113">If the OLE DB provider that is used to connect to the data source does not support `DBPROP_MAXROWS`, the `<Max_Rows>` setting is ignored.</span></span>  
  
 <span data-ttu-id="2b804-114">La sintassi `<First_Rowset>` identifica la partizione il cui set di righe viene restituito per primo.</span><span class="sxs-lookup"><span data-stu-id="2b804-114">The `<First_Rowset>` syntax identifies the partition whose rowset is returned first.</span></span>  
  
 <span data-ttu-id="2b804-115">La sintassi `<Return_Columns>` identifica le colonne del database sottostante da restituire.</span><span class="sxs-lookup"><span data-stu-id="2b804-115">The `<Return_Columns>` syntax identifies the underlying database columns to be returned.</span></span>  
  
## <a name="drillthrough-statement-example"></a><span data-ttu-id="2b804-116">Esempio di istruzione DRILLTHROUGH</span><span class="sxs-lookup"><span data-stu-id="2b804-116">DRILLTHROUGH Statement Example</span></span>  
 <span data-ttu-id="2b804-117">Nell'esempio seguente viene illustrato l'utilizzo dell'istruzione `DRILLTHROUGH`.</span><span class="sxs-lookup"><span data-stu-id="2b804-117">The following example demonstrates the use of the `DRILLTHROUGH` statement.</span></span> <span data-ttu-id="2b804-118">In questo esempio l'istruzione DRILLTHROUGH esegue una query sugli elementi foglia delle dimensioni Store, Product e Time, lungo la dimensione Stores (l'asse di sezionamento), e quindi restituisce il gruppo di misure del reparto, l'ID del reparto e il nome del dipendente.</span><span class="sxs-lookup"><span data-stu-id="2b804-118">In this example, the DRILLTHROUGH statement queries the leaves of the Store, Product, and Time dimensions along the Stores dimension (the slicer axis), and then returns the department measure group, department ID, and employee's first name.</span></span>  
  
```  
DRILLTHROUGH  
Select {Leaves(Store), Leaves(Product), Leaves(Time),*} on 0  
From Stores  
RETURN [Department MeasureGroup].[Department Id], [Employee].[First Name]  
```  
  
## <a name="see-also"></a><span data-ttu-id="2b804-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2b804-119">See Also</span></span>  
 [<span data-ttu-id="2b804-120">Manipolazione dei dati &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="2b804-120">Manipulating Data &#40;MDX&#41;</span></span>](mdx-data-manipulation-manipulating-data.md)  
  
  
