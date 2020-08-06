---
title: SQLCancel | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQLCancel function
ms.assetid: d4c965ae-c1ac-4e9d-b4b9-32b561401106
author: rothja
ms.author: jroth
ms.openlocfilehash: dc3d86229501f80b25fb077788d1835a5f4f5c96
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627700"
---
# <a name="sqlcancel"></a><span data-ttu-id="8adf4-102">SQLCancel</span><span class="sxs-lookup"><span data-stu-id="8adf4-102">SQLCancel</span></span>
  <span data-ttu-id="8adf4-103">Nell'argomento [SQLCancel](https://go.microsoft.com/fwlink/?LinkId=203516) si afferma che in ODBC 2. x, se un'applicazione chiama `SQLCancel` quando non viene eseguita alcuna elaborazione sull'istruzione, `SQLCancel` ha lo stesso effetto di quello `SQLFreeStmt` con l' `SQL_CLOSE` opzione. questo comportamento viene definito solo per completezza e le applicazioni devono chiamare `SQLFreeStmt` o `SQLCloseCursor` per chiudere i cursori.</span><span class="sxs-lookup"><span data-stu-id="8adf4-103">The [SQLCancel](https://go.microsoft.com/fwlink/?LinkId=203516) topic says that in ODBC 2.x, if an application calls `SQLCancel` when no processing is being done on the statement, `SQLCancel` has the same effect as `SQLFreeStmt` with the `SQL_CLOSE` option; this behavior is defined only for completeness and applications should call `SQLFreeStmt` or `SQLCloseCursor` to close cursors.</span></span> <span data-ttu-id="8adf4-104">Tuttavia, anche se l'applicazione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client consente di impostare la versione dell'API ODBC 3.5.x o successiva, nella funzione `SQLCancel` verrà utilizzato il comportamento ODBC 2.x.</span><span class="sxs-lookup"><span data-stu-id="8adf4-104">But even if your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client application sets the ODBC API version to be 3.5.x or later, the `SQLCancel` function will use the ODBC 2.x behavior.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8adf4-105">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8adf4-105">See Also</span></span>  
 <span data-ttu-id="8adf4-106">[SQLCancel](https://go.microsoft.com/fwlink/?LinkId=203516) </span><span class="sxs-lookup"><span data-stu-id="8adf4-106">[SQLCancel](https://go.microsoft.com/fwlink/?LinkId=203516) </span></span>  
 [<span data-ttu-id="8adf4-107">Dettagli di implementazione dell'API ODBC</span><span class="sxs-lookup"><span data-stu-id="8adf4-107">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
