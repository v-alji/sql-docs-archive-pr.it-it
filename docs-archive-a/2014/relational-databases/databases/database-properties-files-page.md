---
title: Proprietà database (pagina File) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
f1_keywords:
- sql12.swb.databaseproperties.files.f1
ms.assetid: 3c030e51-db82-4b43-b1e5-8547ddd3de87
author: stevestein
ms.author: sstein
ms.openlocfilehash: 955a17857ce0d847fb712473dddd581a072ab83d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712020"
---
# <a name="database-properties-files-page"></a><span data-ttu-id="f2f7e-102">Proprietà database (pagina File)</span><span class="sxs-lookup"><span data-stu-id="f2f7e-102">Database Properties (Files Page)</span></span>
  <span data-ttu-id="f2f7e-103">Utilizzare questa pagina per creare un nuovo database oppure per visualizzare o modificare le proprietà del database selezionato.</span><span class="sxs-lookup"><span data-stu-id="f2f7e-103">Use this page to create a new database, or view or modify properties for the selected database.</span></span> <span data-ttu-id="f2f7e-104">Questo argomento si applica a **Proprietà database (pagina File)** per i database esistenti e a **Nuovo database (pagina Generale)** .</span><span class="sxs-lookup"><span data-stu-id="f2f7e-104">This topic applies to the **Database Properties (Files Page)** for existing databases, and to the **New Database (General Page)**.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="f2f7e-105">Elenco di elementi dell'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="f2f7e-105">UI element list</span></span>  
 <span data-ttu-id="f2f7e-106">**Nome database**</span><span class="sxs-lookup"><span data-stu-id="f2f7e-106">**Database name**</span></span>  
 <span data-ttu-id="f2f7e-107">È possibile aggiungere o visualizzare il nome del database.</span><span class="sxs-lookup"><span data-stu-id="f2f7e-107">Add or display the name of the database.</span></span>  
  
 <span data-ttu-id="f2f7e-108">**Proprietario**</span><span class="sxs-lookup"><span data-stu-id="f2f7e-108">**Owner**</span></span>  
 <span data-ttu-id="f2f7e-109">È possibile specificare il proprietario del database selezionandolo nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="f2f7e-109">Specify the owner of the database by selecting from the list.</span></span>  
  
 <span data-ttu-id="f2f7e-110">**Usa indicizzazione full-text**</span><span class="sxs-lookup"><span data-stu-id="f2f7e-110">**Use full-text indexing**</span></span>  
 <span data-ttu-id="f2f7e-111">Questa casella di controllo è selezionata e disabilitata perché l'indicizzazione full-text è sempre abilitata in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f2f7e-111">This check box is checked and disabled because full-text indexing is always enabled in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="f2f7e-112">Per altre informazioni, vedere [Ricerca full-text](../search/full-text-search.md).</span><span class="sxs-lookup"><span data-stu-id="f2f7e-112">For more information, see [Full-Text Search](../search/full-text-search.md).</span></span>  
  
 <span data-ttu-id="f2f7e-113">**File di database**</span><span class="sxs-lookup"><span data-stu-id="f2f7e-113">**Database Files**</span></span>  
 <span data-ttu-id="f2f7e-114">È possibile aggiungere, visualizzare, modificare o rimuovere file del database associato.</span><span class="sxs-lookup"><span data-stu-id="f2f7e-114">Add, view, modify, or remove database files for the associated database.</span></span> <span data-ttu-id="f2f7e-115">I file di database dispongono delle proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="f2f7e-115">Database files have the following properties:</span></span>  
  
 <span data-ttu-id="f2f7e-116">**Nome logico**</span><span class="sxs-lookup"><span data-stu-id="f2f7e-116">**Logical Name**</span></span>  
 <span data-ttu-id="f2f7e-117">È possibile immettere o modificare il nome del file.</span><span class="sxs-lookup"><span data-stu-id="f2f7e-117">Enter or modify the name of the file.</span></span>  
  
 <span data-ttu-id="f2f7e-118">**Tipo di file**</span><span class="sxs-lookup"><span data-stu-id="f2f7e-118">**File Type**</span></span>  
 <span data-ttu-id="f2f7e-119">È possibile selezionare il tipo di file nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="f2f7e-119">Select the file type from the list.</span></span> <span data-ttu-id="f2f7e-120">Il tipo di file può essere **Dati**, **Log**o **Dati FILESTREAM**.</span><span class="sxs-lookup"><span data-stu-id="f2f7e-120">The file type can be **Data**, **Log**, or **Filestream Data**.</span></span> <span data-ttu-id="f2f7e-121">Non è possibile modificare il tipo di file di un file esistente.</span><span class="sxs-lookup"><span data-stu-id="f2f7e-121">You cannot modify the file type of an existing file.</span></span>  
  
 <span data-ttu-id="f2f7e-122">Selezionare **Dati FILESTREAM** se si aggiungono file (contenitori) a un filegroup ottimizzato per la memoria.</span><span class="sxs-lookup"><span data-stu-id="f2f7e-122">Select **Filestream Data** if you are adding files (containers) to a memory-optimized filegroup.</span></span>  
  
 <span data-ttu-id="f2f7e-123">Per aggiungere file (contenitori) a un filegroup di dati FILESTREAM, FILESTREAM deve essere abilitato.</span><span class="sxs-lookup"><span data-stu-id="f2f7e-123">To add files (containers) to a Filestream data filegroup, FILESTREAM must be enabled.</span></span> <span data-ttu-id="f2f7e-124">È possibile abilitare FILESTREAM usando la finestra di dialogo [Proprietà server (pagina Avanzate)](../../database-engine/configure-windows/server-properties-advanced-page.md) .</span><span class="sxs-lookup"><span data-stu-id="f2f7e-124">You can enable FILESTREAM by using the [Server Properties (Advanced Page)](../../database-engine/configure-windows/server-properties-advanced-page.md) dialog box.</span></span>  
  
 <span data-ttu-id="f2f7e-125">**Filegroup**</span><span class="sxs-lookup"><span data-stu-id="f2f7e-125">**Filegroup**</span></span>  
 <span data-ttu-id="f2f7e-126">È possibile selezionare il filegroup per il file nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="f2f7e-126">Select the filegroup for the file from the list.</span></span> <span data-ttu-id="f2f7e-127">Per impostazione predefinita, il filegroup è PRIMARY.</span><span class="sxs-lookup"><span data-stu-id="f2f7e-127">By default, the filegroup is PRIMARY.</span></span> <span data-ttu-id="f2f7e-128">È possibile creare un nuovo filegroup selezionando **\<new filegroup>** e immettendo le informazioni sul filegroup nella finestra di dialogo **Nuovo filegroup**.</span><span class="sxs-lookup"><span data-stu-id="f2f7e-128">You can create a new filegroup by selecting **\<new filegroup>** and entering information about the filegroup in the **New Filegroup** dialog box.</span></span> <span data-ttu-id="f2f7e-129">Anche nella pagina **Filegroup** è possibile creare un nuovo filegroup.</span><span class="sxs-lookup"><span data-stu-id="f2f7e-129">A new filegroup can also be created on the **Filegroup** page.</span></span> <span data-ttu-id="f2f7e-130">Non è possibile modificare il filegroup di un file esistente.</span><span class="sxs-lookup"><span data-stu-id="f2f7e-130">You cannot modify the filegroup of an existing file.</span></span>  
  
 <span data-ttu-id="f2f7e-131">Quando si aggiungono file (contenitori) a un filegroup ottimizzato per la memoria, il campo **Filegroup** viene popolato con il nome del filegroup ottimizzato per la memoria del database.</span><span class="sxs-lookup"><span data-stu-id="f2f7e-131">When adding files (containers) to a memory-optimized filegroup, the **Filegroup** field will be populated with the name of the database's memory-optimized filegroup.</span></span>  
  
 <span data-ttu-id="f2f7e-132">**Dimensioni iniziali**</span><span class="sxs-lookup"><span data-stu-id="f2f7e-132">**Initial Size**</span></span>  
 <span data-ttu-id="f2f7e-133">È possibile immettere o modificare le dimensioni iniziali in megabyte del file.</span><span class="sxs-lookup"><span data-stu-id="f2f7e-133">Enter or modify the initial size for the file in megabytes.</span></span> <span data-ttu-id="f2f7e-134">Per impostazione predefinita, questo valore corrisponde a quello del database **model** .</span><span class="sxs-lookup"><span data-stu-id="f2f7e-134">By default, this is the value of the **model** database.</span></span>  
  
 <span data-ttu-id="f2f7e-135">Questo campo non è valido per i file FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="f2f7e-135">This field is not valid for FILESTREAM files.</span></span>  
  
 <span data-ttu-id="f2f7e-136">Per i file nei filegroup ottimizzati per la memoria, questo campo non può essere modificato.</span><span class="sxs-lookup"><span data-stu-id="f2f7e-136">For files in memory-optimized filegroups, this field cannot be modified.</span></span>  
  
 <span data-ttu-id="f2f7e-137">**Aumento automatico**</span><span class="sxs-lookup"><span data-stu-id="f2f7e-137">**Autogrowth**</span></span>  
 <span data-ttu-id="f2f7e-138">È possibile selezionare o visualizzare le proprietà dell'aumento automatico per il file.</span><span class="sxs-lookup"><span data-stu-id="f2f7e-138">Select or display the autogrowth properties for the file.</span></span> <span data-ttu-id="f2f7e-139">Queste proprietà controllano l'espansione del file al raggiungimento delle dimensioni massime.</span><span class="sxs-lookup"><span data-stu-id="f2f7e-139">These properties control how the file expands when its maximum file size is reached.</span></span> <span data-ttu-id="f2f7e-140">Per modificare i valori di aumento automatico fare clic sul pulsante di modifica accanto alle proprietà di aumento automatico relative al file desiderato e modificare i valori nella finestra di dialogo **Cambia aumento automatico dimensioni** .</span><span class="sxs-lookup"><span data-stu-id="f2f7e-140">To edit autogrowth values, click the edit button next to the autogrowth properties for the file that you want, and change the values in the **Change Autogrowth** dialog box.</span></span> <span data-ttu-id="f2f7e-141">Per impostazione predefinita, questi valori corrispondono a quelli del database **model** .</span><span class="sxs-lookup"><span data-stu-id="f2f7e-141">By default, these are the values of the **model** database.</span></span>  
  
 <span data-ttu-id="f2f7e-142">Questo campo non è valido per i file FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="f2f7e-142">This field is not valid for FILESTREAM files.</span></span>  
  
 <span data-ttu-id="f2f7e-143">Per i file nei filegroup ottimizzati per la memoria, questo campo deve essere **Senza limiti**.</span><span class="sxs-lookup"><span data-stu-id="f2f7e-143">For files in memory-optimized filegroups, this field should be **Unlimited**.</span></span>  
  
 <span data-ttu-id="f2f7e-144">**Percorso**</span><span class="sxs-lookup"><span data-stu-id="f2f7e-144">**Path**</span></span>  
 <span data-ttu-id="f2f7e-145">È possibile visualizzare il percorso del file selezionato.</span><span class="sxs-lookup"><span data-stu-id="f2f7e-145">Displays the path of the selected file.</span></span> <span data-ttu-id="f2f7e-146">Per specificare il percorso di un nuovo file fare clic sul pulsante di modifica accanto al percorso del file e passare alla cartella di destinazione.</span><span class="sxs-lookup"><span data-stu-id="f2f7e-146">To specify a path for a new file, click the edit button next to the path for the file, and navigate to the destination folder.</span></span> <span data-ttu-id="f2f7e-147">Non è possibile modificare il percorso di un file esistente.</span><span class="sxs-lookup"><span data-stu-id="f2f7e-147">You cannot modify the path of an existing file.</span></span>  
  
 <span data-ttu-id="f2f7e-148">Per i file FILESTREAM, il percorso è una cartella.</span><span class="sxs-lookup"><span data-stu-id="f2f7e-148">For FILESTREAM files, the path is a folder.</span></span> <span data-ttu-id="f2f7e-149">Il [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] creerà i file sottostanti in questa cartella.</span><span class="sxs-lookup"><span data-stu-id="f2f7e-149">The [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] will create the underlying files in this folder.</span></span>  
  
 <span data-ttu-id="f2f7e-150">**Nome file**</span><span class="sxs-lookup"><span data-stu-id="f2f7e-150">**File Name**</span></span>  
 <span data-ttu-id="f2f7e-151">È possibile visualizzare il nome del file.</span><span class="sxs-lookup"><span data-stu-id="f2f7e-151">Displays the name of the file.</span></span>  
  
 <span data-ttu-id="f2f7e-152">Questo campo non è valido per i file FILESTREAM, inclusi i file nei filegroup ottimizzati per la memoria.</span><span class="sxs-lookup"><span data-stu-id="f2f7e-152">This field is not valid for FILESTREAM files, including files in memory-optimized filegroups.</span></span>  
  
 <span data-ttu-id="f2f7e-153">**Aggiungere**</span><span class="sxs-lookup"><span data-stu-id="f2f7e-153">**Add**</span></span>  
 <span data-ttu-id="f2f7e-154">È possibile aggiungere un nuovo file al database.</span><span class="sxs-lookup"><span data-stu-id="f2f7e-154">Add a new file to the database.</span></span>  
  
 <span data-ttu-id="f2f7e-155">**Rimuovi**</span><span class="sxs-lookup"><span data-stu-id="f2f7e-155">**Remove**</span></span>  
 <span data-ttu-id="f2f7e-156">È possibile eliminare il file selezionato dal database.</span><span class="sxs-lookup"><span data-stu-id="f2f7e-156">Delete the selected file from the database.</span></span> <span data-ttu-id="f2f7e-157">È possibile eliminare solo file vuoti.</span><span class="sxs-lookup"><span data-stu-id="f2f7e-157">A file cannot be removed unless it is empty.</span></span> <span data-ttu-id="f2f7e-158">Non è possibile eliminare i file di dati e di log primari.</span><span class="sxs-lookup"><span data-stu-id="f2f7e-158">The primary data file and log file cannot be removed.</span></span>  
  
 <span data-ttu-id="f2f7e-159">Per altre informazioni sui file, vedere [Filegroup e file di database](database-files-and-filegroups.md).</span><span class="sxs-lookup"><span data-stu-id="f2f7e-159">For information about files, see [Database Files and Filegroups](database-files-and-filegroups.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2f7e-160">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f2f7e-160">See Also</span></span>  
 <span data-ttu-id="f2f7e-161">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f2f7e-161">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 [<span data-ttu-id="f2f7e-162">sys.databases &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f2f7e-162">sys.databases &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql)  
  
  
