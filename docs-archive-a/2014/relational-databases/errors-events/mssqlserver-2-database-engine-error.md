---
title: MSSQLSERVER_2 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- "2"
helpviewer_keywords:
- 2 (Database Engine error)
ms.assetid: 567fb571-7cda-4ce8-a702-cdff2df5d419
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 87d19a24219fda79de2cad4c06af4f1936b37b24
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636137"
---
# <a name="mssqlserver_2"></a><span data-ttu-id="53828-102">MSSQLSERVER_2</span><span class="sxs-lookup"><span data-stu-id="53828-102">MSSQLSERVER_2</span></span>
    
## <a name="details"></a><span data-ttu-id="53828-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="53828-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="53828-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="53828-104">Product Name</span></span>|<span data-ttu-id="53828-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="53828-105">SQL Server</span></span>|  
|<span data-ttu-id="53828-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="53828-106">Event ID</span></span>|<span data-ttu-id="53828-107">2</span><span class="sxs-lookup"><span data-stu-id="53828-107">2</span></span>|  
|<span data-ttu-id="53828-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="53828-108">Event Source</span></span>|<span data-ttu-id="53828-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="53828-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="53828-110">Componente</span><span class="sxs-lookup"><span data-stu-id="53828-110">Component</span></span>|<span data-ttu-id="53828-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="53828-111">SQLEngine</span></span>|  
|<span data-ttu-id="53828-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="53828-112">Symbolic Name</span></span>||  
|<span data-ttu-id="53828-113">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="53828-113">Message Text</span></span>|<span data-ttu-id="53828-114">Si è verificato un errore durante il tentativo di stabilire una connessione al server.</span><span class="sxs-lookup"><span data-stu-id="53828-114">An error has occurred while establishing a connection to the server.</span></span>  <span data-ttu-id="53828-115">Quando ci si connette a SQL Server, è possibile che l'errore sia determinato dal fatto che le impostazioni predefinite di SQL Server non consentono le connessioni remote.</span><span class="sxs-lookup"><span data-stu-id="53828-115">When connecting to SQL Server, this failure may be caused by the fact that under the default settings SQL Server does not allow remote connections.</span></span> <span data-ttu-id="53828-116">(provider: Provider named pipe, errore: 40 - Impossibile aprire una connessione a SQL Server) (.Net SqlClient Data Provider)</span><span class="sxs-lookup"><span data-stu-id="53828-116">(provider: Named Pipes Provider, error: 40 - Could not open a connection to SQL Server) (.Net SqlClient Data Provider)</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="53828-117">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="53828-117">Explanation</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="53828-118">non ha risposto alla richiesta del client probabilmente perché il server non è stato avviato.</span><span class="sxs-lookup"><span data-stu-id="53828-118">did not respond to the client request because the server is probably not started.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="53828-119">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="53828-119">User Action</span></span>  
 <span data-ttu-id="53828-120">Verificare che il server sia stato avviato.</span><span class="sxs-lookup"><span data-stu-id="53828-120">Make sure that the server is started.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53828-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="53828-121">See Also</span></span>  
 <span data-ttu-id="53828-122">[Gestire il servizio Motore di database](../../database-engine/configure-windows/manage-the-database-engine-services.md) </span><span class="sxs-lookup"><span data-stu-id="53828-122">[Manage the Database Engine Services](../../database-engine/configure-windows/manage-the-database-engine-services.md) </span></span>  
 <span data-ttu-id="53828-123">[Configurare i protocolli client](../../database-engine/configure-windows/configure-client-protocols.md) </span><span class="sxs-lookup"><span data-stu-id="53828-123">[Configure Client Protocols](../../database-engine/configure-windows/configure-client-protocols.md) </span></span>  
 <span data-ttu-id="53828-124">[Protocolli di rete e librerie di rete](../../sql-server/install/network-protocols-and-network-libraries.md) </span><span class="sxs-lookup"><span data-stu-id="53828-124">[Network Protocols and Network Libraries](../../sql-server/install/network-protocols-and-network-libraries.md) </span></span>  
 <span data-ttu-id="53828-125">[Configurazione di rete dei client](../../database-engine/configure-windows/client-network-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="53828-125">[Client Network Configuration](../../database-engine/configure-windows/client-network-configuration.md) </span></span>  
 <span data-ttu-id="53828-126">[Configurare i protocolli client](../../database-engine/configure-windows/configure-client-protocols.md) </span><span class="sxs-lookup"><span data-stu-id="53828-126">[Configure Client Protocols](../../database-engine/configure-windows/configure-client-protocols.md) </span></span>  
 [<span data-ttu-id="53828-127">Abilitare o disabilitare un protocollo di rete del server</span><span class="sxs-lookup"><span data-stu-id="53828-127">Enable or Disable a Server Network Protocol</span></span>](../../database-engine/configure-windows/enable-or-disable-a-server-network-protocol.md)  
  
  
