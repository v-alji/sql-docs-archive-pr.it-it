---
title: SQLNativeSql | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLNativeSql function
ms.assetid: 2d999fec-9e22-4514-ad5f-22a64b82f95b
author: rothja
ms.author: jroth
ms.openlocfilehash: 433b086dc36a79cb82868edebac9f0a4814c21fe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637275"
---
# <a name="sqlnativesql"></a><span data-ttu-id="6a3a2-102">SQLNativeSql</span><span class="sxs-lookup"><span data-stu-id="6a3a2-102">SQLNativeSql</span></span>
  <span data-ttu-id="6a3a2-103">Il driver ODBC di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client soddisfa richieste di **SQLNativeSql** senza visitare il server.</span><span class="sxs-lookup"><span data-stu-id="6a3a2-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver satisfies **SQLNativeSql** requests without visiting the server.</span></span> <span data-ttu-id="6a3a2-104">La funzione verifica in modo efficiente la sintassi di istruzioni SQL.</span><span class="sxs-lookup"><span data-stu-id="6a3a2-104">The function efficiently tests the syntax of SQL statements.</span></span> <span data-ttu-id="6a3a2-105">Il controllo della sintassi non determina se gli identificatori o i risultati di espressioni nelle istruzioni SQL sono validi. È possibile che l'esecuzione del formato SQL nativo di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] restituito da **SQLNativeSql** non riesca.</span><span class="sxs-lookup"><span data-stu-id="6a3a2-105">Syntax checking does not determine if identifiers or the results of expressions in the SQL statements are valid, and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] native SQL returned by **SQLNativeSql** can fail to run.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a3a2-106">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6a3a2-106">See Also</span></span>  
 <span data-ttu-id="6a3a2-107">[SQLNativeSql (funzione)](https://go.microsoft.com/fwlink/?LinkID=59358) </span><span class="sxs-lookup"><span data-stu-id="6a3a2-107">[SQLNativeSql Function](https://go.microsoft.com/fwlink/?LinkID=59358) </span></span>  
 [<span data-ttu-id="6a3a2-108">Dettagli di implementazione dell'API ODBC</span><span class="sxs-lookup"><span data-stu-id="6a3a2-108">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
