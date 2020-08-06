---
title: Riferimento all'interfaccia utente Utilità di esecuzione pacchetti (DtExecUI) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.dtexecui.general.f1
- sql12.dts.dtexecui.executionoptions.f1
- sql12.dts.dtexecui.configuration.f1
- sql12.dts.dtexecui.setvalues.f1
- sql12.dts.dtexecui.commandline.f1
- sql12.dts.dtexecui.commandfiles.f1
- sql12.dts.dtexecui.verification.f1
- sql12.dts.dtexecui.datasources.f1
- sql12.dts.dtexecui.reporting.f1
- sql12.dts.dtexecui.logging.f1
helpviewer_keywords:
- DTExecUI utility
ms.assetid: 3d71df39-126b-4c8e-bd77-128bbd5b0887
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 13601983a4ab841a2b64ff8e4fc722fcf5ae496c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629904"
---
# <a name="execute-package-utility-dtexecui-ui-reference"></a><span data-ttu-id="b93df-102">Riferimento all'interfaccia utente dell'utilità di esecuzione pacchetti (DtExecUI)</span><span class="sxs-lookup"><span data-stu-id="b93df-102">Execute Package Utility (DtExecUI) UI Reference</span></span>
  <span data-ttu-id="b93df-103">Utilizzare l' **Utilità di esecuzione pacchetti** per eseguire i pacchetti di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b93df-103">Use the **Execute Package Utility** to run [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages.</span></span> <span data-ttu-id="b93df-104">L'utilità esegue i pacchetti archiviati in una delle tre posizioni seguenti: database di [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], archivio pacchetti [!INCLUDE[ssIS](../../includes/ssis-md.md)] e file system.</span><span class="sxs-lookup"><span data-stu-id="b93df-104">The utility runs packages that are stored in one of three locations: [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database, the [!INCLUDE[ssIS](../../includes/ssis-md.md)] Package Store, and the file system.</span></span> <span data-ttu-id="b93df-105">Questa interfaccia utente, che può essere aperta da [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o digitando `dtexecui` al prompt dei comandi, rappresenta un'alternativa all'esecuzione di pacchetti usando lo strumento del prompt dei comandi **dtexec** .</span><span class="sxs-lookup"><span data-stu-id="b93df-105">This user interface, which can be opened from [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or by typing `dtexecui` at a command prompt, is an alternative to running packages by using the **DTExec** command prompt tool.</span></span>  
  
 <span data-ttu-id="b93df-106">I pacchetti vengono eseguiti nello stesso processo dell'utilità **dtexecui.exe** .</span><span class="sxs-lookup"><span data-stu-id="b93df-106">Packages execute in the same process as the **dtexecui.exe** utility.</span></span> <span data-ttu-id="b93df-107">Questa utilità è uno strumento a 32 bit, quindi i pacchetti eseguiti usando **dtexecui.exe** in un ambiente a 64 bit vengono eseguiti in Windows on Win32 (WOW).</span><span class="sxs-lookup"><span data-stu-id="b93df-107">Because this utility is a 32-bit tool, packages run by using **dtexecui.exe** in a 64-bit environment run in Windows on Win32 (WOW).</span></span> <span data-ttu-id="b93df-108">Quando si sviluppano e si verificano i comandi usando l'utilità dtexecui.exe in un computer a 64 bit, è consigliabile eseguire la verifica in modalità a 64 bit usando la versione a 64 bit di **dtexec.exe** prima della distribuzione o della pianificazione dei comandi su un server di produzione.</span><span class="sxs-lookup"><span data-stu-id="b93df-108">When developing and testing commands by using the dtexecui.exe utility on a 64-bit computer, you should test the commands in 64-bit mode by using the 64-bit version of **dtexec.exe** before deploying or scheduling the commands on a production server.</span></span>  
  
 <span data-ttu-id="b93df-109">L' **Utilità di esecuzione pacchetti** è un'interfaccia utente grafica per lo strumento del prompt dei comandi **DTExec** .</span><span class="sxs-lookup"><span data-stu-id="b93df-109">The **Execute Package Utility** is a graphical user interface for the **DTExec** command prompt tool.</span></span> <span data-ttu-id="b93df-110">L'interfaccia utente semplifica la configurazione delle opzioni e assembla automaticamente la riga di comando che viene passata allo strumento del prompt dei comandi **DTExec** quando il pacchetto viene eseguito dalle opzioni specificate.</span><span class="sxs-lookup"><span data-stu-id="b93df-110">The user interface makes it easy to configure options and it automatically assembles the command line that is passed to the **DTExec** command prompt tool when you run the package from the specified options.</span></span>  
  
 <span data-ttu-id="b93df-111">L' **Utilità di esecuzione pacchetti** può essere anche usata per assemblare le righe di comando usate dall'utente durante l'esecuzione diretta di **DTExec** .</span><span class="sxs-lookup"><span data-stu-id="b93df-111">The **Execute Package Utility** can also be used to assemble command lines that you use when running **DTExec** directly.</span></span>  
  
### <a name="to-open-execute-package-utility-in-sql-server-management-studio"></a><span data-ttu-id="b93df-112">Per aprire l'Utilità di esecuzione pacchetti in SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b93df-112">To open Execute Package Utility in SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="b93df-113">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]scegliere **Esplora oggetti** dal menu **Visualizza**.</span><span class="sxs-lookup"><span data-stu-id="b93df-113">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], on the **View** menu, click **Object Explorer**.</span></span>  
  
2.  <span data-ttu-id="b93df-114">In Esplora oggetti fare clic su **Connetti**, quindi su **Integration Services**.</span><span class="sxs-lookup"><span data-stu-id="b93df-114">In Object Explorer, click **Connect**, and then click **Integration Services**.</span></span>  
  
3.  <span data-ttu-id="b93df-115">Nella finestra di dialogo **Connetti al server** immettere il nome del server nell'elenco **Nome server** e quindi fare clic su **Connetti**.</span><span class="sxs-lookup"><span data-stu-id="b93df-115">In the **Connect to Server** dialog box, enter the server name in the **Server name** list, and then click **Connect**.</span></span>  
  
4.  <span data-ttu-id="b93df-116">Espandere la cartella **Pacchetti archiviati**e le relative sottocartelle, fare clic con il pulsante destro del mouse sul pacchetto da eseguire e quindi scegliere **Esegui pacchetto**.</span><span class="sxs-lookup"><span data-stu-id="b93df-116">Expand the **Stored Package**s folder and subfolders, right-click the package you want to run, and then click **Run Package**.</span></span>  
  
### <a name="to-open-the-execute-package-utility-at-the-command-prompt"></a><span data-ttu-id="b93df-117">Per aprire l'Utilità di esecuzione pacchetti dal prompt dei comandi</span><span class="sxs-lookup"><span data-stu-id="b93df-117">To open the Execute Package Utility at the Command Prompt</span></span>  
  
-   <span data-ttu-id="b93df-118">In una finestra del prompt dei comandi eseguire `dtexecui`.</span><span class="sxs-lookup"><span data-stu-id="b93df-118">In a command prompt window, run `dtexecui`.</span></span>  
  
 <span data-ttu-id="b93df-119">Nelle sezioni seguenti vengono descritte le pagine della finestra di dialogo **Utilità di esecuzione pacchetti** .</span><span class="sxs-lookup"><span data-stu-id="b93df-119">The following sections describe pages of the **Execute Package Utility** dialog box.</span></span>  
  
## <a name="general-page"></a><span data-ttu-id="b93df-120">Pagina Generale</span><span class="sxs-lookup"><span data-stu-id="b93df-120">General Page</span></span>  
 <span data-ttu-id="b93df-121">Utilizzare la pagina **Generale** della finestra di dialogo **Utilità di esecuzione pacchetti** per specificare il nome e il percorso di un pacchetto.</span><span class="sxs-lookup"><span data-stu-id="b93df-121">Use the **General** page of the **Execute Package Utility** dialog box to specify a package name and location.</span></span>  
  
 <span data-ttu-id="b93df-122">L'utilità di esecuzione pacchetti (dtexecui.exe) esegue sempre un pacchetto nel computer locale anche se il pacchetto si trova su un server remoto.</span><span class="sxs-lookup"><span data-stu-id="b93df-122">The Execute Package utility (dtexecui.exe) always runs a package on the local computer, even if the package is saved on a remote server.</span></span> <span data-ttu-id="b93df-123">Se il pacchetto remoto utilizza file di configurazione che si trovano a loro volta sul server remoto, l'Utilità di esecuzione pacchetti non è in grado di individuare tali file e l'esecuzione del pacchetto ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="b93df-123">If the remote package uses configuration files that also are saved on the remote server, then the Execute Package utility may not locate the configurations and the package fails.</span></span> <span data-ttu-id="b93df-124">Per evitare questo problema, è necessario fare riferimento ai file di configurazione tramite un nome condiviso in formato UNC (Universal Naming Convention), ad esempio \\\mioserver\miofile.</span><span class="sxs-lookup"><span data-stu-id="b93df-124">To avoid this problem, the configurations must be referenced by using a Universal Naming Convention (UNC) share name like \\\myserver\myfile.</span></span>  
  
### <a name="static-options"></a><span data-ttu-id="b93df-125">Opzioni statiche</span><span class="sxs-lookup"><span data-stu-id="b93df-125">Static Options</span></span>  
 <span data-ttu-id="b93df-126">**Origine pacchetto**</span><span class="sxs-lookup"><span data-stu-id="b93df-126">**Package source**</span></span>  
 <span data-ttu-id="b93df-127">Consente di specificare il percorso del pacchetto da eseguire mediante le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b93df-127">Specify the location of the package to run, using the following options:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b93df-128">valore</span><span class="sxs-lookup"><span data-stu-id="b93df-128">Value</span></span>|<span data-ttu-id="b93df-129">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b93df-129">Description</span></span>|  
|<span data-ttu-id="b93df-130">**SQL Server**</span><span class="sxs-lookup"><span data-stu-id="b93df-130">**SQL Server**</span></span>|<span data-ttu-id="b93df-131">Selezionare questa opzione se il pacchetto si trova in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b93df-131">Select this option when the package resides in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="b93df-132">Specificare un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e immettere il nome utente e la password per l'autenticazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b93df-132">Specify an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and provide a user name and password for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="b93df-133">Ogni nome utente e password aggiunge le opzioni **/USER** _nomeutente_ e **/PASSWORD** _password_ al prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="b93df-133">Each user name and password adds the **/USER** _username_ and **/PASSWORD** _password_ options to the command prompt.</span></span>|  
|<span data-ttu-id="b93df-134">**File system**</span><span class="sxs-lookup"><span data-stu-id="b93df-134">**File system**</span></span>|<span data-ttu-id="b93df-135">Selezionare questa opzione se il pacchetto si trova nel file system.</span><span class="sxs-lookup"><span data-stu-id="b93df-135">Select this option when the package resides in the file system.</span></span>|  
|<span data-ttu-id="b93df-136">**Archivio pacchetti SSIS**</span><span class="sxs-lookup"><span data-stu-id="b93df-136">**SSIS Package Store**</span></span>|<span data-ttu-id="b93df-137">Selezionare questa opzione se il pacchetto si trova nell'Archivio pacchetti [!INCLUDE[ssIS](../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b93df-137">Select this option when the package resides in the [!INCLUDE[ssIS](../../includes/ssis-md.md)] Package Store.</span></span>|  
  
 <span data-ttu-id="b93df-138">Ad ognuna di queste impostazioni è associato il set di opzioni seguente.</span><span class="sxs-lookup"><span data-stu-id="b93df-138">Each of these selections has the following set of options.</span></span>  
  
 <span data-ttu-id="b93df-139">**Eseguire**</span><span class="sxs-lookup"><span data-stu-id="b93df-139">**Execute**</span></span>  
 <span data-ttu-id="b93df-140">Fare clic su questo pulsante per eseguire il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="b93df-140">Click to run the package.</span></span>  
  
 <span data-ttu-id="b93df-141">**Close**</span><span class="sxs-lookup"><span data-stu-id="b93df-141">**Close**</span></span>  
 <span data-ttu-id="b93df-142">Fare clic su questo pulsante per chiudere la finestra di dialogo **Utilità di esecuzione pacchetti** .</span><span class="sxs-lookup"><span data-stu-id="b93df-142">Click to close the **Execute Package Utility** dialog box.</span></span>  
  
### <a name="dynamic-options"></a><span data-ttu-id="b93df-143">Opzioni dinamiche</span><span class="sxs-lookup"><span data-stu-id="b93df-143">Dynamic Options</span></span>  
  
#### <a name="package-source--sql-server"></a><span data-ttu-id="b93df-144">Origine pacchetto = SQL Server</span><span class="sxs-lookup"><span data-stu-id="b93df-144">Package Source = SQL Server</span></span>  
 <span data-ttu-id="b93df-145">**Server**</span><span class="sxs-lookup"><span data-stu-id="b93df-145">**Server**</span></span>  
 <span data-ttu-id="b93df-146">Consente di digitare il nome del server in cui si trova il pacchetto o di selezionare il server nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="b93df-146">Type the name of the server where the package resides, or select a server from the list.</span></span>  
  
 <span data-ttu-id="b93df-147">**Accesso al server**</span><span class="sxs-lookup"><span data-stu-id="b93df-147">**Log on to the server**</span></span>  
 <span data-ttu-id="b93df-148">Consente di specificare se il pacchetto deve usare l'autenticazione di Windows o di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per eseguire la connessione a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b93df-148">Specify whether the package should use Windows Authentication or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication to connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="b93df-149">Per una maggiore sicurezza è consigliabile utilizzare l'autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="b93df-149">Windows Authentication is recommended for better security.</span></span> <span data-ttu-id="b93df-150">Se si sceglie di utilizzare l'autenticazione di Windows, non è necessario specificare il nome utente e la password.</span><span class="sxs-lookup"><span data-stu-id="b93df-150">With Windows Authentication you do not have to specify a user name and password.</span></span>  
  
 <span data-ttu-id="b93df-151">**Usa autenticazione di Windows**</span><span class="sxs-lookup"><span data-stu-id="b93df-151">**Use Windows Authentication**</span></span>  
 <span data-ttu-id="b93df-152">Selezionare questa opzione per usare l'autenticazione di Windows e accedere mediante un account utente di [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="b93df-152">Select this option to use Windows Authentication and log on using a [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows user account.</span></span>  
  
 <span data-ttu-id="b93df-153">**Usa autenticazione di SQL Server**</span><span class="sxs-lookup"><span data-stu-id="b93df-153">**Use SQL Server Authentication**</span></span>  
 <span data-ttu-id="b93df-154">Selezionare questa opzione per usare l'autenticazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b93df-154">Select this option to use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="b93df-155">Quando un utente si connette con un nome di account di accesso e una password da una connessione non trusted, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] esegue l'autenticazione controllando se è stato impostato un account di accesso di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e se la password specificata corrisponde a quella registrata in precedenza.</span><span class="sxs-lookup"><span data-stu-id="b93df-155">When a user connects with a specified login name and password from a non-trusted connection, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] performs the authentication by checking to see if a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login account has been set up and if the specified password matches the one previously recorded.</span></span> <span data-ttu-id="b93df-156">Se [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] non riesce a trovare un account di accesso, l'autenticazione ha esito negativo e viene visualizzato un messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="b93df-156">If [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cannot find the login account, authentication fails, and the user receives an error message.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="b93df-157">Se possibile, usare l'autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="b93df-157">When possible, use Windows Authentication.</span></span>  
  
 <span data-ttu-id="b93df-158">**Pacchetto**</span><span class="sxs-lookup"><span data-stu-id="b93df-158">**Package**</span></span>  
 <span data-ttu-id="b93df-159">Digitare il nome del pacchetto o fare clic sul pulsante con i puntini di sospensione **(...)** per individuare il pacchetto mediante la finestra di dialogo **Seleziona pacchetto SSIS**.</span><span class="sxs-lookup"><span data-stu-id="b93df-159">Type the name of the package, or click the ellipsis button **(...)** to locate a package using the **Select an SSIS Package** dialog box.</span></span>  
  
#### <a name="package-source--file-system"></a><span data-ttu-id="b93df-160">Origine pacchetto = File system</span><span class="sxs-lookup"><span data-stu-id="b93df-160">Package Source = File System</span></span>  
 <span data-ttu-id="b93df-161">**Pacchetto**</span><span class="sxs-lookup"><span data-stu-id="b93df-161">**Package**</span></span>  
 <span data-ttu-id="b93df-162">Digitare il nome del pacchetto o fare clic sul pulsante con i puntini di sospensione **(...)** per individuare il pacchetto mediante la finestra di dialogo Apri.</span><span class="sxs-lookup"><span data-stu-id="b93df-162">Type the name of the package, or click the ellipsis button **(...)** to locate a package using the Open dialog box.</span></span> <span data-ttu-id="b93df-163">Per impostazione predefinita, nella finestra di dialogo vengono elencati solo i file con estensione dtsx.</span><span class="sxs-lookup"><span data-stu-id="b93df-163">By default, the dialog box lists only files that have the .dtsx extension.</span></span>  
  
#### <a name="package-source--ssis-package-store"></a><span data-ttu-id="b93df-164">Origine pacchetto = Archivio pacchetti SSIS</span><span class="sxs-lookup"><span data-stu-id="b93df-164">Package Source = SSIS Package Store</span></span>  
 <span data-ttu-id="b93df-165">**Server**</span><span class="sxs-lookup"><span data-stu-id="b93df-165">**Server**</span></span>  
 <span data-ttu-id="b93df-166">Consente di digitare il nome del computer in cui si trova il pacchetto o di selezionare il computer nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="b93df-166">Type the name of the computer where the package resides, or select a computer from the list.</span></span>  
  
 <span data-ttu-id="b93df-167">**Accesso al server**</span><span class="sxs-lookup"><span data-stu-id="b93df-167">**Log on to the server**</span></span>  
 <span data-ttu-id="b93df-168">Consente di specificare se il pacchetto deve utilizzare l'autenticazione di Microsoft Windows per eseguire la connessione all'origine del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="b93df-168">Specify whether the package should use Microsoft Windows Authentication to connect to the package source.</span></span> <span data-ttu-id="b93df-169">Per una maggiore sicurezza è consigliabile utilizzare l'autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="b93df-169">Windows Authentication is recommended for better security.</span></span> <span data-ttu-id="b93df-170">Se si sceglie di utilizzare l'autenticazione di Windows, non è necessario specificare il nome utente e la password.</span><span class="sxs-lookup"><span data-stu-id="b93df-170">With Windows Authentication you do not have to specify a user name and password.</span></span>  
  
 <span data-ttu-id="b93df-171">**Usa autenticazione di Windows**</span><span class="sxs-lookup"><span data-stu-id="b93df-171">**Use Windows Authentication**</span></span>  
 <span data-ttu-id="b93df-172">Selezionare questa opzione per utilizzare l'autenticazione di Windows e accedere mediante un account utente di Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="b93df-172">Select this option to use Windows Authentication and log on using a Microsoft Windows user account.</span></span>  
  
 <span data-ttu-id="b93df-173">**Usa autenticazione di SQL Server**</span><span class="sxs-lookup"><span data-stu-id="b93df-173">**Use SQL Server Authentication**</span></span>  
 <span data-ttu-id="b93df-174">Questa opzione non è disponibile se si esegue un pacchetto incluso nell' **Archivio pacchetti SSIS**.</span><span class="sxs-lookup"><span data-stu-id="b93df-174">This option is not available when you run a package stored in the **SSIS Package Store**.</span></span>  
  
 <span data-ttu-id="b93df-175">**Pacchetto**</span><span class="sxs-lookup"><span data-stu-id="b93df-175">**Package**</span></span>  
 <span data-ttu-id="b93df-176">Digitare il nome del pacchetto o fare clic sul pulsante con i puntini di sospensione **(...)** per individuare il pacchetto mediante la finestra di dialogo **Seleziona pacchetto SSIS**.</span><span class="sxs-lookup"><span data-stu-id="b93df-176">Type the name of the package, or click the ellipsis button **(...)** to locate a package using the **Select an SSIS Package** dialog box.</span></span>  
  
## <a name="configurations-page"></a><span data-ttu-id="b93df-177">Pagina Configurazioni</span><span class="sxs-lookup"><span data-stu-id="b93df-177">Configurations Page</span></span>  
 <span data-ttu-id="b93df-178">Utilizzare la pagina **Configurazioni** della finestra di dialogo **Utilità di esecuzione pacchetti** per selezionare i file di configurazione da caricare in fase di esecuzione e di specificare l'ordine in cui devono essere caricati.</span><span class="sxs-lookup"><span data-stu-id="b93df-178">Use the **Configurations** page of the **Execute Package Utility** dialog box to select the configuration files to load at run time, and to specify the order in which they load.</span></span>  
  
### <a name="options"></a><span data-ttu-id="b93df-179">Opzioni</span><span class="sxs-lookup"><span data-stu-id="b93df-179">Options</span></span>  
 <span data-ttu-id="b93df-180">**File di configurazione**</span><span class="sxs-lookup"><span data-stu-id="b93df-180">**Configuration files**</span></span>  
 <span data-ttu-id="b93df-181">Elenca le configurazioni utilizzate dal pacchetto.</span><span class="sxs-lookup"><span data-stu-id="b93df-181">Lists the configurations that the package uses.</span></span> <span data-ttu-id="b93df-182">Ogni file di configurazione aggiunge un'opzione **/CONFIGFILE nomefile** al prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="b93df-182">Each configuration file adds a **/CONFIGFILE filename** option to the command prompt.</span></span>  
  
 <span data-ttu-id="b93df-183">**Tasti di direzione**</span><span class="sxs-lookup"><span data-stu-id="b93df-183">**Arrow keys**</span></span>  
 <span data-ttu-id="b93df-184">Selezionare un file di configurazione nell'elenco e utilizzare i tasti di direzione sulla destra per modificare l'ordine di caricamento.</span><span class="sxs-lookup"><span data-stu-id="b93df-184">Select a configuration file in the list, and use the arrow keys at right to change the loading order.</span></span> <span data-ttu-id="b93df-185">Le configurazioni vengono caricate a partire dall'inizio dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="b93df-185">Configurations load in order starting from the top of the list.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b93df-186">Se più configurazioni modificano la stessa proprietà, viene utilizzata la configurazione caricata per ultima.</span><span class="sxs-lookup"><span data-stu-id="b93df-186">If multiple configurations modify the same property, the configuration that loads last is used.</span></span>  
  
 <span data-ttu-id="b93df-187">**Aggiungere**</span><span class="sxs-lookup"><span data-stu-id="b93df-187">**Add**</span></span>  
 <span data-ttu-id="b93df-188">Fare clic su questo pulsante per aggiungere configurazioni tramite la finestra di dialogo **Apri** .</span><span class="sxs-lookup"><span data-stu-id="b93df-188">Click to add configurations using the **Open** dialog box.</span></span> <span data-ttu-id="b93df-189">Per impostazione predefinita, nella finestra di dialogo sono elencati solo i file con estensione dtsconfig.</span><span class="sxs-lookup"><span data-stu-id="b93df-189">By default, the dialog box lists only files that have the .dtsconfig extension.</span></span>  
  
 <span data-ttu-id="b93df-190">**Rimuovi**</span><span class="sxs-lookup"><span data-stu-id="b93df-190">**Remove**</span></span>  
 <span data-ttu-id="b93df-191">Selezionare un file di configurazione nell'elenco e quindi fare clic su **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="b93df-191">Select a configuration file in the list and then click **Remove**.</span></span>  
  
 <span data-ttu-id="b93df-192">**Eseguire**</span><span class="sxs-lookup"><span data-stu-id="b93df-192">**Execute**</span></span>  
 <span data-ttu-id="b93df-193">Fare clic su questo pulsante per eseguire il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="b93df-193">Click to run the package.</span></span>  
  
 <span data-ttu-id="b93df-194">**Close**</span><span class="sxs-lookup"><span data-stu-id="b93df-194">**Close**</span></span>  
 <span data-ttu-id="b93df-195">Fare clic su questo pulsante per chiudere la finestra di dialogo **Utilità di esecuzione pacchetti** .</span><span class="sxs-lookup"><span data-stu-id="b93df-195">Click to close the **Execute Package Utility** dialog box.</span></span>  
  
## <a name="command-files-page"></a><span data-ttu-id="b93df-196">Pagina File di comando</span><span class="sxs-lookup"><span data-stu-id="b93df-196">Command Files Page</span></span>  
 <span data-ttu-id="b93df-197">Utilizzare la pagina **File di comando** della finestra di dialogo **Utilità di esecuzione pacchetti** per selezionare i file di comando da caricare in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="b93df-197">Use the **Command Files** page of the **Execute Package Utility** dialog box to select the command files to load at run time.</span></span>  
  
### <a name="options"></a><span data-ttu-id="b93df-198">Opzioni</span><span class="sxs-lookup"><span data-stu-id="b93df-198">Options</span></span>  
 <span data-ttu-id="b93df-199">**File di comando**</span><span class="sxs-lookup"><span data-stu-id="b93df-199">**Command files**</span></span>  
 <span data-ttu-id="b93df-200">Consente di elencare i file di comando utilizzati dal pacchetto.</span><span class="sxs-lookup"><span data-stu-id="b93df-200">Lists the command files that the package uses.</span></span> <span data-ttu-id="b93df-201">Un pacchetto può utilizzare più file per l'impostazione delle opzioni della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="b93df-201">A package can use multiple files to set command-line options.</span></span>  
  
 <span data-ttu-id="b93df-202">**Tasti di direzione**</span><span class="sxs-lookup"><span data-stu-id="b93df-202">**Arrow keys**</span></span>  
 <span data-ttu-id="b93df-203">Selezionare un file di comando nell'elenco e utilizzare i tasti di direzione a destra per modificare l'ordine di caricamento.</span><span class="sxs-lookup"><span data-stu-id="b93df-203">Select a command file in the list, and use the arrow keys at right to change the loading order.</span></span> <span data-ttu-id="b93df-204">I file di comando vengono caricati in ordine a partire dalla parte superiore dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="b93df-204">Command files load in order, starting from the top of the list.</span></span>  
  
 <span data-ttu-id="b93df-205">**Aggiungere**</span><span class="sxs-lookup"><span data-stu-id="b93df-205">**Add**</span></span>  
 <span data-ttu-id="b93df-206">Fare clic su questo pulsante per aggiungere un file di comando usando la finestra di dialogo **Apri** .</span><span class="sxs-lookup"><span data-stu-id="b93df-206">Click to add a command file, using the **Open** dialog box.</span></span>  
  
 <span data-ttu-id="b93df-207">**Rimuovi**</span><span class="sxs-lookup"><span data-stu-id="b93df-207">**Remove**</span></span>  
 <span data-ttu-id="b93df-208">Selezionare un file di comando nella casella di testo e quindi rimuoverlo con il pulsante **Rimuovi** .</span><span class="sxs-lookup"><span data-stu-id="b93df-208">Select a command file in the text box, and then remove it using the **Remove** button.</span></span>  
  
 <span data-ttu-id="b93df-209">**Eseguire**</span><span class="sxs-lookup"><span data-stu-id="b93df-209">**Execute**</span></span>  
 <span data-ttu-id="b93df-210">Fare clic su questo pulsante per eseguire il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="b93df-210">Click to run the package.</span></span>  
  
 <span data-ttu-id="b93df-211">**Close**</span><span class="sxs-lookup"><span data-stu-id="b93df-211">**Close**</span></span>  
 <span data-ttu-id="b93df-212">Fare clic su questo pulsante per chiudere la finestra di dialogo **Utilità di esecuzione pacchetti** .</span><span class="sxs-lookup"><span data-stu-id="b93df-212">Click to close the **Execute Package Utility** dialog box.</span></span>  
  
## <a name="connection-managers-page"></a><span data-ttu-id="b93df-213">Pagina Gestioni connessioni</span><span class="sxs-lookup"><span data-stu-id="b93df-213">Connection Managers Page</span></span>  
 <span data-ttu-id="b93df-214">Utilizzare la pagina **Gestioni connessioni** della finestra di dialogo **Utilità di esecuzione pacchetti** per modificare le stringhe di connessione delle gestioni connessioni utilizzate dal pacchetto.</span><span class="sxs-lookup"><span data-stu-id="b93df-214">Use the **Connection Managers** page of the **Execute Package Utility** dialog box to edit the connection strings of the connection managers that the package uses.</span></span>  
  
### <a name="options"></a><span data-ttu-id="b93df-215">Opzioni</span><span class="sxs-lookup"><span data-stu-id="b93df-215">Options</span></span>  
 <span data-ttu-id="b93df-216">**Gestione connessione**</span><span class="sxs-lookup"><span data-stu-id="b93df-216">**Connection Manager**</span></span>  
 <span data-ttu-id="b93df-217">Selezionare la casella di controllo corrispondente per rendere modificabile la colonna **Stringa di connessione** .</span><span class="sxs-lookup"><span data-stu-id="b93df-217">Select its check box to make the **Connection String** column editable.</span></span>  
  
 <span data-ttu-id="b93df-218">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="b93df-218">**Description**</span></span>  
 <span data-ttu-id="b93df-219">Consente di visualizzare una descrizione di ogni gestione connessione.</span><span class="sxs-lookup"><span data-stu-id="b93df-219">View a description for each connection manager.</span></span> <span data-ttu-id="b93df-220">Non è possibile modificare le descrizioni.</span><span class="sxs-lookup"><span data-stu-id="b93df-220">Descriptions cannot be edited.</span></span>  
  
 <span data-ttu-id="b93df-221">**Stringa di connessione**</span><span class="sxs-lookup"><span data-stu-id="b93df-221">**Connection String**</span></span>  
 <span data-ttu-id="b93df-222">Consente di modificare la stringa di connessione per una gestione connessione.</span><span class="sxs-lookup"><span data-stu-id="b93df-222">Edit the connection string for a connection manager.</span></span> <span data-ttu-id="b93df-223">Questo campo è modificabile solo quando è selezionata la casella di controllo **Gestione connessione** .</span><span class="sxs-lookup"><span data-stu-id="b93df-223">This field is editable only when the **Connection Manager** check box is selected.</span></span>  
  
 <span data-ttu-id="b93df-224">**Eseguire**</span><span class="sxs-lookup"><span data-stu-id="b93df-224">**Execute**</span></span>  
 <span data-ttu-id="b93df-225">Fare clic su questo pulsante per eseguire il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="b93df-225">Click to run the package.</span></span>  
  
 <span data-ttu-id="b93df-226">**Close**</span><span class="sxs-lookup"><span data-stu-id="b93df-226">**Close**</span></span>  
 <span data-ttu-id="b93df-227">Fare clic su questo pulsante per chiudere la finestra di dialogo **Utilità di esecuzione pacchetti** .</span><span class="sxs-lookup"><span data-stu-id="b93df-227">Click to close the **Execute Package Utility** dialog box.</span></span>  
  
## <a name="execution-options-page"></a><span data-ttu-id="b93df-228">Pagina Opzioni di esecuzione</span><span class="sxs-lookup"><span data-stu-id="b93df-228">Execution Options Page</span></span>  
 <span data-ttu-id="b93df-229">Usare la pagina **Opzioni di esecuzione** della finestra di dialogo **Utilità di esecuzione pacchetti** per specificare le opzioni di runtime per il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="b93df-229">Use the **Execution Options** page of the **Execute Package Utility** dialog box to specify run-time options for the package.</span></span>  
  
### <a name="options"></a><span data-ttu-id="b93df-230">Opzioni</span><span class="sxs-lookup"><span data-stu-id="b93df-230">Options</span></span>  
 <span data-ttu-id="b93df-231">**Interrompi il pacchetto in caso di avvisi di convalida**</span><span class="sxs-lookup"><span data-stu-id="b93df-231">**Fail package on validation warnings**</span></span>  
 <span data-ttu-id="b93df-232">Indica se il pacchetto deve essere interrotto quando vengono generati avvisi di convalida.</span><span class="sxs-lookup"><span data-stu-id="b93df-232">Indicate whether the package fails if a validation warning occurs.</span></span>  
  
 <span data-ttu-id="b93df-233">**Convalida pacchetto senza esecuzione**</span><span class="sxs-lookup"><span data-stu-id="b93df-233">**Validate package without executing**</span></span>  
 <span data-ttu-id="b93df-234">Indica se il pacchetto viene esclusivamente convalidato.</span><span class="sxs-lookup"><span data-stu-id="b93df-234">Indicate whether the package is validated only.</span></span>  
  
 <span data-ttu-id="b93df-235">**Numero massimo di file eseguibili simultanei**</span><span class="sxs-lookup"><span data-stu-id="b93df-235">**Maximum concurrent executables**</span></span>  
 <span data-ttu-id="b93df-236">Se si desidera, specificare il numero massimo di file eseguibili che possono essere eseguiti simultaneamente nel pacchetto.</span><span class="sxs-lookup"><span data-stu-id="b93df-236">Indicate whether you want to specify the maximum number of executables that can run in the package at the same time.</span></span> <span data-ttu-id="b93df-237">Dopo avere selezionato questa casella di controllo, utilizzare la casella di selezione per specificare il numero massimo di file eseguibili.</span><span class="sxs-lookup"><span data-stu-id="b93df-237">After you select this check box, use the spin box to specify the maximum number of executables.</span></span>  
  
 <span data-ttu-id="b93df-238">**Abilita checkpoint pacchetto**</span><span class="sxs-lookup"><span data-stu-id="b93df-238">**Enable package checkpoints**</span></span>  
 <span data-ttu-id="b93df-239">Indica se abilitare i checkpoint del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="b93df-239">Indicate whether to enable package checkpoints.</span></span>  
  
 <span data-ttu-id="b93df-240">**File del checkpoint**</span><span class="sxs-lookup"><span data-stu-id="b93df-240">**Checkpoint file**</span></span>  
 <span data-ttu-id="b93df-241">Elenca i file del checkpoint utilizzati dal pacchetto, se si abilitano i checkpoint del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="b93df-241">List the checkpoint file the package uses, if you enable package checkpoints.</span></span>  
  
 <span data-ttu-id="b93df-242">**Sfoglia**</span><span class="sxs-lookup"><span data-stu-id="b93df-242">**Browse**</span></span>  
 <span data-ttu-id="b93df-243">Fare clic sul pulsante Sfoglia **(...)** per individuare il file del checkpoint tramite la finestra di dialogo **Apri**, se si abilitano i checkpoint del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="b93df-243">Click the browse button **(...)** to locate the checkpoint file using the **Open** dialog box, if you enable package checkpoints.</span></span> <span data-ttu-id="b93df-244">Se è già stato specificato un file del checkpoint, questo viene sostituito dal file selezionato.</span><span class="sxs-lookup"><span data-stu-id="b93df-244">If a checkpoint file is already specified, it is replaced by the selected file.</span></span>  
  
 <span data-ttu-id="b93df-245">**Ignora opzioni di riavvio**</span><span class="sxs-lookup"><span data-stu-id="b93df-245">**Override restart options**</span></span>  
 <span data-ttu-id="b93df-246">Indica se ignorare le opzioni di riavvio, se si abilitano i checkpoint del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="b93df-246">Indicate whether to override restart options, if you enable package checkpoints.</span></span>  
  
 <span data-ttu-id="b93df-247">**Opzione di riavvio**</span><span class="sxs-lookup"><span data-stu-id="b93df-247">**Restart option**</span></span>  
 <span data-ttu-id="b93df-248">Consente di selezionare la modalità di utilizzo dei checkpoint, se si ignorano le opzioni di riavvio.</span><span class="sxs-lookup"><span data-stu-id="b93df-248">Select how to use checkpoints, if you override restart options.</span></span>  
  
 <span data-ttu-id="b93df-249">**Eseguire**</span><span class="sxs-lookup"><span data-stu-id="b93df-249">**Execute**</span></span>  
 <span data-ttu-id="b93df-250">Fare clic su questo pulsante per eseguire il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="b93df-250">Click to run the package.</span></span>  
  
 <span data-ttu-id="b93df-251">**Close**</span><span class="sxs-lookup"><span data-stu-id="b93df-251">**Close**</span></span>  
 <span data-ttu-id="b93df-252">Fare clic su questo pulsante per chiudere la finestra di dialogo **Utilità di esecuzione pacchetti** .</span><span class="sxs-lookup"><span data-stu-id="b93df-252">Click to close the **Execute Package Utility** dialog box.</span></span>  
  
## <a name="reporting-page"></a><span data-ttu-id="b93df-253">Pagina Report</span><span class="sxs-lookup"><span data-stu-id="b93df-253">Reporting Page</span></span>  
 <span data-ttu-id="b93df-254">Utilizzare la pagina **Report** dell' **Utilità di esecuzione pacchetti** per specificare le informazioni e gli eventi relativi al pacchetto da registrare nella console durante l'esecuzione del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="b93df-254">Use the **Reporting** page of the **Execute Package Utility** dialog box to specify the events and information about the package to log to the console when the package runs.</span></span>  
  
### <a name="options"></a><span data-ttu-id="b93df-255">Opzioni</span><span class="sxs-lookup"><span data-stu-id="b93df-255">Options</span></span>  
 <span data-ttu-id="b93df-256">**Eventi console**</span><span class="sxs-lookup"><span data-stu-id="b93df-256">**Console events**</span></span>  
 <span data-ttu-id="b93df-257">Consente di specificare gli eventi e i tipi di messaggi da segnalare.</span><span class="sxs-lookup"><span data-stu-id="b93df-257">Indicate the events and types of messages to report.</span></span>  
  
 <span data-ttu-id="b93df-258">**Nessuno**</span><span class="sxs-lookup"><span data-stu-id="b93df-258">**None**</span></span>  
 <span data-ttu-id="b93df-259">Selezionare questa opzione per non generare report.</span><span class="sxs-lookup"><span data-stu-id="b93df-259">Select for no reporting.</span></span>  
  
 <span data-ttu-id="b93df-260">**Errori**</span><span class="sxs-lookup"><span data-stu-id="b93df-260">**Errors**</span></span>  
 <span data-ttu-id="b93df-261">Selezionare questa opzione per segnalare i messaggi di errore.</span><span class="sxs-lookup"><span data-stu-id="b93df-261">Select to report error messages.</span></span>  
  
 <span data-ttu-id="b93df-262">**Avvisi**</span><span class="sxs-lookup"><span data-stu-id="b93df-262">**Warnings**</span></span>  
 <span data-ttu-id="b93df-263">Selezionare questa opzione per segnalare i messaggi di avviso.</span><span class="sxs-lookup"><span data-stu-id="b93df-263">Select to report warning messages.</span></span>  
  
 <span data-ttu-id="b93df-264">**Eventi personalizzati**</span><span class="sxs-lookup"><span data-stu-id="b93df-264">**Custom Events**</span></span>  
 <span data-ttu-id="b93df-265">Selezionare questa opzione per segnalare i messaggi di evento personalizzati.</span><span class="sxs-lookup"><span data-stu-id="b93df-265">Select to report custom event messages.</span></span>  
  
 <span data-ttu-id="b93df-266">**Eventi pipeline**</span><span class="sxs-lookup"><span data-stu-id="b93df-266">**Pipeline Events**</span></span>  
 <span data-ttu-id="b93df-267">Selezionare questa opzione per segnalare i messaggi di evento dei flussi di dati.</span><span class="sxs-lookup"><span data-stu-id="b93df-267">Select to report data flow events messages.</span></span>  
  
 <span data-ttu-id="b93df-268">**Informazioni**</span><span class="sxs-lookup"><span data-stu-id="b93df-268">**Information**</span></span>  
 <span data-ttu-id="b93df-269">Selezionare questa opzione per segnalare i messaggi informativi.</span><span class="sxs-lookup"><span data-stu-id="b93df-269">Select to report information messages.</span></span>  
  
 <span data-ttu-id="b93df-270">**Dettagliato**</span><span class="sxs-lookup"><span data-stu-id="b93df-270">**Verbose**</span></span>  
 <span data-ttu-id="b93df-271">Selezionare questa opzione per utilizzare i report dettagliati.</span><span class="sxs-lookup"><span data-stu-id="b93df-271">Select to use verbose reporting.</span></span>  
  
 <span data-ttu-id="b93df-272">**Registrazione console**</span><span class="sxs-lookup"><span data-stu-id="b93df-272">**Console logging**</span></span>  
 <span data-ttu-id="b93df-273">Consente di specificare le informazioni che si desidera scrivere nel registro al verificarsi dell'evento selezionato.</span><span class="sxs-lookup"><span data-stu-id="b93df-273">Specify the information that you want written to the log when the selected event occurs.</span></span>  
  
 <span data-ttu-id="b93df-274">**Nome**</span><span class="sxs-lookup"><span data-stu-id="b93df-274">**Name**</span></span>  
 <span data-ttu-id="b93df-275">Selezionare questa opzione per segnalare il nome dell'utente che ha creato il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="b93df-275">Select to report the name of the person who created the package.</span></span>  
  
 <span data-ttu-id="b93df-276">**Computer**</span><span class="sxs-lookup"><span data-stu-id="b93df-276">**Computer**</span></span>  
 <span data-ttu-id="b93df-277">Selezionare questa opzione per segnalare il nome del computer nel quale il pacchetto è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="b93df-277">Select to report the name of the computer the package is running on.</span></span>  
  
 <span data-ttu-id="b93df-278">**Operatore**</span><span class="sxs-lookup"><span data-stu-id="b93df-278">**Operator**</span></span>  
 <span data-ttu-id="b93df-279">Selezionare questa opzione per segnalare il nome dell'utente che ha avviato il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="b93df-279">Select to report the name of the person who started the package.</span></span>  
  
 <span data-ttu-id="b93df-280">**Nome origine**</span><span class="sxs-lookup"><span data-stu-id="b93df-280">**Source name**</span></span>  
 <span data-ttu-id="b93df-281">Selezionare questa opzione per segnalare il nome del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="b93df-281">Select to report the package name.</span></span>  
  
 <span data-ttu-id="b93df-282">**GUID origine**</span><span class="sxs-lookup"><span data-stu-id="b93df-282">**Source GUID**</span></span>  
 <span data-ttu-id="b93df-283">Selezionare questa opzione per segnalare il GUID del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="b93df-283">Select to report the package GUID.</span></span>  
  
 <span data-ttu-id="b93df-284">**GUID esecuzione**</span><span class="sxs-lookup"><span data-stu-id="b93df-284">**Execution GUID**</span></span>  
 <span data-ttu-id="b93df-285">Selezionare questa opzione per segnalare il GUID dell'istanza di esecuzione del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="b93df-285">Select to report the GUID of the package execution instance.</span></span>  
  
 <span data-ttu-id="b93df-286">**Messaggio**</span><span class="sxs-lookup"><span data-stu-id="b93df-286">**Message**</span></span>  
 <span data-ttu-id="b93df-287">Selezionare questa opzione per segnalare i messaggi.</span><span class="sxs-lookup"><span data-stu-id="b93df-287">Select to report messages.</span></span>  
  
 <span data-ttu-id="b93df-288">**Ora di inizio e fine**</span><span class="sxs-lookup"><span data-stu-id="b93df-288">**Start time and end time**</span></span>  
 <span data-ttu-id="b93df-289">Selezionare questa opzione per segnalare l'ora di inizio e fine dell'esecuzione del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="b93df-289">Select to report when the package began and finished.</span></span>  
  
 <span data-ttu-id="b93df-290">**Eseguire**</span><span class="sxs-lookup"><span data-stu-id="b93df-290">**Execute**</span></span>  
 <span data-ttu-id="b93df-291">Fare clic su questo pulsante per eseguire il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="b93df-291">Click to run the package.</span></span>  
  
 <span data-ttu-id="b93df-292">**Close**</span><span class="sxs-lookup"><span data-stu-id="b93df-292">**Close**</span></span>  
 <span data-ttu-id="b93df-293">Fare clic su questo pulsante per chiudere la finestra di dialogo **Utilità di esecuzione pacchetti** .</span><span class="sxs-lookup"><span data-stu-id="b93df-293">Click to close the **Execute Package Utility** dialog box.</span></span>  
  
## <a name="logging-page"></a><span data-ttu-id="b93df-294">Pagina Registrazione</span><span class="sxs-lookup"><span data-stu-id="b93df-294">Logging Page</span></span>  
 <span data-ttu-id="b93df-295">Utilizzare la pagina **Registrazione** della finestra di dialogo **Utilità di esecuzione pacchetti** per rendere disponibili i provider di log per il pacchetto in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="b93df-295">Use the **Logging** page of the **Execute Package Utility** dialog box to make log providers available to the package at run time.</span></span> <span data-ttu-id="b93df-296">Specificare il tipo di provider di log del pacchetto e la stringa di connessione al log.</span><span class="sxs-lookup"><span data-stu-id="b93df-296">Provide the package log provider type and the connection string for connecting to the log.</span></span> <span data-ttu-id="b93df-297">Per ogni voce di provider di log, viene aggiunta un'opzione **/LOGGER**_idclasse_ al prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="b93df-297">Each log provider entry adds a **/LOGGER**_classid_ option to the command prompt.</span></span>  
  
### <a name="options"></a><span data-ttu-id="b93df-298">Opzioni</span><span class="sxs-lookup"><span data-stu-id="b93df-298">Options</span></span>  
 <span data-ttu-id="b93df-299">**Provider di log**</span><span class="sxs-lookup"><span data-stu-id="b93df-299">**Log Provider**</span></span>  
 <span data-ttu-id="b93df-300">Selezionare un provider di log dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="b93df-300">Select a log provider from the list.</span></span>  
  
 <span data-ttu-id="b93df-301">**Stringa di configurazione**</span><span class="sxs-lookup"><span data-stu-id="b93df-301">**Configuration String**</span></span>  
 <span data-ttu-id="b93df-302">Selezionare il nome della gestione connessione dal pacchetto che punta al percorso del log oppure digitare la stringa di connessione al provider di log.</span><span class="sxs-lookup"><span data-stu-id="b93df-302">Select the name of the connection manager from the package that points to the log location, or type the connection string for connecting to the log provider.</span></span>  
  
 <span data-ttu-id="b93df-303">**Rimuovi**</span><span class="sxs-lookup"><span data-stu-id="b93df-303">**Remove**</span></span>  
 <span data-ttu-id="b93df-304">Selezionare un provider di log e fare clic su questo pulsante per rimuoverlo.</span><span class="sxs-lookup"><span data-stu-id="b93df-304">Select a log provider and click to remove it.</span></span>  
  
 <span data-ttu-id="b93df-305">**Eseguire**</span><span class="sxs-lookup"><span data-stu-id="b93df-305">**Execute**</span></span>  
 <span data-ttu-id="b93df-306">Fare clic su questo pulsante per eseguire il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="b93df-306">Click to run the package.</span></span>  
  
 <span data-ttu-id="b93df-307">**Close**</span><span class="sxs-lookup"><span data-stu-id="b93df-307">**Close**</span></span>  
 <span data-ttu-id="b93df-308">Fare clic su questo pulsante per chiudere la finestra di dialogo **Utilità di esecuzione pacchetti** .</span><span class="sxs-lookup"><span data-stu-id="b93df-308">Click to close the **Execute Package Utility** dialog box.</span></span>  
  
## <a name="set-values-page"></a><span data-ttu-id="b93df-309">Pagina Imposta valori</span><span class="sxs-lookup"><span data-stu-id="b93df-309">Set Values Page</span></span>  
 <span data-ttu-id="b93df-310">Utilizzare la pagina **Imposta valori** della finestra di dialogo **Utilità di esecuzione pacchetti** per impostare i valori delle proprietà di pacchetti, file eseguibili, connessioni, variabili e provider di log specificando i percorsi delle proprietà e i valori di queste ultime.</span><span class="sxs-lookup"><span data-stu-id="b93df-310">Use the **Set Values** page of the **Execute Package Utility** dialog box to set the property values of packages, executables, connections, variables, and log providers by typing the paths of properties and the property values.</span></span> <span data-ttu-id="b93df-311">Ogni percorso aggiunge un'opzione **/SET**_percorsoproprietà;valore_ al prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="b93df-311">Each path entry adds a **/SET**_propertypath;value_ option to the command prompt.</span></span>  
  
### <a name="options"></a><span data-ttu-id="b93df-312">Opzioni</span><span class="sxs-lookup"><span data-stu-id="b93df-312">Options</span></span>  
 <span data-ttu-id="b93df-313">**Percorso proprietà**</span><span class="sxs-lookup"><span data-stu-id="b93df-313">**Property Path**</span></span>  
 <span data-ttu-id="b93df-314">Consente di immettere il percorso della proprietà.</span><span class="sxs-lookup"><span data-stu-id="b93df-314">Type the path of the property.</span></span> <span data-ttu-id="b93df-315">La sintassi del percorso usa una barra rovesciata (\\) per indicare che l'elemento seguente è un contenitore, il punto (.) per indicare che l'elemento seguente è una proprietà e le parentesi per indicare un membro di una raccolta.</span><span class="sxs-lookup"><span data-stu-id="b93df-315">The path syntax uses a backslash (\\) to indicate that the following item is a container, the period (.) to indicate the following item is a property, and brackets to indicate a collection member.</span></span> <span data-ttu-id="b93df-316">Il membro può essere identificato tramite il relativo indice o nome.</span><span class="sxs-lookup"><span data-stu-id="b93df-316">The member can be identified by its index or its name.</span></span> <span data-ttu-id="b93df-317">Ad esempio, il percorso della proprietà di una variabile di pacchetto è \Pacchetto.Variabili[Variabile].Valore.</span><span class="sxs-lookup"><span data-stu-id="b93df-317">For example, the property path of a package variable is \Package.Variables[MyVariable].Value.</span></span>  
  
 <span data-ttu-id="b93df-318">**Valore**</span><span class="sxs-lookup"><span data-stu-id="b93df-318">**Value**</span></span>  
 <span data-ttu-id="b93df-319">Consente di immettere il valore della proprietà.</span><span class="sxs-lookup"><span data-stu-id="b93df-319">Type the value of the property.</span></span>  
  
 <span data-ttu-id="b93df-320">**Rimuovi**</span><span class="sxs-lookup"><span data-stu-id="b93df-320">**Remove**</span></span>  
 <span data-ttu-id="b93df-321">Selezionare un percorso di proprietà e fare clic su questo pulsante per rimuoverla.</span><span class="sxs-lookup"><span data-stu-id="b93df-321">Select a property path and click to remove it.</span></span>  
  
 <span data-ttu-id="b93df-322">**Eseguire**</span><span class="sxs-lookup"><span data-stu-id="b93df-322">**Execute**</span></span>  
 <span data-ttu-id="b93df-323">Fare clic su questo pulsante per eseguire il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="b93df-323">Click to run the package.</span></span>  
  
 <span data-ttu-id="b93df-324">**Close**</span><span class="sxs-lookup"><span data-stu-id="b93df-324">**Close**</span></span>  
 <span data-ttu-id="b93df-325">Fare clic su questo pulsante per chiudere la finestra di dialogo **Utilità di esecuzione pacchetti** .</span><span class="sxs-lookup"><span data-stu-id="b93df-325">Click to close the **Execute Package Utility** dialog box.</span></span>  
  
## <a name="verification-page"></a><span data-ttu-id="b93df-326">Pagina Verifica</span><span class="sxs-lookup"><span data-stu-id="b93df-326">Verification Page</span></span>  
 <span data-ttu-id="b93df-327">Utilizzare la pagina **Verifica** della finestra di dialogo **Utilità di esecuzione pacchetti** per impostare i criteri di verifica del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="b93df-327">Use the **Verification** page of the **Execute Package** dialog box to set criteria for verifying the package.</span></span>  
  
### <a name="options"></a><span data-ttu-id="b93df-328">Opzioni</span><span class="sxs-lookup"><span data-stu-id="b93df-328">Options</span></span>  
 <span data-ttu-id="b93df-329">**Esegui solo pacchetti firmati**</span><span class="sxs-lookup"><span data-stu-id="b93df-329">**Execute only signed packages**</span></span>  
 <span data-ttu-id="b93df-330">Selezionare questa opzione per eseguire solo i pacchetti firmati.</span><span class="sxs-lookup"><span data-stu-id="b93df-330">Select to execute only packages that have been signed.</span></span>  
  
 <span data-ttu-id="b93df-331">**Verifica build pacchetto**</span><span class="sxs-lookup"><span data-stu-id="b93df-331">**Verify package build**</span></span>  
 <span data-ttu-id="b93df-332">Selezionare questa opzione per verificare la build del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="b93df-332">Select to verify the package build.</span></span>  
  
 <span data-ttu-id="b93df-333">Compilare</span><span class="sxs-lookup"><span data-stu-id="b93df-333">Build</span></span>  
 <span data-ttu-id="b93df-334">Consente di specificare il numero di build sequenziale associato alla build.</span><span class="sxs-lookup"><span data-stu-id="b93df-334">Specify the sequential Build number associated with the build.</span></span>  
  
 <span data-ttu-id="b93df-335">**Verifica ID pacchetto**</span><span class="sxs-lookup"><span data-stu-id="b93df-335">**Verify package ID**</span></span>  
 <span data-ttu-id="b93df-336">Selezionare questa opzione per verificare l'ID del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="b93df-336">Select to verify the package ID.</span></span>  
  
 <span data-ttu-id="b93df-337">ID pacchetto</span><span class="sxs-lookup"><span data-stu-id="b93df-337">Package ID</span></span>  
 <span data-ttu-id="b93df-338">Consente di specificare il numero di identificazione del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="b93df-338">Specify the package identification number.</span></span>  
  
 <span data-ttu-id="b93df-339">**Verifica ID versione**</span><span class="sxs-lookup"><span data-stu-id="b93df-339">**Verify version ID**</span></span>  
 <span data-ttu-id="b93df-340">Selezionare questa opzione per verificare l'ID della versione.</span><span class="sxs-lookup"><span data-stu-id="b93df-340">Select to verify the version ID.</span></span>  
  
 <span data-ttu-id="b93df-341">ID versione</span><span class="sxs-lookup"><span data-stu-id="b93df-341">Version ID</span></span>  
 <span data-ttu-id="b93df-342">Consente di specificare il numero di identificazione della versione.</span><span class="sxs-lookup"><span data-stu-id="b93df-342">Specify the version identification number.</span></span>  
  
 <span data-ttu-id="b93df-343">**Eseguire**</span><span class="sxs-lookup"><span data-stu-id="b93df-343">**Execute**</span></span>  
 <span data-ttu-id="b93df-344">Fare clic su questo pulsante per eseguire il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="b93df-344">Click to run the package.</span></span>  
  
 <span data-ttu-id="b93df-345">**Close**</span><span class="sxs-lookup"><span data-stu-id="b93df-345">**Close**</span></span>  
 <span data-ttu-id="b93df-346">Fare clic su questo pulsante per chiudere la finestra di dialogo **Utilità di esecuzione pacchetti** .</span><span class="sxs-lookup"><span data-stu-id="b93df-346">Click to close the **Execute Package Utility** dialog box.</span></span>  
  
## <a name="command-line-page"></a><span data-ttu-id="b93df-347">Pagina Riga di comando</span><span class="sxs-lookup"><span data-stu-id="b93df-347">Command Line Page</span></span>  
 <span data-ttu-id="b93df-348">Utilizzare il nodo **Riga di comando** della finestra di dialogo **Utilità di esecuzione pacchetti** per modificare la riga di comando generata dalle opzioni create dalle varie finestre di dialogo.</span><span class="sxs-lookup"><span data-stu-id="b93df-348">Use the **Command Line** node of the **Execute Package Utility** dialog box to edit the command line that has been generated by the options created by the various dialogs.</span></span>  
  
### <a name="options"></a><span data-ttu-id="b93df-349">Opzioni</span><span class="sxs-lookup"><span data-stu-id="b93df-349">Options</span></span>  
 <span data-ttu-id="b93df-350">**Ripristina opzioni originali**</span><span class="sxs-lookup"><span data-stu-id="b93df-350">**Restore the original options**</span></span>  
 <span data-ttu-id="b93df-351">Fare clic su questo pulsante per ripristinare lo stato originale della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="b93df-351">Click to restore the command line to its original state.</span></span> <span data-ttu-id="b93df-352">Usare questa opzione se sono state apportate modifiche tramite l'opzione **Modifica riga di comando manualmente** e si vogliono ripristinare le opzioni delle riga di comando originali.</span><span class="sxs-lookup"><span data-stu-id="b93df-352">Use this option if you have made modifications using the **Edit the command line manually** option and want to restore the original command-line options.</span></span>  
  
 <span data-ttu-id="b93df-353">**Modifica riga di comando manualmente**</span><span class="sxs-lookup"><span data-stu-id="b93df-353">**Edit the command line manually**</span></span>  
 <span data-ttu-id="b93df-354">Fare clic per modificare la riga di comando nella casella di testo **Riga di comando** .</span><span class="sxs-lookup"><span data-stu-id="b93df-354">Click to edit the command line in the **Command line** text box.</span></span>  
  
 <span data-ttu-id="b93df-355">**Riga di comando**</span><span class="sxs-lookup"><span data-stu-id="b93df-355">**Command line**</span></span>  
 <span data-ttu-id="b93df-356">Consente di visualizzare la riga di comando corrente,</span><span class="sxs-lookup"><span data-stu-id="b93df-356">Displays the current command line.</span></span> <span data-ttu-id="b93df-357">che risulta modificabile se si seleziona l'opzione per la modifica manuale della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="b93df-357">Editable if you selected the option to edit the command line manually.</span></span>  
  
 <span data-ttu-id="b93df-358">**Eseguire**</span><span class="sxs-lookup"><span data-stu-id="b93df-358">**Execute**</span></span>  
 <span data-ttu-id="b93df-359">Fare clic su questo pulsante per eseguire il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="b93df-359">Click to run the package.</span></span>  
  
 <span data-ttu-id="b93df-360">**Close**</span><span class="sxs-lookup"><span data-stu-id="b93df-360">**Close**</span></span>  
 <span data-ttu-id="b93df-361">Fare clic su questo pulsante per chiudere la finestra di dialogo **Utilità di esecuzione pacchetti** .</span><span class="sxs-lookup"><span data-stu-id="b93df-361">Click to close the **Execute Package Utility** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b93df-362">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b93df-362">See Also</span></span>  
 [<span data-ttu-id="b93df-363">Utilità dtexec</span><span class="sxs-lookup"><span data-stu-id="b93df-363">dtexec Utility</span></span>](dtexec-utility.md)  
  
  
