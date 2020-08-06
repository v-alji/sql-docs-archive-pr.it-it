---
title: Utilizzo di cursori server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- ODBC applications, cursors
- cursors [ODBC], server cursors
- ODBC cursors, server cursors
- server cursors [SQL Server]
ms.assetid: 8a6d99b7-10b8-4474-8639-4914b25ba170
author: rothja
ms.author: jroth
ms.openlocfilehash: e596af3c46849313d813ce2d7f1dab2a7425c090
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626771"
---
# <a name="using-server-cursors"></a><span data-ttu-id="e430c-102">Utilizzo dei cursori del server</span><span class="sxs-lookup"><span data-stu-id="e430c-102">Using Server Cursors</span></span>
  <span data-ttu-id="e430c-103">Se un'applicazione ODBC imposta uno qualsiasi degli attributi del cursore ODBC su un valore diverso da quello predefinito, il [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] driver ODBC di Native Client richiede al server di implementare un cursore API del server dello stesso tipo.</span><span class="sxs-lookup"><span data-stu-id="e430c-103">If an ODBC application sets any of the ODBC cursor attributes to anything other than the defaults, the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver requests the server to implement an API server cursor of the same type.</span></span> <span data-ttu-id="e430c-104">L'utilizzo di cursori API del server libera memoria sul client e può ridurre in modo significativo il traffico di rete tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="e430c-104">Using API server cursors frees memory on the client and can significantly reduce network traffic between the client and server.</span></span>  
  
 <span data-ttu-id="e430c-105">Uno dei possibili svantaggi dei cursori API del server è attualmente il mancato supporto di tutte le istruzioni SQL.</span><span class="sxs-lookup"><span data-stu-id="e430c-105">A potential drawback of API server cursors is that they currently do not support all SQL statements.</span></span> <span data-ttu-id="e430c-106">I cursori API del server non possono essere utilizzati per eseguire:</span><span class="sxs-lookup"><span data-stu-id="e430c-106">API server cursors cannot be used to execute:</span></span>  
  
-   <span data-ttu-id="e430c-107">Batch o stored procedure che restituiscono più set di risultati.</span><span class="sxs-lookup"><span data-stu-id="e430c-107">Batches or stored procedures that return multiple result sets.</span></span>  
  
-   <span data-ttu-id="e430c-108">Istruzioni SELECT che contengono la clausola COMPUTE, COMPUTE BY, FOR BROWSE o INTO.</span><span class="sxs-lookup"><span data-stu-id="e430c-108">SELECT statements that contain COMPUTE, COMPUTE BY, FOR BROWSE, or INTO clauses.</span></span>  
  
-   <span data-ttu-id="e430c-109">Istruzioni EXECUTE che fanno riferimento a una stored procedure remota.</span><span class="sxs-lookup"><span data-stu-id="e430c-109">An EXECUTE statement referencing a remote stored procedure.</span></span>  
  
 <span data-ttu-id="e430c-110">In caso di connessione a un'istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], l'esecuzione di un'istruzione con queste caratteristiche attraverso un cursore del server causa la conversione del cursore in un set di risultati predefinito.</span><span class="sxs-lookup"><span data-stu-id="e430c-110">When connected to an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], executing a statement with these characteristics using a server cursor causes the cursor being converted to a default result set.</span></span> <span data-ttu-id="e430c-111">In caso di connessione a versioni precedenti di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], causa un errore.</span><span class="sxs-lookup"><span data-stu-id="e430c-111">When connected to earlier versions of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], it causes an error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e430c-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e430c-112">See Also</span></span>  
 [<span data-ttu-id="e430c-113">Modalità di implementazione dei cursori</span><span class="sxs-lookup"><span data-stu-id="e430c-113">How Cursors Are Implemented</span></span>](how-cursors-are-implemented.md)  
  
  
