---
title: Esempi di espressioni (Generatore report e SSRS) | Microsoft Docs
ms.prod: sql-server-2014
ms.technology: reporting-services
ms.topic: conceptual
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.reviewer: ''
ms.custom: ''
ms.date: 03/08/2017
ms.openlocfilehash: c7ef06143dafdb5034d0f6202fdc16bc51f74ca8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627113"
---
# <a name="expression-examples-report-builder-and-ssrs"></a><span data-ttu-id="5e830-102">Esempi di espressioni (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="5e830-102">Expression Examples (Report Builder and SSRS)</span></span>

<span data-ttu-id="5e830-103">Le espressioni vengono utilizzate di frequente nei report per controllare il contenuto e l'aspetto del report.</span><span class="sxs-lookup"><span data-stu-id="5e830-103">Expressions are used frequently in reports to control content and report appearance.</span></span> <span data-ttu-id="5e830-104">Le espressioni sono scritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] e possono usare funzioni predefinite di codice personalizzato, variabili di report e di gruppo e variabili definite dall'utente.</span><span class="sxs-lookup"><span data-stu-id="5e830-104">Expressions are written in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)], and can use built-in functions custom code, report and group variables, and user-defined variables.</span></span> <span data-ttu-id="5e830-105">Le espressioni iniziano con un segno di uguale (=).</span><span class="sxs-lookup"><span data-stu-id="5e830-105">Expressions begin with an equal sign (=).</span></span> <span data-ttu-id="5e830-106">Per altre informazioni sull'editor espressioni e sui tipi di riferimenti che è possibile includere, vedere [Uso delle espressioni nei report &#40;Generatore report e SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) e [Aggiungere un'espressione &#40;Generatore report e SSRS&#41;](add-an-expression-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="5e830-106">For more information about the expression editor and the types of references that you can include, see [Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md), and [Add an Expression &#40;Report Builder and SSRS&#41;](add-an-expression-report-builder-and-ssrs.md).</span></span>  

> [!IMPORTANT]  
>  <span data-ttu-id="5e830-107">Quando RDL Sandboxing è abilitato, al momento della pubblicazione del report nel testo dell'espressione è possibile utilizzare solo determinati tipi e membri.</span><span class="sxs-lookup"><span data-stu-id="5e830-107">When RDL Sandboxing is enabled, only certain types and members can be used in expression text at report publish time.</span></span> <span data-ttu-id="5e830-108">Per altre informazioni, vedere [Enable and Disable RDL Sandboxing](../enable-and-disable-rdl-sandboxing.md).</span><span class="sxs-lookup"><span data-stu-id="5e830-108">For more information, see [Enable and Disable RDL Sandboxing](../enable-and-disable-rdl-sandboxing.md).</span></span>  

<span data-ttu-id="5e830-109">In questo argomento vengono forniti alcuni esempi di espressioni che è possibile utilizzare per attività comuni in un report.</span><span class="sxs-lookup"><span data-stu-id="5e830-109">This topic provides examples of expressions that can be used for common tasks in a report.</span></span>  

