---
title: Finestra di dialogo Espressione vincolo CHECK (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdt.dlgbox.checkconstraintexpression
ms.assetid: beb6ce43-3913-4d66-8826-8e885335b790
author: stevestein
ms.author: sstein
ms.openlocfilehash: 38268d4e49a9c674c100bc22c0782e3e61477967
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622999"
---
# <a name="check-constraint-expression-dialog-box-visual-database-tools"></a><span data-ttu-id="c4821-102">Finestra di dialogo Espressione vincolo CHECK (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="c4821-102">Check Constraint Expression Dialog Box (Visual Database Tools)</span></span>
  <span data-ttu-id="c4821-103">Quando si associa un vincolo CHECK a una tabella o colonna, è necessario includere un'espressione SQL.</span><span class="sxs-lookup"><span data-stu-id="c4821-103">When you attach a check constraint to a table or column, you must include an SQL expression.</span></span> <span data-ttu-id="c4821-104">Digitare l'espressione di vincolo CHECK nella casella specifica.</span><span class="sxs-lookup"><span data-stu-id="c4821-104">Type the check constraint expression in the box provided.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="c4821-105">Elenco di elementi dell'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="c4821-105">UI element list</span></span>  
 <span data-ttu-id="c4821-106">Expression</span><span class="sxs-lookup"><span data-stu-id="c4821-106">Expression</span></span>  
 <span data-ttu-id="c4821-107">Immettere l'espressione.</span><span class="sxs-lookup"><span data-stu-id="c4821-107">Enter the expression</span></span>  
  
 <span data-ttu-id="c4821-108">È possibile creare un'espressione di vincolo semplice per verificare i dati in base a una condizione semplice oppure creare un'espressione complessa, con operatori booleani, per verificare i dati in base a diverse condizioni.</span><span class="sxs-lookup"><span data-stu-id="c4821-108">You can create a simple constraint expression to check data for a simple condition; or you can create a complex expression, using Boolean operators, to check data for several conditions.</span></span> <span data-ttu-id="c4821-109">Si supponga ad esempio che nella tabella degli autori sia presente una colonna del codice postale in cui è richiesta una stringa di 5 caratteri.</span><span class="sxs-lookup"><span data-stu-id="c4821-109">For example, suppose the authors table has a zip column where a 5-digit character string is required.</span></span> <span data-ttu-id="c4821-110">L'espressione di vincolo dell'esempio seguente garantisce che venga accettata solo l'immissione di numeri a 5 cifre:</span><span class="sxs-lookup"><span data-stu-id="c4821-110">This sample constraint expression guarantees that only 5-digit numbers are allowed:</span></span>  
  
```  
zip LIKE '[0-9][0-9][0-9][0-9][0-9]'  
```  
  
 <span data-ttu-id="c4821-111">Oppure si supponga che nella tabella delle vendite sia presente una colonna delle quantità in cui è richiesto un valore maggiore di 0.</span><span class="sxs-lookup"><span data-stu-id="c4821-111">Or suppose the sales table has a column called qty which requires a value greater than 0.</span></span> <span data-ttu-id="c4821-112">Questo vincolo di esempio garantisce che vengano accettati solo valori positivi:</span><span class="sxs-lookup"><span data-stu-id="c4821-112">This sample constraint guarantees that only positive values are allowed:</span></span>  
  
```  
qty > 0  
```  
  
 <span data-ttu-id="c4821-113">Oppure si supponga che la tabella degli ordini preveda un limite relativamente al tipo di carte di credito accettate per tutti gli ordini con carte di credito.</span><span class="sxs-lookup"><span data-stu-id="c4821-113">Or suppose the orders table limits the type of credit cards accepted for all credit card orders.</span></span> <span data-ttu-id="c4821-114">Il vincolo dell'esempio seguente garantisce che vengano accettate solo carte Visa, MasterCard o American Express se l'ordine viene effettuato con carta di credito:</span><span class="sxs-lookup"><span data-stu-id="c4821-114">This sample constraint guarantees that if the order is placed on a credit card, then only Visa, MasterCard, or American Express is accepted:</span></span>  
  
```  
NOT (payment_method = 'credit card') OR  
   (card_type IN ('VISA', 'MASTERCARD', 'AMERICAN EXPRESS'))  
```  
  
## <a name="to-define-a-constraint-expression"></a><span data-ttu-id="c4821-115">Per definire un'espressione di vincolo</span><span class="sxs-lookup"><span data-stu-id="c4821-115">To define a constraint expression</span></span>  
 <span data-ttu-id="c4821-116">Nella scheda Vincoli CHECK delle pagine delle proprietà, digitare un'espressione nella casella Espressione di vincolo utilizzando la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="c4821-116">In the Check Constraints tab of the property pages, type an expression in the Constraint expression box using the following syntax:</span></span>  
  
 `{constant | column_name | function | (subquery)}`  
  
 `[{operator | AND | OR | NOT}`  
  
 `{constant | column_name | function | (subquery)}...]`  
  
 <span data-ttu-id="c4821-117">La sintassi SQL è costituita dai parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="c4821-117">The SQL syntax is made up of the following parameters:</span></span>  
  
|<span data-ttu-id="c4821-118">Parametro</span><span class="sxs-lookup"><span data-stu-id="c4821-118">Parameter</span></span>|<span data-ttu-id="c4821-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c4821-119">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c4821-120">constant</span><span class="sxs-lookup"><span data-stu-id="c4821-120">constant</span></span>|<span data-ttu-id="c4821-121">Valore letterale, ad esempio dati numerici o caratteri.</span><span class="sxs-lookup"><span data-stu-id="c4821-121">A literal value, such as numeric or character data.</span></span> <span data-ttu-id="c4821-122">I caratteri devono essere racchiusi tra virgolette semplici (')</span><span class="sxs-lookup"><span data-stu-id="c4821-122">Character data must be enclosed within single quotation marks (').</span></span>|  
|<span data-ttu-id="c4821-123">column_name</span><span class="sxs-lookup"><span data-stu-id="c4821-123">column_name</span></span>|<span data-ttu-id="c4821-124">Specifica una colonna.</span><span class="sxs-lookup"><span data-stu-id="c4821-124">Specifies a column.</span></span>|  
|<span data-ttu-id="c4821-125">function</span><span class="sxs-lookup"><span data-stu-id="c4821-125">function</span></span>|<span data-ttu-id="c4821-126">Funzione predefinita.</span><span class="sxs-lookup"><span data-stu-id="c4821-126">A built-in function.</span></span>|  
|<span data-ttu-id="c4821-127">operator</span><span class="sxs-lookup"><span data-stu-id="c4821-127">operator</span></span>|<span data-ttu-id="c4821-128">Operatore aritmetico, bit per bit, di confronto o operatore di stringa.</span><span class="sxs-lookup"><span data-stu-id="c4821-128">Arithmetic, bitwise, comparison, or string operators.</span></span>|  
|<span data-ttu-id="c4821-129">AND</span><span class="sxs-lookup"><span data-stu-id="c4821-129">AND</span></span>|<span data-ttu-id="c4821-130">Si utilizza nelle espressioni booleane per collegare due espressioni.</span><span class="sxs-lookup"><span data-stu-id="c4821-130">Use in Boolean expressions to connect two expressions.</span></span> <span data-ttu-id="c4821-131">Viene restituito un risultato quando entrambe le espressioni sono true.</span><span class="sxs-lookup"><span data-stu-id="c4821-131">Results are returned when both expressions are true.</span></span><br /><br /> <span data-ttu-id="c4821-132">Quando un'istruzione contiene sia AND che OR, il parametro AND viene elaborato per primo.</span><span class="sxs-lookup"><span data-stu-id="c4821-132">When AND and OR are both used in a statement, AND is processed first.</span></span> <span data-ttu-id="c4821-133">È tuttavia possibile modificare l'ordine di esecuzione tramite l'utilizzo delle parentesi.</span><span class="sxs-lookup"><span data-stu-id="c4821-133">You can change the order of execution by using parentheses.</span></span>|  
|<span data-ttu-id="c4821-134">o</span><span class="sxs-lookup"><span data-stu-id="c4821-134">OR</span></span>|<span data-ttu-id="c4821-135">Si utilizza nelle espressioni booleane per collegare due o più condizioni.</span><span class="sxs-lookup"><span data-stu-id="c4821-135">Use in Boolean expressions to connect two or more conditions.</span></span> <span data-ttu-id="c4821-136">Viene restituito un risultato quando una delle due condizioni è true.</span><span class="sxs-lookup"><span data-stu-id="c4821-136">Results are returned when either condition is true.</span></span><br /><br /> <span data-ttu-id="c4821-137">Quando un'istruzione contiene sia AND che OR, OR viene elaborato dopo AND.</span><span class="sxs-lookup"><span data-stu-id="c4821-137">When AND and OR are both used in a statement, OR is evaluated after AND.</span></span> <span data-ttu-id="c4821-138">È tuttavia possibile modificare l'ordine di esecuzione tramite l'utilizzo delle parentesi.</span><span class="sxs-lookup"><span data-stu-id="c4821-138">You can change the order of execution by using parentheses.</span></span>|  
|<span data-ttu-id="c4821-139">NOT</span><span class="sxs-lookup"><span data-stu-id="c4821-139">NOT</span></span>|<span data-ttu-id="c4821-140">Nega qualsiasi espressione booleana (che può includere parole chiave come LIKE, NULL, BETWEEN, IN ed EXISTS).</span><span class="sxs-lookup"><span data-stu-id="c4821-140">Negates any Boolean expression (which can include keywords, such as LIKE, NULL, BETWEEN, IN, and EXISTS).</span></span><br /><br /> <span data-ttu-id="c4821-141">Quando in un'istruzione sono utilizzati più operatori logici, NOT viene elaborato per primo.</span><span class="sxs-lookup"><span data-stu-id="c4821-141">When more than one logical operator is used in a statement, NOT is processed first.</span></span> <span data-ttu-id="c4821-142">È tuttavia possibile modificare l'ordine di esecuzione tramite l'utilizzo delle parentesi.</span><span class="sxs-lookup"><span data-stu-id="c4821-142">You can change the order of execution by using parentheses.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c4821-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c4821-143">See Also</span></span>  
 <span data-ttu-id="c4821-144">[Vincoli UNIQUE e check](../../relational-databases/tables/unique-constraints-and-check-constraints.md) </span><span class="sxs-lookup"><span data-stu-id="c4821-144">[Unique Constraints and Check Constraints](../../relational-databases/tables/unique-constraints-and-check-constraints.md) </span></span>  
 [<span data-ttu-id="c4821-145">Creare vincoli UNIQUE</span><span class="sxs-lookup"><span data-stu-id="c4821-145">Create Unique Constraints</span></span>](../../relational-databases/tables/create-unique-constraints.md)  
  
  
