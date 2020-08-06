---
title: Specificare il tipo di archiviazione di file tramite bcp (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- bcp utility [SQL Server], file storage types
- importing data, file storage types
- native data format [SQL Server]
- file storage types [SQL Server]
- data formats [SQL Server], file storage types
ms.assetid: 85e12df8-1be7-4bdc-aea9-05aade085c06
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c1f3ad2a94ffe3e0f1db19a8e66f85497e7143dc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624717"
---
# <a name="specify-file-storage-type-by-using-bcp-sql-server"></a><span data-ttu-id="e61ef-102">Specifica del tipo di archiviazione di file tramite bcp (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="e61ef-102">Specify File Storage Type by Using bcp (SQL Server)</span></span>
  <span data-ttu-id="e61ef-103">Il *tipo di archiviazione di file* indica la modalità con la quale vengono archiviati i dati in un file.</span><span class="sxs-lookup"><span data-stu-id="e61ef-103">The *file storage type* describes how data is stored in the data file.</span></span> <span data-ttu-id="e61ef-104">I dati possono essere esportati in un file utilizzando il tipo di dati della tabella del database in cui si trovano (formato nativo), come caratteri (formato carattere) o utilizzando qualsiasi tipo di dati nel caso in cui sia supportata la conversione implicita. È possibile ad esempio copiare il tipo `smallint` come `int`.</span><span class="sxs-lookup"><span data-stu-id="e61ef-104">Data can be exported to a data file as its database table type (native format), in its character representation (character format), or as any data type where implicit conversion is supported; for example, copying a `smallint` as an `int`.</span></span> <span data-ttu-id="e61ef-105">I tipi di dati definiti dall'utente vengono esportati utilizzando il tipo di dati di base corrispondente.</span><span class="sxs-lookup"><span data-stu-id="e61ef-105">User-defined data types are exported as their base types.</span></span>  
  
## <a name="the-bcp-prompt-for-file-storage-type"></a><span data-ttu-id="e61ef-106">Richiesta del tipo di archiviazione di dati con bcp</span><span class="sxs-lookup"><span data-stu-id="e61ef-106">The bcp Prompt for File Storage Type</span></span>  
 <span data-ttu-id="e61ef-107">Se un comando interattivo **bcp** include l'opzione **in** o **out** senza l'opzione relativa al file di formato ( **-f**) o al formato dei dati ( **-n**, **-c**, **-w**o **-N**), viene richiesto il tipo di archiviazione di file di ogni campo di dati, come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="e61ef-107">If an interactive **bcp** command contains the **in** or **out** option without either the format file switch (**-f**) or a data-format switch (**-n**, **-c**, **-w**, or **-N**), the command prompts for the file storage type of each data field, as follows:</span></span>  
  
 `Enter the file storage type of field <field_name> [<default>]:`  
  
 <span data-ttu-id="e61ef-108">La risposta dell'utente a questa richiesta dipende dall'operazione eseguita, come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="e61ef-108">Your response to this prompt depends on the task you perform, as follows:</span></span>  
  
-   <span data-ttu-id="e61ef-109">Per eseguire l'esportazione bulk dei dati da un'istanza di [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in un file di dati nel formato di archiviazione più compatto (formato nativo), accettare i tipi di archiviazione di file predefiniti visualizzati dall'utilità **bcp**.</span><span class="sxs-lookup"><span data-stu-id="e61ef-109">To bulk export data from an instance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to a data file in the most compact storage possible (native data format), accept the default file storage types that are provided by **bcp**.</span></span> <span data-ttu-id="e61ef-110">Per un elenco dei tipi di archiviazione di file nativi, vedere "Tipi di archiviazione di file nativi" più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="e61ef-110">For a list of the native file storage types, see "Native File Storage Types," later in this topic.</span></span>  
  
-   <span data-ttu-id="e61ef-111">Per eseguire l'esportazione bulk dei dati da un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in un file di dati in formato carattere, specificare il tipo di archiviazione `char` per tutte le colonne della tabella.</span><span class="sxs-lookup"><span data-stu-id="e61ef-111">To bulk export data from an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to a data file in character format, specify `char` as the file storage type for all columns in the table.</span></span>  
  
-   <span data-ttu-id="e61ef-112">Per eseguire l'importazione bulk di dati in un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] da un file di dati, specificare il tipo di archiviazione di file `char` per i tipi archiviati nel formato carattere e, a seconda dei casi, uno dei tipi elencati di seguito per i dati archiviati nel formato nativo:</span><span class="sxs-lookup"><span data-stu-id="e61ef-112">To bulk import data to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from a data file, specify the file storage type as `char` for types stored in character format and, for data stored in native data type format, specify one of the file storage types, as appropriate:</span></span>  
  
    |<span data-ttu-id="e61ef-113">tipo di archiviazione di file</span><span class="sxs-lookup"><span data-stu-id="e61ef-113">File storage type</span></span>|<span data-ttu-id="e61ef-114">Parametro da specificare nel prompt dei comandi</span><span class="sxs-lookup"><span data-stu-id="e61ef-114">Enter at command prompt</span></span>|  
    |-----------------------|-----------------------------|  
    |<span data-ttu-id="e61ef-115">`char`<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="e61ef-115">`char` <sup>1</sup></span></span>|<span data-ttu-id="e61ef-116">`c`[`har`]</span><span class="sxs-lookup"><span data-stu-id="e61ef-116">`c`[`har`]</span></span>|  
    |`varchar`|`c[har]`|  
    |`nchar`|`w`|  
    |`nvarchar`|`w`|  
    |<span data-ttu-id="e61ef-117">`text` <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="e61ef-117">`text` <sup>2</sup></span></span>|<span data-ttu-id="e61ef-118">`T`[`ext`]</span><span class="sxs-lookup"><span data-stu-id="e61ef-118">`T`[`ext`]</span></span>|  
    |`ntext2`|`W`|  
    |`binary`|`x`|  
    |`varbinary`|`x`|  
    |<span data-ttu-id="e61ef-119">`image` <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="e61ef-119">`image` <sup>2</sup></span></span>|<span data-ttu-id="e61ef-120">`I`[`mage`]</span><span class="sxs-lookup"><span data-stu-id="e61ef-120">`I`[`mage`]</span></span>|  
    |`datetime`|<span data-ttu-id="e61ef-121">**d[ate]**</span><span class="sxs-lookup"><span data-stu-id="e61ef-121">**d[ate]**</span></span>|  
    |`smalldatetime`|`D`|  
    |`time`|`te`|  
    |`date`|`de`|  
    |`datetime2`|`d2`|  
    |`datetimeoffset`|`do`|  
    |`decimal`|`n`|  
    |`numeric`|`n`|  
    |`float`|<span data-ttu-id="e61ef-122">**f[loat]**</span><span class="sxs-lookup"><span data-stu-id="e61ef-122">**f[loat]**</span></span>|  
    |`real`|`r`|  
    |`Int`|<span data-ttu-id="e61ef-123">**i[nt]**</span><span class="sxs-lookup"><span data-stu-id="e61ef-123">**i[nt]**</span></span>|  
    |`bigint`|`B[igint]`|  
    |`smallint`|<span data-ttu-id="e61ef-124">**s[mallint]**</span><span class="sxs-lookup"><span data-stu-id="e61ef-124">**s[mallint]**</span></span>|  
    |`tinyint`|<span data-ttu-id="e61ef-125">**t[inyint]**</span><span class="sxs-lookup"><span data-stu-id="e61ef-125">**t[inyint]**</span></span>|  
    |`money`|<span data-ttu-id="e61ef-126">**m[oney]**</span><span class="sxs-lookup"><span data-stu-id="e61ef-126">**m[oney]**</span></span>|  
    |`smallmoney`|`M`|  
    |`bit`|`b[it]`|  
    |`uniqueidentifier`|`u`|  
    |`sql_variant`|`V[ariant]`|  
    |`timestamp`|`x`|  
    |<span data-ttu-id="e61ef-127">`UDT` (tipo di dati definito dall'utente)</span><span class="sxs-lookup"><span data-stu-id="e61ef-127">`UDT` (a user-defined data type)</span></span>|`U`|  
    |`XML`|`X`|  
  
     <span data-ttu-id="e61ef-128"><sup>1</sup> l'interazione tra lunghezza del campo, lunghezza del prefisso e caratteri di terminazione determina la quantità di spazio di archiviazione allocata in un file di dati per i dati non carattere esportati come `char` tipo di archiviazione file.</span><span class="sxs-lookup"><span data-stu-id="e61ef-128"><sup>1</sup> The interaction of field length, prefix length, and terminators determines the amount of storage space that is allocated in a data file for noncharacter data that is exported as the `char` file storage type.</span></span>  
  
     <span data-ttu-id="e61ef-129"><sup>2</sup> i `ntext` `text` `image` tipi di dati, e verranno rimossi in una versione futura di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e61ef-129"><sup>2</sup> The `ntext`, `text`, and `image` data types will be removed in a future version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="e61ef-130">Evitare di utilizzare questi tipi di dati in nuovi progetti di sviluppo e pianificare la modifica delle applicazioni che ne fanno uso.</span><span class="sxs-lookup"><span data-stu-id="e61ef-130">In new development work, avoid using these data types, and plan to modify applications that currently use them.</span></span> <span data-ttu-id="e61ef-131">In alternativa, usare `nvarchar(max)`, `varchar(max)` e `varbinary(max)`.</span><span class="sxs-lookup"><span data-stu-id="e61ef-131">Use `nvarchar(max)`, `varchar(max)`, and `varbinary(max)` instead.</span></span>  
  
## <a name="native-file-storage-types"></a><span data-ttu-id="e61ef-132">Tipi di archiviazione di file nativi</span><span class="sxs-lookup"><span data-stu-id="e61ef-132">Native File Storage Types</span></span>  
 <span data-ttu-id="e61ef-133">I tipi di archiviazione di file nativi vengono registrati nel file di formato come tipo di dati del file host corrispondente.</span><span class="sxs-lookup"><span data-stu-id="e61ef-133">Each native file storage type is recorded in the format file as a corresponding host file data type.</span></span>  
  
|<span data-ttu-id="e61ef-134">tipo di archiviazione di file</span><span class="sxs-lookup"><span data-stu-id="e61ef-134">File storage type</span></span>|<span data-ttu-id="e61ef-135">Tipo di dati del file host</span><span class="sxs-lookup"><span data-stu-id="e61ef-135">Host file data type</span></span>|  
|-----------------------|-------------------------|  
|<span data-ttu-id="e61ef-136">`char`<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="e61ef-136">`char` <sup>1</sup></span></span>|<span data-ttu-id="e61ef-137">SQLCHAR</span><span class="sxs-lookup"><span data-stu-id="e61ef-137">SQLCHAR</span></span>|  
|`varchar`|<span data-ttu-id="e61ef-138">SQLCHAR</span><span class="sxs-lookup"><span data-stu-id="e61ef-138">SQLCHAR</span></span>|  
|`nchar`|<span data-ttu-id="e61ef-139">SQLNCHAR</span><span class="sxs-lookup"><span data-stu-id="e61ef-139">SQLNCHAR</span></span>|  
|`nvarchar`|<span data-ttu-id="e61ef-140">SQLNCHAR</span><span class="sxs-lookup"><span data-stu-id="e61ef-140">SQLNCHAR</span></span>|  
|<span data-ttu-id="e61ef-141">`text` <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="e61ef-141">`text` <sup>2</sup></span></span>|<span data-ttu-id="e61ef-142">SQLCHAR</span><span class="sxs-lookup"><span data-stu-id="e61ef-142">SQLCHAR</span></span>|  
|<span data-ttu-id="e61ef-143">`ntext` <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="e61ef-143">`ntext` <sup>2</sup></span></span>|<span data-ttu-id="e61ef-144">SQLNCHAR</span><span class="sxs-lookup"><span data-stu-id="e61ef-144">SQLNCHAR</span></span>|  
|`binary`|<span data-ttu-id="e61ef-145">SQLBINARY</span><span class="sxs-lookup"><span data-stu-id="e61ef-145">SQLBINARY</span></span>|  
|`varbinary`|<span data-ttu-id="e61ef-146">SQLBINARY</span><span class="sxs-lookup"><span data-stu-id="e61ef-146">SQLBINARY</span></span>|  
|<span data-ttu-id="e61ef-147">`image` <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="e61ef-147">`image` <sup>2</sup></span></span>|<span data-ttu-id="e61ef-148">SQLBINARY</span><span class="sxs-lookup"><span data-stu-id="e61ef-148">SQLBINARY</span></span>|  
|`datetime`|<span data-ttu-id="e61ef-149">SQLDATETIME</span><span class="sxs-lookup"><span data-stu-id="e61ef-149">SQLDATETIME</span></span>|  
|`smalldatetime`|<span data-ttu-id="e61ef-150">SQLDATETIM4</span><span class="sxs-lookup"><span data-stu-id="e61ef-150">SQLDATETIM4</span></span>|  
|`decimal`|<span data-ttu-id="e61ef-151">SQLDECIMAL</span><span class="sxs-lookup"><span data-stu-id="e61ef-151">SQLDECIMAL</span></span>|  
|`numeric`|<span data-ttu-id="e61ef-152">SQLNUMERIC</span><span class="sxs-lookup"><span data-stu-id="e61ef-152">SQLNUMERIC</span></span>|  
|`float`|<span data-ttu-id="e61ef-153">SQLFLT8</span><span class="sxs-lookup"><span data-stu-id="e61ef-153">SQLFLT8</span></span>|  
|`real`|<span data-ttu-id="e61ef-154">SQLFLT4</span><span class="sxs-lookup"><span data-stu-id="e61ef-154">SQLFLT4</span></span>|  
|`int`|<span data-ttu-id="e61ef-155">SQLINT</span><span class="sxs-lookup"><span data-stu-id="e61ef-155">SQLINT</span></span>|  
|`bigint`|<span data-ttu-id="e61ef-156">SQLBIGINT</span><span class="sxs-lookup"><span data-stu-id="e61ef-156">SQLBIGINT</span></span>|  
|`smallint`|<span data-ttu-id="e61ef-157">SQLSMALLINT</span><span class="sxs-lookup"><span data-stu-id="e61ef-157">SQLSMALLINT</span></span>|  
|`tinyint`|<span data-ttu-id="e61ef-158">SQLTINYINT</span><span class="sxs-lookup"><span data-stu-id="e61ef-158">SQLTINYINT</span></span>|  
|`money`|<span data-ttu-id="e61ef-159">SQLMONEY</span><span class="sxs-lookup"><span data-stu-id="e61ef-159">SQLMONEY</span></span>|  
|`smallmoney`|<span data-ttu-id="e61ef-160">SQLMONEY4</span><span class="sxs-lookup"><span data-stu-id="e61ef-160">SQLMONEY4</span></span>|  
|`bit`|<span data-ttu-id="e61ef-161">SQLBIT</span><span class="sxs-lookup"><span data-stu-id="e61ef-161">SQLBIT</span></span>|  
|`uniqueidentifier`|<span data-ttu-id="e61ef-162">SQLUNIQUEID</span><span class="sxs-lookup"><span data-stu-id="e61ef-162">SQLUNIQUEID</span></span>|  
|`sql_variant`|<span data-ttu-id="e61ef-163">SQLVARIANT</span><span class="sxs-lookup"><span data-stu-id="e61ef-163">SQLVARIANT</span></span>|  
|`timestamp`|<span data-ttu-id="e61ef-164">SQLBINARY</span><span class="sxs-lookup"><span data-stu-id="e61ef-164">SQLBINARY</span></span>|  
|<span data-ttu-id="e61ef-165">UDT (tipo di dati definito dall'utente)</span><span class="sxs-lookup"><span data-stu-id="e61ef-165">UDT (a user-defined data type)</span></span>|<span data-ttu-id="e61ef-166">SQLUDT</span><span class="sxs-lookup"><span data-stu-id="e61ef-166">SQLUDT</span></span>|  
  
 <span data-ttu-id="e61ef-167"><sup>1</sup> i file di dati archiviati in formato carattere utilizzano `char` come tipo di archiviazione di file.</span><span class="sxs-lookup"><span data-stu-id="e61ef-167"><sup>1</sup> Data files that are stored in character format use `char` as the file storage type.</span></span> <span data-ttu-id="e61ef-168">Per questi file di dati di tipo carattere SQLCHAR costituisce pertanto l'unico tipo di dati incluso in file di formato.</span><span class="sxs-lookup"><span data-stu-id="e61ef-168">Therefore, for character data files, SQLCHAR is the only data type that appears in a format file.</span></span>  
  
 <span data-ttu-id="e61ef-169"><sup>2</sup> non è possibile eseguire l'importazione bulk di dati in `text` `ntext` colonne, e con `image` valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="e61ef-169"><sup>2</sup> You cannot bulk import data into `text`, `ntext`, and `image` columns that have DEFAULT values.</span></span>  
  
## <a name="additional-considerations-for-file-storage-types"></a><span data-ttu-id="e61ef-170">Ulteriori considerazioni sui tipi di archiviazione di file</span><span class="sxs-lookup"><span data-stu-id="e61ef-170">Additional Considerations for File Storage Types</span></span>  
 <span data-ttu-id="e61ef-171">Quando si esegue l'esportazione bulk da un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in un file di dati:</span><span class="sxs-lookup"><span data-stu-id="e61ef-171">When you bulk export data from an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to a data file:</span></span>  
  
-   <span data-ttu-id="e61ef-172">È sempre possibile specificare il tipo di archiviazione di file `char`.</span><span class="sxs-lookup"><span data-stu-id="e61ef-172">You can always specify `char` as the file storage type.</span></span>  
  
-   <span data-ttu-id="e61ef-173">Se si immette un tipo di archiviazione di file che rappresenta una conversione implicita non valida, **bcp** avrà esito negativo. ad esempio, anche se è possibile specificare `int` per `smallint` i dati, se si specifica `smallint` per `int` i dati, risultano errori di overflow.</span><span class="sxs-lookup"><span data-stu-id="e61ef-173">If you enter a file storage type that represents an invalid implicit conversion, **bcp** fails; for example, though you can specify `int` for `smallint` data, if you specify `smallint` for `int` data, overflow errors result.</span></span>  
  
-   <span data-ttu-id="e61ef-174">Se i tipi di dati non carattere, quali `float`, `money`, `datetime` o `int`, vengono archiviati in base al tipo dei relativi database, i dati verranno scritti nel file di dati nel formato nativo di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e61ef-174">When noncharacter data types such as `float`, `money`, `datetime`, or `int` are stored as their database types, the data is written to the data file in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] native format.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e61ef-175">Dopo l'impostazione interattiva di tutti i campi in un comando **bcp**, viene richiesto di salvare le risposte relative a ogni campo in un file di formato non XML.</span><span class="sxs-lookup"><span data-stu-id="e61ef-175">After you interactively specify all of the fields in a **bcp** command, the command prompts you save your responses for each field in a non-XML format file.</span></span> <span data-ttu-id="e61ef-176">Per altre informazioni sui file di formato non XML, vedere [File in formato non XML &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="e61ef-176">For more information on non-XML format files, see [Non-XML Format Files &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e61ef-177">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e61ef-177">See Also</span></span>  
 <span data-ttu-id="e61ef-178">[Utilità bcp](../../tools/bcp-utility.md) </span><span class="sxs-lookup"><span data-stu-id="e61ef-178">[bcp Utility](../../tools/bcp-utility.md) </span></span>  
 <span data-ttu-id="e61ef-179">[Tipi di dati &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e61ef-179">[Data Types &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql) </span></span>  
 <span data-ttu-id="e61ef-180">[Specificare la lunghezza del campo tramite bcp &#40;SQL Server&#41;](specify-field-length-by-using-bcp-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="e61ef-180">[Specify Field Length by Using bcp &#40;SQL Server&#41;](specify-field-length-by-using-bcp-sql-server.md) </span></span>  
 <span data-ttu-id="e61ef-181">[Specificare caratteri di terminazione del campo e della riga &#40;SQL Server&#41;](specify-field-and-row-terminators-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="e61ef-181">[Specify Field and Row Terminators &#40;SQL Server&#41;](specify-field-and-row-terminators-sql-server.md) </span></span>  
 [<span data-ttu-id="e61ef-182">Specificare la lunghezza del prefisso nei file di dati con bcp &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e61ef-182">Specify Prefix Length in Data Files by Using bcp &#40;SQL Server&#41;</span></span>](specify-prefix-length-in-data-files-by-using-bcp-sql-server.md)  
  
  
