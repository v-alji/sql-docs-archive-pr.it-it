---
title: Generatore di espressioni | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.expressionbuilder.f1
helpviewer_keywords:
- Expression Builder dialog box
ms.assetid: 4717ce33-bd4e-44bc-81e0-002de075b4d1
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 812b0d744d415d5419d54176359ddcd5837dd206
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627920"
---
# <a name="expression-builder"></a><span data-ttu-id="ea99c-102">Generatore di espressioni</span><span class="sxs-lookup"><span data-stu-id="ea99c-102">Expression Builder</span></span>
  <span data-ttu-id="ea99c-103">Usare la finestra di dialogo **Generatore di espressioni** per creare e modificare un'espressione di proprietà o scrivere l'espressione che imposta il valore di una variabile tramite un'interfaccia utente grafica in cui sono elencate variabili ed è specificato un riferimento predefinito alle funzioni, i cast di tipo e gli operatori inclusi nel linguaggio delle espressioni di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ea99c-103">Use the **Expression Builder** dialog box to create and edit a property expression or write the expression that sets the value of a variable using a graphical user interface that lists variables and provides a built-in reference to the functions, type casts, and operators that the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] expression language includes.</span></span>  
  
 <span data-ttu-id="ea99c-104">Un'espressione di proprietà è un'espressione assegnata a una proprietà.</span><span class="sxs-lookup"><span data-stu-id="ea99c-104">A property expression is an expression that is assigned to a property.</span></span> <span data-ttu-id="ea99c-105">Quando l'espressione viene valutata, la proprietà viene aggiornata in modo dinamico per utilizzare il risultato della valutazione dell'espressione.</span><span class="sxs-lookup"><span data-stu-id="ea99c-105">When the expression is evaluated, the property is dynamically updated to use the evaluation result of the expression.</span></span> <span data-ttu-id="ea99c-106">In modo analogo, un'espressione utilizzata in una variabile consente l'aggiornamento del valore della variabile con il risultato della valutazione dell'espressione.</span><span class="sxs-lookup"><span data-stu-id="ea99c-106">Likewise, an expression that is used in a variable enables the variable value to be updated with the evaluation result of the expression.</span></span>  
  
 <span data-ttu-id="ea99c-107">Esistono diversi modi per utilizzare le espressioni.</span><span class="sxs-lookup"><span data-stu-id="ea99c-107">There are many ways to use expressions:</span></span>  
  
-   <span data-ttu-id="ea99c-108">**Attività** Aggiornare la riga A usata da un'attività Invia messaggi mediante l'inserimento di un indirizzo di posta elettronica memorizzato in una variabile o aggiornare la riga Oggetto mediante la concatenazione di una stringa come "Vendite per: " e la data corrente restituita dalla funzione GETDATE.</span><span class="sxs-lookup"><span data-stu-id="ea99c-108">**Tasks** Update the To line that a Send Mail task uses by inserting an e-mail address that is stored in a variable; or update the Subject line by concatenating a string such as "Sales for: " and the current date returned by the GETDATE function.</span></span>  
  
-   <span data-ttu-id="ea99c-109">**Variabili** Impostare il valore di una variabile sul mese corrente utilizzando un'espressione quale `DATEPART("mm",GETDATE())`oppure impostare il valore di una stringa mediante la concatenazione del valore letterale della stringa e della data corrente utilizzando l'espressione `"Today's date is " + (DT_WSTR,30)(GETDATE())`.</span><span class="sxs-lookup"><span data-stu-id="ea99c-109">**Variables** Set the value of a variable to the current month by using an expression like `DATEPART("mm",GETDATE())`; or set the value of a string by concatenating the string literal and the current date by using the expression `"Today's date is " + (DT_WSTR,30)(GETDATE())`.</span></span>  
  
