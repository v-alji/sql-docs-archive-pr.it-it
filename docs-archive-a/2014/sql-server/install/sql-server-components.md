---
title: Componenti SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Upgrade Advisor, components
- listing components to analyze
- Upgrade Advisor [SQL Server], components
- component analysis [Upgrade Advisor]
- finding components to analyze
- locating components to analyze
- detecting components to analyze
- server names [Upgrade Advisor]
- analyzing system [Upgrade Advisor], component list
- identifying components to analyze
ms.assetid: 539b9525-ce3f-4950-9146-5527a5a297ee
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 95fe39ce8e616b238cf7c70763e7cf1819341f16
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726460"
---
# <a name="sql-server-components"></a><span data-ttu-id="dfa1d-102">Componenti di SQL Server</span><span class="sxs-lookup"><span data-stu-id="dfa1d-102">SQL Server Components</span></span>
  <span data-ttu-id="dfa1d-103">È possibile eseguire l'analisi guidata di preparazione aggiornamento in un computer locale o remoto in cui è [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] installato,, [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)] o [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="dfa1d-103">You can run the Upgrade Advisor Analysis Wizard against a local or remote computer that has [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], or [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] installed.</span></span> <span data-ttu-id="dfa1d-104">Il primo passaggio dell'analisi di pre-aggiornamento consiste nell'identificare il computer e i componenti per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="dfa1d-104">The first step in the pre-upgrade analysis is to identify the computer and components for analysis.</span></span>  
  
## <a name="options"></a><span data-ttu-id="dfa1d-105">Opzioni</span><span class="sxs-lookup"><span data-stu-id="dfa1d-105">Options</span></span>  
 <span data-ttu-id="dfa1d-106">**Nome computer**</span><span class="sxs-lookup"><span data-stu-id="dfa1d-106">**Computer name**</span></span>  
 <span data-ttu-id="dfa1d-107">Specifica il nome del computer da analizzare,</span><span class="sxs-lookup"><span data-stu-id="dfa1d-107">Specifies the name of the computer to analyze.</span></span> <span data-ttu-id="dfa1d-108">Preparazione aggiornamento compila la casella **nome server** con il nome del computer locale.</span><span class="sxs-lookup"><span data-stu-id="dfa1d-108">Upgrade Advisor populates the **Server name** box with the local computer name.</span></span> <span data-ttu-id="dfa1d-109">È anche possibile utilizzare "." e "localhost" per connettersi al computer locale.</span><span class="sxs-lookup"><span data-stu-id="dfa1d-109">You can also use "." and "localhost" to connect to the local computer.</span></span>  
  
 <span data-ttu-id="dfa1d-110">Per analizzare un computer diverso, utilizzare le linee guida seguenti:</span><span class="sxs-lookup"><span data-stu-id="dfa1d-110">To analyze a different computer, use the following guidelines:</span></span>  
  
-   <span data-ttu-id="dfa1d-111">Per analizzare le istanze non cluster, immettere il nome del computer.</span><span class="sxs-lookup"><span data-stu-id="dfa1d-111">To scan nonclustered instances, enter the computer name.</span></span>  
  
-   <span data-ttu-id="dfa1d-112">Per analizzare istanze cluster, immettere il nome dell'istanza del cluster di failover di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dfa1d-112">To scan clustered instances, enter the name of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster instance.</span></span>  
  
