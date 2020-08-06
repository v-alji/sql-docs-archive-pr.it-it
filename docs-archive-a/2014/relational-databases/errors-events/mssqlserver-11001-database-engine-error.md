---
title: MSSQLSERVER_11001 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- "12001"
helpviewer_keywords:
- 11001 (Database Engine error)
ms.assetid: 53d4d63a-61e3-441f-bfe9-9d44f7a05fd4
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: da7dd171d1b6a64e0cc1666eda1e3593a81eece1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636179"
---
# <a name="mssqlserver_11001"></a><span data-ttu-id="e469e-102">MSSQLSERVER_11001</span><span class="sxs-lookup"><span data-stu-id="e469e-102">MSSQLSERVER_11001</span></span>
    
## <a name="details"></a><span data-ttu-id="e469e-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="e469e-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e469e-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="e469e-104">Product Name</span></span>|<span data-ttu-id="e469e-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="e469e-105">SQL Server</span></span>|  
|<span data-ttu-id="e469e-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="e469e-106">Event ID</span></span>|<span data-ttu-id="e469e-107">11001</span><span class="sxs-lookup"><span data-stu-id="e469e-107">11001</span></span>|  
|<span data-ttu-id="e469e-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="e469e-108">Event Source</span></span>|<span data-ttu-id="e469e-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="e469e-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="e469e-110">Componente</span><span class="sxs-lookup"><span data-stu-id="e469e-110">Component</span></span>|<span data-ttu-id="e469e-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="e469e-111">SQLEngine</span></span>|  
|<span data-ttu-id="e469e-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="e469e-112">Symbolic Name</span></span>||  
|<span data-ttu-id="e469e-113">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="e469e-113">Message Text</span></span>|<span data-ttu-id="e469e-114">Si è verificato un errore durante il tentativo di stabilire una connessione al server.</span><span class="sxs-lookup"><span data-stu-id="e469e-114">An error has occurred while establishing a connection to the server.</span></span>  <span data-ttu-id="e469e-115">Quando ci si connette a SQL Server, è possibile che l'errore sia determinato dal fatto che le impostazioni predefinite di SQL Server non consentono le connessioni remote.</span><span class="sxs-lookup"><span data-stu-id="e469e-115">When connecting to SQL Server, this failure may be caused by the fact that under the default settings SQL Server does not allow remote connections.</span></span> <span data-ttu-id="e469e-116">(provider: provider TCP, errore: 0 - Host sconosciuto.) (provider di dati SqlClient .Net)</span><span class="sxs-lookup"><span data-stu-id="e469e-116">(provider: TCP Provider, error: 0 - No such host is known.) (.Net SqlClient Data Provider)</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="e469e-117">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="e469e-117">Explanation</span></span>  
 <span data-ttu-id="e469e-118">Non è possibile stabilire la connessione tra il client [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e il server.</span><span class="sxs-lookup"><span data-stu-id="e469e-118">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client cannot connect to the server.</span></span> <span data-ttu-id="e469e-119">L'errore potrebbe verificarsi poiché il client non è in grado di risolvere il nome del server oppure il nome del server non è corretto.</span><span class="sxs-lookup"><span data-stu-id="e469e-119">The error could occur because either the client cannot resolve the name of the server or the name of the server is incorrect.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e469e-120">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="e469e-120">User Action</span></span>  
 <span data-ttu-id="e469e-121">Verificare di avere immesso il nome corretto del server sul client e che dal client sia possibile risolvere il nome del server.</span><span class="sxs-lookup"><span data-stu-id="e469e-121">Make sure that you have entered the correct server name on the client, and that you can resolve the name of the server from the client.</span></span> <span data-ttu-id="e469e-122">Per verificare la risoluzione dei nomi TCP/IP, con il sistema operativo Windows è possibile usare il comando **ping**.</span><span class="sxs-lookup"><span data-stu-id="e469e-122">To check TCP/IP name resolution, you can use the **ping** command in the Windows operating system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e469e-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e469e-123">See Also</span></span>  
 <span data-ttu-id="e469e-124">[Protocolli di rete e librerie di rete](../../sql-server/install/network-protocols-and-network-libraries.md) </span><span class="sxs-lookup"><span data-stu-id="e469e-124">[Network Protocols and Network Libraries](../../sql-server/install/network-protocols-and-network-libraries.md) </span></span>  
 <span data-ttu-id="e469e-125">[Configurazione di rete dei client](../../database-engine/configure-windows/client-network-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="e469e-125">[Client Network Configuration](../../database-engine/configure-windows/client-network-configuration.md) </span></span>  
 <span data-ttu-id="e469e-126">[Configurare i protocolli client](../../database-engine/configure-windows/configure-client-protocols.md) </span><span class="sxs-lookup"><span data-stu-id="e469e-126">[Configure Client Protocols](../../database-engine/configure-windows/configure-client-protocols.md) </span></span>  
 [<span data-ttu-id="e469e-127">Abilitare o disabilitare un protocollo di rete del server</span><span class="sxs-lookup"><span data-stu-id="e469e-127">Enable or Disable a Server Network Protocol</span></span>](../../database-engine/configure-windows/enable-or-disable-a-server-network-protocol.md)  
  
  
