---
title: Regole funzionalità (aggiornamento) | Microsoft Docs
ms.custom: ''
ms.date: 05/24/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 653b15db-a984-4b4b-b224-81b0285b099b
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 0527c1ba26fed86a6c1a3d3a2ea7c11b096474f8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635392"
---
# <a name="feature-rules-upgrade"></a><span data-ttu-id="ca95f-102">Regole di funzionalità (aggiornamento)</span><span class="sxs-lookup"><span data-stu-id="ca95f-102">Feature Rules (Upgrade)</span></span>
  <span data-ttu-id="ca95f-103">Prima che l'operazione di installazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] venga completata, viene convalidata la configurazione del computer.</span><span class="sxs-lookup"><span data-stu-id="ca95f-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup validates your computer configuration before the Setup operation completes.</span></span> <span data-ttu-id="ca95f-104">Durante l'installazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], tramite il sistema viene analizzato il computer in cui verrà installato [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e vengono verificate le condizioni che impediscono la corretta operazione di installazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ca95f-104">During [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup, the system scans the computer where [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will be installed and checks for conditions that prevent a successful [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] setup operation.</span></span> <span data-ttu-id="ca95f-105">Prima dell'avvio dell'aggiornamento guidato, vengono recuperate le informazioni sullo stato di ciascun elemento.</span><span class="sxs-lookup"><span data-stu-id="ca95f-105">Before Setup starts the upgrade wizard, it retrieves the status of each item.</span></span> <span data-ttu-id="ca95f-106">Il risultato viene confrontato con i requisiti, quindi vengono fornite indicazioni per la rimozione di eventuali problemi che impediscono di proseguire.</span><span class="sxs-lookup"><span data-stu-id="ca95f-106">It then compares the result with required conditions and provides guidance for removal of blocking issues.</span></span>  
  
 <span data-ttu-id="ca95f-107">Con il controllo della configurazione di sistema viene generato un report con una breve descrizione di ogni regola eseguita, nonché lo stato dell'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="ca95f-107">The system configuration check generates a report which contains a short description for each executed rule, and the execution status.</span></span> <span data-ttu-id="ca95f-108">Il report di controllo della configurazione di sistema si trova nel percorso% ProgramFiles% \\ [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] \120\Setup Bootstrap\LOG \\<YYYYMMDD_HHMM>\\ .</span><span class="sxs-lookup"><span data-stu-id="ca95f-108">The system configuration check report is located at %programfiles%\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\120\Setup Bootstrap\Log\\<YYYYMMDD_HHMM>\\.</span></span>  
  
 <span data-ttu-id="ca95f-109">Prima di eseguire l'operazione di installazione, esaminare i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="ca95f-109">Before you run the setup operation, review the following topics:</span></span>  
  
1.  [<span data-ttu-id="ca95f-110">Requisiti hardware e software per l'installazione di SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="ca95f-110">Hardware and Software Requirements for Installing SQL Server 2014</span></span>](hardware-and-software-requirements-for-installing-sql-server.md)  
  
2.  [<span data-ttu-id="ca95f-111">Funzionalità supportate dalle edizioni di SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="ca95f-111">Features Supported by the Editions of SQL Server 2014</span></span>](../../../2014/getting-started/features-supported-by-the-editions-of-sql-server-2014.md)  
  
3.  [<span data-ttu-id="ca95f-112">Considerazioni sulla sicurezza per un'installazione di SQL Server</span><span class="sxs-lookup"><span data-stu-id="ca95f-112">Security Considerations for a SQL Server Installation</span></span>](../../../2014/sql-server/install/security-considerations-for-a-sql-server-installation.md)  
  
4.  [<span data-ttu-id="ca95f-113">Versioni in lingua locale di SQL Server</span><span class="sxs-lookup"><span data-stu-id="ca95f-113">Local Language Versions in SQL Server</span></span>](../../../2014/sql-server/install/local-language-versions-in-sql-server.md)  
  
 <span data-ttu-id="ca95f-114">Altri riferimenti:</span><span class="sxs-lookup"><span data-stu-id="ca95f-114">Other references:</span></span>  
  
1.  [<span data-ttu-id="ca95f-115">Aggiornamenti di versione ed edizione supportati</span><span class="sxs-lookup"><span data-stu-id="ca95f-115">Supported Version and Edition Upgrades</span></span>](../../database-engine/install-windows/supported-version-and-edition-upgrades.md)  
  
2.  [<span data-ttu-id="ca95f-116">Operazioni preliminari all'installazione del clustering di failover</span><span class="sxs-lookup"><span data-stu-id="ca95f-116">Before Installing Failover Clustering</span></span>](../failover-clusters/install/before-installing-failover-clustering.md)  
  
## <a name="see-also"></a><span data-ttu-id="ca95f-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ca95f-117">See Also</span></span>  
 [<span data-ttu-id="ca95f-118">Regole di installazione</span><span class="sxs-lookup"><span data-stu-id="ca95f-118">Install Rules</span></span>](../../../2014/sql-server/install/install-rules.md)  
  
  
