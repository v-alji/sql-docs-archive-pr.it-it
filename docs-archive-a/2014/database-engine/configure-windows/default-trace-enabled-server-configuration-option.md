---
title: Opzione di configurazione server default trace enabled | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- logs [SQL Server], traces
- traces [SQL Server], logs
- default trace enabled option
ms.assetid: 1322d668-44f4-469e-8fd6-e0d02a81c8f2
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8d40305de7375f2ae10d563871fd40b7acfa463f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724176"
---
# <a name="default-trace-enabled-server-configuration-option"></a><span data-ttu-id="142d9-102">Opzione di configurazione server default trace enabled</span><span class="sxs-lookup"><span data-stu-id="142d9-102">default trace enabled Server Configuration Option</span></span>
  <span data-ttu-id="142d9-103">L'opzione **Default Trace Enabled** consente di abilitare o disabilitare i file di log della traccia predefinita.</span><span class="sxs-lookup"><span data-stu-id="142d9-103">Use the **default trace enabled** option to enable or disable the default trace log files.</span></span> <span data-ttu-id="142d9-104">Tramite la funzionalità di traccia predefinita è possibile ottenere un log completo e persistente delle attività e delle modifiche correlate principalmente alle opzioni di configurazione.</span><span class="sxs-lookup"><span data-stu-id="142d9-104">The default trace functionality provides a rich, persistent log of activity and changes primarily related to the configuration options.</span></span>  
  
> [!WARNING]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)] <span data-ttu-id="142d9-105">In alternativa, usare Eventi estesi.</span><span class="sxs-lookup"><span data-stu-id="142d9-105">Use Extended Events instead.</span></span>  
  
## <a name="purpose"></a><span data-ttu-id="142d9-106">Scopo</span><span class="sxs-lookup"><span data-stu-id="142d9-106">Purpose</span></span>  
 <span data-ttu-id="142d9-107">La traccia predefinita rappresenta un supporto alla risoluzione dei problemi per gli amministratori di database, poiché consente di disporre dei dati del log necessari per diagnosticare i problemi non appena si verificano.</span><span class="sxs-lookup"><span data-stu-id="142d9-107">Default trace provides troubleshooting assistance to database administrators by ensuring that they have the log data necessary to diagnose problems the first time they occur.</span></span>  
  
## <a name="viewing"></a><span data-ttu-id="142d9-108">Visualizzazione</span><span class="sxs-lookup"><span data-stu-id="142d9-108">Viewing</span></span>  
 <span data-ttu-id="142d9-109">È possibile aprire ed esaminare i log di traccia predefiniti utilizzando [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] oppure eseguire query su tali log mediante [!INCLUDE[tsql](../../includes/tsql-md.md)] utilizzando la funzione di sistema `fn_trace_gettable` .</span><span class="sxs-lookup"><span data-stu-id="142d9-109">The default trace logs can be opened and examined by [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] or queried with [!INCLUDE[tsql](../../includes/tsql-md.md)] by using the `fn_trace_gettable` system function.</span></span> [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] <span data-ttu-id="142d9-110">è in grado di aprire i file di log delle tracce predefinite come i normali file di output delle tracce.</span><span class="sxs-lookup"><span data-stu-id="142d9-110">can open the default trace log files just as it does normal trace output files.</span></span> <span data-ttu-id="142d9-111">Per impostazione predefinita, il log di traccia predefinito viene archiviato nella directory `\MSSQL\LOG` tramite un file di traccia consecutivo.</span><span class="sxs-lookup"><span data-stu-id="142d9-111">The default trace log is stored by default in the `\MSSQL\LOG` directory using a rollover trace file.</span></span> <span data-ttu-id="142d9-112">Il nome file di base del log di traccia predefinito è `log.trc`.</span><span class="sxs-lookup"><span data-stu-id="142d9-112">The base file name for the default trace log file is `log.trc`.</span></span> <span data-ttu-id="142d9-113">In un'installazione tipica di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], la traccia predefinita è attivata e viene pertanto denominata TraceID 1.</span><span class="sxs-lookup"><span data-stu-id="142d9-113">In a typical installation of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the default trace is enabled and thus becomes TraceID 1.</span></span> <span data-ttu-id="142d9-114">Se attivato dopo l'installazione e la creazione di altre tracce, TraceID può essere associato a un numero maggiore.</span><span class="sxs-lookup"><span data-stu-id="142d9-114">If enabled after installation and after creating other traces, the TraceID can become a larger number.</span></span>  
  
 <span data-ttu-id="142d9-115">Per altre informazioni sull'uso di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Profiler per la visualizzazione di questo file di traccia, vedere [Aprire un file di traccia &#40;SQL Server Profiler&#41;](../../tools/sql-server-profiler/open-a-trace-file-sql-server-profiler.md).</span><span class="sxs-lookup"><span data-stu-id="142d9-115">For more information about using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Profiler to view this trace file, see [Open a Trace File &#40;SQL Server Profiler&#41;](../../tools/sql-server-profiler/open-a-trace-file-sql-server-profiler.md)</span></span>  
  
