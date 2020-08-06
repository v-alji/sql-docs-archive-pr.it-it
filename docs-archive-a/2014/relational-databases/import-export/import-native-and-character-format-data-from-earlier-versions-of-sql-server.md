---
title: Importare dati in formato nativo e carattere da versioni precedenti di SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- earlier versions [SQL Server], import and export data formats
- -V switch
- data formats [SQL Server], earlier versions
- previous versions [SQL Server], import and export data formats
ms.assetid: e644696f-9017-428e-a5b3-d445d1c630b3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 274c984d6ecec8af8f5bea27496450a45fc2f1df
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635587"
---
# <a name="import-native-and-character-format-data-from-earlier-versions-of-sql-server"></a><span data-ttu-id="50f20-102">Importare dati in formato nativo e carattere da versioni precedenti di SQL Server</span><span class="sxs-lookup"><span data-stu-id="50f20-102">Import Native and Character Format Data from Earlier Versions of SQL Server</span></span>
  <span data-ttu-id="50f20-103">In [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]è possibile usare **bcp** per importare dati in formato nativo e carattere da [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]o da [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] usando l'opzione **-V** .</span><span class="sxs-lookup"><span data-stu-id="50f20-103">In [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], you can use **bcp** to import native and character format data from [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], or [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] by using the **-V** switch.</span></span> <span data-ttu-id="50f20-104">Se si usa l'opzione **-V** , in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] vengono usati tipi di dati della versione precedente specificata di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]e il formato del file di dati corrisponderà al formato della versione precedente in questione.</span><span class="sxs-lookup"><span data-stu-id="50f20-104">The **-V** switch causes [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] to use data types from the specified earlier version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], and the data file format are the same as the format in that earlier version.</span></span>  
  
 <span data-ttu-id="50f20-105">Per specificare una versione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] precedente per un file di dati, usare l'opzione **-V** con uno dei qualificatori seguenti:</span><span class="sxs-lookup"><span data-stu-id="50f20-105">To specify an earlier [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] version for a data file, use the **-V** switch with one of the following qualifiers:</span></span>  
  
|<span data-ttu-id="50f20-106">Versione di SQL Server</span><span class="sxs-lookup"><span data-stu-id="50f20-106">SQL Server version</span></span>|<span data-ttu-id="50f20-107">Qualifier</span><span class="sxs-lookup"><span data-stu-id="50f20-107">Qualifier</span></span>|  
|------------------------|---------------|  
|[!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)]|<span data-ttu-id="50f20-108">**-V80**</span><span class="sxs-lookup"><span data-stu-id="50f20-108">**-V80**</span></span>|  
|[!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]|<span data-ttu-id="50f20-109">**-V90**</span><span class="sxs-lookup"><span data-stu-id="50f20-109">**-V90**</span></span>|  
|[!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]|<span data-ttu-id="50f20-110">**-V100**</span><span class="sxs-lookup"><span data-stu-id="50f20-110">**-V100**</span></span>|  
|[!INCLUDE[ssSQL11](../../includes/sssql11-md.md)]|<span data-ttu-id="50f20-111">**-V 110**</span><span class="sxs-lookup"><span data-stu-id="50f20-111">**-V 110**</span></span>|  
  
## <a name="interpretation-of-data-types"></a><span data-ttu-id="50f20-112">Interpretazione dei tipi di dati</span><span class="sxs-lookup"><span data-stu-id="50f20-112">Interpretation of Data Types</span></span>  
 [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] <span data-ttu-id="50f20-113">e versioni successive supportano alcuni nuovi tipi.</span><span class="sxs-lookup"><span data-stu-id="50f20-113">and later versions have support for some new types.</span></span> <span data-ttu-id="50f20-114">Se si desidera importare un nuovo tipo di dati in una versione precedente di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , è necessario archiviarlo in un formato leggibile dai client **bcp** precedenti.</span><span class="sxs-lookup"><span data-stu-id="50f20-114">When you want to import a new data type into an earlier [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] version, the data type must be stored in a format that readable by the older **bcp** clients.</span></span> <span data-ttu-id="50f20-115">Nella seguente tabella viene riepilogata la modalità di conversione dei nuovi tipi di dati per la compatibilità con le versioni precedenti di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="50f20-115">The following table summarizes how the new data types are converted for compatibility with the earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
