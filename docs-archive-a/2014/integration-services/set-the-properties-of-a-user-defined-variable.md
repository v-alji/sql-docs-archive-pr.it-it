---
title: Impostare le proprietà di una variabile definita dall'utente | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- modifying variables
- variables [Integration Services], properties
ms.assetid: f98ddbec-f668-4dba-a768-44ac3ae0536f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: bf53be469e3d377f7efb379f78e85e31b26767b2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726056"
---
# <a name="set-the-properties-of-a-user-defined-variable"></a><span data-ttu-id="6f86a-102">Impostazione delle proprietà di una variabile definita dall'utente</span><span class="sxs-lookup"><span data-stu-id="6f86a-102">Set the Properties of a User-Defined Variable</span></span>
  <span data-ttu-id="6f86a-103">Per impostare le proprietà di una variabile definita dall'utente in [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]è possibile utilizzare una delle funzionalità seguenti:</span><span class="sxs-lookup"><span data-stu-id="6f86a-103">To set the properties of a user-defined variable in [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], you can use one of the following features:</span></span>  
  
-   <span data-ttu-id="6f86a-104">Finestra Variabili.</span><span class="sxs-lookup"><span data-stu-id="6f86a-104">Variables window.</span></span>  
  
-   <span data-ttu-id="6f86a-105">Finestra Proprietà.</span><span class="sxs-lookup"><span data-stu-id="6f86a-105">Properties window.</span></span> <span data-ttu-id="6f86a-106">La finestra **Proprietà** elenca le proprietà per la configurazione delle variabili non disponibili nella finestra **Variabili** : Description, EvaluateAsExpression, Expression, ReadOnly, ValueType e IncludeInDebugDump.</span><span class="sxs-lookup"><span data-stu-id="6f86a-106">The **Properties** window lists properties for configuring variables that are not available in the **Variables** window: Description, EvaluateAsExpression, Expression, ReadOnly, ValueType, and IncludeInDebugDump.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="6f86a-107">include anche un set di variabili di sistema le cui proprietà non possono essere aggiornate, ad eccezione della proprietà RaiseChangedEvent.</span><span class="sxs-lookup"><span data-stu-id="6f86a-107">also provides a set of system variables whose properties cannot be updated, with the exception of the RaiseChangedEvent property.</span></span>  
  
 <span data-ttu-id="6f86a-108">**Impostazione di espressioni nelle variabili**</span><span class="sxs-lookup"><span data-stu-id="6f86a-108">**Setting Expressions on Variables**</span></span>  
  
 <span data-ttu-id="6f86a-109">Quando si usa la finestra **Proprietà** per impostare le espressioni in una variabile definita dall'utente:</span><span class="sxs-lookup"><span data-stu-id="6f86a-109">When you use the **Properties** window to set expressions on a user-defined variable:</span></span>  
  
-   <span data-ttu-id="6f86a-110">Il valore di una variabile può essere impostato tramite la proprietà Value o Expression.</span><span class="sxs-lookup"><span data-stu-id="6f86a-110">The value of a variable can be set by the Value or the Expression property.</span></span> <span data-ttu-id="6f86a-111">Per impostazione predefinita, la proprietà EvaluateAsExpression è impostata su `False` e il valore della variabile viene impostato dalla proprietà Value.</span><span class="sxs-lookup"><span data-stu-id="6f86a-111">By default, the EvaluateAsExpression property is set to `False` and the value of the variable is set by the Value property.</span></span> <span data-ttu-id="6f86a-112">Per usare un'espressione per impostare il valore, è innanzitutto necessario impostare EvaluateAsExpression su `True` e quindi specificare un'espressione nella proprietà Expression.</span><span class="sxs-lookup"><span data-stu-id="6f86a-112">To use an expression to set the value, you must first set EvaluateAsExpression to `True`, and then provide an expression in the Expression property.</span></span> <span data-ttu-id="6f86a-113">La proprietà Value viene impostata automaticamente sul risultato restituito dall'espressione.</span><span class="sxs-lookup"><span data-stu-id="6f86a-113">The Value property is automatically set to the evaluation result of the expression.</span></span>  
  
