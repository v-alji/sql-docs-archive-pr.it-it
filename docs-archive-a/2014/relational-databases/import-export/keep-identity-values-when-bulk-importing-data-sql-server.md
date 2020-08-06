---
title: Mantenere i valori Identity durante l'importazione bulk dei dati (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- identity values [SQL Server], bulk imports
- data formats [SQL Server], identity values
- bulk importing [SQL Server], identity values
ms.assetid: 45894a3f-2d8a-4edd-9568-afa7d0d3061f
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 07f6714f27f60afda91134034509ff439d92f071
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635586"
---
# <a name="keep-identity-values-when-bulk-importing-data-sql-server"></a><span data-ttu-id="ace65-102">Mantenere i valori Identity durante l'importazione bulk dei dati (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="ace65-102">Keep Identity Values When Bulk Importing Data (SQL Server)</span></span>
  <span data-ttu-id="ace65-103">È possibile eseguire l'importazione bulk dei file di dati contenenti valori Identity in un'istanza di [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ace65-103">Data files that contain identity values can be bulk imported into an instance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="ace65-104">Per impostazione predefinita, i valori per la colonna Identity del file di dati importato vengono ignorati e sostituiti automaticamente da valori univoci assegnati da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ace65-104">By default, the values for the identity column in the data file that is imported are ignored and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] assigns unique values automatically.</span></span> <span data-ttu-id="ace65-105">I valori univoci si basano sui valori di inizializzazione e incremento specificati durante la creazione della tabella.</span><span class="sxs-lookup"><span data-stu-id="ace65-105">The unique values are based on the seed and increment values that are specified during table creation.</span></span>  
  
 <span data-ttu-id="ace65-106">Se il file di dati non contiene valori per la colonna dell'identificatore nella tabella, utilizzare un file di formato per specificare di ignorare la colonna dell'identificatore nella tabella durante l'importazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="ace65-106">If the data file does not contain values for the identifier column in the table, use a format file to specify that the identifier column in the table should be skipped when importing data.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="ace65-107">assegna automaticamente valori univoci per la colonna.</span><span class="sxs-lookup"><span data-stu-id="ace65-107">assigns unique values for the column automatically.</span></span>  
  
 <span data-ttu-id="ace65-108">Per impedire l'assegnazione da parte di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] di valori Identity durante l'importazione bulk delle righe di dati in una tabella, utilizzare il qualificatore per il mantenimento dei valori Identity corretto.</span><span class="sxs-lookup"><span data-stu-id="ace65-108">To prevent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from assigning identity values while bulk importing data rows into a table, use the appropriate keep-identity command qualifier.</span></span> <span data-ttu-id="ace65-109">Quando si specifica un qualificatore per il mantenimento dei valori Identity, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utilizza i valori Identity nel file di dati.</span><span class="sxs-lookup"><span data-stu-id="ace65-109">When you specify a keep-identity qualifier, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] uses the identity values in the data file.</span></span> <span data-ttu-id="ace65-110">Sono disponibili i qualificatori seguenti:</span><span class="sxs-lookup"><span data-stu-id="ace65-110">These qualifiers are as follows:</span></span>  
  