|<span data-ttu-id="50f20-116">Nuovi tipi di dati in SQL Server 2005</span><span class="sxs-lookup"><span data-stu-id="50f20-116">New data types in SQL Server 2005</span></span>|<span data-ttu-id="50f20-117">Tipi di dati compatibili nella versione 6*x*</span><span class="sxs-lookup"><span data-stu-id="50f20-117">Compatible data types in version 6*x*</span></span>|<span data-ttu-id="50f20-118">Tipi di dati compatibili nella versione 70</span><span class="sxs-lookup"><span data-stu-id="50f20-118">Compatible data types in version 70</span></span>|<span data-ttu-id="50f20-119">Tipi di dati compatibili nella versione 80</span><span class="sxs-lookup"><span data-stu-id="50f20-119">Compatible data types in version 80</span></span>|  
|---------------------------------------|-------------------------------------------|-----------------------------------------|-----------------------------------------|  
|`bigint`|`decimal`|`decimal`|*|  
|`sql_variant`|`text`|`nvarchar(4000)`|*|  
|`varchar(max)`|`text`|`text`|`text`|  
|`nvarchar(max)`|`ntext`|`ntext`|`ntext`|  
|`varbinary(max)`|`image`|`image`|`image`|  
|<span data-ttu-id="50f20-120">XML</span><span class="sxs-lookup"><span data-stu-id="50f20-120">XML</span></span>|`ntext`|`ntext`|`ntext`|  
|<span data-ttu-id="50f20-121">Tipo definito dall'utente<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="50f20-121">UDT<sup>1</sup></span></span>|`image`|`image`|`image`|  
  
 <span data-ttu-id="50f20-122">\*Questo tipo è supportato in modo nativo.</span><span class="sxs-lookup"><span data-stu-id="50f20-122">\* This type is natively supported.</span></span>  
  
 <span data-ttu-id="50f20-123"><sup>1</sup> UDT indica un tipo definito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="50f20-123"><sup>1</sup> UDT indicates a user defined type.</span></span>  
  
## <a name="exporting-using--v-80"></a><span data-ttu-id="50f20-124">Esportazione usando –V 80</span><span class="sxs-lookup"><span data-stu-id="50f20-124">Exporting using -V 80</span></span>  
 <span data-ttu-id="50f20-125">Quando si esegue l'esportazione bulk di dati tramite l'opzione **-V80** , i dati di tipo,,, `nvarchar(max)` `varchar(max)` `varbinary(max)` XML e UDT in modalità nativa vengono archiviati con un prefisso a 4 byte, ad esempio i `text` `image` dati, e `ntext` , anziché con un prefisso a 8 byte, che è l'impostazione predefinita per [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="50f20-125">When you bulk export data by using the **-V80** switch, `nvarchar(max)`, `varchar(max)`, `varbinary(max)`, XML, and UDT data in native mode are stored with a 4-byte prefix, like `text`, `image`, and `ntext` data, rather than with an 8-byte prefix, which is the default for [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later versions.</span></span>  
  
