---
title: Convalidare un pacchetto di applicazioni livello dati | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- data-tier application [SQL Server], validate
- data-tier application [SQL Server], compare
- validate DAC
- compare DACs
- data-tier application [SQL Server], view
- view DAC
ms.assetid: 726ffcc2-9221-424a-8477-99e3f85f03bd
author: stevestein
ms.author: sstein
ms.openlocfilehash: 078c7bfeef2ff8636243f4853c03de252c7b9289
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637376"
---
# <a name="validate-a-dac-package"></a><span data-ttu-id="a33d6-102">Convalida di un pacchetto di applicazioni livello dati</span><span class="sxs-lookup"><span data-stu-id="a33d6-102">Validate a DAC Package</span></span>
  <span data-ttu-id="a33d6-103">È consigliabile esaminare il contenuto di un pacchetto di un'applicazione livello dati prima di distribuirlo nella produzione nonché convalidare le azioni di aggiornamento prima di aggiornare un'applicazione livello dati esistente,</span><span class="sxs-lookup"><span data-stu-id="a33d6-103">It is a good practice to review the contents of a DAC package before deploying it in production, and to validate the upgrade actions before upgrading an existing DAC.</span></span> <span data-ttu-id="a33d6-104">in particolare nel caso in cui si distribuiscano pacchetti non sviluppati dalla propria organizzazione.</span><span class="sxs-lookup"><span data-stu-id="a33d6-104">This is especially true when deploying packages that were not developed in your organization.</span></span>  
  
