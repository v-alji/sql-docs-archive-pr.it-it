---
title: Eseguire l'importazione/esportazione guidata SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Import and Export Wizard
- starting SQL Server Import and Export Wizard
- Import and Export Wizard
- starting Import and Export Wizard
ms.assetid: 5fc4f6d1-1f6f-444e-9aeb-827f85e1c405
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 008c541b1f1a295057b0ee7cc384982627b9689a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635127"
---
# <a name="run-the-sql-server-import-and-export-wizard"></a><span data-ttu-id="32df1-102">Esecuzione dell'Importazione/Esportazione guidata SQL Server</span><span class="sxs-lookup"><span data-stu-id="32df1-102">Run the SQL Server Import and Export Wizard</span></span>
  <span data-ttu-id="32df1-103">Importazione/Esportazione guidata [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] costituisce il metodo più semplice per la copia di dati tra origini dati e per la costruzione di pacchetti di base.</span><span class="sxs-lookup"><span data-stu-id="32df1-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Import and Export Wizard provides the simplest method of copying data between data sources and of constructing basic packages.</span></span> <span data-ttu-id="32df1-104">Per ulteriori informazioni sulla procedura guidata, vedere [SQL Server importazione/esportazione guidata](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="32df1-104">For more information about the wizard, see [SQL Server Import and Export Wizard](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span></span>  
  
 <span data-ttu-id="32df1-105">Per un video che illustra come utilizzare l'importazione/esportazione guidata di SQL Server per creare un pacchetto che esporta dati da un database SQL Server a un foglio di calcolo di Microsoft Excel, vedere [esportazione di dati di SQL Server in Excel (video SQL Server)](https://go.microsoft.com/fwlink/?LinkId=131024).</span><span class="sxs-lookup"><span data-stu-id="32df1-105">For a video that demonstrates how to use the SQL Server Import and Export Wizard to create a package that exports data from a SQL Server database to a Microsoft Excel spreadsheet, see [Exporting SQL Server Data to Excel (SQL Server Video)](https://go.microsoft.com/fwlink/?LinkId=131024).</span></span>  
  
### <a name="to-start-the-sql-server-import-and-export-wizard"></a><span data-ttu-id="32df1-106">Per avviare Importazione/Esportazione guidata SQL Server</span><span class="sxs-lookup"><span data-stu-id="32df1-106">To start the SQL Server Import and Export Wizard</span></span>  
  
