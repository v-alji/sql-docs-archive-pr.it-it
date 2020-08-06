---
title: SQLNumResultCols | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLNumResultCols function
ms.assetid: f79d8b3c-521e-4e50-a564-21d73ae5767b
author: rothja
ms.author: jroth
ms.openlocfilehash: 45e72165eef621dc377b02ed3d2e7e1e3cf7ab8e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637274"
---
# <a name="sqlnumresultcols"></a><span data-ttu-id="4ef54-102">SQLNumResultCols</span><span class="sxs-lookup"><span data-stu-id="4ef54-102">SQLNumResultCols</span></span>
  <span data-ttu-id="4ef54-103">Per le istruzioni eseguite, il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver ODBC di Native client non visita il server per segnalare il numero di colonne in un set di risultati.</span><span class="sxs-lookup"><span data-stu-id="4ef54-103">For executed statements, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver does not visit the server to report the number of columns in a result set.</span></span> <span data-ttu-id="4ef54-104">In questo caso, non `SQLNumResultCols` causa un round trip del server.</span><span class="sxs-lookup"><span data-stu-id="4ef54-104">In this case, `SQLNumResultCols` does not cause a server roundtrip.</span></span> <span data-ttu-id="4ef54-105">Analogamente a [SQLDescribeCol](sqldescribecol.md) e [SQLColAttribute](sqlcolattribute.md), `SQLNumResultCols` la chiamata a istruzioni preparate ma non eseguite genera un round trip del server.</span><span class="sxs-lookup"><span data-stu-id="4ef54-105">Like [SQLDescribeCol](sqldescribecol.md) and [SQLColAttribute](sqlcolattribute.md), calling `SQLNumResultCols` on prepared but not executed statements generates a server roundtrip.</span></span>  
  
 <span data-ttu-id="4ef54-106">Quando un'istruzione o un batch di istruzioni [!INCLUDE[tsql](../../includes/tsql-md.md)] restituisce più set di righe di risultati, è possibile che il numero di colonne del set di risultati cambi da un set all'altro.</span><span class="sxs-lookup"><span data-stu-id="4ef54-106">When a [!INCLUDE[tsql](../../includes/tsql-md.md)] statement or statement batch returns multiple result row sets, it is possible for the number of result set columns to change from one set to another.</span></span> <span data-ttu-id="4ef54-107">`SQLNumResultCols`deve essere chiamato per ogni set.</span><span class="sxs-lookup"><span data-stu-id="4ef54-107">`SQLNumResultCols` should be called for each set.</span></span> <span data-ttu-id="4ef54-108">Quando il numero di colonne cambia, l'applicazione deve riassociare i valori dei dati prima di recuperare i risultati delle righe.</span><span class="sxs-lookup"><span data-stu-id="4ef54-108">When the number of columns changes, the application should rebind data values prior to fetching row results.</span></span> <span data-ttu-id="4ef54-109">Per ulteriori informazioni sulla gestione di più restituzione di set di risultati, vedere [SQLMoreResults](sqlmoreresults.md).</span><span class="sxs-lookup"><span data-stu-id="4ef54-109">For more information about handling multiple result set returns, see [SQLMoreResults](sqlmoreresults.md).</span></span>  
  
 <span data-ttu-id="4ef54-110">I miglioramenti apportati al motore di database a partire da [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] consentono a SQLNumResultCols di ottenere descrizioni più accurate dei risultati previsti.</span><span class="sxs-lookup"><span data-stu-id="4ef54-110">Improvements in the database engine starting with [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] allow SQLNumResultCols to obtain more accurate descriptions of the expected results.</span></span> <span data-ttu-id="4ef54-111">Questi risultati più accurati possono essere diversi dai valori restituiti da SQLNumResultCols nelle versioni precedenti di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4ef54-111">These more accurate results may differ from the values returned by SQLNumResultCols in previous versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="4ef54-112">Per altre informazioni, vedere [Metadata Discovery](../native-client/features/metadata-discovery.md).</span><span class="sxs-lookup"><span data-stu-id="4ef54-112">For more information, see [Metadata Discovery](../native-client/features/metadata-discovery.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ef54-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4ef54-113">See Also</span></span>  
 <span data-ttu-id="4ef54-114">[SQLNumResultCols (funzione)](https://go.microsoft.com/fwlink/?LinkId=59359) </span><span class="sxs-lookup"><span data-stu-id="4ef54-114">[SQLNumResultCols Function](https://go.microsoft.com/fwlink/?LinkId=59359) </span></span>  
 [<span data-ttu-id="4ef54-115">Dettagli di implementazione dell'API ODBC</span><span class="sxs-lookup"><span data-stu-id="4ef54-115">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
