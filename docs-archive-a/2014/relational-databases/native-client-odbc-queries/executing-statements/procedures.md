---
title: Procedure | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- stored procedures [ODBC]
- stored procedures [ODBC], about ODBC stored procedures
- ODBC applications, statements
- statements [ODBC], stored procedures
- ODBC applications, stored procedures
ms.assetid: c64d5f3a-376b-48ef-84f3-b6148ac8600a
author: rothja
ms.author: jroth
ms.openlocfilehash: a7ae4678d324ba7d07ae429793b1f75b57bb15e4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624109"
---
# <a name="procedures"></a><span data-ttu-id="03cc7-102">Procedure</span><span class="sxs-lookup"><span data-stu-id="03cc7-102">Procedures</span></span>
  <span data-ttu-id="03cc7-103">Una stored procedure è un oggetto eseguibile precompilato che contiene una o più istruzioni [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="03cc7-103">A stored procedure is a precompiled executable object that contains one or more [!INCLUDE[tsql](../../../includes/tsql-md.md)] statements.</span></span> <span data-ttu-id="03cc7-104">Le stored procedure possono includere parametri di input e di output e possono restituire anche codice di tipo integer.</span><span class="sxs-lookup"><span data-stu-id="03cc7-104">Stored procedures can have input and output parameters and can also put out an integer return code.</span></span> <span data-ttu-id="03cc7-105">Un'applicazione può enumerare le stored procedure disponibili utilizzando funzioni di catalogo.</span><span class="sxs-lookup"><span data-stu-id="03cc7-105">An application can enumerate available stored procedures by using catalog functions.</span></span>  
  
 <span data-ttu-id="03cc7-106">Le applicazioni ODBC destinate a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] devono utilizzare solo l'esecuzione diretta per chiamare una stored procedure.</span><span class="sxs-lookup"><span data-stu-id="03cc7-106">ODBC applications that target [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] should only use direct execution to call a stored procedure.</span></span> <span data-ttu-id="03cc7-107">Quando si è connessi a versioni precedenti di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , il [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] driver ODBC di Native Client implementa la [funzione SQLPrepare](https://go.microsoft.com/fwlink/?LinkId=59360) creando una stored procedure temporanea, che viene quindi chiamata in **SQLExecute**.</span><span class="sxs-lookup"><span data-stu-id="03cc7-107">When connected to earlier versions of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver implements [SQLPrepare Function](https://go.microsoft.com/fwlink/?LinkId=59360) by creating a temporary stored procedure, which is then called on **SQLExecute**.</span></span> <span data-ttu-id="03cc7-108">Viene aggiunto un sovraccarico per fare in modo che **SQLPrepare** crei una stored procedure temporanea che chiama solo il stored procedure di destinazione anziché eseguire direttamente il stored procedure di destinazione.</span><span class="sxs-lookup"><span data-stu-id="03cc7-108">It adds overhead to have **SQLPrepare** create a temporary stored procedure that only calls the target stored procedure versus directly executing the target stored procedure.</span></span> <span data-ttu-id="03cc7-109">Anche in caso di connessione a un'istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], la preparazione di una chiamata richiede round trip aggiuntivo in rete e la compilazione di un piano di esecuzione che chiami solo il piano di esecuzione della stored procedure.</span><span class="sxs-lookup"><span data-stu-id="03cc7-109">Even when connected to an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], preparing a call requires an extra round trip across the network and the building of an execution plan that just calls the stored procedure execution plan.</span></span>  
  
 <span data-ttu-id="03cc7-110">Le applicazioni ODBC devono utilizzare la sintassi ODBC CALL in caso di esecuzione di una stored procedure.</span><span class="sxs-lookup"><span data-stu-id="03cc7-110">ODBC applications should use the ODBC CALL syntax when executing a stored procedure.</span></span> <span data-ttu-id="03cc7-111">Il driver è ottimizzato per l'utilizzo di un meccanismo di chiamata a procedure remote per chiamare la procedura quando si utilizza la sintassi ODBC CALL.</span><span class="sxs-lookup"><span data-stu-id="03cc7-111">The driver is optimized to use a remote procedure call mechanism to call the procedure when the ODBC CALL syntax is used.</span></span> <span data-ttu-id="03cc7-112">Si tratta di un meccanismo molto più efficiente di quello utilizzato per inviare un'istruzione [!INCLUDE[tsql](../../../includes/tsql-md.md)] EXECUTE al server.</span><span class="sxs-lookup"><span data-stu-id="03cc7-112">This is more efficient than the mechanism used to send a [!INCLUDE[tsql](../../../includes/tsql-md.md)] EXECUTE statement to the server.</span></span>  
  
 <span data-ttu-id="03cc7-113">Per ulteriori informazioni, vedere [esecuzione di stored procedure](../../native-client-odbc-stored-procedures/running-stored-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="03cc7-113">For more information, see [Running Stored Procedures](../../native-client-odbc-stored-procedures/running-stored-procedures.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03cc7-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="03cc7-114">See Also</span></span>  
 [<span data-ttu-id="03cc7-115">Esecuzione di istruzioni &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="03cc7-115">Executing Statements &#40;ODBC&#41;</span></span>](executing-statements-odbc.md)  
  
  