-   <span data-ttu-id="32df1-107">Dal menu **Start** scegliere **tutti i programmi**,**Microsoft SQL Server** e quindi fare clic su **Importa ed Esporta dati**.</span><span class="sxs-lookup"><span data-stu-id="32df1-107">On the **Start** menu, point to **All Programs**, point to**Microsoft SQL Server** , and then click **Import and Export Data**.</span></span>  
  
     <span data-ttu-id="32df1-108">-oppure-</span><span class="sxs-lookup"><span data-stu-id="32df1-108">-or-</span></span>  
  
     <span data-ttu-id="32df1-109">In fare [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] clic con il pulsante destro del mouse sulla cartella **pacchetti SSIS** , quindi scegliere **SSISImport ed esportazione guidata**.</span><span class="sxs-lookup"><span data-stu-id="32df1-109">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], right-click the **SSIS Packages** folder, and then click **SSISImport and Export Wizard**.</span></span>  
  
     <span data-ttu-id="32df1-110">-oppure-</span><span class="sxs-lookup"><span data-stu-id="32df1-110">-or-</span></span>  
  
     <span data-ttu-id="32df1-111">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] scegliere **SSISImport ed Export Wizard**dal menu **progetto** .</span><span class="sxs-lookup"><span data-stu-id="32df1-111">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], on the **Project** menu, click **SSISImport and Export Wizard**.</span></span>  
  
     <span data-ttu-id="32df1-112">-oppure-</span><span class="sxs-lookup"><span data-stu-id="32df1-112">-or-</span></span>  
  
     <span data-ttu-id="32df1-113">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] connettersi al tipo di [!INCLUDE[ssDE](../../includes/ssde-md.md)] Server, espandere database, fare clic con il pulsante destro del mouse su un database, scegliere **attività**, quindi fare clic su **Importa dati** o **Esporta dati**.</span><span class="sxs-lookup"><span data-stu-id="32df1-113">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)] server type, expand Databases, right-click a database, point to **Tasks**, and then click **Import Data** or **Export data**.</span></span>  
  
     <span data-ttu-id="32df1-114">-oppure-</span><span class="sxs-lookup"><span data-stu-id="32df1-114">-or-</span></span>  
  
     <span data-ttu-id="32df1-115">In una finestra del prompt dei comandi eseguire DTSWizard.exe, disponibile in C:\Programmi\Microsoft SQL Server\100\DTS\Binn.</span><span class="sxs-lookup"><span data-stu-id="32df1-115">In a command prompt window, run DTSWizard.exe, located in C:\Program Files\Microsoft SQL Server\100\DTS\Binn.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="32df1-116">In un computer a 64 bit con [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] viene installata la versione a 64 bit dell'Importazione/Esportazione guidata [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (DTSWizard.exe).</span><span class="sxs-lookup"><span data-stu-id="32df1-116">On a 64-bit computer, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] installs the 64-bit version of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Import and Export Wizard (DTSWizard.exe).</span></span> <span data-ttu-id="32df1-117">Tuttavia, alcune origini dati, ad esempio Access o Excel, dispongono solo di un provider a 32 bit.</span><span class="sxs-lookup"><span data-stu-id="32df1-117">However, some data sources, such as Access or Excel, only have a 32-bit provider available.</span></span> <span data-ttu-id="32df1-118">Per utilizzare queste origini dati, potrebbe essere necessario installare ed eseguire la versione a 32 bit della procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="32df1-118">To work with these data sources, you might have to install and run the 32-bit version of the wizard.</span></span> <span data-ttu-id="32df1-119">Per installare la versione a 32 bit della procedura guidata, selezionare gli strumenti client o [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] durante l'installazione.</span><span class="sxs-lookup"><span data-stu-id="32df1-119">To install the 32-bit version of the wizard, select either Client Tools or [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] during setup.</span></span>  
  
### <a name="to-import-or-export-data-by-using-the-sql-server-import-and-export-wizard"></a><span data-ttu-id="32df1-120">Per importare o esportare i dati utilizzando l'Importazione/Esportazione guidata SQL Server</span><span class="sxs-lookup"><span data-stu-id="32df1-120">To import or export data by using the SQL Server Import and Export Wizard</span></span>  
  
1.  <span data-ttu-id="32df1-121">Avviare l'Importazione/Esportazione guidata [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="32df1-121">Start the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Import and Export Wizard.</span></span>  
  
2.  <span data-ttu-id="32df1-122">Nelle pagine della procedura guidata corrispondenti selezionare un'origine e una destinazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="32df1-122">On the corresponding wizard pages, select a data source and a data destination.</span></span>  
  
     <span data-ttu-id="32df1-123">Le origini dati disponibili includono i provider di dati [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], i provider OLE DB, i provider [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client, i provider [!INCLUDE[vstecado](../../includes/vstecado-md.md)], Microsoft Office Excel, Microsoft Office Access e l'origine file flat.</span><span class="sxs-lookup"><span data-stu-id="32df1-123">The available data sources include [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] data providers, OLE DB providers, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client providers, [!INCLUDE[vstecado](../../includes/vstecado-md.md)] providers, Microsoft Office Excel, Microsoft Office Access, and the Flat File source.</span></span> <span data-ttu-id="32df1-124">A seconda dell'origine, è necessario impostare opzioni quali la modalità di autenticazione, il nome del server, il nome del database e il formato del file.</span><span class="sxs-lookup"><span data-stu-id="32df1-124">Depending on the source, you set options such as the authentication mode, server name, database name, and file format.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="32df1-125">Il provider [!INCLUDE[msCoName](../../includes/msconame-md.md)] OLE DB per Oracle non supporta i tipi di dati Oracle BLOB, CLOB, NCLOB, BFILE e UROWID.</span><span class="sxs-lookup"><span data-stu-id="32df1-125">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] OLE DB Provider for Oracle does not support the Oracle BLOB, CLOB, NCLOB, BFILE, and UROWID data types.</span></span> <span data-ttu-id="32df1-126">Pertanto, l'origine OLE DB non è in grado di estrarre i dati da tabelle che contengono colonne con tali tipi di dati.</span><span class="sxs-lookup"><span data-stu-id="32df1-126">Therefore, the OLE DB source cannot extract data from tables that contain columns with these data types.</span></span>  
  
     <span data-ttu-id="32df1-127">Le destinazioni dei dati disponibili includono i provider di dati [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], i provider OLE DB, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client, Excel, Access e la destinazione file flat.</span><span class="sxs-lookup"><span data-stu-id="32df1-127">The available data destinations include [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] data providers, OLE DB providers, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client, Excel, Access, and the Flat File destination.</span></span>  
  
