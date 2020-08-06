---
title: Creazione di un'applicazione provider OLE DB SQL Server Native Client | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client OLE DB provider, application creation
- applications [SQL Server Native Client]
- OLE DB, creating applications
ms.assetid: f3ae6815-f32d-4913-a1a2-2ba2f20cfd88
author: rothja
ms.author: jroth
ms.openlocfilehash: a661f23cdacc4b581dadbe7625cb6e2ea318857f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714303"
---
# <a name="creating-a-sql-server-native-client-ole-db-provider-application"></a><span data-ttu-id="95d73-102">Creazione di un'applicazione del provider OLE DB di SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="95d73-102">Creating a SQL Server Native Client OLE DB Provider Application</span></span>
  <span data-ttu-id="95d73-103">La creazione di un' [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] applicazione del provider OLE DB di Native Client prevede i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="95d73-103">Creating a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider application involves these steps:</span></span>  
  
1.  <span data-ttu-id="95d73-104">Avvio di una connessione a un'origine dati.</span><span class="sxs-lookup"><span data-stu-id="95d73-104">Establishing a connection to a data source.</span></span>  
  
2.  <span data-ttu-id="95d73-105">Esecuzione di un comando.</span><span class="sxs-lookup"><span data-stu-id="95d73-105">Executing a command.</span></span>  
  
3.  <span data-ttu-id="95d73-106">Elaborazione dei risultati.</span><span class="sxs-lookup"><span data-stu-id="95d73-106">Processing the results.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="95d73-107">Se possibile, usare l'autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="95d73-107">When possible, use Windows Authentication.</span></span> <span data-ttu-id="95d73-108">Se non è disponibile, agli utenti verrà richiesto di immettere le credenziali in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="95d73-108">If Windows Authentication is not available, prompt users to enter their credentials at run time.</span></span> <span data-ttu-id="95d73-109">Evitare di archiviare le credenziali in un file.</span><span class="sxs-lookup"><span data-stu-id="95d73-109">Avoid storing credentials in a file.</span></span> <span data-ttu-id="95d73-110">Se è necessario rendere persistenti le credenziali, è consigliabile crittografarle usando [CryptoAPI Win32](https://go.microsoft.com/fwlink/?LinkId=9504).</span><span class="sxs-lookup"><span data-stu-id="95d73-110">If you must persist credentials, you should encrypt them with [the Win32 cryptoAPI](https://go.microsoft.com/fwlink/?LinkId=9504).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="95d73-111">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="95d73-111">In This Section</span></span>  
  
-   [<span data-ttu-id="95d73-112">Avvio di una connessione a un'origine dati</span><span class="sxs-lookup"><span data-stu-id="95d73-112">Establishing a Connection to a Data Source</span></span>](establishing-a-connection-to-a-data-source.md)  
  
-   [<span data-ttu-id="95d73-113">Esecuzione di un comando</span><span class="sxs-lookup"><span data-stu-id="95d73-113">Executing a Command</span></span>](executing-a-command.md)  
  
-   [<span data-ttu-id="95d73-114">Risultati dell'elaborazione</span><span class="sxs-lookup"><span data-stu-id="95d73-114">Processing Results</span></span>](processing-results.md)  
  
-   [<span data-ttu-id="95d73-115">Informazioni sulle proprietà OLE DB</span><span class="sxs-lookup"><span data-stu-id="95d73-115">About OLE DB Properties</span></span>](about-ole-db-properties.md)  
  
-   [<span data-ttu-id="95d73-116">Utilizzo della clausola OUTPUT con OLE DB in SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="95d73-116">Using the OUTPUT Clause with OLE DB in SQL Server Native Client</span></span>](using-the-output-clause-with-ole-db-in-sql-server-native-client.md)  
  
## <a name="see-also"></a><span data-ttu-id="95d73-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="95d73-117">See Also</span></span>  
 [<span data-ttu-id="95d73-118">SQL Server Native Client &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="95d73-118">SQL Server Native Client &#40;OLE DB&#41;</span></span>](../native-client/ole-db/sql-server-native-client-ole-db.md)  
  
  