1.  <span data-ttu-id="a33d6-105">**Prima di iniziare:**  [Prerequisiti](#Prerequisites)</span><span class="sxs-lookup"><span data-stu-id="a33d6-105">**Before you begin:**  [Prerequisites](#Prerequisites)</span></span>  
  
2.  <span data-ttu-id="a33d6-106">**Per aggiornare un'applicazione livello dati tramite la:**  [Visualizzare il contenuto di un'applicazione livello dati](#ViewDACContents), [Visualizzare modifiche al database](#ViewDBChanges), [Visualizzare azioni di aggiornamento](#ViewUpgradeActions), [Confrontare le applicazioni livello dati](#CompareDACs)</span><span class="sxs-lookup"><span data-stu-id="a33d6-106">**To upgrade a DAC, using:**  [View the Contents of a DAC](#ViewDACContents), [View Database Changes](#ViewDBChanges), [View Upgrade Actions](#ViewUpgradeActions), [Compare DACs](#CompareDACs)</span></span>  
  
##  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="a33d6-107">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="a33d6-107">Prerequisites</span></span>  
 <span data-ttu-id="a33d6-108">È consigliabile evitare di distribuire un pacchetto di applicazione livello dati proveniente da origini sconosciute o non attendibili.</span><span class="sxs-lookup"><span data-stu-id="a33d6-108">We recommend that you do not deploy a DAC package from unknown or untrusted sources.</span></span> <span data-ttu-id="a33d6-109">Tali pacchetti DAC possono contenere codice dannoso che potrebbe eseguire codice [!INCLUDE[tsql](../../includes/tsql-md.md)] indesiderato o causare errori modificando lo schema.</span><span class="sxs-lookup"><span data-stu-id="a33d6-109">Such DACs could contain malicious code that might execute unintended [!INCLUDE[tsql](../../includes/tsql-md.md)] code or cause errors by modifying the schema.</span></span> <span data-ttu-id="a33d6-110">Prima di usare un'applicazione livello dati proveniente da un'origine sconosciuta o non attendibile, distribuirla in un'istanza di test isolata del [!INCLUDE[ssDE](../../includes/ssde-md.md)], eseguire [DBCC CHECKDB &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) sul database ed esaminare anche il codice nel database, ad esempio stored procedure o altro codice definito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="a33d6-110">Before you use a DAC from an unknown or untrusted source, deploy it on an isolated test instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)], run [DBCC CHECKDB &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) on the database, and also examine the code, such as stored procedures or other user-defined code, in the database.</span></span>  
  
##  <a name="view-the-contents-of-a-dac"></a><a name="ViewDACContents"></a> <span data-ttu-id="a33d6-111">Visualizza il contenuto di un'applicazione livello dati</span><span class="sxs-lookup"><span data-stu-id="a33d6-111">View the Contents of a DAC</span></span>  
 <span data-ttu-id="a33d6-112">Sono disponibili due meccanismi per la visualizzazione del contenuto di un pacchetto di applicazione livello dati (DAC).</span><span class="sxs-lookup"><span data-stu-id="a33d6-112">There are two mechanisms for viewing the contents of a data-tier application (DAC) package.</span></span> <span data-ttu-id="a33d6-113">È possibile importare il pacchetto di applicazione livello dati in un progetto di applicazione livello dati in SQL Server Developer Tools.</span><span class="sxs-lookup"><span data-stu-id="a33d6-113">You can import the DAC package to a DAC project in SQL Server Developer Tools.</span></span> <span data-ttu-id="a33d6-114">In alternativa, è possibile decomprimere il contenuto del pacchetto in una cartella.</span><span class="sxs-lookup"><span data-stu-id="a33d6-114">You can unpack the contents of the package to a folder.</span></span>  
  
 <span data-ttu-id="a33d6-115">**Visualizzare un'applicazione livello dati in SQL Server Developer Tools**</span><span class="sxs-lookup"><span data-stu-id="a33d6-115">**View a DAC in SQL Server Developer Tools**</span></span>  
  
1.  <span data-ttu-id="a33d6-116">Aprire il menu **File**, selezionare **Nuovo** e quindi **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="a33d6-116">Open the **File** menu, select **New**, and then select **Project...**.</span></span>  
  
2.  <span data-ttu-id="a33d6-117">Selezionare il modello di progetto di **SQL Server** e specificare un **Nome**, una **Percorso**e un **Nome soluzione**.</span><span class="sxs-lookup"><span data-stu-id="a33d6-117">Select the **SQL Server** project template, and specify a **Name**, **Location**, and **Solution name**.</span></span>  
  
3.  <span data-ttu-id="a33d6-118">In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul nodo del progetto e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="a33d6-118">In **Solution Explorer**, right click the project node and select **Properties...**.</span></span>  
  
4.  <span data-ttu-id="a33d6-119">Nella scheda **Impostazioni progetto** selezionare la casella di controllo **Applicazione livello dati (file .dacpac)** nella sezione **Tipi di output** e quindi chiudere la finestra di dialogo delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="a33d6-119">On the **Project Settings** tab, in the **Output Types** section, select the **Data-tier Application (.dacpac File)** check box, and then close the properties dialog.</span></span>  
  
5.  <span data-ttu-id="a33d6-120">In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul nodo del progetto e scegliere **Importa applicazione livello dati**.</span><span class="sxs-lookup"><span data-stu-id="a33d6-120">In **Solution Explorer**, right click the project node and select **Import Data-tier Application...**.</span></span>  
  
6.  <span data-ttu-id="a33d6-121">Usare **Esplora soluzioni** per aprire tutti i file dell'applicazione livello dati, ad esempio i criteri di selezione dei server e gli script pre-distribuzione e post-distribuzione.</span><span class="sxs-lookup"><span data-stu-id="a33d6-121">Use **Solution Explorer** to open all of the files in the DAC, such as the server selection policy and the pre- and post-deployment scripts.</span></span>  
  
7.  <span data-ttu-id="a33d6-122">Utilizzare **Visualizzazione schema** per controllare tutti gli oggetti nello schema, rivedendo in particolare il codice di oggetti quali funzioni o stored procedure.</span><span class="sxs-lookup"><span data-stu-id="a33d6-122">Use the **Schema View** to review all of the objects in the schema, particularly reviewing the code in objects such as functions or stored procedures.</span></span>  
  
 <span data-ttu-id="a33d6-123">**Visualizzare un'applicazione livello dati in una cartella**</span><span class="sxs-lookup"><span data-stu-id="a33d6-123">**View a DAC in a Folder**</span></span>  
  
-   <span data-ttu-id="a33d6-124">decomprimere il pacchetto di applicazione livello dati in una cartella seguendo le istruzioni riportate in [Unpack a DAC Package](unpack-a-dac-package.md).</span><span class="sxs-lookup"><span data-stu-id="a33d6-124">Unpack the DAC package into a folder by following the instructions in [Unpack a DAC Package](unpack-a-dac-package.md).</span></span>  
  
-   <span data-ttu-id="a33d6-125">Visualizzare il contenuto degli script [!INCLUDE[tsql](../../includes/tsql-md.md)] aprendoli nell'Editor di query [!INCLUDE[ssDE](../../includes/ssde-md.md)] in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a33d6-125">View the contents of the [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts by opening them in the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span>  
  
-   <span data-ttu-id="a33d6-126">Visualizzare il contenuto dei file di testo negli strumenti quale Blocco note.</span><span class="sxs-lookup"><span data-stu-id="a33d6-126">View the contents of the text files in tools such as notepad.</span></span>  
  
##  <a name="view-database-changes"></a><a name="ViewDBChanges"></a> <span data-ttu-id="a33d6-127">Visualizza modifiche al database</span><span class="sxs-lookup"><span data-stu-id="a33d6-127">View Database Changes</span></span>  
 <span data-ttu-id="a33d6-128">Dopo che la versione corrente di un'applicazione livello dati è distribuita a produzione, è possibile che le modifiche siano state apportate direttamente al database associato che potrebbe creare conflitti con lo schema definito in una nuova versione dell'applicazione livello dati.</span><span class="sxs-lookup"><span data-stu-id="a33d6-128">After the current version of a DAC was deployed to production, changes may have been made directly to the associated database that might conflict with the schema defined in a new version of the DAC.</span></span> <span data-ttu-id="a33d6-129">Prima di aggiornare a una nuova versione dell'applicazione livello dati, controllare per vedere se tali modifiche sono state apportate al database.</span><span class="sxs-lookup"><span data-stu-id="a33d6-129">Before upgrading to a new version of the DAC, check to see if such changes have been made to the database.</span></span>  
  
 <span data-ttu-id="a33d6-130">**Visualizzare modifiche al Database tramite una procedura guidata**</span><span class="sxs-lookup"><span data-stu-id="a33d6-130">**View Database Changes by Using a Wizard**</span></span>  
  
1.  <span data-ttu-id="a33d6-131">Eseguire la procedura guidata **Aggiorna applicazione livello dati** , specificare l'applicazione livello dati attualmente distribuita e il pacchetto di applicazione livello dati contenente la nuova versione dell'applicazione stessa.</span><span class="sxs-lookup"><span data-stu-id="a33d6-131">Run the **Upgrade Data-tier Application** wizard, specifying the currently deployed DAC and the DAC package containing the new version of the DAC.</span></span>  
  
2.  <span data-ttu-id="a33d6-132">Nella pagina **Rileva modifiche** , esaminare il report delle modifiche apportate al database.</span><span class="sxs-lookup"><span data-stu-id="a33d6-132">On the **Detect Change** page, review the report of the changes that have been made to the database.</span></span>  
  
3.  <span data-ttu-id="a33d6-133">Selezionare **Annulla** se non si desidera proseguire con l'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="a33d6-133">Select **Cancel** if you do not want to continue with the upgrade.</span></span>  
  
4.  <span data-ttu-id="a33d6-134">Per altre informazioni sull'uso della procedura guidata, vedere [Aggiornare un'applicazione livello dati](upgrade-a-data-tier-application.md).</span><span class="sxs-lookup"><span data-stu-id="a33d6-134">For more information on using the wizard, see [Upgrade a Data-tier Application](upgrade-a-data-tier-application.md).</span></span>  
  