3.  <span data-ttu-id="32df1-128">Impostare le opzioni per il tipo di destinazione selezionato.</span><span class="sxs-lookup"><span data-stu-id="32df1-128">Set the options for the type of destination that you selected.</span></span>  
  
     <span data-ttu-id="32df1-129">Se la destinazione è un database di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], sarà possibile:</span><span class="sxs-lookup"><span data-stu-id="32df1-129">If the destination is a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database you can specify the following:</span></span>  
  
    -   <span data-ttu-id="32df1-130">Indicare se creare un nuovo database e impostarne le proprietà.</span><span class="sxs-lookup"><span data-stu-id="32df1-130">Indicate whether to create a new database and set the database properties.</span></span> <span data-ttu-id="32df1-131">Non è possibile configurare le proprietà seguenti, per le quali vengono utilizzati i valori predefiniti specificati:</span><span class="sxs-lookup"><span data-stu-id="32df1-131">The following properties cannot be configured and the wizard uses the specified default values:</span></span>  
  
        |<span data-ttu-id="32df1-132">Proprietà</span><span class="sxs-lookup"><span data-stu-id="32df1-132">Property</span></span>|<span data-ttu-id="32df1-133">Valore</span><span class="sxs-lookup"><span data-stu-id="32df1-133">Value</span></span>|  
        |--------------|-----------|  
        |<span data-ttu-id="32df1-134">Regole di confronto</span><span class="sxs-lookup"><span data-stu-id="32df1-134">Collation</span></span>|<span data-ttu-id="32df1-135">Latin1_General_CS_AS_KS_WS</span><span class="sxs-lookup"><span data-stu-id="32df1-135">Latin1_General_CS_AS_KS_WS</span></span>|  
        |<span data-ttu-id="32df1-136">modello di recupero</span><span class="sxs-lookup"><span data-stu-id="32df1-136">Recovery model</span></span>|<span data-ttu-id="32df1-137">Full</span><span class="sxs-lookup"><span data-stu-id="32df1-137">Full</span></span>|  
        |<span data-ttu-id="32df1-138">Usa indicizzazione full-text</span><span class="sxs-lookup"><span data-stu-id="32df1-138">Use full-text indexing</span></span>|<span data-ttu-id="32df1-139">Vero</span><span class="sxs-lookup"><span data-stu-id="32df1-139">True</span></span>|  
  
    -   <span data-ttu-id="32df1-140">Selezionare se copiare i dati da tabelle o viste oppure copiare risultati di query.</span><span class="sxs-lookup"><span data-stu-id="32df1-140">Select whether to copy data from tables or views, or to copy query results.</span></span>  
  
         <span data-ttu-id="32df1-141">Se si desidera eseguire una query sull'origine dei dati e copiare i risultati, sarà possibile creare una query Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="32df1-141">If you want to query the source data and copy the results, you can construct a Transact-SQL query.</span></span> <span data-ttu-id="32df1-142">È possibile immettere la query Transact-SQL manualmente o utilizzare una query salvata in un file.</span><span class="sxs-lookup"><span data-stu-id="32df1-142">You can enter the Transact-SQL query manually or use a query saved to a file.</span></span> <span data-ttu-id="32df1-143">Per individuare il file è possibile utilizzare la caratteristica di esplorazione disponibile nella procedura guidata, la quale apre automaticamente il file e ne incolla il contenuto nella pagina da cui è stato selezionato il file.</span><span class="sxs-lookup"><span data-stu-id="32df1-143">The wizard includes a browse feature for locating the file, and the wizard automatically opens the file and pastes its content into the wizard page when you select the file.</span></span>  
  
         <span data-ttu-id="32df1-144">Se l'origine è un provider [!INCLUDE[vstecado](../../includes/vstecado-md.md)], sarà inoltre possibile utilizzare l'opzione per la copia dei risultati della query specificando la stringa DBCommand come query.</span><span class="sxs-lookup"><span data-stu-id="32df1-144">If the source is an [!INCLUDE[vstecado](../../includes/vstecado-md.md)] provider you can also use the option to copy query results, providing the DBCommand string as the query.</span></span>  
  
         <span data-ttu-id="32df1-145">Se l'origine dati è una vista, l'Importazione/Esportazione guidata [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] la convertirà automaticamente in una tabella nella destinazione.</span><span class="sxs-lookup"><span data-stu-id="32df1-145">If the source data is a view, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Import and Export Wizard automatically converts the view to a table in the destination.</span></span>  
  
    -   <span data-ttu-id="32df1-146">Indicare se la tabella di destinazione dovrà essere eliminata e quindi ricreata e se consentire IDENTITY_INSERT.</span><span class="sxs-lookup"><span data-stu-id="32df1-146">Indicate whether the destination table is dropped and then re-created, and whether to enable identity inserts.</span></span>  
  
    -   <span data-ttu-id="32df1-147">Indicare se eliminare o aggiungere righe a una tabella esistente nella destinazione.</span><span class="sxs-lookup"><span data-stu-id="32df1-147">Indicate whether to delete rows or append rows in an existing destination table.</span></span> <span data-ttu-id="32df1-148">Se la tabella non esiste, l'Importazione/Esportazione guidata [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] la creerà automaticamente.</span><span class="sxs-lookup"><span data-stu-id="32df1-148">If the table does not exist, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Import and Export Wizard automatically creates it.</span></span>  
  
     <span data-ttu-id="32df1-149">Se la destinazione è un file flat, è possibile:</span><span class="sxs-lookup"><span data-stu-id="32df1-149">If the destination is a Flat File destination you can specify the following:</span></span>  
  
    -   <span data-ttu-id="32df1-150">Specificare il delimitatore di riga da utilizzare nel file di destinazione.</span><span class="sxs-lookup"><span data-stu-id="32df1-150">Specify the row delimiter in the destination file.</span></span>  
  
    -   <span data-ttu-id="32df1-151">Specificare il delimitatore di colonna da utilizzare nel file di destinazione.</span><span class="sxs-lookup"><span data-stu-id="32df1-151">Specify the column delimiter in the destination file.</span></span>  
  
