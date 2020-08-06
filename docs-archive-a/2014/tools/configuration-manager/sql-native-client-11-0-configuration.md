---
title: Configurazione di SQL Native Client 11,0 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- client configuration [SQL Server], SQL Server Native Client
ms.assetid: e73143e9-5e7b-4d0a-8827-ab900efdcb35
author: stevestein
ms.author: sstein
ms.openlocfilehash: 183dd2d161b1bf0b13140a607167b81dab086fdf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625121"
---
# <a name="sql-native-client-110-configuration"></a><span data-ttu-id="85ac8-102">Configurazione SQL Native Client 11.0</span><span class="sxs-lookup"><span data-stu-id="85ac8-102">SQL Native Client 11.0 Configuration</span></span>
  <span data-ttu-id="85ac8-103">In questa sezione sono disponibili gli argomenti della Guida per le finestre di dialogo di **Configurazione SQL Server Native Client** in Gestione configurazione [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="85ac8-103">This section contains the F1 Help topics for the **SQL Server Native Client Configuration** dialogs in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="85ac8-104">Native Client è la libreria di rete usata dai computer client per connettersi a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a partire da [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="85ac8-104">Native Client is the network library that client computers use to connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], starting with [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="85ac8-105">Le impostazioni configurate in Configurazione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client vengono utilizzate nel computer in cui viene eseguito il programma client.</span><span class="sxs-lookup"><span data-stu-id="85ac8-105">The settings configured in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client Configuration, are used on the computer running the client program.</span></span> <span data-ttu-id="85ac8-106">Se vengono configurate nel computer che esegue [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], vengono applicate esclusivamente ai programmi client in esecuzione sul server.</span><span class="sxs-lookup"><span data-stu-id="85ac8-106">When configured on the computer running [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], they affect only those client programs running on the server.</span></span>  
  
 <span data-ttu-id="85ac8-107">Queste impostazioni non vengono applicate ai client che si connettono a versioni precedenti di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], a meno che non utilizzino gli strumenti client disponibili a partire da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], ad esempio [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="85ac8-107">These settings do not affect clients connecting to previous versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], unless they are using the client tools starting with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], such as [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="85ac8-108">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="85ac8-108">In this Section</span></span>  
  
-   [<span data-ttu-id="85ac8-109">Proprietà - Configurazione SQL Server Native Client &#40;scheda Flag&#41;</span><span class="sxs-lookup"><span data-stu-id="85ac8-109">SQL Server Native Client Configuration Properties &#40;Flags Tab&#41;</span></span>](../../../2014/tools/configuration-manager/sql-server-native-client-configuration-properties-flags-tab.md)  
  
-   [<span data-ttu-id="85ac8-110">Protocolli client &#40;Gestione configurazione SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="85ac8-110">Client Protocols &#40;SQL Server Configuration Manager&#41;</span></span>](../../relational-databases/sql-server-configuration-manager.md)  
  
    -   [<span data-ttu-id="85ac8-111">Proprietà - Protocolli client &#40;scheda Ordine&#41;</span><span class="sxs-lookup"><span data-stu-id="85ac8-111">Client Protocols Properties &#40;Order Tab&#41;</span></span>](../../../2014/tools/configuration-manager/client-protocols-properties-order-tab.md)  
  
    -   [<span data-ttu-id="85ac8-112">Protocolli client - Proprietà - Shared Memory &#40;scheda Protocollo&#41;</span><span class="sxs-lookup"><span data-stu-id="85ac8-112">Client Protocols - Shared Memory Properties &#40;Protocol Tab&#41;</span></span>](../../../2014/tools/configuration-manager/client-protocols-shared-memory-properties-protocol-tab.md)  
  
    -   [<span data-ttu-id="85ac8-113">Protocolli client-proprietà TCP e IP &#40;scheda protocollo&#41;</span><span class="sxs-lookup"><span data-stu-id="85ac8-113">Client Protocols - TCP and IP Properties &#40;Protocol Tab&#41;</span></span>](../../../2014/tools/configuration-manager/client-protocols-tcp-and-ip-properties-protocol-tab.md)  
  
    -   [<span data-ttu-id="85ac8-114">Protocolli client - Proprietà - Named pipe &#40;scheda Protocolli&#41;</span><span class="sxs-lookup"><span data-stu-id="85ac8-114">Client Protocols - Named Pipes Properties &#40;Protocol Tab&#41;</span></span>](../../../2014/tools/configuration-manager/client-protocols-named-pipes-properties-protocol-tab.md)  
  
-   [<span data-ttu-id="85ac8-115">Alias &#40;Gestione configurazione SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="85ac8-115">Aliases &#40;SQL Server Configuration Manager&#41;</span></span>](../../../2014/tools/configuration-manager/aliases-sql-server-configuration-manager.md)  
  
    -   [<span data-ttu-id="85ac8-116">Nuovo alias &#40;scheda Alias&#41;</span><span class="sxs-lookup"><span data-stu-id="85ac8-116">New Alias &#40;Alias Tab&#41;</span></span>](../../../2014/tools/configuration-manager/new-alias-alias-tab.md)  
  
    -   [<span data-ttu-id="85ac8-117">Proprietà &#60;Alias&#62; &#40;scheda Alias&#41;</span><span class="sxs-lookup"><span data-stu-id="85ac8-117">&#60;Alias&#62; Properties &#40;Alias Tab&#41;</span></span>](../../../2014/tools/configuration-manager/alias-properties-alias-tab.md)  
  
    -   [<span data-ttu-id="85ac8-118">Creazione di una stringa di connessione valida mediante il protocollo di memoria condivisa</span><span class="sxs-lookup"><span data-stu-id="85ac8-118">Creating a Valid Connection String Using Shared Memory Protocol</span></span>](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-shared-memory-protocol.md)  
  
    -   [<span data-ttu-id="85ac8-119">Creazione di una stringa di connessione valida con TCP/IP</span><span class="sxs-lookup"><span data-stu-id="85ac8-119">Creating a Valid Connection String Using TCP IP</span></span>](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-tcp-ip.md)  
  
    -   [<span data-ttu-id="85ac8-120">Creazione di una stringa di connessione valida tramite named pipe</span><span class="sxs-lookup"><span data-stu-id="85ac8-120">Creating a Valid Connection String Using Named Pipes</span></span>](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-named-pipes.md)  
  
  
