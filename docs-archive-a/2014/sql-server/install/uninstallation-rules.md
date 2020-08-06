---
title: Regole di disinstallazione | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 07554612-8cb6-4bd9-adde-956177261ccd
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: c2e1c3e2e36177053a43b032dd4721dc503fa20c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628135"
---
# <a name="uninstallation-rules"></a><span data-ttu-id="dca2c-102">Regole di disinstallazione</span><span class="sxs-lookup"><span data-stu-id="dca2c-102">Uninstallation rules</span></span>
  <span data-ttu-id="dca2c-103">La pagina Regole di disinstallazione esegue un set di regole per garantire il completamento dell'operazione di installazione.</span><span class="sxs-lookup"><span data-stu-id="dca2c-103">The Uninstallation Rules page will run a set of rules to ensure that the Setup operation can complete successfully.</span></span>  
  
 <span data-ttu-id="dca2c-104">Prima che l'operazione di installazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] venga completata, viene convalidata la configurazione del computer.</span><span class="sxs-lookup"><span data-stu-id="dca2c-104">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup validates your computer configuration before the Setup operation completes.</span></span> <span data-ttu-id="dca2c-105">Durante l'installazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] viene eseguita l'analisi del computer in cui verrà installato [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tramite Controllo configurazione sistema.</span><span class="sxs-lookup"><span data-stu-id="dca2c-105">During [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup, the System Configuration Checker (SCC) scans the computer where [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will be installed.</span></span> <span data-ttu-id="dca2c-106">Questo strumento consente di verificare le condizioni che impediscono la corretta operazione di installazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="dca2c-106">The SCC checks for conditions that prevent a successful [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] setup operation.</span></span> <span data-ttu-id="dca2c-107">Prima dell'avvio della disinstallazione guidata di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , lo strumento recupera le informazioni sullo stato di ciascun elemento.</span><span class="sxs-lookup"><span data-stu-id="dca2c-107">Before Setup starts the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] uninstallation wizard, the SCC retrieves the status of each item.</span></span> <span data-ttu-id="dca2c-108">Il risultato viene confrontato con i requisiti, quindi vengono fornite indicazioni per la rimozione di eventuali problemi che impediscono di proseguire.</span><span class="sxs-lookup"><span data-stu-id="dca2c-108">It then compares the result with required conditions and provides guidance for removal of blocking issues.</span></span>  
  
 <span data-ttu-id="dca2c-109">Con il controllo della configurazione di sistema viene generato un report con una breve descrizione di ogni regola eseguita, nonché lo stato dell'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="dca2c-109">The system configuration check generates a report which contains a short description for each executed rule, and the execution status.</span></span> <span data-ttu-id="dca2c-110">Il report di controllo della configurazione di sistema si trova nel percorso% ProgramFiles% \\ [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] \120\Setup Bootstrap\LOG \\<YYYYMMDD_HHMM>\\ .</span><span class="sxs-lookup"><span data-stu-id="dca2c-110">The system configuration check report is located at %programfiles%\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\120\Setup Bootstrap\Log\\<YYYYMMDD_HHMM>\\.</span></span>  
  
 <span data-ttu-id="dca2c-111">Prima di eseguire l'operazione di installazione, esaminare i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="dca2c-111">Before you run the setup operation, review the following topics:</span></span>  
  
1.  [<span data-ttu-id="dca2c-112">Requisiti hardware e software per l'installazione di SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="dca2c-112">Hardware and Software Requirements for Installing SQL Server 2014</span></span>](hardware-and-software-requirements-for-installing-sql-server.md)  
  
2.  [<span data-ttu-id="dca2c-113">Funzionalità supportate dalle edizioni di SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="dca2c-113">Features Supported by the Editions of SQL Server 2014</span></span>](../../../2014/getting-started/features-supported-by-the-editions-of-sql-server-2014.md)  
  
3.  [<span data-ttu-id="dca2c-114">Considerazioni sulla sicurezza per un'installazione di SQL Server</span><span class="sxs-lookup"><span data-stu-id="dca2c-114">Security Considerations for a SQL Server Installation</span></span>](../../../2014/sql-server/install/security-considerations-for-a-sql-server-installation.md)  
  
4.  [<span data-ttu-id="dca2c-115">Versioni in lingua locale di SQL Server</span><span class="sxs-lookup"><span data-stu-id="dca2c-115">Local Language Versions in SQL Server</span></span>](../../../2014/sql-server/install/local-language-versions-in-sql-server.md)  
  
 <span data-ttu-id="dca2c-116">Altri riferimenti:</span><span class="sxs-lookup"><span data-stu-id="dca2c-116">Other references:</span></span>  
  
1.  [<span data-ttu-id="dca2c-117">Aggiornamenti di versione ed edizione supportati</span><span class="sxs-lookup"><span data-stu-id="dca2c-117">Supported Version and Edition Upgrades</span></span>](../../database-engine/install-windows/supported-version-and-edition-upgrades.md)  
  
2.  [<span data-ttu-id="dca2c-118">Operazioni preliminari all'installazione del clustering di failover</span><span class="sxs-lookup"><span data-stu-id="dca2c-118">Before Installing Failover Clustering</span></span>](../failover-clusters/install/before-installing-failover-clustering.md)  
  
## <a name="see-also"></a><span data-ttu-id="dca2c-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dca2c-119">See Also</span></span>  
 [<span data-ttu-id="dca2c-120">Regole di installazione</span><span class="sxs-lookup"><span data-stu-id="dca2c-120">Install Rules</span></span>](../../../2014/sql-server/install/install-rules.md)  
  
  
