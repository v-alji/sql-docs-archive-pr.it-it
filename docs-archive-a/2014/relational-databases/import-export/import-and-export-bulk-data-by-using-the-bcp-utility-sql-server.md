---
title: Importare ed esportare dati per operazioni bulk usando l'utilità bcp (SQL Server) | Microsoft Docs
ms.prod: sql-server-2014
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- bulk exporting [SQL Server], bcp utility
- bulk importing [SQL Server], bcp utility
- bcp utility [SQL Server], about bcp utility
ms.assetid: 73e949de-67a3-4c84-9735-7da1ad4ba34a
author: markingmyname
ms.author: maghan
ms.reviewer: ''
ms.custom: ''
ms.date: 06/14/2017
ms.openlocfilehash: 7d1892b26f3c638a696d8ed15e739f56ac2e682f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635589"
---
# <a name="import-and-export-bulk-data-by-using-the-bcp-utility-sql-server"></a><span data-ttu-id="27767-102">Importazione ed esportazione di dati per operazioni bulk tramite l'utilità bcp (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="27767-102">Import and Export Bulk Data by Using the bcp Utility (SQL Server)</span></span>

<span data-ttu-id="27767-103">Questo argomento offre una panoramica sull'uso dell' [utilità bcp](../../tools/bcp-utility.md) per l'esportazione di dati da qualsiasi posizione di un database di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in cui è possibile usare un'istruzione SELECT, incluse le viste partizionate.</span><span class="sxs-lookup"><span data-stu-id="27767-103">This topic provides an overview for using the [bcp utility](../../tools/bcp-utility.md) to export data from anywhere in a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database where a SELECT statement works, including partitioned views.</span></span>  
  
 <span data-ttu-id="27767-104">L'utilità bcp (Bcp.exe) è uno strumento della riga di comando che utilizza l'API del programma per la copia bulk (BCP).</span><span class="sxs-lookup"><span data-stu-id="27767-104">The bcp utility (Bcp.exe) is a command-line tool that uses the Bulk Copy Program (BCP) API.</span></span> <span data-ttu-id="27767-105">L'utilità bcp consente di eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="27767-105">The bcp utility performs the following tasks:</span></span>  
  
-   <span data-ttu-id="27767-106">Esportazioni bulk di dati da una tabella di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in un file di dati.</span><span class="sxs-lookup"><span data-stu-id="27767-106">Bulk exports data from a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table into a data file.</span></span>  
  
-   <span data-ttu-id="27767-107">Esportazioni bulk di dati da una query.</span><span class="sxs-lookup"><span data-stu-id="27767-107">Bulk exports data from a query.</span></span>  
  
-   <span data-ttu-id="27767-108">Importazioni bulk di dati da un file di dati in una tabella di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="27767-108">Bulk imports data from a data file into a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span>  
  
