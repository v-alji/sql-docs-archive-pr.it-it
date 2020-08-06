---
title: Replica di database eterogenei | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- heterogeneous database replication, about heterogeneous database replication
- replication [SQL Server], heterogeneous database replication
- heterogeneous database replication
ms.assetid: 3fd983ad-e206-45db-9054-417c9b5bb815
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d8988a425bc9519d43b8100e4cd34418114edae1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721306"
---
# <a name="heterogeneous-database-replication"></a><span data-ttu-id="1d09e-102">replica di database eterogenei</span><span class="sxs-lookup"><span data-stu-id="1d09e-102">Heterogeneous Database Replication</span></span>
  [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="1d09e-103">supporta gli scenari eterogenei seguenti per la replica transazionale e snapshot:</span><span class="sxs-lookup"><span data-stu-id="1d09e-103">supports the following heterogeneous scenarios for transactional and snapshot replication:</span></span>  
  
-   <span data-ttu-id="1d09e-104">Pubblicazione di dati da Oracle a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1d09e-104">Publishing data from Oracle to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="1d09e-105">Pubblicazione di dati da [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] a Sottoscrittori non[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1d09e-105">Publishing data from [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to non-[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Subscribers.</span></span>  
  
 <span data-ttu-id="1d09e-106">La replica eterogenea a Sottoscrittori non SQL Server è deprecata.</span><span class="sxs-lookup"><span data-stu-id="1d09e-106">Heterogeneous replication to non-SQL Server subscribers is deprecated.</span></span> <span data-ttu-id="1d09e-107">La pubblicazione Oracle è deprecata.</span><span class="sxs-lookup"><span data-stu-id="1d09e-107">Oracle Publishing is deprecated.</span></span> <span data-ttu-id="1d09e-108">Per spostare dati, creare soluzioni utilizzando Change Data Capture e [!INCLUDE[ssIS](../../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1d09e-108">To move data, create solutions using change data capture and [!INCLUDE[ssIS](../../../includes/ssis-md.md)].</span></span>  
  
> [!CAUTION]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../../../includes/ssnotedepfutureavoid-md.md)]  
  
## <a name="publishing-data-from-oracle"></a><span data-ttu-id="1d09e-109">Pubblicazione di dati da Oracle</span><span class="sxs-lookup"><span data-stu-id="1d09e-109">Publishing Data from Oracle</span></span>  
 <span data-ttu-id="1d09e-110">È possibile utilizzare [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] per pubblicare dati di Oracle con le stesse funzionalità e la stessa facilità d'uso della replica snapshot e transazionale di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1d09e-110">You can use [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to publish data from Oracle with most of the same features and ease-of-use as [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] snapshot and transactional replication.</span></span> <span data-ttu-id="1d09e-111">La pubblicazione di dati da Oracle è ideale per gli scenari seguenti:</span><span class="sxs-lookup"><span data-stu-id="1d09e-111">Publishing data from Oracle is ideal for the following scenarios:</span></span>  
  
|<span data-ttu-id="1d09e-112">Scenario</span><span class="sxs-lookup"><span data-stu-id="1d09e-112">Scenario</span></span>|<span data-ttu-id="1d09e-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1d09e-113">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="1d09e-114">Distribuzioni di applicazioni[!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework</span><span class="sxs-lookup"><span data-stu-id="1d09e-114">[!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework application deployments</span></span>|<span data-ttu-id="1d09e-115">Sviluppo con [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Studio e [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , operando al contempo su dati replicati da un database non[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1d09e-115">Develop with [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Studio and [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] while operating on data replicated from a non-[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] database.</span></span>|  
|<span data-ttu-id="1d09e-116">Server di gestione temporanea di data warehousing</span><span class="sxs-lookup"><span data-stu-id="1d09e-116">Data warehousing staging servers</span></span>|<span data-ttu-id="1d09e-117">Mantenimento dei database di gestione temporanea di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] sincronizzati con un database non[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1d09e-117">Keep [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] staging databases synchronized with a non-[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] database.</span></span>|  
|<span data-ttu-id="1d09e-118">Migrazione a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1d09e-118">Migration to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]</span></span>|<span data-ttu-id="1d09e-119">Verifica dell'applicazione in tempo reale a fronte di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] replicando al contempo le modifiche del sistema di origine.</span><span class="sxs-lookup"><span data-stu-id="1d09e-119">Test your application in real time against [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] while replicating the source system's changes.</span></span> <span data-ttu-id="1d09e-120">Quando il risultato della migrazione è soddisfacente, passare a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1d09e-120">Switch to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] when satisfied with the migration.</span></span>|  
  
 <span data-ttu-id="1d09e-121">Per altre informazioni, vedere [Panoramica della pubblicazione Oracle](oracle-publishing-overview.md).</span><span class="sxs-lookup"><span data-stu-id="1d09e-121">For more information, see [Oracle Publishing Overview](oracle-publishing-overview.md).</span></span>  
  
## <a name="publishing-data-to-non-sql-server-subscribers"></a><span data-ttu-id="1d09e-122">Pubblicazione di dati in Sottoscrittori non SQL Server</span><span class="sxs-lookup"><span data-stu-id="1d09e-122">Publishing Data to Non-SQL Server Subscribers</span></span>  
 <span data-ttu-id="1d09e-123">I database non[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] seguenti sono supportati come Sottoscrittori per le pubblicazioni snapshot e transazionali:</span><span class="sxs-lookup"><span data-stu-id="1d09e-123">The following non-[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] databases are supported as Subscribers to snapshot and transactional publications:</span></span>  
  
-   <span data-ttu-id="1d09e-124">Oracle per tutte le piattaforme supportate da Oracle.</span><span class="sxs-lookup"><span data-stu-id="1d09e-124">Oracle for all platforms that Oracle supports.</span></span>  
  
-   <span data-ttu-id="1d09e-125">IBM DB2 per AS400, MVS, Unix, Linux e Windows.</span><span class="sxs-lookup"><span data-stu-id="1d09e-125">IBM DB2 for AS400, MVS, Unix, Linux, and Windows.</span></span>  
  
 <span data-ttu-id="1d09e-126">Per altre informazioni, vedere [Non-SQL Server Subscribers](non-sql-server-subscribers.md).</span><span class="sxs-lookup"><span data-stu-id="1d09e-126">For more information, see [Non-SQL Server Subscribers](non-sql-server-subscribers.md).</span></span>  
  
  
