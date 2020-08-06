---
title: Finestra Variabili | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.variables.f1
helpviewer_keywords:
- Variables Window dialog box
ms.assetid: f405e5ce-ef69-4c58-8c7d-a3d44dfe9ab0
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ffd6da67386291c14ebf588da9a1cf8f399214b3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635108"
---
# <a name="variables-window"></a><span data-ttu-id="25b58-102">Finestra Variabili</span><span class="sxs-lookup"><span data-stu-id="25b58-102">Variables Window</span></span>
  <span data-ttu-id="25b58-103">Usare la finestra **Variabili** per creare e modificare variabili definite dall'utente e visualizzare quelle di sistema.</span><span class="sxs-lookup"><span data-stu-id="25b58-103">Use the **Variables** window to create and modify user-defined variables and view system variables.</span></span>  
  
 <span data-ttu-id="25b58-104">Per impostazione predefinita la finestra **Variabili** si trova sotto l'area **Gestioni connessioni** in Progettazione SSIS, in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="25b58-104">By default, the **Variables** window is located below the **Connection Managers** area in the SSIS Designer, in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="25b58-105">Se non viene visualizzata la finestra **Variabili**, fare clic su **Variabili** nel menu **SSIS** per visualizzare la finestra.</span><span class="sxs-lookup"><span data-stu-id="25b58-105">If you don't see the **Variables** window, click **Variables** on the **SSIS** menu to display the window.</span></span>  
  
 <span data-ttu-id="25b58-106">Facoltativamente, è possibile visualizzare la finestra **Variabili** eseguendo il mapping del comando View.Variables a una combinazione di tasti scelta dall'utente nella pagina **Tastiera** della finestra di dialogo **Opzioni** .</span><span class="sxs-lookup"><span data-stu-id="25b58-106">You can optionally display the **Variables** window by mapping the View.Variables command to a key combination of your choosing on the **Keyboard** page of the **Options** dialog box.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="25b58-107">I valori delle proprietà `Name` e `Namespace` devono iniziare con una delle lettere dell'alfabeto definite dallo standard Unicode 2.0 oppure con un carattere di sottolineatura (_).</span><span class="sxs-lookup"><span data-stu-id="25b58-107">The values of the `Name` and `Namespace` properties must begin with an alphabetic character letter as defined by the Unicode Standard 2.0, or an underscore (_).</span></span> <span data-ttu-id="25b58-108">I caratteri successivi possono includere lettere o numeri, come definito dallo standard Unicode 2.0, o il carattere di sottolineatura (\_).</span><span class="sxs-lookup"><span data-stu-id="25b58-108">Subsequent characters can be letters or numbers as defined in the Unicode Standard 2.0, or the underscore (\_).</span></span>  
  
