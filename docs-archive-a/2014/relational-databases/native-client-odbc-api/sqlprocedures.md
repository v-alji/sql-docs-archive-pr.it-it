---
title: SQLProcedures | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLProcedures function
ms.assetid: ec41f017-f5e0-40ef-913a-65d206068631
author: rothja
ms.author: jroth
ms.openlocfilehash: e37f15841a36eb95c1e9263d137ba2734d622367
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637270"
---
# <a name="sqlprocedures"></a><span data-ttu-id="13923-102">SQLProcedures</span><span class="sxs-lookup"><span data-stu-id="13923-102">SQLProcedures</span></span>
  <span data-ttu-id="13923-103">Tutte le stored procedure di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] restituiscono un valore.</span><span class="sxs-lookup"><span data-stu-id="13923-103">All [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] stored procedures return a value.</span></span> <span data-ttu-id="13923-104">**SQLProcedures** restituisce SQL_PT_FUNCTION per la colonna del set di risultati PROCEDURE_TYPE.</span><span class="sxs-lookup"><span data-stu-id="13923-104">**SQLProcedures** reports SQL_PT_FUNCTION for the result set column PROCEDURE_TYPE.</span></span>  
  
 <span data-ttu-id="13923-105">**SQLProcedures** restituisce SQL_SUCCESS se sono presenti o meno valori per i parametri *CatalogName, SchemaName* o *ProcName* .</span><span class="sxs-lookup"><span data-stu-id="13923-105">**SQLProcedures** returns SQL_SUCCESS whether or not values exist for *CatalogName, SchemaName,* or *ProcName* parameters.</span></span> <span data-ttu-id="13923-106">**SQLFetch** restituisce SQL_NO_DATA quando in questi parametri vengono utilizzati valori non validi.</span><span class="sxs-lookup"><span data-stu-id="13923-106">**SQLFetch** returns SQL_NO_DATA when invalid values are used in these parameters.</span></span>  
  
 <span data-ttu-id="13923-107">**SQLProcedures** può essere eseguito su un cursore del server statico.</span><span class="sxs-lookup"><span data-stu-id="13923-107">**SQLProcedures** can be executed on a static server cursor.</span></span> <span data-ttu-id="13923-108">Il tentativo di eseguire **SQLProcedures** su un cursore aggiornabile (dinamico o keyset) restituirà SQL_SUCCESS_WITH_INFO, a indicare che il tipo di cursore è stato modificato.</span><span class="sxs-lookup"><span data-stu-id="13923-108">An attempt to execute **SQLProcedures** on an updatable (dynamic or keyset) cursor will return SQL_SUCCESS_WITH_INFO, indicating that the cursor type has been changed.</span></span>  
  
 <span data-ttu-id="13923-109">**SQLProcedures** restituisce informazioni su tutte le routine i cui nomi corrispondono a *ProcName* e possono essere eseguite dall'utente corrente o per cui all'utente corrente è stata concessa l'autorizzazione View definition.</span><span class="sxs-lookup"><span data-stu-id="13923-109">**SQLProcedures** returns information about any procedures whose names match *ProcName* and can be executed by the current user, or for which the current user has been granted VIEW DEFINITION permission.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13923-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="13923-110">See Also</span></span>  
 <span data-ttu-id="13923-111">[SQLProcedures (funzione)](https://go.microsoft.com/fwlink/?LinkId=59364) </span><span class="sxs-lookup"><span data-stu-id="13923-111">[SQLProcedures Function](https://go.microsoft.com/fwlink/?LinkId=59364) </span></span>  
 [<span data-ttu-id="13923-112">Dettagli di implementazione dell'API ODBC</span><span class="sxs-lookup"><span data-stu-id="13923-112">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