4.  <span data-ttu-id="32df1-152">(Facoltativo) Selezionare una tabella e modificare i mapping tra le colonne di origine e destinazione oppure modificare i metadati delle colonne di destinazione:</span><span class="sxs-lookup"><span data-stu-id="32df1-152">(Optional) Select one table and change the mappings between source and destination columns, or change the metadata of destination columns:</span></span>  
  
    -   <span data-ttu-id="32df1-153">Eseguire il mapping delle colonne di origine a colonne di destinazione diverse.</span><span class="sxs-lookup"><span data-stu-id="32df1-153">Map source columns to different destination columns.</span></span>  
  
    -   <span data-ttu-id="32df1-154">Modificare il tipo di dati delle colonne di destinazione.</span><span class="sxs-lookup"><span data-stu-id="32df1-154">Change the data type in the destination column.</span></span>  
  
    -   <span data-ttu-id="32df1-155">Impostare la lunghezza delle colonne con tipi di dati character.</span><span class="sxs-lookup"><span data-stu-id="32df1-155">Set the length of columns with character data types.</span></span>  
  
    -   <span data-ttu-id="32df1-156">Impostare la precisione e la scala delle colonne con tipi di dati numeric.</span><span class="sxs-lookup"><span data-stu-id="32df1-156">Set the precision and scale of columns with numeric data types.</span></span>  
  
    -   <span data-ttu-id="32df1-157">Specificare se le colonne possono contenere valori Null.</span><span class="sxs-lookup"><span data-stu-id="32df1-157">Specify whether the column can contain null values.</span></span>  
  
