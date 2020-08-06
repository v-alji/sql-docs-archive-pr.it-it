---
title: Trasformazione Colonna derivata | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.derivedcolumntrans.f1
helpviewer_keywords:
- multiple derived columns
- expressions [Integration Services], derived columns
- derived columns
- columns [Integration Services], derivations
- Derived Column transformation
ms.assetid: 8eba755e-8e48-4233-bd1e-09a46bf2692f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7bbdc46f2e67b1b859fcfa446c584373cfbeca0d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624272"
---
# <a name="derived-column-transformation"></a><span data-ttu-id="53ab7-102">Trasformazione Colonna derivata</span><span class="sxs-lookup"><span data-stu-id="53ab7-102">Derived Column Transformation</span></span>
  <span data-ttu-id="53ab7-103">La trasformazione Colonna derivata consente di creare nuovi valori di colonna tramite l'applicazione di espressioni alle colonne di input della trasformazione.</span><span class="sxs-lookup"><span data-stu-id="53ab7-103">The Derived Column transformation creates new column values by applying expressions to transformation input columns.</span></span> <span data-ttu-id="53ab7-104">Un'espressione può contenere qualsiasi combinazione di variabili, funzioni, operatori e colonne dell'input della trasformazione.</span><span class="sxs-lookup"><span data-stu-id="53ab7-104">An expression can contain any combination of variables, functions, operators, and columns from the transformation input.</span></span> <span data-ttu-id="53ab7-105">Il risultato può essere aggiunto come nuova colonna o inserito in una colonna esistente come valore di sostituzione.</span><span class="sxs-lookup"><span data-stu-id="53ab7-105">The result can be added as a new column or inserted into an existing column as a replacement value.</span></span> <span data-ttu-id="53ab7-106">La trasformazione Colonna derivata può definire più colonne derivate e qualsiasi variabile o colonna di input può comparire in più espressioni.</span><span class="sxs-lookup"><span data-stu-id="53ab7-106">The Derived Column transformation can define multiple derived columns, and any variable or input columns can appear in multiple expressions.</span></span>  
  
 <span data-ttu-id="53ab7-107">È possibile utilizzare questa trasformazione per eseguire le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="53ab7-107">You can use this transformation to perform the following tasks:</span></span>  
  
-   <span data-ttu-id="53ab7-108">Concatenare i dati di colonne diverse in una colonna derivata.</span><span class="sxs-lookup"><span data-stu-id="53ab7-108">Concatenate data from different columns into a derived column.</span></span> <span data-ttu-id="53ab7-109">È ad esempio possibile combinare i valori delle colonne **FirstName** e **LastName** in una singola colonna derivata di nome **FullName**, usando l'espressione `FirstName + " " + LastName`.</span><span class="sxs-lookup"><span data-stu-id="53ab7-109">For example, you can combine values from the **FirstName** and **LastName** columns into a single derived column named **FullName**, by using the expression `FirstName + " " + LastName`.</span></span>  
  
-   <span data-ttu-id="53ab7-110">Estrarre caratteri da dati stringa, tramite funzioni quali SUBSTRING, e quindi archiviare il risultato in una colonna derivata.</span><span class="sxs-lookup"><span data-stu-id="53ab7-110">Extract characters from string data by using functions such as SUBSTRING, and then store the result in a derived column.</span></span> <span data-ttu-id="53ab7-111">È ad esempio possibile estrarre l'iniziale del nome di una persona dalla colonna **FirstName** usando l'espressione `SUBSTRING(FirstName,1,1)`.</span><span class="sxs-lookup"><span data-stu-id="53ab7-111">For example, you can extract a person's initial from the **FirstName** column, by using the expression `SUBSTRING(FirstName,1,1)`.</span></span>  
  
-   <span data-ttu-id="53ab7-112">Applicare funzioni matematiche a dati numerici e archiviare i risultati in una colonna derivata.</span><span class="sxs-lookup"><span data-stu-id="53ab7-112">Apply mathematical functions to numeric data and store the result in a derived column.</span></span> <span data-ttu-id="53ab7-113">È ad esempio possibile modificare la lunghezza e la precisione della colonna numerica **SalesTax**impostandola su un numero con due cifre decimali, usando l'espressione `ROUND(SalesTax, 2)`.</span><span class="sxs-lookup"><span data-stu-id="53ab7-113">For example, you can change the length and precision of a numeric column, **SalesTax**, to a number with two decimal places, by using the expression `ROUND(SalesTax, 2)`.</span></span>  
  
