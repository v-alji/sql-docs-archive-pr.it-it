---
title: Migliorare l'accesso ai dati della traccia | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- Profiler [SQL Server Profiler], space
- SQL Server Profiler, space
- space [SQL Server], SQL Server Profiler
ms.assetid: c260c000-fd53-4831-993f-df6894f3228b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 60e01ad04ddd9f7fe6d858c399abb552716f2bea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713975"
---
# <a name="improve-access-to-trace-data"></a><span data-ttu-id="4378a-102">Migliorare l'accesso ai dati della traccia</span><span class="sxs-lookup"><span data-stu-id="4378a-102">Improve Access to Trace Data</span></span>
  [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] <span data-ttu-id="4378a-103">usa lo spazio nella directory **temp** per migliorare l'accesso ai dati di traccia.</span><span class="sxs-lookup"><span data-stu-id="4378a-103">uses space in the **temp** directory to improve access to trace data.</span></span> [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] <span data-ttu-id="4378a-104">richiede almeno 10 megabyte (MB) di spazio disponibile.</span><span class="sxs-lookup"><span data-stu-id="4378a-104">requires at least 10 megabytes (MB) of free space.</span></span> <span data-ttu-id="4378a-105">Se lo spazio libero scende al di sotto di tale limite durante l'utilizzo di [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], tutte le funzioni di [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] verranno arrestate.</span><span class="sxs-lookup"><span data-stu-id="4378a-105">If free space drops below 10 MB while you are using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], all [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] functions stop.</span></span>  
  
 <span data-ttu-id="4378a-106">Quando [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] usa lo spazio della directory **temp** , è possibile che le dimensioni di questa directory **temp** aumentino rapidamente.</span><span class="sxs-lookup"><span data-stu-id="4378a-106">When [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] uses space in the **temp** directory, this space usage may cause the **temp** directory to grow rapidly.</span></span> <span data-ttu-id="4378a-107">Per evitare problemi legati all'aumento delle dimensioni, è possibile inserire la directory **temp** in un'unità non di sistema, modificando il valore della variabile di ambiente TEMP.</span><span class="sxs-lookup"><span data-stu-id="4378a-107">To avoid file-growth problems, you can place the **temp** directory on a drive that is not a system drive by changing the value for the TEMP environment variable.</span></span>  
  
 <span data-ttu-id="4378a-108">Nella procedura seguente viene illustrato come modificare il valore della variabile di ambiente TEMP nella maggior parte dei sistemi operativi Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="4378a-108">The following procedure describes how to change the value for the TEMP environment variable in most Microsoft Windows operating systems.</span></span> <span data-ttu-id="4378a-109">Per ulteriori informazioni sull'impostazione delle variabili di ambiente, vedere la documentazione relativa al sistema operativo Windows utilizzato.</span><span class="sxs-lookup"><span data-stu-id="4378a-109">For more information about setting environment variables, see your Windows operating system documentation.</span></span>  
  
### <a name="to-change-the-temp-environment-variable-in-windows-operating-systems"></a><span data-ttu-id="4378a-110">Per modificare la variabile di ambiente TEMP nei sistemi operativi Windows</span><span class="sxs-lookup"><span data-stu-id="4378a-110">To change the TEMP environment variable in Windows operating systems</span></span>  
  
1.  <span data-ttu-id="4378a-111">Dal menu **Start** scegliere **Pannello di controllo**e quindi **Sistema**.</span><span class="sxs-lookup"><span data-stu-id="4378a-111">On the **Start** menu, choose **Control Panel**, and then click **System**.</span></span>  
  
2.  <span data-ttu-id="4378a-112">Nella finestra di dialogo **Proprietà del sistema** fare clic sulla scheda **Avanzate** e quindi fare clic **su Variabili d'ambiente**.</span><span class="sxs-lookup"><span data-stu-id="4378a-112">In the **System Properties** dialog box, click the **Advanced** tab, and then click **Environment Variables**.</span></span>  
  
3.  <span data-ttu-id="4378a-113">Scorrere verso il basso l'elenco **Variabili di sistema**, selezionare la riga corrispondente alla variabile **TEMP** e quindi fare clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="4378a-113">Scroll down the list of **System Variables**, select the row that corresponds to the **TEMP** variable, and click **Edit**.</span></span>  
  
4.  <span data-ttu-id="4378a-114">Nella finestra di dialogo **Modifica variabile di sistema** immettere il percorso e il nome dell'unità e della directory in cui si vuole inserire la directory **temp** .</span><span class="sxs-lookup"><span data-stu-id="4378a-114">In the **Edit System Variable** dialog box, enter the path and name of the drive and directory where you want the **temp** directory to be located.</span></span>  
  
5.  <span data-ttu-id="4378a-115">Per salvare le modifiche, fare clic su **OK** .</span><span class="sxs-lookup"><span data-stu-id="4378a-115">Click **OK** to save the change.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4378a-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4378a-116">See Also</span></span>  
 <span data-ttu-id="4378a-117">[Avviare SQL Server Profiler](../../tools/sql-server-profiler/start-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="4378a-117">[Start SQL Server Profiler](../../tools/sql-server-profiler/start-sql-server-profiler.md) </span></span>  
 [<span data-ttu-id="4378a-118">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="4378a-118">SQL Server Profiler</span></span>](../../tools/sql-server-profiler/sql-server-profiler.md)  
  
  
