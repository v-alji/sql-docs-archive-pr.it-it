---
title: Server di pubblicazione non SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- heterogeneous database replication, non-SQL Server Publishers
- non-SQL Server Publishers
- heterogeneous data sources, non-SQL Server Publishers
- Publishers [SQL Server replication], Oracle
ms.assetid: 08a160a6-33be-46b5-bc7b-d53180d8bdf1
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f15f07dbf294d697afd385318f3dbf1447c8e2d8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624058"
---
# <a name="non-sql-server-publishers"></a><span data-ttu-id="a19ce-102">server di pubblicazione non SQL Server</span><span class="sxs-lookup"><span data-stu-id="a19ce-102">Non-SQL Server Publishers</span></span>
  <span data-ttu-id="a19ce-103">La pubblicazione di dati da [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] origini diverse consente di consolidare i dati in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a19ce-103">Publishing data from non-[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] sources allows you to consolidate data in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="a19ce-104">consente la sottoscrizione di dati snapshot o transazionali pubblicati da un database Oracle.</span><span class="sxs-lookup"><span data-stu-id="a19ce-104">can subscribe to snapshot or transactional data published from an Oracle database.</span></span> <span data-ttu-id="a19ce-105">Per altre informazioni sulla pubblicazione da sistemi Oracle, vedere [Panoramica della pubblicazione Oracle](oracle-publishing-overview.md).</span><span class="sxs-lookup"><span data-stu-id="a19ce-105">For more information about publishing from Oracle, see [Oracle Publishing Overview](oracle-publishing-overview.md).</span></span>  
  
 <span data-ttu-id="a19ce-106">La replica eterogenea a Sottoscrittori non SQL Server è deprecata.</span><span class="sxs-lookup"><span data-stu-id="a19ce-106">Heterogeneous replication to non-SQL Server subscribers is deprecated.</span></span> <span data-ttu-id="a19ce-107">La pubblicazione Oracle è deprecata.</span><span class="sxs-lookup"><span data-stu-id="a19ce-107">Oracle Publishing is deprecated.</span></span> <span data-ttu-id="a19ce-108">Per spostare dati, creare soluzioni utilizzando Change Data Capture e [!INCLUDE[ssIS](../../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a19ce-108">To move data, create solutions using change data capture and [!INCLUDE[ssIS](../../../includes/ssis-md.md)].</span></span>  
  
> [!CAUTION]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../../../includes/ssnotedepfutureavoid-md.md)]  
  
 <span data-ttu-id="a19ce-109">La pubblicazione da database non[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] è ideale nei seguenti scenari:</span><span class="sxs-lookup"><span data-stu-id="a19ce-109">Publishing from non-[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] databases is ideal for the following scenarios:</span></span>  
  
|<span data-ttu-id="a19ce-110">Scenario</span><span class="sxs-lookup"><span data-stu-id="a19ce-110">Scenario</span></span>|<span data-ttu-id="a19ce-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a19ce-111">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="a19ce-112">Distribuzioni di applicazioni[!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework</span><span class="sxs-lookup"><span data-stu-id="a19ce-112">[!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework application deployments</span></span>|<span data-ttu-id="a19ce-113">Sviluppo con [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Studio e [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , operando al contempo su dati replicati da un database non[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a19ce-113">Develop with [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Studio and [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] while operating on data replicated from a non-[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] database.</span></span>|  
|<span data-ttu-id="a19ce-114">Server di gestione temporanea di data warehousing</span><span class="sxs-lookup"><span data-stu-id="a19ce-114">Data warehousing staging servers</span></span>|<span data-ttu-id="a19ce-115">Mantenimento dei database di gestione temporanea di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] sincronizzati con un database non[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a19ce-115">Keep [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] staging databases synchronized with a non-[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] database.</span></span>|  
|<span data-ttu-id="a19ce-116">Migrazione a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a19ce-116">Migration to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]</span></span>|<span data-ttu-id="a19ce-117">Verifica dell'applicazione in tempo reale a fronte di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] replicando al contempo le modifiche del sistema di origine.</span><span class="sxs-lookup"><span data-stu-id="a19ce-117">Test your application in real time against [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] while replicating the source system's changes.</span></span> <span data-ttu-id="a19ce-118">Quando il risultato della migrazione è soddisfacente, passare a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a19ce-118">Switch to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] when satisfied with the migration.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a19ce-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a19ce-119">See Also</span></span>  
 [<span data-ttu-id="a19ce-120">Replica di database eterogenei</span><span class="sxs-lookup"><span data-stu-id="a19ce-120">Heterogeneous Database Replication</span></span>](heterogeneous-database-replication.md)  
  
  