|<span data-ttu-id="ace65-111">Comando</span><span class="sxs-lookup"><span data-stu-id="ace65-111">Command</span></span>|<span data-ttu-id="ace65-112">Qualificatore per il mantenimento dei valori Identity</span><span class="sxs-lookup"><span data-stu-id="ace65-112">Keep-identity qualifier</span></span>|<span data-ttu-id="ace65-113">Tipo di qualificatore</span><span class="sxs-lookup"><span data-stu-id="ace65-113">Qualifier type</span></span>|  
|-------------|------------------------------|--------------------|  
|`bcp`|<span data-ttu-id="ace65-114">**-E**</span><span class="sxs-lookup"><span data-stu-id="ace65-114">**-E**</span></span>|<span data-ttu-id="ace65-115">Opzione</span><span class="sxs-lookup"><span data-stu-id="ace65-115">Switch</span></span>|  
|<span data-ttu-id="ace65-116">BULK INSERT</span><span class="sxs-lookup"><span data-stu-id="ace65-116">BULK INSERT</span></span>|<span data-ttu-id="ace65-117">KEEPIDENTITY</span><span class="sxs-lookup"><span data-stu-id="ace65-117">KEEPIDENTITY</span></span>|<span data-ttu-id="ace65-118">Argomento</span><span class="sxs-lookup"><span data-stu-id="ace65-118">Argument</span></span>|  
|<span data-ttu-id="ace65-119">INSERT ... SELECT \* FROM OPENROWSET(BULK...).</span><span class="sxs-lookup"><span data-stu-id="ace65-119">INSERT ... SELECT \* FROM OPENROWSET(BULK...)</span></span>|<span data-ttu-id="ace65-120">KEEPIDENTITY</span><span class="sxs-lookup"><span data-stu-id="ace65-120">KEEPIDENTITY</span></span>|<span data-ttu-id="ace65-121">Hint di tabella</span><span class="sxs-lookup"><span data-stu-id="ace65-121">Table hint</span></span>|  
  
 <span data-ttu-id="ace65-122">Per altre informazioni, vedere [Utilità bcp](../../tools/bcp-utility.md), [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql), [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql), [INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/insert-transact-sql), [SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql) e [Hint di tabella &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql-table).</span><span class="sxs-lookup"><span data-stu-id="ace65-122">For more information, see [bcp Utility](../../tools/bcp-utility.md), [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql), [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql), [INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/insert-transact-sql), [SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql), and [Table Hints &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql-table).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ace65-123">Per creare un numero a incremento automatico da usare in più tabelle o da chiamare dalle applicazioni senza fare riferimento ad alcuna tabella, vedere [Numeri di sequenza](../sequence-numbers/sequence-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="ace65-123">To create an automatically incrementing number that can be used in multiple tables or that can be called from applications without referencing any table, see [Sequence Numbers](../sequence-numbers/sequence-numbers.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="ace65-124">Esempi</span><span class="sxs-lookup"><span data-stu-id="ace65-124">Examples</span></span>  
 <span data-ttu-id="ace65-125">Negli esempi di questo argomento viene utilizzata l'importazione bulk dei dati tramite INSERT... Selezionare \* FROM OPENROWSET (BULK...) e mantenere i valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="ace65-125">The examples in this topic bulk import data using INSERT ... SELECT \* FROM OPENROWSET(BULK...) and keeping default values.</span></span>  
  
### <a name="sample-table"></a><span data-ttu-id="ace65-126">Tabella di esempio</span><span class="sxs-lookup"><span data-stu-id="ace65-126">Sample Table</span></span>  
 <span data-ttu-id="ace65-127">Gli esempi di importazione in blocco richiedono la creazione di una tabella denominata **myTestKeepNulls** nel database di esempio **AdventureWorks** nello schema **dbo**.</span><span class="sxs-lookup"><span data-stu-id="ace65-127">The bulk-import examples require that a table named **myTestKeepNulls** table be created in the **AdventureWorks** sample database under the **dbo** schema.</span></span> <span data-ttu-id="ace65-128">Per creare la tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="ace65-128">To create this table.</span></span> <span data-ttu-id="ace65-129">nell'editor di query di [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] eseguire:</span><span class="sxs-lookup"><span data-stu-id="ace65-129">in [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] Query Editor, execute:</span></span>  
  
```  
USE AdventureWorks;  
GO  
SELECT * INTO HumanResources.myDepartment   
   FROM HumanResources.Department  
      WHERE 1=0;  
GO  
SELECT * FROM HumanResources.myDepartment;  
```  
  
 <span data-ttu-id="ace65-130">L'istruzione IDENTITY_INSERT nella tabella **Department** su cui si basa `myDepartment` è impostata su OFF.</span><span class="sxs-lookup"><span data-stu-id="ace65-130">The **Department** table on which `myDepartment` is based has IDENTITY_INSERT is set to OFF.</span></span> <span data-ttu-id="ace65-131">Pertanto, per importare i dati in una colonna Identity, è necessario specificare KEEPIDENTITY oppure **-E**.</span><span class="sxs-lookup"><span data-stu-id="ace65-131">Therefore, to import data into an identity column you must specify KEEPIDENTITY or **-E**.</span></span>  
  
