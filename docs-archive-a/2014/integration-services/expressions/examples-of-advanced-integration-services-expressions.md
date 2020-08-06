---
title: Esempi di espressioni avanzate di Integration Services | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- functions [Integration Services]
- operators [Integration Services]
- expressions [Integration Services], examples
- examples [Integration Services]
ms.assetid: c7794ba3-0de5-466b-ae8a-9ddd27360049
author: chugugrace
ms.author: chugu
ms.openlocfilehash: fb1e8dc6f9bffd22c917414f80f6ba9f257b25b8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627922"
---
# <a name="examples-of-advanced-integration-services-expressions"></a><span data-ttu-id="492e9-102">Esempi di espressioni avanzate di Integration Services</span><span class="sxs-lookup"><span data-stu-id="492e9-102">Examples of Advanced Integration Services Expressions</span></span>
  <span data-ttu-id="492e9-103">In questa sezione vengono forniti esempi di alcune funzioni avanzate, in cui sono combinati più operatori e funzioni.</span><span class="sxs-lookup"><span data-stu-id="492e9-103">This section provides examples of advanced expressions that combine multiple operators and functions.</span></span> <span data-ttu-id="492e9-104">Le espressioni utilizzate nei vincoli di precedenza o nella trasformazione Suddivisione condizionale devono restituire un valore booleano.</span><span class="sxs-lookup"><span data-stu-id="492e9-104">If an expression is used in a precedence constraint or the Conditional Split transformation, it must evaluate to a Boolean.</span></span> <span data-ttu-id="492e9-105">Tale restrizione non si applica tuttavia alle espressioni utilizzate in espressioni di proprietà e variabili, nella trasformazione Colonna derivata o nel contenitore Ciclo For.</span><span class="sxs-lookup"><span data-stu-id="492e9-105">That restriction, however, does not apply to expressions used in property expressions, variables, the Derived Column transformation, or the For Loop container.</span></span>  
  
 <span data-ttu-id="492e9-106">Gli esempi seguenti usano i database **AdventureWorks** e [!INCLUDE[ssSampleDBDWobject](../../includes/sssampledbdwobject-md.md)][!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="492e9-106">The following examples use the **AdventureWorks** and the [!INCLUDE[ssSampleDBDWobject](../../includes/sssampledbdwobject-md.md)][!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases.</span></span> <span data-ttu-id="492e9-107">Per ogni esempio viene indicata la tabella utilizzata.</span><span class="sxs-lookup"><span data-stu-id="492e9-107">Each example identifies the tables it uses.</span></span>  
  
## <a name="boolean-expressions"></a><span data-ttu-id="492e9-108">Espressioni booleane</span><span class="sxs-lookup"><span data-stu-id="492e9-108">Boolean Expressions</span></span>  
  
-   <span data-ttu-id="492e9-109">Questo esempio usa la tabella **Product** .</span><span class="sxs-lookup"><span data-stu-id="492e9-109">This example uses the **Product** table.</span></span> <span data-ttu-id="492e9-110">L'espressione valuta la voce del mese nella colonna **SellStartDate** e restituisce TRUE se il mese è giugno o uno successivo.</span><span class="sxs-lookup"><span data-stu-id="492e9-110">The expression evaluates the month entry in the **SellStartDate** column and returns TRUE if the month is June or later.</span></span>  
  
    ```  
    DATEPART("mm",SellStartDate) > 6  
    ```  
  
-   <span data-ttu-id="492e9-111">Questo esempio usa la tabella **Product** .</span><span class="sxs-lookup"><span data-stu-id="492e9-111">This example uses the **Product** table.</span></span> <span data-ttu-id="492e9-112">L'espressione valuta il risultato arrotondato della divisione della colonna **ListPrice** per la colonna **StandardCost** e restituisce TRUE se questo risultato è maggiore di 1,5.</span><span class="sxs-lookup"><span data-stu-id="492e9-112">The expression evaluates the rounded result of dividing the **ListPrice** column by the **StandardCost** column, and returns TRUE if the result is greater than 1.5.</span></span>  
  
    ```  
    ROUND(ListPrice / StandardCost,2) > 1.50  
    ```  
  
-   <span data-ttu-id="492e9-113">Questo esempio usa la tabella **Product** .</span><span class="sxs-lookup"><span data-stu-id="492e9-113">This example uses the **Product** table.</span></span> <span data-ttu-id="492e9-114">L'espressione restituisce TRUE se tutte e tre le operazioni restituiscono TRUE.</span><span class="sxs-lookup"><span data-stu-id="492e9-114">The expression returns TRUE if all three operations evaluate to TRUE.</span></span> <span data-ttu-id="492e9-115">Se la colonna **Size** e la variabile **BikeSize** hanno tipi di dati incompatibili, l'espressione richiederà un cast esplicito, come mostrato nel secondo esempio.</span><span class="sxs-lookup"><span data-stu-id="492e9-115">If the **Size** column and the **BikeSize** variable have incompatible data types, the expression requires an explicit cast as shown the second example.</span></span> <span data-ttu-id="492e9-116">Il cast a DT_WSTR include la lunghezza della stringa.</span><span class="sxs-lookup"><span data-stu-id="492e9-116">The cast to DT_WSTR includes the length of the string.</span></span>  
  
    ```  
    MakeFlag ==  TRUE && FinishedGoodsFlag == TRUE && Size != @BikeSize  
    MakeFlag ==  TRUE && FinishedGoodsFlag == TRUE  && Size != (DT_WSTR,10)@BikeSize  
    ```  
  
-   <span data-ttu-id="492e9-117">Questo esempio usa la tabella **CurrencyRate** .</span><span class="sxs-lookup"><span data-stu-id="492e9-117">This example uses the **CurrencyRate** table.</span></span> <span data-ttu-id="492e9-118">L'espressione confronta valori in tabelle e variabili.</span><span class="sxs-lookup"><span data-stu-id="492e9-118">The expression compares values in tables and variables.</span></span> <span data-ttu-id="492e9-119">Restituisce TRUE se la voce nella colonna **FromCurrencyCode** o **ToCurrencyCode** è uguale al valore della variabile e se il valore in **AverageRate** è maggiore del valore in **EndOfDayRate**.</span><span class="sxs-lookup"><span data-stu-id="492e9-119">It returns TRUE if entries in the **FromCurrencyCode** or **ToCurrencyCode** columns are equal to variable values and if the value in **AverageRate** is greater that the value in **EndOfDayRate**.</span></span>  
  
    ```  
    (FromCurrencyCode == @FromCur || ToCurrencyCode == @ToCur) && AverageRate > EndOfDayRate  
    ```  
  
-   <span data-ttu-id="492e9-120">Questo esempio usa la tabella **Currency** .</span><span class="sxs-lookup"><span data-stu-id="492e9-120">This example uses the **Currency** table.</span></span> <span data-ttu-id="492e9-121">L'espressione restituisce TRUE se il primo carattere nella colonna **Name** non è a o A.</span><span class="sxs-lookup"><span data-stu-id="492e9-121">The expression returns TRUE if the first character in the **Name** column is not a or A.</span></span>  
  
    ```  
    SUBSTRING(UPPER(Name),1,1) != "A"  
    ```  
  
     <span data-ttu-id="492e9-122">L'espressione seguente restituisce gli stessi risultati ma è più efficiente, perché viene convertito in maiuscolo un solo carattere.</span><span class="sxs-lookup"><span data-stu-id="492e9-122">The following expression provides the same results, but it is more efficient because only one character is converted to uppercase.</span></span>  
  
    ```  
    UPPER(SUBSTRING(Name,1,1)) != "A"  
    ```  
  
## <a name="non-boolean-expressions"></a><span data-ttu-id="492e9-123">Espressioni non booleane</span><span class="sxs-lookup"><span data-stu-id="492e9-123">Non-Boolean Expressions</span></span>  
 <span data-ttu-id="492e9-124">Le espressioni non booleane vengono utilizzate nella trasformazione Colonna derivata, nelle espressioni di proprietà e nel contenitore Ciclo For.</span><span class="sxs-lookup"><span data-stu-id="492e9-124">Non-Boolean expressions are used in the Derived Column transformation, property expressions, and the For Loop container.</span></span>  
  
-   <span data-ttu-id="492e9-125">Questo esempio usa la tabella **Contact** .</span><span class="sxs-lookup"><span data-stu-id="492e9-125">This example uses the **Contact** table.</span></span> <span data-ttu-id="492e9-126">L'espressione rimuove gli spazi iniziali e finali dalle colonne **FirstName**, **MiddleName**e **LastName** .</span><span class="sxs-lookup"><span data-stu-id="492e9-126">The expression removes leading and trailing spaces from the **FirstName**, **MiddleName**, and **LastName** columns.</span></span> <span data-ttu-id="492e9-127">Estrae la prima lettera della colonna **MiddleName** se non è Null, concatena l'iniziale del secondo nome e i valori in **FirstName** e **LastName**e inserisce gli spazi appropriati tra i valori.</span><span class="sxs-lookup"><span data-stu-id="492e9-127">It extracts the first letter of the **MiddleName** column if it is not null, concatenates the middle initial and the values in **FirstName** and **LastName**, and inserts appropriate spaces between values.</span></span>  
  
    ```  
    TRIM(FirstName) + " " + (!ISNULL(MiddleName) ? SUBSTRING(MiddleName,1,1) + " " : "") + TRIM(LastName)  
    ```  
  
-   <span data-ttu-id="492e9-128">Questo esempio usa la tabella **Contact** .</span><span class="sxs-lookup"><span data-stu-id="492e9-128">This example uses the **Contact** table.</span></span> <span data-ttu-id="492e9-129">L'espressione convalida le voci nella colonna **Salutation** .</span><span class="sxs-lookup"><span data-stu-id="492e9-129">The expression validates entries in the **Salutation** column.</span></span> <span data-ttu-id="492e9-130">Restituisce una voce di **Salutation** o una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="492e9-130">It returns a **Salutation** entry or an empty string.</span></span>  
  
    ```  
    (Salutation == "Sr." || Salutation == "Ms." || Salutation == "Sra." || Salutation == "Mr.") ? Salutation : ""  
    ```  
  
-   <span data-ttu-id="492e9-131">Questo esempio usa la tabella **Product** .</span><span class="sxs-lookup"><span data-stu-id="492e9-131">This example uses the **Product** table.</span></span> <span data-ttu-id="492e9-132">L'espressione converte in maiuscolo il primo carattere nella colonna **Color** e in minuscolo i caratteri rimanenti.</span><span class="sxs-lookup"><span data-stu-id="492e9-132">The expression converts the first character in the **Color** column to uppercase and converts remaining characters to lowercase.</span></span>  
  
    ```  
    UPPER(SUBSTRING(Color,1,1)) + LOWER(SUBSTRING(Color,2,15))  
    ```  
  
-   <span data-ttu-id="492e9-133">Questo esempio usa la tabella **Product** .</span><span class="sxs-lookup"><span data-stu-id="492e9-133">This example uses the **Product** table.</span></span> <span data-ttu-id="492e9-134">L'espressione calcola il numero dei mesi per cui un determinato prodotto è stato venduto e restituisce la stringa "Unknown" se la colonna **SellStartDate** o **SellEndDate** contiene NULL.</span><span class="sxs-lookup"><span data-stu-id="492e9-134">The expression calculates the number of months a product has been sold and returns the string "Unknown" if either the **SellStartDate** or the **SellEndDate** column contains NULL.</span></span>  
  
    ```  
    !(ISNULL(SellStartDate)) && !(ISNULL(SellEndDate)) ? (DT_WSTR,2)DATEDIFF("mm",SellStartDate,SellEndDate) : "Unknown"  
    ```  
  
-   <span data-ttu-id="492e9-135">Questo esempio usa la tabella **Product** .</span><span class="sxs-lookup"><span data-stu-id="492e9-135">This example uses the **Product** table.</span></span> <span data-ttu-id="492e9-136">L'espressione calcola il margine di profitto sulla colonna **StandardCost** e arrotonda il risultato alla precisione 2.</span><span class="sxs-lookup"><span data-stu-id="492e9-136">The expression calculates the markup on the **StandardCost** column and rounds the result to a precision of two.</span></span> <span data-ttu-id="492e9-137">Il risultato viene presentato come percentuale.</span><span class="sxs-lookup"><span data-stu-id="492e9-137">The result is presented as a percentage.</span></span>  
  
    ```  
    ROUND(ListPrice / StandardCost,2) * 100  
    ```  
  
## <a name="related-tasks"></a><span data-ttu-id="492e9-138">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="492e9-138">Related Tasks</span></span>  
 [<span data-ttu-id="492e9-139">Usare un'espressione in un componente flusso di dati</span><span class="sxs-lookup"><span data-stu-id="492e9-139">Use an Expression in a Data Flow Component</span></span>](../use-an-expression-in-a-data-flow-component.md)  
  
## <a name="related-content"></a><span data-ttu-id="492e9-140">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="492e9-140">Related Content</span></span>  
 <span data-ttu-id="492e9-141">Articolo tecnico relativo al [foglio d'aiuto per le espressioni SSIS](https://pragmaticworks.com/Resources/Cheat-Sheets/SSIS-Expression-Cheat-Sheet)sul sito Web pragmaticworks.com</span><span class="sxs-lookup"><span data-stu-id="492e9-141">Technical article, [SSIS Expression Cheat Sheet](https://pragmaticworks.com/Resources/Cheat-Sheets/SSIS-Expression-Cheat-Sheet), on pragmaticworks.com</span></span>  
  
  
