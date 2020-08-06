---
title: Esecuzione di query (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- ODBC applications, executing queries
- SQL Server Native Client ODBC driver, statements
- ODBC applications, statements
- SQL Server Native Client ODBC driver, queries
- queries [ODBC]
ms.assetid: d935bcba-8ce6-4159-8395-6c86431602ad
author: rothja
ms.author: jroth
ms.openlocfilehash: adc51186803148056401f58f1207d3e9a7abf9c5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624121"
---
# <a name="executing-queries-odbc"></a><span data-ttu-id="b3a91-102">Esecuzione di query (ODBC)</span><span class="sxs-lookup"><span data-stu-id="b3a91-102">Executing Queries (ODBC)</span></span>
  <span data-ttu-id="b3a91-103">Dopo che un'applicazione ODBC inizializza un handle di connessione e si connette a un'origine dati, alloca uno o più handle di istruzione nell'handle di connessione.</span><span class="sxs-lookup"><span data-stu-id="b3a91-103">After an ODBC application initializes a connection handle and connects with a data source, it allocates one or more statement handles on the connection handle.</span></span> <span data-ttu-id="b3a91-104">L'applicazione può quindi eseguire [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] istruzioni nell'handle di istruzione.</span><span class="sxs-lookup"><span data-stu-id="b3a91-104">The application can then execute [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] statements on the statement handle.</span></span> <span data-ttu-id="b3a91-105">Di seguito viene indicata la sequenza generale degli eventi nell'esecuzione di un'istruzione SQL:</span><span class="sxs-lookup"><span data-stu-id="b3a91-105">The general sequence of events in executing an SQL statement is:</span></span>  
  
1.  <span data-ttu-id="b3a91-106">Impostare tutti gli attributi di istruzione necessari.</span><span class="sxs-lookup"><span data-stu-id="b3a91-106">Set any required statement attributes.</span></span>  
  
2.  <span data-ttu-id="b3a91-107">Creare l'istruzione.</span><span class="sxs-lookup"><span data-stu-id="b3a91-107">Construct the statement.</span></span>  
  
3.  <span data-ttu-id="b3a91-108">Eseguire l'istruzione.</span><span class="sxs-lookup"><span data-stu-id="b3a91-108">Execute the statement.</span></span>  
  
4.  <span data-ttu-id="b3a91-109">Recuperare tutti i set di risultati.</span><span class="sxs-lookup"><span data-stu-id="b3a91-109">Retrieve any result sets.</span></span>  
  
 <span data-ttu-id="b3a91-110">Dopo che un'applicazione recupera tutte le righe in tutti i set di risultati restituiti dall'istruzione SQL, può eseguire un'altra query sullo stesso handle di istruzione.</span><span class="sxs-lookup"><span data-stu-id="b3a91-110">After an application retrieves all the rows in all of the result sets returned by the SQL statement, it can execute another query on the same statement handle.</span></span> <span data-ttu-id="b3a91-111">Se un'applicazione determina che non è necessario recuperare tutte le righe in un determinato set di risultati, può annullare il resto del set di risultati chiamando [SQLMoreResults](../native-client-odbc-api/sqlmoreresults.md) o [SQLCloseCursor](../native-client-odbc-api/sqlclosecursor.md).</span><span class="sxs-lookup"><span data-stu-id="b3a91-111">If an application determines that it is not required to retrieve all the rows in a particular result set, it can cancel the rest of the result set by calling either [SQLMoreResults](../native-client-odbc-api/sqlmoreresults.md) or [SQLCloseCursor](../native-client-odbc-api/sqlclosecursor.md).</span></span>  
  
 <span data-ttu-id="b3a91-112">Se in un'applicazione ODBC è necessario eseguire la stessa istruzione SQL più volte con dati diversi, utilizzare un marcatore di parametro rappresentato da un punto interrogativo (?) nella creazione di un'istruzione SQL:</span><span class="sxs-lookup"><span data-stu-id="b3a91-112">If, in an ODBC application, you must execute the same SQL statement multiple times with different data, use a parameter marker denoted by a question mark (?) in the construction of an SQL statement:</span></span>  
  
```  
INSERT INTO MyTable VALUES (?, ?, ?)  
```  
  
 <span data-ttu-id="b3a91-113">Ogni marcatore di parametro può quindi essere associato a una variabile di programma chiamando [SQLBindParameter](../native-client-odbc-api/sqlbindparameter.md).</span><span class="sxs-lookup"><span data-stu-id="b3a91-113">Each parameter marker can then be bound to a program variable by calling [SQLBindParameter](../native-client-odbc-api/sqlbindparameter.md).</span></span>  
  
 <span data-ttu-id="b3a91-114">Al termine dell'esecuzione di tutte le istruzioni SQL e dell'elaborazione dei relativi set di risultati, l'applicazione rilascia l'handle di istruzione.</span><span class="sxs-lookup"><span data-stu-id="b3a91-114">After all SQL statements execute and their result sets process, the application frees the statement handle.</span></span>  
  
 <span data-ttu-id="b3a91-115">Il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver ODBC di Native Client supporta più handle di istruzione per ogni handle di connessione.</span><span class="sxs-lookup"><span data-stu-id="b3a91-115">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver supports multiple statement handles per connection handle.</span></span> <span data-ttu-id="b3a91-116">Le transazioni vengono gestite a livello di connessione, in modo che tutte le operazioni eseguite su tutti gli handle di gestione in un singolo handle di connessione vengano gestite come parte della stessa transazione.</span><span class="sxs-lookup"><span data-stu-id="b3a91-116">Transactions are managed at the connection level, so that all work performed on all statement handles on a single connection handle are managed as part of the same transaction.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b3a91-117">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="b3a91-117">In This Section</span></span>  
  
-   [<span data-ttu-id="b3a91-118">Allocazione di un handle di istruzione</span><span class="sxs-lookup"><span data-stu-id="b3a91-118">Allocating a Statement Handle</span></span>](allocating-a-statement-handle.md)  
  
-   [<span data-ttu-id="b3a91-119">Creazione di un'istruzione SQL &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="b3a91-119">Constructing an SQL Statement &#40;ODBC&#41;</span></span>](constructing-an-sql-statement-odbc.md)  
  
-   [<span data-ttu-id="b3a91-120">Costruzione di istruzioni SQL per i cursori</span><span class="sxs-lookup"><span data-stu-id="b3a91-120">Constructing SQL Statements for Cursors</span></span>](constructing-sql-statements-for-cursors.md)  
  
-   [<span data-ttu-id="b3a91-121">Utilizzo dei parametri delle istruzioni</span><span class="sxs-lookup"><span data-stu-id="b3a91-121">Using Statement Parameters</span></span>](using-statement-parameters.md)  
  
-   [<span data-ttu-id="b3a91-122">Esecuzione di istruzioni &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="b3a91-122">Executing Statements &#40;ODBC&#41;</span></span>](executing-statements/executing-statements-odbc.md)  
  
-   [<span data-ttu-id="b3a91-123">Rilascio di un handle di istruzione</span><span class="sxs-lookup"><span data-stu-id="b3a91-123">Freeing a Statement Handle</span></span>](freeing-a-statement-handle.md)  
  
## <a name="see-also"></a><span data-ttu-id="b3a91-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b3a91-124">See Also</span></span>  
 [<span data-ttu-id="b3a91-125">SQL Server Native Client &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="b3a91-125">SQL Server Native Client &#40;ODBC&#41;</span></span>](../native-client/odbc/sql-server-native-client-odbc.md)  
  
  
