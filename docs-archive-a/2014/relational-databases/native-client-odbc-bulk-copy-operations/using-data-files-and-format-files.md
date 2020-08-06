---
title: Uso di file di dati e file di formato | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- bulk copy [ODBC], file formats
- ODBC, functions
- SQL Server Native Client ODBC driver, bulk copy
- bulk copy [SQL Server Native Client]
- ODBC, bulk copy operations
- bulk copy [ODBC], data files
ms.assetid: c01b7155-3f0a-473d-90b7-87a97bc56ca5
author: rothja
ms.author: jroth
ms.openlocfilehash: 4e0ee92f79e2c8cab9605db0188e01898df8c23e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725708"
---
# <a name="using-data-files-and-format-files"></a><span data-ttu-id="22c8c-102">Utilizzo di file di dati e file di formato</span><span class="sxs-lookup"><span data-stu-id="22c8c-102">Using Data Files and Format Files</span></span>
  <span data-ttu-id="22c8c-103">Il programma per la copia bulk più semplice effettua le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="22c8c-103">The simplest bulk copy program does the following:</span></span>  
  
1.  <span data-ttu-id="22c8c-104">Chiama [bcp_init](../native-client-odbc-extensions-bulk-copy-functions/bcp-init.md) per specificare la copia bulk (set BCP_OUT) da una tabella o da una vista a un file di dati.</span><span class="sxs-lookup"><span data-stu-id="22c8c-104">Calls [bcp_init](../native-client-odbc-extensions-bulk-copy-functions/bcp-init.md) to specify bulk copying out (set BCP_OUT) from a table or view to a data file.</span></span>  
  
2.  <span data-ttu-id="22c8c-105">Chiama [bcp_exec](../native-client-odbc-extensions-bulk-copy-functions/bcp-exec.md) per eseguire l'operazione di copia bulk.</span><span class="sxs-lookup"><span data-stu-id="22c8c-105">Calls [bcp_exec](../native-client-odbc-extensions-bulk-copy-functions/bcp-exec.md) to execute the bulk copy operation.</span></span>  
  
 <span data-ttu-id="22c8c-106">Poiché il file di dati viene creato in modalità nativa, i dati di tutte le colonne nella tabella o nella vista vengono archiviati nel file di dati con lo stesso formato utilizzato nel database.</span><span class="sxs-lookup"><span data-stu-id="22c8c-106">The data file is created in native mode; therefore, data from all columns in the table or view are stored in the data file in the same format as in the database.</span></span> <span data-ttu-id="22c8c-107">Il file può essere quindi oggetto di copia bulk in un server utilizzando questi stessi passaggi e impostando DB_IN anziché DB_OUT.</span><span class="sxs-lookup"><span data-stu-id="22c8c-107">The file can then be bulk copied into a server by using these same steps and setting DB_IN instead of DB_OUT.</span></span> <span data-ttu-id="22c8c-108">È possibile procedere in questo modo solo se le tabelle di origine e di destinazione hanno una struttura identica.</span><span class="sxs-lookup"><span data-stu-id="22c8c-108">This works only if both the source and target tables have exactly the same structure.</span></span> <span data-ttu-id="22c8c-109">Il file di dati risultante può essere anche un input per l'utilità **bcp** utilizzando l'opzione **/n** (modalità nativa).</span><span class="sxs-lookup"><span data-stu-id="22c8c-109">The resulting data file can also be input to the **bcp** utility by using the **/n** (native mode) switch.</span></span>  
  
 <span data-ttu-id="22c8c-110">Per eseguire la copia bulk dal set di risultati di un'istruzione [!INCLUDE[tsql](../../includes/tsql-md.md)] anziché direttamente da una tabella o una vista:</span><span class="sxs-lookup"><span data-stu-id="22c8c-110">To bulk copy out the result set of a [!INCLUDE[tsql](../../includes/tsql-md.md)] statement instead of directly from a table or view:</span></span>  
  
1.  <span data-ttu-id="22c8c-111">Chiamare **bcp_init** per specificare la copia bulk, ma specificare null per il nome della tabella.</span><span class="sxs-lookup"><span data-stu-id="22c8c-111">Call **bcp_init** to specify bulk copying out, but specify NULL for the table name.</span></span>  
  
2.  <span data-ttu-id="22c8c-112">Chiamare [bcp_control](../native-client-odbc-extensions-bulk-copy-functions/bcp-control.md) con *EOPTION* impostato su BCPHINTS e *iValue* impostato su un puntatore a una stringa SQLTCHAR contenente l'istruzione Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="22c8c-112">Call [bcp_control](../native-client-odbc-extensions-bulk-copy-functions/bcp-control.md) with *eOption* set to BCPHINTS and *iValue* set to a pointer to a SQLTCHAR string containing the Transact-SQL statement.</span></span>  
  
