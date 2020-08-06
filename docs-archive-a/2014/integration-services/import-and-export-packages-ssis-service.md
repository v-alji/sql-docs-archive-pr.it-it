---
title: Importare ed esportare pacchetti (servizio SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- packages [Integration Services], importing
- packages [Integration Services], exporting
- importing packages
- exporting packages
ms.assetid: ef18ec11-b536-47d9-abd1-794099f43486
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b69f9d23431ed86f6b84be6857b7104cd8ba3dcc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635164"
---
# <a name="import-and-export-packages-ssis-service"></a><span data-ttu-id="f7898-102">Importare ed esportare pacchetti (servizio SSIS)</span><span class="sxs-lookup"><span data-stu-id="f7898-102">Import and Export Packages (SSIS Service)</span></span>
    
> [!IMPORTANT]  
>  <span data-ttu-id="f7898-103">In questo argomento viene illustrato il servizio [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , un servizio Windows per la gestione dei pacchetti di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f7898-103">This topic discusses the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service, a Windows service for managing [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] packages.</span></span> [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] <span data-ttu-id="f7898-104">supporta il servizio per la compatibilità con le versioni precedenti di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f7898-104">supports the service for backward compatibility with earlier releases of [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span></span> <span data-ttu-id="f7898-105">A partire da [!INCLUDE[ssSQL11](../includes/sssql11-md.md)], è possibile gestire oggetti come i pacchetti del server Integration Services.</span><span class="sxs-lookup"><span data-stu-id="f7898-105">Starting in [!INCLUDE[ssSQL11](../includes/sssql11-md.md)], you can manage objects such as packages on the Integration Services server.</span></span>  
  
 <span data-ttu-id="f7898-106">I pacchetti possono essere salvati nella tabella sysssispackages del database msdb di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] o nel file system.</span><span class="sxs-lookup"><span data-stu-id="f7898-106">Packages can be saved either in the sysssispackages table in the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] msdb database or in the file system.</span></span>  
  
 <span data-ttu-id="f7898-107">L'archivio pacchetti, ovvero l'archivio logico gestito e monitorato dal servizio [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , può includere sia il database msdb che le cartelle del file system specificate nel file di configurazione per il servizio [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f7898-107">The package store, which is the logical storage that [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service monitors and manages, can include both the msdb database and the file system folders specified in the configuration file for the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service.</span></span>  
  
 <span data-ttu-id="f7898-108">È possibile importare ed esportare pacchetti tra i tipi di archivio seguenti:</span><span class="sxs-lookup"><span data-stu-id="f7898-108">You can import and export packages between the following storage types:</span></span>  
  
-   <span data-ttu-id="f7898-109">Cartelle del file system in qualsiasi posizione del file system.</span><span class="sxs-lookup"><span data-stu-id="f7898-109">File system folders anywhere in the file system.</span></span>  
  
-   <span data-ttu-id="f7898-110">Cartelle dell'archivio pacchetti SSIS.</span><span class="sxs-lookup"><span data-stu-id="f7898-110">Folders in the SSIS Package Store.</span></span> <span data-ttu-id="f7898-111">Le due cartelle predefinite sono File system e MSDB.</span><span class="sxs-lookup"><span data-stu-id="f7898-111">The two default folders are named File System and MSDB.</span></span>  
  
-   <span data-ttu-id="f7898-112">Il database msdb di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f7898-112">The [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] msdb database.</span></span>  
  
 [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="f7898-113">consente di importare ed esportare pacchetti. Durante queste operazioni il formato e la posizione dei pacchetti vengono modificati.</span><span class="sxs-lookup"><span data-stu-id="f7898-113">gives you the ability to import and export packages, and by doing this change the storage format and location of packages.</span></span> <span data-ttu-id="f7898-114">Tramite le caratteristiche di importazione ed esportazione è possibile aggiungere pacchetti al file system, all'archivio pacchetti o al database msdb e copiarli quindi con un formato di archiviazione diverso.</span><span class="sxs-lookup"><span data-stu-id="f7898-114">Using the import and export features, you can add packages to the file system, package store, or msdb database, and copy packages from one storage format to another.</span></span> <span data-ttu-id="f7898-115">I pacchetti salvati in msdb, ad esempio, possono essere copiati nel file system e viceversa.</span><span class="sxs-lookup"><span data-stu-id="f7898-115">For example, packages saved in msdb can be copied to the file system and vice versa.</span></span>  
  
 <span data-ttu-id="f7898-116">È inoltre possibile copiare un pacchetto in un formato diverso tramite l'utilità del prompt dei comandi **dtutil** (dtutil.exe).</span><span class="sxs-lookup"><span data-stu-id="f7898-116">You can also copy a package to a different format using the **dtutil** command prompt utility (dtutil.exe).</span></span> <span data-ttu-id="f7898-117">Per altre informazioni, vedere [dtutil Utility](dtutil-utility.md).</span><span class="sxs-lookup"><span data-stu-id="f7898-117">For more information, see [dtutil Utility](dtutil-utility.md).</span></span>  
  
## <a name="to-import-or-export-a-package"></a><span data-ttu-id="f7898-118">Per importare o esportare un pacchetto</span><span class="sxs-lookup"><span data-stu-id="f7898-118">To import or export a package</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="f7898-119">In questo argomento viene illustrato il servizio [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] che fa parte di [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f7898-119">This topic discusses the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service that is part of [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)].</span></span> [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] <span data-ttu-id="f7898-120">supporta il servizio [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] per la compatibilità con le versioni precedenti di [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f7898-120">supports the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service for backward compatibility with [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)].</span></span> <span data-ttu-id="f7898-121">Per informazioni sulla gestione dei pacchetti in [!INCLUDE[ssSQL11](../includes/sssql11-md.md)], vedere [Integration Services &#40;SSIS&#41; Server](catalog/integration-services-ssis-server-and-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="f7898-121">For information about managing packages in [!INCLUDE[ssSQL11](../includes/sssql11-md.md)], see [Integration Services &#40;SSIS&#41; Server](catalog/integration-services-ssis-server-and-catalog.md).</span></span>  
  
 <span data-ttu-id="f7898-122">È possibile importare o esportare un pacchetto di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] da o nei percorsi seguenti:</span><span class="sxs-lookup"><span data-stu-id="f7898-122">You can import or export an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package from or to the following locations:</span></span>  
  
-   <span data-ttu-id="f7898-123">È possibile importare un pacchetto archiviato in un'istanza di [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], nel file system o nell'archivio pacchetti [!INCLUDE[ssIS](../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f7898-123">You can import a package that is stored in an instance of [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], in the file system, or in the [!INCLUDE[ssIS](../includes/ssis-md.md)] package store.</span></span> <span data-ttu-id="f7898-124">Il pacchetto importato viene salvato in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] o in una cartella nell'archivio pacchetti [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f7898-124">The imported package is saved to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] or to a folder in the [!INCLUDE[ssIS](../includes/ssis-md.md)] package store.</span></span>  
  
-   <span data-ttu-id="f7898-125">Un pacchetto archiviato nel file system, in un'istanza di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]o nell'archivio pacchetti [!INCLUDE[ssIS](../includes/ssis-md.md)] può essere esportato in un percorso e un formato di archiviazione diverso.</span><span class="sxs-lookup"><span data-stu-id="f7898-125">You can export a package that is stored in an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], the file system, or the [!INCLUDE[ssIS](../includes/ssis-md.md)] Package Store to a different storage format and location.</span></span>  
  
 <span data-ttu-id="f7898-126">Per l'importazione e l'esportazione di un pacchetto tra versioni diverse di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]ci sono tuttavia alcune restrizioni:</span><span class="sxs-lookup"><span data-stu-id="f7898-126">However, there are some restrictions on importing and exporting a package between different versions of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="f7898-127">In un'istanza di [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)]è possibile importare pacchetti da un'istanza di [!INCLUDE[ssVersion2005](../includes/ssversion2005-md.md)]ma non è possibile esportare pacchetti in un'istanza di [!INCLUDE[ssVersion2005](../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f7898-127">On an instance of [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)], you can import packages from an instance of [!INCLUDE[ssVersion2005](../includes/ssversion2005-md.md)], but you cannot export packages to an instance of [!INCLUDE[ssVersion2005](../includes/ssversion2005-md.md)].</span></span>  
  
-   <span data-ttu-id="f7898-128">In un'istanza di [!INCLUDE[ssVersion2005](../includes/ssversion2005-md.md)]non è possibile importare pacchetti da o esportare pacchetti in un'istanza di [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f7898-128">On an instance of [!INCLUDE[ssVersion2005](../includes/ssversion2005-md.md)], you cannot import packages from, or export packages to, an instance of [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)].</span></span>  
  
 <span data-ttu-id="f7898-129">Le procedure descritte di seguito descrivono come utilizzare [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] per importare o esportare un pacchetto.</span><span class="sxs-lookup"><span data-stu-id="f7898-129">The following procedures describe how to use [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to import or export a package.</span></span>  
  
#### <a name="to-import-a-package-by-using-sql-server-management-studio"></a><span data-ttu-id="f7898-130">Per importare un pacchetto utilizzando SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f7898-130">To import a package by Using SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="f7898-131">Fare clic sul pulsante **Start**, scegliere **Microsoft** [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] e quindi fare clic su **SQL Server Management Studio**.</span><span class="sxs-lookup"><span data-stu-id="f7898-131">Click **Start**, point to **Microsoft** [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], and then click **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="f7898-132">Nella finestra di dialogo **Connetti al server** impostare le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f7898-132">In the **Connect to Server** dialog box set the following options:</span></span>  
  
    -   <span data-ttu-id="f7898-133">Nella casella **Tipo server** selezionare **Integration Services**.</span><span class="sxs-lookup"><span data-stu-id="f7898-133">In the **Server type** box, select **Integration Services**.</span></span>  
  
    -   <span data-ttu-id="f7898-134">Nella casella **Nome server** specificare il nome di un server oppure fare clic su **\<Browse for more...>** e individuare il server da usare.</span><span class="sxs-lookup"><span data-stu-id="f7898-134">In the **Server name** box, provide a server name or click **\<Browse for more...>** and locate the server to use.</span></span>  
  
3.  <span data-ttu-id="f7898-135">Se il riquadro Esplora oggetti non è visualizzato, scegliere **Esplora oggetti** dal menu **Visualizza**.</span><span class="sxs-lookup"><span data-stu-id="f7898-135">If Object Explorer is not open, on the **View** menu, click **Object Explorer**.</span></span>  
  
4.  <span data-ttu-id="f7898-136">In Esplora oggetti espandere la cartella **Pacchetti archiviati** .</span><span class="sxs-lookup"><span data-stu-id="f7898-136">In Object Explorer, expand the **Stored Packages** folder.</span></span>  
  
5.  <span data-ttu-id="f7898-137">Espandere le sottocartelle per individuare la cartella in cui si desidera importare un pacchetto.</span><span class="sxs-lookup"><span data-stu-id="f7898-137">Expand the subfolders to locate the folder into which you want to import a package.</span></span>  
  
6.  <span data-ttu-id="f7898-138">Fare clic con il pulsante destro del mouse sulla cartella e scegliere **Importa pacchetto**,</span><span class="sxs-lookup"><span data-stu-id="f7898-138">Right-click the folder, click **Import Package**.</span></span> <span data-ttu-id="f7898-139">quindi effettuare una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f7898-139">and then do one of the following:</span></span>  
  
    -   <span data-ttu-id="f7898-140">Per importare il pacchetto da un'istanza di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], selezionare l'opzione **SQL Server** , specificare il server e selezionare la modalità di autenticazione.</span><span class="sxs-lookup"><span data-stu-id="f7898-140">To import from an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], select the **SQL Server** option, and then specify the server and select the authentication mode.</span></span> <span data-ttu-id="f7898-141">Se si seleziona l'autenticazione di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , specificare un nome utente e una password.</span><span class="sxs-lookup"><span data-stu-id="f7898-141">If you select [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication, provide a user name and a password.</span></span>  
  
         <span data-ttu-id="f7898-142">Fare clic sul pulsante Sfoglia **(...)** , selezionare il pacchetto da importare e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="f7898-142">Click the browse button **(...)**, select the package to import, and then click **OK.**</span></span>  
  
    -   <span data-ttu-id="f7898-143">Per importare il pacchetto dal file system, selezionare l'opzione **File system** .</span><span class="sxs-lookup"><span data-stu-id="f7898-143">To import from the file system, select the **File system** option.</span></span>  
  
         <span data-ttu-id="f7898-144">Fare clic sul pulsante Sfoglia **(...)** , selezionare il pacchetto da importare e quindi fare clic su **Apri**.</span><span class="sxs-lookup"><span data-stu-id="f7898-144">Click the browse button **(...)**, select the package to import, and then click **Open.**</span></span>  
  
    -   <span data-ttu-id="f7898-145">Per importare il pacchetto dall'archivio pacchetti [!INCLUDE[ssIS](../includes/ssis-md.md)] , selezionare l'opzione **Archivio pacchetti SSIS** e specificare il server.</span><span class="sxs-lookup"><span data-stu-id="f7898-145">To import from the [!INCLUDE[ssIS](../includes/ssis-md.md)] Package Store, select the **SSIS Package Store** option and specify the server.</span></span>  
  
         <span data-ttu-id="f7898-146">Fare clic sul pulsante Sfoglia **(...)** , selezionare il pacchetto da importare e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="f7898-146">Click the browse button **(...)**, select the package to import, and then click **OK.**</span></span>  
  
7.  <span data-ttu-id="f7898-147">Facoltativamente, aggiornare il nome del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="f7898-147">Optionally, update the package name.</span></span>  
  
8.  <span data-ttu-id="f7898-148">Per aggiornare il livello di protezione del pacchetto, fare clic sul pulsante Sfoglia **(...)** e specificare un livello di protezione diverso usando la finestra di dialogo **Livello di protezione pacchetto**.</span><span class="sxs-lookup"><span data-stu-id="f7898-148">To update the protection level of the package, click the browse button **(...)** and choose a different protection level by using the **Package Protection Level** dialog box.</span></span> <span data-ttu-id="f7898-149">Se l'opzione **Crittografa tutti i dati sensibili con una password** o **Crittografa tutti i dati con una password** è selezionata, digitare e confermare una password.</span><span class="sxs-lookup"><span data-stu-id="f7898-149">If the **Encrypt sensitive data with password** or the **Encrypt all data with password** option is selected, type and confirm a password.</span></span>  
  
9. <span data-ttu-id="f7898-150">Fare clic su **OK** per completare l'importazione.</span><span class="sxs-lookup"><span data-stu-id="f7898-150">Click **OK** to complete the import.</span></span>  
  
#### <a name="to-export-a-package-by-using-sql-server-management-studio"></a><span data-ttu-id="f7898-151">Per esportare un pacchetto utilizzando SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f7898-151">To export a package by Using SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="f7898-152">Fare clic sul pulsante **Start**, scegliere **Microsoft** [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] e quindi fare clic su **SQL Server Management Studio**.</span><span class="sxs-lookup"><span data-stu-id="f7898-152">Click **Start**, point to **Microsoft** [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], and then click **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="f7898-153">Nella finestra di dialogo **Connetti al server** impostare le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f7898-153">In the **Connect to Server** dialog box, set the following options:</span></span>  
  
    -   <span data-ttu-id="f7898-154">Nella casella **Tipo server** selezionare **Integration Services**.</span><span class="sxs-lookup"><span data-stu-id="f7898-154">In the **Server type** box, select **Integration Services**.</span></span>  
  
    -   <span data-ttu-id="f7898-155">Nella casella **Nome server** specificare il nome di un server oppure fare clic su **\<Browse for more...>** e individuare il server da usare.</span><span class="sxs-lookup"><span data-stu-id="f7898-155">In the **Server name** box, provide a server name or click **\<Browse for more...>** and locate the server to use.</span></span>  
  
3.  <span data-ttu-id="f7898-156">Se il riquadro Esplora oggetti non è visualizzato, scegliere **Esplora oggetti** dal menu **Visualizza**.</span><span class="sxs-lookup"><span data-stu-id="f7898-156">If Object Explorer is not open, on the **View** menu, click **Object Explorer**.</span></span>  
  
4.  <span data-ttu-id="f7898-157">In Esplora oggetti espandere la cartella **Pacchetti archiviati** .</span><span class="sxs-lookup"><span data-stu-id="f7898-157">In Object Explorer, expand the **Stored Packages** folder.</span></span>  
  
5.  <span data-ttu-id="f7898-158">Espandere le sottocartelle per individuare il pacchetto da esportare.</span><span class="sxs-lookup"><span data-stu-id="f7898-158">Expand the subfolders to locate the package you want to export.</span></span>  
  
6.  <span data-ttu-id="f7898-159">Fare clic sul pacchetto con il pulsante destro del mouse, scegliere **Esporta**e quindi eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f7898-159">Right-click the package, click **Export**, and then do one of the following:</span></span>  
  
    -   <span data-ttu-id="f7898-160">Per esportare il pacchetto in un'istanza di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], selezionare l'opzione **SQL Server** , specificare il server e selezionare la modalità di autenticazione.</span><span class="sxs-lookup"><span data-stu-id="f7898-160">To export to an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], select the **SQL Server** option, and then specify the server and select the authentication mode.</span></span> <span data-ttu-id="f7898-161">Se si seleziona l'autenticazione di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , specificare un nome utente e una password.</span><span class="sxs-lookup"><span data-stu-id="f7898-161">If you select [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication, provide a user name and a password.</span></span>  
  
         <span data-ttu-id="f7898-162">Fare clic sul pulsante Sfoglia **(...)** ed espandere la cartella **Pacchetti SSIS** per individuare la cartella in cui salvare il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="f7898-162">Click the browse button **(...)**, and expand the **SSIS Packages** folder to locate the folder to which you want to save the package.</span></span> <span data-ttu-id="f7898-163">Facoltativamente, aggiornare il nome predefinito del pacchetto e quindi scegliere **OK**.</span><span class="sxs-lookup"><span data-stu-id="f7898-163">Optionally, update the default name of the package, and then click **OK**.</span></span>  
  
    -   <span data-ttu-id="f7898-164">Per esportare il pacchetto nel file system, selezionare l'opzione **File system** .</span><span class="sxs-lookup"><span data-stu-id="f7898-164">To export to the file system, select the **File System** option.</span></span>  
  
         <span data-ttu-id="f7898-165">Fare clic sul pulsante Sfoglia **(...)** per individuare la cartella in cui esportare il pacchetto, digitare il nome del file del pacchetto e quindi scegliere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="f7898-165">Click the browse button **(...)** to locate the folder to which you want to export the package, type the name of the package file, and then click **Save.**</span></span>  
  
    -   <span data-ttu-id="f7898-166">Per eseguire l'esportazione nell'archivio pacchetti [!INCLUDE[ssIS](../includes/ssis-md.md)] , selezionare l'opzione **Archivio pacchetti SSIS** e specificare il server.</span><span class="sxs-lookup"><span data-stu-id="f7898-166">To export to the [!INCLUDE[ssIS](../includes/ssis-md.md)] package store, select the **SSIS Package Store** option, and specify the server.</span></span>  
  
         <span data-ttu-id="f7898-167">Fare clic sul pulsante Sfoglia **(...)** , espandere la cartella **Pacchetti SSIS** e selezionare la cartella in cui si vuole salvare il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="f7898-167">Click the browse button **(...)**, expand the **SSIS Packages** folder, and select the folder to which you want to save the package.</span></span> <span data-ttu-id="f7898-168">Facoltativamente, immettere un nuovo nome per il pacchetto nella casella di testo **Nome pacchetto** .</span><span class="sxs-lookup"><span data-stu-id="f7898-168">Optionally, enter a new name for the package in the **Package Name** text box.</span></span> [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
7.  <span data-ttu-id="f7898-169">Per aggiornare il livello di protezione del pacchetto, fare clic sul pulsante Sfoglia **(...)** e specificare un livello di protezione diverso usando la finestra di dialogo **Livello di protezione pacchetto**.</span><span class="sxs-lookup"><span data-stu-id="f7898-169">To update the protection level of the package, click the browse button **(...)** and choose a different protection level by using the **Package Protection Level** dialog box.</span></span> <span data-ttu-id="f7898-170">Se l'opzione **Crittografa tutti i dati sensibili con una password** o **Crittografa tutti i dati con una password** è selezionata, digitare e confermare una password.</span><span class="sxs-lookup"><span data-stu-id="f7898-170">If the **Encrypt sensitive data with password** or the **Encrypt all data with password** option is selected, type and confirm a password.</span></span>  
  
8.  <span data-ttu-id="f7898-171">Scegliere **OK** per completare l'esportazione.</span><span class="sxs-lookup"><span data-stu-id="f7898-171">Click **OK** to complete the export.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7898-172">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f7898-172">See Also</span></span>  
 [<span data-ttu-id="f7898-173">Gestione dei pacchetti &#40;servizio SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="f7898-173">Package Management &#40;SSIS Service&#41;</span></span>](service/package-management-ssis-service.md)  
  
  
