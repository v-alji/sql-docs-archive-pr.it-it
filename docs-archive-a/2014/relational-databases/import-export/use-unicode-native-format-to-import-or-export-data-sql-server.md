---
title: Usare il formato nativo Unicode per importare o esportare dati (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- Unicode [SQL Server], bulk importing and exporting
- data formats [SQL Server], Unicode native
ms.assetid: a6213308-f3d5-406e-9029-19d8bb3367f3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: beae2f836de16dedf3be6d8c196910c53be02266
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724703"
---
# <a name="use-unicode-native-format-to-import-or-export-data-sql-server"></a><span data-ttu-id="fd37d-102">Utilizzare il formato Unicode nativo per importare o esportare dati (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="fd37d-102">Use Unicode Native Format to Import or Export Data (SQL Server)</span></span>
  <span data-ttu-id="fd37d-103">Il formato Unicode nativo risulta particolarmente utile quando è necessario copiare informazioni da un'installazione di [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a un'altra.</span><span class="sxs-lookup"><span data-stu-id="fd37d-103">Unicode native format is helpful when information must be copied from one [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installation to another.</span></span> <span data-ttu-id="fd37d-104">L'utilizzo del formato nativo per i dati non carattere consente di risparmiare tempo evitando di dover eseguire la conversione dei tipi di dati in formato carattere e viceversa.</span><span class="sxs-lookup"><span data-stu-id="fd37d-104">The use of native format for noncharacter data saves time, eliminating unnecessary conversion of data types to and from character format.</span></span> <span data-ttu-id="fd37d-105">L'utilizzo del formato carattere Unicode per tutti i dati di tipo carattere consente di evitare la perdita dei caratteri estesi durante il trasferimento bulk dei dati tra server che utilizzano tabelle codici diverse.</span><span class="sxs-lookup"><span data-stu-id="fd37d-105">The use of Unicode character format for all character data prevents loss of any extended characters during bulk transfer of data between servers using different code pages.</span></span> <span data-ttu-id="fd37d-106">Un file di dati in formato nativo Unicode è leggibile con qualsiasi metodo di importazione bulk.</span><span class="sxs-lookup"><span data-stu-id="fd37d-106">A data file in Unicode native format can be read by any bulk-import method.</span></span>  
  
 <span data-ttu-id="fd37d-107">Il formato nativo Unicode è consigliato per i trasferimenti bulk di dati tra più istanze di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utilizzando un file di dati che include caratteri estesi o DBCS.</span><span class="sxs-lookup"><span data-stu-id="fd37d-107">Unicode native format is recommended for the bulk transfer of data between multiple instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by using a data file that contains extended or DBCS characters.</span></span> <span data-ttu-id="fd37d-108">Per i dati non carattere, il formato nativo Unicode utilizza i tipi di dati (database) nativi.</span><span class="sxs-lookup"><span data-stu-id="fd37d-108">For noncharacter data, Unicode native format uses native (database) data types.</span></span> <span data-ttu-id="fd37d-109">Per i dati carattere, ad esempio `char`, `nchar`, `varchar`, `nvarchar`, `text`, `varchar(max)`, `nvarchar(max)` e `ntext`, il formato nativo Unicode utilizza il formato di dati carattere Unicode.</span><span class="sxs-lookup"><span data-stu-id="fd37d-109">For character data, such as `char`, `nchar`, `varchar`, `nvarchar`, `text`, `varchar(max)`, `nvarchar(max)`, and `ntext`, the Unicode native format uses Unicode character data format.</span></span>  
  
 <span data-ttu-id="fd37d-110">I dati `sql_variant` memorizzati come SQLVARIANT in un file di dati in formato nativo Unicode vengono gestiti in modo analogo a quanto avviene per un file di dati in formato nativo, fatta eccezione per il fatto che i valori `char` e `varchar` sono convertiti in `nchar` e `nvarchar`, raddoppiando lo spazio necessario per le colonne interessate.</span><span class="sxs-lookup"><span data-stu-id="fd37d-110">The `sql_variant` data that is stored as a SQLVARIANT in a Unicode native-format data file operates in the same manner as it does in a native-format data file, except that `char` and `varchar` values are converted to `nchar` and `nvarchar`, which doubles the amount of storage required for the affected columns.</span></span> <span data-ttu-id="fd37d-111">I metadati originali vengono mantenuti e i valori riconvertiti nel tipo di dati `char` e `varchar` originale quando viene eseguita l'importazione bulk in una colonna di tabella.</span><span class="sxs-lookup"><span data-stu-id="fd37d-111">The original metadata is preserved, and the values are converted back to their original `char` and `varchar` data type when bulk imported into a table column.</span></span>  
  
## <a name="command-options-for-unicode-native-format"></a><span data-ttu-id="fd37d-112">Opzioni di comando per il formato nativo Unicode</span><span class="sxs-lookup"><span data-stu-id="fd37d-112">Command Options for Unicode Native Format</span></span>  
 <span data-ttu-id="fd37d-113">È possibile importare dati in formato nativo Unicode in una tabella usando **bcp**, BULK INSERT o INSERT... SELECT \* FROM OPENROWSET (bulk...). Per un comando **bcp** o un'istruzione BULK INSERT, è possibile specificare il formato dati nella riga di comando.</span><span class="sxs-lookup"><span data-stu-id="fd37d-113">You can import Unicode native format data into a table using **bcp**, BULK INSERT or INSERT ... SELECT \* FROM OPENROWSET(BULK...). For a **bcp** command or BULK INSERT statement, you can specify the data format on the command line.</span></span> <span data-ttu-id="fd37d-114">Per un'istruzione INSERT ... SELECT \* FROM OPENROWSET(BULK...) è necessario specificare il formato dati in un file di formato.</span><span class="sxs-lookup"><span data-stu-id="fd37d-114">For an INSERT ... SELECT \* FROM OPENROWSET(BULK...) statement, you must specify the data format in a format file.</span></span>  
  
 <span data-ttu-id="fd37d-115">Il formato nativo Unicode è supportato dalle seguenti opzioni:</span><span class="sxs-lookup"><span data-stu-id="fd37d-115">Unicode native format is supported by the following options:</span></span>  
  
|<span data-ttu-id="fd37d-116">Comando</span><span class="sxs-lookup"><span data-stu-id="fd37d-116">Command</span></span>|<span data-ttu-id="fd37d-117">Opzione</span><span class="sxs-lookup"><span data-stu-id="fd37d-117">Option</span></span>|<span data-ttu-id="fd37d-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fd37d-118">Description</span></span>|  
|-------------|------------|-----------------|  
|<span data-ttu-id="fd37d-119">**bcp**</span><span class="sxs-lookup"><span data-stu-id="fd37d-119">**bcp**</span></span>|<span data-ttu-id="fd37d-120">**-N**</span><span class="sxs-lookup"><span data-stu-id="fd37d-120">**-N**</span></span>|<span data-ttu-id="fd37d-121">Fa in modo che l'utilità **bcp** usi il formato nativo Unicode, che usa i tipi di dati nativi (database) per tutti i dati non carattere e il formato di dati carattere Unicode per tutti i dati di tipo carattere (,,,, `char` `nchar` `varchar` `nvarchar` `text` e `ntext` ).</span><span class="sxs-lookup"><span data-stu-id="fd37d-121">Causes the **bcp** utility to use the Unicode native format, which uses native (database) data types for all noncharacter data and Unicode character data format for all character (`char`, `nchar`, `varchar`, `nvarchar`, `text`, and `ntext`) data.</span></span>|  
|<span data-ttu-id="fd37d-122">BULK INSERT</span><span class="sxs-lookup"><span data-stu-id="fd37d-122">BULK INSERT</span></span>|<span data-ttu-id="fd37d-123">FileType **='** widenative **'**</span><span class="sxs-lookup"><span data-stu-id="fd37d-123">DATAFILETYPE **='** widenative **'**</span></span>|<span data-ttu-id="fd37d-124">Utilizzare il formato Unicode nativo per l'importazione bulk dei dati.</span><span class="sxs-lookup"><span data-stu-id="fd37d-124">Use Unicode native format when bulk importing data.</span></span>|  
  
 <span data-ttu-id="fd37d-125">Per altre informazioni, vedere [Utilità bcp](../../tools/bcp-utility.md), [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) o [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="fd37d-125">For more information, see [bcp Utility](../../tools/bcp-utility.md), [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql), or [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fd37d-126">In alternativa, è possibile definire la formattazione di ogni singolo campo in un file di formato.</span><span class="sxs-lookup"><span data-stu-id="fd37d-126">Alternatively, you can specify formatting on a per-field basis in a format file.</span></span> <span data-ttu-id="fd37d-127">Per altre informazioni, vedere [File di formato per l'importazione o l'esportazione di dati &#40;SQL Server&#41;](format-files-for-importing-or-exporting-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="fd37d-127">For more information, see [Format Files for Importing or Exporting Data &#40;SQL Server&#41;](format-files-for-importing-or-exporting-data-sql-server.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="fd37d-128">Esempi</span><span class="sxs-lookup"><span data-stu-id="fd37d-128">Examples</span></span>  
 <span data-ttu-id="fd37d-129">Gli esempi seguenti mostrano come eseguire l'esportazione in blocco di dati nativi usando **bcp** e l'importazione in blocco degli stessi dati usando BULK INSERT.</span><span class="sxs-lookup"><span data-stu-id="fd37d-129">The following examples demonstrate how to bulk export native data using **bcp** and bulk import the same data using BULK INSERT.</span></span>  
  
### <a name="sample-table"></a><span data-ttu-id="fd37d-130">Tabella di esempio</span><span class="sxs-lookup"><span data-stu-id="fd37d-130">Sample Table</span></span>  
 <span data-ttu-id="fd37d-131">Gli esempi richiedono la creazione di una tabella denominata **myTestUniNativeData** nel database di esempio **AdventureWorks** all'interno dello schema **dbo**.</span><span class="sxs-lookup"><span data-stu-id="fd37d-131">The examples require that a table named **myTestUniNativeData** table be created in the **AdventureWorks** sample database under the **dbo** schema.</span></span> <span data-ttu-id="fd37d-132">Prima di eseguire le procedure illustrate negli esempi, è necessario creare la tabella.</span><span class="sxs-lookup"><span data-stu-id="fd37d-132">Before you can run the examples, you must create this table.</span></span> <span data-ttu-id="fd37d-133">Nell'editor di query di [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] eseguire:</span><span class="sxs-lookup"><span data-stu-id="fd37d-133">In [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] Query Editor, execute:</span></span>  
  
```  
USE AdventureWorks;  
GO  
CREATE TABLE myTestUniNativeData (  
   Col1 smallint,  
   Col2 nvarchar(50),  
   Col3 nvarchar(50)  
   );   
```  
  
 <span data-ttu-id="fd37d-134">Per popolare la tabella e visualizzare il contenuto risultante, eseguire le istruzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="fd37d-134">To populate this table and view the resulting contents execute the following statements:</span></span>  
  
```  
INSERT INTO myTestUniNativeData(Col1,Col2,Col3)  
   VALUES(1,'DataField2','DataField3');  
INSERT INTO myTestUniNativeData(Col1,Col2,Col3)  
   VALUES(2,'DataField2','DataField3');  
GO  
SELECT Col1,Col2,Col3 FROM myTestUniNativeData  
  
```  
  
### <a name="using-bcp-to-bulk-export-native-data"></a><span data-ttu-id="fd37d-135">Utilizzo del comando bcp per l'esportazione bulk di dati nativi</span><span class="sxs-lookup"><span data-stu-id="fd37d-135">Using bcp to Bulk Export Native Data</span></span>  
 <span data-ttu-id="fd37d-136">Per esportare i dati dalla tabella al file di dati, usare **bcp** con l'opzione **out** e i qualificatori seguenti:</span><span class="sxs-lookup"><span data-stu-id="fd37d-136">To export data from the table to the data file, use **bcp** with the **out** option and the following qualifiers:</span></span>  
  
|<span data-ttu-id="fd37d-137">Qualificatori</span><span class="sxs-lookup"><span data-stu-id="fd37d-137">Qualifiers</span></span>|<span data-ttu-id="fd37d-138">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fd37d-138">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="fd37d-139">**-N**</span><span class="sxs-lookup"><span data-stu-id="fd37d-139">**-N**</span></span>|<span data-ttu-id="fd37d-140">Specifica i tipi di dati nativi.</span><span class="sxs-lookup"><span data-stu-id="fd37d-140">Specifies native data types.</span></span>|  
|<span data-ttu-id="fd37d-141">**-T**</span><span class="sxs-lookup"><span data-stu-id="fd37d-141">**-T**</span></span>|<span data-ttu-id="fd37d-142">Specifica che l'utilità **bcp** si connette a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] con una connessione trusted che usa la sicurezza integrata.</span><span class="sxs-lookup"><span data-stu-id="fd37d-142">Specifies that the **bcp** utility connects to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] with a trusted connection using integrated security.</span></span> <span data-ttu-id="fd37d-143">Se non si specifica **-T** , è necessario specificare **-U** e **-P** per eseguire correttamente l'accesso.</span><span class="sxs-lookup"><span data-stu-id="fd37d-143">If **-T** is not specified, you need to specify **-U** and **-P** to successfully log in.</span></span>|  
  
 <span data-ttu-id="fd37d-144">Nel seguente esempio viene eseguita l'esportazione bulk dei dati in formato nativo dalla tabella `myTestUniNativeData` in un nuovo file di dati denominato `myTestUniNativeData-N.Dat`.</span><span class="sxs-lookup"><span data-stu-id="fd37d-144">The following example bulk exports data in native format from the `myTestUniNativeData` table into a new data file named `myTestUniNativeData-N.Dat` data file.</span></span> <span data-ttu-id="fd37d-145">Al prompt dei comandi di [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows digitare:</span><span class="sxs-lookup"><span data-stu-id="fd37d-145">At the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows command prompt, enter:</span></span>  
  
```  
bcp AdventureWorks..myTestUniNativeData out C:\myTestUniNativeData-N.Dat -N -T  
  
```  
  
### <a name="using-bulk-insert-to-bulk-import-native-data"></a><span data-ttu-id="fd37d-146">Utilizzo dell'istruzione BULK INSERT per l'importazione bulk di dati nativi</span><span class="sxs-lookup"><span data-stu-id="fd37d-146">Using BULK INSERT to Bulk Import Native Data</span></span>  
 <span data-ttu-id="fd37d-147">Nell'esempio seguente si utilizza BULK INSERT per importare i dati dal file di dati `myTestUniNativeData-N.Dat` nella tabella `myTestUniNativeData`.</span><span class="sxs-lookup"><span data-stu-id="fd37d-147">The following example uses BULK INSERT to import the data in the `myTestUniNativeData-N.Dat` data file into the `myTestUniNativeData` table.</span></span> <span data-ttu-id="fd37d-148">Nell'editor di query di [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] eseguire:</span><span class="sxs-lookup"><span data-stu-id="fd37d-148">In [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] Query Editor, execute:</span></span>  
  
```  
USE AdventureWorks;  
GO  
BULK INSERT myTestUniNativeData   
    FROM 'C:\myTestUniNativeData-N.Dat'   
   WITH (DATAFILETYPE='widenative');   
GO  
SELECT Col1,Col2,Col3 FROM myTestUniNativeData;  
GO  
  
```  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="fd37d-149">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="fd37d-149">Related Tasks</span></span>  
 <span data-ttu-id="fd37d-150">**Per utilizzare formati di dati per l'importazione o l'esportazione bulk**</span><span class="sxs-lookup"><span data-stu-id="fd37d-150">**To use data formats for bulk import or bulk export**</span></span>  
  
-   [<span data-ttu-id="fd37d-151">Importare dati in formato nativo e carattere da versioni precedenti di SQL Server</span><span class="sxs-lookup"><span data-stu-id="fd37d-151">Import Native and Character Format Data from Earlier Versions of SQL Server</span></span>](import-native-and-character-format-data-from-earlier-versions-of-sql-server.md)  
  
-   [<span data-ttu-id="fd37d-152">Utilizzo del formato carattere per l'importazione o l'esportazione di dati &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="fd37d-152">Use Character Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-character-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="fd37d-153">Usare il formato nativo per importare o esportare dati &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="fd37d-153">Use Native Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-native-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="fd37d-154">Utilizzo del formato carattere Unicode per l'importazione o l'esportazione di dati &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="fd37d-154">Use Unicode Character Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-unicode-character-format-to-import-or-export-data-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="fd37d-155">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fd37d-155">See Also</span></span>  
 <span data-ttu-id="fd37d-156">[Utilità bcp](../../tools/bcp-utility.md) </span><span class="sxs-lookup"><span data-stu-id="fd37d-156">[bcp Utility](../../tools/bcp-utility.md) </span></span>  
 <span data-ttu-id="fd37d-157">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="fd37d-157">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span></span>  
 <span data-ttu-id="fd37d-158">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="fd37d-158">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span></span>  
 [<span data-ttu-id="fd37d-159">Tipi di dati &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="fd37d-159">Data Types &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/data-types-transact-sql)  
  
  
