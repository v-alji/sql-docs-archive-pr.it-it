---
title: Editor attività Esegui SQL (pagina Mapping parametri) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.executesqltask.parametermapping.f1
helpviewer_keywords:
- Execute SQL Task Editor
ms.assetid: 8ebe020a-7921-46b2-8823-398748f379b2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: cfbb4468cb69947dfa54fb519b7698286393d578
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626829"
---
# <a name="execute-sql-task-editor-parameter-mapping-page"></a><span data-ttu-id="2d39b-102">Editor attività Esegui SQL (pagina Mapping parametri)</span><span class="sxs-lookup"><span data-stu-id="2d39b-102">Execute SQL Task Editor (Parameter Mapping Page)</span></span>
  <span data-ttu-id="2d39b-103">Usare la pagina **Mapping parametri** della finestra di dialogo **Editor attività Esegui SQL** per eseguire il mapping tra variabili e parametri nell'istruzione SQL.</span><span class="sxs-lookup"><span data-stu-id="2d39b-103">Use the **Parameter Mapping** page of the **Execute SQL Task Editor** dialog box to map variables to parameters in the SQL statement.</span></span>  
  
 <span data-ttu-id="2d39b-104">Per informazioni su questa attività, vedere [Attività Esegui SQL](control-flow/execute-sql-task.md) e [Parametri e codici restituiti nell'attività Esegui SQL](../../2014/integration-services/parameters-and-return-codes-in-the-execute-sql-task.md).</span><span class="sxs-lookup"><span data-stu-id="2d39b-104">To learn about this task, see [Execute SQL Task](control-flow/execute-sql-task.md) and [Parameters and Return Codes in the Execute SQL Task](../../2014/integration-services/parameters-and-return-codes-in-the-execute-sql-task.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="2d39b-105">Opzioni</span><span class="sxs-lookup"><span data-stu-id="2d39b-105">Options</span></span>  
 <span data-ttu-id="2d39b-106">**Nome variabile**</span><span class="sxs-lookup"><span data-stu-id="2d39b-106">**Variable Name**</span></span>  
 <span data-ttu-id="2d39b-107">Dopo aver aggiunto un mapping dei parametri facendo clic su **Aggiungi**, selezionare una variabile di sistema o una variabile definita dall'utente nell'elenco oppure fare clic su \<**New variable...**> per aggiungere una nuova variabile usando la finestra di dialogo **Aggiungi variabile**.</span><span class="sxs-lookup"><span data-stu-id="2d39b-107">After you have added a parameter mapping by clicking **Add**, select a system or user-defined variable from the list or click \<**New variable...**> to add a new variable by using the **Add Variable** dialog box.</span></span>  
  
 <span data-ttu-id="2d39b-108">**Argomenti correlati:** [Variabili di Integration Services &#40;SSIS&#41;](integration-services-ssis-variables.md)</span><span class="sxs-lookup"><span data-stu-id="2d39b-108">**Related Topics:** [Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md)</span></span>  
  
 <span data-ttu-id="2d39b-109">**Direzione**</span><span class="sxs-lookup"><span data-stu-id="2d39b-109">**Direction**</span></span>  
 <span data-ttu-id="2d39b-110">Consente di selezionare la direzione del parametro.</span><span class="sxs-lookup"><span data-stu-id="2d39b-110">Select the direction of the parameter.</span></span> <span data-ttu-id="2d39b-111">Eseguire il mapping di ogni variabile a un parametro di input, a un parametro di output o a un codice restituito.</span><span class="sxs-lookup"><span data-stu-id="2d39b-111">Map each variable to an input parameter, output parameter, or a return code.</span></span>  
  
 <span data-ttu-id="2d39b-112">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="2d39b-112">**Data Type**</span></span>  
 <span data-ttu-id="2d39b-113">Selezionare il tipo di dati del parametro.</span><span class="sxs-lookup"><span data-stu-id="2d39b-113">Select the data type of the parameter.</span></span> <span data-ttu-id="2d39b-114">L'elenco dei tipi di dati disponibili è specifico del provider selezionato per la gestione connessione utilizzata dall'attività.</span><span class="sxs-lookup"><span data-stu-id="2d39b-114">The list of available data types is specific to the provider selected in the connection manager used by the task.</span></span>  
  
 <span data-ttu-id="2d39b-115">**Nome parametro**</span><span class="sxs-lookup"><span data-stu-id="2d39b-115">**Parameter Name**</span></span>  
 <span data-ttu-id="2d39b-116">Consente di specificare un nome per il parametro.</span><span class="sxs-lookup"><span data-stu-id="2d39b-116">Provide a parameter name.</span></span>  
  
 <span data-ttu-id="2d39b-117">A seconda del tipo di gestione connessione utilizzata dall'attività, è necessario specificare numeri o nomi di parametri.</span><span class="sxs-lookup"><span data-stu-id="2d39b-117">Depending on the connection manager type that the task uses, you must use numbers or parameter names.</span></span> <span data-ttu-id="2d39b-118">Alcuni tipi di gestioni delle connessioni prevedono che il primo carattere del nome del parametro sia il segno \@, nomi specifici come \@Param1 oppure nomi di colonna come nomi di parametri.</span><span class="sxs-lookup"><span data-stu-id="2d39b-118">Some connection manager types require that the first character of the parameter name is the \@ sign , specific names like \@Param1, or column names as parameter names.</span></span>  
  
 <span data-ttu-id="2d39b-119">**Argomenti correlati:** [Parametri e codici restituiti nell'attività Esegui SQL](../../2014/integration-services/parameters-and-return-codes-in-the-execute-sql-task.md)</span><span class="sxs-lookup"><span data-stu-id="2d39b-119">**Related Topics:** [Parameters and Return Codes in the Execute SQL Task](../../2014/integration-services/parameters-and-return-codes-in-the-execute-sql-task.md)</span></span>  
  
 <span data-ttu-id="2d39b-120">**Dimensioni parametro**</span><span class="sxs-lookup"><span data-stu-id="2d39b-120">**Parameter Size**</span></span>  
 <span data-ttu-id="2d39b-121">Fornisce le dimensioni dei parametri a lunghezza variabile, ad esempio stringhe e campi binario.</span><span class="sxs-lookup"><span data-stu-id="2d39b-121">Provide the size of parameters that have variable length, such as strings and binary fields.</span></span>  
  
 <span data-ttu-id="2d39b-122">Tale impostazione assicura che il provider allochi spazio sufficiente per i valori dei parametri a lunghezza variabile.</span><span class="sxs-lookup"><span data-stu-id="2d39b-122">This setting ensures that the provider allocates sufficient space for variable-length parameter values.</span></span>  
  
 <span data-ttu-id="2d39b-123">**Aggiungere**</span><span class="sxs-lookup"><span data-stu-id="2d39b-123">**Add**</span></span>  
 <span data-ttu-id="2d39b-124">Fare clic su questo pulsante per aggiungere un mapping dei parametri.</span><span class="sxs-lookup"><span data-stu-id="2d39b-124">Click to add a parameter mapping.</span></span>  
  
 <span data-ttu-id="2d39b-125">**Rimuovi**</span><span class="sxs-lookup"><span data-stu-id="2d39b-125">**Remove**</span></span>  
 <span data-ttu-id="2d39b-126">Selezionare un mapping dei parametri nell'elenco e quindi fare clic su **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="2d39b-126">Select a parameter mapping in the list and then click **Remove**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d39b-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2d39b-127">See Also</span></span>  
 <span data-ttu-id="2d39b-128">[Guida di riferimento ai messaggi e agli errori di Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="2d39b-128">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="2d39b-129">[Editor attività Esegui SQL &#40;pagina generale&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="2d39b-129">[Execute SQL Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="2d39b-130">[Editor attività Esegui SQL &#40;pagina del set di risultati&#41;](../../2014/integration-services/execute-sql-task-editor-result-set-page.md) </span><span class="sxs-lookup"><span data-stu-id="2d39b-130">[Execute SQL Task Editor &#40;Result Set Page&#41;](../../2014/integration-services/execute-sql-task-editor-result-set-page.md) </span></span>  
 [<span data-ttu-id="2d39b-131">Guida di riferimento a Transact-SQL &#40;Motore di database&#41;</span><span class="sxs-lookup"><span data-stu-id="2d39b-131">Transact-SQL Reference &#40;Database Engine&#41;</span></span>](/sql/t-sql/language-reference)  
  
  
