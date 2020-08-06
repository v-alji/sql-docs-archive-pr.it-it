---
title: Impostare un avviso del database di SQL Server (Windows) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- alerts [SQL Server], creating
ms.assetid: 65d2c5c1-921f-4eff-9ef7-149170ab61e8
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 090eeda2c134857df18d083ce06d460214aa4dfb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637815"
---
# <a name="set-up-a-sql-server-database-alert-windows"></a><span data-ttu-id="4f682-102">Impostazione di un avviso del database di SQL Server (Windows)</span><span class="sxs-lookup"><span data-stu-id="4f682-102">Set Up a SQL Server Database Alert (Windows)</span></span>
  <span data-ttu-id="4f682-103">Tramite Monitoraggio di sistema è possibile creare un avviso da generare quando viene raggiunto un valore soglia per un contatore di Monitoraggio di sistema.</span><span class="sxs-lookup"><span data-stu-id="4f682-103">Using System Monitor, you can create an alert to be raised when a threshold value for a System Monitor counter has been reached.</span></span> <span data-ttu-id="4f682-104">In risposta all'avviso, Monitoraggio di sistema può avviare un'applicazione, ad esempio un'applicazione personalizzata programmata per gestire la condizione dell'avviso.</span><span class="sxs-lookup"><span data-stu-id="4f682-104">In response to the alert, System Monitor can launch an application, such as a custom application written to handle the alert condition.</span></span> <span data-ttu-id="4f682-105">Ad esempio, è possibile creare un avviso che viene generato quando il numero di deadlock supera un valore specifico.</span><span class="sxs-lookup"><span data-stu-id="4f682-105">For example, you can create an alert that is raised when the number of deadlocks exceeds a specific value.</span></span>  
  
 <span data-ttu-id="4f682-106">È inoltre possibile impostare gli avvisi tramite Microsoft [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] e [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="4f682-106">Alerts also can be defined using Microsoft [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span> <span data-ttu-id="4f682-107">Per altre informazioni, vedere [Avvisi](../../ssms/agent/alerts.md).</span><span class="sxs-lookup"><span data-stu-id="4f682-107">For more information, see [Alerts](../../ssms/agent/alerts.md).</span></span>  
  
### <a name="to-set-up-a-sql-server-database-alert"></a><span data-ttu-id="4f682-108">Per impostare un avviso del database di SQL Server</span><span class="sxs-lookup"><span data-stu-id="4f682-108">To set up a SQL Server database alert</span></span>  
  
1.  <span data-ttu-id="4f682-109">Nell'albero di navigazione della finestra Prestazioni espandere **Avvisi e registri di prestazioni**.</span><span class="sxs-lookup"><span data-stu-id="4f682-109">On the navigation tree of the Performance window, expand **Performance Logs and Alerts**.</span></span>  
  
2.  <span data-ttu-id="4f682-110">Fare clic con il pulsante destro del mouse su **Avvisi**e quindi scegliere **Impostazioni nuovo avviso**.</span><span class="sxs-lookup"><span data-stu-id="4f682-110">Right-click **Alerts**, and then click **New Alert Settings**.</span></span>  
  
3.  <span data-ttu-id="4f682-111">Nella finestra di dialogo **Impostazioni nuovo avviso** digitare un nome per il nuovo avviso e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="4f682-111">In the **New Alert Settings** dialog box, type a name for the new alert, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="4f682-112">Nella scheda **Generale** della finestra di dialogo relativa al nuovo avviso inserire un commento nel campo **Commento**e fare clic su **Aggiungi** per aggiungere un contatore all'avviso.</span><span class="sxs-lookup"><span data-stu-id="4f682-112">On the **General** tab of the dialog box for the new alert, add a **Comment**, and click **Add** to add a counter to the alert.</span></span>  
  
     <span data-ttu-id="4f682-113">Tutti gli avvisi devono avere almeno un contatore.</span><span class="sxs-lookup"><span data-stu-id="4f682-113">All alerts must have at least one counter.</span></span>  
  
5.  <span data-ttu-id="4f682-114">Nella finestra di dialogo Aggiungi contatori selezionare un oggetto di SQL Server nell'elenco **Oggetto prestazione** e quindi selezionare un contatore in **Seleziona i contatori dall'elenco**.</span><span class="sxs-lookup"><span data-stu-id="4f682-114">In the Add Counters dialog box, select a SQL Server object from the **Performance Object** list, and then select a counter from the **Select counters from list**.</span></span>  
  
6.  <span data-ttu-id="4f682-115">Per aggiungere il contatore all'avviso, fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="4f682-115">To add the counter to the alert, click **Add**.</span></span> <span data-ttu-id="4f682-116">È possibile continuare ad aggiungere contatori oppure fare clic su **Chiudi** per tornare alla finestra di dialogo del nuovo avviso.</span><span class="sxs-lookup"><span data-stu-id="4f682-116">You can continue to add counters, or you can click **Close** to return to the dialog box for the new alert.</span></span>  
  
7.  <span data-ttu-id="4f682-117">Nella finestra di dialogo del nuovo avviso selezionare **Superiore** o **Inferiore**nell'elenco **Avvisa quando il valore è** e quindi specificare un valore soglia in **Limite**.</span><span class="sxs-lookup"><span data-stu-id="4f682-117">In the new alert dialog box, click either **Over** or **Under**in the **Alert when the value is** list, and then enter a threshold value in **Limit**.</span></span>  
  
     <span data-ttu-id="4f682-118">L'avviso viene generato quando il valore del contatore è superiore o inferiore al valore soglia, a seconda che sia stato selezionato **Superiore** o **Inferiore**.</span><span class="sxs-lookup"><span data-stu-id="4f682-118">The alert is generated when the value for the counter is more than or less than the threshold value (depending on whether you clicked **Over** or **Under**).</span></span>  
  
8.  <span data-ttu-id="4f682-119">Nelle caselle **Campiona dati ogni** impostare la frequenza di campionamento.</span><span class="sxs-lookup"><span data-stu-id="4f682-119">In the **Sample data every** boxes, set the sampling frequency.</span></span>  
  
9. <span data-ttu-id="4f682-120">Nella scheda **Azione** impostare le azioni in modo che vengano eseguite ogni volta che viene generato l'avviso.</span><span class="sxs-lookup"><span data-stu-id="4f682-120">On the **Action** tab, set actions to occur every time the alert is triggered.</span></span>  
  
10. <span data-ttu-id="4f682-121">Nella scheda **Pianificazione** impostare l'avvio e l'arresto pianificati per l'analisi dell'avviso.</span><span class="sxs-lookup"><span data-stu-id="4f682-121">On the **Schedule** tab, set the start and stop schedule for the alert scan.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f682-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4f682-122">See Also</span></span>  
 [<span data-ttu-id="4f682-123">Creare un avviso del database di SQL Server</span><span class="sxs-lookup"><span data-stu-id="4f682-123">Create a SQL Server Database Alert</span></span>](../performance-monitor/create-a-sql-server-database-alert.md)  
  
  