### <a name="view-database-changes-by-using-powershell"></a><span data-ttu-id="a33d6-135">Visualizzare modifiche al database tramite PowerShell</span><span class="sxs-lookup"><span data-stu-id="a33d6-135">View Database Changes by Using PowerShell</span></span>
  
1.  <span data-ttu-id="a33d6-136">Creare un oggetto server SMO e impostarlo sull'istanza contenente l'applicazione livello dati da visualizzare.</span><span class="sxs-lookup"><span data-stu-id="a33d6-136">Create a SMO Server object and set it to the instance that contains the DAC to be viewed.</span></span>  
  
2.  <span data-ttu-id="a33d6-137">Aprire un oggetto `ServerConnection` e collegarlo alla stessa istanza.</span><span class="sxs-lookup"><span data-stu-id="a33d6-137">Open a `ServerConnection` object and connect to the same instance.</span></span>  
  
3.  <span data-ttu-id="a33d6-138">Specificare il nome dell'applicazione livello dati in una variabile.</span><span class="sxs-lookup"><span data-stu-id="a33d6-138">Specify the DAC name in a variable.</span></span>  
  
4.  <span data-ttu-id="a33d6-139">Utilizzare il metodo `GetDatabaseChanges()` per recuperare un oggetto `ChangeResults` e reindirizzare l'oggetto a un file di testo per generare un report semplice degli oggetti nuovi, eliminati e modificati.</span><span class="sxs-lookup"><span data-stu-id="a33d6-139">Use the `GetDatabaseChanges()` method to retrieve a `ChangeResults` object, and pipe the object to a text file to generate a simple report of new, deleted, and changed objects.</span></span>  
  
