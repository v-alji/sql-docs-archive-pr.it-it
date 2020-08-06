---
title: Installare gli aggiornamenti di manutenzione di SQL Server 2014 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
ms.assetid: 7d6c962b-c8d0-49f7-a2ac-00ad8dca930a
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ace0fd187386d9a9d96e82f61d1efaa254f08c6c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713435"
---
# <a name="install-sql-server-2014-servicing-updates"></a><span data-ttu-id="87703-102">Installare gli aggiornamenti dei servizi di SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="87703-102">Install SQL Server 2014 Servicing Updates</span></span>
  <span data-ttu-id="87703-103">In questo argomento vengono fornite informazioni sull'installazione degli aggiornamenti per [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="87703-103">This topic provides information about installing updates for [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="87703-104">In questa sezione vengono fornite informazioni sui seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="87703-104">This section provides information about the following:</span></span>  
  
-   <span data-ttu-id="87703-105">Installazione di aggiornamenti per [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] durante una nuova installazione</span><span class="sxs-lookup"><span data-stu-id="87703-105">Installing updates for [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] during a new installation</span></span>  
  
-   <span data-ttu-id="87703-106">Installazione di aggiornamenti per [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] dopo che è stato installato.</span><span class="sxs-lookup"><span data-stu-id="87703-106">Installing updates for [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] after it has already been installed.</span></span>  
  
 <span data-ttu-id="87703-107">Si consiglia agli clienti di valutare e installare tempestivamente gli ultimi aggiornamenti di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per assicurarsi che i sistemi dispongano degli aggiornamenti di sicurezza più recenti.</span><span class="sxs-lookup"><span data-stu-id="87703-107">We recommend that customers evaluate and install latest [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] updates in a timely manner to make sure that systems are up-to-date with the most recent security updates.</span></span>  
  
## <a name="installing-updates-for-sscurrent-during-a-new-installation"></a><span data-ttu-id="87703-108">Installazione di aggiornamenti per [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] durante una nuova installazione</span><span class="sxs-lookup"><span data-stu-id="87703-108">Installing Updates for [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] During a New Installation</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="87703-109">Il programma di installazione integra gli aggiornamenti più recenti del pacchetto con l'installazione del prodotto principale in modo che quest'ultimo e i relativi aggiornamenti applicabili vengano installati contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="87703-109">setup integrates the latest product updates with the main product installation so that the main product and its applicable updates are installed at the same time.</span></span> <span data-ttu-id="87703-110">Aggiornamento prodotto consente la ricerca degli aggiornamenti applicabili da:</span><span class="sxs-lookup"><span data-stu-id="87703-110">Product Update can search for the applicable updates from:</span></span>  
  
