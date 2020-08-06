---
title: Editor ciclo foreach (pagina Mapping variabili) | Microsoft Docs
ms.custom: ''
ms.date: 08/22/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.foreachloopcontainer.mapping.f1
ms.assetid: aa847b87-f391-48a5-9849-eeda2d6b00b9
author: chugugrace
ms.author: chugu
ms.openlocfilehash: cd37c8c6c00f18d8b5493a058239cc880ecc1f5e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727059"
---
# <a name="foreach-loop-editor-variable-mappings-page"></a><span data-ttu-id="b5252-102">Editor ciclo Foreach (pagina Mapping variabili)</span><span class="sxs-lookup"><span data-stu-id="b5252-102">Foreach Loop Editor (Variable Mappings Page)</span></span>
  <span data-ttu-id="b5252-103">Utilizzare la pagina **Mapping variabili** della finestra di dialogo **Editor ciclo Foreach** per eseguire il mapping delle variabili al valore della raccolta.</span><span class="sxs-lookup"><span data-stu-id="b5252-103">Use the **Variables Mappings** page of the **Foreach Loop Editor** dialog box to map variables to the collection value.</span></span> <span data-ttu-id="b5252-104">Il valore della variabile viene aggiornato con i valori della raccolta in ogni iterazione del ciclo.</span><span class="sxs-lookup"><span data-stu-id="b5252-104">The value of the variable is updated with the collection values on each iteration of the loop.</span></span>  
  
 <span data-ttu-id="b5252-105">Per informazioni sull'utilizzo del contenitore Ciclo Foreach in un pacchetto di Integration Services, vedere [Foreach Loop Container](control-flow/foreach-loop-container.md) .</span><span class="sxs-lookup"><span data-stu-id="b5252-105">To learn about how to use the Foreach Loop container in an Integration Services package,  see [Foreach Loop Container](control-flow/foreach-loop-container.md) .</span></span> <span data-ttu-id="b5252-106">Per informazioni su come configurarlo, vedere [Configurazione di un contenitore Ciclo Foreach](../../2014/integration-services/configure-a-foreach-loop-container.md).</span><span class="sxs-lookup"><span data-stu-id="b5252-106">To learn about how to configure it, see [Configure a Foreach Loop Container](../../2014/integration-services/configure-a-foreach-loop-container.md).</span></span>  
  
 <span data-ttu-id="b5252-107">Nell'esercitazione di [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] per la creazione di un pacchetto ETL semplice è inclusa una lezione in cui vengono descritte le procedure di aggiunta e configurazione di un ciclo Foreach.</span><span class="sxs-lookup"><span data-stu-id="b5252-107">The [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] tutorial, Creating a Simple ETL Package Tutorial, includes a lesson that teaches you to add and configure a Foreach Loop.</span></span>  
  
## <a name="options"></a><span data-ttu-id="b5252-108">Opzioni</span><span class="sxs-lookup"><span data-stu-id="b5252-108">Options</span></span>  
 <span data-ttu-id="b5252-109">**Variabile**</span><span class="sxs-lookup"><span data-stu-id="b5252-109">**Variable**</span></span>  
 <span data-ttu-id="b5252-110">Selezionare una variabile esistente oppure fare clic su \<**New variable...**> per creare una nuova variabile.</span><span class="sxs-lookup"><span data-stu-id="b5252-110">Select an existing variable, or click \<**New variable...**> to create a new variable.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b5252-111">Dopo il mapping di una variabile, viene aggiunta automaticamente una nuova riga all'elenco **Variabile**.</span><span class="sxs-lookup"><span data-stu-id="b5252-111">After you map a variable, a new row is automatically added to the **Variable** list.</span></span>  
  
 <span data-ttu-id="b5252-112">**Argomenti correlati**: [Variabili di Integration Services &#40;SSIS&#41;](integration-services-ssis-variables.md), [Aggiungere una variabile](../../2014/integration-services/add-variable.md)</span><span class="sxs-lookup"><span data-stu-id="b5252-112">**Related Topics**: [Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md), [Add Variable](../../2014/integration-services/add-variable.md)</span></span>  
  
 <span data-ttu-id="b5252-113">**Index**</span><span class="sxs-lookup"><span data-stu-id="b5252-113">**Index**</span></span>  
 <span data-ttu-id="b5252-114">Se si utilizza l'enumeratore Foreach Item, specificare l'indice della colonna nel valore della raccolta di cui eseguire il mapping alla variabile.</span><span class="sxs-lookup"><span data-stu-id="b5252-114">If using the Foreach Item enumerator, specify the index of the column in the collection value to map to the variable.</span></span> <span data-ttu-id="b5252-115">Per altri tipi di enumeratore, l'indice è di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="b5252-115">For other enumerator types, the index is read-only.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b5252-116">L'indice è in base 0.</span><span class="sxs-lookup"><span data-stu-id="b5252-116">The index is 0-based.</span></span>  
  
 <span data-ttu-id="b5252-117">**Argomenti correlati**: [Esecuzione di un ciclo su file e tabelle di Excel utilizzando un contenitore Ciclo Foreach](control-flow/loop-through-excel-files-and-tables-by-using-a-foreach-loop-container.md)</span><span class="sxs-lookup"><span data-stu-id="b5252-117">**Related Topics**: [Loop through Excel Files and Tables by Using a Foreach Loop Container](control-flow/loop-through-excel-files-and-tables-by-using-a-foreach-loop-container.md)</span></span>  
  
 <span data-ttu-id="b5252-118">**Elimina**</span><span class="sxs-lookup"><span data-stu-id="b5252-118">**Delete**</span></span>  
 <span data-ttu-id="b5252-119">Selezionare una variabile e quindi fare clic su **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="b5252-119">Select a variable, and then click **Delete**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5252-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b5252-120">See Also</span></span>  
 <span data-ttu-id="b5252-121">[Guida di riferimento ai messaggi e agli errori di Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="b5252-121">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="b5252-122">[Editor ciclo foreach &#40;pagina generale&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="b5252-122">[Foreach Loop Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="b5252-123">[Editor ciclo foreach &#40;pagina raccolta&#41;](../../2014/integration-services/foreach-loop-editor-collection-page.md) </span><span class="sxs-lookup"><span data-stu-id="b5252-123">[Foreach Loop Editor &#40;Collection Page&#41;](../../2014/integration-services/foreach-loop-editor-collection-page.md) </span></span>  
 <span data-ttu-id="b5252-124">[Pagina Espressioni](expressions/expressions-page.md) </span><span class="sxs-lookup"><span data-stu-id="b5252-124">[Expressions Page](expressions/expressions-page.md) </span></span>  
 [<span data-ttu-id="b5252-125">Contenitore Ciclo For</span><span class="sxs-lookup"><span data-stu-id="b5252-125">For Loop Container</span></span>](control-flow/for-loop-container.md)  
  
  