3.  <span data-ttu-id="22c8c-113">Chiamare **bcp_exec** per eseguire l'operazione di copia bulk.</span><span class="sxs-lookup"><span data-stu-id="22c8c-113">Call **bcp_exec** to execute the bulk copy operation.</span></span>  
  
 <span data-ttu-id="22c8c-114">L'istruzione [!INCLUDE[tsql](../../includes/tsql-md.md)] può essere qualsiasi istruzione che genera un set di risultati.</span><span class="sxs-lookup"><span data-stu-id="22c8c-114">The [!INCLUDE[tsql](../../includes/tsql-md.md)] statement can be any statement that generates a result set.</span></span> <span data-ttu-id="22c8c-115">Il file di dati creato contiene il primo set di risultati dell'istruzione [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="22c8c-115">The data file is created containing the first result set of the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement.</span></span> <span data-ttu-id="22c8c-116">Nella copia bulk viene ignorato qualsiasi set di risultati successivo al primo se tramite l'istruzione [!INCLUDE[tsql](../../includes/tsql-md.md)] vengono generati più set di risultati.</span><span class="sxs-lookup"><span data-stu-id="22c8c-116">Bulk copy ignores any result set after the first if the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement generates multiple result sets.</span></span>  
  
 <span data-ttu-id="22c8c-117">Per creare un file di dati in cui i dati della colonna vengono archiviati in un formato diverso da quello della tabella, chiamare [bcp_columns](../native-client-odbc-extensions-bulk-copy-functions/bcp-columns.md) per specificare il numero di colonne che verranno modificate, quindi chiamare [bcp_colfmt](../native-client-odbc-extensions-bulk-copy-functions/bcp-colfmt.md) per ogni colonna di cui si desidera modificare il formato.</span><span class="sxs-lookup"><span data-stu-id="22c8c-117">To create a data file in which column data is stored in a different format than in the table, call [bcp_columns](../native-client-odbc-extensions-bulk-copy-functions/bcp-columns.md) to specify how many columns will be changed, then call [bcp_colfmt](../native-client-odbc-extensions-bulk-copy-functions/bcp-colfmt.md) for each column whose format you want to change.</span></span> <span data-ttu-id="22c8c-118">Questa operazione viene eseguita dopo aver chiamato **bcp_init** ma prima di chiamare **bcp_exec**.</span><span class="sxs-lookup"><span data-stu-id="22c8c-118">This is done after calling **bcp_init** but before calling **bcp_exec**.</span></span> <span data-ttu-id="22c8c-119">**bcp_colfmt** specifica il formato in cui i dati della colonna vengono archiviati nel file di dati.</span><span class="sxs-lookup"><span data-stu-id="22c8c-119">**bcp_colfmt** specifies the format in which the column's data is stored in the data file.</span></span> <span data-ttu-id="22c8c-120">Può essere usato durante la copia bulk in o in uscita. È inoltre possibile utilizzare **bcp_colfmt** per impostare i terminatori di riga e di colonna.</span><span class="sxs-lookup"><span data-stu-id="22c8c-120">It can be used when bulk copying in or out. You can also use **bcp_colfmt** to set the row and column terminators.</span></span> <span data-ttu-id="22c8c-121">Se, ad esempio, i dati non contengono caratteri di tabulazione, è possibile creare un file delimitato da tabulazioni usando **bcp_colfmt** per impostare il carattere di tabulazione come carattere di terminazione per ogni colonna.</span><span class="sxs-lookup"><span data-stu-id="22c8c-121">For example, if your data contains no tab characters, you can create a tab-delimited file by using **bcp_colfmt** to set the tab character as the terminator for each column.</span></span>  
  
 <span data-ttu-id="22c8c-122">Quando si esegue la copia bulk e si utilizza **bcp_colfmt**, è possibile creare facilmente un file di formato che descrive il file di dati creato chiamando [bcp_writefmt](../native-client-odbc-extensions-bulk-copy-functions/bcp-writefmt.md) dopo l'ultima chiamata al **bcp_colfmt**.</span><span class="sxs-lookup"><span data-stu-id="22c8c-122">When bulk copying out and using **bcp_colfmt**, you can easily create a format file describing the data file you have created by calling [bcp_writefmt](../native-client-odbc-extensions-bulk-copy-functions/bcp-writefmt.md) after the last call to **bcp_colfmt**.</span></span>  
  
 <span data-ttu-id="22c8c-123">Quando si esegue la copia bulk da un file di dati descritto da un file di formato, leggere il file di formato chiamando [bcp_readfmt](../native-client-odbc-extensions-bulk-copy-functions/bcp-readfmt.md) dopo **bcp_init** ma prima di **bcp_exec**.</span><span class="sxs-lookup"><span data-stu-id="22c8c-123">When bulk copying in from a data file described by a format file, read the format file by calling [bcp_readfmt](../native-client-odbc-extensions-bulk-copy-functions/bcp-readfmt.md) after **bcp_init** but before **bcp_exec**.</span></span>  
  
 <span data-ttu-id="22c8c-124">La funzione **bcp_control** controlla diverse opzioni durante la copia bulk in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] da un file di dati.</span><span class="sxs-lookup"><span data-stu-id="22c8c-124">The **bcp_control** function controls several options when bulk copying into [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from a data file.</span></span> <span data-ttu-id="22c8c-125">**bcp_control** imposta le opzioni, ad esempio il numero massimo di errori prima della terminazione, la riga del file in cui avviare la copia bulk, la riga in cui arrestare e le dimensioni del batch.</span><span class="sxs-lookup"><span data-stu-id="22c8c-125">**bcp_control** sets options, such as the maximum number of errors before termination, the row in the file on which to start the bulk copy, the row to stop on, and the batch size.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22c8c-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="22c8c-126">See Also</span></span>  
 [<span data-ttu-id="22c8c-127">Esecuzione di operazioni di copia bulk &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="22c8c-127">Performing Bulk Copy Operations &#40;ODBC&#41;</span></span>](performing-bulk-copy-operations-odbc.md)  
  
  
