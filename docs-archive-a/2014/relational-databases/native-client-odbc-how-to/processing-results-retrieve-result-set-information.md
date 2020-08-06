---
title: Recuperare informazioni sul set di risultati (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- result sets [ODBC]
- result sets [ODBC], fetching
ms.assetid: 34f235e4-f80b-4123-8764-9deb18506f14
author: rothja
ms.author: jroth
ms.openlocfilehash: 0f7ed275eb9b6558a77160c3c7fb2fc233c199cc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626748"
---
# <a name="retrieve-result-set-information-odbc"></a><span data-ttu-id="973b0-102">Recuperare informazioni sul set di risultati (ODBC)</span><span class="sxs-lookup"><span data-stu-id="973b0-102">Retrieve Result Set Information (ODBC)</span></span>
    
### <a name="to-get-information-about-a-result-set"></a><span data-ttu-id="973b0-103">Per recuperare informazioni su un set di risultati</span><span class="sxs-lookup"><span data-stu-id="973b0-103">To get information about a result set</span></span>  
  
1.  <span data-ttu-id="973b0-104">Chiamare [SQLNumResultCols](../native-client-odbc-api/sqlnumresultcols.md) per ottenere il numero di colonne nel set di risultati.</span><span class="sxs-lookup"><span data-stu-id="973b0-104">Call [SQLNumResultCols](../native-client-odbc-api/sqlnumresultcols.md) to get the number of columns in the result set.</span></span>  
  
2.  <span data-ttu-id="973b0-105">Per ogni colonna del set di risultati, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="973b0-105">For each column in the result set:</span></span>  
  
    -   <span data-ttu-id="973b0-106">Chiamare [SQLDescribeCol](../native-client-odbc-api/sqldescribecol.md) per ottenere informazioni sulla colonna risultato.</span><span class="sxs-lookup"><span data-stu-id="973b0-106">Call [SQLDescribeCol](../native-client-odbc-api/sqldescribecol.md) to get information about the result column.</span></span>  
  
     <span data-ttu-id="973b0-107">Oppure</span><span class="sxs-lookup"><span data-stu-id="973b0-107">Or</span></span>  
  
    -   <span data-ttu-id="973b0-108">Chiamare [SQLColAttribute](../native-client-odbc-api/sqlcolattribute.md) per ottenere informazioni specifiche sul descrittore sulla colonna risultato.</span><span class="sxs-lookup"><span data-stu-id="973b0-108">Call [SQLColAttribute](../native-client-odbc-api/sqlcolattribute.md) to get specific descriptor information about the result column.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="973b0-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="973b0-109">See Also</span></span>  
 <span data-ttu-id="973b0-110">[Procedure per l'elaborazione dei risultati &#40;ODBC&#41;](../../database-engine/dev-guide/processing-results-how-to-topics-odbc.md) </span><span class="sxs-lookup"><span data-stu-id="973b0-110">[Processing Results How-to Topics &#40;ODBC&#41;](../../database-engine/dev-guide/processing-results-how-to-topics-odbc.md) </span></span>  
 [<span data-ttu-id="973b0-111">Determinazione delle caratteristiche di un set di risultati &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="973b0-111">Determining the Characteristics of a Result Set &#40;ODBC&#41;</span></span>](../native-client-odbc-results/determining-the-characteristics-of-a-result-set-odbc.md)  
  
  
