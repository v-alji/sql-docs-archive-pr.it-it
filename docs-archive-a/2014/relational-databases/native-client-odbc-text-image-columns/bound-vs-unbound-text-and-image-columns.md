---
title: Colonne di testo e di immagine non associato e associato | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- text columns [ODBC]
- SQL Server Native Client ODBC driver, image columns
- SQL Server Native Client ODBC driver, text columns
- data types [ODBC], image
- data types [ODBC], text
- columns [ODBC]
- ODBC data types, image columns
- ODBC data types, text columns
- image columns [ODBC]
ms.assetid: ffd3442e-d880-46e9-b848-2365a09a2406
author: rothja
ms.author: jroth
ms.openlocfilehash: 20a91d26ac8c2d1201386cb19bde13b49a3dbada
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725628"
---
# <a name="bound-vs-unbound-text-and-image-columns"></a><span data-ttu-id="a4ea7-102">Colonne di tipo text e image associate e non associate</span><span class="sxs-lookup"><span data-stu-id="a4ea7-102">Bound vs. Unbound Text and Image Columns</span></span>
  <span data-ttu-id="a4ea7-103">Quando si utilizzano i cursori server, il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver ODBC di Native Client è ottimizzato per non trasmettere i dati per le colonne di tipo **Text**, **ntext**o **Image** non associato al momento dell'esecuzione di **SQLFetch** .</span><span class="sxs-lookup"><span data-stu-id="a4ea7-103">When using server cursors, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver is optimized to not transmit the data for unbound **text**, **ntext**, or **image** columns at the time **SQLFetch** is performed.</span></span> <span data-ttu-id="a4ea7-104">I dati di tipo **Text**, **ntext**o **Image** non vengono effettivamente recuperati dal server fino a quando l'applicazione non rilascia [SQLGetData](../native-client-odbc-api/sqlgetdata.md) per la colonna.</span><span class="sxs-lookup"><span data-stu-id="a4ea7-104">The **text**, **ntext**, or **image** data is not actually retrieved from the server until the application issues [SQLGetData](../native-client-odbc-api/sqlgetdata.md) for the column.</span></span>  
  
 <span data-ttu-id="a4ea7-105">Molte applicazioni possono essere scritte in modo che non vengano visualizzati dati di tipo **Text**, **ntext**o **Image** quando un utente scorre verso l'alto e verso il basso un cursore.</span><span class="sxs-lookup"><span data-stu-id="a4ea7-105">Many applications can be written so that no **text**, **ntext**, or **image** data is displayed while a user is simply scrolling up and down in a cursor.</span></span> <span data-ttu-id="a4ea7-106">Quando un utente seleziona una riga per ottenere maggiori dettagli, l'applicazione può quindi chiamare **SQLGetData** per recuperare i dati di tipo **Text**, **ntext**o **Image** .</span><span class="sxs-lookup"><span data-stu-id="a4ea7-106">When a user selects a row to get more detail, the application can then call **SQLGetData** to retrieve the **text**, **ntext**, or **image** data.</span></span> <span data-ttu-id="a4ea7-107">In questo modo si impedisce la trasmissione dei dati di tipo **Text**, **ntext**o **Image** per le righe non selezionate dall'utente e pertanto è possibile impedire la trasmissione di grandi quantità di dati.</span><span class="sxs-lookup"><span data-stu-id="a4ea7-107">This will prevent transmitting the **text**, **ntext**, or **image** data for any of the rows the user does not select, and can therefore prevent the transmission of very large amounts of data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4ea7-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a4ea7-108">See Also</span></span>  
 <span data-ttu-id="a4ea7-109">[Gestione delle colonne di testo e immagini](managing-text-and-image-columns.md) </span><span class="sxs-lookup"><span data-stu-id="a4ea7-109">[Managing Text and Image Columns](managing-text-and-image-columns.md) </span></span>  
 [<span data-ttu-id="a4ea7-110">Comportamenti dei cursori</span><span class="sxs-lookup"><span data-stu-id="a4ea7-110">Cursor Behaviors</span></span>](../native-client-odbc-cursors/cursor-behaviors.md)  
  
  
