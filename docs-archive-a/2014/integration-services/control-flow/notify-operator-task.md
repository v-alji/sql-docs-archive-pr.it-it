---
title: Attività Notifica operatori | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.notifyoperatortask.f1
helpviewer_keywords:
- Notify Operator task
- notifications [Integration Services]
- SQL Server Agent [Integration Services]
ms.assetid: 6c816c68-c6d6-44e4-bb34-c8e060a958a1
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ed5158a4ec5cfe8374fedbb2afbca1294b58f05e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724847"
---
# <a name="notify-operator-task"></a><span data-ttu-id="a533b-102">Notifica operatori - attività</span><span class="sxs-lookup"><span data-stu-id="a533b-102">Notify Operator Task</span></span>
  <span data-ttu-id="a533b-103">L'attività Notifica operatori consente di inviare messaggi di notifica agli operatori di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="a533b-103">The Notify Operator task sends notification messages to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent operators.</span></span> <span data-ttu-id="a533b-104">Un operatore di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent è l'alias di una persona o di un gruppo che può ricevere notifiche elettroniche.</span><span class="sxs-lookup"><span data-stu-id="a533b-104">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent operator is an alias for a person or group that can receive electronic notifications.</span></span> <span data-ttu-id="a533b-105">Per altre informazioni sugli operatori di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , vedere [Operatori](../../ssms/agent//operators.md).</span><span class="sxs-lookup"><span data-stu-id="a533b-105">For more information about [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] operators, see [Operators](../../ssms/agent//operators.md).</span></span>  
  
 <span data-ttu-id="a533b-106">Grazie all'attività Notifica operatori, con un pacchetto possono essere inviate notifiche a uno o più operatori tramite posta elettronica, cercapersone o **Net Send**.</span><span class="sxs-lookup"><span data-stu-id="a533b-106">By using the Notify Operator task, a package can notify one or more operators via e-mail, pager, or **net send**.</span></span> <span data-ttu-id="a533b-107">Ogni operatore può ricevere notifiche tramite metodi diversi.</span><span class="sxs-lookup"><span data-stu-id="a533b-107">Each operator can be notified by different methods.</span></span> <span data-ttu-id="a533b-108">È ad esempio possibile usare la posta elettronica e il cercapersone per inviare notifiche a OperatorA e usare il cercapersone e **Net Send**per inviare notifiche a OperatorB.</span><span class="sxs-lookup"><span data-stu-id="a533b-108">For example, OperatorA is notified by e-mail and pager, and OperatorB is notified by pager and **net send**.</span></span> <span data-ttu-id="a533b-109">Gli operatori che ricevono notifiche dall'attività devono essere membri della raccolta **OperatorNotify** per l'attività Notifica operatori.</span><span class="sxs-lookup"><span data-stu-id="a533b-109">The operators who receive notifications from the task must be members of the **OperatorNotify** collection on the Notify Operator task.</span></span>  
  
 <span data-ttu-id="a533b-110">L'attività Notifica operatori è l'unica attività di manutenzione del database che non incapsula istruzioni Transact-SQL o comandi DBCC.</span><span class="sxs-lookup"><span data-stu-id="a533b-110">The Notify Operator task is the only database maintenance task that does not encapsulate a Transact-SQL statement or a DBCC command.</span></span>  
  
## <a name="configuration-of-the-notify-operator-task"></a><span data-ttu-id="a533b-111">Configurazione dell'attività Notifica operatori</span><span class="sxs-lookup"><span data-stu-id="a533b-111">Configuration of the Notify Operator Task</span></span>  
 <span data-ttu-id="a533b-112">È possibile impostare le proprietà tramite Progettazione [!INCLUDE[ssIS](../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a533b-112">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="a533b-113">Questa attività è disponibile nella sezione **Attività di manutenzione** della **casella degli strumenti** di Progettazione [!INCLUDE[ssIS](../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a533b-113">This task is in the **Maintenance Plan Tasks** section of the **Toolbox** in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="a533b-114">Per ulteriori informazioni sulle proprietà che è possibile impostare in Progettazione [!INCLUDE[ssIS](../../includes/ssis-md.md)] , fare clic sull'argomento seguente:</span><span class="sxs-lookup"><span data-stu-id="a533b-114">For more information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="a533b-115">Attività Notifica operatori &#40;Piano di manutenzione&#41;</span><span class="sxs-lookup"><span data-stu-id="a533b-115">Notify Operator Task &#40;Maintenance Plan&#41;</span></span>](../../relational-databases/maintenance-plans/notify-operator-task-maintenance-plan.md)  
  
 <span data-ttu-id="a533b-116">Per altre informazioni sull'impostazione di queste proprietà in Progettazione [!INCLUDE[ssIS](../../includes/ssis-md.md)] , fare clic sull'argomento seguente:</span><span class="sxs-lookup"><span data-stu-id="a533b-116">For more information about how to set these properties in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="a533b-117">Impostazione delle proprietà di un'attività o di un contenitore</span><span class="sxs-lookup"><span data-stu-id="a533b-117">Set the Properties of a Task or Container</span></span>](../set-the-properties-of-a-task-or-container.md)  
  
  
