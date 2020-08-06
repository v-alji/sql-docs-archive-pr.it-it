---
title: Parametri SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Database Engine analysis [Upgrade Advisor]
- SQL Server Upgrade Advisor, Database Engine
- Upgrade Advisor [SQL Server], Database Engine
- analyzing system [Upgrade Advisor], Database Engine
ms.assetid: 44a18bfe-e593-47a5-995f-382c01d3f618
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 2b885e7616506fd08cae99166cc794dbfb5dac7d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720807"
---
# <a name="sql-server-parameters"></a><span data-ttu-id="a8fbb-102">Parametri per SQL Server</span><span class="sxs-lookup"><span data-stu-id="a8fbb-102">SQL Server Parameters</span></span>
  <span data-ttu-id="a8fbb-103">In questa pagina impostare i parametri che verranno utilizzati per l'analisi del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a8fbb-103">On this page, set parameters that the analyzer will use for [!INCLUDE[ssDE](../../includes/ssde-md.md)] analysis.</span></span> <span data-ttu-id="a8fbb-104">È possibile analizzare uno, più o tutti i database, analizzare i file di traccia creati usando [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] e analizzare i file batch SQL.</span><span class="sxs-lookup"><span data-stu-id="a8fbb-104">You can analyze one, several, or all databases, analyze trace files that were created by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], and analyze SQL batch files.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a8fbb-105">Alcuni problemi di aggiornamento possono essere rilevati solo se si inviano file di traccia o file batch SQL per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="a8fbb-105">Some upgrade issues can be detected only if you submit trace files or SQL batch files to be analyzed.</span></span>  
  