## <a name="copying-date-values"></a><span data-ttu-id="50f20-126">Copia dei valori di data</span><span class="sxs-lookup"><span data-stu-id="50f20-126">Copying Date Values</span></span>  
 <span data-ttu-id="50f20-127">**bcp** consente di usare l'API della copia bulk ODBC.</span><span class="sxs-lookup"><span data-stu-id="50f20-127">**bcp** uses the ODBC bulk copy API.</span></span> <span data-ttu-id="50f20-128">Quindi, per importare i valori di dati in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], **bcp** usa il formato di data ODBC (*aaaa-mm-gg hh:mm:ss*[ *.f...* ]).</span><span class="sxs-lookup"><span data-stu-id="50f20-128">Therefore, to import date values into [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], **bcp** uses the ODBC date format (*yyyy-mm-dd hh:mm:ss*[*.f...*]).</span></span>  
  
 <span data-ttu-id="50f20-129">Il comando **bcp** Esporta i file di dati in formato carattere usando il formato predefinito ODBC per `datetime` `smalldatetime` i valori e.</span><span class="sxs-lookup"><span data-stu-id="50f20-129">The **bcp** command exports character format data files using the ODBC default format for `datetime` and `smalldatetime` values.</span></span> <span data-ttu-id="50f20-130">Ad esempio, per una colonna `datetime` contenente la data `12 Aug 1998` verrà eseguita la copia bulk in un file di dati come stringa di caratteri `1998-08-12 00:00:00.000`.</span><span class="sxs-lookup"><span data-stu-id="50f20-130">For example, a `datetime` column containing the date `12 Aug 1998` is bulk copied to a data file as the character string `1998-08-12 00:00:00.000`.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="50f20-131">Quando si importano dati in un `smalldatetime` campo con **bcp**, assicurarsi che il valore per seconds sia 00,000; in caso contrario, l'operazione avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="50f20-131">When importing data into a `smalldatetime` field using **bcp**, be sure the value for seconds is 00.000; otherwise the operation will fail.</span></span> <span data-ttu-id="50f20-132">Il tipo di dati `smalldatetime` contiene solo valori approssimati al minuto più vicino.</span><span class="sxs-lookup"><span data-stu-id="50f20-132">The `smalldatetime` data type only holds values to the nearest minute.</span></span> <span data-ttu-id="50f20-133">In questa istanza, le istruzioni BULK INSERT e INSERT ... SELECT \* FROM OPENROWSET(BULK...) verranno eseguite ma il valore dei secondi verrà troncato.</span><span class="sxs-lookup"><span data-stu-id="50f20-133">BULK INSERT and INSERT ... SELECT \* FROM OPENROWSET(BULK...) will not fail in this instance but will truncate the seconds value.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="50f20-134">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="50f20-134">Related Tasks</span></span>  
 <span data-ttu-id="50f20-135">**Per utilizzare formati di dati per l'importazione o l'esportazione bulk**</span><span class="sxs-lookup"><span data-stu-id="50f20-135">**To use data formats for bulk import or bulk export**</span></span>  
  
-   [<span data-ttu-id="50f20-136">Utilizzo del formato carattere per l'importazione o l'esportazione di dati &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="50f20-136">Use Character Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-character-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="50f20-137">Usare il formato nativo per importare o esportare dati &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="50f20-137">Use Native Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-native-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="50f20-138">Utilizzo del formato carattere Unicode per l'importazione o l'esportazione di dati &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="50f20-138">Use Unicode Character Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-unicode-character-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="50f20-139">Usare il formato Unicode nativo per importare o esportare dati &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="50f20-139">Use Unicode Native Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-unicode-native-format-to-import-or-export-data-sql-server.md)  
  
 
  
## <a name="see-also"></a><span data-ttu-id="50f20-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="50f20-140">See Also</span></span>  
 <span data-ttu-id="50f20-141">[Utilità bcp](../../tools/bcp-utility.md) </span><span class="sxs-lookup"><span data-stu-id="50f20-141">[bcp Utility](../../tools/bcp-utility.md) </span></span>  
 <span data-ttu-id="50f20-142">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="50f20-142">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span></span>  
 <span data-ttu-id="50f20-143">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="50f20-143">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span></span>  
 <span data-ttu-id="50f20-144">[Tipi di dati &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="50f20-144">[Data Types &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql) </span></span>  
 <span data-ttu-id="50f20-145">[Compatibilità con le versioni precedenti del motore di database di SQL Server](../../database-engine/sql-server-database-engine-backward-compatibility.md) </span><span class="sxs-lookup"><span data-stu-id="50f20-145">[SQL Server Database Engine Backward Compatibility](../../database-engine/sql-server-database-engine-backward-compatibility.md) </span></span>  
 [<span data-ttu-id="50f20-146">CAST e CONVERT &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="50f20-146">CAST and CONVERT &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/cast-and-convert-transact-sql)  
  
  
