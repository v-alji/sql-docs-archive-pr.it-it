---
title: Pagina Espressioni | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.expressionspage.f1
helpviewer_keywords:
- Expressions Page dialog box
ms.assetid: c9016ec6-11c1-4ebd-b2a7-0fa6631fd9e4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ba4e73ea495456e8f9e452108ab09106a65543ae
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627921"
---
# <a name="expressions-page"></a><span data-ttu-id="119e4-102">Pagina Espressioni</span><span class="sxs-lookup"><span data-stu-id="119e4-102">Expressions Page</span></span>
  <span data-ttu-id="119e4-103">Usare la pagina **Espressioni** per modificare le espressioni di proprietà e accedere alle finestre di dialogo **Editor espressioni di proprietà** e **Property Expression Builder** (Generatore di espressioni di proprietà).</span><span class="sxs-lookup"><span data-stu-id="119e4-103">Use the **Expressions** page to edit property expressions and to access the **Property Expressions Editor** and **Property Expression Builder** dialog boxes.</span></span>  
  
 <span data-ttu-id="119e4-104">Le espressioni di proprietà aggiornano i valori delle proprietà durante l'esecuzione del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="119e4-104">Property expressions update the values of properties when the package is run.</span></span> <span data-ttu-id="119e4-105">È possibile utilizzare queste espressioni con le proprietà di pacchetti, attività, contenitori, gestioni connessioni e alcuni componenti del flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="119e4-105">Property expressions can be used with the properties of packages, tasks, containers, connection managers, as well as some data flow components.</span></span> <span data-ttu-id="119e4-106">Le espressioni vengono valutate e i risultati vengono utilizzati in sostituzione dei valori che sono stati impostati per le proprietà alla configurazione del pacchetto e dei relativi oggetti.</span><span class="sxs-lookup"><span data-stu-id="119e4-106">The expressions are evaluated and their results are used instead of the values to which you set the properties when you configured the package and package objects.</span></span> <span data-ttu-id="119e4-107">Nelle espressioni possono essere presenti variabili e le funzioni e gli operatori forniti dal linguaggio delle espressioni.</span><span class="sxs-lookup"><span data-stu-id="119e4-107">The expressions can include variables and the functions and operators that the expression language provides.</span></span> <span data-ttu-id="119e4-108">È possibile, ad esempio, generare la riga Oggetto di un'attività Invia messaggi concatenando il valore di una variabile contenente la stringa "Previsioni del tempo per:" e i risultati restituiti dalla funzione GETDATE() per ottenere la stringa "Previsioni del tempo per: 4/5/2006".</span><span class="sxs-lookup"><span data-stu-id="119e4-108">For example, you can generate the subject line for the Send Mail task by concatenating the value of a variable that contains the string "Weather forecast for " and the return results of the GETDATE() function to make the string "Weather forecast for 4/5/2006".</span></span>  
  
 <span data-ttu-id="119e4-109">Per altre informazioni sulla scrittura di espressioni e sull'utilizzo di espressioni di proprietà, vedere [Espressioni di Integration Services &#40;SSIS&#41;](integration-services-ssis-expressions.md) e [Utilizzo delle espressioni di proprietà nei pacchetti](use-property-expressions-in-packages.md).</span><span class="sxs-lookup"><span data-stu-id="119e4-109">To learn more about writing expressions and using property expressions, see [Integration Services &#40;SSIS&#41; Expressions](integration-services-ssis-expressions.md) and [Use Property Expressions in Packages](use-property-expressions-in-packages.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="119e4-110">Opzioni</span><span class="sxs-lookup"><span data-stu-id="119e4-110">Options</span></span>  
 <span data-ttu-id="119e4-111">**Espressioni (...)**</span><span class="sxs-lookup"><span data-stu-id="119e4-111">**Expressions (...)**</span></span>  
 <span data-ttu-id="119e4-112">Fare clic sui puntini di sospensione per aprire la finestra di dialogo **Editor espressioni di proprietà** .</span><span class="sxs-lookup"><span data-stu-id="119e4-112">Click the ellipsis to open the **Property Expressions Editor** dialog box.</span></span> <span data-ttu-id="119e4-113">Per altre informazioni, vedere [Editor espressioni di proprietà](property-expressions-editor.md).</span><span class="sxs-lookup"><span data-stu-id="119e4-113">For more information, see [Property Expressions Editor](property-expressions-editor.md).</span></span>  
  
 **\<property name>**  
 <span data-ttu-id="119e4-114">Fare clic sui puntini di sospensione per aprire la finestra di dialogo **Generatore di espressioni** .</span><span class="sxs-lookup"><span data-stu-id="119e4-114">Click the ellipsis to open the **Expression Builder** dialog box.</span></span> <span data-ttu-id="119e4-115">Per altre informazioni, vedere [Generatore di espressioni](expression-builder.md).</span><span class="sxs-lookup"><span data-stu-id="119e4-115">For more information, see [Expression Builder](expression-builder.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="119e4-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="119e4-116">See Also</span></span>  
 <span data-ttu-id="119e4-117">[Variabili di Integration Services &#40;SSIS&#41;](../integration-services-ssis-variables.md) </span><span class="sxs-lookup"><span data-stu-id="119e4-117">[Integration Services &#40;SSIS&#41; Variables](../integration-services-ssis-variables.md) </span></span>  
 <span data-ttu-id="119e4-118">[Variabili di sistema](../system-variables.md) </span><span class="sxs-lookup"><span data-stu-id="119e4-118">[System Variables](../system-variables.md) </span></span>  
 [<span data-ttu-id="119e4-119">Espressioni di Integration Services &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="119e4-119">Integration Services &#40;SSIS&#41; Expressions</span></span>](integration-services-ssis-expressions.md)  
  
  
