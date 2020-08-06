---
title: Specificare la lunghezza del campo tramite bcp (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- native data format [SQL Server]
- default field lengths
- field length [SQL Server]
- data formats [SQL Server], field length
- bcp utility [SQL Server], field length
ms.assetid: 240f33ca-ef4a-413a-a4de-831885cb505b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 13343b4f3778df1bbe7ef1c99b3d06338f18631c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713163"
---
# <a name="specify-field-length-by-using-bcp-sql-server"></a><span data-ttu-id="a5ea3-102">Definizione della lunghezza di campo tramite bcp (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="a5ea3-102">Specify Field Length by Using bcp (SQL Server)</span></span>
  <span data-ttu-id="a5ea3-103">La lunghezza del campo indica il numero massimo di caratteri necessari per rappresentare i dati in formato carattere.</span><span class="sxs-lookup"><span data-stu-id="a5ea3-103">The field length indicates the maximum number of characters that are required to represent data in character format.</span></span> <span data-ttu-id="a5ea3-104">Se i dati sono archiviati in formato nativo, la lunghezza di campo è già nota. Ad esempio, il tipo di dati `int` accetta 4 byte.</span><span class="sxs-lookup"><span data-stu-id="a5ea3-104">The field length is already known if the data is stored in the native format; for example, the `int` data type takes 4 bytes.</span></span> <span data-ttu-id="a5ea3-105">Se è stato indicato 0 per la lunghezza del prefisso, il comando **bcp** richiede la lunghezza del campo, le lunghezze di campo predefinite e l'effetto della lunghezza del campo sull'archiviazione dei dati in file di dati contenenti `char` dati.</span><span class="sxs-lookup"><span data-stu-id="a5ea3-105">If you have indicated 0 for the prefix length, the **bcp** command prompts you for field length, the default field lengths, and the impact of field-length on data storage in data files that contain `char` data.</span></span>  
  
## <a name="the-bcp-prompt-for-field-length"></a><span data-ttu-id="a5ea3-106">Richiesta di lunghezza di campo da parte di bcp</span><span class="sxs-lookup"><span data-stu-id="a5ea3-106">The bcp Prompt for Field Length</span></span>  
 <span data-ttu-id="a5ea3-107">Se un comando interattivo **bcp** include l'opzione **in** o **out** senza l'opzione relativa al file di formato( **-f**) o al formato dei dati ( **-n**, **-c**, **-w**, or **-N**), viene chiesta la lunghezza del campo di ogni campo di dati, come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="a5ea3-107">If an interactive **bcp** command contains the **in** or **out** option without either the format file switch (**-f**) or a data-format switch (**-n**, **-c**, **-w**, or **-N**), the command prompts for the field length of each data field, as follows:</span></span>  
  
 `Enter length of field <field_name> [<default>]:`  
  
 <span data-ttu-id="a5ea3-108">Per un esempio contestualizzato di tale richiesta, vedere [Impostazione dei formati di dati per la compatibilità mediante &#40;SQL Server&#41;](specify-data-formats-for-compatibility-when-using-bcp-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="a5ea3-108">For an example that shows this prompt in context, see [Specify Data Formats for Compatibility when Using bcp &#40;SQL Server&#41;](specify-data-formats-for-compatibility-when-using-bcp-sql-server.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a5ea3-109">Dopo l'impostazione interattiva di tutti i campi in un comando **bcp**, viene richiesto di salvare le risposte relative a ogni campo in un file di formato non XML.</span><span class="sxs-lookup"><span data-stu-id="a5ea3-109">After you interactively specify all of the fields in a **bcp** command, the command prompts you save your responses for each field in a non-XML format file.</span></span> <span data-ttu-id="a5ea3-110">Per altre informazioni sui file di formato non XML, vedere [File in formato non XML &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="a5ea3-110">For more information on non-XML format files, see [Non-XML Format Files &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span></span>  
  
 <span data-ttu-id="a5ea3-111">La richiesta o meno della lunghezza del campo da parte del comando **bcp** dipende da diversi fattori, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="a5ea3-111">Whether a **bcp** command prompts for field length depends on several factors, as follows:</span></span>  
  
-   <span data-ttu-id="a5ea3-112">Quando si copiano tipi di dati con lunghezza non fissa e si specifica una lunghezza del prefisso pari a 0, **bcp** richiede una lunghezza del campo.</span><span class="sxs-lookup"><span data-stu-id="a5ea3-112">When you copy data types that are not of fixed length and you specify a prefix length of 0, **bcp** prompts for a field length.</span></span>  
  
-   <span data-ttu-id="a5ea3-113">Quando si convertono i dati di tipo non carattere in dati di tipo carattere, **bcp** suggerisce una lunghezza del campo predefinita sufficiente per archiviare i dati.</span><span class="sxs-lookup"><span data-stu-id="a5ea3-113">When converting noncharacter data to character data, **bcp** suggests a default field length large enough to store the data.</span></span>  
  
-   <span data-ttu-id="a5ea3-114">Se il tipo di file di archiviazione è non carattere, il comando **bcp** non richiede l'immissione della lunghezza del campo.</span><span class="sxs-lookup"><span data-stu-id="a5ea3-114">If the file storage type is noncharacter, the **bcp** command does not prompt for a field length.</span></span> <span data-ttu-id="a5ea3-115">I dati vengono archiviati usando il tipo di rappresentazione nativo di [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (formato nativo).</span><span class="sxs-lookup"><span data-stu-id="a5ea3-115">The data is stored in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] native data representation (native format).</span></span>  
  
## <a name="using-default-field-lengths"></a><span data-ttu-id="a5ea3-116">Utilizzo delle lunghezze di campo predefinite</span><span class="sxs-lookup"><span data-stu-id="a5ea3-116">Using Default Field Lengths</span></span>  
 <span data-ttu-id="a5ea3-117">In genere, [!INCLUDE[msCoName](../../includes/msconame-md.md)] consiglia di accettare i valori predefiniti per la lunghezza del campo proposti da **bcp**.</span><span class="sxs-lookup"><span data-stu-id="a5ea3-117">Generally, [!INCLUDE[msCoName](../../includes/msconame-md.md)] recommends that you accept the **bcp**-suggested default values for the field length.</span></span> <span data-ttu-id="a5ea3-118">Quando si crea un file in modalità carattere, l'utilizzo della lunghezza di campo predefinita consente di assicurare che i dati non verranno troncati e che non si verificheranno errori di overflow numerico</span><span class="sxs-lookup"><span data-stu-id="a5ea3-118">When a character mode data file is created, using the default field length ensures that data is not truncated and that numeric overflow errors do not occur.</span></span>  
  
 <span data-ttu-id="a5ea3-119">Se si specifica una lunghezza di campo non valida, è possibile che si verifichino errori.</span><span class="sxs-lookup"><span data-stu-id="a5ea3-119">If you specify a field length that is incorrect, problems can occur.</span></span> <span data-ttu-id="a5ea3-120">Ad esempio, se si copiano dati numerici e si specifica una lunghezza di campo insufficiente per i dati, l'utilità **bcp** visualizza un messaggio di overflow e i dati non vengono copiati.</span><span class="sxs-lookup"><span data-stu-id="a5ea3-120">For instance, if you copy numeric data and you specify a field length that is too short for the data, the **bcp** utility prints an overflow message and does not copy the data.</span></span> <span data-ttu-id="a5ea3-121">Inoltre, se si esportano `datetime` dati e si specifica una lunghezza di campo inferiore a 26 byte per la stringa di caratteri, l'utilità **bcp** tronca i dati senza un messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="a5ea3-121">Also, if you export `datetime` data and specify a field length of less than 26 bytes for the character string, the **bcp** utility truncates the data without an error message.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="a5ea3-122">Se si utilizza l'opzione predefinita per la dimensione, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] prevede di leggere una stringa intera.</span><span class="sxs-lookup"><span data-stu-id="a5ea3-122">When the default size option is used, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] expects to read an entire string.</span></span> <span data-ttu-id="a5ea3-123">In alcuni casi, l'utilizzo di una lunghezza di campo predefinita può provocare un errore di tipo "Fine del file imprevista".</span><span class="sxs-lookup"><span data-stu-id="a5ea3-123">In some situations, use of a default field length can lead to an "unexpected end of file" error.</span></span> <span data-ttu-id="a5ea3-124">In genere, questo errore si verifica con i `money` `datetime` tipi di dati e quando solo parte del campo previsto è presente nel file di dati, ad esempio quando un `datetime` valore di *mm* / *DD* / *AA* viene specificato senza il componente ora e è, pertanto, più breve della lunghezza prevista di 24 caratteri di un `datetime` valore nel `char` formato.</span><span class="sxs-lookup"><span data-stu-id="a5ea3-124">Typically, this error occurs with the `money` and `datetime` data types when only part of the expected field occurs in the data file; for example, when a `datetime` value of *mm*/*dd*/*yy* is specified without the time component and is, therefore, shorter than the expected 24 character length of a `datetime` value in `char` format.</span></span> <span data-ttu-id="a5ea3-125">Per evitare tale tipo di errore, utilizzare caratteri di terminazione del campo o campi dati di lunghezza fissa oppure modificare la lunghezza di campo predefinita, specificando un valore diverso.</span><span class="sxs-lookup"><span data-stu-id="a5ea3-125">To avoid this type of error, use field terminators or fixed-length data fields, or change the default field length by specifying another value.</span></span>  
  
### <a name="default-field-lengths-for-character-file-storage"></a><span data-ttu-id="a5ea3-126">Lunghezze di campo predefinite per l'archiviazione di file di caratteri</span><span class="sxs-lookup"><span data-stu-id="a5ea3-126">Default Field Lengths for Character File Storage</span></span>  
 <span data-ttu-id="a5ea3-127">Nella tabella seguente vengono elencate le lunghezze di campo predefinite per i dati da archiviare come tipo di archiviazione file di caratteri.</span><span class="sxs-lookup"><span data-stu-id="a5ea3-127">The following table lists the default field lengths for data to be stored as a character-file storage type.</span></span> <span data-ttu-id="a5ea3-128">La lunghezza dei dati che ammettono valori Null è uguale alla lunghezza dei dati che non ammettono valori Null.</span><span class="sxs-lookup"><span data-stu-id="a5ea3-128">Nullable data is the same length as nonnull data.</span></span>  
  
|<span data-ttu-id="a5ea3-129">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="a5ea3-129">Data type</span></span>|<span data-ttu-id="a5ea3-130">Lunghezza predefinita (caratteri)</span><span class="sxs-lookup"><span data-stu-id="a5ea3-130">Default length (characters)</span></span>|  
|---------------|-----------------------------------|  
|`char`|<span data-ttu-id="a5ea3-131">Lunghezza definita per la colonna</span><span class="sxs-lookup"><span data-stu-id="a5ea3-131">Length defined for the column</span></span>|  
|`varchar`|<span data-ttu-id="a5ea3-132">Lunghezza definita per la colonna</span><span class="sxs-lookup"><span data-stu-id="a5ea3-132">Length defined for the column</span></span>|  
|`nchar`|<span data-ttu-id="a5ea3-133">Due volte la lunghezza definita per la colonna</span><span class="sxs-lookup"><span data-stu-id="a5ea3-133">Twice the length defined for the column</span></span>|  
|`nvarchar`|<span data-ttu-id="a5ea3-134">Due volte la lunghezza definita per la colonna</span><span class="sxs-lookup"><span data-stu-id="a5ea3-134">Twice the length defined for the column</span></span>|  
|`Text`|<span data-ttu-id="a5ea3-135">0</span><span class="sxs-lookup"><span data-stu-id="a5ea3-135">0</span></span>|  
|`ntext`|<span data-ttu-id="a5ea3-136">0</span><span class="sxs-lookup"><span data-stu-id="a5ea3-136">0</span></span>|  
|`bit`|<span data-ttu-id="a5ea3-137">1</span><span class="sxs-lookup"><span data-stu-id="a5ea3-137">1</span></span>|  
|`binary`|<span data-ttu-id="a5ea3-138">Due volte la lunghezza definita per la colonna + 1</span><span class="sxs-lookup"><span data-stu-id="a5ea3-138">Twice the length defined for the column + 1</span></span>|  
|`varbinary`|<span data-ttu-id="a5ea3-139">Due volte la lunghezza definita per la colonna + 1</span><span class="sxs-lookup"><span data-stu-id="a5ea3-139">Twice the length defined for the column + 1</span></span>|  
|`image`|<span data-ttu-id="a5ea3-140">0</span><span class="sxs-lookup"><span data-stu-id="a5ea3-140">0</span></span>|  
|`datetime`|<span data-ttu-id="a5ea3-141">24</span><span class="sxs-lookup"><span data-stu-id="a5ea3-141">24</span></span>|  
|`smalldatetime`|<span data-ttu-id="a5ea3-142">24</span><span class="sxs-lookup"><span data-stu-id="a5ea3-142">24</span></span>|  
|`float`|<span data-ttu-id="a5ea3-143">30</span><span class="sxs-lookup"><span data-stu-id="a5ea3-143">30</span></span>|  
|`real`|<span data-ttu-id="a5ea3-144">30</span><span class="sxs-lookup"><span data-stu-id="a5ea3-144">30</span></span>|  
|`int`|<span data-ttu-id="a5ea3-145">12</span><span class="sxs-lookup"><span data-stu-id="a5ea3-145">12</span></span>|  
|`bigint`|<span data-ttu-id="a5ea3-146">19</span><span class="sxs-lookup"><span data-stu-id="a5ea3-146">19</span></span>|  
|`smallint`|<span data-ttu-id="a5ea3-147">7</span><span class="sxs-lookup"><span data-stu-id="a5ea3-147">7</span></span>|  
|`tinyint`|<span data-ttu-id="a5ea3-148">5</span><span class="sxs-lookup"><span data-stu-id="a5ea3-148">5</span></span>|  
|`money`|<span data-ttu-id="a5ea3-149">30</span><span class="sxs-lookup"><span data-stu-id="a5ea3-149">30</span></span>|  
|`smallmoney`|<span data-ttu-id="a5ea3-150">30</span><span class="sxs-lookup"><span data-stu-id="a5ea3-150">30</span></span>|  
|`decimal`|<span data-ttu-id="a5ea3-151">41\*</span><span class="sxs-lookup"><span data-stu-id="a5ea3-151">41\*</span></span>|  
|`numeric`|<span data-ttu-id="a5ea3-152">41\*</span><span class="sxs-lookup"><span data-stu-id="a5ea3-152">41\*</span></span>|  
|`uniqueidentifier`|<span data-ttu-id="a5ea3-153">37</span><span class="sxs-lookup"><span data-stu-id="a5ea3-153">37</span></span>|  
|`timestamp`|<span data-ttu-id="a5ea3-154">17</span><span class="sxs-lookup"><span data-stu-id="a5ea3-154">17</span></span>|  
|`varchar(max)`|<span data-ttu-id="a5ea3-155">0</span><span class="sxs-lookup"><span data-stu-id="a5ea3-155">0</span></span>|  
|`varbinary(max)`|<span data-ttu-id="a5ea3-156">0</span><span class="sxs-lookup"><span data-stu-id="a5ea3-156">0</span></span>|  
|`nvarchar(max)`|<span data-ttu-id="a5ea3-157">0</span><span class="sxs-lookup"><span data-stu-id="a5ea3-157">0</span></span>|  
|<span data-ttu-id="a5ea3-158">UDT</span><span class="sxs-lookup"><span data-stu-id="a5ea3-158">UDT</span></span>|<span data-ttu-id="a5ea3-159">Lunghezza della colonna UDT</span><span class="sxs-lookup"><span data-stu-id="a5ea3-159">Length of the user-defined term (UDT) column</span></span>|  
|<span data-ttu-id="a5ea3-160">XML</span><span class="sxs-lookup"><span data-stu-id="a5ea3-160">XML</span></span>|<span data-ttu-id="a5ea3-161">0</span><span class="sxs-lookup"><span data-stu-id="a5ea3-161">0</span></span>|  
  
 <span data-ttu-id="a5ea3-162">\*Per ulteriori informazioni sui `decimal` tipi di `numeric` dati e, vedere [decimal and numeric &#40;Transact-SQL&#41;](/sql/t-sql/data-types/decimal-and-numeric-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="a5ea3-162">\*For more information about the `decimal` and `numeric` data types, see [decimal and numeric &#40;Transact-SQL&#41;](/sql/t-sql/data-types/decimal-and-numeric-transact-sql).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a5ea3-163">Una colonna di tipo `tinyint` può contenere valori compresi tra 0 e 255. Il numero massimo di caratteri necessari per rappresentare un numero compreso nell'intervallo è tre (sono necessari tre caratteri per rappresentare i valori da 100 a 255).</span><span class="sxs-lookup"><span data-stu-id="a5ea3-163">A column of type `tinyint` can have values from 0 through 255; the maximum number of characters that are needed to represent any number in that range is three (representing values 100 through 255).</span></span>  
  
### <a name="default-field-lengths-for-native-file-storage"></a><span data-ttu-id="a5ea3-164">Lunghezze di campo predefinite per l'archiviazione di file nativi</span><span class="sxs-lookup"><span data-stu-id="a5ea3-164">Default Field Lengths for Native File Storage</span></span>  
 <span data-ttu-id="a5ea3-165">Nella tabella seguente vengono elencate le lunghezze di campo predefinite per i dati da archiviare come tipo di archiviazione file nativi.</span><span class="sxs-lookup"><span data-stu-id="a5ea3-165">The following table lists the default field lengths for data to be stored as native file storage type.</span></span> <span data-ttu-id="a5ea3-166">La lunghezza dei dati che ammettono valori Null è uguale alla lunghezza dei dati che non ammettono valori Null e i dati di tipo carattere vengono sempre archiviati nel formato carattere.</span><span class="sxs-lookup"><span data-stu-id="a5ea3-166">Nullable data is the same length as nonnull data, and character data is always stored in character format.</span></span>  
  
|<span data-ttu-id="a5ea3-167">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="a5ea3-167">Data type</span></span>|<span data-ttu-id="a5ea3-168">Lunghezza predefinita (caratteri)</span><span class="sxs-lookup"><span data-stu-id="a5ea3-168">Default length (characters)</span></span>|  
|---------------|-----------------------------------|  
|`bit`|<span data-ttu-id="a5ea3-169">1</span><span class="sxs-lookup"><span data-stu-id="a5ea3-169">1</span></span>|  
|`binary`|<span data-ttu-id="a5ea3-170">Lunghezza definita per la colonna</span><span class="sxs-lookup"><span data-stu-id="a5ea3-170">Length defined for the column</span></span>|  
|`varbinary`|<span data-ttu-id="a5ea3-171">Lunghezza definita per la colonna</span><span class="sxs-lookup"><span data-stu-id="a5ea3-171">Length defined for the column</span></span>|  
|`image`|<span data-ttu-id="a5ea3-172">0</span><span class="sxs-lookup"><span data-stu-id="a5ea3-172">0</span></span>|  
|`datetime`|<span data-ttu-id="a5ea3-173">8</span><span class="sxs-lookup"><span data-stu-id="a5ea3-173">8</span></span>|  
|`smalldatetime`|<span data-ttu-id="a5ea3-174">4</span><span class="sxs-lookup"><span data-stu-id="a5ea3-174">4</span></span>|  
|`float`|<span data-ttu-id="a5ea3-175">8</span><span class="sxs-lookup"><span data-stu-id="a5ea3-175">8</span></span>|  
|`real`|<span data-ttu-id="a5ea3-176">4</span><span class="sxs-lookup"><span data-stu-id="a5ea3-176">4</span></span>|  
|`int`|<span data-ttu-id="a5ea3-177">4</span><span class="sxs-lookup"><span data-stu-id="a5ea3-177">4</span></span>|  
|`bigint`|<span data-ttu-id="a5ea3-178">8</span><span class="sxs-lookup"><span data-stu-id="a5ea3-178">8</span></span>|  
|`smallint`|<span data-ttu-id="a5ea3-179">2</span><span class="sxs-lookup"><span data-stu-id="a5ea3-179">2</span></span>|  
|`tinyint`|<span data-ttu-id="a5ea3-180">1</span><span class="sxs-lookup"><span data-stu-id="a5ea3-180">1</span></span>|  
|`money`|<span data-ttu-id="a5ea3-181">8</span><span class="sxs-lookup"><span data-stu-id="a5ea3-181">8</span></span>|  
|`smallmoney`|<span data-ttu-id="a5ea3-182">4</span><span class="sxs-lookup"><span data-stu-id="a5ea3-182">4</span></span>|  
|<span data-ttu-id="a5ea3-183">`decimal`<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="a5ea3-183">`decimal` <sup>1</sup></span></span>|<sup>*</sup>|  
|<span data-ttu-id="a5ea3-184">`numeric`<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="a5ea3-184">`numeric` <sup>1</sup></span></span>|<sup>*</sup>|  
|`uniqueidentifier`|<span data-ttu-id="a5ea3-185">16</span><span class="sxs-lookup"><span data-stu-id="a5ea3-185">16</span></span>|  
|`timestamp`|<span data-ttu-id="a5ea3-186">8</span><span class="sxs-lookup"><span data-stu-id="a5ea3-186">8</span></span>|  
  
 <span data-ttu-id="a5ea3-187"><sup>1</sup> per altre informazioni sui `decimal` tipi di `numeric` dati e, vedere [Decimal and numeric &#40;Transact-SQL&#41;](/sql/t-sql/data-types/decimal-and-numeric-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="a5ea3-187"><sup>1</sup> For more information about the `decimal` and `numeric` data types, see [decimal and numeric &#40;Transact-SQL&#41;](/sql/t-sql/data-types/decimal-and-numeric-transact-sql).</span></span>  
  
 <span data-ttu-id="a5ea3-188">In tutti i casi illustrati in precedenza, per creare un file di dati per un successivo ricaricamento in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e ridurre al minimo lo spazio utilizzato per l'archiviazione, utilizzare un prefisso di lunghezza con il tipo di archiviazione nel file e la lunghezza di campo predefiniti.</span><span class="sxs-lookup"><span data-stu-id="a5ea3-188">In all of the preceding cases, to create a data file for later reloading into [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that keeps the storage space to a minimum, use a length prefix with the default file storage type and the default field length.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5ea3-189">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a5ea3-189">See Also</span></span>  
 <span data-ttu-id="a5ea3-190">[Utilità bcp](../../tools/bcp-utility.md) </span><span class="sxs-lookup"><span data-stu-id="a5ea3-190">[bcp Utility](../../tools/bcp-utility.md) </span></span>  
 <span data-ttu-id="a5ea3-191">[Tipi di dati &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a5ea3-191">[Data Types &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql) </span></span>  
 <span data-ttu-id="a5ea3-192">[Specificare caratteri di terminazione del campo e della riga &#40;SQL Server&#41;](specify-field-and-row-terminators-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="a5ea3-192">[Specify Field and Row Terminators &#40;SQL Server&#41;](specify-field-and-row-terminators-sql-server.md) </span></span>  
 <span data-ttu-id="a5ea3-193">[Specificare la lunghezza del prefisso nei file di dati tramite bcp &#40;SQL Server&#41;](specify-prefix-length-in-data-files-by-using-bcp-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="a5ea3-193">[Specify Prefix Length in Data Files by Using bcp &#40;SQL Server&#41;](specify-prefix-length-in-data-files-by-using-bcp-sql-server.md) </span></span>  
 <span data-ttu-id="a5ea3-194">[Specificare il tipo di archiviazione di file tramite bcp &#40;SQL Server&#41;](specify-file-storage-type-by-using-bcp-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="a5ea3-194">[Specify File Storage Type by Using bcp &#40;SQL Server&#41;](specify-file-storage-type-by-using-bcp-sql-server.md) </span></span>  
 [<span data-ttu-id="a5ea3-195">Mantenimento dei valori Null o uso dei valori predefiniti durante un'importazione bulk &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a5ea3-195">Keep Nulls or Use Default Values During Bulk Import &#40;SQL Server&#41;</span></span>](keep-nulls-or-use-default-values-during-bulk-import-sql-server.md)  
  
  
