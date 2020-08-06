---
title: Creare una tabella per archiviare dati FILESTREAM | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: filestream
ms.topic: conceptual
helpviewer_keywords:
- FILESTREAM [SQL Server], table storage
ms.assetid: 029c3059-5c83-43e2-a859-9027031b7de1
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 484d7b58ce949df79dc7e17ee4dc7307b70c0154
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715408"
---
# <a name="create-a-table-for-storing-filestream-data"></a><span data-ttu-id="5e554-102">Creazione di una tabella per archiviare dati FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="5e554-102">Create a Table for Storing FILESTREAM Data</span></span>
  <span data-ttu-id="5e554-103">In questo argomento viene illustrato come creare una tabella per archiviare dati FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="5e554-103">This topic shows how to create a table for storing FILESTREAM data.</span></span>  
  
 <span data-ttu-id="5e554-104">Quando il database presenta un filegroup FILESTREAM, è possibile creare o modificare tabelle per archiviare i dati FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="5e554-104">When the database has a FILESTREAM filegroup, you can create or modify tables to store FILESTREAM data.</span></span> <span data-ttu-id="5e554-105">Per specificare che una colonna che contiene dati FILESTREAM, creare una colonna `varbinary(max)` e aggiungere l'attributo FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="5e554-105">To specify that a column contains FILESTREAM data, you create a `varbinary(max)` column and add the FILESTREAM attribute.</span></span>  
  
### <a name="to-create-a-table-to-store-filestream-data"></a><span data-ttu-id="5e554-106">Per creare una tabella per archiviare dati FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="5e554-106">To create a table to store FILESTREAM data</span></span>  
  
1.  <span data-ttu-id="5e554-107">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]fare clic su **Nuova query** per visualizzare l'editor di query.</span><span class="sxs-lookup"><span data-stu-id="5e554-107">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], click **New Query** to display the Query Editor.</span></span>  
  
2.  <span data-ttu-id="5e554-108">Copiare il codice [!INCLUDE[tsql](../../includes/tsql-md.md)] dall'esempio seguente e incollarlo nell'Editor di query.</span><span class="sxs-lookup"><span data-stu-id="5e554-108">Copy the [!INCLUDE[tsql](../../includes/tsql-md.md)] code from the following example into the Query Editor.</span></span> <span data-ttu-id="5e554-109">Tramite il codice [!INCLUDE[tsql](../../includes/tsql-md.md)] viene creata una tabella abilitata per FILESTREAM denominata Records.</span><span class="sxs-lookup"><span data-stu-id="5e554-109">This [!INCLUDE[tsql](../../includes/tsql-md.md)] code creates a FILESTREAM-enabled table called Records.</span></span>  
  
3.  <span data-ttu-id="5e554-110">Per creare la tabella, fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="5e554-110">To create the table, click **Execute**.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5e554-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="5e554-111">Example</span></span>  
 <span data-ttu-id="5e554-112">Nel codice di esempio seguente viene descritto come creare una tabella denominata `Records`.</span><span class="sxs-lookup"><span data-stu-id="5e554-112">The following code example shows how to create a table that is named `Records`.</span></span> <span data-ttu-id="5e554-113">La colonna `Id` è una colonna `ROWGUIDCOL` ed è necessaria per utilizzare dati FILESTREAM con API Win32.</span><span class="sxs-lookup"><span data-stu-id="5e554-113">The `Id` column is a `ROWGUIDCOL` column and is required to use FILESTREAM data with Win32 APIs.</span></span> <span data-ttu-id="5e554-114">La colonna `SerialNumber` è di tipo `UNIQUE INTEGER`.</span><span class="sxs-lookup"><span data-stu-id="5e554-114">The `SerialNumber` column is a `UNIQUE INTEGER`.</span></span> <span data-ttu-id="5e554-115">La colonna `Chart` è una colonna `FILESTREAM` e viene utilizzata per archiviare `Chart` nel file system.</span><span class="sxs-lookup"><span data-stu-id="5e554-115">The `Chart` column is a `FILESTREAM` column and is used to store the `Chart` in the file system.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5e554-116">Questo esempio fa riferimento al database Archive creato in [Creazione di un database abilitato per FILESTREAM](create-a-filestream-enabled-database.md).</span><span class="sxs-lookup"><span data-stu-id="5e554-116">This example refers to the Archive database that is created in [Create a FILESTREAM-Enabled Database](create-a-filestream-enabled-database.md).</span></span>  
  
 [!code-sql[FILESTREAM#FS_CreateTable](../../snippets/tsql/SQL15/tsql/filestream/transact-sql/filestream.sql#fs_createtable)]  
  
## <a name="see-also"></a><span data-ttu-id="5e554-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5e554-117">See Also</span></span>  
 <span data-ttu-id="5e554-118">[CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="5e554-118">[CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql) </span></span>  
 [<span data-ttu-id="5e554-119">ALTER TABLE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="5e554-119">ALTER TABLE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-table-transact-sql)  
  
  
