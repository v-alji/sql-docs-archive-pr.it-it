---
title: Importazione bulk di dati di oggetti di grandi dimensioni tramite il provider di set di righe con utilizzo bulk OPENROWSET (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- SINGLE_NCLOB option
- bulk rowset providers [SQL Server]
- bulk importing [SQL Server], data formats
- OPENROWSET function, bulk importing large data
- SINGLE_CLOB option
- data formats [SQL Server], large-object data
- large data, bulk imports
- SINGLE_BLOB option
ms.assetid: 171cdd5c-1e47-4bd7-b99a-4f0fd4e10526
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 0f43aa2fa5e7f7ef0b2c8f1f6e5e6ff28e02f9f1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627702"
---
# <a name="bulk-import-large-object-data-by-using-the-openrowset-bulk-rowset-provider-sql-server"></a><span data-ttu-id="ba2e5-102">Importazione bulk di dati di tipo LOB tramite il provider di set di righe con lettura bulk OPENROWSET (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="ba2e5-102">Bulk Import Large-Object Data by using the OPENROWSET Bulk Rowset Provider (SQL Server)</span></span>
  <span data-ttu-id="ba2e5-103">Il provider di set di righe con lettura bulk OPENROWSET di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] consente di eseguire un'importazione bulk di un file di dati come dati di grandi dimensioni (LOB, Large Object).</span><span class="sxs-lookup"><span data-stu-id="ba2e5-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] OPENROWSET Bulk Rowset Provider enables you to bulk import a data file as large-object data.</span></span>  
  
 <span data-ttu-id="ba2e5-104">I tipi di dati LOB (Large Object) supportati dal provider di tipo bulk per set di righe OPENROWSET sono **varbinary**(max) o **image**, **varchar**(max) o **text**e **nvarchar**(max) o **ntext**.</span><span class="sxs-lookup"><span data-stu-id="ba2e5-104">The large-object data types supported by OPENROWSET Bulk Rowset Provider are **varbinary**(max) or **image**, **varchar**(max) or **text**, and **nvarchar**(max) or **ntext**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ba2e5-105">I tipi di dati **image**, **text** e **ntext** sono deprecati.</span><span class="sxs-lookup"><span data-stu-id="ba2e5-105">The **image**, **text** and **ntext** data types are deprecated.</span></span>  
  
 <span data-ttu-id="ba2e5-106">La clausola OPENROWSET BULK supporta tre opzioni per l'importazione del contenuto di un file di dati sotto forma di set di righe caratterizzato da una sola riga e una sola colonna.</span><span class="sxs-lookup"><span data-stu-id="ba2e5-106">The OPENROWSET BULK clause supports three options for importing the contents of a data file as a single-row, single-column rowset.</span></span> <span data-ttu-id="ba2e5-107">È possibile specificare una di queste opzioni relative ai dati di tipo LOB, invece di utilizzare un file di formato.</span><span class="sxs-lookup"><span data-stu-id="ba2e5-107">You can specify one of these large-object options instead of using a format file.</span></span> <span data-ttu-id="ba2e5-108">Le opzioni disponibili sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="ba2e5-108">These options are as follows:</span></span>  
  
 <span data-ttu-id="ba2e5-109">SINGLE_BLOB</span><span class="sxs-lookup"><span data-stu-id="ba2e5-109">SINGLE_BLOB</span></span>  
 <span data-ttu-id="ba2e5-110">Legge il contenuto di *data_file* come un'unica riga e restituisce il contenuto come set di righe di tipo **varbinary(max)** con una sola colonna.</span><span class="sxs-lookup"><span data-stu-id="ba2e5-110">Reads the contents of *data_file* as a single-row, returns the contents as a single-column rowset of type **varbinary(max)**.</span></span>  
  
 <span data-ttu-id="ba2e5-111">SINGLE_CLOB</span><span class="sxs-lookup"><span data-stu-id="ba2e5-111">SINGLE_CLOB</span></span>  
 <span data-ttu-id="ba2e5-112">Legge il contenuto del file di dati specificato come caratteri e restituisce il contenuto come set di righe di tipo **varchar(max)** con una sola riga e una sola colonna, usando le regole di confronto del database corrente, ad esempio un documento di testo o di [!INCLUDE[msCoName](../../includes/msconame-md.md)] Word.</span><span class="sxs-lookup"><span data-stu-id="ba2e5-112">Reads the contents of the specified data file as characters, returns the contents as a single-row, single-column rowset of type **varchar(max)**, using the collation of the current database; such as a text or [!INCLUDE[msCoName](../../includes/msconame-md.md)] Word document.</span></span>  
  
 <span data-ttu-id="ba2e5-113">SINGLE_NCLOB</span><span class="sxs-lookup"><span data-stu-id="ba2e5-113">SINGLE_NCLOB</span></span>  
 <span data-ttu-id="ba2e5-114">Legge il contenuto del file di dati specificato come Unicode e restituisce il contenuto come set di righe di tipo **nvarchar(max)** con una sola riga e una sola colonna, usando le regole di confronto del database corrente.</span><span class="sxs-lookup"><span data-stu-id="ba2e5-114">Reads the contents of the specified data file as Unicode, returns the contents as a single-row, single-column rowset of type **nvarchar(max)**, using the collation of the current database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba2e5-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ba2e5-115">See Also</span></span>  
 <span data-ttu-id="ba2e5-116">[Importazione di dati per operazioni bulk utilizzando BULK INSERT o OPENROWSET&#40;BULK...&#41; &#40;SQL Server&#41;](import-bulk-data-by-using-bulk-insert-or-openrowset-bulk-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="ba2e5-116">[Import Bulk Data by Using BULK INSERT or OPENROWSET&#40;BULK...&#41; &#40;SQL Server&#41;](import-bulk-data-by-using-bulk-insert-or-openrowset-bulk-sql-server.md) </span></span>  
 <span data-ttu-id="ba2e5-117">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ba2e5-117">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="ba2e5-118">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ba2e5-118">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span></span>  
 <span data-ttu-id="ba2e5-119">[Mantenimento dei valori Null o utilizzo dei valori predefiniti durante un'importazione bulk &#40;SQL Server&#41;](keep-nulls-or-use-default-values-during-bulk-import-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="ba2e5-119">[Keep Nulls or Use Default Values During Bulk Import &#40;SQL Server&#41;](keep-nulls-or-use-default-values-during-bulk-import-sql-server.md) </span></span>  
 <span data-ttu-id="ba2e5-120">[Utilità bcp](../../tools/bcp-utility.md) </span><span class="sxs-lookup"><span data-stu-id="ba2e5-120">[bcp Utility](../../tools/bcp-utility.md) </span></span>  
 [<span data-ttu-id="ba2e5-121">BULK INSERT &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ba2e5-121">BULK INSERT &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/bulk-insert-transact-sql)  
  
  