-   <span data-ttu-id="6f86a-114">La proprietà ValueType contiene il tipo di dati del valore della proprietà Value.</span><span class="sxs-lookup"><span data-stu-id="6f86a-114">The ValueType property contains the data type of the value in the Value property.</span></span> <span data-ttu-id="6f86a-115">Quando la proprietà Value viene impostata tramite un'espressione, la proprietà ValueType viene automaticamente aggiornata a un tipo di dati compatibile con il risultato restituito dall'espressione.</span><span class="sxs-lookup"><span data-stu-id="6f86a-115">When Value is set by an expression, ValueType is automatically updated to a data type that is compatible with the evaluation result of the expression.</span></span> <span data-ttu-id="6f86a-116">Se, ad esempio, il valore contiene 0 e la proprietà ValueType contiene **Int32** e si imposta Expression su GETDATE (), il valore contiene la data e l'ora correnti e ValueType è impostato su `DateTime` .</span><span class="sxs-lookup"><span data-stu-id="6f86a-116">For example, if Value contains 0 and ValueType property contains **Int32** and you then set Expression to GETDATE(), Value contains the current date and time and ValueType is set to `DateTime`.</span></span>  
  
-   <span data-ttu-id="6f86a-117">Tramite la finestra **Proprietà** della variabile è possibile accedere alla finestra di dialogo **Generatore di espressioni** ,</span><span class="sxs-lookup"><span data-stu-id="6f86a-117">The **Properties** window for the variable provides access to the **Expression Builder** dialog box.</span></span> <span data-ttu-id="6f86a-118">che consente di compilare, convalidare e valutare le espressioni.</span><span class="sxs-lookup"><span data-stu-id="6f86a-118">You can use this tool to build, validate, and evaluate expressions.</span></span> <span data-ttu-id="6f86a-119">Per altre informazioni, vedere [Generatore di espressioni](expressions/expression-builder.md) e [Espressioni di Integration Services &#40;SSIS&#41;](expressions/integration-services-ssis-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="6f86a-119">For more information, see [Expression Builder](expressions/expression-builder.md) and [Integration Services &#40;SSIS&#41; Expressions](expressions/integration-services-ssis-expressions.md).</span></span>  
  
 <span data-ttu-id="6f86a-120">Quando si usa la finestra **Variabili** per impostare le espressioni in una variabile definita dall'utente:</span><span class="sxs-lookup"><span data-stu-id="6f86a-120">When you use the **Variables** window to set expressions on a user-defined variable:</span></span>  
  
-   <span data-ttu-id="6f86a-121">Per utilizzare un'espressione per impostare il valore della variabile, verificare innanzitutto che il tipo di dati della variabile sia compatibile con il risultato della valutazione dell'espressione e quindi specificare un'espressione nella `Expression` colonna della finestra **variabili** .</span><span class="sxs-lookup"><span data-stu-id="6f86a-121">To use an expression to set the variable value, first confirm that the variable data type is compatible with the evaluation result of the expression and then provide an expression in the `Expression` column of the **Variables** window.</span></span> <span data-ttu-id="6f86a-122">La proprietà EvaluateAsExpression nella finestra **Proprietà** viene automaticamente impostata su `True` .</span><span class="sxs-lookup"><span data-stu-id="6f86a-122">The EvaluateAsExpression property in the **Properties** window is automatically set to `True`.</span></span>  
  
-   <span data-ttu-id="6f86a-123">Quando si assegna un'espressione a una variabile, accanto a quest'ultima viene visualizzato un marcatore icona speciale.</span><span class="sxs-lookup"><span data-stu-id="6f86a-123">When you assign an expression to a variable, a special icon marker displays next to the variable.</span></span> <span data-ttu-id="6f86a-124">Tale marcatore icona speciale viene visualizzato anche accanto alle gestioni connessioni e alle attività in cui sono impostate espressioni.</span><span class="sxs-lookup"><span data-stu-id="6f86a-124">This special icon marker also displays next to connection managers and tasks that have expressions set on them.</span></span>  
  
-   <span data-ttu-id="6f86a-125">Tramite la finestra **Variabili** della variabile è possibile accedere alla finestra di dialogo **Generatore di espressioni** ,</span><span class="sxs-lookup"><span data-stu-id="6f86a-125">The **Variables** window for the variable provides access to the **Expression Builder** dialog box.</span></span> <span data-ttu-id="6f86a-126">che consente di compilare, convalidare e valutare le espressioni.</span><span class="sxs-lookup"><span data-stu-id="6f86a-126">You can use this tool to build, validate, and evaluate expressions.</span></span> <span data-ttu-id="6f86a-127">Per altre informazioni, vedere [Generatore di espressioni](expressions/expression-builder.md) e [Espressioni di Integration Services &#40;SSIS&#41;](expressions/integration-services-ssis-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="6f86a-127">For more information, see [Expression Builder](expressions/expression-builder.md) and [Integration Services &#40;SSIS&#41; Expressions](expressions/integration-services-ssis-expressions.md).</span></span>  
  
 <span data-ttu-id="6f86a-128">Nella finestra **variabili** e **Proprietà** , se si assegna un'espressione alla variabile e `EvaluateAsExpression` viene impostato su `True` , non è possibile modificare il tipo di dati della variabile.</span><span class="sxs-lookup"><span data-stu-id="6f86a-128">In both the **Variables** and **Properties** window, if you assign an expression to the variable, and `EvaluateAsExpression` is set to `True`, you cannot change the variable data type.</span></span>  
  
 <span data-ttu-id="6f86a-129">**Impostazione delle proprietà Namespace e Name**</span><span class="sxs-lookup"><span data-stu-id="6f86a-129">**Setting the Namespace and Name Properties**</span></span>  
  
 <span data-ttu-id="6f86a-130">I valori delle proprietà `Name` e `Namespace` devono iniziare con una delle lettere dell'alfabeto definite dallo standard Unicode 2.0 oppure con un carattere di sottolineatura (_).</span><span class="sxs-lookup"><span data-stu-id="6f86a-130">The values of the `Name` and `Namespace` properties must begin with an alphabetic character letter as defined by the Unicode Standard 2.0, or an underscore (_).</span></span> <span data-ttu-id="6f86a-131">I caratteri successivi possono includere lettere o numeri, come definito dallo standard Unicode 2.0, o il carattere di sottolineatura (\_).</span><span class="sxs-lookup"><span data-stu-id="6f86a-131">Subsequent characters can be letters or numbers as defined in the Unicode Standard 2.0, or the underscore (\_).</span></span>  
  
## <a name="using-the-variables-window-to-set-properties"></a><span data-ttu-id="6f86a-132">Utilizzo della finestra Variabili per impostare le proprietà</span><span class="sxs-lookup"><span data-stu-id="6f86a-132">Using the Variables Window to Set Properties</span></span>  
  
#### <a name="to-set-the-properties-of-a-variable-by-using-the-variables-window"></a><span data-ttu-id="6f86a-133">Per impostare le proprietà di una variabile utilizzando la finestra Variabili</span><span class="sxs-lookup"><span data-stu-id="6f86a-133">To set the properties of a variable by using the Variables window</span></span>  
  
1.  <span data-ttu-id="6f86a-134">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]aprire il progetto di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] che contiene il pacchetto desiderato.</span><span class="sxs-lookup"><span data-stu-id="6f86a-134">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="6f86a-135">In Esplora soluzioni fare clic con il pulsante destro del mouse sul pacchetto in modo da aprirlo.</span><span class="sxs-lookup"><span data-stu-id="6f86a-135">In Solution Explorer, right-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="6f86a-136">Scegliere **Variabili** dal menu **SSIS**.</span><span class="sxs-lookup"><span data-stu-id="6f86a-136">On the **SSIS** menu, click **Variables**.</span></span>  
  
     <span data-ttu-id="6f86a-137">Facoltativamente, è possibile visualizzare la finestra **Variabili** eseguendo il mapping del comando View.Variables a una combinazione di tasti scelta dall'utente nella pagina **Tastiera** della finestra di dialogo **Opzioni** .</span><span class="sxs-lookup"><span data-stu-id="6f86a-137">You can optionally display the **Variables** window by mapping the View.Variables command to a key combination of your choosing on the **Keyboard** page of the **Options** dialog box.</span></span>  
  
