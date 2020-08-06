---
title: Creare un database abilitato per FILESTREAM | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: filestream
ms.topic: conceptual
helpviewer_keywords:
- FILESTREAM [SQL Server], FILESTREAM-enabled databases
ms.assetid: 0fc16356-76f7-44b8-a58b-f0b7c43694ec
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 0fe6e5bc6e4f60bc0703482f3bf4d761104b3c5f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716379"
---
# <a name="create-a-filestream-enabled-database"></a><span data-ttu-id="d8add-102">Creazione di un database abilitato per FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="d8add-102">Create a FILESTREAM-Enabled Database</span></span>
  <span data-ttu-id="d8add-103">In questo argomento viene illustrato come creare un database che supporti FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="d8add-103">This topic shows how to create a database that supports FILESTREAM.</span></span> <span data-ttu-id="d8add-104">Poiché in FILESTREAM viene utilizzato un tipo speciale di filegroup, quando si crea il database è necessario specificare la clausola CONTAINS FILESTREAM per almeno un filegroup.</span><span class="sxs-lookup"><span data-stu-id="d8add-104">Because FILESTREAM uses a special type of filegroup, when you create the database, you must specify the CONTAINS FILESTREAM clause for at least one filegroup.</span></span>  
  
 <span data-ttu-id="d8add-105">Un filegroup FILESTREAM può contenere più di un file.</span><span class="sxs-lookup"><span data-stu-id="d8add-105">A FILESTREAM filegroup can contain more than one file.</span></span> <span data-ttu-id="d8add-106">Per un esempio di codice che illustra come creare un filegroup FILESTREAM contenente più file, vedere [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="d8add-106">For a code example that demonstrates how to create a FILESTREAM filegroup that contains multiple files, see [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql).</span></span>  
  
### <a name="to-create-a-filestream-enabled-database"></a><span data-ttu-id="d8add-107">Per creare un database abilitato per FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="d8add-107">To create a FILESTREAM-enabled database</span></span>  
  
1.  <span data-ttu-id="d8add-108">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]fare clic su **Nuova query** per visualizzare l'editor di query.</span><span class="sxs-lookup"><span data-stu-id="d8add-108">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], click **New Query** to display the Query Editor.</span></span>  
  
2.  <span data-ttu-id="d8add-109">Copia il [!INCLUDE[tsql](../../includes/tsql-md.md)] codice consente di creare un database abilitato per FILESTREAM denominato Archive.</span><span class="sxs-lookup"><span data-stu-id="d8add-109">Copy the [!INCLUDE[tsql](../../includes/tsql-md.md)] code creates a FILESTREAM-enabled database called Archive.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d8add-110">Per eseguire questo script, è necessario che la directory C:\Data esista.</span><span class="sxs-lookup"><span data-stu-id="d8add-110">For this script, the directory C:\Data must exist.</span></span>  
  
3.  <span data-ttu-id="d8add-111">Per compilare il database, fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="d8add-111">To build the database, click **Execute**.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d8add-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="d8add-112">Example</span></span>  
 <span data-ttu-id="d8add-113">Nel codice di esempio seguente viene creato un database denominato `Archive`.</span><span class="sxs-lookup"><span data-stu-id="d8add-113">The following code example creates a database that is named `Archive`.</span></span> <span data-ttu-id="d8add-114">Il database contiene tre filegroup: `PRIMARY`, `Arch1`e `FileStreamGroup1`.</span><span class="sxs-lookup"><span data-stu-id="d8add-114">The database contains three filegroups: `PRIMARY`, `Arch1`, and `FileStreamGroup1`.</span></span> <span data-ttu-id="d8add-115">`PRIMARY` e `Arch1` sono filegroup normali che non possono contenere dati FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="d8add-115">`PRIMARY` and `Arch1` are regular filegroups that cannot contain FILESTREAM data.</span></span> <span data-ttu-id="d8add-116">`FileStreamGroup1` è il filegroup `FILESTREAM` .</span><span class="sxs-lookup"><span data-stu-id="d8add-116">`FileStreamGroup1` is the `FILESTREAM` filegroup.</span></span>  
  
```sql  
CREATE DATABASE Archive   
ON  
PRIMARY ( NAME = Arch1,  
    FILENAME = 'c:\data\archdat1.mdf'),  
FILEGROUP FileStreamGroup1 CONTAINS FILESTREAM( NAME = Arch3,  
    FILENAME = 'c:\data\filestream1')  
LOG ON  ( NAME = Archlog1,  
    FILENAME = 'c:\data\archlog1.ldf')  
GO  
```  
  
 <span data-ttu-id="d8add-117">Per un filegroup `FILESTREAM` , `FILENAME` fa riferimento a un percorso.</span><span class="sxs-lookup"><span data-stu-id="d8add-117">For a `FILESTREAM` filegroup, `FILENAME` refers to a path.</span></span> <span data-ttu-id="d8add-118">È necessario che il percorso fino all'ultima cartella esista già, mentre l'ultima cartella non deve essere presente.</span><span class="sxs-lookup"><span data-stu-id="d8add-118">The path up to the last folder must exist, and the last folder must not exist.</span></span> <span data-ttu-id="d8add-119">In questo esempio è necessario che `c:\data` esista.</span><span class="sxs-lookup"><span data-stu-id="d8add-119">In this example, `c:\data` must exist.</span></span> <span data-ttu-id="d8add-120">La sottocartella `filestream1` tuttavia non può esistere quando si esegue l'istruzione `CREATE DATABASE` .</span><span class="sxs-lookup"><span data-stu-id="d8add-120">However, the `filestream1` subfolder cannot exist when you execute the `CREATE DATABASE` statement.</span></span> <span data-ttu-id="d8add-121">Per altre informazioni sulla sintassi, vedere [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="d8add-121">For more information about the syntax, see [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql).</span></span>  
  
 <span data-ttu-id="d8add-122">Dopo avere eseguito l'esempio precedente, nella cartella c:\Data\filestream1 sono presenti il file filestream.hdr e la cartella $FSLOG.</span><span class="sxs-lookup"><span data-stu-id="d8add-122">After you run the previous example, a filestream.hdr file and an $FSLOG folder appears in the c:\Data\filestream1 folder.</span></span> <span data-ttu-id="d8add-123">Il file filestream.hdr è un file di intestazione per il contenitore FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="d8add-123">The filestream.hdr file is a header file for the FILESTREAM container.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="d8add-124">Il file filestream.hdr è un importante file di sistema.</span><span class="sxs-lookup"><span data-stu-id="d8add-124">The filestream.hdr file is an important system file.</span></span> <span data-ttu-id="d8add-125">Tale file contiene informazioni di intestazione di FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="d8add-125">It contains FILESTREAM header information.</span></span> <span data-ttu-id="d8add-126">Non rimuoverlo o modificarlo.</span><span class="sxs-lookup"><span data-stu-id="d8add-126">Do not remove or modify this file.</span></span>  
  
 <span data-ttu-id="d8add-127">Per database esistenti, è possibile utilizzare l'istruzione [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql) per aggiungere un filegroup FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="d8add-127">For existing databases, you can use the [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql) statement to add a FILESTREAM filegroup.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8add-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d8add-128">See Also</span></span>  
 <span data-ttu-id="d8add-129">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="d8add-129">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span></span>  
 [<span data-ttu-id="d8add-130">ALTER DATABASE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d8add-130">ALTER DATABASE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql)  
  
  