### <a name="view-database-changes-example-powershell"></a><span data-ttu-id="a33d6-140">Visualizzare esempio di modifiche al database (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="a33d6-140">View Database Changes Example (PowerShell)</span></span>
  
 <span data-ttu-id="a33d6-141">Nell'esempio seguente vengono segnalate eventuali modifiche apportate al database in un'applicazione livello dati distribuita denominata MyApplicaiton.</span><span class="sxs-lookup"><span data-stu-id="a33d6-141">The following example reports any database changes that have been made in a deployed DAC named MyApplicaiton.</span></span>  
  
```powershell
## Set a SMO Server object to the default instance on the local computer.  
CD SQLSERVER:\SQL\localhost\DEFAULT  
$srv = Get-Item .  
  
## Open a Common.ServerConnection to the same instance.  
$serverconnection = New-Object Microsoft.SqlServer.Management.Common.ServerConnection($srv.ConnectionContext.SqlConnectionObject)  
$serverconnection.Connect()  
$dacstore = New-Object Microsoft.SqlServer.Management.Dac.DacStore($serverconnection)  
  
## Specify the DAC instance name.  
$dacName  = "MyApplication"  
  
## Generate the change list and save to file.  
$dacChanges = $dacstore.GetDatabaseChanges($dacName) | Out-File -Filepath C:\DACScripts\MyApplicationChanges.txt  
```  
  
##  <a name="view-upgrade-actions"></a><a name="ViewUpgradeActions"></a> <span data-ttu-id="a33d6-142">Visualizza azioni di aggiornamento</span><span class="sxs-lookup"><span data-stu-id="a33d6-142">View Upgrade Actions</span></span>  
 <span data-ttu-id="a33d6-143">Prima di utilizzare una nuova versione di un pacchetto di applicazione livello dati per aggiornare un'applicazione livello dati distribuita da un pacchetto di applicazione livello dati precedente, è possibile generare un report in cui sono contenute le istruzioni [!INCLUDE[tsql](../../includes/tsql-md.md)] che verranno eseguite durante l'aggiornamento, quindi controllare le istruzioni.</span><span class="sxs-lookup"><span data-stu-id="a33d6-143">Before using a new version of a DAC package to upgrade a DAC that was deployed from an earlier DAC package, you can generate a report that contains the [!INCLUDE[tsql](../../includes/tsql-md.md)] statements that will be run during the upgrade, and then review the statements.</span></span>  
  
 <span data-ttu-id="a33d6-144">**Segnalare azioni di aggiornamento tramite una procedura guidata**</span><span class="sxs-lookup"><span data-stu-id="a33d6-144">**Report Upgrade Actions by Using a Wizard**</span></span>  
  
