---
title: Operatori nelle espressioni (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: d22dc8b6-4353-40e7-91a1-65e8dae6325d
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: fa8042df39e535425a05414c1e39ee6a12ff2f39
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628438"
---
# <a name="operators-in-expressions-report-builder-and-ssrs"></a><span data-ttu-id="5ae45-102">Operatori nelle espressioni (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="5ae45-102">Operators in Expressions (Report Builder and SSRS)</span></span>
  <span data-ttu-id="5ae45-103">Un operatore è un simbolo che rappresenta le azioni applicate a uno o più termini di un'espressione.</span><span class="sxs-lookup"><span data-stu-id="5ae45-103">An operator is a symbol that represents actions applied to one or more terms in an expression.</span></span> <span data-ttu-id="5ae45-104">In un'espressione sono supportate le categorie di operatori seguenti: aritmetico, di confronto, di concatenazione, logico o bit per bit e di scorrimento bit.</span><span class="sxs-lookup"><span data-stu-id="5ae45-104">The following categories of operators are supported in an expression: arithmetic, comparison, concatenation, logical or bitwise, and bit shift.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="arithmetic"></a><span data-ttu-id="5ae45-105">Aritmetico</span><span class="sxs-lookup"><span data-stu-id="5ae45-105">Arithmetic</span></span>  
 <span data-ttu-id="5ae45-106">Gli operatori aritmetici eseguono operazioni matematiche su due termini numerici in un'espressione.</span><span class="sxs-lookup"><span data-stu-id="5ae45-106">Arithmetic operators perform mathematical operations on two numeric terms in an expression.</span></span>  
  
|<span data-ttu-id="5ae45-107">Operatore</span><span class="sxs-lookup"><span data-stu-id="5ae45-107">Operator</span></span>|<span data-ttu-id="5ae45-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5ae45-108">Description</span></span>|  
|--------------|-----------------|  
|^|<span data-ttu-id="5ae45-109">Eleva un numero alla potenza di un altro numero.</span><span class="sxs-lookup"><span data-stu-id="5ae45-109">Raises a number to the power of another number.</span></span>|  
|*|<span data-ttu-id="5ae45-110">Moltiplica due numeri.</span><span class="sxs-lookup"><span data-stu-id="5ae45-110">Multiplies two numbers.</span></span>|  
|/|<span data-ttu-id="5ae45-111">Divide due numeri e restituisce un risultato a virgola mobile.</span><span class="sxs-lookup"><span data-stu-id="5ae45-111">Divides two numbers and returns a floating-point result.</span></span>|  
|<span data-ttu-id="5ae45-112">\|Divide due numeri e restituisce un risultato intero.</span><span class="sxs-lookup"><span data-stu-id="5ae45-112">\|Divides two numbers and returns an integer result.</span></span>|  
|<span data-ttu-id="5ae45-113">Mod</span><span class="sxs-lookup"><span data-stu-id="5ae45-113">Mod</span></span>|<span data-ttu-id="5ae45-114">Restituisce il resto intero di una divisione,</span><span class="sxs-lookup"><span data-stu-id="5ae45-114">Returns the integer remainder of a division.</span></span> <span data-ttu-id="5ae45-115">ad esempio 7 Mod 5 = 2 perché il resto di 7 diviso 5 è 2.</span><span class="sxs-lookup"><span data-stu-id="5ae45-115">For example, 7 Mod 5 = 2 because the remainder of 7 divided by 5 is 2.</span></span>|  
|+|<span data-ttu-id="5ae45-116">Somma due numeri.</span><span class="sxs-lookup"><span data-stu-id="5ae45-116">Adds two numbers together.</span></span>|  
|-|<span data-ttu-id="5ae45-117">Restituisce la differenza tra due numeri o indica il valore negativo di un termine numerico.</span><span class="sxs-lookup"><span data-stu-id="5ae45-117">Returns the difference between two numbers or indicates the negative value of a numeric term.</span></span>|  
  
### <a name="comparison"></a><span data-ttu-id="5ae45-118">Confronto</span><span class="sxs-lookup"><span data-stu-id="5ae45-118">Comparison</span></span>  
 <span data-ttu-id="5ae45-119">Gli operatori di confronto consentono di confrontare due espressioni.</span><span class="sxs-lookup"><span data-stu-id="5ae45-119">Comparison operators test whether two expressions are the same.</span></span>  
  
|<span data-ttu-id="5ae45-120">Operatore</span><span class="sxs-lookup"><span data-stu-id="5ae45-120">Operator</span></span>|<span data-ttu-id="5ae45-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5ae45-121">Description</span></span>|  
|--------------|-----------------|  
|<|<span data-ttu-id="5ae45-122">Minore di.</span><span class="sxs-lookup"><span data-stu-id="5ae45-122">Less than.</span></span>|  
|\<=|<span data-ttu-id="5ae45-123">Minore o uguale a.</span><span class="sxs-lookup"><span data-stu-id="5ae45-123">Less than or equal to.</span></span>|  
|>|<span data-ttu-id="5ae45-124">Maggiore di.</span><span class="sxs-lookup"><span data-stu-id="5ae45-124">Greater than.</span></span>|  
|>=|<span data-ttu-id="5ae45-125">Maggiore o uguale a.</span><span class="sxs-lookup"><span data-stu-id="5ae45-125">Greater than or equal to.</span></span>|  
|=|<span data-ttu-id="5ae45-126">Uguale a.</span><span class="sxs-lookup"><span data-stu-id="5ae45-126">Equal to.</span></span>|  
|<>|<span data-ttu-id="5ae45-127">Diverso da.</span><span class="sxs-lookup"><span data-stu-id="5ae45-127">Not equal to.</span></span>|  
|<span data-ttu-id="5ae45-128">Simile a</span><span class="sxs-lookup"><span data-stu-id="5ae45-128">Like</span></span>|<span data-ttu-id="5ae45-129">Determina se una stringa di caratteri specifica corrisponde a un modello specificato.</span><span class="sxs-lookup"><span data-stu-id="5ae45-129">Determines whether a specific character string matches a specified pattern.</span></span> <span data-ttu-id="5ae45-130">Il modello può contenere caratteri specifici e caratteri jolly.</span><span class="sxs-lookup"><span data-stu-id="5ae45-130">A pattern can include regular characters and wildcard characters.</span></span> <span data-ttu-id="5ae45-131">In una ricerca in base a un modello i normali caratteri devono corrispondere esattamente ai caratteri specificati nella stringa di caratteri del modello.</span><span class="sxs-lookup"><span data-stu-id="5ae45-131">During pattern matching, regular characters must exactly match the characters specified in the character string.</span></span> <span data-ttu-id="5ae45-132">I caratteri jolly tuttavia possono venire abbinati a frammenti arbitrari della stringa.</span><span class="sxs-lookup"><span data-stu-id="5ae45-132">However, wildcard characters can be matched with arbitrary fragments of the character string.</span></span> <span data-ttu-id="5ae45-133">L'utilizzo di caratteri jolly rende l'operatore LIKE più flessibile rispetto all'utilizzo degli operatori di confronto tra stringhe = e !=.</span><span class="sxs-lookup"><span data-stu-id="5ae45-133">Using wildcard characters makes the LIKE operator more flexible than using the = and != string comparison operators.</span></span><br /><br /> <span data-ttu-id="5ae45-134">Di seguito sono elencati i caratteri che è possibile utilizzare come caratteri jolly:</span><span class="sxs-lookup"><span data-stu-id="5ae45-134">The following lists characters that can be used as wildcards:</span></span><br /><br /> <span data-ttu-id="5ae45-135">**%**: Qualsiasi stringa di zero o più caratteri.</span><span class="sxs-lookup"><span data-stu-id="5ae45-135">**%**: Any string of zero or more characters.</span></span><br /><br /> <span data-ttu-id="5ae45-136">**_**: Qualsiasi carattere singolo.</span><span class="sxs-lookup"><span data-stu-id="5ae45-136">**_**: Any single character.</span></span><br /><br /> <span data-ttu-id="5ae45-137">**[]**: Qualsiasi carattere singolo compreso nell'intervallo specificato (ad esempio, [a-f]) o set (ad esempio, [aeiou]).</span><span class="sxs-lookup"><span data-stu-id="5ae45-137">**[ ]**: Any single character within the specified range (for example, [a-f]) or set (for example, [aeiou]).</span></span><br /><br /> <span data-ttu-id="5ae45-138">**[^]**: Qualsiasi carattere singolo non compreso nell'intervallo specificato (ad esempio, [^ a-f]) o set (ad esempio, [^ aeiou]).</span><span class="sxs-lookup"><span data-stu-id="5ae45-138">**[^]**: Any single character not within the specified range (for example, [^a-f]) or set (for example, [^aeiou]).</span></span>|  
|<span data-ttu-id="5ae45-139">Is</span><span class="sxs-lookup"><span data-stu-id="5ae45-139">Is</span></span>|<span data-ttu-id="5ae45-140">Confronta due riferimenti a oggetti.</span><span class="sxs-lookup"><span data-stu-id="5ae45-140">Compares two object references.</span></span>|  
  
### <a name="string-concatenation"></a><span data-ttu-id="5ae45-141">Concatenazione di stringhe</span><span class="sxs-lookup"><span data-stu-id="5ae45-141">String Concatenation</span></span>  
 <span data-ttu-id="5ae45-142">La concatenazione di stringhe aggiunge la seconda stringa alla prima in un'espressione.</span><span class="sxs-lookup"><span data-stu-id="5ae45-142">String concatenation appends the second string to the first string in an expression.</span></span> <span data-ttu-id="5ae45-143">Per le altre operazioni con stringhe, utilizzare le funzioni predefinite.</span><span class="sxs-lookup"><span data-stu-id="5ae45-143">For other string operations, use built-in functions.</span></span>  
  
|<span data-ttu-id="5ae45-144">Operatore</span><span class="sxs-lookup"><span data-stu-id="5ae45-144">Operator</span></span>|<span data-ttu-id="5ae45-145">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5ae45-145">Description</span></span>|  
|--------------|-----------------|  
|&|<span data-ttu-id="5ae45-146">Concatena due stringhe</span><span class="sxs-lookup"><span data-stu-id="5ae45-146">Concatenates two strings</span></span>|  
|+|<span data-ttu-id="5ae45-147">Concatena due stringhe</span><span class="sxs-lookup"><span data-stu-id="5ae45-147">Concatenates two strings</span></span>|  
  
### <a name="logical-and-bitwise"></a><span data-ttu-id="5ae45-148">Logico e bit per bit</span><span class="sxs-lookup"><span data-stu-id="5ae45-148">Logical and Bitwise</span></span>  
 <span data-ttu-id="5ae45-149">Gli operatori logici e bit per bit eseguono modifiche logiche tra due termini interi in un'espressione.</span><span class="sxs-lookup"><span data-stu-id="5ae45-149">Logical and bitwise operators perform logical manipulations between two integer terms in an expression.</span></span>  
  
|<span data-ttu-id="5ae45-150">Operatore</span><span class="sxs-lookup"><span data-stu-id="5ae45-150">Operator</span></span>|<span data-ttu-id="5ae45-151">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5ae45-151">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="5ae45-152">e</span><span class="sxs-lookup"><span data-stu-id="5ae45-152">And</span></span>|<span data-ttu-id="5ae45-153">Esegue una congiunzione logica di due espressioni booleane oppure una congiunzione bit per bit di due espressioni numeriche.</span><span class="sxs-lookup"><span data-stu-id="5ae45-153">Performs a logical conjunction on two Boolean expressions, or bitwise conjunction on two numeric expressions.</span></span>|  
|<span data-ttu-id="5ae45-154">Not</span><span class="sxs-lookup"><span data-stu-id="5ae45-154">Not</span></span>|<span data-ttu-id="5ae45-155">Esegue una negazione logica di un'espressione booleana oppure una negazione bit per bit di un'espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="5ae45-155">Performs logical negation on a Boolean expression, or bitwise negation on a numeric expression.</span></span>|  
|<span data-ttu-id="5ae45-156">Oppure</span><span class="sxs-lookup"><span data-stu-id="5ae45-156">Or</span></span>|<span data-ttu-id="5ae45-157">Esegue una disgiunzione logica di due espressioni booleane oppure una disgiunzione bit per bit di due valori numerici.</span><span class="sxs-lookup"><span data-stu-id="5ae45-157">Performs a logical disjunction on two Boolean expressions, or bitwise disjunction on two numeric values.</span></span>|  
|<span data-ttu-id="5ae45-158">Xor</span><span class="sxs-lookup"><span data-stu-id="5ae45-158">Xor</span></span>|<span data-ttu-id="5ae45-159">Esegue un'operazione di esclusione logica di due espressioni booleane oppure un'esclusione bit per bit di due espressioni numeriche.</span><span class="sxs-lookup"><span data-stu-id="5ae45-159">Performs a logical exclusion operation on two Boolean expressions, or a bitwise exclusion on two numeric expressions.</span></span>|  
|<span data-ttu-id="5ae45-160">AndAlso</span><span class="sxs-lookup"><span data-stu-id="5ae45-160">AndAlso</span></span>|<span data-ttu-id="5ae45-161">Esegue una congiunzione logica di due espressioni.</span><span class="sxs-lookup"><span data-stu-id="5ae45-161">Performs logical conjunction on two expressions.</span></span>|  
|<span data-ttu-id="5ae45-162">OrElse</span><span class="sxs-lookup"><span data-stu-id="5ae45-162">OrElse</span></span>|<span data-ttu-id="5ae45-163">Esegue una disgiunzione logica di due espressioni.</span><span class="sxs-lookup"><span data-stu-id="5ae45-163">Performs logical disjunction on two expressions.</span></span>|  
  
### <a name="bit-shift"></a><span data-ttu-id="5ae45-164">Scorrimento di bit</span><span class="sxs-lookup"><span data-stu-id="5ae45-164">Bit Shift</span></span>  
 <span data-ttu-id="5ae45-165">Gli operatori bit per bit eseguono modifiche di bit tra due termini interi in un'espressione.</span><span class="sxs-lookup"><span data-stu-id="5ae45-165">Bitwise operators perform bit manipulations between two integer terms in an expression.</span></span>  
  
|<span data-ttu-id="5ae45-166">Operatore</span><span class="sxs-lookup"><span data-stu-id="5ae45-166">Operator</span></span>|<span data-ttu-id="5ae45-167">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5ae45-167">Description</span></span>|  
|--------------|-----------------|  
|<\<|<span data-ttu-id="5ae45-168">Esegue uno scorrimento a sinistra aritmetico a sinistra in un modello di bit.</span><span class="sxs-lookup"><span data-stu-id="5ae45-168">Performs an arithmetic left-shift on a bit pattern.</span></span>|  
|>>|<span data-ttu-id="5ae45-169">Esegue uno scorrimento a destra aritmetico in un modello di bit.</span><span class="sxs-lookup"><span data-stu-id="5ae45-169">Performs an arithmetic right-shift on a bit pattern.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5ae45-170">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5ae45-170">See Also</span></span>  
 <span data-ttu-id="5ae45-171">[Finestra di dialogo Espressione](../expression-dialog-box.md) </span><span class="sxs-lookup"><span data-stu-id="5ae45-171">[Expression Dialog Box](../expression-dialog-box.md) </span></span>  
 <span data-ttu-id="5ae45-172">[Espressioni &#40;Generatore report e SSRS&#41;](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="5ae45-172">[Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="5ae45-173">[Esempi di espressioni &#40;Generatore report e SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="5ae45-173">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="5ae45-174">[Tipi di dati nelle espressioni &#40;Generatore report e SSRS&#41;](data-types-in-expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="5ae45-174">[Data Types in Expressions &#40;Report Builder and SSRS&#41;](data-types-in-expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="5ae45-175">Finestra di dialogo dell'espressione &#40;Generatore report&#41;</span><span class="sxs-lookup"><span data-stu-id="5ae45-175">Expression Dialog Box &#40;Report Builder&#41;</span></span>](../expression-dialog-box-report-builder.md)  
  
  