-   <span data-ttu-id="5e830-110">[Funzioni di Visual Basic](#VisualBasicFunctions) Esempi di funzioni di [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] di tipo data, stringa, conversione e condizionale.</span><span class="sxs-lookup"><span data-stu-id="5e830-110">[Visual Basic Functions](#VisualBasicFunctions) Examples for date, string, conversion and conditional [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] functions.</span></span>  

-   <span data-ttu-id="5e830-111">[Funzioni di report](#ReportFunctions) Esempi relativi a funzioni di aggregazione e altre funzioni di report predefinite.</span><span class="sxs-lookup"><span data-stu-id="5e830-111">[Report Functions](#ReportFunctions) Examples for aggregates and other built-in report functions.</span></span>  

-   <span data-ttu-id="5e830-112">[Aspetto dei dati del report](#AppearanceofReportData) Esempi relativi alla modifica dell'aspetto di un report.</span><span class="sxs-lookup"><span data-stu-id="5e830-112">[Appearance of Report Data](#AppearanceofReportData) Examples for changing the appearance of a report.</span></span>  

-   <span data-ttu-id="5e830-113">[Proprietà](#Properties) Esempi relativi all'impostazione delle proprietà degli elementi del report per il controllo del formato o della visibilità.</span><span class="sxs-lookup"><span data-stu-id="5e830-113">[Properties](#Properties) Examples for setting report item properties to control format or visibility.</span></span>  

-   <span data-ttu-id="5e830-114">[Parametri](#Parameters) Esempi relativi all'utilizzo di parametri in un'espressione.</span><span class="sxs-lookup"><span data-stu-id="5e830-114">[Parameters](#Parameters) Examples for using parameters in an expression.</span></span>  

-   <span data-ttu-id="5e830-115">[Codice personalizzato](#CustomCode) Esempi di codice personalizzato incorporato.</span><span class="sxs-lookup"><span data-stu-id="5e830-115">[Custom Code](#CustomCode) Examples of embedded custom code.</span></span>  

<span data-ttu-id="5e830-116">Per esempi di espressioni per utilizzi specifici, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="5e830-116">For expression examples for specific uses, see the following topics:</span></span>  

-   [<span data-ttu-id="5e830-117">Esempi di espressioni di raggruppamento &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="5e830-117">Group Expression Examples &#40;Report Builder and SSRS&#41;</span></span>](expression-examples-report-builder-and-ssrs.md)  

-   [<span data-ttu-id="5e830-118">Esempi di equazioni di filtro &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="5e830-118">Filter Equation Examples &#40;Report Builder and SSRS&#41;</span></span>](filter-equation-examples-report-builder-and-ssrs.md)  

-   [<span data-ttu-id="5e830-119">Filtri di uso comune &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="5e830-119">Commonly Used Filters &#40;Report Builder and SSRS&#41;</span></span>](commonly-used-filters-report-builder-and-ssrs.md)  

-   [<span data-ttu-id="5e830-120">Riferimenti a raccolte di variabili di report e di gruppo &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="5e830-120">Report and Group Variables Collections References &#40;Report Builder and SSRS&#41;</span></span>](built-in-collections-report-and-group-variables-references-report-builder.md)  

<span data-ttu-id="5e830-121">Per altre informazioni sulle espressioni semplici e complesse, per sapere dove è possibile usare le espressioni e quali tipi di riferimenti è possibile includere in un'espressione, vedere gli argomenti contenuti in [Espressioni &#40;Generatore report e SSRS&#41;](expressions-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="5e830-121">For more information about simple and complex expressions, where you can use expressions, and the types of references that you can include in an expression, see topics under [Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md).</span></span> <span data-ttu-id="5e830-122">Per altre informazioni sul contesto in cui le espressioni vengono valutate per calcolare le aggregazioni, vedere [Ambito di espressioni per totali, aggregazioni e raccolte predefinite &#40;Generatore report e SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span><span class="sxs-lookup"><span data-stu-id="5e830-122">For more information about the context in which expressions are evaluated for calculating aggregates, see [Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span></span>  

<span data-ttu-id="5e830-123">Per ulteriori informazioni su come scrivere espressioni in cui vengono utilizzati molti operatori e funzioni che si utilizzano anche per esempi di espressione in questo argomento, ma nel contesto di scrittura di un report, vedere [Tutorial: Introducing Expressions](../tutorial-introducing-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="5e830-123">To learn how to write expressions that use many of the functions and operators also used by expression examples in this topic, but in the context of writing a report, see [Tutorial: Introducing Expressions](../tutorial-introducing-expressions.md).</span></span>  

<span data-ttu-id="5e830-124">Nell'editor espressioni è inclusa una vista gerarchica delle funzioni predefinite.</span><span class="sxs-lookup"><span data-stu-id="5e830-124">The expression editor includes a hierarchical view of built-in functions.</span></span> <span data-ttu-id="5e830-125">Quando si seleziona la funzione, nel riquadro Valori viene visualizzato un esempio di codice.</span><span class="sxs-lookup"><span data-stu-id="5e830-125">When you select the function, a code example appears in the Values pane.</span></span> <span data-ttu-id="5e830-126">Per ulteriori informazioni, vedere la finestra di dialogo [espressione](../expression-dialog-box.md) o finestra di [dialogo espressione &#40;Generatore report&#41;](../expression-dialog-box-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="5e830-126">For more information, see the [Expression Dialog Box](../expression-dialog-box.md) or [Expression Dialog Box &#40;Report Builder&#41;](../expression-dialog-box-report-builder.md).</span></span>  

## <a name="functions"></a><span data-ttu-id="5e830-127">Funzioni</span><span class="sxs-lookup"><span data-stu-id="5e830-127">Functions</span></span>  

<span data-ttu-id="5e830-128">Molte espressioni incluse in un report contengono funzioni.</span><span class="sxs-lookup"><span data-stu-id="5e830-128">Many expressions in a report contain functions.</span></span> <span data-ttu-id="5e830-129">Con queste funzioni è possibile formattare dati, applicare logica e accedere ai metadati del report.</span><span class="sxs-lookup"><span data-stu-id="5e830-129">You can format data, apply logic, and access report metadata using these functions.</span></span> <span data-ttu-id="5e830-130">È possibile scrivere espressioni che utilizzano funzioni dalla [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] libreria di runtime e dagli <xref:System.Convert> <xref:System.Math> spazi dei nomi e.</span><span class="sxs-lookup"><span data-stu-id="5e830-130">You can write expressions that use functions from the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] run-time library, and from the <xref:System.Convert> and <xref:System.Math> namespaces.</span></span> <span data-ttu-id="5e830-131">È possibile aggiungere riferimenti a funzioni da altri assembly o da codice personalizzato.</span><span class="sxs-lookup"><span data-stu-id="5e830-131">You can add references to functions from other assemblies or custom code.</span></span> <span data-ttu-id="5e830-132">È anche possibile usare le classi di [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] , tra cui <xref:System.Text.RegularExpressions> .</span><span class="sxs-lookup"><span data-stu-id="5e830-132">You can also use classes from the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], including <xref:System.Text.RegularExpressions>.</span></span>  

###  <a name="visual-basic-functions"></a><a name="VisualBasicFunctions"></a> <span data-ttu-id="5e830-133">Funzioni di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5e830-133">Visual Basic Functions</span></span>  
<span data-ttu-id="5e830-134">È possibile utilizzare le funzioni di [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] per modificare i dati visualizzati nelle caselle di testo o utilizzati per parametri, proprietà o altre aree del report.</span><span class="sxs-lookup"><span data-stu-id="5e830-134">You can use [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] functions to manipulate the data that is displayed in text boxes or that is used for parameters, properties, or other areas of the report.</span></span> <span data-ttu-id="5e830-135">In questa sezione vengono forniti esempi che illustrano alcune di queste funzioni.</span><span class="sxs-lookup"><span data-stu-id="5e830-135">This section provides examples demonstrating some of these functions.</span></span> <span data-ttu-id="5e830-136">Per altre informazioni, vedere la pagina relativa ai [membri delle librerie di runtime di Visual Basic](https://go.microsoft.com/fwlink/?LinkId=198941) in MSDN.</span><span class="sxs-lookup"><span data-stu-id="5e830-136">For more information, see [Visual Basic Runtime Library Members](https://go.microsoft.com/fwlink/?LinkId=198941) on MSDN.</span></span>  

<span data-ttu-id="5e830-137">In [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] sono disponibili molte opzioni di formato personalizzato, ad esempio per formati di data specifici.</span><span class="sxs-lookup"><span data-stu-id="5e830-137">The [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] provides many custom format options, for example, for specific date formats.</span></span> <span data-ttu-id="5e830-138">Per ulteriori informazioni, vedere [Formattazione dei tipi di dati](https://go.microsoft.com/fwlink/?LinkId=112024) in MSDN.</span><span class="sxs-lookup"><span data-stu-id="5e830-138">For more information, see [Formatting Types](https://go.microsoft.com/fwlink/?LinkId=112024) on MSDN.</span></span>  

#### <a name="math-functions"></a><span data-ttu-id="5e830-139">Funzioni matematiche</span><span class="sxs-lookup"><span data-stu-id="5e830-139">Math Functions</span></span>  

-   <span data-ttu-id="5e830-140">La funzione `Round` risulta utile per l'arrotondamento dei numeri al numero intero più vicino.</span><span class="sxs-lookup"><span data-stu-id="5e830-140">The `Round` function is useful to round numbers to the nearest integer.</span></span> <span data-ttu-id="5e830-141">L'espressione seguente comporta un arrotondamento del valore 1.3 a 1:</span><span class="sxs-lookup"><span data-stu-id="5e830-141">The following expression rounds a 1.3 to 1:</span></span>  

```  
= Round(1.3)  
```  

<span data-ttu-id="5e830-142">È anche possibile scrivere un'espressione per arrotondare un valore a un multiplo specificato, come avviene con la funzione `MRound` di Excel.</span><span class="sxs-lookup"><span data-stu-id="5e830-142">You can also write an expression to round a value to a multiple that you specify, similar to the `MRound` function in Excel.</span></span> <span data-ttu-id="5e830-143">Moltiplicare il valore di un fattore che crea un numero intero, arrotondare il numero e dividere il risultato per lo stesso fattore.</span><span class="sxs-lookup"><span data-stu-id="5e830-143">Multiply the value by a factor that creates an integer, round the number, and then divide by the same factor.</span></span> <span data-ttu-id="5e830-144">Per arrotondare ad esempio 1.3 al multiplo più vicino di .2 (1.4), utilizzare l'espressione seguente:</span><span class="sxs-lookup"><span data-stu-id="5e830-144">For example, to round 1.3 to the nearest multiple of .2 (1.4), use the following expression:</span></span>  

```  
= Round(1.3*5)/5  
```  

####  <a name="date-functions"></a><a name="DateFunctions"></a><span data-ttu-id="5e830-145">Funzioni di data</span><span class="sxs-lookup"><span data-stu-id="5e830-145">Date Functions</span></span>  

-   <span data-ttu-id="5e830-146">La funzione `Today` fornisce la data corrente.</span><span class="sxs-lookup"><span data-stu-id="5e830-146">The `Today` function provides the current date.</span></span> <span data-ttu-id="5e830-147">Questa espressione può essere utilizzata in una casella di testo per visualizzare la data nel report oppure in un parametro per filtrare i dati in base alla data corrente.</span><span class="sxs-lookup"><span data-stu-id="5e830-147">This expression can be used in a text box to display the date on the report, or in a parameter to filter data based on the current date.</span></span>  

```  
=Today()  
```  

-   <span data-ttu-id="5e830-148">La funzione `DateAdd` è utile per fornire un intervallo di date in base a un solo parametro.</span><span class="sxs-lookup"><span data-stu-id="5e830-148">The `DateAdd` function is useful for supplying a range of dates based on a single parameter.</span></span> <span data-ttu-id="5e830-149">L'espressione seguente restituisce una data successiva di sei mesi alla data di un parametro denominato *StartDate*.</span><span class="sxs-lookup"><span data-stu-id="5e830-149">The following expression provides a date that is six months after the date from a parameter named *StartDate*.</span></span>  

```  
=DateAdd(DateInterval.Month, 6, Parameters!StartDate.Value)  
```  

-   <span data-ttu-id="5e830-150">La funzione `Year` visualizza l'anno per una determinata data.</span><span class="sxs-lookup"><span data-stu-id="5e830-150">The `Year` function displays the year for a particular date.</span></span> <span data-ttu-id="5e830-151">È possibile utilizzare questa espressione per raggruppare date oppure per visualizzare l'anno come etichetta di un set di date.</span><span class="sxs-lookup"><span data-stu-id="5e830-151">You can use this to group dates together or to display the year as a label for a set of dates.</span></span> <span data-ttu-id="5e830-152">Questa espressione restituisce l'anno per un gruppo specifico di date di ordini di vendita.</span><span class="sxs-lookup"><span data-stu-id="5e830-152">This expression provides the year for a given group of sales order dates.</span></span> <span data-ttu-id="5e830-153">Per modificare le date è possibile utilizzare anche la funzione `Month` e altre funzioni.</span><span class="sxs-lookup"><span data-stu-id="5e830-153">The `Month` function and other functions can also be used to manipulate dates.</span></span> <span data-ttu-id="5e830-154">Per altre informazioni, vedere la documentazione di [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5e830-154">For more information, see the [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] documentation.</span></span>  

```  
=Year(Fields!OrderDate.Value)  
```  

-   <span data-ttu-id="5e830-155">È possibile combinare le funzioni in un'espressione per personalizzare il formato.</span><span class="sxs-lookup"><span data-stu-id="5e830-155">You can combine functions in an expression to customize the format.</span></span> <span data-ttu-id="5e830-156">L'espressione seguente cambia il formato di una data da mese-giorno-anno in mese-settimana-numero settimana,</span><span class="sxs-lookup"><span data-stu-id="5e830-156">The following expression changes the format of a date in the form month-day-year to month-week-week number.</span></span> <span data-ttu-id="5e830-157">ad esempio 12/23/2009 in dicembre settimana 3:</span><span class="sxs-lookup"><span data-stu-id="5e830-157">For example, 12/23/2009 to December Week 3:</span></span>  

```  
=Format(Fields!MyDate.Value, "MMMM") & " Week " &   
(Int(DateDiff("d", DateSerial(Year(Fields!MyDate.Value),   
Month(Fields!MyDate.Value),1), Fields!FullDateAlternateKey.Value)/7)+1).ToString  
```  

<span data-ttu-id="5e830-158">Se utilizzata come campo calcolato in un set di dati, questa espressione consente di aggregare i valori di un grafico in base alla settimana in ogni mese.</span><span class="sxs-lookup"><span data-stu-id="5e830-158">When used as a calculated field in a dataset, you can use this expression on a chart to aggregate values by week within each month.</span></span>  

-   <span data-ttu-id="5e830-159">L'espressione seguente applica al valore SellStartDate il formato MMM-AA.</span><span class="sxs-lookup"><span data-stu-id="5e830-159">The following expression formats the SellStartDate value as MMM-YY.</span></span> <span data-ttu-id="5e830-160">Il campo SellStartDate è un tipo di dati datetime.</span><span class="sxs-lookup"><span data-stu-id="5e830-160">SellStartDate field is a datetime data type.</span></span>  

```  
=FORMAT(Fields!SellStartDate.Value, "MMM-yy")  
```  

-   <span data-ttu-id="5e830-161">L'espressione seguente applica al valore SellStartDate il formato gg/MM/aaaa.</span><span class="sxs-lookup"><span data-stu-id="5e830-161">The following expression formats the SellStartDate value as dd/MM/yyyy.</span></span> <span data-ttu-id="5e830-162">Il campo SellStartDate è un tipo di dati datetime.</span><span class="sxs-lookup"><span data-stu-id="5e830-162">The SellStartDate field is a datetime data type.</span></span>  

```  
=FORMAT(Fields!SellStartDate.Value, "dd/MM/yyyy")  
```  

-   <span data-ttu-id="5e830-163">La funzione `CDate` converte il valore in una data.</span><span class="sxs-lookup"><span data-stu-id="5e830-163">The `CDate` function converts the value to a date.</span></span> <span data-ttu-id="5e830-164">La funzione `Now` restituisce un valore di data che contiene la data e l'ora correnti in base al sistema.</span><span class="sxs-lookup"><span data-stu-id="5e830-164">The `Now` function returns a date value containing the current date and time according to your system.</span></span> <span data-ttu-id="5e830-165">`DateDiff` restituisce un valore Long che specifica il numero di intervalli di tempo tra due valori di data.</span><span class="sxs-lookup"><span data-stu-id="5e830-165">`DateDiff` returns a Long value specifying the number of time intervals between two Date values.</span></span>  

<span data-ttu-id="5e830-166">Nell'esempio seguente viene visualizzata la data di inizio dell'anno in corso</span><span class="sxs-lookup"><span data-stu-id="5e830-166">The following example displays the start date of the current year</span></span>  

```  
=DateAdd(DateInterval.Year,DateDiff(DateInterval.Year,CDate("01/01/1900"),Now()),CDate("01/01/1900"))  
```  

-   <span data-ttu-id="5e830-167">Nell'esempio seguente viene visualizzata la data di inizio del mese precedente basato sul mese corrente.</span><span class="sxs-lookup"><span data-stu-id="5e830-167">The following example displays the start date for the previous month based on the current month.</span></span>  

```  
=DateAdd(DateInterval.Month,DateDiff(DateInterval.Month,CDate("01/01/1900"),Now())-1,CDate("01/01/1900"))  
```  

-   <span data-ttu-id="5e830-168">L'espressione seguente genera gli anni di intervallo tra SellStartDate e LastReceiptDate.</span><span class="sxs-lookup"><span data-stu-id="5e830-168">The following expression generates the interval years between SellStartDate and LastReceiptDate.</span></span> <span data-ttu-id="5e830-169">Questi campi si trovano in due set di dati diversi, DataSet1 e DataSet2.</span><span class="sxs-lookup"><span data-stu-id="5e830-169">These fields are in two different datasets, DataSet1 and DataSet2.</span></span> <span data-ttu-id="5e830-170">La funzione di aggregazione [First &#40;Generatore report e SSRS&#41;](report-builder-functions-first-function.md) restituisce il primo valore di SellStartDate in DataSet1 e il primo valore di LastReceiptDate in DataSet2.</span><span class="sxs-lookup"><span data-stu-id="5e830-170">The [First Function &#40;Report Builder and SSRS&#41;](report-builder-functions-first-function.md), which is an aggregate function, returns the first value of SellStartDate in DataSet1 and the first value of LastReceiptDate in DataSet2.</span></span>  

```  
=DATEDIFF("yyyy", First(Fields!SellStartDate.Value, "DataSet1"), First(Fields!LastReceiptDate.Value, "DataSet2"))  
```  

-   <span data-ttu-id="5e830-171">La funzione `DatePart` restituisce un valore Integer contenente il componente specificato di un determinato valore Data. L'espressione seguente restituisce l'anno del primo valore di SellStartDate in DataSet1.</span><span class="sxs-lookup"><span data-stu-id="5e830-171">The `DatePart` function returns an Integer value containing the specified component of a given Date value.The following expression returns the year for the first value of the SellStartDate in DataSet1.</span></span> <span data-ttu-id="5e830-172">L'ambito del set di dati è specificato poiché il report include più set di dati.</span><span class="sxs-lookup"><span data-stu-id="5e830-172">The dataset scope is specified because there are multiple datasets in the report.</span></span>  

```  
=Datepart("yyyy", First(Fields!SellStartDate.Value, "DataSet1"))  

```  

-   <span data-ttu-id="5e830-173">La funzione `DateSerial` restituisce un valore Data che rappresenta un anno, un mese, un giorno specificato, con le informazioni sull'ora impostate su mezzanotte.</span><span class="sxs-lookup"><span data-stu-id="5e830-173">The `DateSerial` function returns a Date value representing a specified year, month, and day, with the time information set to midnight.</span></span> <span data-ttu-id="5e830-174">Nell'esempio seguente viene visualizzata la data di fine del mese precedente, basato sul mese corrente.</span><span class="sxs-lookup"><span data-stu-id="5e830-174">The following example displays the ending date for the prior month, based on the current month.</span></span>  

```  
=DateSerial(Year(Now()), Month(Now()), "1").AddDays(-1)  
```  

-   <span data-ttu-id="5e830-175">Le espressioni seguenti mostrano diverse date, in base a un valore di parametro di data selezionato dall'utente.</span><span class="sxs-lookup"><span data-stu-id="5e830-175">The following expressions display various dates based on a date parameter value selected by the user.</span></span>  

|<span data-ttu-id="5e830-176">Descrizione esempio</span><span class="sxs-lookup"><span data-stu-id="5e830-176">Example Description</span></span>|<span data-ttu-id="5e830-177">Esempio</span><span class="sxs-lookup"><span data-stu-id="5e830-177">Example</span></span>|  
|-------------------------|-------------|  
|<span data-ttu-id="5e830-178">Ieri</span><span class="sxs-lookup"><span data-stu-id="5e830-178">Yesterday</span></span>|`=DateSerial(Year(Parameters!TodaysDate.Value),Month(Parameters!TodaysDate.Value),Day(Parameters!TodaysDate.Value)-1)`|  
|<span data-ttu-id="5e830-179">Due giorni fa</span><span class="sxs-lookup"><span data-stu-id="5e830-179">Two Days Ago</span></span>|`=DateSerial(Year(Parameters!TodaysDate.Value),Month(Parameters!TodaysDate.Value),Day(Parameters!TodaysDate.Value)-2)`|  
|<span data-ttu-id="5e830-180">Un mese fa</span><span class="sxs-lookup"><span data-stu-id="5e830-180">One Month Ago</span></span>|`=DateSerial(Year(Parameters!TodaysDate.Value),Month(Parameters!TodaysDate.Value)-1,Day(Parameters!TodaysDate.Value))`|  
|<span data-ttu-id="5e830-181">Due mesi fa</span><span class="sxs-lookup"><span data-stu-id="5e830-181">Two Months Ago</span></span>|`=DateSerial(Year(Parameters!TodaysDate.Value),Month(Parameters!TodaysDate.Value)-2,Day(Parameters!TodaysDate.Value))`|  
|<span data-ttu-id="5e830-182">Un anno fa</span><span class="sxs-lookup"><span data-stu-id="5e830-182">One Year Ago</span></span>|`=DateSerial(Year(Parameters!TodaysDate.Value)-1,Month(Parameters!TodaysDate.Value),Day(Parameters!TodaysDate.Value))`|  
|<span data-ttu-id="5e830-183">Due anni fa</span><span class="sxs-lookup"><span data-stu-id="5e830-183">Two Years Ago</span></span>|`=DateSerial(Year(Parameters!TodaysDate.Value)-2,Month(Parameters!TodaysDate.Value),Day(Parameters!TodaysDate.Value))`|  

####  <a name="string-functions"></a><a name="StringFunctions"></a><span data-ttu-id="5e830-184">Funzioni stringa</span><span class="sxs-lookup"><span data-stu-id="5e830-184">String Functions</span></span>  

-   <span data-ttu-id="5e830-185">È possibile combinare più campi utilizzando operatori di concatenazione e costanti di [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5e830-185">Combine more than one field by using concatenation operators and [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] constants.</span></span> <span data-ttu-id="5e830-186">L'espressione seguente restituisce due campi, ognuno su una riga distinta nella stessa casella di testo:</span><span class="sxs-lookup"><span data-stu-id="5e830-186">The following expression returns two fields, each on a separate line in the same text box:</span></span>  

```  
=Fields!FirstName.Value & vbCrLf & Fields!LastName.Value   
```  

-   <span data-ttu-id="5e830-187">È possibile formattare date e numeri in una stringa tramite la funzione `Format`.</span><span class="sxs-lookup"><span data-stu-id="5e830-187">Format dates and numbers in a string with the `Format` function.</span></span> <span data-ttu-id="5e830-188">L'espressione seguente visualizza il valore dei parametri *StartDate* e *EndDate* nel formato di data estesa:</span><span class="sxs-lookup"><span data-stu-id="5e830-188">The following expression displays values of the *StartDate* and *EndDate* parameters in long date format:</span></span>  

```  
=Format(Parameters!StartDate.Value, "D") & " through " &  Format(Parameters!EndDate.Value, "D")    
```  

<span data-ttu-id="5e830-189">Se la casella di testo contiene solo una data o un numero, è necessario utilizzare la proprietà Format della casella di testo per applicare la formattazione anziché la `Format` funzione all'interno della casella di testo.</span><span class="sxs-lookup"><span data-stu-id="5e830-189">If the text box contains only a date or number, you should use the Format property of the text box to apply formatting instead of the `Format` function within the text box.</span></span>  

-   <span data-ttu-id="5e830-190">Le `Right` `Len` funzioni, e `InStr` sono utili per la restituzione di una sottostringa, ad *DOMAIN*esempio per la rimozione del nome \\ *username* utente di dominio al solo nome utente.</span><span class="sxs-lookup"><span data-stu-id="5e830-190">The `Right`, `Len`, and `InStr` functions are useful for returning a substring, for example, trimming *DOMAIN*\\*username* to just the user name.</span></span> <span data-ttu-id="5e830-191">L'espressione seguente restituisce la parte della stringa a destra del carattere barra rovesciata (\\) da un parametro denominato *User*:</span><span class="sxs-lookup"><span data-stu-id="5e830-191">The following expression returns the part of the string to the right of a backslash (\\) character from a parameter named *User*:</span></span>  

```  
=Right(Parameters!User.Value, Len(Parameters!User.Value) - InStr(Parameters!User.Value, "\"))  
```  

<span data-ttu-id="5e830-192">L'espressione seguente restituisce lo stesso valore di quello precedente, usando i membri della [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] <xref:System.String> classe anziché le [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] funzioni:</span><span class="sxs-lookup"><span data-stu-id="5e830-192">The following expression results in the same value as the previous one, using members of the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] <xref:System.String> class instead of [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] functions:</span></span>  

```  
=Parameters!User.Value.Substring(Parameters!User.Value.IndexOf("\")+1, Parameters!User.Value.Length-Parameters!User.Value.IndexOf("\")-1)  
```  

-   <span data-ttu-id="5e830-193">È possibile visualizzare i valori selezionati di un parametro multivalore.</span><span class="sxs-lookup"><span data-stu-id="5e830-193">Display the selected values from a multivalue parameter.</span></span> <span data-ttu-id="5e830-194">Nell'esempio seguente viene utilizzata la `Join` funzione per concatenare i valori selezionati del parametro *IsSelected* in un'unica stringa che può essere impostata come espressione per il valore di una casella di testo in un elemento del report:</span><span class="sxs-lookup"><span data-stu-id="5e830-194">The following example uses the `Join` function to concatenate the selected values of the parameter *MySelection* into a single string that can be set as an expression for the value of a text box in a report item:</span></span>  

```  
= Join(Parameters!MySelection.Value)  
```  

<span data-ttu-id="5e830-195">Nell'esempio riportato di seguito viene eseguita la stessa operazione dell'esempio precedente e viene visualizzata una stringa di testo prima dell'elenco dei valori selezionati.</span><span class="sxs-lookup"><span data-stu-id="5e830-195">The following example does the same as the above example, as well as displays a text string prior to the list of selected values.</span></span>  

```  
="Report for " & JOIN(Parameters!MySelection.Value, " & ")  

```  

-   <span data-ttu-id="5e830-196">Le `Regex` funzioni di [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] <xref:System.Text.RegularExpressions> sono utili per modificare il formato di stringhe esistenti, ad esempio per formattare un numero di telefono.</span><span class="sxs-lookup"><span data-stu-id="5e830-196">The `Regex` functions from the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] <xref:System.Text.RegularExpressions> are useful for changing the format of existing strings, for example, formatting a telephone number.</span></span> <span data-ttu-id="5e830-197">Nell'espressione seguente viene utilizzata la `Replace` funzione per modificare il formato di un numero di telefono a dieci cifre in un campo da "*nnn* - *nnn* - *nnnn*" a "(*nnn*) *nnn* - *nnnn*":</span><span class="sxs-lookup"><span data-stu-id="5e830-197">The following expression uses the `Replace` function to change the format of a ten-digit telephone number in a field from "*nnn*-*nnn*-*nnnn*" to "(*nnn*) *nnn*-*nnnn*":</span></span>  

```  
=System.Text.RegularExpressions.Regex.Replace(Fields!Phone.Value, "(\d{3})[ -.]*(\d{3})[ -.]*(\d{4})", "($1) $2-$3")  
```  

> [!NOTE]  
>  <span data-ttu-id="5e830-198">Verificare che nel valore di Fields!Phone.Value non siano contenuti spazi aggiuntivi e che sia di tipo <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="5e830-198">Verify that the value for Fields!Phone.Value has no extra spaces and is of type <xref:System.String>.</span></span>  

#### <a name="lookup"></a><span data-ttu-id="5e830-199">Ricerca</span><span class="sxs-lookup"><span data-stu-id="5e830-199">Lookup</span></span>  

-   <span data-ttu-id="5e830-200">Specificando un campo chiave è possibile utilizzare la funzione `Lookup` per recuperare un valore da un set di dati per una relazione uno-a-uno, ad esempio, una coppia chiave-valore.</span><span class="sxs-lookup"><span data-stu-id="5e830-200">By specifying a key field, you can use the `Lookup` function to retrieve a value from a dataset for a one-to-one relationship, for example, a key-value pair.</span></span> <span data-ttu-id="5e830-201">Nell'espressione seguente viene visualizzato il nome prodotto da un set di dati ("Product"), in base all'identificatore del prodotto con cui eseguire la corrispondenza:</span><span class="sxs-lookup"><span data-stu-id="5e830-201">The following expression displays the product name from a dataset ("Product"), given the product identifier to match on:</span></span>  

```  
=Lookup(Fields!PID.Value, Fields!ProductID.Value, Fields!ProductName.Value, "Product")  
```  

#### <a name="lookupset"></a><span data-ttu-id="5e830-202">LookupSet</span><span class="sxs-lookup"><span data-stu-id="5e830-202">LookupSet</span></span>  

-   <span data-ttu-id="5e830-203">Specificando un campo chiave è possibile utilizzare la funzione `LookupSet` per recuperare un set di valori da un set di dati per una relazione uno-a-molti.</span><span class="sxs-lookup"><span data-stu-id="5e830-203">By specifying a key field, you can use the `LookupSet` function to retrieve a set of values from a dataset for a one-to-many relationship.</span></span> <span data-ttu-id="5e830-204">Ad esempio una persona può disporre di più numeri di telefono.</span><span class="sxs-lookup"><span data-stu-id="5e830-204">For example, a person can have multiple telephone numbers.</span></span> <span data-ttu-id="5e830-205">Nell'esempio seguente, si supponga che nel set di dati PhoneList sia contenuto un identificatore della persona e un numero di telefono in ogni riga.</span><span class="sxs-lookup"><span data-stu-id="5e830-205">In the following example, assume the dataset PhoneList contains a person identifier and a telephone number in each row.</span></span> <span data-ttu-id="5e830-206">Tramite `LookupSet` viene restituita una matrice di valori.</span><span class="sxs-lookup"><span data-stu-id="5e830-206">`LookupSet` returns an array of values.</span></span> <span data-ttu-id="5e830-207">L'espressione seguente combina i valori restituiti in un'unica stringa e visualizza l'elenco di numeri di telefono per la persona specificata da ContactID:</span><span class="sxs-lookup"><span data-stu-id="5e830-207">The following expression combines the return values into a single string and displays the list of telephone numbers for the person specified by ContactID:</span></span>  

```  
=Join(LookupSet(Fields!ContactID.Value, Fields!PersonID.Value, Fields!PhoneNumber.Value, "PhoneList"),",")  
```  

####  <a name="conversion-functions"></a><a name="ConversionFunctions"></a><span data-ttu-id="5e830-208">Funzioni di conversione</span><span class="sxs-lookup"><span data-stu-id="5e830-208">Conversion Functions</span></span>  
<span data-ttu-id="5e830-209">È possibile utilizzare le funzioni di [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] per convertire un campo da un tipo di dati a un altro.</span><span class="sxs-lookup"><span data-stu-id="5e830-209">You can use [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] functions to convert a field from the one data type to a different data type.</span></span> <span data-ttu-id="5e830-210">Le funzioni di conversione possono essere utilizzate per convertire il tipo di dati predefinito di un campo nel tipo di dati necessario per i calcoli oppure per combinare testo.</span><span class="sxs-lookup"><span data-stu-id="5e830-210">Conversion functions can be used to convert the default data type for a field to the data type needed for calculations or to combine text.</span></span>  

-   <span data-ttu-id="5e830-211">L'espressione seguente converte la costante 500 nel tipo Decimal, in modo da confrontarla con un tipo di dati money di [!INCLUDE[tsql](../../includes/tsql-md.md)] nel campo Valore per un'espressione di filtro.</span><span class="sxs-lookup"><span data-stu-id="5e830-211">The following expression converts the constant 500 to type Decimal in order to compare it to a [!INCLUDE[tsql](../../includes/tsql-md.md)] money data type in the Value field for a filter expression.</span></span>  

```  
=CDec(500)  
```  

-   <span data-ttu-id="5e830-212">L'espressione seguente visualizza il numero di valori selezionati per il parametro multivalore *MySelection*.</span><span class="sxs-lookup"><span data-stu-id="5e830-212">The following expression displays the number of values selected for the multivalue parameter *MySelection*.</span></span>  

```  
=CStr(Parameters!MySelection.Count)  
```  

####  <a name="decision-functions"></a><a name="DecisionFunctions"></a> <span data-ttu-id="5e830-213">Funzioni condizionali</span><span class="sxs-lookup"><span data-stu-id="5e830-213">Decision Functions</span></span>  

-   <span data-ttu-id="5e830-214">La funzione `Iif` restituisce uno di due valori a seconda che l'espressione sia True o False.</span><span class="sxs-lookup"><span data-stu-id="5e830-214">The `Iif` function returns one of two values depending on whether the expression is true or not.</span></span> <span data-ttu-id="5e830-215">Nell'espressione seguente viene utilizzata la funzione `Iif` per restituire un valore booleano `True` se il valore `LineTotal` è maggiore di 100.</span><span class="sxs-lookup"><span data-stu-id="5e830-215">The following expression uses the `Iif` function to return a Boolean value of `True` if the value of `LineTotal` exceeds 100.</span></span> <span data-ttu-id="5e830-216">In caso contrario, viene restituito `False`:</span><span class="sxs-lookup"><span data-stu-id="5e830-216">Otherwise it returns `False`:</span></span>  

```  
=IIF(Fields!LineTotal.Value > 100, True, False)  
```  

-   <span data-ttu-id="5e830-217">È possibile utilizzare più funzioni `IIF`, note anche come funzioni IIF nidificate, per restituire uno di tre valori possibili a seconda del valore di `PctComplete`.</span><span class="sxs-lookup"><span data-stu-id="5e830-217">Use multiple `IIF` functions (also known as "nested IIFs") to return one of three values depending on the value of `PctComplete`.</span></span> <span data-ttu-id="5e830-218">L'espressione seguente può essere inserita nel colore di riempimento di una casella di testo per modificare il colore di sfondo in base al valore della casella di testo.</span><span class="sxs-lookup"><span data-stu-id="5e830-218">The following expression can be placed in the fill color of a text box to change the background color depending on the value in the text box.</span></span>  

```  
=IIF(Fields!PctComplete.Value >= 10, "Green", IIF(Fields!PctComplete.Value >= 1, "Blue", "Red"))  
```  

<span data-ttu-id="5e830-219">I valori maggiori o uguali a 10 vengono visualizzati con uno sfondo verde, quelli compresi tra 1 e 9 con uno sfondo blu e quelli minori di 1 con uno sfondo rosso.</span><span class="sxs-lookup"><span data-stu-id="5e830-219">Values greater than or equal to 10 display with a green background, between 1 and 9 display with a blue background, and less than 1 display with a red background.</span></span>  

-   <span data-ttu-id="5e830-220">Per ottenere la stessa funzionalità, è anche possibile utilizzare la funzione `Switch`.</span><span class="sxs-lookup"><span data-stu-id="5e830-220">A different way to get the same functionality uses the `Switch` function.</span></span> <span data-ttu-id="5e830-221">La funzione `Switch` risulta utile quando è necessario testare tre o più condizioni.</span><span class="sxs-lookup"><span data-stu-id="5e830-221">The `Switch` function is useful when you have three or more conditions to test.</span></span> <span data-ttu-id="5e830-222">La funzione `Switch` restituisce il valore associato alla prima espressione in una serie che restituisce True:</span><span class="sxs-lookup"><span data-stu-id="5e830-222">The `Switch` function returns the value associated with the first expression in a series that evaluates to true:</span></span>  

```  
=Switch(Fields!PctComplete.Value >= 10, "Green", Fields!PctComplete.Value >= 1, "Blue", Fields!PctComplete.Value = 1, "Yellow", Fields!PctComplete.Value <= 0, "Red",)  
```  

<span data-ttu-id="5e830-223">I valori maggiori o uguali a 10 vengono visualizzati con uno sfondo verde, quelli compresi tra 1 e 9 con uno sfondo blu, quelli uguali a 1 con uno sfondo giallo e quelli minori o uguali a 0 con uno sfondo rosso.</span><span class="sxs-lookup"><span data-stu-id="5e830-223">Values greater than or equal to 10 display with a green background, between 1 and 9 display with a blue background, equal to 1 display with a yellow background, and 0 or less display with a red background.</span></span>  

-   <span data-ttu-id="5e830-224">Viene verificato il valore del campo `ImportantDate` e viene restituito "Red" se è antecedente a una settimana e "Blue" in caso contrario.</span><span class="sxs-lookup"><span data-stu-id="5e830-224">Test the value of the `ImportantDate` field and return "Red" if it is more than a week old, and "Blue" otherwise.</span></span> <span data-ttu-id="5e830-225">Questa espressione può essere utilizzata per controllare la proprietà Color di una casella di testo in un elemento del report:</span><span class="sxs-lookup"><span data-stu-id="5e830-225">This expression can be used to control the Color property of a text box in a report item:</span></span>  

```  
=IIF(DateDiff("d",Fields!ImportantDate.Value, Now())>7,"Red","Blue")  
```  

-   <span data-ttu-id="5e830-226">Viene verificato il valore del campo `PhoneNumber` e viene restituito "No Value" se è `null` (`Nothing` in [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]); in caso contrario, viene restituito il valore del numero di telefono.</span><span class="sxs-lookup"><span data-stu-id="5e830-226">Test the value of the `PhoneNumber` field and return "No Value" if it is `null` (`Nothing` in [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]); otherwise return the phone number value.</span></span> <span data-ttu-id="5e830-227">Questa espressione può essere utilizzata per controllare il valore di una casella di testo in un elemento del report.</span><span class="sxs-lookup"><span data-stu-id="5e830-227">This expression can be used to control the value of a text box in a report item.</span></span>  

```  
=IIF(Fields!PhoneNumber.Value Is Nothing,"No Value",Fields!PhoneNumber.Value)  
```  

-   <span data-ttu-id="5e830-228">Viene verificato il valore del campo `Department` e viene restituito il nome di un sottoreport o `null` (`Nothing` in [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="5e830-228">Test the value of the `Department` field and return either a subreport name or a `null` (`Nothing` in [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]).</span></span> <span data-ttu-id="5e830-229">Questa espressione può essere utilizzata per i sottoreport drill-through condizionali.</span><span class="sxs-lookup"><span data-stu-id="5e830-229">This expression can be used for conditional drillthrough subreports.</span></span>  

```  
=IIF(Fields!Department.Value = "Development", "EmployeeReport", Nothing)  
```  

-   <span data-ttu-id="5e830-230">Viene verificato se il valore di un campo è Null.</span><span class="sxs-lookup"><span data-stu-id="5e830-230">Test if a field value is null.</span></span> <span data-ttu-id="5e830-231">Questa espressione può essere utilizzata per controllare la proprietà `Hidden` di un elemento immagine del report.</span><span class="sxs-lookup"><span data-stu-id="5e830-231">This expression can be used to control the `Hidden` property of an image report item.</span></span> <span data-ttu-id="5e830-232">Nell'esempio seguente l'immagine specificata dal campo [LargePhoto] viene visualizzata solo se il valore del campo non è Null.</span><span class="sxs-lookup"><span data-stu-id="5e830-232">In the following example, the image specified by the field [LargePhoto] is displayed only if the value of the field is not null.</span></span>  

```  
=IIF(IsNothing(Fields!LargePhoto.Value),True,False)  
```  

-   <span data-ttu-id="5e830-233">La funzione `MonthName` restituisce il valore di stringa contenente il nome del mese specificato.</span><span class="sxs-lookup"><span data-stu-id="5e830-233">The `MonthName` function returns a string value containing the name of the specified month.</span></span> <span data-ttu-id="5e830-234">Nell'esempio seguente viene visualizzato ND nel campo Mese quando il campo contiene il valore 0.</span><span class="sxs-lookup"><span data-stu-id="5e830-234">The following example displays NA in the Month field when the field contains the value of 0.</span></span>  

```  
IIF(Fields!Month.Value=0,"NA",MonthName(IIF(Fields!Month.Value=0,1,Fields!Month.Value)))  

```  

###  <a name="report-functions"></a><a name="ReportFunctions"></a> <span data-ttu-id="5e830-235">Funzioni di report</span><span class="sxs-lookup"><span data-stu-id="5e830-235">Report Functions</span></span>  
<span data-ttu-id="5e830-236">In un'espressione è possibile aggiungere un riferimento a funzioni per i report aggiuntive tramite le quali vengono modificati i dati di un report.</span><span class="sxs-lookup"><span data-stu-id="5e830-236">In an expression, you can add a reference to additional report functions that manipulate data in a report.</span></span> <span data-ttu-id="5e830-237">In questa sezione vengono forniti esempi di due funzioni per i report.</span><span class="sxs-lookup"><span data-stu-id="5e830-237">This section provides examples for two of these functions.</span></span> <span data-ttu-id="5e830-238">Per altre informazioni sulle funzioni di report ed esempi, vedere [Riferimento a funzioni di aggregazione &#40;Generatore report e SSRS&#41;](report-builder-functions-aggregate-functions-reference.md).</span><span class="sxs-lookup"><span data-stu-id="5e830-238">For more information about report functions and examples, see [Aggregate Functions Reference &#40;Report Builder and SSRS&#41;](report-builder-functions-aggregate-functions-reference.md).</span></span>  

#####  <a name="sum"></a><a name="Sum"></a><span data-ttu-id="5e830-239">Somma</span><span class="sxs-lookup"><span data-stu-id="5e830-239">Sum</span></span>  

-   <span data-ttu-id="5e830-240">La funzione `Sum` consente di calcolare il totale dei valori di un gruppo o di un'area dati.</span><span class="sxs-lookup"><span data-stu-id="5e830-240">The `Sum` function can total the values in a group or data region.</span></span> <span data-ttu-id="5e830-241">Può risultare utile nell'intestazione o nel piè di pagina di un gruppo.</span><span class="sxs-lookup"><span data-stu-id="5e830-241">This function can be useful in the header or footer of a group.</span></span> <span data-ttu-id="5e830-242">L'espressione seguente visualizza la somma dei dati del gruppo o dell'area dati Order:</span><span class="sxs-lookup"><span data-stu-id="5e830-242">The following expression displays the sum of data in the Order group or data region:</span></span>  

```  
=Sum(Fields!LineTotal.Value, "Order")  
```  

-   <span data-ttu-id="5e830-243">È possibile utilizzare la funzione `Sum` anche per i calcoli di aggregazione condizionali.</span><span class="sxs-lookup"><span data-stu-id="5e830-243">You can also use the `Sum` function for conditional aggregate calculations.</span></span> <span data-ttu-id="5e830-244">Se ad esempio un set di dati include un campo denominato State, con i valori possibili Not Started, Started e Finished, l'espressione seguente, se inserita nell'intestazione di un gruppo, calcola la somma aggregata solo per il valore Finished:</span><span class="sxs-lookup"><span data-stu-id="5e830-244">For example, if a dataset has a field that is named State with possible values Not Started, Started, Finished, the following expression, when placed in a group header, calculates the aggregate sum for only the value Finished:</span></span>  

```  
=Sum(IIF(Fields!State.Value = "Finished", 1, 0))  
```  

#####  <a name="rownumber"></a><a name="RowNumber"></a><span data-ttu-id="5e830-245">RowNumber</span><span class="sxs-lookup"><span data-stu-id="5e830-245">RowNumber</span></span>  

-   <span data-ttu-id="5e830-246">La funzione `RowNumber`, se utilizzata in una casella di testo in un'area dati, visualizza il numero di riga di ogni istanza della casella di testo in cui compare l'espressione.</span><span class="sxs-lookup"><span data-stu-id="5e830-246">The `RowNumber` function, when used in a text box within a data region, displays the row number for each instance of the text box in which the expression appears.</span></span> <span data-ttu-id="5e830-247">Questa funzione può essere utile per numerare le righe di una tabella,</span><span class="sxs-lookup"><span data-stu-id="5e830-247">This function can be useful to number rows in a table.</span></span> <span data-ttu-id="5e830-248">ma anche per attività più complesse, ad esempio per l'inserimento di interruzioni di pagina in base al numero di righe.</span><span class="sxs-lookup"><span data-stu-id="5e830-248">It can also be useful for more complex tasks, such as providing page breaks based on number of rows.</span></span> <span data-ttu-id="5e830-249">Per ulteriori informazioni, vedere [Interruzioni di pagina](#PageBreaks) di seguito in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="5e830-249">For more information, see [Page Breaks](#PageBreaks) in this topic.</span></span>  

<span data-ttu-id="5e830-250">L'ambito specificato per `RowNumber` controlla quando inizia la rinumerazione.</span><span class="sxs-lookup"><span data-stu-id="5e830-250">The scope you specify for `RowNumber` controls when renumbering begins.</span></span> <span data-ttu-id="5e830-251">La parola chiave `Nothing` indica che il conteggio inizierà dalla prima riga dell'area dati più esterna.</span><span class="sxs-lookup"><span data-stu-id="5e830-251">The `Nothing` keyword indicates that the function will start counting at the first row in the outermost data region.</span></span> <span data-ttu-id="5e830-252">Per iniziare il conteggio all'interno di aree dati nidificate, utilizzare il nome dell'area dati.</span><span class="sxs-lookup"><span data-stu-id="5e830-252">To start counting within nested data regions, use the name of the data region.</span></span> <span data-ttu-id="5e830-253">Per iniziare il conteggio in un gruppo, utilizzare il nome del gruppo.</span><span class="sxs-lookup"><span data-stu-id="5e830-253">To start counting within a group, use the name of the group.</span></span>  

```  
=RowNumber(Nothing)  
```  

##  <a name="appearance-of-report-data"></a><a name="AppearanceofReportData"></a> <span data-ttu-id="5e830-254">Aspetto dei dati del report</span><span class="sxs-lookup"><span data-stu-id="5e830-254">Appearance of Report Data</span></span>  
<span data-ttu-id="5e830-255">È possibile utilizzare le espressioni per modificare l'aspetto dei dati in un report.</span><span class="sxs-lookup"><span data-stu-id="5e830-255">You can use expressions to manipulate how data appears on a report.</span></span> <span data-ttu-id="5e830-256">È possibile, ad esempio, visualizzare i valori di due campi in una sola casella di testo, visualizzare informazioni sul report o intervenire sulla modalità di inserimento delle interruzioni di pagina nel report.</span><span class="sxs-lookup"><span data-stu-id="5e830-256">For example, you can display the values of two fields in a single text box, display information about the report, or affect how page breaks are inserted in the report.</span></span>  

###  <a name="page-headers-and-footers"></a><a name="PageHeadersandFooters"></a><span data-ttu-id="5e830-257">Intestazioni e piè di pagina</span><span class="sxs-lookup"><span data-stu-id="5e830-257">Page Headers and Footers</span></span>  
<span data-ttu-id="5e830-258">Se si desidera che nel piè di pagina del report vengano visualizzati il nome del report e il numero di pagina,</span><span class="sxs-lookup"><span data-stu-id="5e830-258">When designing a report, you may want to display the name of the report and page number in the report footer.</span></span> <span data-ttu-id="5e830-259">è possibile utilizzare le espressioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5e830-259">To do this, you can use the following expressions:</span></span>  

-   <span data-ttu-id="5e830-260">L'espressione seguente restituisce il nome del report e la data di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="5e830-260">The following expression provides the name of the report and the time it was run.</span></span> <span data-ttu-id="5e830-261">Può essere inserita in una casella di testo nel piè di pagina del report oppure nel corpo del report.</span><span class="sxs-lookup"><span data-stu-id="5e830-261">It can be placed in a text box in the report footer or in the body of the report.</span></span> <span data-ttu-id="5e830-262">Per la formattazione dell'ora viene utilizzata la stringa di formattazione di [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] per la data breve:</span><span class="sxs-lookup"><span data-stu-id="5e830-262">The time is formatted with the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] formatting string for short date:</span></span>  

```  
=Globals.ReportName & ", dated " & Format(Globals.ExecutionTime, "d")  
```  

-   <span data-ttu-id="5e830-263">L'espressione seguente, inserita in una casella di testo nel piè di pagina di un report, restituisce il numero di pagina e le pagine totali del report:</span><span class="sxs-lookup"><span data-stu-id="5e830-263">The following expression, placed in a text box in the footer of a report, provides page number and total pages in the report:</span></span>  

```  
=Globals.PageNumber & " of " & Globals.TotalPages  
```  

<span data-ttu-id="5e830-264">Negli esempi seguenti viene illustrato come visualizzare il primo e l'ultimo valore di una pagina nell'intestazione di pagina.</span><span class="sxs-lookup"><span data-stu-id="5e830-264">The following examples describe how to display the first and last values from a page in the page header, similar to what you might find in a directory listing.</span></span> <span data-ttu-id="5e830-265">Si suppone che sia presente un'area dati contenente una casella di testo denominata `LastName`.</span><span class="sxs-lookup"><span data-stu-id="5e830-265">The example assumes a data region that contains a text box named `LastName`.</span></span>  

-   <span data-ttu-id="5e830-266">L'espressione seguente, inserita in una casella di testo a sinistra dell'intestazione di pagina, restituisce il primo valore della casella di testo `LastName` nella pagina:</span><span class="sxs-lookup"><span data-stu-id="5e830-266">The following expression, placed in a text box on the left side of the page header, provides the first value of the `LastName` text box on the page:</span></span>  

```  
=First(ReportItems("LastName").Value)  
```  

-   <span data-ttu-id="5e830-267">L'espressione seguente, se inserita in una casella di testo a destra dell'intestazione di pagina, restituisce l'ultimo valore della casella di testo `LastName` nella pagina:</span><span class="sxs-lookup"><span data-stu-id="5e830-267">The following expression, placed in a text box on the right side of the page header, provides the last value of the `LastName` text box on the page:</span></span>  

```  
=Last(ReportItems("LastName").Value)  
```  

<span data-ttu-id="5e830-268">Nell'esempio seguente viene illustrato come visualizzare un totale di pagina.</span><span class="sxs-lookup"><span data-stu-id="5e830-268">The following example describes how to display a page total.</span></span> <span data-ttu-id="5e830-269">Si suppone che sia presente un'area dati contenente una casella di testo denominata `Cost`.</span><span class="sxs-lookup"><span data-stu-id="5e830-269">The example assumes a data region that contains a text box named `Cost`.</span></span>  

-   <span data-ttu-id="5e830-270">L'espressione seguente, inserita nell'intestazione o nel piè di pagina, restituisce la somma dei valori presenti nella casella di testo `Cost` nella pagina:</span><span class="sxs-lookup"><span data-stu-id="5e830-270">The following expression, placed in the page header or footer, provides the sum of the values in the `Cost` text box for the page:</span></span>  

```  
=Sum(ReportItems("Cost").Value)  
```  

> [!NOTE]  
>  <span data-ttu-id="5e830-271">In un'intestazione o piè di pagina è possibile fare riferimento a un solo elemento del report in ogni espressione.</span><span class="sxs-lookup"><span data-stu-id="5e830-271">You can refer to only one report item per expression in a page header or footer.</span></span> <span data-ttu-id="5e830-272">Inoltre, nelle espressioni di intestazione e piè di pagina è possibile fare riferimento al nome della casella di testo, ma non all'espressione di dati effettiva al suo interno.</span><span class="sxs-lookup"><span data-stu-id="5e830-272">Also, you can refer to the text box name, but not the actual data expression within the text box, in page header and footer expressions.</span></span>  

###  <a name="page-breaks"></a><a name="PageBreaks"></a> <span data-ttu-id="5e830-273">Interruzioni di pagina</span><span class="sxs-lookup"><span data-stu-id="5e830-273">Page Breaks</span></span>  
<span data-ttu-id="5e830-274">In alcuni report può essere necessario inserire un'interruzione di pagina alla fine di un numero di righe specificato anziché alla fine di gruppi o elementi del report oppure in aggiunta a questi.</span><span class="sxs-lookup"><span data-stu-id="5e830-274">In some reports, you may want to place a page break at the end of a specified number of rows instead of, or in addition to, on groups or report items.</span></span> <span data-ttu-id="5e830-275">A tale scopo, creare un gruppo che contiene i gruppi o i record di dettaglio desiderati, aggiungere un'interruzione di pagina al gruppo, quindi aggiungere un'espressione di raggruppamento per eseguire il raggruppamento in base al numero di righe specificato.</span><span class="sxs-lookup"><span data-stu-id="5e830-275">To do this, create a group that contains the groups or detail records you want, add a page break to the group, and then add a group expression to group by a specified number of rows.</span></span>  

-   <span data-ttu-id="5e830-276">L'espressione seguente, se inserita nell'espressione di raggruppamento, assegna un numero a ogni set di 25 righe.</span><span class="sxs-lookup"><span data-stu-id="5e830-276">The following expression, when placed in the group expression, assigns a number to each set of 25 rows.</span></span> <span data-ttu-id="5e830-277">Se si definisce un'interruzione di pagina per il gruppo, si ottiene un'interruzione di pagina ogni 25 righe.</span><span class="sxs-lookup"><span data-stu-id="5e830-277">When a page break is defined for the group, this expression results in a page break every 25 rows.</span></span>  

```  
=Ceiling(RowNumber(Nothing)/25)  
```  

<span data-ttu-id="5e830-278">Per consentire all'utente di impostare un valore relativo al numero di righe per pagina, creare un parametro denominato `RowsPerPage` su cui basare l'espressione di raggruppamento, come illustrato nell'espressione seguente:</span><span class="sxs-lookup"><span data-stu-id="5e830-278">To allow the user to set a value for the number of rows per page, create a parameter named `RowsPerPage` and base the group expression on the parameter, as shown in the following expression:</span></span>  

```  
=Ceiling(RowNumber(Nothing)/Parameters!RowsPerPage.Value)  
```  

<span data-ttu-id="5e830-279">Per altre informazioni sull'impostazione di interruzioni di pagina per un gruppo, vedere [Aggiunta di un'interruzione di pagina &#40;Generatore report e SSRS&#41;](add-a-page-break-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="5e830-279">For more information about setting page breaks for a group, see [Add a Page Break &#40;Report Builder and SSRS&#41;](add-a-page-break-report-builder-and-ssrs.md).</span></span>  

##  <a name="properties"></a><span data-ttu-id="5e830-280">Proprietà <a name="Properties"></a></span><span class="sxs-lookup"><span data-stu-id="5e830-280"><a name="Properties"></a> Properties</span></span>  
<span data-ttu-id="5e830-281">Le espressioni non vengono utilizzate solo per visualizzare dati in caselle di testo.</span><span class="sxs-lookup"><span data-stu-id="5e830-281">Expressions are not only used to display data in text boxes.</span></span> <span data-ttu-id="5e830-282">Possono essere utilizzate anche per modificare la modalità di applicazione delle proprietà agli elementi del report.</span><span class="sxs-lookup"><span data-stu-id="5e830-282">They can also be used to change how properties are applied to report items.</span></span> <span data-ttu-id="5e830-283">È possibile modificare le informazioni sullo stile di un elemento del report oppure modificarne la visibilità.</span><span class="sxs-lookup"><span data-stu-id="5e830-283">You can change style information for a report item, or change its visibility.</span></span>  

###  <a name="formatting"></a><a name="Formatting"></a><span data-ttu-id="5e830-284">Formattazione</span><span class="sxs-lookup"><span data-stu-id="5e830-284">Formatting</span></span>  

-   <span data-ttu-id="5e830-285">L'espressione seguente, se usata nella proprietà Color di una casella di testo, cambia il colore del testo a seconda del valore del campo `Profit` :</span><span class="sxs-lookup"><span data-stu-id="5e830-285">The following expression, when used in the Color property of a text box, changes the color of the text depending on the value of the `Profit` field:</span></span>  

```  
=Iif(Fields!Profit.Value < 0, "Red", "Black")  
```  

<span data-ttu-id="5e830-286">È anche possibile utilizzare la variabile oggetto [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]`Me`.</span><span class="sxs-lookup"><span data-stu-id="5e830-286">You can also use the [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] object variable `Me`.</span></span> <span data-ttu-id="5e830-287">Questa variabile consente di fare riferimento in un altro modo al valore di una casella di testo.</span><span class="sxs-lookup"><span data-stu-id="5e830-287">This variable is another way of referring to the value of a text box.</span></span>  

`=Iif(Me.Value < 0, "Red", "Black")`  

-   <span data-ttu-id="5e830-288">L'espressione seguente, se usata nella proprietà BackgroundColor di un elemento del report in un'area dati, alterna il verde chiaro e il bianco come colore di sfondo di ogni riga:</span><span class="sxs-lookup"><span data-stu-id="5e830-288">The following expression, when used in the BackgroundColor property of a report item in a data region, alternates the background color of each row between pale green and white:</span></span>  

```  
=Iif(RowNumber(Nothing) Mod 2, "PaleGreen", "White")  
```  

<span data-ttu-id="5e830-289">Se si utilizza un'espressione per un ambito specifico, potrebbe essere necessario indicare il set di dati per la funzione di aggregazione.</span><span class="sxs-lookup"><span data-stu-id="5e830-289">If you are using an expression for a specified scope, you may have to indicate the dataset for the aggregate function:</span></span>  

```  
=Iif(RowNumber("Employees") Mod 2, "PaleGreen", "White")  
```  

> [!NOTE]  
>  <span data-ttu-id="5e830-290">I colori disponibili provengono dall'enumerazione KnownColor di [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5e830-290">Available colors come from the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] KnownColor enumeration.</span></span>  

### <a name="chart-colors"></a><span data-ttu-id="5e830-291">Colori del grafico</span><span class="sxs-lookup"><span data-stu-id="5e830-291">Chart Colors</span></span>  
<span data-ttu-id="5e830-292">Per specificare i colori per un grafico con forme, è possibile utilizzare codice personalizzato per controllare l'ordine in base al quale viene eseguito il mapping dei colori ai valori dei punti dati.</span><span class="sxs-lookup"><span data-stu-id="5e830-292">To specify colors for a Shape chart, you can use custom code to control the order that colors are mapped to data point values.</span></span> <span data-ttu-id="5e830-293">In questo modo è possibile utilizzare colori coerenti per più grafici con gli stessi gruppi di categorie.</span><span class="sxs-lookup"><span data-stu-id="5e830-293">This helps you use consistent colors for multiple charts that have the same category groups.</span></span> <span data-ttu-id="5e830-294">Per altre informazioni, vedere [Specifica di colori coerenti in più grafici con forme &#40;Generatore report e SSRS&#41;](charts-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="5e830-294">For more information, see [Specify Consistent Colors across Multiple Shape Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md).</span></span>  

###  <a name="visibility"></a><a name="Visibility"></a><span data-ttu-id="5e830-295">Visibilità</span><span class="sxs-lookup"><span data-stu-id="5e830-295">Visibility</span></span>  
<span data-ttu-id="5e830-296">È possibile visualizzare e nascondere elementi in un report utilizzando le proprietà di visibilità per gli elementi del report.</span><span class="sxs-lookup"><span data-stu-id="5e830-296">You can show and hide items in a report using the visibility properties for the report item.</span></span> <span data-ttu-id="5e830-297">In un'area dati, ad esempio una tabella, è possibile nascondere inizialmente le righe di dettaglio in base al valore di un'espressione.</span><span class="sxs-lookup"><span data-stu-id="5e830-297">In a data region such as a table, you can initially hide detail rows based on the value in an expression.</span></span>  

-   <span data-ttu-id="5e830-298">L'espressione seguente, se utilizzata per la visibilità iniziale delle righe di dettaglio in un gruppo, visualizza le righe di dettaglio per tutte le vendite con un valore superiore al 90 percento nel campo `PctQuota` :</span><span class="sxs-lookup"><span data-stu-id="5e830-298">The following expression, when used for initial visibility of detail rows in a group, shows the detail rows for all sales exceeding 90 percent in the `PctQuota` field:</span></span>  

```  
=Iif(Fields!PctQuota.Value>.9, False, True)  
```  

-   <span data-ttu-id="5e830-299">L'espressione seguente, se impostata nella proprietà Hidden di una tabella, visualizza la tabella solo se contiene più di 12 righe:</span><span class="sxs-lookup"><span data-stu-id="5e830-299">The following expression, when set in the Hidden property of a table, shows the table only if it has more than 12 rows:</span></span>  

```  
=IIF(CountRows()>12,false,true)  
```  

-   <span data-ttu-id="5e830-300">L'espressione seguente, se impostata nella `Hidden` proprietà di una colonna, Visualizza la colonna solo se il campo esiste nel set di dati del report dopo che i dati sono stati recuperati dall'origine dati:</span><span class="sxs-lookup"><span data-stu-id="5e830-300">The following expression, when set in the `Hidden` property of a column, shows the column only if the field exists in the report dataset after the data is retrieved from the data source:</span></span>  

```  
=IIF(Fields!Column_1.IsMissing, true, false)  
```  

###  <a name="urls"></a><a name="Hyperlinks"></a><span data-ttu-id="5e830-301">URL</span><span class="sxs-lookup"><span data-stu-id="5e830-301">URLs</span></span>  
<span data-ttu-id="5e830-302">È possibile personalizzare gli URL utilizzando i dati del report e inoltre controllare in base a condizioni specifiche se gli URL vengono aggiunti come azione per una casella di testo.</span><span class="sxs-lookup"><span data-stu-id="5e830-302">You can customize URLs by using report data and also conditionally control whether URLs are added as an action for a text box.</span></span>  

-   <span data-ttu-id="5e830-303">L'espressione seguente, se utilizzata come azione per una casella di testo, genera un URL personalizzato in cui è specificato il campo del set di dati `EmployeeID` come parametro.</span><span class="sxs-lookup"><span data-stu-id="5e830-303">The following expression, when used as an action on a text box, generates a customized URL that specifies the dataset field `EmployeeID` as a URL parameter.</span></span>  

```  
="http://adventure-works/MyInfo?ID=" & Fields!EmployeeID.Value  
```  

<span data-ttu-id="5e830-304">Per altre informazioni, vedere [Aggiunta di un collegamento ipertestuale a un URL &#40;Generatore report e SSRS&#41;](add-a-hyperlink-to-a-url-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="5e830-304">For more information, see [Add a Hyperlink to a URL &#40;Report Builder and SSRS&#41;](add-a-hyperlink-to-a-url-report-builder-and-ssrs.md).</span></span>  

-   <span data-ttu-id="5e830-305">L'espressione seguente controlla in base a specifiche condizioni se aggiungere un URL in una casella di testo.</span><span class="sxs-lookup"><span data-stu-id="5e830-305">The following expression conditionally controls whether to add a URL in a text box.</span></span> <span data-ttu-id="5e830-306">L'espressione dipende da un parametro denominato `IncludeURLs` che consente all'utente di decidere se includere o meno URL attivi in un report.</span><span class="sxs-lookup"><span data-stu-id="5e830-306">This expression depends on a parameter named `IncludeURLs` that allows a user to decide whether to include active URLs in a report.</span></span> <span data-ttu-id="5e830-307">Questa espressione viene impostata come azione per una casella di testo.</span><span class="sxs-lookup"><span data-stu-id="5e830-307">This expression is set as an action on a text box.</span></span> <span data-ttu-id="5e830-308">Se si imposta il parametro su False e quindi si visualizza il report, è possibile esportare il report in Microsoft Excel senza collegamenti ipertestuali.</span><span class="sxs-lookup"><span data-stu-id="5e830-308">By setting the parameter to False and then viewing the report, you can export the report Microsoft Excel without hyperlinks.</span></span>  

```  
=IIF(Parameters!IncludeURLs.Value,"http://adventure-works.com/productcatalog",Nothing)  
```  

##  <a name="report-data"></a><a name="ReportData"></a><span data-ttu-id="5e830-309">Dati del report</span><span class="sxs-lookup"><span data-stu-id="5e830-309">Report Data</span></span>  
<span data-ttu-id="5e830-310">È possibile utilizzare le espressioni per modificare i dati utilizzati nei report.</span><span class="sxs-lookup"><span data-stu-id="5e830-310">Expressions can be used to manipulate the data that is used in the report.</span></span> <span data-ttu-id="5e830-311">È possibile fare riferimento a parametri e ad altre informazioni dei report,</span><span class="sxs-lookup"><span data-stu-id="5e830-311">You can refer to parameters and other report information.</span></span> <span data-ttu-id="5e830-312">nonché modificare la query utilizzata per recuperare i dati per il report.</span><span class="sxs-lookup"><span data-stu-id="5e830-312">You can even change the query that is used to retrieve data for the report.</span></span>  

###  <a name="parameters"></a><a name="Parameters"></a> <span data-ttu-id="5e830-313">Parametri</span><span class="sxs-lookup"><span data-stu-id="5e830-313">Parameters</span></span>  
<span data-ttu-id="5e830-314">È possibile utilizzare espressioni in un parametro per modificare il valore predefinito del parametro.</span><span class="sxs-lookup"><span data-stu-id="5e830-314">You can use expressions in a parameter to vary the default value for the parameter.</span></span> <span data-ttu-id="5e830-315">Ad esempio, è possibile utilizzare un parametro per filtrare i dati relativi a un utente specifico sulla base dell'ID utente utilizzato per eseguire il report.</span><span class="sxs-lookup"><span data-stu-id="5e830-315">For example, you can use a parameter to filter data to a particular user based on the user ID that is used to run the report.</span></span>  

-   <span data-ttu-id="5e830-316">L'espressione seguente, se utilizzata come valore predefinito di un parametro, recupera l'ID utente della persona che esegue il report:</span><span class="sxs-lookup"><span data-stu-id="5e830-316">The following expression, when used as the default value for a parameter, collects the user ID of the person running the report:</span></span>  

```  
=User!UserID  
```  

-   <span data-ttu-id="5e830-317">Per fare riferimento a un parametro incluso in un parametro di query, un'espressione di filtro, una casella di testo o un'altra area del report, utilizzare la raccolta globale `Parameters`.</span><span class="sxs-lookup"><span data-stu-id="5e830-317">To refer to a parameter in a query parameter, filter expression, text box, or other area of the report, use the `Parameters` global collection.</span></span> <span data-ttu-id="5e830-318">In questo esempio si presuppone che il parametro sia denominato *Department*:</span><span class="sxs-lookup"><span data-stu-id="5e830-318">This example assumes that the parameter is named *Department*:</span></span>  

```  
=Parameters!Department.Value  
```  

-   <span data-ttu-id="5e830-319">I parametri possono essere creati in un report ma impostati come nascosti.</span><span class="sxs-lookup"><span data-stu-id="5e830-319">Parameters can be created in a report but set to hidden.</span></span> <span data-ttu-id="5e830-320">Quando il report viene eseguito nel server di report, il parametro non viene visualizzato sulla barra degli strumenti e il lettore del report non può modificare il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="5e830-320">When the report runs on the report server, the parameter does not appear in the toolbar and the report reader cannot change the default value.</span></span> <span data-ttu-id="5e830-321">È possibile utilizzare un parametro nascosto impostato su un valore predefinito come costante personalizzata.</span><span class="sxs-lookup"><span data-stu-id="5e830-321">You can use a hidden parameter set to a default value as custom constant.</span></span> <span data-ttu-id="5e830-322">È possibile utilizzare questo valore in qualsiasi espressione, anche in un'espressione di campo.</span><span class="sxs-lookup"><span data-stu-id="5e830-322">You can use this value in any expression, including a field expression.</span></span> <span data-ttu-id="5e830-323">L'espressione seguente identifica il campo specificato dal valore del parametro predefinito per il parametro denominato *ParameterField*:</span><span class="sxs-lookup"><span data-stu-id="5e830-323">The following expression identifies the field specified by the default parameter value for the parameter named *ParameterField*:</span></span>  

```  
=Fields(Parameters!ParameterField.Value).Value  
```  

## <a name="custom-code"></a><a name="CustomCode"></a><span data-ttu-id="5e830-324">Codice personalizzato</span><span class="sxs-lookup"><span data-stu-id="5e830-324">Custom Code</span></span>

<span data-ttu-id="5e830-325">È possibile utilizzare codice personalizzato in un report.</span><span class="sxs-lookup"><span data-stu-id="5e830-325">You can use custom code in a report.</span></span> <span data-ttu-id="5e830-326">Il codice personalizzato può essere incorporato in un report o archiviato in un assembly personalizzato utilizzato nel report.</span><span class="sxs-lookup"><span data-stu-id="5e830-326">Custom code is either embedded in a report or stored in a custom assembly which is used in the report.</span></span> <span data-ttu-id="5e830-327">Per altre informazioni sul codice personalizzato, vedere [Riferimenti a codice personalizzato e ad assembly in espressioni in Progettazione report &#40;SSRS&#41;](custom-code-and-assembly-references-in-expressions-in-report-designer-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="5e830-327">For more information about custom code, see [Custom Code and Assembly References in Expressions in Report Designer &#40;SSRS&#41;](custom-code-and-assembly-references-in-expressions-in-report-designer-ssrs.md).</span></span>  

### <a name="using-group-variables-for-custom-aggregation"></a><span data-ttu-id="5e830-328">Utilizzo delle variabili di gruppo per l'aggregazione personalizzata</span><span class="sxs-lookup"><span data-stu-id="5e830-328">Using Group Variables for Custom Aggregation</span></span>

<span data-ttu-id="5e830-329">È possibile inizializzare il valore di una variabile di gruppo locale all'interno di un particolare ambito del gruppo e quindi includere un riferimento a tale variabile nelle espressioni.</span><span class="sxs-lookup"><span data-stu-id="5e830-329">You can initialize the value for a group variable that is local to a particular group scope and then include a reference to that variable in expressions.</span></span> <span data-ttu-id="5e830-330">Una delle modalità di utilizzo di una variabile di gruppo con codice personalizzato consiste nell'implementare un'aggregazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="5e830-330">One of the ways that you can use a group variable with custom code is to implement a custom aggregate.</span></span> <span data-ttu-id="5e830-331">Per ulteriori informazioni, vedere [Using Group Variables in Reporting Services 2008 for Custom Aggregation](https://go.microsoft.com/fwlink/?LinkId=128714).</span><span class="sxs-lookup"><span data-stu-id="5e830-331">For more information, see [Using Group Variables in Reporting Services 2008 for Custom Aggregation](https://go.microsoft.com/fwlink/?LinkId=128714).</span></span>  

<span data-ttu-id="5e830-332">Per altre informazioni sulle variabili, vedere [Riferimenti a raccolte di variabili di report e di gruppo &#40;Generatore report e SSRS&#41;](built-in-collections-report-and-group-variables-references-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="5e830-332">For more information about variables, see [Report and Group Variables Collections References &#40;Report Builder and SSRS&#41;](built-in-collections-report-and-group-variables-references-report-builder.md).</span></span>  

## <a name="suppressing-null-or-zero-values-at-run-time"></a><span data-ttu-id="5e830-333">Eliminazione di valori Null o zero in fase di esecuzione</span><span class="sxs-lookup"><span data-stu-id="5e830-333">Suppressing Null or Zero Values at Run Time</span></span>

<span data-ttu-id="5e830-334">Alcuni valori di un'espressione possono restituire un valore Null o non definito in fase di elaborazione del report.</span><span class="sxs-lookup"><span data-stu-id="5e830-334">Some values in an expression can evaluate to null or undefined at report processing time.</span></span> <span data-ttu-id="5e830-335">In questo modo possono verificarsi errori di run-time che generano la visualizzazione di **#Errore** nella casella di testo anziché dell'espressione valutata.</span><span class="sxs-lookup"><span data-stu-id="5e830-335">This can create run-time errors that result in **#Error** displaying in the text box instead of the evaluated expression.</span></span> <span data-ttu-id="5e830-336">Questo comportamento influisce in modo particolare sulla funzione `IIF` in quanto, a differenza di un'istruzione If-Then-Else, ogni parte dell'istruzione `IIF` (incluse le chiamate a funzioni) viene valutata prima di essere passata alla routine che verifica se il risultato è `true` o `false`.</span><span class="sxs-lookup"><span data-stu-id="5e830-336">The `IIF` function is particularly sensitive to this behavior because, unlike an If-Then-Else statement, each part of the `IIF` statement is evaluated (including function calls) before being passed to the routine that tests for `true` or `false`.</span></span> <span data-ttu-id="5e830-337">L'istruzione `=IIF(Fields!Sales.Value is NOTHING, 0, Fields!Sales.Value)` genera **#Errore** nel report visualizzabile se `Fields!Sales.Value` è NOTHING.</span><span class="sxs-lookup"><span data-stu-id="5e830-337">The statement `=IIF(Fields!Sales.Value is NOTHING, 0, Fields!Sales.Value)` generates **#Error** in the rendered report if `Fields!Sales.Value` is NOTHING.</span></span>  

<span data-ttu-id="5e830-338">Per evitare questa condizione, utilizzare una delle strategie seguenti:</span><span class="sxs-lookup"><span data-stu-id="5e830-338">To avoid this condition, use one of the following strategies:</span></span>  

-   <span data-ttu-id="5e830-339">Impostare il numeratore su 0 e il denominatore su 1 se il valore per il campo B è 0 o non definito; in caso contrario, impostare il numeratore sul valore per il campo A e il denominatore sul valore per il campo B.</span><span class="sxs-lookup"><span data-stu-id="5e830-339">Set the numerator to 0 and the denominator to 1 if the value for field B is 0 or undefined; otherwise, set the numerator to the value for field A and the denominator to the value for field B.</span></span>  

```  
=IIF(Field!B.Value=0, 0, Field!A.Value / IIF(Field!B.Value =0, 1, Field!B.Value))  
```  

-   <span data-ttu-id="5e830-340">Utilizzare una funzione di codice personalizzata per restituire il valore per l'espressione.</span><span class="sxs-lookup"><span data-stu-id="5e830-340">Use a custom code function to return the value for the expression.</span></span> <span data-ttu-id="5e830-341">Nell'esempio seguente viene restituita la differenza in percentuale tra un valore corrente e uno precedente.</span><span class="sxs-lookup"><span data-stu-id="5e830-341">The following example returns the percentage difference between a current value and a previous value.</span></span> <span data-ttu-id="5e830-342">Questa funzione può essere utilizzata per calcolare la differenza tra due valori successivi e consente di gestire il caso limite del primo confronto (quando non è disponibile alcun valore precedente) e i casi in cui il valore precedente o il valore corrente sia `null` (`Nothing` in [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="5e830-342">This can be used to calculate the difference between any two successive values and it handles the edge case of the first comparison (when there is no previous value) and cases whether either the previous value or the current value is `null` (`Nothing` in [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]).</span></span>  

```  
Public Function GetDeltaPercentage(ByVal PreviousValue, ByVal CurrentValue) As Object  
     If IsNothing(PreviousValue) OR IsNothing(CurrentValue) Then  
          Return Nothing  
     Else if PreviousValue = 0 OR CurrentValue = 0 Then  
          Return Nothing  
     Else
          Return (CurrentValue - PreviousValue) / CurrentValue  
     End If  
End Function  
```  

<span data-ttu-id="5e830-343">Nell'espressione seguente viene mostrato come chiamare questo codice personalizzato da una casella di testo, per il contenitore "ColumnGroupByYear" (area dati o gruppo).</span><span class="sxs-lookup"><span data-stu-id="5e830-343">The following expression shows how to call this custom code from a text box, for the "ColumnGroupByYear" container (group or data region).</span></span>  

```  
=Code.GetDeltaPercentage(Previous(Sum(Fields!Sales.Value),"ColumnGroupByYear"), Sum(Fields!Sales.Value))  
```  

<span data-ttu-id="5e830-344">In questo modo si evitano eccezioni in fase di esecuzione</span><span class="sxs-lookup"><span data-stu-id="5e830-344">This helps to avoid run-time exceptions.</span></span> <span data-ttu-id="5e830-345">ed è ora possibile utilizzare un'espressione come `=IIF(Me.Value < 0, "red", "black")` nella proprietà `Color` della casella di testo a seconda se i valori sono maggiori o minori di 0.</span><span class="sxs-lookup"><span data-stu-id="5e830-345">You can now use an expression like `=IIF(Me.Value < 0, "red", "black")` in the `Color` property of the text box to conditionally the display text based on whether the values are greater than or less than 0.</span></span>  

## <a name="see-also"></a><span data-ttu-id="5e830-346">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5e830-346">See Also</span></span>

- [<span data-ttu-id="5e830-347">Esempi di equazioni di filtro &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="5e830-347">Filter Equation Examples &#40;Report Builder and SSRS&#41;</span></span>](filter-equation-examples-report-builder-and-ssrs.md)
- [<span data-ttu-id="5e830-348">Esempi di espressioni di raggruppamento &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="5e830-348">Group Expression Examples &#40;Report Builder and SSRS&#41;</span></span>](expression-examples-report-builder-and-ssrs.md)
- [<span data-ttu-id="5e830-349">Utilizzo delle espressioni nei report &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="5e830-349">Expression Uses in Reports &#40;Report Builder and SSRS&#41;</span></span>](expression-uses-in-reports-report-builder-and-ssrs.md)
- [<span data-ttu-id="5e830-350">Espressioni &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="5e830-350">Expressions &#40;Report Builder and SSRS&#41;</span></span>](expressions-report-builder-and-ssrs.md)
- [<span data-ttu-id="5e830-351">Filtri di uso comune &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="5e830-351">Commonly Used Filters &#40;Report Builder and SSRS&#41;</span></span>](commonly-used-filters-report-builder-and-ssrs.md)