---
title: finestra Variabili locali
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Locals Window [Transact-SQL]
ms.assetid: 59bea640-7823-4b4d-832c-f384d83cca2f
author: rothja
ms.author: jroth
ms.openlocfilehash: 6f8f62eb69a50d7543af41dddb9c62c842d17151
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637213"
---
# <a name="locals-window"></a><span data-ttu-id="b96e9-102">finestra Variabili locali</span><span class="sxs-lookup"><span data-stu-id="b96e9-102">Locals Window</span></span>
  <span data-ttu-id="b96e9-103">Nella finestra **Variabili locali** vengono visualizzate informazioni sulle espressioni locali nell'ambito corrente del debugger [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b96e9-103">The **Locals** window displays information about the local expressions in the current scope of the [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger.</span></span> <span data-ttu-id="b96e9-104">L'ambito è impostato sul frame dello stack di chiamate corrente selezionato nella finestra **Stack di chiamate** .</span><span class="sxs-lookup"><span data-stu-id="b96e9-104">The scope is set to the current call stack frame that is selected in the **Call Stack** window.</span></span> <span data-ttu-id="b96e9-105">Per visualizzare espressioni locali, è necessario utilizzare la modalità di debug.</span><span class="sxs-lookup"><span data-stu-id="b96e9-105">You must be in debug mode to display the local expressions.</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="b96e9-106">Elenco attività</span><span class="sxs-lookup"><span data-stu-id="b96e9-106">Task List</span></span>  
 <span data-ttu-id="b96e9-107">**Per accedere alla finestra Variabili locali**</span><span class="sxs-lookup"><span data-stu-id="b96e9-107">**To access the Locals window**</span></span>  
  
-   <span data-ttu-id="b96e9-108">Scegliere **Finestre** dal menu **Debug**, quindi fare clic su **Variabili locali**.</span><span class="sxs-lookup"><span data-stu-id="b96e9-108">On the **Debug** menu, click **Windows**, and then click **Locals**.</span></span>  
  
 <span data-ttu-id="b96e9-109">**Per modificare il valore di un'espressione**</span><span class="sxs-lookup"><span data-stu-id="b96e9-109">**To change the value of an expression**</span></span>  
  
-   <span data-ttu-id="b96e9-110">Fare clic con il pulsante destro del mouse sull'espressione e scegliere **Modifica valore**.</span><span class="sxs-lookup"><span data-stu-id="b96e9-110">Right-click the expression, and then select **Edit Value**.</span></span>  
  
