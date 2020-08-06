---
title: Proprietà database (pagina Filegroup) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
f1_keywords:
- sql12.swb.databaseproperties.filegroups.f1
ms.assetid: 8d06e859-73dd-4019-b6e8-99c5c5297697
author: stevestein
ms.author: sstein
ms.openlocfilehash: d0546a17491ed5d3b36890a605c5faa922c24fe6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627806"
---
# <a name="database-properties-filegroups-page"></a><span data-ttu-id="b788c-102">Proprietà database (pagina Filegroup)</span><span class="sxs-lookup"><span data-stu-id="b788c-102">Database Properties (Filegroups Page)</span></span>
  <span data-ttu-id="b788c-103">Utilizzare questa pagina per visualizzare i filegroup o aggiungere un nuovo filegroup al database selezionato.</span><span class="sxs-lookup"><span data-stu-id="b788c-103">Use this page to view the filegroups or add a new filegroup to the selected database.</span></span> <span data-ttu-id="b788c-104">I tipi di filegroup sono suddivisi in filegroup di *righe*, in filegroup di dati FILESTREAM e in filegroup ottimizzati per la memoria.</span><span class="sxs-lookup"><span data-stu-id="b788c-104">Filegroup types are separated into *row* filegroups, FILESTREAM data, and memory-optimized filegroups.</span></span>  
  
 <span data-ttu-id="b788c-105">I filegroup di righe contengono file di dati e di log standard.</span><span class="sxs-lookup"><span data-stu-id="b788c-105">Row filegroups contain regular data and log files.</span></span> <span data-ttu-id="b788c-106">I filegroup di dati FILESTREAM contengono file di dati FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="b788c-106">FILESTREAM data filegroups contain FILESTREAM data files.</span></span> <span data-ttu-id="b788c-107">Questi file di dati archiviano informazioni sulle modalità con cui i dati BLOB (binary large object) vengono archiviati nel file system quando si utilizza l'archiviazione FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="b788c-107">These data files store information about how binary large object (BLOB) data is stored on the file system when you are using FILESTREAM storage.</span></span> <span data-ttu-id="b788c-108">Le opzioni sono le stesse per entrambi tipi di filegroup.</span><span class="sxs-lookup"><span data-stu-id="b788c-108">The options are the same for both types of filegroups.</span></span>  
  
 <span data-ttu-id="b788c-109">Se FILESTREAM non è stato abilitato, la sezione **Filestream** non sarà disponibile.</span><span class="sxs-lookup"><span data-stu-id="b788c-109">If FILESTREAM is not enabled, the **Filestream** section will not be available.</span></span> <span data-ttu-id="b788c-110">È possibile abilitare l'archiviazione FILESTREAM usando la finestra di dialogo [Proprietà server (pagina Avanzate)](../../database-engine/configure-windows/server-properties-advanced-page.md).</span><span class="sxs-lookup"><span data-stu-id="b788c-110">You can enable FILESTREAM storage by using [Server Properties (Advanced Page)](../../database-engine/configure-windows/server-properties-advanced-page.md).</span></span>  
  
 <span data-ttu-id="b788c-111">Per altre informazioni sul modo in cui [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usa i filegroup righe, vedere [Filegroup e file di database](database-files-and-filegroups.md).</span><span class="sxs-lookup"><span data-stu-id="b788c-111">For information about how [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] uses row filegroups, see [Database Files and Filegroups](database-files-and-filegroups.md).</span></span> <span data-ttu-id="b788c-112">Per altre informazioni sui filegroup e i dati FILESTREAM, vedere [FILESTREAM &#40;SQL Server&#41;](../blob/filestream-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="b788c-112">For more information about FILESTREAM data and filegroups, see [FILESTREAM &#40;SQL Server&#41;](../blob/filestream-sql-server.md).</span></span>  
  
 <span data-ttu-id="b788c-113">I filegroup ottimizzati per la memoria sono necessari per consentire ai database di contenere una o più tabelle ottimizzate per la memoria.</span><span class="sxs-lookup"><span data-stu-id="b788c-113">Memory-optimized file groups are required for a database to contain one or more memory-optimized tables.</span></span>  
  
## <a name="row-and-filestream-data-filegroup-options"></a><span data-ttu-id="b788c-114">Opzioni di filegroup di righe e di dati FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="b788c-114">Row and FILESTREAM Data Filegroup Options</span></span>  
 <span data-ttu-id="b788c-115">**Nome**</span><span class="sxs-lookup"><span data-stu-id="b788c-115">**Name**</span></span>  
 <span data-ttu-id="b788c-116">Consente di immettere il nome del filegroup.</span><span class="sxs-lookup"><span data-stu-id="b788c-116">Enter the name of the filegroup.</span></span>  
  
 <span data-ttu-id="b788c-117">**File**</span><span class="sxs-lookup"><span data-stu-id="b788c-117">**Files**</span></span>  
 <span data-ttu-id="b788c-118">Visualizza il numero dei file contenuti nel filegroup.</span><span class="sxs-lookup"><span data-stu-id="b788c-118">Displays the count of files in the filegroup.</span></span>  
  
 <span data-ttu-id="b788c-119">**Sola lettura**</span><span class="sxs-lookup"><span data-stu-id="b788c-119">**Read-only**</span></span>  
 <span data-ttu-id="b788c-120">Consente di impostare il filegroup sullo stato di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="b788c-120">Select to set the filegroup to a read-only status.</span></span>  
  
 <span data-ttu-id="b788c-121">**Default**</span><span class="sxs-lookup"><span data-stu-id="b788c-121">**Default**</span></span>  
 <span data-ttu-id="b788c-122">Consente di impostare il filegroup come filegroup predefinito.</span><span class="sxs-lookup"><span data-stu-id="b788c-122">Select to make this filegroup the default filegroup.</span></span> <span data-ttu-id="b788c-123">È possibile avere un filegroup predefinito per le righe e un filegroup predefinito per i dati FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="b788c-123">You can have one default filegroup for rows and one default filegroup for FILESTREAM data.</span></span>  
  
 <span data-ttu-id="b788c-124">**Aggiungere**</span><span class="sxs-lookup"><span data-stu-id="b788c-124">**Add**</span></span>  
 <span data-ttu-id="b788c-125">Consente di aggiungere una nuova riga vuota alla griglia in cui sono elencati i filegroup per il database.</span><span class="sxs-lookup"><span data-stu-id="b788c-125">Adds a new blank row to the grid listing filegroups for the database.</span></span>  
  
 <span data-ttu-id="b788c-126">**Rimuovi**</span><span class="sxs-lookup"><span data-stu-id="b788c-126">**Remove**</span></span>  
 <span data-ttu-id="b788c-127">Consente di rimuovere il filegroup selezionato dalla griglia.</span><span class="sxs-lookup"><span data-stu-id="b788c-127">Removes the selected filegroup row from the grid.</span></span>  
  
## <a name="memory-optimized-data-filegroup-options"></a><span data-ttu-id="b788c-128">Opzioni di filegroup di dati con ottimizzazione per la memoria</span><span class="sxs-lookup"><span data-stu-id="b788c-128">Memory-Optimized Data Filegroup Options</span></span>  
 <span data-ttu-id="b788c-129">**Nome**</span><span class="sxs-lookup"><span data-stu-id="b788c-129">**Name**</span></span>  
 <span data-ttu-id="b788c-130">Consente di immettere il nome del filegroup ottimizzato per la memoria.</span><span class="sxs-lookup"><span data-stu-id="b788c-130">Enter the name of the memory-optimized filegroup.</span></span>  
  
 <span data-ttu-id="b788c-131">**File FILESTREAM**</span><span class="sxs-lookup"><span data-stu-id="b788c-131">**Filestream Files**</span></span>  
 <span data-ttu-id="b788c-132">Visualizza il numero di file (contenitori) nel filegroup di dati ottimizzato per la memoria.</span><span class="sxs-lookup"><span data-stu-id="b788c-132">Displays the number of files (containers) in the memory-optimized data filegroup.</span></span> <span data-ttu-id="b788c-133">È possibile aggiungere contenitori nella pagina **File** .</span><span class="sxs-lookup"><span data-stu-id="b788c-133">You can add containers in the **Files** page.</span></span>  
  
 <span data-ttu-id="b788c-134">**Aggiungere**</span><span class="sxs-lookup"><span data-stu-id="b788c-134">**Add**</span></span>  
 <span data-ttu-id="b788c-135">Consente di aggiungere una nuova riga vuota alla griglia in cui sono elencati i filegroup per il database.</span><span class="sxs-lookup"><span data-stu-id="b788c-135">Adds a new blank row to the grid listing filegroups for the database.</span></span>  
  
 <span data-ttu-id="b788c-136">**Rimuovi**</span><span class="sxs-lookup"><span data-stu-id="b788c-136">**Remove**</span></span>  
 <span data-ttu-id="b788c-137">Consente di rimuovere il filegroup selezionato dalla griglia.</span><span class="sxs-lookup"><span data-stu-id="b788c-137">Removes the selected filegroup row from the grid.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b788c-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b788c-138">See Also</span></span>  
 <span data-ttu-id="b788c-139">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b788c-139">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 [<span data-ttu-id="b788c-140">sys.databases &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b788c-140">sys.databases &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql)  
  
  