## <a name="options"></a><span data-ttu-id="a8fbb-106">Opzioni</span><span class="sxs-lookup"><span data-stu-id="a8fbb-106">Options</span></span>  
 <span data-ttu-id="a8fbb-107">**Database da analizzare**</span><span class="sxs-lookup"><span data-stu-id="a8fbb-107">**Database(s) to analyze**</span></span>  
 <span data-ttu-id="a8fbb-108">Per analizzare tutti i database, selezionare la casella di controllo **tutti i database** .</span><span class="sxs-lookup"><span data-stu-id="a8fbb-108">To analyze all databases, select the **All databases** check box.</span></span> <span data-ttu-id="a8fbb-109">Per analizzare una selezione di database, selezionare la casella di controllo accanto a ogni database per includerlo nell'analisi.</span><span class="sxs-lookup"><span data-stu-id="a8fbb-109">To analyze a selection of databases, select the check box next to each database to include in the scan.</span></span>  
  
 <span data-ttu-id="a8fbb-110">**Analizza file di traccia**</span><span class="sxs-lookup"><span data-stu-id="a8fbb-110">**Analyze trace file(s)**</span></span>  
 <span data-ttu-id="a8fbb-111">Selezionare questa casella di controllo per analizzare i file di traccia nel file system.</span><span class="sxs-lookup"><span data-stu-id="a8fbb-111">Select this check box to analyze trace files in the file system.</span></span>  
  
 <span data-ttu-id="a8fbb-112">**Percorso dei file di traccia**</span><span class="sxs-lookup"><span data-stu-id="a8fbb-112">**Path to trace file(s)**</span></span>  
 <span data-ttu-id="a8fbb-113">È possibile analizzare uno o più file.</span><span class="sxs-lookup"><span data-stu-id="a8fbb-113">You can analyze one or more files.</span></span> <span data-ttu-id="a8fbb-114">Selezionare più file in un percorso oppure specificare più nomi di file.</span><span class="sxs-lookup"><span data-stu-id="a8fbb-114">You can browse to a location and select multiple files, or you can provide multiple file names.</span></span> <span data-ttu-id="a8fbb-115">Utilizzare il percorso completo di ogni file, includere il nome del file e separare le voci con il carattere barra verticale (|).</span><span class="sxs-lookup"><span data-stu-id="a8fbb-115">Use the full path name to each file, include the file name, and separate entries by using the pipe character (|).</span></span>  
  
 <span data-ttu-id="a8fbb-116">Se si abilita **analizza i file di traccia**, la **successiva** viene disabilitata fino a quando non si immettono un nome di percorso e un nome file.</span><span class="sxs-lookup"><span data-stu-id="a8fbb-116">If you enable **Analyze trace file(s)**, **Next** is disabled until you enter a path name and a file name.</span></span>  
  
 <span data-ttu-id="a8fbb-117">**Analizza [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] file batch**</span><span class="sxs-lookup"><span data-stu-id="a8fbb-117">**Analyze [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] batch file(s)**</span></span>  
 <span data-ttu-id="a8fbb-118">Selezionare questa casella di controllo per analizzare i file batch [!INCLUDE[tsql](../../includes/tsql-md.md)] nel file system.</span><span class="sxs-lookup"><span data-stu-id="a8fbb-118">Select this check box to analyze [!INCLUDE[tsql](../../includes/tsql-md.md)] batch files in the file system.</span></span>  
  
 <span data-ttu-id="a8fbb-119">**Percorso [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] file batch**</span><span class="sxs-lookup"><span data-stu-id="a8fbb-119">**Path to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] batch file(s)**</span></span>  
 <span data-ttu-id="a8fbb-120">È possibile analizzare uno o più file batch.</span><span class="sxs-lookup"><span data-stu-id="a8fbb-120">You can analyze one or more batch files.</span></span> <span data-ttu-id="a8fbb-121">Selezionare più file in un percorso oppure specificare più nomi di file.</span><span class="sxs-lookup"><span data-stu-id="a8fbb-121">You can browse to a location and select multiple files, or you can type multiple file names.</span></span> <span data-ttu-id="a8fbb-122">Utilizzare il percorso completo di ogni file, includere il nome del file e separare le voci con il carattere barra verticale (|).</span><span class="sxs-lookup"><span data-stu-id="a8fbb-122">Use the full path name to each file, include the file name, and separate entries by using the pipe character (|).</span></span>  
  
 <span data-ttu-id="a8fbb-123">Se si abilita **Analizza file batch SQL**, il pulsante **Avanti** è disabilitato fino a quando non si immettono un nome di percorso e un nome file.</span><span class="sxs-lookup"><span data-stu-id="a8fbb-123">If you enable **Analyze SQL batch file(s)**, the **Next** button is disabled until you enter a path name and a file name.</span></span>  
  
 <span data-ttu-id="a8fbb-124">**Separatore batch SQL**</span><span class="sxs-lookup"><span data-stu-id="a8fbb-124">**SQL Batch Separator**</span></span>  
 <span data-ttu-id="a8fbb-125">Testo utilizzato per separare i batch di istruzioni [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a8fbb-125">The text that is used to separate batches of [!INCLUDE[tsql](../../includes/tsql-md.md)] statements.</span></span> <span data-ttu-id="a8fbb-126">Il valore predefinito è **go**.</span><span class="sxs-lookup"><span data-stu-id="a8fbb-126">The default value is **GO**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8fbb-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a8fbb-127">See Also</span></span>  
 <span data-ttu-id="a8fbb-128">[Utilizzo di preparazione aggiornamento](../../../2014/sql-server/install/working-with-upgrade-advisor.md) </span><span class="sxs-lookup"><span data-stu-id="a8fbb-128">[Working with Upgrade Advisor](../../../2014/sql-server/install/working-with-upgrade-advisor.md) </span></span>  
 [<span data-ttu-id="a8fbb-129">Guida di riferimento all'interfaccia utente di Preparazione aggiornamento</span><span class="sxs-lookup"><span data-stu-id="a8fbb-129">Upgrade Advisor User Interface Reference</span></span>](../../../2014/sql-server/install/upgrade-advisor-user-interface-reference.md)  
  
  