5.  <span data-ttu-id="32df1-158">(Facoltativo) Selezionare più tabelle e aggiornare i metadati e le opzioni da applicarvi:</span><span class="sxs-lookup"><span data-stu-id="32df1-158">(Optional) Select multiple tables, and update the metadata and options to apply to those tables:</span></span>  
  
    -   <span data-ttu-id="32df1-159">Selezionare uno schema di destinazione esistente oppure specificare un nuovo schema a cui assegnare le tabelle.</span><span class="sxs-lookup"><span data-stu-id="32df1-159">Select an existing destination schema or provide a new schema to which to assign tables.</span></span>  
  
    -   <span data-ttu-id="32df1-160">Specificare se abilitare l'opzione IDENTITY_INSERT nelle tabelle di destinazione.</span><span class="sxs-lookup"><span data-stu-id="32df1-160">Specify whether to enable identity inserts in destination tables.</span></span>  
  
    -   <span data-ttu-id="32df1-161">Specificare se eliminare e ricreare le tabelle di destinazione.</span><span class="sxs-lookup"><span data-stu-id="32df1-161">Specify whether to drop and re-create destination tables.</span></span>  
  
    -   <span data-ttu-id="32df1-162">Specificare se troncare le tabelle di destinazione esistenti.</span><span class="sxs-lookup"><span data-stu-id="32df1-162">Specify whether to truncate existing destination tables.</span></span>  
  
6.  <span data-ttu-id="32df1-163">Salvare ed eseguire un pacchetto.</span><span class="sxs-lookup"><span data-stu-id="32df1-163">Save and run a package.</span></span>  
  
     <span data-ttu-id="32df1-164">Se la procedura guidata viene avviata da [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o dal prompt dei comandi, il pacchetto potrà essere eseguito immediatamente.</span><span class="sxs-lookup"><span data-stu-id="32df1-164">If the wizard is started from [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or the command prompt, the package can run immediately.</span></span> <span data-ttu-id="32df1-165">Facoltativamente, è possibile salvare il pacchetto nel [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database **msdb** o nel file System.</span><span class="sxs-lookup"><span data-stu-id="32df1-165">You can optionally save the package to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **msdb** database or to the file system.</span></span> <span data-ttu-id="32df1-166">Per ulteriori informazioni sul database **msdb** , vedere [Gestione pacchetti &#40;&#41;del servizio SSIS ](../service/package-management-ssis-service.md).</span><span class="sxs-lookup"><span data-stu-id="32df1-166">For more information about the **msdb** database, see [Package Management &#40;SSIS Service&#41;](../service/package-management-ssis-service.md).</span></span>  
  
     <span data-ttu-id="32df1-167">Quando si salva il pacchetto, è possibile impostarne il livello di protezione e, se per quest'ultimo si utilizza una password, specificarla.</span><span class="sxs-lookup"><span data-stu-id="32df1-167">When you save the package you can set the package protection level, and if the protection level uses a password, provide the password.</span></span> <span data-ttu-id="32df1-168">Per ulteriori informazioni sui livelli di protezione dei pacchetti, vedere [Access Control for sensitive data in Packages](../security/access-control-for-sensitive-data-in-packages.md).</span><span class="sxs-lookup"><span data-stu-id="32df1-168">For more information about package protection levels, see [Access Control for Sensitive Data in Packages](../security/access-control-for-sensitive-data-in-packages.md).</span></span>  
  
     <span data-ttu-id="32df1-169">Se la procedura guidata viene avviata da un progetto di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], non sarà possibile eseguire il pacchetto dalla procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="32df1-169">If the wizard is started from an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], you cannot run the package from the wizard.</span></span> <span data-ttu-id="32df1-170">Il pacchetto verrà invece aggiunto al progetto di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] da cui è stata avviata la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="32df1-170">Instead, the package is added to the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project from which you started the wizard.</span></span> <span data-ttu-id="32df1-171">e potrà quindi essere eseguito in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="32df1-171">You can then run the package in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="32df1-172">In [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] l'opzione per salvare il pacchetto creato con la procedura guidata non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="32df1-172">In [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)], the option to save the package created by the wizard is not available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32df1-173">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="32df1-173">See Also</span></span>  
 <span data-ttu-id="32df1-174">[Importazione/esportazione guidata SQL Server](import-and-export-data-with-the-sql-server-import-and-export-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="32df1-174">[SQL Server Import and Export Wizard](import-and-export-data-with-the-sql-server-import-and-export-wizard.md) </span></span>  
 [<span data-ttu-id="32df1-175">Creare pacchetti in SQL Server Data Tools</span><span class="sxs-lookup"><span data-stu-id="32df1-175">Create Packages in SQL Server Data Tools</span></span>](../create-packages-in-sql-server-data-tools.md)  
  
  
