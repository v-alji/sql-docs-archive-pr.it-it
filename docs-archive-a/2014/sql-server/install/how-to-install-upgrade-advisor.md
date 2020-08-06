---
title: 'Procedura: installazione di preparazione aggiornamento | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- installing Upgrade Advisor
- Setup [Upgrade Advisor]
- SQL Server Upgrade Advisor, installing
- Upgrade Advisor [SQL Server], installing
ms.assetid: 481b0704-ce79-4543-b141-67306128aa2b
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 3ed5b66522126bfabc94bfa8036ec6c31ac04500
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637056"
---
# <a name="how-to-install-upgrade-advisor"></a><span data-ttu-id="54e0a-102">Procedura: Installazione di Preparazione aggiornamento</span><span class="sxs-lookup"><span data-stu-id="54e0a-102">How to: Install Upgrade Advisor</span></span>
  <span data-ttu-id="54e0a-103">Preparazione aggiornamento supporta l'analisi remota di tutti i componenti supportati, ad eccezione di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="54e0a-103">Upgrade Advisor supports remote analysis of all supported components except [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="54e0a-104">Se non si prevede di analizzare le istanze di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], è possibile installare Preparazione aggiornamento in qualsiasi computer in grado di connettersi all'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="54e0a-104">If you are not scanning instances of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], you can install Upgrade Advisor on any computer that can connect to your instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="54e0a-105">e che soddisfi i prerequisiti di Preparazione aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="54e0a-105">The computer must also meet Upgrade Advisor prerequisites.</span></span> <span data-ttu-id="54e0a-106">Se si prevede di analizzare le istanze di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], è necessario installare Preparazione aggiornamento nel server di report.</span><span class="sxs-lookup"><span data-stu-id="54e0a-106">If you are scanning instances of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], you must install Upgrade Advisor on the report server.</span></span>  
  
 <span data-ttu-id="54e0a-107">Per ulteriori informazioni, vedere [installazione di preparazione aggiornamento](../../../2014/sql-server/install/installing-upgrade-advisor.md).</span><span class="sxs-lookup"><span data-stu-id="54e0a-107">For more information, see [Installing Upgrade Advisor](../../../2014/sql-server/install/installing-upgrade-advisor.md).</span></span>  
  
### <a name="to-install-upgrade-advisor"></a><span data-ttu-id="54e0a-108">Per installare Preparazione aggiornamento</span><span class="sxs-lookup"><span data-stu-id="54e0a-108">To install Upgrade Advisor</span></span>  
  
1.  <span data-ttu-id="54e0a-109">Avviare l'installazione utilizzando uno dei metodi seguenti:</span><span class="sxs-lookup"><span data-stu-id="54e0a-109">Start the installation using one of the following methods:</span></span>  
  
    -   <span data-ttu-id="54e0a-110">Se si sta eseguendo l'installazione dal [!INCLUDE[msCoName](../../includes/msconame-md.md)] sito Web, fare clic sul collegamento **download** , quindi fare clic sul pulsante **Esegui** per avviare l'installazione.</span><span class="sxs-lookup"><span data-stu-id="54e0a-110">If you are installing from the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Web site, click the **Download** link and then click the **Run** button to start the installation.</span></span>  
  
    -   <span data-ttu-id="54e0a-111">Se si sta eseguendo l'installazione dal supporto del prodotto, aprire la cartella **Redist** , aprire la cartella **Preparazione aggiornamento** , quindi fare doppio clic su **SQLUA.msi**.</span><span class="sxs-lookup"><span data-stu-id="54e0a-111">If you are installing from the product media, open the **redist** folder, open the **Upgrade Advisor** folder, and then double-click **SQLUA.msi**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="54e0a-112">Preparazione aggiornamento richiede [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="54e0a-112">Upgrade Advisor requires the [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework 4.</span></span> <span data-ttu-id="54e0a-113">Se non è installato, o se si dispone di una versione non definitiva, verrà visualizzato un messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="54e0a-113">If it is not installed, or if you have a pre-release version, an error message will appear.</span></span> <span data-ttu-id="54e0a-114">Disinstallare qualsiasi versione precedente di [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], quindi installare la versione più recente di .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="54e0a-114">Uninstall any earlier version of the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] and then install the latest version of .NET Framework 4.</span></span>  
    >   
    >  <span data-ttu-id="54e0a-115">[!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[tsql](../../includes/tsql-md.md)] ScriptDom è un prerequisito per l'installazione [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] di preparazione aggiornamento e non viene installato tramite l'installazione di preparazione aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="54e0a-115">The [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[tsql](../../includes/tsql-md.md)] ScriptDom is a prerequisite for installing [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Upgrade Advisor, and is not installed by Upgrade Advisor Setup.</span></span> <span data-ttu-id="54e0a-116">Per il programma di installazione è necessario scaricare e installare [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[tsql](../../includes/tsql-md.md)] ScriptDom dal [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Feature Pack.</span><span class="sxs-lookup"><span data-stu-id="54e0a-116">The Setup requires you to download and install the [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[tsql](../../includes/tsql-md.md)] ScriptDom from the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Feature Pack.</span></span>  
  
2.  <span data-ttu-id="54e0a-117">Nella pagina \*\* [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] installazione di preparazione aggiornamento\*\* , fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="54e0a-117">On the **Welcome to the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Upgrade Advisor Setup** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="54e0a-118">Nella pagina **contratto di licenza** leggere il contratto di licenza.</span><span class="sxs-lookup"><span data-stu-id="54e0a-118">On the **License Agreement** page, read the license agreement.</span></span> <span data-ttu-id="54e0a-119">Se si accettano le condizioni, selezionare Accetto **il contratto di licenza** e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="54e0a-119">If you agree, select **I accept the license agreement** and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="54e0a-120">Nella pagina **informazioni di registrazione** immettere il nome e la società.</span><span class="sxs-lookup"><span data-stu-id="54e0a-120">On the **Registration Information** page, enter your name and company.</span></span>  
  
5.  <span data-ttu-id="54e0a-121">Nella pagina **Selezione funzionalità** esaminare il valore del **percorso di installazione** .</span><span class="sxs-lookup"><span data-stu-id="54e0a-121">On the **Feature Selection** page, review the **Installation path** value.</span></span> <span data-ttu-id="54e0a-122">Se necessario, utilizzare il pulsante **Sfoglia** per modificare il percorso.</span><span class="sxs-lookup"><span data-stu-id="54e0a-122">If necessary, use the **Browse** button to change the location.</span></span> <span data-ttu-id="54e0a-123">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="54e0a-123">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="54e0a-124">Nella pagina **pronto per l'installazione del programma** fare clic su **Installa** per installare Upgrade Advisor.</span><span class="sxs-lookup"><span data-stu-id="54e0a-124">On the **Ready to Install the Program** page, click **Install** to install Upgrade Advisor.</span></span>  
  
7.  <span data-ttu-id="54e0a-125">Fare clic su **Fine** per uscire dalla procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="54e0a-125">Click **Finish** to exit the wizard.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54e0a-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="54e0a-126">See Also</span></span>  
 [<span data-ttu-id="54e0a-127">Prerequisiti di Preparazione aggiornamento</span><span class="sxs-lookup"><span data-stu-id="54e0a-127">Upgrade Advisor Prerequisites</span></span>](../../../2014/sql-server/install/upgrade-advisor-prerequisites.md)  
  
  
