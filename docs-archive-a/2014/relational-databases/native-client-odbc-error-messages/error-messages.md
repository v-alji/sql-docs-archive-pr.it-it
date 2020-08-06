---
title: Messaggi di errore | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client ODBC driver, errors
- messages [ODBC], types
- ODBC error handling, message types
- errors [ODBC], types
ms.assetid: 46c0c22e-d105-4d5b-bb9d-5694472e8651
author: rothja
ms.author: jroth
ms.openlocfilehash: d004ba320b50896b6f57c5de335d7f7b3d33e87a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722776"
---
# <a name="error-messages"></a><span data-ttu-id="a0145-102">messaggi di errore</span><span class="sxs-lookup"><span data-stu-id="a0145-102">Error Messages</span></span>
  <span data-ttu-id="a0145-103">Il testo dei messaggi restituiti dal [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver ODBC di Native client viene inserito nel parametro *MessageText* di **SQLGetDiagRec**.</span><span class="sxs-lookup"><span data-stu-id="a0145-103">The text of messages returned by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver is placed in the *MessageText* parameter of **SQLGetDiagRec**.</span></span> <span data-ttu-id="a0145-104">L'origine di un errore viene indicata dall'intestazione del messaggio:</span><span class="sxs-lookup"><span data-stu-id="a0145-104">The source of an error is indicated by the header of the message:</span></span>  
  
 <span data-ttu-id="a0145-105">[Microsoft][Gestione driver ODBC]</span><span class="sxs-lookup"><span data-stu-id="a0145-105">[Microsoft][ODBC Driver Manager]</span></span>  
 <span data-ttu-id="a0145-106">Questi errori vengono generati da Gestione driver ODBC.</span><span class="sxs-lookup"><span data-stu-id="a0145-106">These errors are raised by the ODBC Driver Manager.</span></span>  
  
 <span data-ttu-id="a0145-107">[Microsoft][Libreria di cursori ODBC]</span><span class="sxs-lookup"><span data-stu-id="a0145-107">[Microsoft][ODBC Cursor Library]</span></span>  
 <span data-ttu-id="a0145-108">Questi errori vengono generati dalla libreria di cursori ODBC.</span><span class="sxs-lookup"><span data-stu-id="a0145-108">These errors are raised by the ODBC cursor library.</span></span>  
  
 <span data-ttu-id="a0145-109">[Microsoft][SQL Server Native Client]</span><span class="sxs-lookup"><span data-stu-id="a0145-109">[Microsoft][SQL Server Native Client]</span></span>  
 <span data-ttu-id="a0145-110">Questi errori vengono generati dal [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver ODBC di Native Client.</span><span class="sxs-lookup"><span data-stu-id="a0145-110">These errors are raised by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver.</span></span> <span data-ttu-id="a0145-111">Se non sono presenti altri nodi con il nome di una libreria di rete o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], l'errore è stato rilevato nel driver.</span><span class="sxs-lookup"><span data-stu-id="a0145-111">If there are no other nodes with either the name of a Net-Library or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], then the error was encountered in the driver.</span></span>  
  
 <span data-ttu-id="a0145-112">Microsoft [SQL Server Native Client] [*Net-transportaname*]</span><span class="sxs-lookup"><span data-stu-id="a0145-112">[Microsoft][SQL Server Native Client][*Net-Transportname*]</span></span>  
 <span data-ttu-id="a0145-113">Questi errori vengono generati dalla libreria di rete [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , dove *net-TransportName* è il nome visualizzato del trasporto di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] rete di un client, ad esempio Named Pipes, Shared Memory, TCP/IP Sockets o via.</span><span class="sxs-lookup"><span data-stu-id="a0145-113">These errors are raised by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Net-Library, where *Net-Transportname* is the display name of a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client network transport (for example, Named Pipes, Shared Memory, TCP/IP Sockets, or VIA).</span></span> <span data-ttu-id="a0145-114">Il resto del messaggio di errore contiene la funzione della libreria di rete chiamata e la funzione chiamata nell'API di rete sottostante dalla funzione TDS.</span><span class="sxs-lookup"><span data-stu-id="a0145-114">The remainder of the error message contains the Net-Library function called and the function called in the underlying network API by the TDS function.</span></span> <span data-ttu-id="a0145-115">Il codice di errore *pfNative* restituito con questi errori è il codice di errore dello stack del protocollo di rete sottostante.</span><span class="sxs-lookup"><span data-stu-id="a0145-115">The *pfNative* error code returned with these errors is the error code from the underlying network protocol stack.</span></span>  
  
 <span data-ttu-id="a0145-116">[Microsoft][SQL Server Native Client][[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]]</span><span class="sxs-lookup"><span data-stu-id="a0145-116">[Microsoft][SQL Server Native Client][[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]]</span></span>  
 <span data-ttu-id="a0145-117">Questi errori vengono generati da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a0145-117">These errors are raised by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="a0145-118">Il resto del messaggio di errore corrisponde al testo del messaggio di errore restituito da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a0145-118">The remainder of the error message is the text of the error message from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="a0145-119">Il codice *pfNative* restituito con questi errori è il numero di errore di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a0145-119">The *pfNative* code returned with these errors is the error number from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="a0145-120">Per ulteriori informazioni su un elenco di messaggi di errore (e sui relativi numeri) che possono essere restituiti da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , vedere la descrizione e le colonne di errore della tabella di sistema **sysmessages** nel database **Master** in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a0145-120">For more information about a list of error messages (and their numbers) that can be returned by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see the description and error columns of the **sysmessages** system table in the **master** database in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0145-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a0145-121">See Also</span></span>  
 [<span data-ttu-id="a0145-122">Gestione di errori e messaggi</span><span class="sxs-lookup"><span data-stu-id="a0145-122">Handling Errors and Messages</span></span>](handling-errors-and-messages.md)  
  
  