-   <span data-ttu-id="ea99c-110">**Gestioni connessioni** Impostare la tabella codici di una gestione connessioni file flat utilizzando una variabile che contiene un identificatore di tabella codici diverso oppure specificare il numero di righe da ignorare nel file di dati immettendo nell'espressione un valore integer positivo, ad esempio 3.</span><span class="sxs-lookup"><span data-stu-id="ea99c-110">**Connection Managers** Set the code page of a Flat File connection manager by using a variable that contains a different code page identifier; or specify the number of rows in the data file to skip by entering a positive integer like 3 in the expression.</span></span>  
  
 <span data-ttu-id="ea99c-111">Per sapere di più sulle espressioni di proprietà e sulla scrittura di espressioni, vedere [Utilizzo delle espressioni di proprietà nei pacchetti](use-property-expressions-in-packages.md) e [Espressioni di Integration Services &#40;SSIS&#41;](integration-services-ssis-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="ea99c-111">To learn more about property expressions and writing expressions, see [Use Property Expressions in Packages](use-property-expressions-in-packages.md) and [Integration Services &#40;SSIS&#41; Expressions](integration-services-ssis-expressions.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="ea99c-112">Opzioni</span><span class="sxs-lookup"><span data-stu-id="ea99c-112">Options</span></span>  
  
|<span data-ttu-id="ea99c-113">Termine</span><span class="sxs-lookup"><span data-stu-id="ea99c-113">Term</span></span>|<span data-ttu-id="ea99c-114">Definizione</span><span class="sxs-lookup"><span data-stu-id="ea99c-114">Definition</span></span>|  
|----------|----------------|  
|<span data-ttu-id="ea99c-115">**Variabili**</span><span class="sxs-lookup"><span data-stu-id="ea99c-115">**Variables**</span></span>|<span data-ttu-id="ea99c-116">Espandere la cartella **Variabili** e trascinare le variabili nella casella **Espressione** .</span><span class="sxs-lookup"><span data-stu-id="ea99c-116">Expand the **Variables** folder and drag variables to the **Expression** box.</span></span>|  
|<span data-ttu-id="ea99c-117">**Funzioni matematiche**</span><span class="sxs-lookup"><span data-stu-id="ea99c-117">**Mathematical Functions**</span></span><br /><br /> <span data-ttu-id="ea99c-118">**Funzioni per i valori stringa**</span><span class="sxs-lookup"><span data-stu-id="ea99c-118">**String Functions**</span></span><br /><br /> <span data-ttu-id="ea99c-119">**Funzioni di data/ora**</span><span class="sxs-lookup"><span data-stu-id="ea99c-119">**Date/Time Functions**</span></span><br /><br /> <span data-ttu-id="ea99c-120">**Funzioni NULL**</span><span class="sxs-lookup"><span data-stu-id="ea99c-120">**NULL Functions**</span></span><br /><br /> <span data-ttu-id="ea99c-121">**Cast di tipo**</span><span class="sxs-lookup"><span data-stu-id="ea99c-121">**Type Casts**</span></span><br /><br /> <span data-ttu-id="ea99c-122">**Operatori**</span><span class="sxs-lookup"><span data-stu-id="ea99c-122">**Operators**</span></span>|<span data-ttu-id="ea99c-123">Espandere le cartelle e trascinare le funzioni, i cast di tipo e gli operatori nella casella **Espressione** .</span><span class="sxs-lookup"><span data-stu-id="ea99c-123">Expand the folders and drag functions, type casts, and operators to the **Expression** box.</span></span>|  
|<span data-ttu-id="ea99c-124">**Espressione**</span><span class="sxs-lookup"><span data-stu-id="ea99c-124">**Expression**</span></span>|<span data-ttu-id="ea99c-125">Consente di modificare o digitare un'espressione.</span><span class="sxs-lookup"><span data-stu-id="ea99c-125">Edit or type an expression.\`</span></span>|  
|<span data-ttu-id="ea99c-126">**Valore valutato**</span><span class="sxs-lookup"><span data-stu-id="ea99c-126">**Evaluated value**</span></span>|<span data-ttu-id="ea99c-127">Indica il valore restituito dall'espressione.</span><span class="sxs-lookup"><span data-stu-id="ea99c-127">Lists the evaluation result of the expression.</span></span>|  
|<span data-ttu-id="ea99c-128">**Valuta espressione**</span><span class="sxs-lookup"><span data-stu-id="ea99c-128">**Evaluate Expression**</span></span>|<span data-ttu-id="ea99c-129">Fare clic su **Valuta espressione** per visualizzare i valori restituiti dell'espressione.</span><span class="sxs-lookup"><span data-stu-id="ea99c-129">Click **Evaluate Expression** to view the evaluation result of the expression.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ea99c-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ea99c-130">See Also</span></span>  
 <span data-ttu-id="ea99c-131">[Pagina Espressioni](expressions-page.md) </span><span class="sxs-lookup"><span data-stu-id="ea99c-131">[Expressions Page](expressions-page.md) </span></span>  
 <span data-ttu-id="ea99c-132">[Editor espressioni di proprietà](property-expressions-editor.md) </span><span class="sxs-lookup"><span data-stu-id="ea99c-132">[Property Expressions Editor](property-expressions-editor.md) </span></span>  
 <span data-ttu-id="ea99c-133">[Variabili di Integration Services &#40;SSIS&#41;](../integration-services-ssis-variables.md) </span><span class="sxs-lookup"><span data-stu-id="ea99c-133">[Integration Services &#40;SSIS&#41; Variables](../integration-services-ssis-variables.md) </span></span>  
 [<span data-ttu-id="ea99c-134">Variabili di sistema</span><span class="sxs-lookup"><span data-stu-id="ea99c-134">System Variables</span></span>](../system-variables.md)  
  
  