-   <span data-ttu-id="dfa1d-113">Per analizzare i componenti non cluster installati in un nodo di un cluster, immettere il nome del computer del nodo del cluster di failover.</span><span class="sxs-lookup"><span data-stu-id="dfa1d-113">To scan nonclustered components that are installed on a node of a cluster, enter the computer name of the failover cluster node.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="dfa1d-114">Non includere il nome dell'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dfa1d-114">Do not include the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance name.</span></span>  
  
 <span data-ttu-id="dfa1d-115">Anziché il nome del computer, è possibile specificare l'indirizzo IP.</span><span class="sxs-lookup"><span data-stu-id="dfa1d-115">Instead of specifying the computer name, you can specify the IP address.</span></span>  
  
 <span data-ttu-id="dfa1d-116">Se si analizza [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], è necessario specificare il nome del computer locale.</span><span class="sxs-lookup"><span data-stu-id="dfa1d-116">If scanning [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], you must specify the name of the local computer.</span></span> <span data-ttu-id="dfa1d-117">Con Preparazione aggiornamento vengono analizzati solo i server di report locali.</span><span class="sxs-lookup"><span data-stu-id="dfa1d-117">Upgrade Advisor scans local report servers only.</span></span>  
  
 <span data-ttu-id="dfa1d-118">**Detect**</span><span class="sxs-lookup"><span data-stu-id="dfa1d-118">**Detect**</span></span>  
 <span data-ttu-id="dfa1d-119">Il pulsante **rileva** accede al computer specificato e rileva i componenti da analizzare:</span><span class="sxs-lookup"><span data-stu-id="dfa1d-119">The **Detect** button accesses the specified computer and detects components to analyze:</span></span>  
  
-   <span data-ttu-id="dfa1d-120">Se si analizza un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in un computer remoto, è necessario abilitare i servizi del Registro di sistema nel computer remoto.</span><span class="sxs-lookup"><span data-stu-id="dfa1d-120">If you are analyzing a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance on a remote computer, you must enable the remote registry services on the remote computer.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="dfa1d-121">viene rilevato se nel Registro di sistema del computer viene individuata un'istanza di [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)] o [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dfa1d-121">is detected if an instance of [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], or [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] is found in the computer's registry.</span></span>  
  
-   [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="dfa1d-122">viene rilevato se nel Registro di sistema del computer viene individuata un'istanza di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dfa1d-122">is detected if an instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] is found in the computer's registry.</span></span>  
  
-   [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="dfa1d-123">viene rilevato se nel Registro di sistema del computer viene individuato [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dfa1d-123">is detected if [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] is found in the computer's registry.</span></span> <span data-ttu-id="dfa1d-124">Tuttavia, con Preparazione aggiornamento vengono analizzati solo i server di report locali.</span><span class="sxs-lookup"><span data-stu-id="dfa1d-124">However, Upgrade Advisor scans local report servers only.</span></span>  
  
 <span data-ttu-id="dfa1d-125">**Componenti**</span><span class="sxs-lookup"><span data-stu-id="dfa1d-125">**Components**</span></span>  
 <span data-ttu-id="dfa1d-126">Selezionare i componenti da analizzare.</span><span class="sxs-lookup"><span data-stu-id="dfa1d-126">Select the components to analyze.</span></span> <span data-ttu-id="dfa1d-127">È possibile fare clic sul pulsante **rileva** per selezionare tutti i componenti installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="dfa1d-127">You can click the **Detect** button to select all the components installed on the computer.</span></span> <span data-ttu-id="dfa1d-128">Accanto ai componenti rilevati come installati nel computer verrà visualizzato un segno di spunta.</span><span class="sxs-lookup"><span data-stu-id="dfa1d-128">A check mark will appear next to the components that are detected as installed on the computer.</span></span> <span data-ttu-id="dfa1d-129">È anche possibile selezionare manualmente i componenti da analizzare selezionando o deselezionando la casella di controllo corrispondente.</span><span class="sxs-lookup"><span data-stu-id="dfa1d-129">You can also manually select the components to analyze by selecting or clearing the check box next to each component.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfa1d-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dfa1d-130">See Also</span></span>  
 <span data-ttu-id="dfa1d-131">[Utilizzo di preparazione aggiornamento](../../../2014/sql-server/install/working-with-upgrade-advisor.md) </span><span class="sxs-lookup"><span data-stu-id="dfa1d-131">[Working with Upgrade Advisor](../../../2014/sql-server/install/working-with-upgrade-advisor.md) </span></span>  
 [<span data-ttu-id="dfa1d-132">Guida di riferimento all'interfaccia utente di Preparazione aggiornamento</span><span class="sxs-lookup"><span data-stu-id="dfa1d-132">Upgrade Advisor User Interface Reference</span></span>](../../../2014/sql-server/install/upgrade-advisor-user-interface-reference.md)  
  
  