4.  <span data-ttu-id="6f86a-138">Facoltativamente, nella finestra **Variabili** fare clic su **Opzioni griglia**, quindi selezionare le colonne che si vuole visualizzare nella finestra **Variabili** e selezionare i filtri da applicare all'elenco di variabili.</span><span class="sxs-lookup"><span data-stu-id="6f86a-138">Optionally, in the **Variables** window click **Grid Options**, and then select the columns to appear in the **Variables** window and select the filters to apply to the list of variables.</span></span>  
  
5.  <span data-ttu-id="6f86a-139">Selezionare la variabile nell'elenco, quindi aggiornare i valori in `Name` , tipo di **dati**,, `Value` `Namespace` , **genera evento di modifica**, **Descrizione** e `Expression` colonne.</span><span class="sxs-lookup"><span data-stu-id="6f86a-139">Select the variable in the list, and then update values in the `Name`, **Data Type**, `Value`, `Namespace`, **Raise Change Event**, **Description,** and `Expression` columns.</span></span>  
  
6.  <span data-ttu-id="6f86a-140">Selezionare la variabile nell'elenco e quindi fare clic su **Sposta variabile** per modificarne l'ambito.</span><span class="sxs-lookup"><span data-stu-id="6f86a-140">Select the variable in the list, and then click **Move Variable** to change the scope.</span></span>  
  
7.  <span data-ttu-id="6f86a-141">Per salvare il pacchetto aggiornato, dal menu **File** scegliere **Salva elementi selezionati**.</span><span class="sxs-lookup"><span data-stu-id="6f86a-141">To save the updated package, on the **File** menu, click **Save Selected Items**.</span></span>  
  
