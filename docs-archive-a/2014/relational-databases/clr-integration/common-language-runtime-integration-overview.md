---
title: Panoramica dell'integrazione con CLR (Common Language Runtime) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- managed code [SQL Server]
- common language runtime [SQL Server], about CLR integration
- cross-language integration
- integrating CLR [SQL Server]
- .NET Framework [SQL Server], common language runtime
- code access security [CLR integration]
- managed code [SQL Server], CLR integration
ms.assetid: 7be9e644-36a2-48fc-9206-faf59fdff4d7
author: rothja
ms.author: jroth
ms.openlocfilehash: 25345fd39fb8a77f62e4e352b75629a98cb9d7af
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627825"
---
# <a name="common-language-runtime-clr-integration-overview"></a><span data-ttu-id="34834-102">Panoramica dell'integrazione con CLR (Common Language Runtime)</span><span class="sxs-lookup"><span data-stu-id="34834-102">Common Language Runtime (CLR) Integration Overview</span></span>
  [!INCLUDE[msCoName](../../../includes/msconame-md.md)]<span data-ttu-id="34834-103">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]include ora l'integrazione del componente Common Language Runtime (CLR) del .NET Framework per [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="34834-103">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] now features the integration of the common language runtime (CLR) component of the .NET Framework for [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows.</span></span> <span data-ttu-id="34834-104">CLR fornisce codice gestito con servizi quali l'integrazione tra linguaggi diversi, la sicurezza da accesso di codice, la gestione della durata degli oggetti e il supporto per il debug e il profiling.</span><span class="sxs-lookup"><span data-stu-id="34834-104">The CLR supplies managed code with services such as cross-language integration, code access security, object lifetime management, and debugging and profiling support.</span></span> <span data-ttu-id="34834-105">Grazie all'integrazione con Common Language Runtime, gli sviluppatori di applicazioni e gli utenti di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] hanno ora la possibilità di scrivere stored procedure, trigger, tipi definiti dall'utente, funzioni definite dall'utente (scalari e con valori di tabella) e funzioni di aggregazione definite dall'utente utilizzando qualsiasi linguaggio di .NET Framework, inclusi [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic .NET e [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual C#.</span><span class="sxs-lookup"><span data-stu-id="34834-105">For [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] users and application developers, CLR integration means that you can now write stored procedures, triggers, user-defined types, user-defined functions (scalar and table-valued), and user-defined aggregate functions using any .NET Framework language, including [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic .NET and [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual C#.</span></span> [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="34834-106">include la versione preinstallata di 4 di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="34834-106">includes the .NET Framework version 4 pre-installed.</span></span>  
  
 <span data-ttu-id="34834-107">I vantaggi principali di questa integrazione sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="34834-107">Among the major benefits of this integration are:</span></span>  
  
-   <span data-ttu-id="34834-108">**Un modello di programmazione migliore.**</span><span class="sxs-lookup"><span data-stu-id="34834-108">**A better programming model.**</span></span> <span data-ttu-id="34834-109">I linguaggi .NET Framework sono sotto molti aspetti più completi di Transact-SQL, in quanto offrono costrutti e funzionalità precedentemente non disponibili per gli sviluppatori di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="34834-109">The .NET Framework languages are in many respects richer than Transact-SQL, offering constructs and capabilities previously not available to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] developers.</span></span> <span data-ttu-id="34834-110">È possibile inoltre sfruttare la potenza della libreria .NET Framework che fornisce una vasta gamma di classi, utilizzabili in modo rapido ed efficiente per risolvere i problemi di programmazione.</span><span class="sxs-lookup"><span data-stu-id="34834-110">Developers may also leverage the power of the .NET Framework Library, which provides an extensive set of classes that can be used to quickly and efficiently solve programming problems.</span></span>  
  
-   <span data-ttu-id="34834-111">**Miglioramento della sicurezza e della protezione.**</span><span class="sxs-lookup"><span data-stu-id="34834-111">**Improved safety and security.**</span></span> <span data-ttu-id="34834-112">Il codice gestito è in esecuzione in un ambiente CLR, ospitato dal motore di database.</span><span class="sxs-lookup"><span data-stu-id="34834-112">Managed code runs in a common language run-time environment, hosted by the Database Engine.</span></span> [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="34834-113">lo utilizza per fornire un'alternativa più sicura alle stored procedure estese disponibili in versioni precedenti di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="34834-113">leverages this to provide a safer and more secure alternative to the extended stored procedures available in earlier versions of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="34834-114">**Possibilità di definire tipi di dati e funzioni di aggregazione.**</span><span class="sxs-lookup"><span data-stu-id="34834-114">**Ability to define data types and aggregate functions.**</span></span> <span data-ttu-id="34834-115">I tipi definiti dall'utente e le funzioni di aggregazione definite dall'utente sono due nuovi oggetti di database gestiti che espandono le capacità di archiviazione ed esecuzione di query di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="34834-115">User defined types and user defined aggregates are two new managed database objects which expand the storage and querying capabilities of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="34834-116">**Sviluppo semplificato attraverso un ambiente standardizzato.**</span><span class="sxs-lookup"><span data-stu-id="34834-116">**Streamlined development through a standardized environment.**</span></span> <span data-ttu-id="34834-117">Lo sviluppo di database è integrato nelle versioni future dell'ambiente di sviluppo di [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Studio .NET.</span><span class="sxs-lookup"><span data-stu-id="34834-117">Database development is integrated into future releases of the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Studio .NET development environment.</span></span> <span data-ttu-id="34834-118">Gli sviluppatori utilizzano per lo sviluppo e il debug degli script e degli oggetti di database gli stessi strumenti impiegati per scrivere componenti e servizi .NET Framework di livello intermedio o di livello client.</span><span class="sxs-lookup"><span data-stu-id="34834-118">Developers use the same tools for developing and debugging database objects and scripts as they use to write middle-tier or client-tier .NET Framework components and services.</span></span>  
  
-   <span data-ttu-id="34834-119">**Possibilità di prestazioni e scalabilità migliori.**</span><span class="sxs-lookup"><span data-stu-id="34834-119">**Potential for improved performance and scalability.**</span></span> <span data-ttu-id="34834-120">In molte situazioni, i modelli di compilazione ed esecuzione del linguaggio .NET Framework consentono di ottenere prestazioni migliori rispetto a Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="34834-120">In many situations, the .NET Framework language compilation and execution models deliver improved performance over Transact-SQL.</span></span>  
  
 <span data-ttu-id="34834-121">Nella tabella seguente sono elencati gli argomenti inclusi in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="34834-121">This following table lists the topics in this section.</span></span>  
  
 [<span data-ttu-id="34834-122">Panoramica dell'integrazione con CLR</span><span class="sxs-lookup"><span data-stu-id="34834-122">Overview of CLR Integration</span></span>](clr-integration-overview.md)  
 <span data-ttu-id="34834-123">Vengono descritti i tipi di oggetti che è possibile compilare utilizzando l'integrazione con CLR e vengono esaminati i requisiti per la compilazione di oggetti di database tramite questa integrazione.</span><span class="sxs-lookup"><span data-stu-id="34834-123">Describes the kinds of objects that can be built using CLR integration, and reviews the requirements for building database objects using CLR integration.</span></span>  
  
 [<span data-ttu-id="34834-124">Novità dell'integrazione con CLR</span><span class="sxs-lookup"><span data-stu-id="34834-124">What's New in CLR Integration</span></span>](clr-integration-what-s-new.md)  
 <span data-ttu-id="34834-125">Vengono descritte le nuove caratteristiche di questa versione.</span><span class="sxs-lookup"><span data-stu-id="34834-125">Describes the new features in this release.</span></span>  
  
 [<span data-ttu-id="34834-126">Architettura dell'integrazione con CLR</span><span class="sxs-lookup"><span data-stu-id="34834-126">Architecture of CLR Integration</span></span>](../../database-engine/dev-guide/architecture-of-clr-integration.md)  
 <span data-ttu-id="34834-127">Vengono illustrati gli obiettivi di progettazione dell'integrazione con CLR.</span><span class="sxs-lookup"><span data-stu-id="34834-127">Describes the design goals of CLR integration.</span></span>  
  
 [<span data-ttu-id="34834-128">Abilitazione dell'integrazione con CLR</span><span class="sxs-lookup"><span data-stu-id="34834-128">Enabling CLR Integration</span></span>](clr-integration-enabling.md)  
 <span data-ttu-id="34834-129">Viene illustrato come abilitare l'integrazione con CLR.</span><span class="sxs-lookup"><span data-stu-id="34834-129">Describes how to enable CLR integration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34834-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="34834-130">See Also</span></span>  
 <span data-ttu-id="34834-131">[Installazione del .NET Framework](https://technet.microsoft.com/library/ms166014\(v=SQL.105\).aspx) </span><span class="sxs-lookup"><span data-stu-id="34834-131">[Installing the .NET Framework](https://technet.microsoft.com/library/ms166014\(v=SQL.105\).aspx) </span></span>  
 [<span data-ttu-id="34834-132">Prestazioni dell'integrazione con CLR</span><span class="sxs-lookup"><span data-stu-id="34834-132">Performance of CLR Integration</span></span>](clr-integration-architecture-performance.md)  
  
  
