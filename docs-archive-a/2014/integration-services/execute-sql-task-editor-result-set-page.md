---
title: Editor attività Esegui SQL (pagina set di risultati) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.executesqltask.resultset.f1
helpviewer_keywords:
- Execute SQL Task Editor
ms.assetid: d27000c8-8d91-4e1c-b45e-bca9a3c12f6d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 027f3c77e84b47958e9fb6567acdb308c14eb1e7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626828"
---
# <a name="execute-sql-task-editor-result-set-page"></a><span data-ttu-id="c1367-102">Editor attività Esegui SQL (pagina Set dei risultati)</span><span class="sxs-lookup"><span data-stu-id="c1367-102">Execute SQL Task Editor (Result Set Page)</span></span>
  <span data-ttu-id="c1367-103">La pagina **Set dei risultati** della finestra di dialogo **Editor attività Esegui SQL** consente di eseguire il mapping dei risultati dell'istruzione SQL a variabili nuove o esistenti.</span><span class="sxs-lookup"><span data-stu-id="c1367-103">Use the **Result Set** page of the **Execute SQL Task Editor** dialog to map the result of the SQL statement to new or existing variables.</span></span> <span data-ttu-id="c1367-104">Le opzioni disponibili in questa finestra di dialogo sono disabilitate se **ResultSet** è impostato su **None**nella pagina Generale.</span><span class="sxs-lookup"><span data-stu-id="c1367-104">The options in this dialog box are disabled if **ResultSet** on the General page is set to **None**.</span></span>  
  
 <span data-ttu-id="c1367-105">Per altre informazioni su questa attività vedere [Attività Esegui SQL](control-flow/execute-sql-task.md) e [Set di risultati nell'attività Esegui SQL](../../2014/integration-services/result-sets-in-the-execute-sql-task.md).</span><span class="sxs-lookup"><span data-stu-id="c1367-105">For more information about this task, see [Execute SQL Task](control-flow/execute-sql-task.md) and [Result Sets in the Execute SQL Task](../../2014/integration-services/result-sets-in-the-execute-sql-task.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="c1367-106">Opzioni</span><span class="sxs-lookup"><span data-stu-id="c1367-106">Options</span></span>  
 <span data-ttu-id="c1367-107">**Nome risultato**</span><span class="sxs-lookup"><span data-stu-id="c1367-107">**Result Name**</span></span>  
 <span data-ttu-id="c1367-108">Dopo aver aggiunto un set di mapping del set di risultati facendo clic su **Aggiungi**, specificare un nome per il risultato.</span><span class="sxs-lookup"><span data-stu-id="c1367-108">After you have added a result set mapping set by clicking **Add**, provide a name for the result.</span></span> <span data-ttu-id="c1367-109">A seconda del tipo di set di risultati, è necessario utilizzare nomi specifici per i risultati.</span><span class="sxs-lookup"><span data-stu-id="c1367-109">Depending on the result set type, you must use specific result names.</span></span>  
  
 <span data-ttu-id="c1367-110">Se il set di risultati è di tipo **Riga singola**, è possibile utilizzare o il nome di una colonna restituita dalla query o il numero che rappresenta la posizione di una colonna nell'elenco di colonne di una colonna restituita dalla query.</span><span class="sxs-lookup"><span data-stu-id="c1367-110">If the result set type is **Single row**, you can use either the name of a column returned by the query or the number that represents the position of a column in the column list of a column returned by the query.</span></span>  
  
 <span data-ttu-id="c1367-111">Se il set di risultati è di tipo **Set dei risultati completo** o **XML**, sarà necessario usare 0 come nome del set di risultati.</span><span class="sxs-lookup"><span data-stu-id="c1367-111">If the result set type is **Full result set** or **XML**, you must use 0 as the result set name.</span></span>  
  
 <span data-ttu-id="c1367-112">**Argomenti correlati**: [Set di risultati nell'attività Esegui SQL](../../2014/integration-services/result-sets-in-the-execute-sql-task.md)</span><span class="sxs-lookup"><span data-stu-id="c1367-112">**Related Topics**: [Result Sets in the Execute SQL Task](../../2014/integration-services/result-sets-in-the-execute-sql-task.md)</span></span>  
  
 <span data-ttu-id="c1367-113">**Nome variabile**</span><span class="sxs-lookup"><span data-stu-id="c1367-113">**Variable Name**</span></span>  
 <span data-ttu-id="c1367-114">Eseguire il mapping del set di risultati a una variabile selezionando una variabile o facendo clic su \<**New variable...**> per aggiungere una nuova variabile usando la finestra di dialogo **Aggiungi variabile**.</span><span class="sxs-lookup"><span data-stu-id="c1367-114">Map the result set to a variable by selecting a variable or click \<**New variable...**> to add a new variable by using the **Add Variable** dialog box.</span></span>  
  
 <span data-ttu-id="c1367-115">**Aggiungere**</span><span class="sxs-lookup"><span data-stu-id="c1367-115">**Add**</span></span>  
 <span data-ttu-id="c1367-116">Fare clic su questo pulsante per aggiungere un mapping del set di risultati.</span><span class="sxs-lookup"><span data-stu-id="c1367-116">Click to add a result set mapping.</span></span>  
  
 <span data-ttu-id="c1367-117">**Rimuovi**</span><span class="sxs-lookup"><span data-stu-id="c1367-117">**Remove**</span></span>  
 <span data-ttu-id="c1367-118">Selezionare un mapping del set di risultati e quindi fare clic su **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="c1367-118">Select a result set mapping in the list and then click **Remove**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1367-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c1367-119">See Also</span></span>  
 <span data-ttu-id="c1367-120">[Guida di riferimento ai messaggi e agli errori di Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="c1367-120">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="c1367-121">[Editor attività Esegui SQL &#40;pagina generale&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="c1367-121">[Execute SQL Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="c1367-122">[Editor attività Esegui SQL &#40;pagina Mapping parametri&#41;](../../2014/integration-services/execute-sql-task-editor-parameter-mapping-page.md) </span><span class="sxs-lookup"><span data-stu-id="c1367-122">[Execute SQL Task Editor &#40;Parameter Mapping Page&#41;](../../2014/integration-services/execute-sql-task-editor-parameter-mapping-page.md) </span></span>  
 [<span data-ttu-id="c1367-123">Guida di riferimento a Transact-SQL &#40;Motore di database&#41;</span><span class="sxs-lookup"><span data-stu-id="c1367-123">Transact-SQL Reference &#40;Database Engine&#41;</span></span>](/sql/t-sql/language-reference)  
  
  
