---
title: Colonne classificate (data mining) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- content types [data mining]
- STDEV column
- VARIANCE column
- PROBABLILITY column
- PROBABILITY_STDEV column
- columns [data mining], classified
- classified columns [data mining]
- PROBABILITY_VARIANCE column
- SUPPORT column
ms.assetid: 68bf3b78-dc12-497c-898f-b43a45646123
author: minewiskan
ms.author: owend
ms.openlocfilehash: 5c264dfb6a97b8b8f576966e8929f6b0dc51e4ed
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635889"
---
# <a name="classified-columns-data-mining"></a><span data-ttu-id="5c023-102">Colonne classificate (Data mining)</span><span class="sxs-lookup"><span data-stu-id="5c023-102">Classified Columns (Data Mining)</span></span>
  <span data-ttu-id="5c023-103">Quando si definisce una colonna classificata, si crea una relazione tra la colonna corrente e un'altra colonna nella struttura di data mining.</span><span class="sxs-lookup"><span data-stu-id="5c023-103">When you define a classified column, you create a relationship between the current column and another column in the mining structure.</span></span> <span data-ttu-id="5c023-104">Nei dati nella colonna della struttura di data mining definita come colonna classificata sono contenute informazioni relative alle categorie in cui vengono descritti i valori in un'altra colonna nella struttura di data mining.</span><span class="sxs-lookup"><span data-stu-id="5c023-104">The data in the mining structure column that you designate as the classified column contains categorical information that describes the values in another column in the mining structure.</span></span>  
  
 <span data-ttu-id="5c023-105">Si supponga, ad esempio, di disporre di due colonne con dati numerici: una colonna, [Yearly Purchases], contenente gli acquisti annuali totali per cliente per anno solare specifico e l'altra colonna, [Standard Deviations], contenente le deviazioni standard per tali valori.</span><span class="sxs-lookup"><span data-stu-id="5c023-105">For example, suppose you have two columns with numerical data: one column, [Yearly Purchases], contains the total yearly purchases per customer for a specific calendar year, and the other column, [Standard Deviations], contains the standard deviations for those values.</span></span> <span data-ttu-id="5c023-106">In questo caso, è possibile definire la colonna [Yearly Purchases] come classificata e questa relazione potrà essere usata dal modello nell'analisi.</span><span class="sxs-lookup"><span data-stu-id="5c023-106">In this case you could designate the [Yearly Purchases] column as the classified column, and the model would be able to use this relationship in analysis.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5c023-107">Gli algoritmi forniti in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] non supportano l'utilizzo di colonne classificate. Questa funzionalità viene fornita per l'utilizzo nella creazione di algoritmi personalizzati.</span><span class="sxs-lookup"><span data-stu-id="5c023-107">The algorithms provided in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] do not support the use of classified columns; this feature is provided for use in creating custom algorithms.</span></span>  
  
## <a name="defining-a-classified-column"></a><span data-ttu-id="5c023-108">Definizione di una colonna classificata</span><span class="sxs-lookup"><span data-stu-id="5c023-108">Defining a Classified Column</span></span>  
 <span data-ttu-id="5c023-109">Il tipo di dati di una colonna classificata deve essere `Long` o `Double`.</span><span class="sxs-lookup"><span data-stu-id="5c023-109">The data type of a classified column must be either `Long` or `Double`.</span></span>  
  
 <span data-ttu-id="5c023-110">Nell'elenco seguente vengono descritti i tipi di contenuto supportati da [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] per le colonne classificate.</span><span class="sxs-lookup"><span data-stu-id="5c023-110">The following list describes the content types that [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] supports for classified columns.</span></span>  
  
 <span data-ttu-id="5c023-111">**PROBABILITY**</span><span class="sxs-lookup"><span data-stu-id="5c023-111">**PROBABILITY**</span></span>  
 <span data-ttu-id="5c023-112">Il valore della colonna indica la probabilità del valore associato ed è un numero compreso tra 0 e 1.</span><span class="sxs-lookup"><span data-stu-id="5c023-112">The value in the column is the probability of the associated value, and is a number between 0 and 1.</span></span>  
  
 <span data-ttu-id="5c023-113">**VARIANZA**</span><span class="sxs-lookup"><span data-stu-id="5c023-113">**VARIANCE**</span></span>  
 <span data-ttu-id="5c023-114">Il valore della colonna indica la varianza del valore associato.</span><span class="sxs-lookup"><span data-stu-id="5c023-114">The value in the column is the variance of the associated value.</span></span>  
  
 <span data-ttu-id="5c023-115">**STDEV**</span><span class="sxs-lookup"><span data-stu-id="5c023-115">**STDEV**</span></span>  
 <span data-ttu-id="5c023-116">Il valore della colonna indica la deviazione standard del valore associato.</span><span class="sxs-lookup"><span data-stu-id="5c023-116">The value in the column is the standard deviation of the associated value.</span></span>  
  
 <span data-ttu-id="5c023-117">**PROBABILITY_VARIANCE**</span><span class="sxs-lookup"><span data-stu-id="5c023-117">**PROBABILITY_VARIANCE**</span></span>  
 <span data-ttu-id="5c023-118">Il valore della colonna indica la varianza della probabilità per il valore associato.</span><span class="sxs-lookup"><span data-stu-id="5c023-118">The value in the column is the variance of the probability for the associated value.</span></span>  
  
 <span data-ttu-id="5c023-119">**PROBABILITY_STDEV**</span><span class="sxs-lookup"><span data-stu-id="5c023-119">**PROBABILITY_STDEV**</span></span>  
 <span data-ttu-id="5c023-120">Il valore della colonna indica la deviazione standard della probabilità per il valore associato.</span><span class="sxs-lookup"><span data-stu-id="5c023-120">The value in the column is the standard deviation of the probability for the associated value.</span></span>  
  
 <span data-ttu-id="5c023-121">**SUPPORTO**</span><span class="sxs-lookup"><span data-stu-id="5c023-121">**SUPPORT**</span></span>  
 <span data-ttu-id="5c023-122">Il valore della colonna indica il peso o fattore di replica del case del valore associato.</span><span class="sxs-lookup"><span data-stu-id="5c023-122">The value in the column is the weight, or case replication factor, of the associated value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c023-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5c023-123">See Also</span></span>  
 <span data-ttu-id="5c023-124">[Tipi di contenuto &#40;&#41;di data mining](content-types-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="5c023-124">[Content Types &#40;Data Mining&#41;](content-types-data-mining.md) </span></span>  
 <span data-ttu-id="5c023-125">[Strutture di data mining &#40;Analysis Services-&#41;di data mining](mining-structures-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="5c023-125">[Mining Structures &#40;Analysis Services - Data Mining&#41;](mining-structures-analysis-services-data-mining.md) </span></span>  
 [<span data-ttu-id="5c023-126">Tipi di dati &#40;Data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="5c023-126">Data Types &#40;Data Mining&#41;</span></span>](data-types-data-mining.md)  
  
  
