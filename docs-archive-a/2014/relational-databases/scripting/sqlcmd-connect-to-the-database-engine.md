---
title: Connessione al Motore di database tramite sqlcmd
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- sqlcmd utility, Database Engine connections
- Named Pipes [SQL Server], sqlcmd utility
- TCP/IP [SQL Server], client protocols
- network protocols [SQL Server], sqlcmd utility
- protocols [SQL Server], sqlcmd utility
- VIA
- client protocols [SQL Server]
ms.assetid: 74b0fb71-7f8e-4171-9431-d07528532524
author: rothja
ms.author: jroth
ms.openlocfilehash: 3b409683b651e3e6508baced5eb3bc9fcc631e2c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625296"
---
# <a name="connect-to-the-database-engine-with-sqlcmd"></a><span data-ttu-id="7408c-102">Connessione al Motore di database tramite sqlcmd</span><span class="sxs-lookup"><span data-stu-id="7408c-102">Connect to the Database Engine With sqlcmd</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="7408c-103">supporta le comunicazioni client con il protocollo di rete TCP/IP (predefinito) e il protocollo Named Pipes.</span><span class="sxs-lookup"><span data-stu-id="7408c-103">supports client communication with the TCP/IP network protocol (the default), and the named pipes protocol.</span></span> <span data-ttu-id="7408c-104">Se il client si connette a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)] nello stesso computer, è inoltre disponibile il protocollo Shared Memory.</span><span class="sxs-lookup"><span data-stu-id="7408c-104">The shared memory protocol is also available if the client is connecting to an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] on the same computer.</span></span> <span data-ttu-id="7408c-105">La selezione del protocollo può essere in genere eseguita in tre modi.</span><span class="sxs-lookup"><span data-stu-id="7408c-105">There are three common methods of selecting the protocol.</span></span> <span data-ttu-id="7408c-106">Il protocollo usato dall'utilità **sqlcmd** viene determinato nel seguente ordine:</span><span class="sxs-lookup"><span data-stu-id="7408c-106">The protocol used by the **sqlcmd** utility is determined in the following order:</span></span>  
  
-   <span data-ttu-id="7408c-107">**sqlcmd** usa il protocollo specificato nella stringa di connessione come illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="7408c-107">**sqlcmd** uses the protocol specified as part of the connection string as described below.</span></span>  
  
-   <span data-ttu-id="7408c-108">Se nella stringa di connessione non viene specificato alcun protocollo, **sqlcmd** usa il protocollo definito nell'alias con il quale viene stabilita la connessione.</span><span class="sxs-lookup"><span data-stu-id="7408c-108">If no protocol is specified as part the connection string, **sqlcmd** will use the protocol defined as part of the alias that it is connecting to.</span></span> <span data-ttu-id="7408c-109">Per configurare **sqlcmd** per l'uso di un protocollo di rete specifico creando un alias, vedere [Creare o eliminare un alias server per l'uso da parte di un client &#40;Gestione configurazione SQL Server&#41;](../../database-engine/configure-windows/create-or-delete-a-server-alias-for-use-by-a-client.md).</span><span class="sxs-lookup"><span data-stu-id="7408c-109">To configure **sqlcmd** to use a specific network protocol by creating an alias, see [Create or Delete a Server Alias for Use by a Client &#40;SQL Server Configuration Manager&#41;](../../database-engine/configure-windows/create-or-delete-a-server-alias-for-use-by-a-client.md).</span></span>  
  
-   <span data-ttu-id="7408c-110">Se il protocollo non viene specificato in un altro modo, **sqlcmd** usa il protocollo di rete determinato dall'ordine dei protocolli in Gestione configurazione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7408c-110">If the protocol is not specified in some other way, **sqlcmd** will use the network protocol determined by the protocol order in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span>  
  
 <span data-ttu-id="7408c-111">Negli esempi seguenti vengono illustrate diverse modalità di connessione all'istanza predefinita di [!INCLUDE[ssDE](../../includes/ssde-md.md)] sulla porta 1433 e a istanze denominate di [!INCLUDE[ssDE](../../includes/ssde-md.md)] in attesa sulla porta 1691.</span><span class="sxs-lookup"><span data-stu-id="7408c-111">The following examples show various ways of connecting to the default instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] on port 1433, and named instances of [!INCLUDE[ssDE](../../includes/ssde-md.md)] presumed to be listening on port 1691.</span></span> <span data-ttu-id="7408c-112">In alcuni degli esempi viene utilizzato l'indirizzo IP dell'adattatore loopback (127.0.0.1).</span><span class="sxs-lookup"><span data-stu-id="7408c-112">Some of these examples use the IP address of the loopback adapter (127.0.0.1).</span></span> <span data-ttu-id="7408c-113">Eseguire una prova utilizzando l'indirizzo IP della scheda di interfaccia di rete del computer in uso.</span><span class="sxs-lookup"><span data-stu-id="7408c-113">Test using the IP address of your computer network interface card.</span></span>  
  
 <span data-ttu-id="7408c-114">Connettersi al [!INCLUDE[ssDE](../../includes/ssde-md.md)] specificando il nome dell'istanza:</span><span class="sxs-lookup"><span data-stu-id="7408c-114">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)] by specifying the instance name:</span></span>  
  
```  
sqlcmd -S ComputerA  
sqlcmd -S ComputerA\instanceB  
```  
  
 <span data-ttu-id="7408c-115">Connettersi al [!INCLUDE[ssDE](../../includes/ssde-md.md)] specificando l'indirizzo IP:</span><span class="sxs-lookup"><span data-stu-id="7408c-115">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)] by specifying the IP address:</span></span>  
  
```  
sqlcmd -S 127.0.0.1  
sqlcmd -S 127.0.0.1\instanceB  
```  
  
 <span data-ttu-id="7408c-116">Connettersi al [!INCLUDE[ssDE](../../includes/ssde-md.md)] specificando il numero della porta TCP\IP:</span><span class="sxs-lookup"><span data-stu-id="7408c-116">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)] by specifying the TCP\IP port number:</span></span>  
  