1.  <span data-ttu-id="a33d6-145">Eseguire la procedura guidata **Aggiorna applicazione livello dati** , specificare l'applicazione livello dati attualmente distribuita e il pacchetto di applicazione livello dati contenente la nuova versione dell'applicazione stessa.</span><span class="sxs-lookup"><span data-stu-id="a33d6-145">Run the **Upgrade Data-tier Application** wizard, specifying the currently deployed DAC and the DAC package containing the new version of the DAC.</span></span>  
  
2.  <span data-ttu-id="a33d6-146">Nella pagina **Riepilogo** , esaminare il report delle azioni di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="a33d6-146">On the **Summary** page, review the report of the upgrade actions.</span></span>  
  
3.  <span data-ttu-id="a33d6-147">Selezionare **Annulla** se non si desidera proseguire con l'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="a33d6-147">Select **Cancel** if you do not want to continue with the upgrade.</span></span>  
  
4.  <span data-ttu-id="a33d6-148">Per altre informazioni sull'uso della procedura guidata, vedere [Aggiornare un'applicazione livello dati](upgrade-a-data-tier-application.md).</span><span class="sxs-lookup"><span data-stu-id="a33d6-148">For more information on using the wizard, see [Upgrade a Data-tier Application](upgrade-a-data-tier-application.md).</span></span>  
  
 <span data-ttu-id="a33d6-149">**Segnalare azioni di aggiornamento tramite PowerShell**</span><span class="sxs-lookup"><span data-stu-id="a33d6-149">**Report Upgrade Actions by Using PowerShell**</span></span>  
  
1.  <span data-ttu-id="a33d6-150">Creare un oggetto server SMO e impostarlo sull'istanza contenente l'applicazione livello dati distribuita.</span><span class="sxs-lookup"><span data-stu-id="a33d6-150">Create a SMO Server object and set it to the instance that contains the deployed DAC.</span></span>  
  
2.  <span data-ttu-id="a33d6-151">Aprire un oggetto `ServerConnection` e collegarlo alla stessa istanza.</span><span class="sxs-lookup"><span data-stu-id="a33d6-151">Open a `ServerConnection` object and connect to the same instance.</span></span>  
  
3.  <span data-ttu-id="a33d6-152">Usare `System.IO.File` per caricare il file del pacchetto di applicazione livello dati.</span><span class="sxs-lookup"><span data-stu-id="a33d6-152">Use `System.IO.File` to load the DAC package file.</span></span>  
  
4.  <span data-ttu-id="a33d6-153">Specificare il nome dell'applicazione livello dati in una variabile.</span><span class="sxs-lookup"><span data-stu-id="a33d6-153">Specify the DAC name in a variable.</span></span>  
  
5.  <span data-ttu-id="a33d6-154">Utilizzare il metodo `GetIncrementalUpgradeScript()` per ottenere un elenco delle istruzioni Transact-SQL che verrebbero eseguite durante un aggiornamento e reindirizzare l'elenco a un file di testo.</span><span class="sxs-lookup"><span data-stu-id="a33d6-154">Use the `GetIncrementalUpgradeScript()` method to get a list of the Transact-SQL statements an upgrade would run, and pipe the list to a text file.</span></span>  
  
6.  <span data-ttu-id="a33d6-155">Chiudere il flusso di file usato per leggere il file del pacchetto di applicazione livello dati.</span><span class="sxs-lookup"><span data-stu-id="a33d6-155">Close the file stream used to read the DAC package file.</span></span>  
  
### <a name="view-upgrade-actions-example-powershell"></a><span data-ttu-id="a33d6-156">Visualizzare esempio di azioni di aggiornamento (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="a33d6-156">View Upgrade Actions Example (PowerShell)</span></span>
  
 <span data-ttu-id="a33d6-157">Nell'esempio seguente vengono segnalate le istruzioni Transact-SQL che sarebbero eseguite per l'aggiornamento di una'applicazione livello dati con nome MyApplicaiton allo schema definito in un file MyApplicationVNext.dacpac.</span><span class="sxs-lookup"><span data-stu-id="a33d6-157">The following example reports the Transact-SQL statements that would be run to upgrading a DAC named MyApplicaiton to the schema defined in a MyApplicationVNext.dacpac file.</span></span>  
  