-   <span data-ttu-id="53ab7-114">Creare espressioni che confrontano colonne di input e variabili.</span><span class="sxs-lookup"><span data-stu-id="53ab7-114">Create expressions that compare input columns and variables.</span></span> <span data-ttu-id="53ab7-115">È ad esempio possibile usare l'espressione **per confrontare la variabile** Version **con i dati nella colonna**ProductVersion **e, a seconda del risultato del confronto, usare il valore di** Version **o**ProductVersion `ProductVersion == @Version? ProductVersion : @Version`.</span><span class="sxs-lookup"><span data-stu-id="53ab7-115">For example, you can compare the variable **Version** against the data in the column **ProductVersion**, and depending on the comparison result, use the value of either **Version** or **ProductVersion**, by using the expression `ProductVersion == @Version? ProductVersion : @Version`.</span></span>  
  
-   <span data-ttu-id="53ab7-116">Estrarre parti di un valore datetime.</span><span class="sxs-lookup"><span data-stu-id="53ab7-116">Extract parts of a datetime value.</span></span> <span data-ttu-id="53ab7-117">È ad esempio possibile usare le funzioni GETDATE e DATEPART per estrarre l'anno corrente usando l'espressione `DATEPART("year",GETDATE())`.</span><span class="sxs-lookup"><span data-stu-id="53ab7-117">For example, you can use the GETDATE and DATEPART functions to extract the current year, by using the expression `DATEPART("year",GETDATE())`.</span></span>  
  
-   <span data-ttu-id="53ab7-118">Consente di convertire le stringhe di data in un formato specifico usando un'espressione.</span><span class="sxs-lookup"><span data-stu-id="53ab7-118">Convert date strings to a specific format using an expression.</span></span>  
  
## <a name="configuration-of-the-derived-column-transformation"></a><span data-ttu-id="53ab7-119">Configurazione della trasformazione Colonna derivata</span><span class="sxs-lookup"><span data-stu-id="53ab7-119">Configuration of the Derived Column Transformation</span></span>  
 <span data-ttu-id="53ab7-120">Per configurare la trasformazione Colonna derivata, procedere nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="53ab7-120">You can configure the Derived column transformation in the following ways:</span></span>  
  
-   <span data-ttu-id="53ab7-121">Specificare un'espressione per ogni colonna di input o nuova colonna da modificare.</span><span class="sxs-lookup"><span data-stu-id="53ab7-121">Provide an expression for each input column or new column that will be changed.</span></span> <span data-ttu-id="53ab7-122">Per altre informazioni, vedere [Espressioni di Integration Services &#40;SSIS&#41;](../../expressions/integration-services-ssis-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="53ab7-122">For more information, see [Integration Services &#40;SSIS&#41; Expressions](../../expressions/integration-services-ssis-expressions.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="53ab7-123">Se un'espressione fa riferimento a una colonna di input sovrascritta dalla trasformazione Colonna derivata, l'espressione utilizzerà il valore originale della colonna anziché il valore derivato.</span><span class="sxs-lookup"><span data-stu-id="53ab7-123">If an expression references an input column that is overwritten by the Derived Column transformation, the expression uses the original value of the column, not the derived value.</span></span>  
  