### <a name="sample-data-file"></a><span data-ttu-id="ace65-132">File di dati di esempio</span><span class="sxs-lookup"><span data-stu-id="ace65-132">Sample Data File</span></span>  
 <span data-ttu-id="ace65-133">Nel file di dati utilizzato negli esempi di importazione bulk sono inclusi i dati esportati dalla tabella `HumanResources.Department` nel formato nativo.</span><span class="sxs-lookup"><span data-stu-id="ace65-133">The data file used in the bulk-import examples contains data bulk exported from the `HumanResources.Department` table in native format.</span></span> <span data-ttu-id="ace65-134">Per creare il file di dati, al prompt dei comandi di [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows digitare:</span><span class="sxs-lookup"><span data-stu-id="ace65-134">To create the data file, at the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows command prompt, enter:</span></span>  
  
```  
bcp AdventureWorks.HumanResources.Department out myDepartment-n.Dat -n -T  
```  
  
### <a name="sample-format-file"></a><span data-ttu-id="ace65-135">File di formato di esempio</span><span class="sxs-lookup"><span data-stu-id="ace65-135">Sample Format File</span></span>  
 <span data-ttu-id="ace65-136">In questi esempi di importazione bulk viene impiegato un file di formato XML, `myDepartment-f-x-n.Xml`, che utilizza formati nativi.</span><span class="sxs-lookup"><span data-stu-id="ace65-136">This bulk-import examples use an XML format file, `myDepartment-f-x-n.Xml`, which uses native data formats.</span></span> <span data-ttu-id="ace65-137">Negli esempi viene utilizzato `bcp` per creare il file di formato dalla tabella `HumanResources.Department` del database `AdventureWorks`.</span><span class="sxs-lookup"><span data-stu-id="ace65-137">This example uses `bcp` to create to generate this format file from the `HumanResources.Department` table of the `AdventureWorks` database.</span></span> <span data-ttu-id="ace65-138">Al prompt dei comandi di Windows digitare:</span><span class="sxs-lookup"><span data-stu-id="ace65-138">At the Windows command prompt, enter:</span></span>  
  
```  
bcp AdventureWorks.HumanResources.Department format nul -n -x -f myDepartment-f-n-x.Xml -T  
```  
  
 <span data-ttu-id="ace65-139">Per altre informazioni sulla creazione di un file di formato, vedere [Creazione di un file di formato &#40;SQL Server&#41;](create-a-format-file-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="ace65-139">For more information about creating a format file, see [Create a Format File &#40;SQL Server&#41;](create-a-format-file-sql-server.md).</span></span>  
  
### <a name="a-using-bcp-and-keeping-identity-values"></a><span data-ttu-id="ace65-140">R.</span><span class="sxs-lookup"><span data-stu-id="ace65-140">A.</span></span> <span data-ttu-id="ace65-141">Utilizzo di bcp mantenendo i valori Identity</span><span class="sxs-lookup"><span data-stu-id="ace65-141">Using bcp and Keeping Identity Values</span></span>  
 <span data-ttu-id="ace65-142">Nell'esempio seguente viene illustrato come mantenere i valori Identity quando si utilizza `bcp` per l'importazione bulk dei dati.</span><span class="sxs-lookup"><span data-stu-id="ace65-142">The following example demonstrates how to keep identity values when using `bcp` to bulk import data.</span></span> <span data-ttu-id="ace65-143">Il comando `bcp` utilizza il file di formato `myDepartment-f-n-x.Xml` e include le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ace65-143">The `bcp` command uses the format file, `myDepartment-f-n-x.Xml`, and contains the following switches:</span></span>  
  
|<span data-ttu-id="ace65-144">Qualificatori</span><span class="sxs-lookup"><span data-stu-id="ace65-144">Qualifiers</span></span>|<span data-ttu-id="ace65-145">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ace65-145">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="ace65-146">**-E**</span><span class="sxs-lookup"><span data-stu-id="ace65-146">**-E**</span></span>|<span data-ttu-id="ace65-147">Specifica che il valore o i valori Identity inclusi nel file di dati devono essere utilizzati per la colonna Identity.</span><span class="sxs-lookup"><span data-stu-id="ace65-147">Specifies that identity value or values in the data file are to be used for the identity column.</span></span>|  
|<span data-ttu-id="ace65-148">**-T**</span><span class="sxs-lookup"><span data-stu-id="ace65-148">**-T**</span></span>|<span data-ttu-id="ace65-149">Specifica che l' `bcp` utilità si connette a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] con una connessione trusted.</span><span class="sxs-lookup"><span data-stu-id="ace65-149">Specifies that the `bcp` utility connects to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] with a trusted connection.</span></span>|  
  
 <span data-ttu-id="ace65-150">Al prompt dei comandi di Windows digitare:</span><span class="sxs-lookup"><span data-stu-id="ace65-150">At the Windows command prompt, enter.</span></span>  
  
```  
bcp AdventureWorks.HumanResources.myDepartment in C:\myDepartment-n.Dat -f C:\myDepartment-f-n-x.Xml -E -T  
  
```  
  
### <a name="b-using-bulk-insert-and-keeping-identity-values"></a><span data-ttu-id="ace65-151">B.</span><span class="sxs-lookup"><span data-stu-id="ace65-151">B.</span></span> <span data-ttu-id="ace65-152">Utilizzo di BULK INSERT mantenendo i valori Identity</span><span class="sxs-lookup"><span data-stu-id="ace65-152">Using BULK INSERT and Keeping Identity Values</span></span>  
 <span data-ttu-id="ace65-153">Nell'esempio seguente viene utilizzato BULK INSERT per l'importazione bulk dei dati dal file `myDepartment-c.Dat` nella tabella `AdventureWorks.HumanResources.myDepartment` .</span><span class="sxs-lookup"><span data-stu-id="ace65-153">The following example uses BULK INSERT to bulk import data from the `myDepartment-c.Dat` file into the `AdventureWorks.HumanResources.myDepartment` table.</span></span> <span data-ttu-id="ace65-154">L'istruzione utilizza il file di formato `myDepartment-f-n-x.Xml` e include l'opzione KEEPIDENTITY per garantire che i valori Identity vengano mantenuti nel file di dati.</span><span class="sxs-lookup"><span data-stu-id="ace65-154">The statement uses the `myDepartment-f-n-x.Xml` format file and includes the KEEPIDENTITY option to ensure that any identity values in the data file are retained.</span></span>  
  
 <span data-ttu-id="ace65-155">Nell'editor di query di [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] eseguire:</span><span class="sxs-lookup"><span data-stu-id="ace65-155">In the [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] Query Editor, execute:</span></span>  
  
```  
USE AdventureWorks;  
GO  
DELETE HumanResources.myDepartment;  
GO  
BULK INSERT HumanResources.myDepartment  
   FROM 'C:\myDepartment-n.Dat'  
   WITH (  
      KEEPIDENTITY,  
      FORMATFILE='C:\myDepartment-f-n-x.Xml'  
   );  
GO  
SELECT * FROM HumanResources.myDepartment;  
  
```  
  
### <a name="c-using-openrowset-and-keeping-identity-values"></a><span data-ttu-id="ace65-156">C.</span><span class="sxs-lookup"><span data-stu-id="ace65-156">C.</span></span> <span data-ttu-id="ace65-157">Utilizzo di OPENROWSET mantenendo i valori Identity</span><span class="sxs-lookup"><span data-stu-id="ace65-157">Using OPENROWSET and Keeping Identity Values</span></span>  
 <span data-ttu-id="ace65-158">Nell'esempio seguente viene utilizzato il provider di set di righe con lettura bulk OPENROWSET per l'importazione bulk dei dati dal file `myDepartment-c.Dat` nella tabella `AdventureWorks.HumanResources.myDepartment` .</span><span class="sxs-lookup"><span data-stu-id="ace65-158">The following example uses the OPENROWSET bulk rowset provider to bulk import data from the `myDepartment-c.Dat` file into the `AdventureWorks.HumanResources.myDepartment` table.</span></span> <span data-ttu-id="ace65-159">L'istruzione utilizza il file di formato `myDepartment-f-n-x.Xml` e include l'hint KEEPIDENTITY per garantire che i valori Identity vengano mantenuti nel file di dati.</span><span class="sxs-lookup"><span data-stu-id="ace65-159">The statement uses the `myDepartment-f-n-x.Xml` format file and includes the KEEPIDENTITY hint to ensure that any identity values in the data file are retained.</span></span>  
  
 <span data-ttu-id="ace65-160">Nell'editor di query di [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] eseguire:</span><span class="sxs-lookup"><span data-stu-id="ace65-160">In the [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] Query Editor, execute:</span></span>  
  
```  
USE AdventureWorks;  
GO  
DELETE HumanResources.myDepartment;  
GO  
  
INSERT INTO HumanResources.myDepartment  
   with (KEEPIDENTITY)  
   (DepartmentID, Name, GroupName, ModifiedDate)  
   SELECT *  
      FROM  OPENROWSET(BULK 'C:\myDepartment-n.Dat',  
      FORMATFILE='C:\myDepartment-f-n-x.Xml') as t1;  
GO  
  
```  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="ace65-161">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="ace65-161">Related Tasks</span></span>  
  
-   [<span data-ttu-id="ace65-162">Mantenimento dei valori Null o uso dei valori predefiniti durante un'importazione bulk &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ace65-162">Keep Nulls or Use Default Values During Bulk Import &#40;SQL Server&#41;</span></span>](keep-nulls-or-use-default-values-during-bulk-import-sql-server.md)  
  
-   [<span data-ttu-id="ace65-163">Preparare i dati per l'importazione o l'esportazione in blocco &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ace65-163">Prepare Data for Bulk Export or Import &#40;SQL Server&#41;</span></span>](prepare-data-for-bulk-export-or-import-sql-server.md)  
  
 <span data-ttu-id="ace65-164">**Per utilizzare un file di formato**</span><span class="sxs-lookup"><span data-stu-id="ace65-164">**To use a format file**</span></span>  
  
-   [<span data-ttu-id="ace65-165">Creazione di un file di formato &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ace65-165">Create a Format File &#40;SQL Server&#41;</span></span>](create-a-format-file-sql-server.md)  
  
-   [<span data-ttu-id="ace65-166">Usare un file di formato per l'importazione in blocco dei dati &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ace65-166">Use a Format File to Bulk Import Data &#40;SQL Server&#41;</span></span>](use-a-format-file-to-bulk-import-data-sql-server.md)  
  
-   [<span data-ttu-id="ace65-167">Utilizzo di un file di formato per eseguire il mapping tra le colonne della tabella e i campi del file di dati &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ace65-167">Use a Format File to Map Table Columns to Data-File Fields &#40;SQL Server&#41;</span></span>](use-a-format-file-to-map-table-columns-to-data-file-fields-sql-server.md)  
  
-   [<span data-ttu-id="ace65-168">Utilizzo di un file di formato per escludere un campo di dati &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ace65-168">Use a Format File to Skip a Data Field &#40;SQL Server&#41;</span></span>](use-a-format-file-to-skip-a-data-field-sql-server.md)  
  
-   [<span data-ttu-id="ace65-169">Utilizzo di un file di formato per ignorare una colonna di una tabella &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ace65-169">Use a Format File to Skip a Table Column &#40;SQL Server&#41;</span></span>](use-a-format-file-to-skip-a-table-column-sql-server.md)  
  
 <span data-ttu-id="ace65-170">**Per utilizzare formati di dati per l'importazione o l'esportazione bulk**</span><span class="sxs-lookup"><span data-stu-id="ace65-170">**To use data formats for bulk import or bulk export**</span></span>  
  
-   [<span data-ttu-id="ace65-171">Importare dati in formato nativo e carattere da versioni precedenti di SQL Server</span><span class="sxs-lookup"><span data-stu-id="ace65-171">Import Native and Character Format Data from Earlier Versions of SQL Server</span></span>](import-native-and-character-format-data-from-earlier-versions-of-sql-server.md)  
  
-   [<span data-ttu-id="ace65-172">Utilizzo del formato carattere per l'importazione o l'esportazione di dati &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ace65-172">Use Character Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-character-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="ace65-173">Usare il formato nativo per importare o esportare dati &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ace65-173">Use Native Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-native-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="ace65-174">Utilizzo del formato carattere Unicode per l'importazione o l'esportazione di dati &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ace65-174">Use Unicode Character Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-unicode-character-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="ace65-175">Usare il formato Unicode nativo per importare o esportare dati &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ace65-175">Use Unicode Native Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-unicode-native-format-to-import-or-export-data-sql-server.md)  
  
 <span data-ttu-id="ace65-176">**Per specificare i formati di dati per la compatibilità mediante bcp**</span><span class="sxs-lookup"><span data-stu-id="ace65-176">**To specify data formats for compatibility when using bcp**</span></span>  
  
1.  [<span data-ttu-id="ace65-177">Impostazione dei caratteri di terminazione del campo e della riga &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ace65-177">Specify Field and Row Terminators &#40;SQL Server&#41;</span></span>](specify-field-and-row-terminators-sql-server.md)  
  
2.  [<span data-ttu-id="ace65-178">Specificare la lunghezza del prefisso nei file di dati con bcp &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ace65-178">Specify Prefix Length in Data Files by Using bcp &#40;SQL Server&#41;</span></span>](specify-prefix-length-in-data-files-by-using-bcp-sql-server.md)  
  
3.  [<span data-ttu-id="ace65-179">Specifica del tipo di archiviazione di file tramite bcp &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ace65-179">Specify File Storage Type by Using bcp &#40;SQL Server&#41;</span></span>](specify-file-storage-type-by-using-bcp-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="ace65-180">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ace65-180">See Also</span></span>  
 <span data-ttu-id="ace65-181">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ace65-181">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="ace65-182">[Utilità bcp](../../tools/bcp-utility.md) </span><span class="sxs-lookup"><span data-stu-id="ace65-182">[bcp Utility](../../tools/bcp-utility.md) </span></span>  
 <span data-ttu-id="ace65-183">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ace65-183">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span></span>  
 <span data-ttu-id="ace65-184">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ace65-184">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span></span>  
 [<span data-ttu-id="ace65-185">Hint di tabella &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ace65-185">Table Hints &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/queries/hints-transact-sql-table)  
  
  