## <a name="options"></a><span data-ttu-id="25b58-109">Opzioni</span><span class="sxs-lookup"><span data-stu-id="25b58-109">Options</span></span>  
 <span data-ttu-id="25b58-110">**Aggiungi variabile**</span><span class="sxs-lookup"><span data-stu-id="25b58-110">**Add Variable**</span></span>  
 <span data-ttu-id="25b58-111">Consente di aggiungere una variabile definita dall'utente.</span><span class="sxs-lookup"><span data-stu-id="25b58-111">Add a user-defined variable.</span></span>  
  
 <span data-ttu-id="25b58-112">**Sposta variabile**</span><span class="sxs-lookup"><span data-stu-id="25b58-112">**Move Variable**</span></span>  
 <span data-ttu-id="25b58-113">Fare clic su una variabile nell'elenco e quindi fare clic su **Sposta variabile** per modificare l'ambito della variabile.</span><span class="sxs-lookup"><span data-stu-id="25b58-113">Click a variable in the list, and then click **Move Variable** to change the variable scope.</span></span> <span data-ttu-id="25b58-114">Nella finestra di dialogo **Seleziona nuovo ambito** selezionare il pacchetto oppure un contenitore, un'attività o un gestore eventi del pacchetto per modificare l'ambito della variabile.</span><span class="sxs-lookup"><span data-stu-id="25b58-114">In the **Select New Scope** dialog box, select the package or a container, task, or event handler in the package, to change the variable scope.</span></span>  
  
 <span data-ttu-id="25b58-115">Per altre informazioni sull'ambito delle variabili, vedere [Variabili di Integration Services &#40;SSIS&#41;](integration-services-ssis-variables.md).</span><span class="sxs-lookup"><span data-stu-id="25b58-115">For more information about variable scope, see [Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md).</span></span>  
  
 <span data-ttu-id="25b58-116">**Elimina variabile**</span><span class="sxs-lookup"><span data-stu-id="25b58-116">**Delete Variable**</span></span>  
 <span data-ttu-id="25b58-117">Selezionare una variabile dall'elenco e quindi fare clic su **Elimina variabile**.</span><span class="sxs-lookup"><span data-stu-id="25b58-117">Select a variable from the list, and then click **Delete Variable**.</span></span>  
  
 <span data-ttu-id="25b58-118">**Opzioni griglia**</span><span class="sxs-lookup"><span data-stu-id="25b58-118">**Grid Options**</span></span>  
 <span data-ttu-id="25b58-119">Fare clic su questo pulsante per aprire la finestra di dialogo **Opzioni griglia variabili** , in cui è possibile modificare la selezione delle colonne e applicare i filtri alla finestra **Variabili** .</span><span class="sxs-lookup"><span data-stu-id="25b58-119">Click to open the **Variable Grid Options** dialog box where you can change the column selection and apply filters to the **Variables** window.</span></span> <span data-ttu-id="25b58-120">Per altre informazioni, vedere [Opzioni griglia variabili](../../2014/integration-services/variable-grid-options.md).</span><span class="sxs-lookup"><span data-stu-id="25b58-120">For more information, see [Variable Grid Options](../../2014/integration-services/variable-grid-options.md).</span></span>  
  
 `Name`  
 <span data-ttu-id="25b58-121">Consente di visualizzare il nome della variabile.</span><span class="sxs-lookup"><span data-stu-id="25b58-121">View the variable name.</span></span> <span data-ttu-id="25b58-122">È possibile aggiornare il nome delle variabili definite dall'utente.</span><span class="sxs-lookup"><span data-stu-id="25b58-122">You can update the name for user-defined variables.</span></span>  
  
 <span data-ttu-id="25b58-123">**Ambito**</span><span class="sxs-lookup"><span data-stu-id="25b58-123">**Scope**</span></span>  
 <span data-ttu-id="25b58-124">Consente di visualizzare l'ambito della variabile,</span><span class="sxs-lookup"><span data-stu-id="25b58-124">View the scope of the variable.</span></span> <span data-ttu-id="25b58-125">che può essere costituito dall'intero pacchetto oppure da un contenitore o da un'attività.</span><span class="sxs-lookup"><span data-stu-id="25b58-125">A variable has either the scope of the entire package, or the scope of a container or task.</span></span> <span data-ttu-id="25b58-126">L'ambito della variabile deve essere sufficiente affinché la variabile sia visibile per qualsiasi altro componente o attività che necessita di leggerne o impostarne il valore.</span><span class="sxs-lookup"><span data-stu-id="25b58-126">The scope of the variable must be sufficient so that the variable is visible to any other tasks or components that need to read or set its value.</span></span>  
  
 <span data-ttu-id="25b58-127">È possibile modificare l'ambito facendo clic sulla variabile e quindi selezionando **Sposta variabile** nella finestra **Variabili** .</span><span class="sxs-lookup"><span data-stu-id="25b58-127">You can change the scope by clicking the variable and then clicking **Move Variable** in the **Variables** window.</span></span>  
  
 <span data-ttu-id="25b58-128">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="25b58-128">**Data Type**</span></span>  
 <span data-ttu-id="25b58-129">Consente di visualizzare il tipo di dati della variabile.</span><span class="sxs-lookup"><span data-stu-id="25b58-129">View the data type of the variable.</span></span> <span data-ttu-id="25b58-130">È possibile selezionare un tipo di dati dall'elenco per le variabili definite dall'utente.</span><span class="sxs-lookup"><span data-stu-id="25b58-130">You can select a data type from the list for user-defined variables.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="25b58-131">Se si assegna un'espressione alla variabile, non è possibile modificare il tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="25b58-131">If you assign an expression to the variable, you cannot change the data type.</span></span>  
  
 <span data-ttu-id="25b58-132">**Valore**</span><span class="sxs-lookup"><span data-stu-id="25b58-132">**Value**</span></span>  
 <span data-ttu-id="25b58-133">Consente di visualizzare il valore della variabile.</span><span class="sxs-lookup"><span data-stu-id="25b58-133">View the variable value.</span></span> <span data-ttu-id="25b58-134">È possibile aggiornare il valore per le variabili definite dall'utente.</span><span class="sxs-lookup"><span data-stu-id="25b58-134">You can update the value for user-defined variables.</span></span> <span data-ttu-id="25b58-135">Questo valore può essere letterale, un'espressione e una stringa su più righe.</span><span class="sxs-lookup"><span data-stu-id="25b58-135">This value can be a literal or an expression, and the value can be a multi-line string.</span></span> <span data-ttu-id="25b58-136">Per assegnare un'espressione alla variabile, fare clic sul pulsante con i puntini di sospensione accanto alla colonna **Espressione** nella finestra **Variabili** .</span><span class="sxs-lookup"><span data-stu-id="25b58-136">To assign an expression to the variable, click the ellipse button that is next to the **Expression** column in the **Variables** window.</span></span>  
  
 `Namespace`  
 <span data-ttu-id="25b58-137">Consente di visualizzare il nome dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="25b58-137">View the namespace name.</span></span> <span data-ttu-id="25b58-138">Le variabili definite dall'utente vengono inizialmente create nello spazio dei nomi **User** , ma è possibile modificare il nome dello spazio dei nomi nel `Namespace` campo.</span><span class="sxs-lookup"><span data-stu-id="25b58-138">User-defined variables are initially created in the **User** namespace, but you can change the namespace name in the `Namespace` field.</span></span> <span data-ttu-id="25b58-139">Per visualizzare questa colonna, fare clic su **Opzioni griglia**.</span><span class="sxs-lookup"><span data-stu-id="25b58-139">To display this column, click **Grid Options**.</span></span>  
  
 <span data-ttu-id="25b58-140">**Raise Change Event**</span><span class="sxs-lookup"><span data-stu-id="25b58-140">**Raise Change Event**</span></span>  
 <span data-ttu-id="25b58-141">Consente di indicare se generare l'evento `OnVariableValueChanged` alla modifica di un valore.</span><span class="sxs-lookup"><span data-stu-id="25b58-141">Indicate whether to raise the `OnVariableValueChanged` event when a value changes.</span></span> <span data-ttu-id="25b58-142">È possibile aggiornare il valore per le variabili definite dall'utente e le variabili di sistema.</span><span class="sxs-lookup"><span data-stu-id="25b58-142">You can update the value for user-defined and system variables.</span></span> <span data-ttu-id="25b58-143">Per impostazione predefinita, questa colonna non viene visualizzata nella finestra **Variabili** .</span><span class="sxs-lookup"><span data-stu-id="25b58-143">By default, the **Variables** window does not list this column.</span></span> <span data-ttu-id="25b58-144">Per visualizzare questa colonna, fare clic su **Opzioni griglia**.</span><span class="sxs-lookup"><span data-stu-id="25b58-144">To display this column, click **Grid Options**.</span></span>  
  
 <span data-ttu-id="25b58-145">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="25b58-145">**Description**</span></span>  
 <span data-ttu-id="25b58-146">Consente di visualizzare la descrizione della variabile.</span><span class="sxs-lookup"><span data-stu-id="25b58-146">View the variable description.</span></span> <span data-ttu-id="25b58-147">È possibile modificare la descrizione per le variabili definite dall'utente.</span><span class="sxs-lookup"><span data-stu-id="25b58-147">You can change the description for user-defined variables.</span></span> <span data-ttu-id="25b58-148">Per impostazione predefinita, questa colonna non viene visualizzata nella finestra **Variabili** .</span><span class="sxs-lookup"><span data-stu-id="25b58-148">By default, the **Variables** window does not list this column.</span></span> <span data-ttu-id="25b58-149">Per visualizzare questa colonna, fare clic su **Opzioni griglia**.</span><span class="sxs-lookup"><span data-stu-id="25b58-149">To display this column, click **Grid Options**.</span></span>  
  
 <span data-ttu-id="25b58-150">**Espressione**</span><span class="sxs-lookup"><span data-stu-id="25b58-150">**Expression**</span></span>  
 <span data-ttu-id="25b58-151">Consente di visualizzare l'espressione assegnata alla variabile.</span><span class="sxs-lookup"><span data-stu-id="25b58-151">View the expression assigned to the variable.</span></span> <span data-ttu-id="25b58-152">Per assegnare un'espressione, fare clic sul pulsante con i puntini di sospensione.</span><span class="sxs-lookup"><span data-stu-id="25b58-152">To assign an expression, click the ellipse button.</span></span>  
  
 <span data-ttu-id="25b58-153">Se si assegna un'espressione a una variabile, accanto a quest'ultima viene visualizzato un marcatore icona speciale.</span><span class="sxs-lookup"><span data-stu-id="25b58-153">If you assign an expression to a variable, a special icon marker displays next to the variable.</span></span> <span data-ttu-id="25b58-154">Tale marcatore icona speciale viene visualizzato anche accanto alle gestioni connessioni e alle attività in cui sono impostate espressioni.</span><span class="sxs-lookup"><span data-stu-id="25b58-154">This special icon marker also displays next to connection managers and tasks that have expressions set on them.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25b58-155">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="25b58-155">See Also</span></span>  
 <span data-ttu-id="25b58-156">[Variabili di Integration Services &#40;SSIS&#41;](integration-services-ssis-variables.md) </span><span class="sxs-lookup"><span data-stu-id="25b58-156">[Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md) </span></span>  
 <span data-ttu-id="25b58-157">[Usare variabili nei pacchetti](../../2014/integration-services/use-variables-in-packages.md) </span><span class="sxs-lookup"><span data-stu-id="25b58-157">[Use Variables in Packages](../../2014/integration-services/use-variables-in-packages.md) </span></span>  
 <span data-ttu-id="25b58-158">[Integration Services &#40;espressioni di&#41; SSIS](expressions/integration-services-ssis-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="25b58-158">[Integration Services &#40;SSIS&#41; Expressions](expressions/integration-services-ssis-expressions.md) </span></span>  
 [<span data-ttu-id="25b58-159">Generazione di file di dump per l'esecuzione dei pacchetti</span><span class="sxs-lookup"><span data-stu-id="25b58-159">Generating Dump Files for Package Execution</span></span>](troubleshooting/generating-dump-files-for-package-execution.md)  
  
  
