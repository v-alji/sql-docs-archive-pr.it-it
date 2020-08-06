---
title: Disconnessione da un'origine dati | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- ODBC data sources, connections
- data sources [SQL Server Native Client]
- disconnecting [ODBC]
- ODBC applications, disconnecting
- SQLDisconnect function
- ODBC applications, data sources
- connections [SQL Server Native Client]
- SQLFreeHandle function
- ODBC data sources, disconnecting
- SQL Server Native Client ODBC driver, data sources
- ODBC functions
- SQL Server Native Client ODBC driver, connections
ms.assetid: 65b0267d-b2ab-4a59-83f2-436d90cfbf79
author: rothja
ms.author: jroth
ms.openlocfilehash: 5db3b83ab65d854f3a4d2182d9a4a1314e097681
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628651"
---
# <a name="disconnecting-from-a-data-source"></a><span data-ttu-id="ce627-102">Disconnessione da un'origine dati</span><span class="sxs-lookup"><span data-stu-id="ce627-102">Disconnecting from a Data Source</span></span>
  <span data-ttu-id="ce627-103">Quando un'applicazione ha terminato di usare un'origine dati, chiama **SQLConnect**.</span><span class="sxs-lookup"><span data-stu-id="ce627-103">When an application has finished using a data source, it calls **SQLDisconnect**.</span></span> <span data-ttu-id="ce627-104">**SQLConnect** libera tutte le istruzioni allocate sulla connessione e disconnette il driver dall'origine dati.</span><span class="sxs-lookup"><span data-stu-id="ce627-104">**SQLDisconnect** frees any statements that are allocated on the connection and disconnects the driver from the data source.</span></span> <span data-ttu-id="ce627-105">Dopo la disconnessione, l'applicazione può chiamare [SQLFreeHandle](../native-client-odbc-api/sqlfreehandle.md) per liberare l'handle di connessione.</span><span class="sxs-lookup"><span data-stu-id="ce627-105">After disconnecting, the application can call [SQLFreeHandle](../native-client-odbc-api/sqlfreehandle.md) to free the connection handle.</span></span> <span data-ttu-id="ce627-106">Prima di uscire, un'applicazione chiama anche **SQLFreeHandle** per liberare l'handle di ambiente.</span><span class="sxs-lookup"><span data-stu-id="ce627-106">Before exiting, an application also calls **SQLFreeHandle** to free the environment handle.</span></span>  
  
 <span data-ttu-id="ce627-107">Dopo la disconnessione, un'applicazione può riutilizzare l'handle di connessione allocato per connettersi a un'origine dati diversa oppure per riconnettersi alla stessa origine dati.</span><span class="sxs-lookup"><span data-stu-id="ce627-107">After disconnecting, an application can reuse the allocated connection handle, either to connect to a different data source or reconnect to the same data source.</span></span> <span data-ttu-id="ce627-108">La decisione di rimanere connessi anziché disconnettersi e riconnettersi in un secondo momento richiede la valutazione da parte del writer dell'applicazione dei costi relativi di ogni opzione.</span><span class="sxs-lookup"><span data-stu-id="ce627-108">The decision to remain connected instead of disconnecting and reconnecting later requires that the application writer consider the relative costs of each option.</span></span> <span data-ttu-id="ce627-109">Connettersi e rimanere connessi a un'origine dati può essere relativamente costoso, a seconda del supporto di connessione utilizzato.</span><span class="sxs-lookup"><span data-stu-id="ce627-109">Connecting to a data source and remaining connected can be relatively costly, depending on the connection medium.</span></span> <span data-ttu-id="ce627-110">Nella valutazione vanno considerati anche la probabilità di dover eseguire operazioni aggiuntive sulla stessa origine dati e il tempo richiesto.</span><span class="sxs-lookup"><span data-stu-id="ce627-110">In making a trade-off, the application must also make assumptions about the probability and timing of additional operations on the same data source.</span></span> <span data-ttu-id="ce627-111">È inoltre possibile che un'applicazione debba utilizzare più di una connessione.</span><span class="sxs-lookup"><span data-stu-id="ce627-111">An application may also have to use more than one connection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce627-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ce627-112">See Also</span></span>  
 [<span data-ttu-id="ce627-113">Comunicazione con SQL Server &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="ce627-113">Communicating with SQL Server &#40;ODBC&#41;</span></span>](communicating-with-sql-server-odbc.md)  
  
  
