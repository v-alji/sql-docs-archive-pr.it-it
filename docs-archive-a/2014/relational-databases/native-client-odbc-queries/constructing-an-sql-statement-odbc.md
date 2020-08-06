---
title: Creazione di un'istruzione SQL (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client ODBC driver, statements
- statements [ODBC], constructing
- ODBC applications, statements
ms.assetid: 0acc71e2-8004-4dd8-8592-05c022bdd692
author: rothja
ms.author: jroth
ms.openlocfilehash: 1c454f936c49335555ca09b190e4d604c9fbad64
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624124"
---
# <a name="constructing-an-sql-statement-odbc"></a><span data-ttu-id="242ea-102">Costruzione di un'istruzione SQL (ODBC)</span><span class="sxs-lookup"><span data-stu-id="242ea-102">Constructing an SQL Statement (ODBC)</span></span>
  <span data-ttu-id="242ea-103">Le applicazioni ODBC eseguono l'accesso al database quasi sempre mediante l'esecuzione delle istruzioni [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="242ea-103">ODBC applications perform almost all of their database access by executing [!INCLUDE[tsql](../../includes/tsql-md.md)] statements.</span></span> <span data-ttu-id="242ea-104">Il formato di tali istruzioni dipende dai requisiti dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="242ea-104">The form of these statements depends on the application requirements.</span></span> <span data-ttu-id="242ea-105">Le istruzioni SQL possono essere costruite nei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="242ea-105">SQL statements can be constructed in the following ways:</span></span>  
  
-   <span data-ttu-id="242ea-106">Hard-coded</span><span class="sxs-lookup"><span data-stu-id="242ea-106">Hard-coded</span></span>  
  
     <span data-ttu-id="242ea-107">Istruzioni statiche eseguite da un'applicazione come attività fissa.</span><span class="sxs-lookup"><span data-stu-id="242ea-107">Static statements performed by an application as a fixed task.</span></span>  
  
-   <span data-ttu-id="242ea-108">In fase di esecuzione</span><span class="sxs-lookup"><span data-stu-id="242ea-108">Constructed at run time</span></span>  
  
     <span data-ttu-id="242ea-109">Istruzioni SQL costruite in fase di esecuzione che consentono all'utente di personalizzare l'istruzione servendosi di clausole comuni, ad esempio SELECT, WHERE e ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="242ea-109">SQL statements constructed at run time that enable the user to tailor the statement by using common clauses, such as SELECT, WHERE, and ORDER BY.</span></span> <span data-ttu-id="242ea-110">Sono incluse query ad hoc immesse dagli utenti.</span><span class="sxs-lookup"><span data-stu-id="242ea-110">This includes ad hoc queries entered by users.</span></span>  
  
 <span data-ttu-id="242ea-111">Il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver ODBC del client analizza le istruzioni SQL solo per la sintassi ODBC e ISO non supportata direttamente da [!INCLUDE[ssDE](../../includes/ssde-md.md)] , in cui il driver viene trasformato [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="242ea-111">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Client ODBC driver parses SQL statements only for ODBC and ISO syntax not directly supported by the [!INCLUDE[ssDE](../../includes/ssde-md.md)], which the driver transforms into [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="242ea-112">Tutte le altre sintassi SQL vengono passate all'oggetto [!INCLUDE[ssDE](../../includes/ssde-md.md)] invariato, in cui [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] determinerà se è valido [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="242ea-112">All other SQL syntax is passed to the [!INCLUDE[ssDE](../../includes/ssde-md.md)] unchanged, where [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will determine if it is valid [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="242ea-113">Questo approccio comporta due vantaggi:</span><span class="sxs-lookup"><span data-stu-id="242ea-113">This approach yields two benefits:</span></span>  
  
-   <span data-ttu-id="242ea-114">Riduzione dell'overhead</span><span class="sxs-lookup"><span data-stu-id="242ea-114">Reduced overhead</span></span>  
  
     <span data-ttu-id="242ea-115">L'elaborazione dell'overhead per il driver viene ridotto al minimo, in quanto l'analisi deve essere eseguita solo per un piccolo set di clausole ODBC e ISO.</span><span class="sxs-lookup"><span data-stu-id="242ea-115">Processing overhead for the driver is minimized because it only has to scan for a small set of ODBC and ISO clauses.</span></span>  
  
-   <span data-ttu-id="242ea-116">Flessibilità</span><span class="sxs-lookup"><span data-stu-id="242ea-116">Flexibility</span></span>  
  
     <span data-ttu-id="242ea-117">I programmatori possono personalizzare la portabilità delle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="242ea-117">Programmers can tailor the portability of their applications.</span></span> <span data-ttu-id="242ea-118">Per migliorare la portabilità rispetto a più database, utilizzare principalmente la sintassi ODBC e ISO.</span><span class="sxs-lookup"><span data-stu-id="242ea-118">To enhance portability against multiple databases, use primarily ODBC and ISO syntax.</span></span> <span data-ttu-id="242ea-119">Per utilizzare miglioramenti specifici di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], utilizzare la sintassi di [!INCLUDE[tsql](../../includes/tsql-md.md)] appropriata.</span><span class="sxs-lookup"><span data-stu-id="242ea-119">To use enhancements specific to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], use the appropriate [!INCLUDE[tsql](../../includes/tsql-md.md)] syntax.</span></span> <span data-ttu-id="242ea-120">Il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver ODBC di Native Client supporta la [!INCLUDE[tsql](../../includes/tsql-md.md)] sintassi completa, pertanto le applicazioni basate su ODBC possono sfruttare tutte le funzionalità di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="242ea-120">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver supports the complete [!INCLUDE[tsql](../../includes/tsql-md.md)] syntax so ODBC-based applications can take advantage of all the features in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="242ea-121">L'elenco di colonne di un'istruzione SELECT deve contenere solo le colonne richieste per eseguire l'attività corrente.</span><span class="sxs-lookup"><span data-stu-id="242ea-121">The column list in a SELECT statement should contain only the columns required to perform the current task.</span></span> <span data-ttu-id="242ea-122">In questo modo non solo si riduce la quantità di dati inviati attraverso la rete, ma anche l'effetto delle modifiche del database sull'applicazione.</span><span class="sxs-lookup"><span data-stu-id="242ea-122">Not only does this reduce the amount of data sent across the network, but also it reduces the effect of database changes on the application.</span></span> <span data-ttu-id="242ea-123">Se in un'applicazione non si fa riferimento a una colonna di una tabella, l'applicazione non viene interessata dalle modifiche apportate alla colonna.</span><span class="sxs-lookup"><span data-stu-id="242ea-123">If an application does not reference a column from a table, then the application is not affected by any changes made to that column.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="242ea-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="242ea-124">See Also</span></span>  
 [<span data-ttu-id="242ea-125">Esecuzione di query &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="242ea-125">Executing Queries &#40;ODBC&#41;</span></span>](executing-queries-odbc.md)  
  
  