## <a name="columns"></a><span data-ttu-id="b96e9-111">Colonne</span><span class="sxs-lookup"><span data-stu-id="b96e9-111">Columns</span></span>  
 <span data-ttu-id="b96e9-112">**Nome**</span><span class="sxs-lookup"><span data-stu-id="b96e9-112">**Name**</span></span>  
 <span data-ttu-id="b96e9-113">Nome dell'espressione locale.</span><span class="sxs-lookup"><span data-stu-id="b96e9-113">Is the name of the local expression.</span></span> <span data-ttu-id="b96e9-114">Nel debugger [!INCLUDE[tsql](../../includes/tsql-md.md)] vengono elencati parametri, variabili e funzioni di sistema i cui nomi iniziano per @@.</span><span class="sxs-lookup"><span data-stu-id="b96e9-114">The [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger lists variables, parameters, and the system functions that have names that start with @@.</span></span>  
  
 <span data-ttu-id="b96e9-115">**Valore**</span><span class="sxs-lookup"><span data-stu-id="b96e9-115">**Value**</span></span>  
 <span data-ttu-id="b96e9-116">Consente di visualizzare il valore è assegnato attualmente all'espressione locale.</span><span class="sxs-lookup"><span data-stu-id="b96e9-116">Displays the value that is currently assigned to the local expression.</span></span> <span data-ttu-id="b96e9-117">Questa colonna è vuota quando non è stato assegnato alcun valore all'espressione.</span><span class="sxs-lookup"><span data-stu-id="b96e9-117">This column is blank when no value has been assigned to the expression.</span></span>  
  
 <span data-ttu-id="b96e9-118">Se la lunghezza di un'espressione è maggiore della larghezza della colonna **Valore** , il valore completo verrà visualizzato in una descrizione comandi quando si sposta il puntatore sulla cella **Valore** per l'espressione.</span><span class="sxs-lookup"><span data-stu-id="b96e9-118">If the length of an expression is larger than the width of the **Value** column, a tooltip displays the full value when you move the pointer over the **Value** cell for that expression.</span></span>  
  
 <span data-ttu-id="b96e9-119">Un'icona di lente di ingrandimento in una cella **Valore** indica che è disponibile il visualizzatore del debugger [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b96e9-119">A magnifying glass icon in a **Value** cell indicates that the [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger visualizer is available.</span></span> <span data-ttu-id="b96e9-120">Nell'elenco è possibile specificare **Visualizzatore testo**, **Visualizzatore XML**o **Visualizzatore HTML**.</span><span class="sxs-lookup"><span data-stu-id="b96e9-120">In the list, you can specify **Text Visualizer**, **XML Visualizer**, or **HTML Visualizer**.</span></span> <span data-ttu-id="b96e9-121">Per avviare un visualizzatore del debugger, fare clic sull'icona di lente di ingrandimento.</span><span class="sxs-lookup"><span data-stu-id="b96e9-121">To start a debugger visualizer, click the magnifying glass icon.</span></span> <span data-ttu-id="b96e9-122">Tramite il debugger [!INCLUDE[tsql](../../includes/tsql-md.md)] viene visualizzata una finestra di dialogo contenente dati in un formato appropriato per il tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="b96e9-122">The [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger opens a dialog box that displays the data in a format appropriate to the data type.</span></span>  
  
 <span data-ttu-id="b96e9-123">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="b96e9-123">**Type**</span></span>  
 <span data-ttu-id="b96e9-124">Consente di visualizzare il tipo di dati dell'espressione.</span><span class="sxs-lookup"><span data-stu-id="b96e9-124">Displays the data type of the expression.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b96e9-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b96e9-125">See Also</span></span>  
 <span data-ttu-id="b96e9-126">[Debugger Transact-SQL](transact-sql-debugger.md) </span><span class="sxs-lookup"><span data-stu-id="b96e9-126">[Transact-SQL Debugger](transact-sql-debugger.md) </span></span>  
 <span data-ttu-id="b96e9-127">[Informazioni del debugger Transact-SQL](transact-sql-debugger-information.md) </span><span class="sxs-lookup"><span data-stu-id="b96e9-127">[Transact-SQL Debugger Information](transact-sql-debugger-information.md) </span></span>  
 <span data-ttu-id="b96e9-128">[finestra Espressioni di controllo](transact-sql-debugger-watch-window.md) </span><span class="sxs-lookup"><span data-stu-id="b96e9-128">[Watch Window](transact-sql-debugger-watch-window.md) </span></span>  
 <span data-ttu-id="b96e9-129">[Finestra Stack di chiamate](transact-sql-debugger-call-stack-window.md) </span><span class="sxs-lookup"><span data-stu-id="b96e9-129">[Call Stack Window](transact-sql-debugger-call-stack-window.md) </span></span>  
 <span data-ttu-id="b96e9-130">[Finestra di dialogo Controllo immediato](transact-sql-debugger-quickwatch-dialog-box.md) </span><span class="sxs-lookup"><span data-stu-id="b96e9-130">[QuickWatch Dialog Box](transact-sql-debugger-quickwatch-dialog-box.md) </span></span>  
 [<span data-ttu-id="b96e9-131">Espressioni &#40; Transact-SQL &#41;</span><span class="sxs-lookup"><span data-stu-id="b96e9-131">Expressions &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/expressions-transact-sql)  
