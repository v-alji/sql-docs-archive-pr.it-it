---
title: MSSQLSERVER_18264 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 18264 (Database Engine error)
ms.assetid: 3050fc56-2be5-43cf-916b-50a3ac5f89aa
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 3edfeb82601e254c02df87cc4a978b9ab5e653e1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629850"
---
# <a name="mssqlserver_18264"></a><span data-ttu-id="54225-102">MSSQLSERVER_18264</span><span class="sxs-lookup"><span data-stu-id="54225-102">MSSQLSERVER_18264</span></span>
    
## <a name="details"></a><span data-ttu-id="54225-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="54225-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="54225-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="54225-104">Product Name</span></span>|<span data-ttu-id="54225-105">Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="54225-105">Microsoft SQL Server</span></span>|  
|<span data-ttu-id="54225-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="54225-106">Event ID</span></span>|<span data-ttu-id="54225-107">18264</span><span class="sxs-lookup"><span data-stu-id="54225-107">18264</span></span>|  
|<span data-ttu-id="54225-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="54225-108">Event Source</span></span>|<span data-ttu-id="54225-109">MSSQLENGINE</span><span class="sxs-lookup"><span data-stu-id="54225-109">MSSQLENGINE</span></span>|  
|<span data-ttu-id="54225-110">Componente</span><span class="sxs-lookup"><span data-stu-id="54225-110">Component</span></span>|<span data-ttu-id="54225-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="54225-111">SQLEngine</span></span>|  
|<span data-ttu-id="54225-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="54225-112">Symbolic Name</span></span>|<span data-ttu-id="54225-113">STRMIO_DBDUMP</span><span class="sxs-lookup"><span data-stu-id="54225-113">STRMIO_DBDUMP</span></span>|  
|<span data-ttu-id="54225-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="54225-114">Message Text</span></span>|<span data-ttu-id="54225-115">Backup del database eseguito:</span><span class="sxs-lookup"><span data-stu-id="54225-115">Database backed up.</span></span> <span data-ttu-id="54225-116">database: %s, data (ora) di creazione: %s(%s), pagine copiate: %d, primo LSN: %s, ultimo LSN: %s, numero di dispositivi di dump: %d, informazioni dispositivo: (%s).</span><span class="sxs-lookup"><span data-stu-id="54225-116">Database: %s, creation date(time): %s(%s), pages dumped: %d, first LSN: %s, last LSN: %s, number of dump devices: %d, device information: (%s).</span></span> <span data-ttu-id="54225-117">Questo è un messaggio informativo.</span><span class="sxs-lookup"><span data-stu-id="54225-117">This is an informational message only.</span></span> <span data-ttu-id="54225-118">Non è richiesta alcuna azione da parte dell'utente.</span><span class="sxs-lookup"><span data-stu-id="54225-118">No user action is required.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="54225-119">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="54225-119">Explanation</span></span>  
 <span data-ttu-id="54225-120">Per impostazione predefinita, per ogni backup eseguito in modo corretto viene aggiunto questo messaggio informativo al log degli errori di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e al registro eventi di sistema.</span><span class="sxs-lookup"><span data-stu-id="54225-120">By default, every successful backup adds this informational message to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log and the system event log.</span></span> <span data-ttu-id="54225-121">Se il backup del log delle transazioni viene eseguito di frequente, questi messaggi possono aumentare rapidamente, provocando la creazione di log degli errori di grandi dimensioni e rendendo difficile l'individuazione di altri messaggi.</span><span class="sxs-lookup"><span data-stu-id="54225-121">If you very frequently back up the transaction log, these messages can accumulate quickly, creating very large error logs that can make finding other messages difficult.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="54225-122">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="54225-122">User Action</span></span>  
 <span data-ttu-id="54225-123">È possibile eliminare queste voci di log mediante il flag di traccia **3226** di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="54225-123">You can suppress these log entries by using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] trace flag **3226**.</span></span> <span data-ttu-id="54225-124">L'abilitazione di questo flag di traccia risulta utile se si eseguono backup del log frequenti e se nessuno degli script dipende da tali voci.</span><span class="sxs-lookup"><span data-stu-id="54225-124">Enabling this trace flag is useful if you are running frequent log backups and if none of your scripts depend on those entries.</span></span>  
  
 <span data-ttu-id="54225-125">Per informazioni sull'utilizzo dei flag di traccia, vedere la documentazione online di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="54225-125">For information about using trace flags, see SQL Server Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54225-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="54225-126">See Also</span></span>  
 [<span data-ttu-id="54225-127">Flag di traccia &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="54225-127">Trace Flags &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/database-console-commands/dbcc-traceon-trace-flags-transact-sql)  
  
  
