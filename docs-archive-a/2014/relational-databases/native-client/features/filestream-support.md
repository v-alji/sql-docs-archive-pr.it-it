---
title: Supporto FILESTREAM | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- FILESTREAM [SQL Server], SQL Server Native Client
- SQL Server Native Client [FILESTREAM support]
ms.assetid: 1ad3400d-7fcd-40c9-87ae-f5afc61e0374
author: rothja
ms.author: jroth
ms.openlocfilehash: 18e9a002bfb205e2c0807234550998fe48120d20
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714280"
---
# <a name="filestream-support"></a><span data-ttu-id="e4115-102">Supporto FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="e4115-102">FILESTREAM Support</span></span>
  <span data-ttu-id="e4115-103">FILESTREAM consente di archiviare e accedere a valori binari di grandi dimensioni mediante [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] o accesso diretto al file system di Windows.</span><span class="sxs-lookup"><span data-stu-id="e4115-103">FILESTREAM provides a way to store and access large binary values, either through [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] or by direct access to the Windows file system.</span></span> <span data-ttu-id="e4115-104">Un valore binario di grandi dimensioni è un valore superiore a 2 gigabyte (GB).</span><span class="sxs-lookup"><span data-stu-id="e4115-104">A large binary value is a value larger than 2 gigabytes (GB).</span></span> <span data-ttu-id="e4115-105">Per altre informazioni sul supporto FILESTREAM avanzato, vedere [FILESTREAM &#40;SQL Server&#41;](../../blob/filestream-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="e4115-105">For more information about enhanced FILESTREAM support, see [FILESTREAM &#40;SQL Server&#41;](../../blob/filestream-sql-server.md).</span></span>  
  
 <span data-ttu-id="e4115-106">Quando si apre una connessione al database, per impostazione predefinita `@@TEXTSIZE` viene impostato su -1 (senza limiti).</span><span class="sxs-lookup"><span data-stu-id="e4115-106">When a database connection is opened, `@@TEXTSIZE` will be set to -1 ("unlimited"), by default.</span></span>  
  
 <span data-ttu-id="e4115-107">È anche possibile accedere alle colonne FILESTREAM e aggiornarle utilizzando l'API del file system di Windows.</span><span class="sxs-lookup"><span data-stu-id="e4115-107">It is also possible to access and update FILESTREAM columns using Windows file system APIs.</span></span>  
  
 <span data-ttu-id="e4115-108">Per altre informazioni, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="e4115-108">For more information, see the following topics:</span></span>  
  
-   [<span data-ttu-id="e4115-109">Supporto FILESTREAM &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="e4115-109">FILESTREAM Support &#40;OLE DB&#41;</span></span>](../ole-db/filestream-support-ole-db.md)  
  
-   [<span data-ttu-id="e4115-110">Supporto FILESTREAM &#40;&#41;ODBC</span><span class="sxs-lookup"><span data-stu-id="e4115-110">FILESTREAM Support &#40;ODBC&#41;</span></span>](../odbc/filestream-support-odbc.md)  
  
-   [<span data-ttu-id="e4115-111">Accesso ai dati FILESTREAM con OpenSqlFilestream</span><span class="sxs-lookup"><span data-stu-id="e4115-111">Access FILESTREAM Data with OpenSqlFilestream</span></span>](../../blob/access-filestream-data-with-opensqlfilestream.md)  
  
## <a name="querying-for-filestream-columns"></a><span data-ttu-id="e4115-112">Esecuzione di una query sulle colonne FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="e4115-112">Querying for FILESTREAM Columns</span></span>  
 <span data-ttu-id="e4115-113">I set di righe degli schemi in OLE DB non indicano se una colonna è di tipo FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="e4115-113">Schema rowsets in OLE DB will not report whether a column is a FILESTREAM column.</span></span> <span data-ttu-id="e4115-114">Impossibile utilizzare ITableDefinition in OLE DB per creare una colonna FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="e4115-114">ITableDefinition in OLE DB cannot be used to create a FILESTREAM column.</span></span>  
  
 <span data-ttu-id="e4115-115">Le funzioni di catalogo come SQLColumns in ODBC non segnaleranno se una colonna è una colonna FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="e4115-115">Catalog functions such as SQLColumns in ODBC will not report whether a column is a FILESTREAM column.</span></span>  
  
 <span data-ttu-id="e4115-116">Per creare colonne FILESTREAM o per rilevare quali colonne esistenti sono colonne FILESTREAM, è possibile utilizzare la `is_filestream` colonna della vista del catalogo [sys. Columns](/sql/relational-databases/system-catalog-views/sys-columns-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="e4115-116">To create FILESTREAM columns or to detect which existing columns are FILESTREAM columns, you can use the `is_filestream` column of the [sys.columns](/sql/relational-databases/system-catalog-views/sys-columns-transact-sql) catalog view.</span></span>  
  
 <span data-ttu-id="e4115-117">Di seguito è riportato un esempio:</span><span class="sxs-lookup"><span data-stu-id="e4115-117">The following is an example:</span></span>  
  
```  
-- Create a table with a FILESTREAM column.  
CREATE TABLE Bob_01 (GuidCol1 uniqueidentifier ROWGUIDCOL NOT NULL UNIQUE DEFAULT NEWID(), IntCol2 int, varbinaryCol3 varbinary(max) FILESTREAM);  
  
-- Find FILESTREAM columns.  
SELECT name FROM sys.columns WHERE is_filestream=1;  
  
-- Determine whether a column is a FILESTREAM column.  
SELECT is_filestream FROM sys.columns WHERE name = 'varbinaryCol3' AND object_id IN (SELECT object_id FROM sys.tables WHERE name='Bob_01');  
```  
  
## <a name="down-level-compatibility"></a><span data-ttu-id="e4115-118">Compatibilità con le versioni precedenti</span><span class="sxs-lookup"><span data-stu-id="e4115-118">Down-Level Compatibility</span></span>  
 <span data-ttu-id="e4115-119">Se il client è stato compilato utilizzando la versione di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client inclusa in [!INCLUDE[ssVersion2005](../../../includes/sscurrent-md.md)] , il `varbinary(max)` comportamento sarà compatibile con [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e4115-119">If your client was compiled using the version of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client that was included with [!INCLUDE[ssVersion2005](../../../includes/sscurrent-md.md)], `varbinary(max)` behavior will be compatible with [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)].</span></span> <span data-ttu-id="e4115-120">Questo significa che i dati restituiti avranno come dimensione massima 2 GB.</span><span class="sxs-lookup"><span data-stu-id="e4115-120">That is, the maximum size of returned data will be limited to 2 GB.</span></span> <span data-ttu-id="e4115-121">Per valori di dimensioni superiori a 2 GB, verrà eseguito un troncamento e restituito l'avviso "Troncamento a destra dei dati della stringa".</span><span class="sxs-lookup"><span data-stu-id="e4115-121">For result values larger that 2 GB, truncation will occur and a "string data right truncation" warning will be returned.</span></span>  
  
 <span data-ttu-id="e4115-122">Quando la compatibilità con il tipo di dati è impostata su 80, il comportamento client sarà coerente con il comportamento del client legacy.</span><span class="sxs-lookup"><span data-stu-id="e4115-122">When data-type compatibility is set to 80, client behavior will be consistent with down-level client behavior.</span></span>  
  
 <span data-ttu-id="e4115-123">Per i client che utilizzano SQLOLEDB o altri provider rilasciati prima [!INCLUDE[ssVersion2005](../../../includes/ssnoversion-md.md)] di Native client, `varbinary(max)` verrà eseguito il mapping all'immagine.</span><span class="sxs-lookup"><span data-stu-id="e4115-123">For clients that use SQLOLEDB or other providers that were released before the [!INCLUDE[ssVersion2005](../../../includes/ssnoversion-md.md)] Native Client, `varbinary(max)` will be mapped to image.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4115-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e4115-124">See Also</span></span>  
 [<span data-ttu-id="e4115-125">Funzionalità di SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="e4115-125">SQL Server Native Client Features</span></span>](sql-server-native-client-features.md)  
  
  
