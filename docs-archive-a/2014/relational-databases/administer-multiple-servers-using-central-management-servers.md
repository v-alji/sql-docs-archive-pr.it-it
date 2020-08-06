---
title: Amministrare più server tramite server di gestione centrale | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- multiserver queries
- central management server
- multiserver administration [SQL Server]
- master servers [SQL Server], central management servers
- target configuration [SQL Server]
- server configuration [SQL Server]
ms.assetid: 427911a7-57d4-4542-8846-47c3267a5d9c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 3906165b595f6faa15812f70377a3bc0f550e52e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715447"
---
# <a name="administer-multiple-servers-using-central-management-servers"></a><span data-ttu-id="4c3c5-102">Amministrare più server tramite server di gestione centrale</span><span class="sxs-lookup"><span data-stu-id="4c3c5-102">Administer Multiple Servers Using Central Management Servers</span></span>
  <span data-ttu-id="4c3c5-103">È possibile amministrare più server designando server di gestione centrale e creando gruppi di server.</span><span class="sxs-lookup"><span data-stu-id="4c3c5-103">You can administer multiple servers by designating Central Management Servers and creating server groups.</span></span>  
  
## <a name="benefits-of-central-management-servers-and-server-groups"></a><span data-ttu-id="4c3c5-104">Vantaggi del server di gestione centrale e di gruppi di server</span><span class="sxs-lookup"><span data-stu-id="4c3c5-104">Benefits of Central Management Servers and Server Groups</span></span>  
 <span data-ttu-id="4c3c5-105">Un'istanza di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] definita come server di gestione centrale gestisce i gruppi di server che contengono le informazioni sulla connessione per una o più istanze di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4c3c5-105">An instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] that is designated as a Central Management Server maintains server groups that contain the connection information for one or more instances of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="4c3c5-106">Le istruzioni [!INCLUDE[tsql](../includes/tsql-md.md)] e i criteri della gestione basata su criteri possono essere eseguiti contemporaneamente in più gruppi di server.</span><span class="sxs-lookup"><span data-stu-id="4c3c5-106">[!INCLUDE[tsql](../includes/tsql-md.md)] statements and Policy-Based Management policies can be executed at the same time against server groups.</span></span> <span data-ttu-id="4c3c5-107">È inoltre possibile visualizzare i file di log di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] in istanze gestite tramite un server di gestione centrale.</span><span class="sxs-lookup"><span data-stu-id="4c3c5-107">You can also view the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] log files on instances that are managed through a Central Management Server.</span></span> <span data-ttu-id="4c3c5-108">Le versioni di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] precedenti a [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)] non possono essere designate come server di gestione centrale.</span><span class="sxs-lookup"><span data-stu-id="4c3c5-108">Versions of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] that are earlier than [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)] cannot be designated as a Central Management Server.</span></span>  
  
 [!INCLUDE[tsql](../includes/tsql-md.md)] <span data-ttu-id="4c3c5-109">le istruzioni possono inoltre essere eseguite su gruppi di server locali nella finestra Server registrati.</span><span class="sxs-lookup"><span data-stu-id="4c3c5-109">statements can also be executed against local server groups in Registered Servers.</span></span>  
  
### <a name="related-tasks"></a><span data-ttu-id="4c3c5-110">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="4c3c5-110">Related Tasks</span></span>  
 <span data-ttu-id="4c3c5-111">Per creare un server di gestione centrale e gruppi di server, usare la finestra **Server registrati** in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4c3c5-111">To create a Central Management Server and server groups, use the **Registered Servers** window in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="4c3c5-112">Notare che il server di gestione centrale non può essere un membro di uno dei gruppi che gestisce.</span><span class="sxs-lookup"><span data-stu-id="4c3c5-112">Note that the Central Management Server cannot be a member of a group that it maintains.</span></span> <span data-ttu-id="4c3c5-113">Per altre informazioni su come creare server di gestione centrale e gruppi di server, vedere [Creazione di un server di gestione centrale e di un gruppo di server &#40;SQL Server Management Studio&#41;](../ssms/register-servers/create-a-central-management-server-and-server-group.md).</span><span class="sxs-lookup"><span data-stu-id="4c3c5-113">For more information about how to create Central Management Servers and server groups, see [Create a Central Management Server and Server Group &#40;SQL Server Management Studio&#41;](../ssms/register-servers/create-a-central-management-server-and-server-group.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c3c5-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4c3c5-114">See Also</span></span>  
 [<span data-ttu-id="4c3c5-115">Amministrazione di server tramite la gestione basata su criteri</span><span class="sxs-lookup"><span data-stu-id="4c3c5-115">Administer Servers by Using Policy-Based Management</span></span>](policy-based-management/administer-servers-by-using-policy-based-management.md)  
  
  
