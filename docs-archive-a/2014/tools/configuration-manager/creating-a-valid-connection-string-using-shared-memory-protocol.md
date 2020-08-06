---
title: Creazione di una stringa di connessione valida mediante il protocollo di memoria condivisa | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- connection strings [Database Engine], shared memory
- aliases [SQL Server], shared memory
ms.assetid: 5fff42e8-377f-4b40-b0c8-b02393f8a1af
author: stevestein
ms.author: sstein
ms.openlocfilehash: ca97332a09a33fcfc15a3dbb2599af27dbe0e1db
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711376"
---
# <a name="creating-a-valid-connection-string-using-shared-memory-protocol"></a><span data-ttu-id="2e83c-102">Creazione di una stringa di connessione valida mediante il protocollo di memoria condivisa</span><span class="sxs-lookup"><span data-stu-id="2e83c-102">Creating a Valid Connection String Using Shared Memory Protocol</span></span>
  <span data-ttu-id="2e83c-103">Le connessioni a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] da un client in esecuzione nello stesso computer usano il protocollo Shared Memory.</span><span class="sxs-lookup"><span data-stu-id="2e83c-103">Connections to [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from a client running on the same computer use the shared memory protocol.</span></span> <span data-ttu-id="2e83c-104">La memoria condivisa non dispone di proprietà configurabili.</span><span class="sxs-lookup"><span data-stu-id="2e83c-104">Shared memory has no configurable properties.</span></span> <span data-ttu-id="2e83c-105">Viene sempre utilizzata al primo tentativo di connessione e non può essere spostata dalla posizione iniziale nell'elenco **Protocolli abilitati** in **Proprietà protocolli client** .</span><span class="sxs-lookup"><span data-stu-id="2e83c-105">Shared memory is always tried first, and cannot be moved from the top position of the **Enabled Protocols** list in the **Client Protocols Properties** list.</span></span> <span data-ttu-id="2e83c-106">È possibile disabilitare il protocollo di memoria condivisa, operazione utile durante la risoluzione dei problemi relativi a uno degli altri protocolli.</span><span class="sxs-lookup"><span data-stu-id="2e83c-106">The Shared Memory protocol can be disabled, which is useful when troubleshooting one of the other protocols.</span></span>  
  
 <span data-ttu-id="2e83c-107">Non è possibile creare un alias utilizzando il protocollo di memoria condivisa, ma, se si abilita la memoria condivisa e quindi ci si connette a [!INCLUDE[ssDE](../../includes/ssde-md.md)] tramite un nome, viene creata una connessione di memoria condivisa.</span><span class="sxs-lookup"><span data-stu-id="2e83c-107">You cannot create an alias using the shared memory protocol, but if shared memory is enabled, then connecting to the [!INCLUDE[ssDE](../../includes/ssde-md.md)] by name, creates a shared memory connection.</span></span> <span data-ttu-id="2e83c-108">Una stringa di connessione di memoria condivisa utilizza il formato `lpc:<servername>[\instancename]`.</span><span class="sxs-lookup"><span data-stu-id="2e83c-108">A shared memory connection string uses the format `lpc:<servername>[\instancename]`.</span></span>  
  
## <a name="connecting-to-the-local-server"></a><span data-ttu-id="2e83c-109">Connessione al server locale</span><span class="sxs-lookup"><span data-stu-id="2e83c-109">Connecting to the Local Server</span></span>  
 <span data-ttu-id="2e83c-110">Quando si stabilisce una connessione a un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in esecuzione sullo stesso computer del client, è possibile usare **(locale)** come nome del server.</span><span class="sxs-lookup"><span data-stu-id="2e83c-110">When connecting to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] running on the same computer as the client, you can use **(local)** as the server name.</span></span> <span data-ttu-id="2e83c-111">Non si tratta di un'operazione consigliabile, in quanto genera ambiguità, ma può risultare utile se si è sicuri che il client viene eseguito nello stesso computer del server.</span><span class="sxs-lookup"><span data-stu-id="2e83c-111">This is not encouraged as it leads to ambiguity, however it can be useful when the client is known to be running on the intended computer.</span></span> <span data-ttu-id="2e83c-112">Se, ad esempio, si crea un'applicazione per utenti mobili non connessi, ad esempio il personale di vendita, e [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] viene eseguito su computer portatili e usato per archiviare dati di progetto, un client che si connette al server **(locale)** si connetterà sempre all'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in esecuzione sul portatile.</span><span class="sxs-lookup"><span data-stu-id="2e83c-112">For instance, when creating an application for mobile disconnected users, such as a sales force, where [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will run on laptop computers and store project data, a client connecting to **(local)** would always connect to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] running on the laptop.</span></span> <span data-ttu-id="2e83c-113">In sostituzione di **(locale)** . è possibile usare la parola**localhost**o un punto ( **.** ).</span><span class="sxs-lookup"><span data-stu-id="2e83c-113">The word **localhost** or a period (**.**) can be used in place of **(local)**.</span></span>  
  
## <a name="verifying-your-connection-protocol"></a><span data-ttu-id="2e83c-114">Verifica del protocollo di connessione</span><span class="sxs-lookup"><span data-stu-id="2e83c-114">Verifying your Connection Protocol</span></span>  
 <span data-ttu-id="2e83c-115">La query seguente restituisce il protocollo utilizzato per la connessione corrente.</span><span class="sxs-lookup"><span data-stu-id="2e83c-115">The following query will return the protocol used for the current connection.</span></span>  
  
```  
SELECT net_transport   
FROM sys.dm_exec_connections   
WHERE session_id = @@SPID;  
  
```  
  
## <a name="examples"></a><span data-ttu-id="2e83c-116">Esempi:</span><span class="sxs-lookup"><span data-stu-id="2e83c-116">Examples:</span></span>  
 <span data-ttu-id="2e83c-117">I nomi seguenti consentono di connettersi al computer locale con il protocollo di memoria condivisa, se abilitato:</span><span class="sxs-lookup"><span data-stu-id="2e83c-117">The following names will connect to the local computer with the shared memory protocol if it is enabled:</span></span>  
  
 `<servername>`  
  
 `<servername>\<instancename>`  
  
 `(local)`  
  
 `localhost`  
  
 <span data-ttu-id="2e83c-118">Non è possibile creare un alias per una connessione di memoria condivisa.</span><span class="sxs-lookup"><span data-stu-id="2e83c-118">You cannot create an alias for a shared memory connection.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2e83c-119">Se si specifica un indirizzo IP nella casella **Server** , verrà stabilita una connessione TCP/IP.</span><span class="sxs-lookup"><span data-stu-id="2e83c-119">Specifying an IP Address in the **Server** box will result in a TCP/IP connection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e83c-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2e83c-120">See Also</span></span>  
 <span data-ttu-id="2e83c-121">[Creazione di una stringa di connessione valida con TCP/IP](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-tcp-ip.md) </span><span class="sxs-lookup"><span data-stu-id="2e83c-121">[Creating a Valid Connection String Using TCP IP](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-tcp-ip.md) </span></span>  
 <span data-ttu-id="2e83c-122">[Creazione di una stringa di connessione valida tramite named pipe](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-named-pipes.md) </span><span class="sxs-lookup"><span data-stu-id="2e83c-122">[Creating a Valid Connection String Using Named Pipes](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-named-pipes.md) </span></span>  
 [<span data-ttu-id="2e83c-123">Scelta di un protocollo di rete</span><span class="sxs-lookup"><span data-stu-id="2e83c-123">Choosing a Network Protocol</span></span>](../../../2014/tools/configuration-manager/choosing-a-network-protocol.md)  
  
  