```powershell
## Set a SMO Server object to the default instance on the local computer.  
CD SQLSERVER:\SQL\localhost\DEFAULT  
$srv = Get-Item .  
  
## Open a Common.ServerConnection to the same instance.  
$serverconnection = New-Object Microsoft.SqlServer.Management.Common.ServerConnection($srv.ConnectionContext.SqlConnectionObject)  
$serverconnection.Connect()  
$dacstore = New-Object Microsoft.SqlServer.Management.Dac.DacStore($serverconnection)  
  
## Load the DAC package file.  
$dacpacPath = "C:\MyDACs\MyApplicationVNext.dacpac"  
$fileStream = [System.IO.File]::Open($dacpacPath,[System.IO.FileMode]::OpenOrCreate)  
$dacType = [Microsoft.SqlServer.Management.Dac.DacType]::Load($fileStream)  
  
## Specify the DAC instance name.  
$dacName  = "MyApplication"  
  
## Generate the upgrade script and save to file.  
$dacstore.GetIncrementalUpgradeScript($dacName, $dacType) | Out-File -Filepath C:\DACScripts\MyApplicationUpgrade.sql  
  
## Close the filestream to the new DAC package.  
$fileStream.Close()  
```  
  
##  <a name="compare-dacs"></a><a name="CompareDACs"></a><span data-ttu-id="a33d6-158">Confrontare DAC</span><span class="sxs-lookup"><span data-stu-id="a33d6-158">Compare DACs</span></span>  
 <span data-ttu-id="a33d6-159">Prima di aggiornare un'applicazione del livello dati, è consigliabile controllare le differenze nel database e negli oggetti a livello di istanza tra il pacchetto di applicazioni livello dati corrente e quello nuovo.</span><span class="sxs-lookup"><span data-stu-id="a33d6-159">Before upgrading a DAC, it is a good practice to review the differences in the database and instance-level objects between the current and new DACs.</span></span> <span data-ttu-id="a33d6-160">Se non si dispone di una copia del pacchetto di applicazione livello dati corrente, è possibile estrarre un pacchetto dal database corrente.</span><span class="sxs-lookup"><span data-stu-id="a33d6-160">If you do not have a copy of the package for the current DAC, you can extract a package from the current database.</span></span>  
  
 <span data-ttu-id="a33d6-161">Se si importano entrambi i pacchetti di applicazione livello dati nei progetti di applicazione livello dati in SQL Server Developer Tools, è possibile utilizzare lo strumento di Confronto schema per analizzare le differenze tra i due pacchetti di applicazioni livello dati.</span><span class="sxs-lookup"><span data-stu-id="a33d6-161">If you import both DAC packages into DAC projects in SQL Server Developer Tools, you can use the Schema Compare tool to analyze the differences between the two DACs.</span></span>  
  
 <span data-ttu-id="a33d6-162">In alternativa, decomprimere le applicazioni livello dati in cartelle separate.</span><span class="sxs-lookup"><span data-stu-id="a33d6-162">Alternatively, unpack the DACs into separate folders.</span></span> <span data-ttu-id="a33d6-163">È possibile quindi utilizzare uno strumento delle differenze, quale l'utilità WinDiff, per analizzare le differenze.</span><span class="sxs-lookup"><span data-stu-id="a33d6-163">You can then use a difference tool, such as the WinDiff utility, to analyze the differences.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a33d6-164">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a33d6-164">See Also</span></span>  
 <span data-ttu-id="a33d6-165">[Applicazioni livello dati](data-tier-applications.md) </span><span class="sxs-lookup"><span data-stu-id="a33d6-165">[Data-tier Applications](data-tier-applications.md) </span></span>  
 <span data-ttu-id="a33d6-166">[Distribuire un'applicazione livello dati](deploy-a-data-tier-application.md) </span><span class="sxs-lookup"><span data-stu-id="a33d6-166">[Deploy a Data-tier Application](deploy-a-data-tier-application.md) </span></span>  
 [<span data-ttu-id="a33d6-167">Aggiornare un'applicazione livello dati</span><span class="sxs-lookup"><span data-stu-id="a33d6-167">Upgrade a Data-tier Application</span></span>](upgrade-a-data-tier-application.md)  
