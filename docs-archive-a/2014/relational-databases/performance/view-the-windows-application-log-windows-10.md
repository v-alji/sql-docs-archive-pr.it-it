---
title: Visualizzare il log applicazioni di Windows (Windows) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- viewing logs
- application logs [SQL Server]
- logs [SQL Server], application
- monitoring Windows NT application log [SQL Server]
- Windows NT application logs [SQL Server]
- displaying logs
- monitoring [SQL Server], events
- logs [SQL Server], viewing
ms.assetid: 168a6c6e-12df-46a9-9904-55d63ca8fe14
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 1255e95833d9fc56abd1700f5acb0d2f49ebf77c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715228"
---
# <a name="view-the-windows-application-log-windows"></a><span data-ttu-id="5157c-102">Visualizzazione del log applicazioni di Windows</span><span class="sxs-lookup"><span data-stu-id="5157c-102">View the Windows Application Log (Windows)</span></span>
  <span data-ttu-id="5157c-103">Quando si configura [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per l'utilizzo del registro applicazioni di Windows, ogni sessione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] scrive nuovi eventi in tale registro.</span><span class="sxs-lookup"><span data-stu-id="5157c-103">When [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is configured to use the Windows application log, each [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] session writes new events to that log.</span></span> <span data-ttu-id="5157c-104">A differenza di quanto avviene per il log degli errori di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , non viene creato un nuovo registro applicazioni a ogni avvio di un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5157c-104">Unlike the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log, a new application log is not created each time you start an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
### <a name="to-view-the-windows-application-log"></a><span data-ttu-id="5157c-105">Per visualizzare il registro delle applicazioni di Windows</span><span class="sxs-lookup"><span data-stu-id="5157c-105">To view the Windows application log</span></span>  
  
1.  <span data-ttu-id="5157c-106">Fare clic sul pulsante **Start** , scegliere **Tutti i programmi**, **Strumenti di amministrazione**e quindi **Visualizzatore eventi**.</span><span class="sxs-lookup"><span data-stu-id="5157c-106">On the **Start** menu, point to **All Programs**, point to **Administrative Tools**, and then click **Event Viewer**.</span></span>  
  
2.  <span data-ttu-id="5157c-107">Nel Visualizzatore eventi fare clic su **Applicazione**.</span><span class="sxs-lookup"><span data-stu-id="5157c-107">In Event Viewer, click **Application**.</span></span>  
  
3.  <span data-ttu-id="5157c-108">Gli eventi di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sono contrassegnati dalla voce **MSSQLSERVER** (le istanze denominate sono contrassegnate dalla voce **MSSQL$** _<nome_istanza>_ ) nella colonna **Source**.</span><span class="sxs-lookup"><span data-stu-id="5157c-108">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] events are identified by the entry **MSSQLSERVER** (named instances are identified with **MSSQL$**_<instance_name>_) in the **Source** column.</span></span> <span data-ttu-id="5157c-109">Gli eventi di SQL Server Agent sono contrassegnati dalla voce SQLSERVERAGENT (per le istanze denominate di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], gli eventi di Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sono contrassegnati dall'identificatore **SQLAgent$** \<*instance_name*>).</span><span class="sxs-lookup"><span data-stu-id="5157c-109">SQL Server Agent events are identified by the entry SQLSERVERAGENT (for named instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent events are identified with **SQLAgent$**\<*instance_name*>).</span></span> <span data-ttu-id="5157c-110">Gli eventi del servizio Microsoft Search sono contrassegnati dalla voce **Microsoft Search**.</span><span class="sxs-lookup"><span data-stu-id="5157c-110">Microsoft Search service events are identified by the entry **Microsoft Search**.</span></span>  
  
4.  <span data-ttu-id="5157c-111">Per visualizzare il registro di un altro computer, fare clic con il pulsante destro del mouse su **Visualizzatore eventi**, scegliere **Connetti a un altro computer** , quindi immettere le informazioni necessarie nella finestra di dialogo **Selezione computer**.</span><span class="sxs-lookup"><span data-stu-id="5157c-111">To view the log of a different computer, right-click **Event Viewer**, click **Connect to another computer,** and complete the **Select Computer**dialog box.</span></span>  
  
5.  <span data-ttu-id="5157c-112">Facoltativamente, per visualizzare solo gli eventi di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , scegliere **Filtro** dal menu **Visualizza**e quindi selezionare **MSSQLSERVER** nell'elenco **Origine evento**.</span><span class="sxs-lookup"><span data-stu-id="5157c-112">Optionally, to display only [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] events, on the **View** menu click **Filter**, and in the **Event source** list, select **MSSQLSERVER**.</span></span> <span data-ttu-id="5157c-113">Per visualizzare solo gli eventi di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent selezionare invece **SQLSERVERAGENT** nell'elenco **Origine evento** .</span><span class="sxs-lookup"><span data-stu-id="5157c-113">To view only [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent events, instead select **SQLSERVERAGENT** in the **Event source** list.</span></span>  
  
6.  <span data-ttu-id="5157c-114">Per visualizzare ulteriori informazioni su un evento, fare doppio clic sull'evento stesso.</span><span class="sxs-lookup"><span data-stu-id="5157c-114">To view more information about an event, double-click the event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5157c-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5157c-115">See Also</span></span>  
 [<span data-ttu-id="5157c-116">Visualizzazione del log degli errori di SQL Server &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="5157c-116">View the SQL Server Error Log &#40;SQL Server Management Studio&#41;</span></span>](../../ssms/sql-server-management-studio-ssms.md)  
  
  