-   [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="87703-111">Update</span><span class="sxs-lookup"><span data-stu-id="87703-111">Update</span></span>  
  
-   <span data-ttu-id="87703-112">Windows Server Update Services (WSUS)</span><span class="sxs-lookup"><span data-stu-id="87703-112">Windows Server Update Services (WSUS)</span></span>  
  
-   <span data-ttu-id="87703-113">Cartella locale</span><span class="sxs-lookup"><span data-stu-id="87703-113">A local folder</span></span>  
  
-   <span data-ttu-id="87703-114">Condivisione di rete</span><span class="sxs-lookup"><span data-stu-id="87703-114">A network share</span></span>  
  
 <span data-ttu-id="87703-115">Dopo avere individuato le versioni più recenti degli aggiornamenti applicabili, questi vengono scaricati e integrati dal programma di installazione con il processo di installazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] corrente.</span><span class="sxs-lookup"><span data-stu-id="87703-115">After Setup finds the latest versions of the applicable updates, it downloads and integrates them with the current [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] setup process.</span></span> <span data-ttu-id="87703-116">Tramite l'aggiornamento del prodotto è possibile includere un aggiornamento cumulativo, un Service Pack o un Service Pack con aggiornamento cumulativo.</span><span class="sxs-lookup"><span data-stu-id="87703-116">Product Update can include a cumulative update, service pack, or service pack plus cumulative update.</span></span> <span data-ttu-id="87703-117">La funzionalità di aggiornamento del prodotto è un'estensione della [funzionalità](https://go.microsoft.com/fwlink/?LinkId=219945) di integrazione disponibile in [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] PCU1.</span><span class="sxs-lookup"><span data-stu-id="87703-117">Product Update functionality is an extension of the [Slipstream Functionality](https://go.microsoft.com/fwlink/?LinkId=219945) that was available in [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] PCU1.</span></span>  
  
## <a name="installing-updates-for-sscurrent-after-it-has-already-been-installed"></a><span data-ttu-id="87703-118">Installazione di aggiornamenti per [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] dopo che è stato installato</span><span class="sxs-lookup"><span data-stu-id="87703-118">Installing Updates for [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] after it has already been installed</span></span>  
 <span data-ttu-id="87703-119">In un'istanza installata di si [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] consiglia di applicare tutti gli aggiornamenti disponibili, ovvero le versioni di distribuzione generale (GDR-Security/Critical Update), i Service Pack (SP) e l'ultimo aggiornamento cumulativo disponibile (Cu).</span><span class="sxs-lookup"><span data-stu-id="87703-119">On an installed instance of [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], we recommend that you apply all available updates: General Distribution Releases (GDR - security/critical updates), Service Packs (SP), as well as the latest available Cumulative Update (CU).</span></span>  
  
 <span data-ttu-id="87703-120">A seconda del tipo di versione del servizio, SQL Server aggiornamenti sono disponibili tramite Microsoft Update (MU), l'area download Microsoft e/o il server hotfix del servizio supporto tecnico clienti.</span><span class="sxs-lookup"><span data-stu-id="87703-120">Depending on the type of servicing release, SQL Server updates are available via Microsoft Update (MU), the Microsoft Download Center, and/or the Customer Support Services hotfix Server.</span></span> <span data-ttu-id="87703-121">Gli aggiornamenti della sicurezza e critici per SQL Server vengono forniti automaticamente da Microsoft Update (per poter visualizzare questi aggiornamenti, è necessario acconsentire esplicitamente a MU tramite Windows Update nel pannello di controllo).</span><span class="sxs-lookup"><span data-stu-id="87703-121">Security and Critical updates for SQL Server are automatically provided by Microsoft Update (to be able to see these updates you need to opt-in to MU through Windows Update in Control panel).</span></span> <span data-ttu-id="87703-122">I Service Pack sono disponibili in MU come download facoltativi/importanti, oltre che nell'area download.</span><span class="sxs-lookup"><span data-stu-id="87703-122">Service Packs are available on MU as Optional/Important downloads as well as the Download Center.</span></span> <span data-ttu-id="87703-123">Gli aggiornamenti cumulativi sono disponibili nel server di download degli hotfix Microsoft fornito negli articoli della Knowledge base.</span><span class="sxs-lookup"><span data-stu-id="87703-123">Cumulative updates are available on the Microsoft hotfix download server provided in CU Knowledge Base articles.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87703-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="87703-124">See Also</span></span>  
 <span data-ttu-id="87703-125">[Installare SQL Server 2014 dall'installazione guidata &#40;&#41;](install-sql-server-from-the-installation-wizard-setup.md) </span><span class="sxs-lookup"><span data-stu-id="87703-125">[Install SQL Server 2014 from the Installation Wizard &#40;Setup&#41;](install-sql-server-from-the-installation-wizard-setup.md) </span></span>  
 <span data-ttu-id="87703-126">L' [installazione di aggiornamenti dal prompt dei comandi](installing-updates-from-the-command-prompt.md) [consente di aggiungere funzionalità a un'istanza di SQL Server 2014 &#40;di installazione&#41;](add-features-to-an-instance-of-sql-server-setup.md) </span><span class="sxs-lookup"><span data-stu-id="87703-126">[Installing updates from the command prompt](installing-updates-from-the-command-prompt.md) [Add Features to an Instance of SQL Server 2014 &#40;Setup&#41;](add-features-to-an-instance-of-sql-server-setup.md) </span></span>  
 [<span data-ttu-id="87703-127">Rimuovere un'installazione di SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="87703-127">Drop a SQL Server 2014 Installation</span></span>](repair-a-failed-sql-server-installation.md)  
  
  