-   <span data-ttu-id="27767-109">Generazione di file di formato.</span><span class="sxs-lookup"><span data-stu-id="27767-109">Generates format files.</span></span>  
  
 <span data-ttu-id="27767-110">L'utilità bcp è accessibile con il comando **bcp** .</span><span class="sxs-lookup"><span data-stu-id="27767-110">The bcp utility is accessed by the **bcp** command.</span></span> <span data-ttu-id="27767-111">Per usare il comando **bcp** un'importazione in blocco di dati, è necessario conoscere lo schema della tabella e i tipi di dati delle colonne, a meno che non venga usato un file di formato preesistente.</span><span class="sxs-lookup"><span data-stu-id="27767-111">To use the **bcp** command to bulk import data, you must understand the schema of the table and the data types of its columns, unless you are using a pre-existing format file.</span></span>  
  
 <span data-ttu-id="27767-112">L'utilità consente di esportare dati da una tabella di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in un file di dati per utilizzarli in altri programmi.</span><span class="sxs-lookup"><span data-stu-id="27767-112">The bcp utility can export data from a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table to a data file for use in other programs.</span></span> <span data-ttu-id="27767-113">Consente inoltre di importare dati in una tabella di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] da un altro programma, in genere un altro sistema di gestione di database (DBMS, Database Management System).</span><span class="sxs-lookup"><span data-stu-id="27767-113">The utility can also import data into a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table from another program, usually another database management system (DBMS).</span></span> <span data-ttu-id="27767-114">I dati vengono innanzitutto esportati dal programma di origine in un file di dati e quindi, in un'operazione separata, vengono copiati dal file di dati in una tabella di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="27767-114">The data is first exported from the source program to a data file and then, in a separate operation, copied from the data file into a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span>  
  
 <span data-ttu-id="27767-115">Le opzioni del comando **bcp** consentono di specificare il tipo di dati del file di dati e altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="27767-115">The **bcp** command provides switches that you use to specify the data type of the data file and other information.</span></span> <span data-ttu-id="27767-116">Se tali opzioni non vengono specificate, verrà richiesto di immettere le informazioni sulla formattazione, ad esempio il tipo dei campi dati di un file di dati.</span><span class="sxs-lookup"><span data-stu-id="27767-116">If these switches are not specified, the command prompts for formatting information, such as the type of data fields in a data file.</span></span> <span data-ttu-id="27767-117">Verrà quindi richiesto se si desidera creare un file di formato contenente le risposte interattive fornite.</span><span class="sxs-lookup"><span data-stu-id="27767-117">The command then asks whether you want to create a format file that contains your interactive responses.</span></span> <span data-ttu-id="27767-118">Un file di formato risulta spesso utile per assicurare la flessibilità per operazioni future di importazione o esportazione bulk.</span><span class="sxs-lookup"><span data-stu-id="27767-118">If you want flexibility for future bulk-import or bulk-export operations, a format file is often useful.</span></span> <span data-ttu-id="27767-119">È possibile specificare il file di formato in comandi **bcp** successivi per file di dati equivalenti.</span><span class="sxs-lookup"><span data-stu-id="27767-119">You can specify the format file on later **bcp** commands for equivalent data files.</span></span> <span data-ttu-id="27767-120">Per altre informazioni, vedere [Impostazione dei formati di dati per la compatibilità mediante bcp &#40;SQL Server&#41;](specify-data-formats-for-compatibility-when-using-bcp-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="27767-120">For more information, see [Specify Data Formats for Compatibility when Using bcp &#40;SQL Server&#41;](specify-data-formats-for-compatibility-when-using-bcp-sql-server.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="27767-121">L'utilità bcp è scritta tramite la copia bulk di ODBC</span><span class="sxs-lookup"><span data-stu-id="27767-121">The bcp utility is written by using the ODBC bulk-copy</span></span>  
  
 <span data-ttu-id="27767-122">Per una descrizione della sintassi del comando **bcp** , vedere [Utilità bcp](../../tools/bcp-utility.md).</span><span class="sxs-lookup"><span data-stu-id="27767-122">For a description of the **bcp** command syntax, see [bcp Utility](../../tools/bcp-utility.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="27767-123">Esempi</span><span class="sxs-lookup"><span data-stu-id="27767-123">Examples</span></span>

 <span data-ttu-id="27767-124">Per esempi su **bcp**, vedere:</span><span class="sxs-lookup"><span data-stu-id="27767-124">For **bcp** examples, see:</span></span>  
  
-   [<span data-ttu-id="27767-125">Utilità bcp</span><span class="sxs-lookup"><span data-stu-id="27767-125">bcp Utility</span></span>](../../tools/bcp-utility.md)  
  
-   [<span data-ttu-id="27767-126">Creazione di un file di formato &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="27767-126">Create a Format File &#40;SQL Server&#41;</span></span>](create-a-format-file-sql-server.md)  
  
-   [<span data-ttu-id="27767-127">Esempi di importazione ed esportazione bulk di documenti XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="27767-127">Examples of Bulk Import and Export of XML Documents &#40;SQL Server&#41;</span></span>](examples-of-bulk-import-and-export-of-xml-documents-sql-server.md)  
  
-   [<span data-ttu-id="27767-128">Mantenere i valori Identity durante l'importazione in blocco dei dati &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="27767-128">Keep Identity Values When Bulk Importing Data &#40;SQL Server&#41;</span></span>](keep-identity-values-when-bulk-importing-data-sql-server.md)  
  
-   [<span data-ttu-id="27767-129">Mantenimento dei valori Null o uso dei valori predefiniti durante un'importazione bulk &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="27767-129">Keep Nulls or Use Default Values During Bulk Import &#40;SQL Server&#41;</span></span>](keep-nulls-or-use-default-values-during-bulk-import-sql-server.md)  
  
-   [<span data-ttu-id="27767-130">Impostazione dei caratteri di terminazione del campo e della riga &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="27767-130">Specify Field and Row Terminators &#40;SQL Server&#41;</span></span>](specify-field-and-row-terminators-sql-server.md)  
  
-   [<span data-ttu-id="27767-131">Usare un file di formato per l'importazione in blocco dei dati &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="27767-131">Use a Format File to Bulk Import Data &#40;SQL Server&#41;</span></span>](use-a-format-file-to-bulk-import-data-sql-server.md)  
  
-   [<span data-ttu-id="27767-132">Utilizzo del formato carattere per l'importazione o l'esportazione di dati &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="27767-132">Use Character Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-character-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="27767-133">Usare il formato nativo per importare o esportare dati &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="27767-133">Use Native Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-native-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="27767-134">Utilizzo del formato carattere Unicode per l'importazione o l'esportazione di dati &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="27767-134">Use Unicode Character Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-unicode-character-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="27767-135">Usare il formato Unicode nativo per importare o esportare dati &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="27767-135">Use Unicode Native Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-unicode-native-format-to-import-or-export-data-sql-server.md)  

## <a name="see-also"></a><span data-ttu-id="27767-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="27767-136">See Also</span></span>

<span data-ttu-id="27767-137">[Inserisci &#40;&#41;](/sql/t-sql/statements/insert-transact-sql) 
 Transact-SQL [Clausola SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-clause-transact-sql) 
 [utilità bcp](../../tools/bcp-utility.md) </span><span class="sxs-lookup"><span data-stu-id="27767-137">[INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/insert-transact-sql)
[SELECT Clause &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-clause-transact-sql)
[bcp Utility](../../tools/bcp-utility.md) </span></span>  
<span data-ttu-id="27767-138">[Preparare l'importazione bulk dei dati &#40;SQL Server&#41;](prepare-to-bulk-import-data-sql-server.md) 
 [BULK INSERT &#40;&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) 
 Transact-SQL [Importazione ed esportazione bulk di dati &#40;SQL Server&#41;](bulk-import-and-export-of-data-sql-server.md) 
 [OPENROWSET &#40;&#41;](/sql/t-sql/functions/openrowset-transact-sql) 
 Transact-SQL [Creare un file di formato &#40;SQL Server&#41;](create-a-format-file-sql-server.md)</span><span class="sxs-lookup"><span data-stu-id="27767-138">[Prepare to Bulk Import Data &#40;SQL Server&#41;](prepare-to-bulk-import-data-sql-server.md)
[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql)
[Bulk Import and Export of Data &#40;SQL Server&#41;](bulk-import-and-export-of-data-sql-server.md)
[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql)
[Create a Format File &#40;SQL Server&#41;](create-a-format-file-sql-server.md)</span></span>