### <a name="example"></a><span data-ttu-id="142d9-116">Esempio:</span><span class="sxs-lookup"><span data-stu-id="142d9-116">Example:</span></span>  
 <span data-ttu-id="142d9-117">L'istruzione seguente consente di aprire il log di traccia predefinito nel percorso predefinito:</span><span class="sxs-lookup"><span data-stu-id="142d9-117">The following statement opens the default trace log in the default location:</span></span>  
  
```  
SELECT *   
FROM fn_trace_gettable  
('C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\LOG\log.trc', default);  
GO  
  
```  
  
## <a name="configuring"></a><span data-ttu-id="142d9-118">Configurazione</span><span class="sxs-lookup"><span data-stu-id="142d9-118">Configuring</span></span>  
 <span data-ttu-id="142d9-119">Se impostata su 1, l'opzione **Default Trace Enabled** abilita la **traccia predefinita**.</span><span class="sxs-lookup"><span data-stu-id="142d9-119">When set to 1, the **default trace enabled** option enables **Default Trace**.</span></span> <span data-ttu-id="142d9-120">L'impostazione predefinita per questa opzione è 1 (ON).</span><span class="sxs-lookup"><span data-stu-id="142d9-120">The default setting for this option is 1 (ON).</span></span> <span data-ttu-id="142d9-121">Se si imposta il valore 0 si disabilita la traccia.</span><span class="sxs-lookup"><span data-stu-id="142d9-121">A value of 0 turns off the trace.</span></span>  
  
 <span data-ttu-id="142d9-122">L'opzione **Default Trace Enabled** è un'opzione avanzata.</span><span class="sxs-lookup"><span data-stu-id="142d9-122">The **default trace enabled** option is an advanced option.</span></span> <span data-ttu-id="142d9-123">Se si usa la stored procedure di sistema **sp_configure** per modificare l'impostazione, è possibile modificare l'opzione **Default Trace Enabled** solo quando il valore di **Show Advanced Options** è impostato su 1.</span><span class="sxs-lookup"><span data-stu-id="142d9-123">If you are using the **sp_configure** system stored procedure to change the setting, you can change the **default trace enabled** option only when **show advanced options** is set to 1.</span></span> <span data-ttu-id="142d9-124">L'impostazione diventa effettiva immediatamente e non richiede il riavvio del server.</span><span class="sxs-lookup"><span data-stu-id="142d9-124">The setting takes effect immediately without a server restart.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="142d9-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="142d9-125">See Also</span></span>  
 <span data-ttu-id="142d9-126">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="142d9-126">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="142d9-127">[Opzioni di configurazione del server &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="142d9-127">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="142d9-128">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="142d9-128">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