## <a name="using-the-properties-window-to-set-properties"></a><span data-ttu-id="6f86a-142">Utilizzo della finestra Proprietà per impostare le proprietà</span><span class="sxs-lookup"><span data-stu-id="6f86a-142">Using the Properties Window to Set Properties</span></span>  
  
#### <a name="to-set-the-properties-of-a-variable-by-using-the-properties-window"></a><span data-ttu-id="6f86a-143">Per impostare le proprietà di una variabile utilizzando la finestra Proprietà</span><span class="sxs-lookup"><span data-stu-id="6f86a-143">To set the properties of a variable by using the Properties window</span></span>  
  
1.  <span data-ttu-id="6f86a-144">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]aprire il progetto di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] che contiene il pacchetto desiderato.</span><span class="sxs-lookup"><span data-stu-id="6f86a-144">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="6f86a-145">In Esplora soluzioni fare clic con il pulsante destro del mouse sul pacchetto in modo da aprirlo.</span><span class="sxs-lookup"><span data-stu-id="6f86a-145">In Solution Explorer, right-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="6f86a-146">Scegliere **Finestra Proprietà** dal menu **Visualizza**.</span><span class="sxs-lookup"><span data-stu-id="6f86a-146">On the **View** menu, click **Properties Window**.</span></span>  
  
4.  <span data-ttu-id="6f86a-147">In Progettazione [!INCLUDE[ssIS](../includes/ssis-md.md)] fare clic sulla scheda **Esplora pacchetti** ed espandere il nodo Pacchetto.</span><span class="sxs-lookup"><span data-stu-id="6f86a-147">In [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, click the **Package Explorer** tab and expand the Package node.</span></span>  
  
5.  <span data-ttu-id="6f86a-148">Per modificare le variabili con ambito pacchetto, espandere il nodo Variabili oppure espandere il nodo Gestori eventi o File eseguibili fino a individuare il nodo Variabili contenente la variabile che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="6f86a-148">To modify variables with package scope, expand the Variables node; otherwise, expand the Event Handlers or Executables nodes until you locate the Variables node that contains the variable that you want to modify.</span></span>  
  
6.  <span data-ttu-id="6f86a-149">Fare clic sulla variabile di cui si desidera modificare le proprietà.</span><span class="sxs-lookup"><span data-stu-id="6f86a-149">Click the variable whose properties you want to modify.</span></span>  
  
7.  <span data-ttu-id="6f86a-150">Nella finestra **Proprietà** aggiornare le proprietà delle variabili in lettura/scrittura.</span><span class="sxs-lookup"><span data-stu-id="6f86a-150">In the **Properties** window, update the read/write variable properties.</span></span> <span data-ttu-id="6f86a-151">Alcune proprietà sono di sola lettura per le variabili definite dall'utente.</span><span class="sxs-lookup"><span data-stu-id="6f86a-151">Some properties are read/read only for user-defined variables.</span></span>  
  
     <span data-ttu-id="6f86a-152">Per altre informazioni sulle proprietà, vedere [Variabili di Integration Services &#40;SSIS&#41;](integration-services-ssis-variables.md).</span><span class="sxs-lookup"><span data-stu-id="6f86a-152">For more information about the properties, see [Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md).</span></span>  
  
8.  <span data-ttu-id="6f86a-153">Per salvare il pacchetto aggiornato, dal menu **File** scegliere **Salva elementi selezionati**.</span><span class="sxs-lookup"><span data-stu-id="6f86a-153">To save the updated package, on the **File** menu, click **Save Selected Items**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f86a-154">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6f86a-154">See Also</span></span>  
 <span data-ttu-id="6f86a-155">[Variabili di Integration Services &#40;SSIS&#41;](integration-services-ssis-variables.md) </span><span class="sxs-lookup"><span data-stu-id="6f86a-155">[Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md) </span></span>  
 <span data-ttu-id="6f86a-156">[Usare variabili nei pacchetti](../../2014/integration-services/use-variables-in-packages.md) </span><span class="sxs-lookup"><span data-stu-id="6f86a-156">[Use Variables in Packages](../../2014/integration-services/use-variables-in-packages.md) </span></span>  
 [<span data-ttu-id="6f86a-157">Aggiungere, eliminare o modificare l'ambito di una variabile definita dall'utente in un pacchetto</span><span class="sxs-lookup"><span data-stu-id="6f86a-157">Add, Delete, Change Scope of User-Defined Variable in a Package</span></span>](../../2014/integration-services/add-delete-change-scope-of-user-defined-variable-in-a-package.md)  
  
  
