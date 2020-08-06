---
title: Supporto SQL Server Native Client per il database locale | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
ms.assetid: 127569d1-a9f7-49bf-a561-c084986a8871
author: rothja
ms.author: jroth
ms.openlocfilehash: b08ea46e8db1b665280116a439b95748f69d03ef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626066"
---
# <a name="sql-server-native-client-support-for-localdb"></a><span data-ttu-id="03fa5-102">Supporto SQL Server Native Client per il database locale</span><span class="sxs-lookup"><span data-stu-id="03fa5-102">SQL Server Native Client Support for LocalDB</span></span>
  <span data-ttu-id="03fa5-103">A partire da [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)], sarà disponibile una versione lightweight di SQL Server, chiamato Database locale.</span><span class="sxs-lookup"><span data-stu-id="03fa5-103">Beginning in [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)], a lightweight version of SQL Server, called LocalDB, will be available.</span></span> <span data-ttu-id="03fa5-104">In questo argomento viene discussa la modalità di connessione a un database in un'istanza del database locale.</span><span class="sxs-lookup"><span data-stu-id="03fa5-104">This topic discusses how to connect to a database in a LocalDB instance.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="03fa5-105">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="03fa5-105">Remarks</span></span>  
 <span data-ttu-id="03fa5-106">Per ulteriori informazioni sul database locale inclusa la modalità di installazione del database locale e di configurazione della relativa istanza, vedere:</span><span class="sxs-lookup"><span data-stu-id="03fa5-106">For more information about LocalDB, including how to install LocalDB and configure your LocalDB instance, see:</span></span>  
  
-   [<span data-ttu-id="03fa5-107">Riferimento al database locale di SQL Server Express</span><span class="sxs-lookup"><span data-stu-id="03fa5-107">SQL Server Express LocalDB Reference</span></span>](../../sql-server-express-localdb-reference.md)  
  
-   [<span data-ttu-id="03fa5-108">SQL Server 2014 Express LocalDB</span><span class="sxs-lookup"><span data-stu-id="03fa5-108">SQL Server 2014 Express LocalDB</span></span>](../../../database-engine/configure-windows/sql-server-2016-express-localdb.md)  
  
 <span data-ttu-id="03fa5-109">Riepilogando, il database locale consente di:</span><span class="sxs-lookup"><span data-stu-id="03fa5-109">To summarize, LocalDB allows you to:</span></span>  
  
-   <span data-ttu-id="03fa5-110">utilizzare `sqllocaldb.exe i` per rilevare il nome dell'istanza predefinita.</span><span class="sxs-lookup"><span data-stu-id="03fa5-110">Use `sqllocaldb.exe i` to discover the name of the default instance.</span></span>  
  
-   <span data-ttu-id="03fa5-111">utilizzare la parola chiave della stringa di connessione `AttachDBFilename` per specificare a quale file di database il server si deve collegare.</span><span class="sxs-lookup"><span data-stu-id="03fa5-111">Use the `AttachDBFilename` connection string keyword to specify which database file the server should attach.</span></span> <span data-ttu-id="03fa5-112">Quando `AttachDBFilename` si utilizza, se non si specifica il nome del database con la parola chiave della stringa di connessione al **database** , il database verrà rimosso dall'istanza del database locale quando l'applicazione viene chiusa.</span><span class="sxs-lookup"><span data-stu-id="03fa5-112">When using `AttachDBFilename`, if you do not specify the name of the database with the **Database** connection string keyword, the database will be removed from the LocalDB instance when the application closes.</span></span>  
  
-   <span data-ttu-id="03fa5-113">Specificare un'istanza del database locale nella stringa di connessione:</span><span class="sxs-lookup"><span data-stu-id="03fa5-113">Specify a LocalDB instance in your connection string:</span></span>  
  
```  
SERVER=(localdb)\v11.0  
```  
  
 <span data-ttu-id="03fa5-114">Se necessario, è possibile creare un'istanza del database locale con sqllocaldb.exe.</span><span class="sxs-lookup"><span data-stu-id="03fa5-114">If necessary, you can create a LocalDB instance with sqllocaldb.exe.</span></span> <span data-ttu-id="03fa5-115">È possibile utilizzare anche sqlcmd.exe per aggiungere e modificare i database in un'istanza del database locale.</span><span class="sxs-lookup"><span data-stu-id="03fa5-115">You can also use sqlcmd.exe to add and modify databases in a LocalDB instance.</span></span> <span data-ttu-id="03fa5-116">Ad esempio: `sqlcmd -S (localdb)\v11.0`.</span><span class="sxs-lookup"><span data-stu-id="03fa5-116">For example, `sqlcmd -S (localdb)\v11.0`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03fa5-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="03fa5-117">See Also</span></span>  
 [<span data-ttu-id="03fa5-118">Funzionalità di SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="03fa5-118">SQL Server Native Client Features</span></span>](sql-server-native-client-features.md)  
  
  
