---
title: Elaborazione dei risultati delle stored procedure | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- ODBC, stored procedures
- SQL Server Native Client ODBC driver, stored procedures
- stored procedures [ODBC], results
ms.assetid: 788ef2a4-17de-4526-960b-46bf29aafc9f
author: rothja
ms.author: jroth
ms.openlocfilehash: 5f37a6d8beff88748fa944293bd67f449d29eff2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725636"
---
# <a name="processing-stored-procedure-results"></a><span data-ttu-id="55d62-102">Risultati dell'elaborazione delle stored procedure</span><span class="sxs-lookup"><span data-stu-id="55d62-102">Processing Stored Procedure Results</span></span>
  <span data-ttu-id="55d62-103">Per le stored procedure di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sono disponibili quattro meccanismi di restituzione dei dati:</span><span class="sxs-lookup"><span data-stu-id="55d62-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] stored procedures have four mechanisms used to return data:</span></span>  
  
-   <span data-ttu-id="55d62-104">Ogni istruzione SELECT di una stored procedure genera un set di risultati.</span><span class="sxs-lookup"><span data-stu-id="55d62-104">Each SELECT statement in the procedure generates a result set.</span></span>  
  
-   <span data-ttu-id="55d62-105">La procedura può restituire dati tramite parametri di output.</span><span class="sxs-lookup"><span data-stu-id="55d62-105">The procedure can return data through output parameters.</span></span>  
  
-   <span data-ttu-id="55d62-106">Un parametro di output del cursore può passare nuovamente un cursore del server [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="55d62-106">A cursor output parameter can pass back a [!INCLUDE[tsql](../../includes/tsql-md.md)] server cursor.</span></span>  
  
-   <span data-ttu-id="55d62-107">La procedura può avere un codice restituito di tipo integer.</span><span class="sxs-lookup"><span data-stu-id="55d62-107">The procedure can have an integer return code.</span></span>  
  
 <span data-ttu-id="55d62-108">Le applicazioni devono essere in grado di gestire tutti questi output dalle stored procedure.</span><span class="sxs-lookup"><span data-stu-id="55d62-108">Applications must be able to handle all these outputs from stored procedures.</span></span> <span data-ttu-id="55d62-109">L'istruzione CALL o EXECUTE deve includere marcatori di parametro per il codice restituito e i parametri di output.</span><span class="sxs-lookup"><span data-stu-id="55d62-109">The CALL or EXECUTE statement should include parameter markers for the return code and output parameters.</span></span> <span data-ttu-id="55d62-110">Utilizzare [SQLBindParameter](../native-client-odbc-api/sqlbindparameter.md) per associarli tutti come parametri di output e il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver ODBC di Native Client trasferirà i valori di output alle variabili associate.</span><span class="sxs-lookup"><span data-stu-id="55d62-110">Use [SQLBindParameter](../native-client-odbc-api/sqlbindparameter.md) to bind them all as output parameters and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver will transfer the output values to the bound variables.</span></span> <span data-ttu-id="55d62-111">I parametri di output e i codici restituiti sono gli ultimi elementi restituiti al client da e [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] non vengono restituiti all'applicazione fino a quando [SQLMoreResults](../native-client-odbc-api/sqlmoreresults.md) non restituisce SQL_NO_DATA.</span><span class="sxs-lookup"><span data-stu-id="55d62-111">Output parameters and return codes are the last items returned to the client by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]; they are not returned to the application until [SQLMoreResults](../native-client-odbc-api/sqlmoreresults.md) returns SQL_NO_DATA.</span></span>  
  
 <span data-ttu-id="55d62-112">ODBC non supporta i parametri di cursore [!INCLUDE[tsql](../../includes/tsql-md.md)] di associazione.</span><span class="sxs-lookup"><span data-stu-id="55d62-112">ODBC does not support binding [!INCLUDE[tsql](../../includes/tsql-md.md)] cursor parameters.</span></span> <span data-ttu-id="55d62-113">Dal momento che tutti i parametri di output devono essere associati prima di eseguire una stored procedure, le stored procedure [!INCLUDE[tsql](../../includes/tsql-md.md)] che contengono un parametro di cursore di output non possono essere chiamate dalle applicazioni ODBC.</span><span class="sxs-lookup"><span data-stu-id="55d62-113">Because all output parameters must be bound before executing a procedure, any [!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedure that contains an output cursor parameter cannot be called by ODBC applications.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55d62-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="55d62-114">See Also</span></span>  
 [<span data-ttu-id="55d62-115">Esecuzione delle stored procedure</span><span class="sxs-lookup"><span data-stu-id="55d62-115">Running Stored Procedures</span></span>](running-stored-procedures.md)  
  
  
