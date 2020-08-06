---
title: Opzione di configurazione del server remote admin connections | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- administrator connections [SQL Server]
- DAC
- connections [SQL Server], dedicated administrator
- remote admin connections option
- dedicated administrator connections [SQL Server]
ms.assetid: bf32b60a-7a48-401f-b6be-b5e2e46c413f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: c17cf278d18444c5b93d4f4b7e0a3da8dbfb671e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636385"
---
# <a name="remote-admin-connections-server-configuration-option"></a><span data-ttu-id="6c30d-102">Opzione di configurazione del server remote admin connections</span><span class="sxs-lookup"><span data-stu-id="6c30d-102">remote admin connections Server Configuration Option</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="6c30d-103">offre una connessione amministrativa dedicata (DAC).</span><span class="sxs-lookup"><span data-stu-id="6c30d-103">provides a dedicated administrator connection (DAC).</span></span> <span data-ttu-id="6c30d-104">Questa connessione consente agli amministratori di accedere a un server in esecuzione per eseguire funzioni diagnostiche o istruzioni [!INCLUDE[tsql](../../includes/tsql-md.md)] , nonché di risolvere i problemi che si verificano nel server, anche quando il server è bloccato o è in esecuzione in uno stato anomalo e non risponde a una connessione del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6c30d-104">The DAC lets an administrator access a running server to execute diagnostic functions or [!INCLUDE[tsql](../../includes/tsql-md.md)] statements, or to troubleshoot problems on the server, even when the server is locked or running in an abnormal state and not responding to a [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] connection.</span></span> <span data-ttu-id="6c30d-105">Per impostazione predefinita, la connessione DAC è disponibile solo da un client nel server.</span><span class="sxs-lookup"><span data-stu-id="6c30d-105">By default, the DAC is only available from a client on the server.</span></span> <span data-ttu-id="6c30d-106">Per consentire alle applicazioni client nei computer remoti di utilizzare la connessione DAC, utilizzare l'opzione remote admin connections di sp_configure.</span><span class="sxs-lookup"><span data-stu-id="6c30d-106">To enable client applications on remote computers to use the DAC, use the remote admin connections option of sp_configure.</span></span>  
  
 <span data-ttu-id="6c30d-107">Per impostazione predefinita, la connessione DAC è in attesa sull'indirizzo IP di loopback (127.0.0.1), porta 1434.</span><span class="sxs-lookup"><span data-stu-id="6c30d-107">By default, the DAC only listens on the loop-back IP address (127.0.0.1), port 1434.</span></span> <span data-ttu-id="6c30d-108">Se la porta TCP 1434 non è disponibile, all'avvio di [!INCLUDE[ssDE](../../includes/ssde-md.md)] viene assegnata dinamicamente una porta TCP.</span><span class="sxs-lookup"><span data-stu-id="6c30d-108">If TCP port 1434 is not available, a TCP port is dynamically assigned when the [!INCLUDE[ssDE](../../includes/ssde-md.md)] starts up.</span></span> <span data-ttu-id="6c30d-109">Quando in un computer sono installate più istanze di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , verificare il numero della porta TCP nel log degli errori.</span><span class="sxs-lookup"><span data-stu-id="6c30d-109">When more than one instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is installed on a computer, check the error log for the TCP port number.</span></span>  
  
 <span data-ttu-id="6c30d-110">Nella tabella seguente sono elencati i valori possibili per l'opzione remote admin connections.</span><span class="sxs-lookup"><span data-stu-id="6c30d-110">The following table lists the possible values for the remote admin connections option.</span></span>  
  
|<span data-ttu-id="6c30d-111">valore</span><span class="sxs-lookup"><span data-stu-id="6c30d-111">Value</span></span>|<span data-ttu-id="6c30d-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6c30d-112">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="6c30d-113">0</span><span class="sxs-lookup"><span data-stu-id="6c30d-113">0</span></span>|<span data-ttu-id="6c30d-114">Indica che l'utilizzo della connessione DAC è consentito solo alle connessioni locali.</span><span class="sxs-lookup"><span data-stu-id="6c30d-114">Indicates only local connections are allowed by using the DAC.</span></span>|  
|<span data-ttu-id="6c30d-115">1</span><span class="sxs-lookup"><span data-stu-id="6c30d-115">1</span></span>|<span data-ttu-id="6c30d-116">Indica che l'utilizzo della connessione DAC è consentito alle connessioni remote.</span><span class="sxs-lookup"><span data-stu-id="6c30d-116">Indicates remote connections are allowed by using the DAC.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="6c30d-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="6c30d-117">Example</span></span>  
 <span data-ttu-id="6c30d-118">Nell'esempio seguente viene abilitata la connessione DAC da un computer remoto.</span><span class="sxs-lookup"><span data-stu-id="6c30d-118">The following example enables the DAC from a remote computer.</span></span>  
  
```  
sp_configure 'remote admin connections', 1;  
GO  
RECONFIGURE;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="6c30d-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6c30d-119">See Also</span></span>  
 [<span data-ttu-id="6c30d-120">Connessione di diagnostica per gli amministratori di database</span><span class="sxs-lookup"><span data-stu-id="6c30d-120">Diagnostic Connection for Database Administrators</span></span>](diagnostic-connection-for-database-administrators.md)  
  
  
