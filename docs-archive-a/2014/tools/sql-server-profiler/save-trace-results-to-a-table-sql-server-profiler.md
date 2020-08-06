---
title: Salvare i risultati della traccia in una tabella (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- saving traces
- traces [SQL Server], saving
ms.assetid: edbecf74-683b-4e43-a1ef-7a3d5f5e27f6
author: stevestein
ms.author: sstein
ms.openlocfilehash: 08acfb4e7136f8b28d1c990d508b8578f96a57b8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722020"
---
# <a name="save-trace-results-to-a-table-sql-server-profiler"></a><span data-ttu-id="731a7-102">Salvare i risultati della traccia in una tabella (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="731a7-102">Save Trace Results to a Table (SQL Server Profiler)</span></span>
  <span data-ttu-id="731a7-103">In questo argomento viene descritta la procedura per salvare i risultati della traccia in una tabella di database mediante [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="731a7-103">This topic describes how to save trace results to a database table by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>  
  
### <a name="to-save-trace-results-to-a-table"></a><span data-ttu-id="731a7-104">Per salvare i risultati della traccia in una tabella</span><span class="sxs-lookup"><span data-stu-id="731a7-104">To save trace results to a table</span></span>  
  
1.  <span data-ttu-id="731a7-105">Scegliere **Nuova traccia** dal menu **File**e quindi connettersi a un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="731a7-105">On the **File** menu, click **New Trace**, and then connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
     <span data-ttu-id="731a7-106">Verrà visualizzata la finestra di dialogo **Proprietà traccia**.</span><span class="sxs-lookup"><span data-stu-id="731a7-106">The **Trace Properties**dialog box appears.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="731a7-107">Se l'opzione **Avvia traccia non appena viene stabilita una connessione**è selezionata, la finestra di dialogo **Proprietà traccia**non viene visualizzata e viene invece avviata la traccia.</span><span class="sxs-lookup"><span data-stu-id="731a7-107">If **Start tracing immediately after making connection**is selected, the **Trace Properties**dialog box fails to appear and the trace begins instead.</span></span> <span data-ttu-id="731a7-108">Per disabilitare questa impostazione, scegliere **Opzioni**dal menu **Strumenti**e deselezionare la casella di controllo **Avvia traccia non appena viene stabilita una connessione** .</span><span class="sxs-lookup"><span data-stu-id="731a7-108">To turn off this setting, on the **Tools**menu, click **Options**, and clear the **Start tracing immediately after making connection** check box.</span></span>  
  
2.  <span data-ttu-id="731a7-109">Nella casella **Nome traccia** digitare il nome della traccia e quindi fare clic su **Salva nella tabella**.</span><span class="sxs-lookup"><span data-stu-id="731a7-109">In the **Trace name** box, type a name for the trace, and then click **Save to table**.</span></span>  
  
3.  <span data-ttu-id="731a7-110">Nella finestra di dialogo **Connetti al server** connettersi al database di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] che conterrà la tabella di traccia.</span><span class="sxs-lookup"><span data-stu-id="731a7-110">In the **Connect to server** dialog box, connect to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database that will contain the trace table.</span></span>  
  
4.  <span data-ttu-id="731a7-111">Nella finestra di dialogo **Tabella di destinazione** selezionare un database dall'elenco **Database**.</span><span class="sxs-lookup"><span data-stu-id="731a7-111">In the **Destination Table** dialog box, select a database from the **Database**list.</span></span>  
  
5.  <span data-ttu-id="731a7-112">Nell'elenco **Proprietario** selezionare il proprietario della traccia.</span><span class="sxs-lookup"><span data-stu-id="731a7-112">In the **Owner** list, select the owner for the trace.</span></span>  
  
6.  <span data-ttu-id="731a7-113">Nell'elenco **Tabella** digitare o selezionare il nome della tabella per i risultati della traccia.</span><span class="sxs-lookup"><span data-stu-id="731a7-113">In the **Table** list, type or select the table name for the trace results.</span></span> <span data-ttu-id="731a7-114">Scegliere **OK.**</span><span class="sxs-lookup"><span data-stu-id="731a7-114">Click **OK.**</span></span>  
  
7.  <span data-ttu-id="731a7-115">Nella finestra di dialogo **Proprietà traccia** selezionare la casella di controllo **Imposta numero massimo di righe (in migliaia)** per specificare il numero massimo di righe da salvare.</span><span class="sxs-lookup"><span data-stu-id="731a7-115">In the **Trace Properties** dialog box, select the **Set maximum rows (in thousands)** check box to specify the maximum number of rows to save.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="731a7-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="731a7-116">See Also</span></span>  
 [<span data-ttu-id="731a7-117">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="731a7-117">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
