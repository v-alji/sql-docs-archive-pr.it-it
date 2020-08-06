---
title: Editor gestione connessione SQL Server Compact Edition (pagina tutti) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.sqlmobileconnection.all.f1
helpviewer_keywords:
- SQL Server Compact Connection Manager Editor
ms.assetid: f9fbff4b-c502-44b3-8e7b-398d66e82206
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4f881d63de5435426475c3aed4b666870d706b40
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627296"
---
# <a name="sql-server-compact-edition-connection-manager-editor-all-page"></a><span data-ttu-id="206f9-102">Editor gestione connessione SQL Server Compact Edition (pagina Tutte)</span><span class="sxs-lookup"><span data-stu-id="206f9-102">SQL Server Compact Edition Connection Manager Editor (All Page)</span></span>
  <span data-ttu-id="206f9-103">Utilizzare la finestra di dialogo **Editor gestione connessione SQL Server Compact Edition** per specificare le proprietà di connessione a un database di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact.</span><span class="sxs-lookup"><span data-stu-id="206f9-103">Use the **SQL Server Compact Edition Connection Manager** dialog box to specify properties for connecting to a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact database.</span></span>  
  
 <span data-ttu-id="206f9-104">Per ulteriori informazioni sulla gestione connessione di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact Edition, vedere [Editor gestione connessione SQL Server Compact Edition](connection-manager/sql-server-compact-edition-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="206f9-104">To learn more about the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact Edition connection manager, see [SQL Server Compact Edition Connection Manager](connection-manager/sql-server-compact-edition-connection-manager.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="206f9-105">Opzioni</span><span class="sxs-lookup"><span data-stu-id="206f9-105">Options</span></span>  
 <span data-ttu-id="206f9-106">**AutoShrink Threshold**</span><span class="sxs-lookup"><span data-stu-id="206f9-106">**AutoShrink Threshold**</span></span>  
 <span data-ttu-id="206f9-107">Consente di specificare la quantità di spazio libero in percentuale consentito nel database di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact al raggiungimento della quale verrà avviata l'operazione di compattazione automatica.</span><span class="sxs-lookup"><span data-stu-id="206f9-107">Specify the amount of free space, as a percentage, that is allowed in the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact database before the autoshrink process runs.</span></span>  
  
 <span data-ttu-id="206f9-108">**Default Lock Escalation**</span><span class="sxs-lookup"><span data-stu-id="206f9-108">**Default Lock Escalation**</span></span>  
 <span data-ttu-id="206f9-109">Consente di specificare il numero di blocchi di database acquisiti dal database di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact prima di tentare l'escalation.</span><span class="sxs-lookup"><span data-stu-id="206f9-109">Specify the number of database locks that the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact database acquires before it tries to escalate locks.</span></span>  
  
 <span data-ttu-id="206f9-110">**Default Lock Timeout**</span><span class="sxs-lookup"><span data-stu-id="206f9-110">**Default Lock Timeout**</span></span>  
 <span data-ttu-id="206f9-111">Consente di specificare l'intervallo di tempo predefinito (in millisecondi) per cui una transazione deve rimanere in attesa di un blocco.</span><span class="sxs-lookup"><span data-stu-id="206f9-111">Specify the default interval, in milliseconds, that a transaction will wait for a lock.</span></span>  
  
 <span data-ttu-id="206f9-112">**Flush Interval**</span><span class="sxs-lookup"><span data-stu-id="206f9-112">**Flush Interval**</span></span>  
 <span data-ttu-id="206f9-113">Consente di specificare l'intervallo di tempo (in secondi) dopo il quale le transazioni completate devono essere scaricate su disco.</span><span class="sxs-lookup"><span data-stu-id="206f9-113">Specify the interval, in seconds, between committed transactions to flush data to disk.</span></span>  
  
 <span data-ttu-id="206f9-114">**Locale Identifier**</span><span class="sxs-lookup"><span data-stu-id="206f9-114">**Locale Identifier**</span></span>  
 <span data-ttu-id="206f9-115">Consente di specificare l'ID delle impostazioni locali (LCID) del database di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact.</span><span class="sxs-lookup"><span data-stu-id="206f9-115">Specify the Locale ID (LCID) of the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact database.</span></span>  
  
 <span data-ttu-id="206f9-116">**Max Buffer Size**</span><span class="sxs-lookup"><span data-stu-id="206f9-116">**Max Buffer Size**</span></span>  
 <span data-ttu-id="206f9-117">Consente di specificare la quantità massima di memoria in KB usata da [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact al raggiungimento della quale viene eseguito lo scaricamento dei dati su disco.</span><span class="sxs-lookup"><span data-stu-id="206f9-117">Specify the maximum amount of memory, in kilobytes, that [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact uses before flushing data to disk.</span></span>  
  
 <span data-ttu-id="206f9-118">**Dimensioni massime del database**</span><span class="sxs-lookup"><span data-stu-id="206f9-118">**Max Database Size**</span></span>  
 <span data-ttu-id="206f9-119">Consente di specificare le dimensioni massime in MB del database di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact.</span><span class="sxs-lookup"><span data-stu-id="206f9-119">Specify the maximum size, in megabytes, of the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact database.</span></span>  
  
 <span data-ttu-id="206f9-120">**Modalità**</span><span class="sxs-lookup"><span data-stu-id="206f9-120">**Mode**</span></span>  
 <span data-ttu-id="206f9-121">Consente di specificare la modalità file in cui aprire il database di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact.</span><span class="sxs-lookup"><span data-stu-id="206f9-121">Specify the file mode in which to open the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact database.</span></span> <span data-ttu-id="206f9-122">Il valore predefinito di questa proprietà è **Read Write**.</span><span class="sxs-lookup"><span data-stu-id="206f9-122">The default value for this property is **Read Write**.</span></span>  
  
 <span data-ttu-id="206f9-123">Nella tabella seguente sono descritti i quattro valori disponibili per la proprietà Mode.</span><span class="sxs-lookup"><span data-stu-id="206f9-123">The Mode option has four values, as described in the following table.</span></span>  
  
|<span data-ttu-id="206f9-124">Valore</span><span class="sxs-lookup"><span data-stu-id="206f9-124">Value</span></span>|<span data-ttu-id="206f9-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="206f9-125">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="206f9-126">**Sola lettura**</span><span class="sxs-lookup"><span data-stu-id="206f9-126">**Read Only**</span></span>|<span data-ttu-id="206f9-127">Imposta l'accesso di sola lettura al database.</span><span class="sxs-lookup"><span data-stu-id="206f9-127">Specifies read-only access to the database.</span></span>|  
|<span data-ttu-id="206f9-128">**Lettura/scrittura**</span><span class="sxs-lookup"><span data-stu-id="206f9-128">**Read Write**</span></span>|<span data-ttu-id="206f9-129">Imposta l'autorizzazione di lettura/scrittura per il database.</span><span class="sxs-lookup"><span data-stu-id="206f9-129">Specifies read/write permission to the database.</span></span>|  
|<span data-ttu-id="206f9-130">**Exclusive**</span><span class="sxs-lookup"><span data-stu-id="206f9-130">**Exclusive**</span></span>|<span data-ttu-id="206f9-131">Imposta l'accesso esclusivo al database.</span><span class="sxs-lookup"><span data-stu-id="206f9-131">Specifies exclusive access to the database.</span></span>|  
|<span data-ttu-id="206f9-132">**Shared Read**</span><span class="sxs-lookup"><span data-stu-id="206f9-132">**Shared Read**</span></span>|<span data-ttu-id="206f9-133">Specifica che altri utenti possono accedere contemporaneamente in lettura al database.</span><span class="sxs-lookup"><span data-stu-id="206f9-133">Specifies that other users can read from the database at the same time.</span></span>|  
  
 <span data-ttu-id="206f9-134">**Persist Security Info**</span><span class="sxs-lookup"><span data-stu-id="206f9-134">**Persist Security Info**</span></span>  
 <span data-ttu-id="206f9-135">Consente di specificare se le informazioni di sicurezza vengono restituite all'interno della stringa di connessione.</span><span class="sxs-lookup"><span data-stu-id="206f9-135">Specify whether security information is returned as part of the connection string.</span></span> <span data-ttu-id="206f9-136">Il valore predefinito dell'opzione è **False**.</span><span class="sxs-lookup"><span data-stu-id="206f9-136">The default value for this option is **False**.</span></span>  
  
 <span data-ttu-id="206f9-137">**Temp File Directory**</span><span class="sxs-lookup"><span data-stu-id="206f9-137">**Temp File Directory**</span></span>  
 <span data-ttu-id="206f9-138">Consente di specificare il percorso del file di database temporaneo di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact.</span><span class="sxs-lookup"><span data-stu-id="206f9-138">Specify the location of the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact temporary database file.</span></span>  
  
 <span data-ttu-id="206f9-139">**Origine dati**</span><span class="sxs-lookup"><span data-stu-id="206f9-139">**Data Source**</span></span>  
 <span data-ttu-id="206f9-140">Consente di specificare il nome del database di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact.</span><span class="sxs-lookup"><span data-stu-id="206f9-140">Specify the name of the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact database.</span></span>  
  
 <span data-ttu-id="206f9-141">**Password**</span><span class="sxs-lookup"><span data-stu-id="206f9-141">**Password**</span></span>  
 <span data-ttu-id="206f9-142">Consente di immettere la password per il database di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact.</span><span class="sxs-lookup"><span data-stu-id="206f9-142">Enter the password for the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="206f9-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="206f9-143">See Also</span></span>  
 <span data-ttu-id="206f9-144">[Guida di riferimento ai messaggi e agli errori di Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="206f9-144">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="206f9-145">Editor gestione connessione SQL Server Compact Edition &#40;pagina Connessione&#41;</span><span class="sxs-lookup"><span data-stu-id="206f9-145">SQL Server Compact Edition Connection Manager Editor &#40;Connection Page&#41;</span></span>](../../2014/integration-services/sql-server-compact-edition-connection-manager-editor-connection-page.md)  
  
  
