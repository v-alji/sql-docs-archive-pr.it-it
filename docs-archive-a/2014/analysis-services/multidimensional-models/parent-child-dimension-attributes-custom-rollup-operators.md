---
title: Operatori di rollup personalizzati nelle dimensioni padre-figlio | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- child rollup operations
- UnaryOperatorColumn property
- custom rollup operators [Analysis Services]
- unary operators
- parent-child dimensions [Analysis Services]
ms.assetid: a3ddd9fc-5fa3-4227-9322-8c45a5b5c2c3
author: minewiskan
ms.author: owend
ms.openlocfilehash: db12ccc6703ee4863dd3b6bd598d2317b54fce6a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630113"
---
# <a name="custom-rollup-operators-in-parent-child-dimensions"></a><span data-ttu-id="d479d-102">Operatori di rollup personalizzati nelle dimensioni padre-figlio</span><span class="sxs-lookup"><span data-stu-id="d479d-102">Custom Rollup Operators in Parent-Child Dimensions</span></span>
  <span data-ttu-id="d479d-103">Gli operatori personalizzati di rollup rappresentano un modo semplice per determinare la modalità di esecuzione del rollup dei valori padre di una gerarchia padre-figlio.</span><span class="sxs-lookup"><span data-stu-id="d479d-103">Custom rollup operators provide a simple way to control how member values are rolled up into parent values in a parent-child hierarchy.</span></span> <span data-ttu-id="d479d-104">In una dimensione che contiene una relazione padre-figlio, specificare una colonna che contiene operatori unari che determinano il rollup di tutti i membri non calcolati dell'attributo padre.</span><span class="sxs-lookup"><span data-stu-id="d479d-104">In a dimension containing a parent-child relationship, you specify a column that contains unary operators that specify rollup for all noncalculated members of the parent attribute.</span></span> <span data-ttu-id="d479d-105">L'operatore unario viene applicato ai membri ogni volta che i valori dei membri padre vengono valutati.</span><span class="sxs-lookup"><span data-stu-id="d479d-105">The unary operator is applied to members whenever the values of the parent members are evaluated.</span></span>  
  
 <span data-ttu-id="d479d-106">Gli operatori unari vengono archiviati nella colonna definita dalla proprietà `UnaryOperatorColumn` dell'attributo padre e vengono applicati a ogni membro dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="d479d-106">The unary operators are stored in column defined by the `UnaryOperatorColumn` property of the parent attribute, and they are applied to each member of the attribute.</span></span> <span data-ttu-id="d479d-107">La colonna specificata da questa proprietà può risiedere nella tabella della dimensione o in una tabella correlata alla tabella della dimensione da una chiave esterna nella tabella della dimensione.</span><span class="sxs-lookup"><span data-stu-id="d479d-107">The column specified by this property can reside either in the dimension table or in a table related to the dimension table by a foreign key in the dimension table.</span></span>  
  
 <span data-ttu-id="d479d-108">Gli operatori personalizzati di rollup offrono una funzionalità simile, anche se più semplificata, alle formule personalizzate membro.</span><span class="sxs-lookup"><span data-stu-id="d479d-108">Custom rollup operators provide functionality similar to, but more simplified than, custom member formulas.</span></span> <span data-ttu-id="d479d-109">Una formula personalizzata membro utilizza le espressioni MDX (Multidimensional Expressions) per determinare il modo in cui viene eseguito il rollup dei membri.</span><span class="sxs-lookup"><span data-stu-id="d479d-109">A custom member formula uses Multidimensional Expressions (MDX) expressions to determine how the members are rolled up.</span></span> <span data-ttu-id="d479d-110">Un operatore personalizzato di rollup, invece, utilizza un operatore unario semplice per determinare gli effetti del valore di un membro sul relativo membro padre.</span><span class="sxs-lookup"><span data-stu-id="d479d-110">In contrast, a custom rollup operator uses a simple unary operator to determine how the value of a member affects the parent.</span></span> <span data-ttu-id="d479d-111">Le formule personalizzate membro del livello precedente hanno priorità rispetto agli operatori personalizzati di rollup di un livello.</span><span class="sxs-lookup"><span data-stu-id="d479d-111">Custom member formulas of the preceding level in a dimension override a level's custom rollup operator.</span></span>  
  
## <a name="custom-rollup-precedence"></a><span data-ttu-id="d479d-112">Precedenza del rollup personalizzato</span><span class="sxs-lookup"><span data-stu-id="d479d-112">Custom Rollup Precedence</span></span>  
 <span data-ttu-id="d479d-113">In termini di precedenza, gli operatori personalizzati di rollup dell'attributo di origine di un livello di una gerarchia hanno la priorità rispetto alle formule personalizzate membro del livello precedente.</span><span class="sxs-lookup"><span data-stu-id="d479d-113">In terms of precedence, the custom rollup operators of the source attribute for a level in a hierarchy override the custom member formulas of the previous level.</span></span> <span data-ttu-id="d479d-114">Le formule personalizzate membro del livello precedente hanno però priorità rispetto agli operatori personalizzati di rollup di un livello.</span><span class="sxs-lookup"><span data-stu-id="d479d-114">However, the custom member formulas of the preceding level override the custom rollup operators of a level.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d479d-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d479d-115">See Also</span></span>  
 <span data-ttu-id="d479d-116">[Definire formule personalizzate membro](attribute-properties-define-custom-member-formulas.md) </span><span class="sxs-lookup"><span data-stu-id="d479d-116">[Define Custom Member Formulas](attribute-properties-define-custom-member-formulas.md) </span></span>  
 [<span data-ttu-id="d479d-117">Operatori unari nelle dimensioni padre-figlio</span><span class="sxs-lookup"><span data-stu-id="d479d-117">Unary Operators in Parent-Child Dimensions</span></span>](parent-child-dimension-attributes-unary-operators.md)  
  
  
