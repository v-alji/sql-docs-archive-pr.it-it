---
title: Invio in batch di chiamate a stored procedure | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- stored procedures [ODBC], batching
- ODBC, stored procedures
- SQL Server Native Client ODBC driver, stored procedures
- batches [ODBC]
- ODBC CALL escape sequence
ms.assetid: b7f53e11-15f0-4602-8134-b166160888f0
author: rothja
ms.author: jroth
ms.openlocfilehash: a0df58ce59853ee15b863cbc7bce34041c37fee4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725644"
---
# <a name="batching-stored-procedure-calls"></a><span data-ttu-id="fd732-102">Invio in batch di chiamate a stored procedure</span><span class="sxs-lookup"><span data-stu-id="fd732-102">Batching Stored Procedure Calls</span></span>
  <span data-ttu-id="fd732-103">Il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver ODBC di Native client esegue automaticamente il batch stored procedure le chiamate al server quando appropriato.</span><span class="sxs-lookup"><span data-stu-id="fd732-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver automatically batches stored procedure calls to the server when appropriate.</span></span> <span data-ttu-id="fd732-104">Il driver effettua questa operazione solo quando viene utilizzata la sequenza di escape e non per l'istruzione [!INCLUDE[tsql](../../includes/tsql-md.md)] EXECUTE.</span><span class="sxs-lookup"><span data-stu-id="fd732-104">The driver only does this when the ODBC CALL escape sequence is used; it does not do this for the [!INCLUDE[tsql](../../includes/tsql-md.md)] EXECUTE statement.</span></span> <span data-ttu-id="fd732-105">L'invio in batch di chiamate a stored procedure può ridurre il numero di round trip al server e migliorare significativamente le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="fd732-105">Batching stored procedure calls can reduce the number of round trips to the server and significantly increase performance.</span></span>  
  
 <span data-ttu-id="fd732-106">Il driver invia in batch al server le chiamate alle procedure quando si esegue un batch che contiene più sequenze di escape ODBC CALL.</span><span class="sxs-lookup"><span data-stu-id="fd732-106">The driver batches procedure calls to the server when you execute a batch that contains multiple ODBC CALL escape sequences.</span></span> <span data-ttu-id="fd732-107">Invia inoltre in batch chiamate alle procedure quando si utilizzano matrici di parametri associati con una sequenza di escape ODBC CALL.</span><span class="sxs-lookup"><span data-stu-id="fd732-107">It also batches procedure calls when bound parameter arrays are used with an ODBC CALL escape sequence.</span></span> <span data-ttu-id="fd732-108">Se, ad esempio, si utilizza l'associazione di parametri a livello di riga o di colonna per associare una matrice con cinque elementi ai parametri di un'istruzione SQL ODBC CALL, quando viene chiamato **SQLExecute** o **SQLExecDirect** , il driver invia un singolo batch con cinque chiamate di procedura al server.</span><span class="sxs-lookup"><span data-stu-id="fd732-108">For example, if you use either row-wise or column-wise parameter binding to bind an array with five elements to the parameters of an ODBC CALL SQL statement, when **SQLExecute** or **SQLExecDirect** is called, the driver sends a single batch with five procedure calls to the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd732-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fd732-109">See Also</span></span>  
 [<span data-ttu-id="fd732-110">Esecuzione delle stored procedure</span><span class="sxs-lookup"><span data-stu-id="fd732-110">Running Stored Procedures</span></span>](running-stored-procedures.md)  
  
  
