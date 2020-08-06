---
title: Esempi di espressioni di raggruppamento (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- data [Reporting Services], grouping
- grouping data
- expressions [Reporting Services], adding
- groups [Reporting Services], expressions
ms.assetid: 34cd0249-fc74-4cf2-ba11-7b072992bfd2
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 128e3fa7aed189fd00072c2c3e961b80f8137c99
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711656"
---
# <a name="group-expression-examples-report-builder-and-ssrs"></a><span data-ttu-id="32256-102">Esempi di espressioni di raggruppamento (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="32256-102">Group Expression Examples (Report Builder and SSRS)</span></span>
  <span data-ttu-id="32256-103">In un'area dati è possibile raggruppare i dati in base a un solo campo oppure creare espressioni più complesse che consentono di identificare i dati in base a quali eseguire il raggruppamento.</span><span class="sxs-lookup"><span data-stu-id="32256-103">In a data region, you can group data by a single field, or create more complex expressions that identify the data on which to group.</span></span> <span data-ttu-id="32256-104">Le espressioni complesse includono riferimenti a più campi o parametri, istruzioni condizionali o codice personalizzato.</span><span class="sxs-lookup"><span data-stu-id="32256-104">Complex expressions include references to multiple fields or parameters, conditional statements, or custom code.</span></span> <span data-ttu-id="32256-105">Quando si definisce un gruppo per un'area dati, queste espressioni vengono aggiunte alle proprietà del **gruppo**.</span><span class="sxs-lookup"><span data-stu-id="32256-105">When you define a group for a data region, you add these expressions to the **Group** properties.</span></span> <span data-ttu-id="32256-106">Per altre informazioni, vedere [Aggiunta o eliminazione di un gruppo in un'area dati &#40;Generatore report e SSRS&#41;](add-or-delete-a-group-in-a-data-region-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="32256-106">For more information, see [Add or Delete a Group in a Data Region &#40;Report Builder and SSRS&#41;](add-or-delete-a-group-in-a-data-region-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="32256-107">Per unire due o più gruppi basati sulle espressioni di campo semplice, aggiungere ogni campo all'elenco delle espressioni di raggruppamento nella definizione del gruppo.</span><span class="sxs-lookup"><span data-stu-id="32256-107">To merge two or more groups that are based on simple field expressions, add each field to the group expressions list in the group definition.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="examples-of-group-expressions"></a><span data-ttu-id="32256-108">Esempi di espressioni di raggruppamento</span><span class="sxs-lookup"><span data-stu-id="32256-108">Examples of Group Expressions</span></span>  
 <span data-ttu-id="32256-109">Nella tabella seguente sono disponibili esempi di espressioni di raggruppamento utilizzabili per la definizione di un gruppo.</span><span class="sxs-lookup"><span data-stu-id="32256-109">The following table provides examples of group expressions that you can use to define a group.</span></span>  
  
|<span data-ttu-id="32256-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="32256-110">Description</span></span>|<span data-ttu-id="32256-111">Expression</span><span class="sxs-lookup"><span data-stu-id="32256-111">Expression</span></span>|  
|-----------------|----------------|  
|<span data-ttu-id="32256-112">Raggruppamento in base al campo `Region` .</span><span class="sxs-lookup"><span data-stu-id="32256-112">Group by the `Region` field.</span></span>|`=Fields!Region.Value`|  
|<span data-ttu-id="32256-113">Raggruppamento in base a cognome e nome.</span><span class="sxs-lookup"><span data-stu-id="32256-113">Group by last name and first name.</span></span>|`=Fields!LastName.Value`<br /><br /> `=Fields!FirstName.Value`|  
|<span data-ttu-id="32256-114">Raggruppamento in base alla prima lettera del cognome.</span><span class="sxs-lookup"><span data-stu-id="32256-114">Group by the first letter of the last name.</span></span>|`=Fields!LastName.Value.Substring(0,1)`|  
|<span data-ttu-id="32256-115">Raggruppamento per parametro, in base alla selezione dell'utente.</span><span class="sxs-lookup"><span data-stu-id="32256-115">Group by parameter, based on user selection.</span></span><br /><br /> <span data-ttu-id="32256-116">In questo esempio il parametro `GroupBy` deve essere basato su un elenco di valori disponibili che fornisce una scelta valida in base a cui eseguire il raggruppamento.</span><span class="sxs-lookup"><span data-stu-id="32256-116">In this example, the parameter `GroupBy` must be based on an available values list that provides a valid choice to group on.</span></span>|`=Fields(Parameters!GroupBy.Value).Value`|  
|<span data-ttu-id="32256-117">Raggruppamento per tre intervalli di età separati:</span><span class="sxs-lookup"><span data-stu-id="32256-117">Group by three separate age ranges:</span></span><br /><br /> <span data-ttu-id="32256-118">"Under 21", "Tra 21 e 50" e "Over 50".</span><span class="sxs-lookup"><span data-stu-id="32256-118">"Under 21", "Between 21 and 50", and "Over 50".</span></span>|`=IIF(First(Fields!Age.Value)<21,"Under 21",(IIF(First(Fields!Age.Value)>=21 AND First(Fields!Age.Value)<=50,"Between 21 and 50","Over 50")))`|  
|<span data-ttu-id="32256-119">Raggruppamento in base a molti intervalli di età.</span><span class="sxs-lookup"><span data-stu-id="32256-119">Group by many age ranges.</span></span> <span data-ttu-id="32256-120">Questo esempio contiene codice personalizzato, scritto in [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] .NET, che restituisce una stringa per gli intervalli seguenti:</span><span class="sxs-lookup"><span data-stu-id="32256-120">This example shows custom code, written in [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] .NET, that returns a string for the following ranges:</span></span><br /><br /> <span data-ttu-id="32256-121">25 o inferiore</span><span class="sxs-lookup"><span data-stu-id="32256-121">25 or Under</span></span><br /><br /> <span data-ttu-id="32256-122">Da 26 a 50</span><span class="sxs-lookup"><span data-stu-id="32256-122">26 to 50</span></span><br /><br /> <span data-ttu-id="32256-123">Da 51 a 75</span><span class="sxs-lookup"><span data-stu-id="32256-123">51 to 75</span></span><br /><br /> <span data-ttu-id="32256-124">Over 75</span><span class="sxs-lookup"><span data-stu-id="32256-124">Over 75</span></span>|`=Code.GetRangeValueByAge(Fields!Age.Value)`<br /><br /> <span data-ttu-id="32256-125">Codice personalizzato:</span><span class="sxs-lookup"><span data-stu-id="32256-125">Custom code:</span></span><br /><br /> `Function GetRangeValueByAge(ByVal age As Integer) As String`<br /><br /> `Select Case age`<br /><br /> `Case 0 To 25`<br /><br /> `GetRangeValueByByAge = "25 or Under"`<br /><br /> `Case 26 To 50`<br /><br /> `GetRangeValueByByAge = "26 to 50"`<br /><br /> `Case 51 to 75`<br /><br /> `GetRangeValueByByAge = "51 to 75"`<br /><br /> `Case Else`<br /><br /> `GetRangeValueByByAge = "Over 75"`<br /><br /> `End Select`<br /><br /> `Return GetRangeValueByByAge`<br /><br /> `End Function`|  
  
## <a name="see-also"></a><span data-ttu-id="32256-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="32256-126">See Also</span></span>  
 <span data-ttu-id="32256-127">[Filtro, raggruppamento e ordinamento di dati &#40;Generatore report e SSRS&#41;](filter-group-and-sort-data-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="32256-127">[Filter, Group, and Sort Data &#40;Report Builder and SSRS&#41;](filter-group-and-sort-data-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="32256-128">[Esempi di espressioni &#40;Generatore report e SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="32256-128">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="32256-129">Riferimenti a codice personalizzato e ad assembly in espressioni in Progettazione report &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="32256-129">Custom Code and Assembly References in Expressions in Report Designer &#40;SSRS&#41;</span></span>](custom-code-and-assembly-references-in-expressions-in-report-designer-ssrs.md)  
  
  
