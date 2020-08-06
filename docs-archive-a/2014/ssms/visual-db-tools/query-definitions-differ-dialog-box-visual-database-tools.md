---
title: Finestra di dialogo Definizioni di query diverse (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdtsql.chm:69639
- vdtsql.chm:69640
- vdt.dlgbox.querydefinitionsdiffer
ms.assetid: 90383473-2922-40e5-9682-3850849aa856
author: stevestein
ms.author: sstein
ms.openlocfilehash: b9a39d5d6b739fa4ab1a96ea95b513ecb7f6682f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720766"
---
# <a name="query-definitions-differ-dialog-box-visual-database-tools"></a><span data-ttu-id="d5cf3-102">Finestra di dialogo Definizioni di query diverse (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="d5cf3-102">Query Definitions Differ Dialog Box (Visual Database Tools)</span></span>
  <span data-ttu-id="d5cf3-103">Tramite questa finestra l'utente viene avvisato dell'impossibilità di rappresentare graficamente la query nei riquadri Diagramma e Criteri e della possibilità di modificare la query soltanto nel riquadro SQL.</span><span class="sxs-lookup"><span data-stu-id="d5cf3-103">This dialog box notifies you that your query cannot be represented graphically in the Diagram and Criteria panes, and that you can edit your query only in the SQL pane.</span></span>  
  
 <span data-ttu-id="d5cf3-104">La finestra di dialogo viene visualizzata quando si immette o si modifica un'istruzione SQL nel riquadro SQL, quindi si passa a un altro riquadro, si verifica la query o si esegue la query e viene applicata una delle seguenti condizioni:</span><span class="sxs-lookup"><span data-stu-id="d5cf3-104">This dialog box may appear when you enter or edit an SQL statement in the SQL pane; you then move to another pane, verify the query, or attempt to execute the query; and one of the following conditions applies:</span></span>  
  
-   <span data-ttu-id="d5cf3-105">L'istruzione SQL è incompleta o contiene uno o più errori di sintassi.</span><span class="sxs-lookup"><span data-stu-id="d5cf3-105">The SQL statement is incomplete or contains one or more syntax errors.</span></span>  
  
-   <span data-ttu-id="d5cf3-106">L'istruzione SQL è valida ma non è supportata nei riquadri grafici (ad esempio una query di unione).</span><span class="sxs-lookup"><span data-stu-id="d5cf3-106">The SQL statement is valid but is not supported in the graphical panes (for example, a Union query).</span></span>  
  
-   <span data-ttu-id="d5cf3-107">L'istruzione SQL è valida ma contiene una sintassi specifica per la connessione ai dati che si sta utilizzando.</span><span class="sxs-lookup"><span data-stu-id="d5cf3-107">The SQL statement is valid but contains syntax specific to the data connection you are using.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="d5cf3-108">È possibile verificare la validità di un'istruzione usando il pulsante **Verifica istruzione SQL** della barra degli strumenti **Query** .</span><span class="sxs-lookup"><span data-stu-id="d5cf3-108">You can check whether a statement is valid using the **Verify SQL Statement** button on the **Query** toolbar.</span></span>  
  
 <span data-ttu-id="d5cf3-109">Nella finestra di dialogo viene visualizzato un messaggio che indica il motivo per cui l'istruzione SQL non può essere rappresentata e quindi chiede come si desidera procedere.</span><span class="sxs-lookup"><span data-stu-id="d5cf3-109">The dialog box displays a message with the reason that the SQL statement cannot be represented, and then asks how you want to proceed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d5cf3-110">La finestra di dialogo **Definizioni di query diverse** non viene visualizzata se i riquadri Diagramma e Criteri sono stati nascosti.</span><span class="sxs-lookup"><span data-stu-id="d5cf3-110">The **Query Definitions Differ** dialog box does not appear if you have hidden the Diagram and Criteria panes.</span></span>  
  
## <a name="options"></a><span data-ttu-id="d5cf3-111">Opzioni</span><span class="sxs-lookup"><span data-stu-id="d5cf3-111">Options</span></span>  
 <span data-ttu-id="d5cf3-112">**Pulsante Ignora**</span><span class="sxs-lookup"><span data-stu-id="d5cf3-112">**Ignore Button**</span></span>  
 <span data-ttu-id="d5cf3-113">Scegliere questo pulsante per specificare che si desidera accettare l'istruzione SQL, per modificarla ulteriormente o per eseguirla.</span><span class="sxs-lookup"><span data-stu-id="d5cf3-113">Choose this button to specify that you want to accept the SQL statement, either to edit it further or to execute it.</span></span> <span data-ttu-id="d5cf3-114">Se si accetta l'istruzione, i riquadri Diagramma e Criteri saranno visualizzati in grigio, in modo da indicare che non rappresentano l'istruzione del riquadro SQL.</span><span class="sxs-lookup"><span data-stu-id="d5cf3-114">If you accept the statement, the Diagram and Criteria panes appear dimmed to indicate that they do not represent the statement in the SQL pane.</span></span>  
  
 <span data-ttu-id="d5cf3-115">**Pulsante Annulla**</span><span class="sxs-lookup"><span data-stu-id="d5cf3-115">**Undo Button**</span></span>  
 <span data-ttu-id="d5cf3-116">Scegliere questo pulsante per annullare le modifiche apportate nel riquadro SQL.</span><span class="sxs-lookup"><span data-stu-id="d5cf3-116">Choose this button to discard your changes to the SQL pane.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d5cf3-117">Se l'istruzione è corretta ma non è supportata graficamente da Progettazione query e Progettazione viste, sarà possibile eseguirla anche se non può essere rappresentata nei riquadri Diagramma e Criteri.</span><span class="sxs-lookup"><span data-stu-id="d5cf3-117">If the statement is correct but not supported graphically by the Query and View Designer, you can execute it even though it cannot be represented in the Diagram and Criteria panes.</span></span> <span data-ttu-id="d5cf3-118">Se, ad esempio, si immette una query di unione, l'istruzione può essere eseguita ma non rappresentata in altri riquadri.</span><span class="sxs-lookup"><span data-stu-id="d5cf3-118">For example, if you enter a Union query, the statement can be executed but not represented in the other panes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5cf3-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d5cf3-119">See Also</span></span>  
 [<span data-ttu-id="d5cf3-120">Strumenti di progettazione di query e viste &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="d5cf3-120">Query and View Designer Tools &#40;Visual Database Tools&#41;</span></span>](visual-database-tools.md)  
  
  
