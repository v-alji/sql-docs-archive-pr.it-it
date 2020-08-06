---
title: Finestra di comando
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Command Window [Transact-SQL]
ms.assetid: e567ebf9-0793-451b-92c7-26193a02d9da
author: rothja
ms.author: jroth
ms.openlocfilehash: c766ed5408de96b6a2305ce377f9031947618a7b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636663"
---
# <a name="command-window"></a><span data-ttu-id="92901-102">Finestra di comando</span><span class="sxs-lookup"><span data-stu-id="92901-102">Command Window</span></span>
  <span data-ttu-id="92901-103">Usare la funzionalità **Finestra di comando** per eseguire comandi, ad esempio i comandi debug o di modifica, sul codice incluso nella finestra dell'editor di query del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] di cui è in corso il debug.</span><span class="sxs-lookup"><span data-stu-id="92901-103">Use the **CommandWindow** to run commands, such as debug and edit commands, against the code in the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] Query Editor window that is currently being debugged.</span></span> <span data-ttu-id="92901-104">Per usare la funzionalità **Finestra di comando**, è necessario usare la modalità di debug.</span><span class="sxs-lookup"><span data-stu-id="92901-104">You must be in debug mode to use the **Command Window**.</span></span> <span data-ttu-id="92901-105">Il debugger [!INCLUDE[tsql](../../includes/tsql-md.md)] supporta molti dei comandi supportati anche nella finestra **Comando** di [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="92901-105">The [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger supports many of the commands that are also supported in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] **Command** window.</span></span> <span data-ttu-id="92901-106">Per altre informazioni, vedere [Visual Studio Command Window](https://go.microsoft.com/fwlink/?LinkId=112007)(Finestra di comando di Visual Studio).</span><span class="sxs-lookup"><span data-stu-id="92901-106">For more information, see [Visual Studio Command Window](https://go.microsoft.com/fwlink/?LinkId=112007).</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="92901-107">Elenco attività</span><span class="sxs-lookup"><span data-stu-id="92901-107">Task List</span></span>  
 <span data-ttu-id="92901-108">**Per accedere alla funzionalità Finestra di comando**</span><span class="sxs-lookup"><span data-stu-id="92901-108">**To access the Command Window**</span></span>  
  
-   <span data-ttu-id="92901-109">Scegliere **Avvia debug** dal menu **Debug**.</span><span class="sxs-lookup"><span data-stu-id="92901-109">On the **Debug** menu, click **Start Debugging**.</span></span>  
  
 <span data-ttu-id="92901-110">**Per stampare il valore di una variabile**</span><span class="sxs-lookup"><span data-stu-id="92901-110">**To print the value of a variable**</span></span>  
  
-   <span data-ttu-id="92901-111">In **finestra**digitare \*\*debug. Print \<VariableName> \*\*, quindi premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="92901-111">In the **CommandWindow**, type **Debug.Print \<VariableName>**, and then press ENTER.</span></span>  
  
 <span data-ttu-id="92901-112">**Per elencare le informazioni sul thread corrente**</span><span class="sxs-lookup"><span data-stu-id="92901-112">**To list information about the current thread**</span></span>  
  
-   <span data-ttu-id="92901-113">In **finestra**Digitare `Debug.ListThread` e quindi premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="92901-113">In the **CommandWindow**, type `Debug.ListThread`, and then press ENTER.</span></span>  
  
 <span data-ttu-id="92901-114">**Per aggiungere una variabile alla finestra Controllo immediato**</span><span class="sxs-lookup"><span data-stu-id="92901-114">**To add a variable to the QuickWatch window**</span></span>  
  
-   <span data-ttu-id="92901-115">In **finestra**digitare \*\*debug. controllo immediato \<VariableName> \*\*, quindi premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="92901-115">In the **CommandWindow**, type **Debug.QuickWatch \<VariableName>**, and then press ENTER.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92901-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="92901-116">See Also</span></span>  
 [<span data-ttu-id="92901-117">Debugger Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="92901-117">Transact-SQL Debugger</span></span>](transact-sql-debugger.md)  
