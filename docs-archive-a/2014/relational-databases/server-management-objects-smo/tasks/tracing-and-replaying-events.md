---
title: Traccia e riproduzione di eventi | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- replaying events
- traces [SMO]
- events [SMO], replaying
- events [SMO], tracing
ms.assetid: f41b3f85-2f6c-4c3e-9776-8c73d2cc7a53
author: stevestein
ms.author: sstein
ms.openlocfilehash: f7f0d570c70ef1cba080217e6c3a0f9b6055a4d5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716176"
---
# <a name="tracing-and-replaying-events"></a><span data-ttu-id="4bc69-102">Traccia e riproduzione di eventi</span><span class="sxs-lookup"><span data-stu-id="4bc69-102">Tracing and Replaying Events</span></span>
  <span data-ttu-id="4bc69-103">In SMO gli oggetti `Trace` e `Replay` nello spazio dei nomi <xref:Microsoft.SqlServer.Management.Trace> forniscono l'accesso a livello di programmazione alla funzionalità [!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)], utilizzata per monitorare un'istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] o [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4bc69-103">In SMO, the `Trace` and `Replay` objects in the <xref:Microsoft.SqlServer.Management.Trace> namespace provide programmatic access to the [!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)] functionality, which is used for monitoring an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] or [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="4bc69-104">È possibile acquisire e salvare i dati di ogni evento in un file o in una tabella per operazioni di analisi successive.</span><span class="sxs-lookup"><span data-stu-id="4bc69-104">You can capture and save data about each event to a file or table to analyze later.</span></span> <span data-ttu-id="4bc69-105">È ad esempio possibile monitorare un ambiente di produzione per verificare le stored procedure che influiscono sulle prestazioni a causa di un'esecuzione troppo lenta.</span><span class="sxs-lookup"><span data-stu-id="4bc69-105">For example, you can monitor a production environment to see which procedures are impeding performance by executing too slowly.</span></span>  
  
 <span data-ttu-id="4bc69-106">Gli oggetti `Trace` e `Replay` forniscono un set di oggetti che possono essere utilizzati per la creazione di tracce in un'istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4bc69-106">The `Trace` and `Replay` objects provide a set of objects that can be used to create traces on an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="4bc69-107">Questi oggetti possono essere utilizzati all'interno di applicazioni personalizzate per creare tracce in modo manuale per [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] o [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4bc69-107">These objects can be used from within your own applications to create traces manually for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] or [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="4bc69-108">Inoltre, gli oggetti SMO `Trace` possono essere utilizzati per leggere file e tabelle di Traccia SQL creati monitorando [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] o la registrazione DTS.</span><span class="sxs-lookup"><span data-stu-id="4bc69-108">Additionally, SMO `Trace` objects can be used to read SQL Trace files and tables that were created by monitoring [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)], or DTS logging.</span></span>  
  
 <span data-ttu-id="4bc69-109">Gli oggetti SMO `Trace` consentono di eseguire le funzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="4bc69-109">SMO `Trace` objects let you perform the following functions:</span></span>  
  
-   <span data-ttu-id="4bc69-110">Creare una traccia.</span><span class="sxs-lookup"><span data-stu-id="4bc69-110">Create a trace.</span></span>  
  
-   <span data-ttu-id="4bc69-111">Impostare i filtri nella traccia.</span><span class="sxs-lookup"><span data-stu-id="4bc69-111">Set filters on the trace.</span></span>  
  
-   <span data-ttu-id="4bc69-112">Impostare gli eventi per la traccia.</span><span class="sxs-lookup"><span data-stu-id="4bc69-112">Set the events that are being traced.</span></span>  
  
-   <span data-ttu-id="4bc69-113">Avviare o arrestare una traccia.</span><span class="sxs-lookup"><span data-stu-id="4bc69-113">Stop or start a trace.</span></span>  
  
-   <span data-ttu-id="4bc69-114">Leggere file di traccia e tabelle di traccia.</span><span class="sxs-lookup"><span data-stu-id="4bc69-114">Read trace files, and trace tables.</span></span>  
  
-   <span data-ttu-id="4bc69-115">Ottenere informazioni sugli eventi in una traccia.</span><span class="sxs-lookup"><span data-stu-id="4bc69-115">Get information about events on a trace.</span></span>  
  
-   <span data-ttu-id="4bc69-116">Ottenere informazioni sui filtri in una traccia.</span><span class="sxs-lookup"><span data-stu-id="4bc69-116">Get information about filters on a trace.</span></span>  
  
-   <span data-ttu-id="4bc69-117">Modificare i dati di traccia a livello di programmazione.</span><span class="sxs-lookup"><span data-stu-id="4bc69-117">Manipulate trace data programmatically.</span></span>  
  
-   <span data-ttu-id="4bc69-118">Scrivere file di traccia e tabelle di traccia.</span><span class="sxs-lookup"><span data-stu-id="4bc69-118">Write trace tables and trace files.</span></span>  
  
-   <span data-ttu-id="4bc69-119">Riprodurre file di traccia o tabelle di traccia.</span><span class="sxs-lookup"><span data-stu-id="4bc69-119">Replay trace files or trace tables.</span></span>  
  
 <span data-ttu-id="4bc69-120">I dati di traccia degli `Trace` `Replay` oggetti e possono essere usati dall'applicazione SMO oppure possono essere esaminati manualmente usando [SQL Server Profiler](../../../tools/sql-server-profiler/sql-server-profiler.md).</span><span class="sxs-lookup"><span data-stu-id="4bc69-120">The trace data from the `Trace` and `Replay` objects can be used by the SMO application, or it can be examined manually by using [SQL Server Profiler](../../../tools/sql-server-profiler/sql-server-profiler.md).</span></span> <span data-ttu-id="4bc69-121">I dati di traccia sono inoltre compatibili con le stored procedure di [traccia SQL](../../sql-trace/sql-trace.md) che forniscono anche le funzionalità di traccia.</span><span class="sxs-lookup"><span data-stu-id="4bc69-121">The trace data is also compatible with the [SQL Trace](../../sql-trace/sql-trace.md) stored procedures that also provide tracing capabilities.</span></span>  
  
 <span data-ttu-id="4bc69-122">Gli oggetti di traccia SMO risiedono nello spazio dei nomi <xref:Microsoft.SqlServer.Management.Trace>, che richiede un riferimento al file Microsoft.SQLServer.ConnectionInfo.dll.</span><span class="sxs-lookup"><span data-stu-id="4bc69-122">The SMO trace objects reside in the <xref:Microsoft.SqlServer.Management.Trace> namespace, which requires a reference to the Microsoft.SQLServer.ConnectionInfo.dll file.</span></span>  
  
 <span data-ttu-id="4bc69-123">Gli oggetti `Trace` e `Replay` richiedono un oggetto <xref:Microsoft.SqlServer.Management.Common.ServerConnection><xref:Microsoft.SqlServer.Management.Smo.Server.%23ctor%2A> per stabilire una connessione con l'istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4bc69-123">The `Trace` and `Replay` objects require a <xref:Microsoft.SqlServer.Management.Common.ServerConnection><xref:Microsoft.SqlServer.Management.Smo.Server.%23ctor%2A> object to establish a connection with the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="4bc69-124">L'oggetto <xref:Microsoft.SqlServer.Management.Common.ServerConnection> risiede nello spazio dei nomi <xref:Microsoft.SqlServer.Management.Common>, che richiede un riferimento al file Microsoft.SQLServer.ConnectionInfo.dll.</span><span class="sxs-lookup"><span data-stu-id="4bc69-124">The <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object resides in the <xref:Microsoft.SqlServer.Management.Common> namespace, which requires a reference to the Microsoft.SQLServer.ConnectionInfo.dll file.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4bc69-125">Gli oggetti `Trace` e `Replay` non sono supportati in una piattaforma a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="4bc69-125">The `Trace` and `Replay` objects are not supported on a 64-bit platform.</span></span>  
  
  