```  
sqlcmd -S ComputerA,1433  
sqlcmd -S ComputerA,1691  
sqlcmd -S 127.0.0.1,1433  
sqlcmd -S 127.0.0.1,1691  
```  
  
### <a name="to-connect-using-tcpip"></a><span data-ttu-id="7408c-117">Per connettersi utilizzando il protocollo TCP/IP</span><span class="sxs-lookup"><span data-stu-id="7408c-117">To connect using TCP/IP</span></span>  
  
-   <span data-ttu-id="7408c-118">Connettersi utilizzando la sintassi generale seguente:</span><span class="sxs-lookup"><span data-stu-id="7408c-118">Connect using the following general syntax:</span></span>  
  
    ```  
    sqlcmd -S tcp:<computer name>,<port number>  
    ```  
  
-   <span data-ttu-id="7408c-119">Connettersi all'istanza predefinita:</span><span class="sxs-lookup"><span data-stu-id="7408c-119">Connect to the default instance:</span></span>  
  
    ```  
    sqlcmd -S tcp:ComputerA,1433  
    sqlcmd -S tcp:127.0.0.1,1433  
    ```  
  
-   <span data-ttu-id="7408c-120">Connettersi a un'istanza denominata:</span><span class="sxs-lookup"><span data-stu-id="7408c-120">Connect to a named instance:</span></span>  
  
    ```  
    sqlcmd -S tcp:ComputerA,1691  
    sqlcmd -S tcp:127.0.0.1,1691  
    ```  
  
### <a name="to-connect-using-named-pipes"></a><span data-ttu-id="7408c-121">Per connettersi utilizzando il protocollo Named Pipes</span><span class="sxs-lookup"><span data-stu-id="7408c-121">To connect using named pipes</span></span>  
  
-   <span data-ttu-id="7408c-122">Stabilire la connessione utilizzando la sintassi generale seguente:</span><span class="sxs-lookup"><span data-stu-id="7408c-122">Connect using one of the following general syntax:</span></span>  
  
    ```  
    sqlcmd -S np:\\<computer name>\<pipe name>  
    ```  
  
-   <span data-ttu-id="7408c-123">Connettersi all'istanza predefinita:</span><span class="sxs-lookup"><span data-stu-id="7408c-123">Connect to the default instance:</span></span>  
  
    ```  
    sqlcmd -S np:\\ComputerA\pipe\sql\query  
    sqlcmd -S np:\\127.0.0.1\pipe\sql\query  
    ```  
  
-   <span data-ttu-id="7408c-124">Connettersi a un'istanza denominata:</span><span class="sxs-lookup"><span data-stu-id="7408c-124">Connect to a named instance instance:</span></span>  
  
    ```  
    sqlcmd -S np:\\ComputerA\pipe\MSSQL$<instancename>\sql\query  
    sqlcmd -S np:\\127.0.0.1\pipe\MSSQL$<instancename>\sql\query  
    ```  
  
### <a name="to-connect-using-shared-memory-a-local-procedure-call-from-a-client-on-the-server"></a><span data-ttu-id="7408c-125">Per connettersi utilizzando il protocollo Shared Memory (chiamata a una procedura locale) da un client nel server</span><span class="sxs-lookup"><span data-stu-id="7408c-125">To connect using shared memory (a local procedure call) from a client on the server</span></span>  
  
-   <span data-ttu-id="7408c-126">Stabilire la connessione utilizzando la sintassi generale seguente:</span><span class="sxs-lookup"><span data-stu-id="7408c-126">Connect using one of the following general syntax:</span></span>  
  
    ```  
    sqlcmd -S lpc:<computer name>  
    ```  
  
-   <span data-ttu-id="7408c-127">Connettersi all'istanza predefinita:</span><span class="sxs-lookup"><span data-stu-id="7408c-127">Connect to the default instance:</span></span>  
  
    ```  
    sqlcmd -S lpc:ComputerA  
    ```  
  
-   <span data-ttu-id="7408c-128">Connettersi a un'istanza denominata:</span><span class="sxs-lookup"><span data-stu-id="7408c-128">Connect to a named instance:</span></span>  
  
    ```  
    sqlcmd -S lpc:ComputerA\<instancename>  
    ```  
  
  
