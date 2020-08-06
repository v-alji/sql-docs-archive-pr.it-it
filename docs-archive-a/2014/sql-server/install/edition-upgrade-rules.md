---
title: Regole di aggiornamento edizione | Microsoft Docs
ms.custom: ''
ms.date: 05/24/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 77c4d751-4fea-4e69-a7c8-ab8fc0dbadb2
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 453944ede41bfc5cf258c6f0946b15b716c6c22c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628183"
---
# <a name="edition-upgrade-rules"></a><span data-ttu-id="2f2fe-102">Regole per l'aggiornamento delle edizioni</span><span class="sxs-lookup"><span data-stu-id="2f2fe-102">Edition Upgrade Rules</span></span>
  <span data-ttu-id="2f2fe-103">Prima che l'operazione di installazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] venga completata, viene convalidata la configurazione del computer.</span><span class="sxs-lookup"><span data-stu-id="2f2fe-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup validates your computer configuration before the Setup operation completes.</span></span> <span data-ttu-id="2f2fe-104">Durante l'installazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] viene eseguita l'analisi del computer in cui verrà installato [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tramite Controllo configurazione sistema.</span><span class="sxs-lookup"><span data-stu-id="2f2fe-104">During [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup, the System Configuration Checker (SCC) scans the computer where [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will be installed.</span></span> <span data-ttu-id="2f2fe-105">Questo strumento consente di verificare le condizioni che impediscono la corretta operazione di installazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2f2fe-105">The SCC checks for conditions that prevent a successful [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] setup operation.</span></span> <span data-ttu-id="2f2fe-106">Prima dell'avvio dell'aggiornamento dell'edizione, lo strumento recupera le informazioni sullo stato di ciascun elemento.</span><span class="sxs-lookup"><span data-stu-id="2f2fe-106">Before Setup starts the edition upgrade, the SCC retrieves the status of each item.</span></span> <span data-ttu-id="2f2fe-107">Il risultato viene confrontato con i requisiti, quindi vengono fornite indicazioni per la rimozione di eventuali problemi che impediscono di proseguire.</span><span class="sxs-lookup"><span data-stu-id="2f2fe-107">It then compares the result with required conditions and provides guidance for removal of blocking issues.</span></span>  
  
 <span data-ttu-id="2f2fe-108">Con il controllo della configurazione di sistema viene generato un report con una breve descrizione di ogni regola eseguita, nonché lo stato dell'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="2f2fe-108">The system configuration check generates a report which contains a short description for each executed rule, and the execution status.</span></span> <span data-ttu-id="2f2fe-109">Il report di controllo della configurazione di sistema si trova nel percorso% ProgramFiles% \\ [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] \120\Setup Bootstrap\LOG \\<YYYYMMDD_HHMM>\\ .</span><span class="sxs-lookup"><span data-stu-id="2f2fe-109">The system configuration check report is located at %programfiles%\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\120\Setup Bootstrap\Log\\<YYYYMMDD_HHMM>\\.</span></span>  
  
 <span data-ttu-id="2f2fe-110">Prima di eseguire l'operazione di installazione, esaminare i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="2f2fe-110">Before you run the setup operation, review the following topics:</span></span>  
  
1.  [<span data-ttu-id="2f2fe-111">Requisiti hardware e software per l'installazione di SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="2f2fe-111">Hardware and Software Requirements for Installing SQL Server 2014</span></span>](hardware-and-software-requirements-for-installing-sql-server.md)  
  
2.  [<span data-ttu-id="2f2fe-112">Funzionalità supportate dalle edizioni di SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="2f2fe-112">Features Supported by the Editions of SQL Server 2014</span></span>](../../../2014/getting-started/features-supported-by-the-editions-of-sql-server-2014.md)  
  
3.  [<span data-ttu-id="2f2fe-113">Considerazioni sulla sicurezza per un'installazione di SQL Server</span><span class="sxs-lookup"><span data-stu-id="2f2fe-113">Security Considerations for a SQL Server Installation</span></span>](../../../2014/sql-server/install/security-considerations-for-a-sql-server-installation.md)  
  
4.  [<span data-ttu-id="2f2fe-114">Versioni in lingua locale di SQL Server</span><span class="sxs-lookup"><span data-stu-id="2f2fe-114">Local Language Versions in SQL Server</span></span>](../../../2014/sql-server/install/local-language-versions-in-sql-server.md)  
  
 <span data-ttu-id="2f2fe-115">Altri riferimenti:</span><span class="sxs-lookup"><span data-stu-id="2f2fe-115">Other references:</span></span>  
  
1.  [<span data-ttu-id="2f2fe-116">Aggiornamenti di versione ed edizione supportati</span><span class="sxs-lookup"><span data-stu-id="2f2fe-116">Supported Version and Edition Upgrades</span></span>](../../database-engine/install-windows/supported-version-and-edition-upgrades.md)  
  
2.  [<span data-ttu-id="2f2fe-117">Operazioni preliminari all'installazione del clustering di failover</span><span class="sxs-lookup"><span data-stu-id="2f2fe-117">Before Installing Failover Clustering</span></span>](../failover-clusters/install/before-installing-failover-clustering.md)  
  
## <a name="see-also"></a><span data-ttu-id="2f2fe-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2f2fe-118">See Also</span></span>  
 [<span data-ttu-id="2f2fe-119">Regole di installazione</span><span class="sxs-lookup"><span data-stu-id="2f2fe-119">Install Rules</span></span>](../../../2014/sql-server/install/install-rules.md)  
  
  
