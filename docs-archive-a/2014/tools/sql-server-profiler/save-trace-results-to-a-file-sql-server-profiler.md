---
title: Salvare i risultati della traccia in un file (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- saving traces
- traces [SQL Server], saving
ms.assetid: ac528747-0c19-4f3d-96f5-44c762a4abed
author: stevestein
ms.author: sstein
ms.openlocfilehash: 9644751cda3689cf7b7cb00ec25310bc700ca1c5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722043"
---
# <a name="save-trace-results-to-a-file-sql-server-profiler"></a><span data-ttu-id="27415-102">Salvare i risultati della traccia in un file (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="27415-102">Save Trace Results to a File (SQL Server Profiler)</span></span>
  <span data-ttu-id="27415-103">Nel presente argomento viene illustrata la procedura di salvataggio dei risultati della traccia in un file utilizzando [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="27415-103">This topic describes how to save trace results to a file by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>  
  
### <a name="to-save-trace-results-to-a-file"></a><span data-ttu-id="27415-104">Per salvare i risultati della traccia in un file</span><span class="sxs-lookup"><span data-stu-id="27415-104">To save trace results to a file</span></span>  
  
1.  <span data-ttu-id="27415-105">Scegliere **Nuova traccia** dal menu **File**e quindi connettersi a un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="27415-105">On the **File** menu, click **New Trace**, and then connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
     <span data-ttu-id="27415-106">Verrà visualizzata la finestra di dialogo **Proprietà traccia**.</span><span class="sxs-lookup"><span data-stu-id="27415-106">The **Trace Properties**dialog box appears.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="27415-107">Se l'opzione **Avvia traccia non appena viene stabilita una connessione**è selezionata, la finestra di dialogo **Proprietà traccia**non viene visualizzata e viene invece avviata la traccia.</span><span class="sxs-lookup"><span data-stu-id="27415-107">If **Start tracing immediately after making connection**is selected, the **Trace Properties**dialog box fails to appear and the trace begins instead.</span></span> <span data-ttu-id="27415-108">Per disabilitare questa impostazione, scegliere **Opzioni**dal menu **Strumenti**e deselezionare la casella di controllo **Avvia traccia non appena viene stabilita una connessione** .</span><span class="sxs-lookup"><span data-stu-id="27415-108">To turn off this setting, on the **Tools**menu, click **Options**, and clear the **Start tracing immediately after making connection** check box.</span></span>  
  
2.  <span data-ttu-id="27415-109">Nella casella **Nome traccia** digitare un nome per la traccia.</span><span class="sxs-lookup"><span data-stu-id="27415-109">In the **Trace name** box, type a name for the trace.</span></span>  
  
3.  <span data-ttu-id="27415-110">Selezionare la casella di controllo **Salva nel file** .</span><span class="sxs-lookup"><span data-stu-id="27415-110">Select the **Save to file** check box.</span></span>  
  
     <span data-ttu-id="27415-111">Verrà visualizzata la finestra di dialogo **Salva con nome**.</span><span class="sxs-lookup"><span data-stu-id="27415-111">The **Save As**dialog box appears.</span></span>  
  
4.  <span data-ttu-id="27415-112">Specificare un percorso e un nome di file nella finestra di dialogo **Salva con nome**.</span><span class="sxs-lookup"><span data-stu-id="27415-112">Specify a path and filename in the **Save As**dialog box.</span></span> <span data-ttu-id="27415-113">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="27415-113">Click **Save.**</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="27415-114">Assicurarsi che il servizio SQL Server disponga delle autorizzazioni necessarie per la scrittura su un file nella directory specificata.</span><span class="sxs-lookup"><span data-stu-id="27415-114">Ensure that the SQL Server service has sufficient permissions to write to a file in the directory specified.</span></span>  
  
5.  <span data-ttu-id="27415-115">Nella finestra di dialogo **Proprietà traccia** digitare le dimensioni massime del file nella casella di testo **Dimensioni massime del file (MB)** .</span><span class="sxs-lookup"><span data-stu-id="27415-115">In the **Trace Properties** dialog box, enter the maximum file size in the **Set maximum file size (MB)** text box.</span></span> <span data-ttu-id="27415-116">Il valore predefinito è 5 megabyte (MB).</span><span class="sxs-lookup"><span data-stu-id="27415-116">The default value is 5 megabytes (MB).</span></span>  
  
6.  <span data-ttu-id="27415-117">Facoltativamente, specificare le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="27415-117">Optionally, specify the following options:</span></span>  
  
    -   <span data-ttu-id="27415-118">Selezionare la casella di controllo **Consenti rollover dei file** per fare in modo che [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] crei nuovi file per i dati di traccia dopo aver raggiunto le dimensioni massime del file.</span><span class="sxs-lookup"><span data-stu-id="27415-118">Select the **Enable file rollover** check box to have [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] create new files for trace data once the maximum file size is reached.</span></span> <span data-ttu-id="27415-119">Questa opzione è selezionata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="27415-119">This option is selected by default.</span></span>  
  
    -   <span data-ttu-id="27415-120">Selezionare la casella di controllo **Dati di traccia elaborati dal server** per assicurare che il server registri ogni evento di traccia.</span><span class="sxs-lookup"><span data-stu-id="27415-120">Select the **Server processes trace data** check box to ensure that the server records each trace event.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="27415-121">Quando la casella di controllo **Dati di traccia elaborati dal server**deselezionata, il server non registra gli eventi se tale registrazione determina una significativa riduzione delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="27415-121">When **Server processes trace data**is cleared, the server does not record events if recording events significantly degrades performance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27415-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="27415-122">See Also</span></span>  
 [<span data-ttu-id="27415-123">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="27415-123">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
