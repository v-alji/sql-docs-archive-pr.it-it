---
title: Attività Esegui istruzione T-SQL | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.executetsqlstatementtask.f1
helpviewer_keywords:
- Transact-SQL statements, SSIS
- statements [Integration Services]
- Execute T-SQL Statement task [Integration Services]
ms.assetid: 7e9086ca-d27e-46c0-bfad-d61333ebd55e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7ebc73ad843ac7fcf1dfbe7699ecd8ea53edcdad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713384"
---
# <a name="execute-t-sql-statement-task"></a><span data-ttu-id="75c51-102">Attività Esegui istruzione T-SQL</span><span class="sxs-lookup"><span data-stu-id="75c51-102">Execute T-SQL Statement Task</span></span>
  <span data-ttu-id="75c51-103">L'attività Esegui istruzione T-SQL consente di eseguire istruzioni Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="75c51-103">The Execute T-SQL Statement task runs Transact-SQL statements.</span></span> <span data-ttu-id="75c51-104">Per altre informazioni, vedere [Guida di riferimento a Transact-SQL &#40;Motore di database&#41;](/sql/t-sql/language-reference) e [Query di Integration Services &#40;SSIS&#41;](../integration-services-ssis-queries.md).</span><span class="sxs-lookup"><span data-stu-id="75c51-104">For more information, see [Transact-SQL Reference &#40;Database Engine&#41;](/sql/t-sql/language-reference) and [Integration Services &#40;SSIS&#41; Queries](../integration-services-ssis-queries.md).</span></span>  
  
 <span data-ttu-id="75c51-105">Questa attività è simile all'attività Esegui SQL,</span><span class="sxs-lookup"><span data-stu-id="75c51-105">This task is similar to the Execute SQL task.</span></span> <span data-ttu-id="75c51-106">ma supporta solo la versione Transact-SQL del linguaggio SQL e non può essere utilizzata per eseguire istruzioni su server che utilizzano altri sottolinguaggi del linguaggio SQL.</span><span class="sxs-lookup"><span data-stu-id="75c51-106">However, the Execute T-SQL Statement task supports only the Transact-SQL version of the SQL language and you cannot use this task to run statements on servers that use other dialects of the SQL language.</span></span> <span data-ttu-id="75c51-107">Se è necessario eseguire query con parametri, salvare i risultati delle query nelle variabili oppure utilizzare espressioni di proprietà, è necessario utilizzare l'attività Esegui SQL anziché l'attività Esegui istruzione T-SQL.</span><span class="sxs-lookup"><span data-stu-id="75c51-107">If you need to run parameterized queries, save the query results to variables, or use property expressions, you should use the Execute SQL task instead of the Execute T-SQL Statement task.</span></span> <span data-ttu-id="75c51-108">Per altre informazioni, vedere [Attività Esegui SQL](execute-sql-task.md).</span><span class="sxs-lookup"><span data-stu-id="75c51-108">For more information, see [Execute SQL Task](execute-sql-task.md).</span></span>  
  
## <a name="configuration-of-the-execute-t-sql-task"></a><span data-ttu-id="75c51-109">Configurazione dell'attività Esegui istruzione T-SQL</span><span class="sxs-lookup"><span data-stu-id="75c51-109">Configuration of the Execute T-SQL Task</span></span>  
 <span data-ttu-id="75c51-110">È possibile impostare le proprietà tramite Progettazione [!INCLUDE[ssIS](../../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="75c51-110">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="75c51-111">Questa attività è disponibile nella sezione **Attività di manutenzione** della **casella degli strumenti** di Progettazione [!INCLUDE[ssIS](../../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="75c51-111">This task is in the **Maintenance Plan Tasks** section of the **Toolbox** in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="75c51-112">Per ulteriori informazioni sulle proprietà che è possibile impostare in Progettazione [!INCLUDE[ssIS](../../../includes/ssis-md.md)] , fare clic sull'argomento seguente:</span><span class="sxs-lookup"><span data-stu-id="75c51-112">For more information about the properties that you can set in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="75c51-113">Attività Esegui istruzione T-SQL &#40;Piano di manutenzione&#41;</span><span class="sxs-lookup"><span data-stu-id="75c51-113">Execute T-SQL Statement Task &#40;Maintenance Plan&#41;</span></span>](../../relational-databases/maintenance-plans/execute-t-sql-statement-task-maintenance-plan.md)  
  
 <span data-ttu-id="75c51-114">Per altre informazioni sull'impostazione di queste proprietà in Progettazione [!INCLUDE[ssIS](../../../includes/ssis-md.md)] , fare clic sull'argomento seguente:</span><span class="sxs-lookup"><span data-stu-id="75c51-114">For more information about how to set these properties in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="75c51-115">Impostazione delle proprietà di un'attività o di un contenitore</span><span class="sxs-lookup"><span data-stu-id="75c51-115">Set the Properties of a Task or Container</span></span>](../set-the-properties-of-a-task-or-container.md)  
  
## <a name="see-also"></a><span data-ttu-id="75c51-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="75c51-116">See Also</span></span>  
 <span data-ttu-id="75c51-117">[Attività di Integration Services](integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="75c51-117">[Integration Services Tasks](integration-services-tasks.md) </span></span>  
 <span data-ttu-id="75c51-118">[Flusso di controllo](control-flow.md) </span><span class="sxs-lookup"><span data-stu-id="75c51-118">[Control Flow](control-flow.md) </span></span>  
 [<span data-ttu-id="75c51-119">MERGE nei pacchetti di Integration Services</span><span class="sxs-lookup"><span data-stu-id="75c51-119">MERGE in Integration Services Packages</span></span>](merge-in-integration-services-packages.md)  
  
  