-   <span data-ttu-id="53ab7-124">Se si aggiungono i risultati a nuove colonne e il tipo di dati è `string`, specificare una tabella codici.</span><span class="sxs-lookup"><span data-stu-id="53ab7-124">If adding results to new columns and the data type is `string`, specify a code page.</span></span> <span data-ttu-id="53ab7-125">Per altre informazioni, vedere [Comparing String Data](../comparing-string-data.md).</span><span class="sxs-lookup"><span data-stu-id="53ab7-125">For more information, see [Comparing String Data](../comparing-string-data.md).</span></span>  
  
 <span data-ttu-id="53ab7-126">La trasformazione Colonna derivata condizionale include la proprietà personalizzata FriendlyExpression,</span><span class="sxs-lookup"><span data-stu-id="53ab7-126">The Derived Column transformation includes the FriendlyExpression custom property.</span></span> <span data-ttu-id="53ab7-127">che può essere aggiornata da un'espressione di proprietà al caricamento del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="53ab7-127">This property can be updated by a property expression when the package is loaded.</span></span> <span data-ttu-id="53ab7-128">Per altre informazioni, vedere [Usare le espressioni di proprietà nei pacchetti](../../expressions/use-property-expressions-in-packages.md)e [Proprietà personalizzate delle trasformazioni](transformation-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="53ab7-128">For more information, see [Use Property Expressions in Packages](../../expressions/use-property-expressions-in-packages.md), and [Transformation Custom Properties](transformation-custom-properties.md).</span></span>  
  
 <span data-ttu-id="53ab7-129">Questa trasformazione include un input, un output regolare e un output degli errori.</span><span class="sxs-lookup"><span data-stu-id="53ab7-129">This transformation has one input, one regular output, and one error output.</span></span>  
  
 <span data-ttu-id="53ab7-130">È possibile impostare le proprietà tramite Progettazione [!INCLUDE[ssIS](../../../includes/ssis-md.md)] o a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="53ab7-130">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="53ab7-131">Per altre informazioni sulle proprietà che è possibile impostare nella finestra di dialogo **Editor trasformazione Colonna derivata** , vedere [Editor trasformazione Colonna derivata](../../derived-column-transformation-editor.md).</span><span class="sxs-lookup"><span data-stu-id="53ab7-131">For more information about the properties that you can set in the **Derived Column Transformation Editor** dialog box, see [Derived Column Transformation Editor](../../derived-column-transformation-editor.md).</span></span>  
  
 <span data-ttu-id="53ab7-132">Nella finestra di dialogo **Editor avanzato** sono disponibili le proprietà che è possibile impostare a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="53ab7-132">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="53ab7-133">Per ulteriori informazioni sulle proprietà che è possibile impostare nella finestra di dialogo **Editor avanzato** o a livello di codice, fare clic su uno degli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="53ab7-133">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="53ab7-134">Proprietà comuni</span><span class="sxs-lookup"><span data-stu-id="53ab7-134">Common Properties</span></span>](../../common-properties.md)  
  
-   [<span data-ttu-id="53ab7-135">Proprietà personalizzate delle trasformazioni</span><span class="sxs-lookup"><span data-stu-id="53ab7-135">Transformation Custom Properties</span></span>](transformation-custom-properties.md)  
  
 <span data-ttu-id="53ab7-136">Per ulteriori informazioni sulle procedure per l'impostazione delle proprietà, fare clic su uno degli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="53ab7-136">For more information about how to set properties, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="53ab7-137">Impostazione delle proprietà di un componente del flusso di dati</span><span class="sxs-lookup"><span data-stu-id="53ab7-137">Set the Properties of a Data Flow Component</span></span>](../set-the-properties-of-a-data-flow-component.md)  
  
## <a name="related-tasks"></a><span data-ttu-id="53ab7-138">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="53ab7-138">Related Tasks</span></span>  
  
-   [<span data-ttu-id="53ab7-139">Derivazione di valori di colonna tramite la trasformazione Colonna derivata</span><span class="sxs-lookup"><span data-stu-id="53ab7-139">Derive Column Values by Using the Derived Column Transformation</span></span>](derived-column-transformation.md)  
  
## <a name="related-content"></a><span data-ttu-id="53ab7-140">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="53ab7-140">Related Content</span></span>  
 <span data-ttu-id="53ab7-141">Articolo tecnico relativo agli [esempi di espressioni SSIS](https://go.microsoft.com/fwlink/?LinkId=220761)nel sito Web social.technet.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="53ab7-141">Technical article, [SSIS Expression Examples](https://go.microsoft.com/fwlink/?LinkId=220761), on social.technet.microsoft.com</span></span>  
  
 <span data-ttu-id="53ab7-142">Blog, [come suddividere i dati delle colonne con SSIS](https://microsoft-ssis.blogspot.com/2012/10/split-multi-value-column-into-multiple.html).</span><span class="sxs-lookup"><span data-stu-id="53ab7-142">Blog, [How to Split Column Data using SSIS](https://microsoft-ssis.blogspot.com/2012/10/split-multi-value-column-into-multiple.html).</span></span>  
  
  
