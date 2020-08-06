---
title: SQLGetCursorName | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLGetCursorName function
ms.assetid: 3a427a23-28ef-49aa-b9ec-6cab0914bdf3
author: rothja
ms.author: jroth
ms.openlocfilehash: 01ce6e42b4e8753d07309ec7ce298d4f743d4a6d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623254"
---
# <a name="sqlgetcursorname"></a><span data-ttu-id="4bdc5-102">SQLGetCursorName</span><span class="sxs-lookup"><span data-stu-id="4bdc5-102">SQLGetCursorName</span></span>
  <span data-ttu-id="4bdc5-103">Se l'applicazione non specifica un nome di cursore, il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver ODBC di Native client ne genera uno per l'applicazione durante la generazione del cursore.</span><span class="sxs-lookup"><span data-stu-id="4bdc5-103">If the application does not specify a cursor name, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver generates one for the application upon cursor generation.</span></span> <span data-ttu-id="4bdc5-104">L'applicazione può utilizzare **SQLGetCursorName** per recuperare il nome del cursore definito dal driver per le istruzioni Update e Delete posizionate.</span><span class="sxs-lookup"><span data-stu-id="4bdc5-104">The application can use **SQLGetCursorName** to retrieve the driver-defined cursor name for positioned UPDATE and DELETE statements.</span></span> <span data-ttu-id="4bdc5-105">Non è necessario che l'applicazione chiami **SQLSetCursorName** per sfruttare le istruzioni di manipolazione dei dati posizionate.</span><span class="sxs-lookup"><span data-stu-id="4bdc5-105">The application does not need to call **SQLSetCursorName** to take advantage of positioned data manipulation statements.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bdc5-106">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4bdc5-106">See Also</span></span>  
 <span data-ttu-id="4bdc5-107">[SQLGetCursorName (funzione)](https://go.microsoft.com/fwlink/?LinkId=59349) </span><span class="sxs-lookup"><span data-stu-id="4bdc5-107">[SQLGetCursorName Function](https://go.microsoft.com/fwlink/?LinkId=59349) </span></span>  
 [<span data-ttu-id="4bdc5-108">Dettagli di implementazione dell'API ODBC</span><span class="sxs-lookup"><span data-stu-id="4bdc5-108">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
