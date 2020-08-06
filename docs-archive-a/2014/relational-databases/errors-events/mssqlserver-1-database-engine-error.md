---
title: MSSQLSERVER_-1 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- "-1"
helpviewer_keywords:
- -1 (Database Engine error)
ms.assetid: bad25b91-eaed-46c0-a5b7-71117a32304c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 880212b1d2e9572bbb31535a5ba68b445c7e6f35
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719967"
---
# <a name="mssqlserver_-1"></a><span data-ttu-id="023f1-102">MSSQLSERVER_-1</span><span class="sxs-lookup"><span data-stu-id="023f1-102">MSSQLSERVER_-1</span></span>
    
## <a name="details"></a><span data-ttu-id="023f1-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="023f1-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="023f1-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="023f1-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="023f1-105">ID evento</span><span class="sxs-lookup"><span data-stu-id="023f1-105">Event ID</span></span>|<span data-ttu-id="023f1-106">-1</span><span class="sxs-lookup"><span data-stu-id="023f1-106">-1</span></span>|  
|<span data-ttu-id="023f1-107">Origine evento</span><span class="sxs-lookup"><span data-stu-id="023f1-107">Event Source</span></span>|<span data-ttu-id="023f1-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="023f1-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="023f1-109">Componente</span><span class="sxs-lookup"><span data-stu-id="023f1-109">Component</span></span>|<span data-ttu-id="023f1-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="023f1-110">SQLEngine</span></span>|  
|<span data-ttu-id="023f1-111">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="023f1-111">Symbolic Name</span></span>||  
|<span data-ttu-id="023f1-112">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="023f1-112">Message Text</span></span>|<span data-ttu-id="023f1-113">Si è verificato un errore durante il tentativo di stabilire una connessione al server.</span><span class="sxs-lookup"><span data-stu-id="023f1-113">An error has occurred while establishing a connection to the server.</span></span>  <span data-ttu-id="023f1-114">Quando ci si connette a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], questo errore potrebbe essere provocato dal fatto che [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] non ammette connessioni remote sotto le impostazioni predefinite.</span><span class="sxs-lookup"><span data-stu-id="023f1-114">When connecting to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], this failure may be caused by the fact that under the default settings [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] does not allow remote connections.</span></span> <span data-ttu-id="023f1-115">(provider: interfacce di rete SQL, errore: 28 - Il server non supporta il protocollo richiesto) (Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], Errore: -1)</span><span class="sxs-lookup"><span data-stu-id="023f1-115">(provider: SQL Network Interfaces, error: 28 - Server doesn't support requested protocol) (Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], Error: -1)</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="023f1-116">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="023f1-116">Explanation</span></span>  
 <span data-ttu-id="023f1-117">Non è possibile stabilire la connessione tra il client [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e il server.</span><span class="sxs-lookup"><span data-stu-id="023f1-117">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client cannot connect to the server.</span></span> <span data-ttu-id="023f1-118">L'errore può essere causato da uno dei problemi seguenti:</span><span class="sxs-lookup"><span data-stu-id="023f1-118">This error could be caused by one of the following reasons:</span></span>  
  
-   <span data-ttu-id="023f1-119">Un nome di istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] specificato non è valido.</span><span class="sxs-lookup"><span data-stu-id="023f1-119">A specified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance name is not valid.</span></span>  
  
-   <span data-ttu-id="023f1-120">Il protocollo TCP o i protocolli named pipe non sono abilitati.</span><span class="sxs-lookup"><span data-stu-id="023f1-120">The TCP, or named pipes protocols are not enabled.</span></span>  
  
-   <span data-ttu-id="023f1-121">La connessione è stata rifiutata dal firewall del server.</span><span class="sxs-lookup"><span data-stu-id="023f1-121">The firewall on the server has refused the connection.</span></span>  
  
-   <span data-ttu-id="023f1-122">Il servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser (sqlbrowser) non è stato avviato.</span><span class="sxs-lookup"><span data-stu-id="023f1-122">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service (sqlbrowser) is not started.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="023f1-123">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="023f1-123">User Action</span></span>  
 <span data-ttu-id="023f1-124">Per risolvere l'errore, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="023f1-124">To resolve this error, try one of the following actions:</span></span>  
  
-   <span data-ttu-id="023f1-125">Controllare l'ortografia del nome dell'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] specificato nella stringa di connessione.</span><span class="sxs-lookup"><span data-stu-id="023f1-125">Check the spelling of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance name that is specified in the connection string.</span></span>  
  
-   <span data-ttu-id="023f1-126">Usare lo strumento Gestione configurazione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per consentire a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] di accettare le connessioni remote tramite protocolli TCP o Named Pipes.</span><span class="sxs-lookup"><span data-stu-id="023f1-126">Use the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager tool to enable [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to accept remote connections over the TCP or named pipes protocols.</span></span>  
  
-   <span data-ttu-id="023f1-127">Assicurarsi di avere configurato il firewall nell'istanza server di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per aprire porte per [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e la porta di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser (UDP 1434).</span><span class="sxs-lookup"><span data-stu-id="023f1-127">Make sure that you have configured the firewall on the server instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to open ports for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser port (UDP 1434).</span></span>  
  
-   <span data-ttu-id="023f1-128">Assicurarsi che il servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser sia stato avviato nel server.</span><span class="sxs-lookup"><span data-stu-id="023f1-128">Make sure that the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service is started on the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="023f1-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="023f1-129">See Also</span></span>  
 <span data-ttu-id="023f1-130">[Configurare un Windows Firewall per l'accesso motore di database](../../database-engine/configure-windows/configure-a-windows-firewall-for-database-engine-access.md) </span><span class="sxs-lookup"><span data-stu-id="023f1-130">[Configure a Windows Firewall for Database Engine Access](../../database-engine/configure-windows/configure-a-windows-firewall-for-database-engine-access.md) </span></span>  
 <span data-ttu-id="023f1-131">[Configurare i protocolli client](../../database-engine/configure-windows/configure-client-protocols.md) </span><span class="sxs-lookup"><span data-stu-id="023f1-131">[Configure Client Protocols](../../database-engine/configure-windows/configure-client-protocols.md) </span></span>  
 <span data-ttu-id="023f1-132">[Protocolli di rete e librerie di rete](../../sql-server/install/network-protocols-and-network-libraries.md) </span><span class="sxs-lookup"><span data-stu-id="023f1-132">[Network Protocols and Network Libraries](../../sql-server/install/network-protocols-and-network-libraries.md) </span></span>  
 <span data-ttu-id="023f1-133">[Configurazione di rete dei client](../../database-engine/configure-windows/client-network-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="023f1-133">[Client Network Configuration](../../database-engine/configure-windows/client-network-configuration.md) </span></span>  
 <span data-ttu-id="023f1-134">[Configurare i protocolli client](../../database-engine/configure-windows/configure-client-protocols.md) </span><span class="sxs-lookup"><span data-stu-id="023f1-134">[Configure Client Protocols](../../database-engine/configure-windows/configure-client-protocols.md) </span></span>  
 [<span data-ttu-id="023f1-135">Abilitare o disabilitare un protocollo di rete del server</span><span class="sxs-lookup"><span data-stu-id="023f1-135">Enable or Disable a Server Network Protocol</span></span>](../../database-engine/configure-windows/enable-or-disable-a-server-network-protocol.md)  
  
  
