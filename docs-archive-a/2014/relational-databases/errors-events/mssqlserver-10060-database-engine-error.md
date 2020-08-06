---
title: MSSQLSERVER_10060 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- "10060"
helpviewer_keywords:
- 10060 (Database Engine error)
ms.assetid: 28c21277-cad8-406c-a955-07933a56982a
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d634cfb06381fb916ef2e421e0677e76edb9ae02
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722864"
---
# <a name="mssqlserver_10060"></a><span data-ttu-id="b94d4-102">MSSQLSERVER_10060</span><span class="sxs-lookup"><span data-stu-id="b94d4-102">MSSQLSERVER_10060</span></span>
    
## <a name="details"></a><span data-ttu-id="b94d4-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="b94d4-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b94d4-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="b94d4-104">Product Name</span></span>|<span data-ttu-id="b94d4-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="b94d4-105">SQL Server</span></span>|  
|<span data-ttu-id="b94d4-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="b94d4-106">Event ID</span></span>|<span data-ttu-id="b94d4-107">10060</span><span class="sxs-lookup"><span data-stu-id="b94d4-107">10060</span></span>|  
|<span data-ttu-id="b94d4-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="b94d4-108">Event Source</span></span>|<span data-ttu-id="b94d4-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="b94d4-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="b94d4-110">Componente</span><span class="sxs-lookup"><span data-stu-id="b94d4-110">Component</span></span>|<span data-ttu-id="b94d4-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="b94d4-111">SQLEngine</span></span>|  
|<span data-ttu-id="b94d4-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="b94d4-112">Symbolic Name</span></span>||  
|<span data-ttu-id="b94d4-113">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="b94d4-113">Message Text</span></span>|<span data-ttu-id="b94d4-114">Si è verificato un errore durante il tentativo di stabilire una connessione al server.</span><span class="sxs-lookup"><span data-stu-id="b94d4-114">An error has occurred while establishing a connection to the server.</span></span>  <span data-ttu-id="b94d4-115">Quando ci si connette a SQL Server, è possibile che l'errore sia determinato dal fatto che le impostazioni predefinite di SQL Server non consentono le connessioni remote.</span><span class="sxs-lookup"><span data-stu-id="b94d4-115">When connecting to SQL Server, this failure may be caused by the fact that under the default settings SQL Server does not allow remote connections.</span></span> <span data-ttu-id="b94d4-116">(provider: provider TCP, errore: 0 - Impossibile stabilire la connessione. Risposta non corretta della parte connessa dopo l'intervallo di tempo oppure mancata risposta dall'host collegato.) (Microsoft SQL Server, Errore: 10060)</span><span class="sxs-lookup"><span data-stu-id="b94d4-116">(provider: TCP Provider, error: 0 - A connection attempt failed because the connected party did not properly respond after a period of time, or established connection failed because connected host has failed to respond.) (Microsoft SQL Server, Error: 10060)</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="b94d4-117">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="b94d4-117">Explanation</span></span>  
 <span data-ttu-id="b94d4-118">Non è possibile stabilire la connessione tra il client [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e il server.</span><span class="sxs-lookup"><span data-stu-id="b94d4-118">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client cannot connect to the server.</span></span> <span data-ttu-id="b94d4-119">Questo errore potrebbe verificarsi poiché la connessione è stata rifiutata dal firewall del server oppure il server non è configurato per l'accettazione di connessioni remote.</span><span class="sxs-lookup"><span data-stu-id="b94d4-119">This error could occur because either the firewall on the server has refused the connection or the server is not configured to accept remote connections.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b94d4-120">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="b94d4-120">User Action</span></span>  
 <span data-ttu-id="b94d4-121">Per risolvere l'errore, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b94d4-121">To resolve this error, try one of the following actions:</span></span>  
  
-   <span data-ttu-id="b94d4-122">Verificare che il firewall del computer sia configurato per consentire all'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] di accettare le connessioni.</span><span class="sxs-lookup"><span data-stu-id="b94d4-122">Make sure that you have configured the firewall on the computer to allow this instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to accept connections.</span></span>  
  
-   <span data-ttu-id="b94d4-123">Utilizzare lo strumento Gestione configurazione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per consentire l'accettazione di connessioni remote in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b94d4-123">Use the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager tool to allow [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to accept remote connections.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b94d4-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b94d4-124">See Also</span></span>  
 <span data-ttu-id="b94d4-125">[Configurare un Windows Firewall per l'accesso motore di database](../../database-engine/configure-windows/configure-a-windows-firewall-for-database-engine-access.md) </span><span class="sxs-lookup"><span data-stu-id="b94d4-125">[Configure a Windows Firewall for Database Engine Access](../../database-engine/configure-windows/configure-a-windows-firewall-for-database-engine-access.md) </span></span>  
 <span data-ttu-id="b94d4-126">[Configurare i protocolli client](../../database-engine/configure-windows/configure-client-protocols.md) </span><span class="sxs-lookup"><span data-stu-id="b94d4-126">[Configure Client Protocols](../../database-engine/configure-windows/configure-client-protocols.md) </span></span>  
 <span data-ttu-id="b94d4-127">[Protocolli di rete e librerie di rete](../../sql-server/install/network-protocols-and-network-libraries.md) </span><span class="sxs-lookup"><span data-stu-id="b94d4-127">[Network Protocols and Network Libraries](../../sql-server/install/network-protocols-and-network-libraries.md) </span></span>  
 <span data-ttu-id="b94d4-128">[Configurazione di rete dei client](../../database-engine/configure-windows/client-network-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="b94d4-128">[Client Network Configuration](../../database-engine/configure-windows/client-network-configuration.md) </span></span>  
 <span data-ttu-id="b94d4-129">[Configurare i protocolli client](../../database-engine/configure-windows/configure-client-protocols.md) </span><span class="sxs-lookup"><span data-stu-id="b94d4-129">[Configure Client Protocols](../../database-engine/configure-windows/configure-client-protocols.md) </span></span>  
 [<span data-ttu-id="b94d4-130">Abilitare o disabilitare un protocollo di rete del server</span><span class="sxs-lookup"><span data-stu-id="b94d4-130">Enable or Disable a Server Network Protocol</span></span>](../../database-engine/configure-windows/enable-or-disable-a-server-network-protocol.md)  
  
  
