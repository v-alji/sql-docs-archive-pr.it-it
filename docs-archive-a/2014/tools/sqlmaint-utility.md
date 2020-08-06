---
title: Utilità sqlmaint | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
helpviewer_keywords:
- database maintenance plans [SQL Server]
- sqlmaint utility
- maintaining databases [SQL Server]
- backups [SQL Server], sqlmaint utility
- command prompt utilities [SQL Server], sqlmaint
- maintenance plans [SQL Server], command prompt
- backing up [SQL Server], sqlmaint utility
ms.assetid: 937a9932-4aed-464b-b97a-a5acfe6a50de
author: stevestein
ms.author: sstein
ms.openlocfilehash: 80e60b75305ee91e8b62a201d9c86af301326789
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711215"
---
# <a name="sqlmaint-utility"></a><span data-ttu-id="2a6a8-102">utilità sqlmaint</span><span class="sxs-lookup"><span data-stu-id="2a6a8-102">sqlmaint Utility</span></span>
  <span data-ttu-id="2a6a8-103">L'utilità**sqlmaint** consente di eseguire un set specifico di operazioni di manutenzione in uno o più database.</span><span class="sxs-lookup"><span data-stu-id="2a6a8-103">The**sqlmaint** utility performs a specified set of maintenance operations on one or more databases.</span></span> <span data-ttu-id="2a6a8-104">Usare l'utilità **sqlmaint** per eseguire controlli DBCC, backup di un database e del relativo log delle transazioni, aggiornare statistiche e ricompilare indici.</span><span class="sxs-lookup"><span data-stu-id="2a6a8-104">Use **sqlmaint** to run DBCC checks, back up a database and its transaction log, update statistics, and rebuild indexes.</span></span> <span data-ttu-id="2a6a8-105">Tutte le attività di manutenzione dei database generano un report che può essere inviato a un file di testo, un file HTML o un account di posta elettronica specificato.</span><span class="sxs-lookup"><span data-stu-id="2a6a8-105">All database maintenance activities generate a report that can be sent to a designated text file, HTML file, or e-mail account.</span></span> <span data-ttu-id="2a6a8-106">**sqlmaint** esegue i piani di manutenzione dei database creati con le versioni precedenti di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2a6a8-106">**sqlmaint** executes database maintenance plans created with previous versions of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="2a6a8-107">Per eseguire i piani di manutenzione di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] dal prompt dei comandi, usare l' [utilità dtexec](../integration-services/packages/dtexec-utility.md).</span><span class="sxs-lookup"><span data-stu-id="2a6a8-107">To run [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] maintenance plans from the command prompt, use the [dtexec Utility](../integration-services/packages/dtexec-utility.md).</span></span>  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepNextAvoid](../includes/ssnotedepnextavoid-md.md)] <span data-ttu-id="2a6a8-108">Usare invece la funzionalità di pianificazione della manutenzione di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2a6a8-108">Use [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] maintenance plan feature instead.</span></span> <span data-ttu-id="2a6a8-109">Per altre informazioni sui piani di manutenzione, vedere [Piani di manutenzione](../relational-databases/maintenance-plans/maintenance-plans.md).</span><span class="sxs-lookup"><span data-stu-id="2a6a8-109">For more information on maintenance plans, see [Maintenance Plans](../relational-databases/maintenance-plans/maintenance-plans.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a6a8-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2a6a8-110">Syntax</span></span>  
  
```  
  
      sqlmaint   
[-?] |  
[  
     [-Sserver_name[\instance_name]]  
     [-Ulogin_ID [-Ppassword]]  
     {  
          [-Ddatabase_name | -PlanNamename | -PlanIDguid ]  
          [-Rpttext_file]  
          [-Tooperator_name]  
          [-HtmlRpthtml_file [-DelHtmlRpt <time_period>] ]  
          [-RmUnusedSpacethreshold_percentfree_percent]  
          [-CkDB | -CkDBNoIdx]  
          [-CkAl | -CkAlNoIdx]  
          [-CkCat]  
          [-UpdOptiStatssample_percent]  
          [-RebldIdxfree_space]  
          [-SupportComputedColumn]  
          [-WriteHistory]  
          [  
               {-BkUpDB [backup_path] | -BkUpLog [backup_path] }  
               {-BkUpMedia  
                    {DISK [  
                           [-DelBkUps<time_period>]   
                           [-CrBkSubDir ]   
                           [-UseDefDir ]   
                          ]  
                     | TAPE   
                    }  
               }  
               [-BkUpOnlyIfClean]  
               [-VrfyBackup]  
          ]  
     }  
]  
<time_period> ::=  
number[minutes | hours | days | weeks | months]  
```  
  
## <a name="arguments"></a><span data-ttu-id="2a6a8-111">Argomenti</span><span class="sxs-lookup"><span data-stu-id="2a6a8-111">Arguments</span></span>  
 <span data-ttu-id="2a6a8-112">Separare i parametri e i relativi valori con uno spazio.</span><span class="sxs-lookup"><span data-stu-id="2a6a8-112">The parameters and their values must be separated by a space.</span></span> <span data-ttu-id="2a6a8-113">Inserire ad esempio uno spazio tra **-S** e *nome_server*.</span><span class="sxs-lookup"><span data-stu-id="2a6a8-113">For example, there must be a space between **-S** and *server_name*.</span></span>  
  
 <span data-ttu-id="2a6a8-114">**-?**</span><span class="sxs-lookup"><span data-stu-id="2a6a8-114">**-?**</span></span>  
 <span data-ttu-id="2a6a8-115">Specifica che deve essere restituito il diagramma della sintassi di **sqlmaint** .</span><span class="sxs-lookup"><span data-stu-id="2a6a8-115">Specifies that the syntax diagram for **sqlmaint** be returned.</span></span> <span data-ttu-id="2a6a8-116">Questo parametro deve essere utilizzato da solo.</span><span class="sxs-lookup"><span data-stu-id="2a6a8-116">This parameter must be used alone.</span></span>  
  
 <span data-ttu-id="2a6a8-117">**-S** _server_name_[ **\\** _instance_name_]</span><span class="sxs-lookup"><span data-stu-id="2a6a8-117">**-S** _server_name_[ **\\**_instance_name_]</span></span>  
 <span data-ttu-id="2a6a8-118">Specifica l'istanza di destinazione di [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2a6a8-118">Specifies the target instance of [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="2a6a8-119">Specificare il *nome_server* per connettersi all'istanza predefinita di [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)] su tale server.</span><span class="sxs-lookup"><span data-stu-id="2a6a8-119">Specify *server_name* to connect to the default instance of [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)] on that server.</span></span> <span data-ttu-id="2a6a8-120">Specificare *server_name **_\\_** instance_name* per connettersi a un'istanza denominata di [!INCLUDE[ssDE](../includes/ssde-md.md)] in tale server.</span><span class="sxs-lookup"><span data-stu-id="2a6a8-120">Specify *server_name\*\*_\\_*\* instance_name\* to connect to a named instance of [!INCLUDE[ssDE](../includes/ssde-md.md)] on that server.</span></span> <span data-ttu-id="2a6a8-121">Se non si specifica alcun server, **sqlmaint** si connette all'istanza predefinita di [!INCLUDE[ssDE](../includes/ssde-md.md)] nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="2a6a8-121">If no server is specified, **sqlmaint** connects to the default instance of [!INCLUDE[ssDE](../includes/ssde-md.md)] on the local computer.</span></span>  
  
 <span data-ttu-id="2a6a8-122">**-U** _login_ID_</span><span class="sxs-lookup"><span data-stu-id="2a6a8-122">**-U** _login_ID_</span></span>  
 <span data-ttu-id="2a6a8-123">Specifica l'ID di accesso utilizzato per la connessione al server.</span><span class="sxs-lookup"><span data-stu-id="2a6a8-123">Specifies the login ID to use when connecting to the server.</span></span> <span data-ttu-id="2a6a8-124">Se omesso, **sqlmaint** prova a usare l'autenticazione di Windows [!INCLUDE[msCoName](../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2a6a8-124">If not supplied, **sqlmaint** attempts to use [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows Authentication.</span></span> <span data-ttu-id="2a6a8-125">Se *login_ID* contiene caratteri speciali, il valore deve essere racchiuso tra virgolette doppie ("). In caso contrario, le virgolette doppie sono facoltative.</span><span class="sxs-lookup"><span data-stu-id="2a6a8-125">If *login_ID* contains special characters, it must be enclosed in double quotation marks ("); otherwise, the double quotation marks are optional.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="2a6a8-126">Se possibile, usare l'autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="2a6a8-126">When possible, use Windows Authentication.</span></span>  
  
 <span data-ttu-id="2a6a8-127">**-P** _password_</span><span class="sxs-lookup"><span data-stu-id="2a6a8-127">**-P** _password_</span></span>  
 <span data-ttu-id="2a6a8-128">Specifica la password per l'ID di accesso.</span><span class="sxs-lookup"><span data-stu-id="2a6a8-128">Specifies the password for the login ID.</span></span> <span data-ttu-id="2a6a8-129">È valido solo se viene indicato anche il parametro **-U** .</span><span class="sxs-lookup"><span data-stu-id="2a6a8-129">Only valid if the **-U** parameter is also supplied.</span></span> <span data-ttu-id="2a6a8-130">Se *password* contiene caratteri speciali, il valore deve essere racchiuso tra virgolette doppie. In caso contrario, le virgolette doppie sono facoltative.</span><span class="sxs-lookup"><span data-stu-id="2a6a8-130">If *password* contains special characters, it must be enclosed in double quotation marks; otherwise, the double quotation marks are optional.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="2a6a8-131">La password non è nascosta.</span><span class="sxs-lookup"><span data-stu-id="2a6a8-131">The password is not masked.</span></span> <span data-ttu-id="2a6a8-132">Se possibile, usare l'autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="2a6a8-132">When possible, use Windows Authentication.</span></span>  
  
 <span data-ttu-id="2a6a8-133">**-D** _database_name_</span><span class="sxs-lookup"><span data-stu-id="2a6a8-133">**-D** _database_name_</span></span>  
 <span data-ttu-id="2a6a8-134">Specifica il nome del database nel quale eseguire l'operazione di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="2a6a8-134">Specifies the name of the database in which to perform the maintenance operation.</span></span> <span data-ttu-id="2a6a8-135">Se *database_name* contiene caratteri speciali, il valore deve essere racchiuso tra virgolette doppie. In caso contrario, le virgolette doppie sono facoltative.</span><span class="sxs-lookup"><span data-stu-id="2a6a8-135">If *database_name* contains special characters, it must be enclosed in double quotation marks; otherwise, the double quotation marks are optional.</span></span>  
  
 <span data-ttu-id="2a6a8-136">**-PlanName** _name_</span><span class="sxs-lookup"><span data-stu-id="2a6a8-136">**-PlanName** _name_</span></span>  
 <span data-ttu-id="2a6a8-137">Specifica il nome di un piano di manutenzione del database definito utilizzando Creazione guidata piano di manutenzione database.</span><span class="sxs-lookup"><span data-stu-id="2a6a8-137">Specifies the name of a database maintenance plan defined using the Database Maintenance Plan Wizard.</span></span> <span data-ttu-id="2a6a8-138">L'unica informazione del piano usata da **sqlmaint** è l'elenco dei database.</span><span class="sxs-lookup"><span data-stu-id="2a6a8-138">The only information **sqlmaint** uses from the plan is the list of the databases in the plan.</span></span> <span data-ttu-id="2a6a8-139">Le attività di manutenzione specificate negli altri parametri di **sqlmaint** vengono applicate a questo elenco di database.</span><span class="sxs-lookup"><span data-stu-id="2a6a8-139">Any maintenance activities you specify in the other **sqlmaint** parameters are applied to this list of databases.</span></span>  
  
 <span data-ttu-id="2a6a8-140">**-PlanID** _guid_</span><span class="sxs-lookup"><span data-stu-id="2a6a8-140">**-PlanID** _guid_</span></span>  
 <span data-ttu-id="2a6a8-141">Specifica l'identificatore univoco globale (GUID, Globally Unique Identifier) del piano di manutenzione del database definito utilizzando Creazione guidata piano di manutenzione database.</span><span class="sxs-lookup"><span data-stu-id="2a6a8-141">Specifies the globally unique identifier (GUID) of a database maintenance plan defined using the Database Maintenance Plan Wizard.</span></span> <span data-ttu-id="2a6a8-142">L'unica informazione del piano usata da **sqlmaint** è l'elenco dei database.</span><span class="sxs-lookup"><span data-stu-id="2a6a8-142">The only information **sqlmaint** uses from the plan is the list of the databases in the plan.</span></span> <span data-ttu-id="2a6a8-143">Le attività di manutenzione specificate negli altri parametri di **sqlmaint** vengono applicate a questo elenco di database.</span><span class="sxs-lookup"><span data-stu-id="2a6a8-143">Any maintenance activities you specify in the other **sqlmaint** parameters are applied to this list of databases.</span></span> <span data-ttu-id="2a6a8-144">Questo valore deve corrispondere al valore plan_id di msdb.dbo.sysdbmaintplans.</span><span class="sxs-lookup"><span data-stu-id="2a6a8-144">This must match a plan_id value in msdb.dbo.sysdbmaintplans.</span></span>  
  
 <span data-ttu-id="2a6a8-145">**-Rpt** _text_file_</span><span class="sxs-lookup"><span data-stu-id="2a6a8-145">**-Rpt** _text_file_</span></span>  
 <span data-ttu-id="2a6a8-146">Specifica il percorso completo e il nome del file in cui deve essere generato il report.</span><span class="sxs-lookup"><span data-stu-id="2a6a8-146">Specifies the full path and name of the file into which the report is to be generated.</span></span> <span data-ttu-id="2a6a8-147">Il report viene visualizzato anche sullo schermo.</span><span class="sxs-lookup"><span data-stu-id="2a6a8-147">The report is also generated on the screen.</span></span> <span data-ttu-id="2a6a8-148">Il report gestisce informazioni sulla versione tramite l'aggiunta di una data al nome del file.</span><span class="sxs-lookup"><span data-stu-id="2a6a8-148">The report maintains version information by adding a date to the file name.</span></span> <span data-ttu-id="2a6a8-149">La data viene inserita alla fine del nome file ma prima del punto, in formato _*yyyyMMddhhmm*.</span><span class="sxs-lookup"><span data-stu-id="2a6a8-149">The date is generated as follows: at the end of the file name but before the period, in the form _*yyyyMMddhhmm*.</span></span> <span data-ttu-id="2a6a8-150">*yyyy* = anno, *MM* = mese, *dd* = giorno, *hh* = ora, *mm* = minuto.</span><span class="sxs-lookup"><span data-stu-id="2a6a8-150">*yyyy* = year, *MM* = month, *dd* = day, *hh* = hour, *mm* = minute.</span></span>  
  
 <span data-ttu-id="2a6a8-151">Se si esegue l'utilità alle 10.23</span><span class="sxs-lookup"><span data-stu-id="2a6a8-151">If you run the utility at 10:23 A.M.</span></span> <span data-ttu-id="2a6a8-152">del 1° dicembre 1996 e il valore di *text_file* è:</span><span class="sxs-lookup"><span data-stu-id="2a6a8-152">on December 1, 1996, and this is the *text_file* value:</span></span>  
  
```  
c:\Program Files\Microsoft SQL Server\Mssql\Backup\AdventureWorks2012_maint.rpt  
```  
  
 <span data-ttu-id="2a6a8-153">il nome del file generato è:</span><span class="sxs-lookup"><span data-stu-id="2a6a8-153">The generated file name is:</span></span>  
  
```  
c:\Program Files\Microsoft SQL Server\Mssql\Backup\AdventureWorks2012_maint_199612011023.rpt  
```  
  
 <span data-ttu-id="2a6a8-154">Quando si accede a un server remoto con *sqlmaint* , è necessario specificare il nome UNC (Universal Naming Convention) completo del file per **text_file** .</span><span class="sxs-lookup"><span data-stu-id="2a6a8-154">The full Universal Naming Convention (UNC) file name is required for *text_file* when **sqlmaint** accesses a remote server.</span></span>  
  
 <span data-ttu-id="2a6a8-155">**-Per** _operator_name_</span><span class="sxs-lookup"><span data-stu-id="2a6a8-155">**-To** _operator_name_</span></span>  
 <span data-ttu-id="2a6a8-156">Specifica l'operatore al quale il report generato viene inviato tramite SQL Mail.</span><span class="sxs-lookup"><span data-stu-id="2a6a8-156">Specifies the operator to whom the generated report is sent through SQL Mail.</span></span>  
  
 <span data-ttu-id="2a6a8-157">**-HtmlRpt** _html_file_</span><span class="sxs-lookup"><span data-stu-id="2a6a8-157">**-HtmlRpt** _html_file_</span></span>  
 <span data-ttu-id="2a6a8-158">Specifica il percorso completo e il nome del file in cui generare il report HTML.</span><span class="sxs-lookup"><span data-stu-id="2a6a8-158">Specifies the full path and name of the file into which an HTML report is to be generated.</span></span> <span data-ttu-id="2a6a8-159">**sqlmaint** aggiunge al nome file una stringa nel formato _*yyyyMMddhhmm* , in modo analogo a quanto avviene per il parametro **-Rpt** .</span><span class="sxs-lookup"><span data-stu-id="2a6a8-159">**sqlmaint** generates the file name by appending a string of the format _*yyyyMMddhhmm* to the file name, just as it does for the **-Rpt** parameter.</span></span>  
  
 <span data-ttu-id="2a6a8-160">Quando si accede a un server remoto con *sqlmaint* , è necessario specificare il nome UNC completo del file per **html_file** .</span><span class="sxs-lookup"><span data-stu-id="2a6a8-160">The full UNC file name is required for *html_file* when **sqlmaint** accesses a remote server.</span></span>  
  
 <span data-ttu-id="2a6a8-161">**-DelHtmlRpt** \<*time_period*></span><span class="sxs-lookup"><span data-stu-id="2a6a8-161">**-DelHtmlRpt** \<*time_period*></span></span>  
 <span data-ttu-id="2a6a8-162">Specifica che è necessario eliminare dalla directory dei report tutti i report HTML se l'intervallo di tempo dopo la creazione del file del report supera \<*time_period*>.</span><span class="sxs-lookup"><span data-stu-id="2a6a8-162">Specifies that any HTML report in the report directory be deleted if the time interval after the creation of the report file exceeds \<*time_period*>.</span></span> <span data-ttu-id="2a6a8-163">**-DelHtmlRpt** cerca i file con nome corrispondente al modello generato dal parametro *html_file*.</span><span class="sxs-lookup"><span data-stu-id="2a6a8-163">**-DelHtmlRpt** looks for files whose name fits the pattern generated from the *html_file* parameter.</span></span> <span data-ttu-id="2a6a8-164">Se *html_file* è c:\Programmi\Microsoft SQL Server\Mssql\Backup\AdventureWorks2012_maint.htm, **-DelHtmlRpt** fa sì che **sqlmaint** elimini tutti i file con nome corrispondente al modello C:\Programmi\Microsoft SQL Server\Mssql\Backup\AdventureWorks2012_maint\*.htm e successivi al valore specificato per \<*time_period*>.</span><span class="sxs-lookup"><span data-stu-id="2a6a8-164">If *html_file* is c:\Program Files\Microsoft SQL Server\Mssql\Backup\AdventureWorks2012_maint.htm, then **-DelHtmlRpt** causes **sqlmaint** to delete any files whose names match the pattern C:\Program Files\Microsoft SQL Server\Mssql\Backup\AdventureWorks2012_maint\*.htm and that are older than the specified \<*time_period*>.</span></span>  
  
 <span data-ttu-id="2a6a8-165">**-RmUnusedSpace** _threshold_percent free_percent_</span><span class="sxs-lookup"><span data-stu-id="2a6a8-165">**-RmUnusedSpace** _threshold_percent free_percent_</span></span>  
 <span data-ttu-id="2a6a8-166">Specifica la rimozione dello spazio inutilizzato dal database indicato in **-D**.</span><span class="sxs-lookup"><span data-stu-id="2a6a8-166">Specifies that unused space be removed from the database specified in **-D**.</span></span> <span data-ttu-id="2a6a8-167">Questa opzione è utile solo nel caso di database per i quali è stato impostato l'aumento automatico delle dimensioni.</span><span class="sxs-lookup"><span data-stu-id="2a6a8-167">This option is only useful for databases that are defined to grow automatically.</span></span> <span data-ttu-id="2a6a8-168">*Threshold_percent* specifica le dimensioni, in megabyte, che il database deve raggiungere prima che **sqlmaint** rimuova lo spazio inutilizzato.</span><span class="sxs-lookup"><span data-stu-id="2a6a8-168">*Threshold_percent* specifies in megabytes the size that the database must reach before **sqlmaint** attempts to remove unused data space.</span></span> <span data-ttu-id="2a6a8-169">Se le dimensioni del database sono inferiori a *threshold_percent*, non viene eseguita alcuna azione.</span><span class="sxs-lookup"><span data-stu-id="2a6a8-169">If the database is smaller than the *threshold_percent*, no action is taken.</span></span> <span data-ttu-id="2a6a8-170">*Free_percent* specifica la quantità di spazio inutilizzato che deve rimanere nel database, in termini di percentuale delle dimensioni finali del database.</span><span class="sxs-lookup"><span data-stu-id="2a6a8-170">*Free_percent* specifies how much unused space must remain in the database, specified as a percentage of the final size of the database.</span></span> <span data-ttu-id="2a6a8-171">Se ad esempio un database di 200 MB contiene 100 MB di dati e si specifica 10 per *free_percent* , le dimensioni finali del database saranno di 110 MB.</span><span class="sxs-lookup"><span data-stu-id="2a6a8-171">For example, if a 200-MB database contains 100 MB of data, specifying 10 for *free_percent* results in the final database size being 110 MB.</span></span> <span data-ttu-id="2a6a8-172">Le dimensioni del database non vengono aumentate se sono inferiori a *free_percent* più la quantità di dati del database.</span><span class="sxs-lookup"><span data-stu-id="2a6a8-172">Note that a database is not expanded if it is smaller than *free_percent* plus the amount of data in the database.</span></span> <span data-ttu-id="2a6a8-173">Se ad esempio un database di 108 MB contiene 100 MB di dati e si specifica 10 per *free_percent* , il database non viene esteso a 110 MB, ma resta di 108 MB.</span><span class="sxs-lookup"><span data-stu-id="2a6a8-173">For example, if a 108-MB database has 100 MB of data, specifying 10 for *free_percent* does not expand the database to 110 MB; it remains at 108 MB.</span></span>  
  
 <span data-ttu-id="2a6a8-174">**-CkDB** |  **-CkDBNoIdx**</span><span class="sxs-lookup"><span data-stu-id="2a6a8-174">**-CkDB** | **-CkDBNoIdx**</span></span>  
 <span data-ttu-id="2a6a8-175">Specifica l'esecuzione di un'istruzione DBCC CHECKDB o DBCC CHECKDB con l'opzione NOINDEX nel database indicato in **-D**.</span><span class="sxs-lookup"><span data-stu-id="2a6a8-175">Specifies that a DBCC CHECKDB statement or a DBCC CHECKDB statement with the NOINDEX option be run in the database specified in **-D**.</span></span> <span data-ttu-id="2a6a8-176">Per ulteriori informazioni, vedere DBCC CHECKDB.</span><span class="sxs-lookup"><span data-stu-id="2a6a8-176">For more information, see DBCC CHECKDB.</span></span>  
  
 <span data-ttu-id="2a6a8-177">Se durante l'esecuzione di *sqlmaint* il database è in uso, viene scritto un avviso in **text_file** .</span><span class="sxs-lookup"><span data-stu-id="2a6a8-177">A warning is written to *text_file* if the database is in use when **sqlmaint** runs.</span></span>  
  
 <span data-ttu-id="2a6a8-178">**-CkAl** |  **-CkAlNoIdx**</span><span class="sxs-lookup"><span data-stu-id="2a6a8-178">**-CkAl** | **-CkAlNoIdx**</span></span>  
 <span data-ttu-id="2a6a8-179">Specifica l'esecuzione di un'istruzione DBCC CHECKALLOC con l'opzione NOINDEX nel database indicato in **-D**.</span><span class="sxs-lookup"><span data-stu-id="2a6a8-179">Specifies that a DBCC CHECKALLOC statement with the NOINDEX option be run in the database specified in **-D**.</span></span> <span data-ttu-id="2a6a8-180">Per altre informazioni, vedere [DBCC CHECKALLOC &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checkalloc-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2a6a8-180">For more information, see [DBCC CHECKALLOC &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checkalloc-transact-sql).</span></span>  
  
 <span data-ttu-id="2a6a8-181">**-CkCat**</span><span class="sxs-lookup"><span data-stu-id="2a6a8-181">**-CkCat**</span></span>  
 <span data-ttu-id="2a6a8-182">Specifica l'esecuzione di un'istruzione DBCC CHECKCATALOG (Transact-SQL) nel database indicato in **-D**.</span><span class="sxs-lookup"><span data-stu-id="2a6a8-182">Specifies that a DBCC CHECKCATALOG (Transact-SQL) statement be run in the database specified in **-D**.</span></span> <span data-ttu-id="2a6a8-183">Per altre informazioni, vedere [DBCC CHECKCATALOG &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checkcatalog-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2a6a8-183">For more information, see [DBCC CHECKCATALOG &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checkcatalog-transact-sql).</span></span>  
  
 <span data-ttu-id="2a6a8-184">**-UpdOptiStats** _sample_percent_</span><span class="sxs-lookup"><span data-stu-id="2a6a8-184">**-UpdOptiStats** _sample_percent_</span></span>  
 <span data-ttu-id="2a6a8-185">Specifica l'esecuzione dell'istruzione seguente in tutte le tabelle del database:</span><span class="sxs-lookup"><span data-stu-id="2a6a8-185">Specifies that the following statement be run on each table in the database:</span></span>  
  
```  
UPDATE STATISTICS table WITH SAMPLE sample_percent PERCENT;  
```  
  
 <span data-ttu-id="2a6a8-186">Se le tabelle contengono colonne calcolate e si usa **-UpdOptiStats** , è anche necessario specificare l'argomento **-SupportedComputedColumn**.</span><span class="sxs-lookup"><span data-stu-id="2a6a8-186">If the tables contain computed columns, you must also specify the **-SupportedComputedColumn** argument when you use **-UpdOptiStats**.</span></span>  
  
 <span data-ttu-id="2a6a8-187">Per altre informazioni, vedere [UPDATE STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/statements/update-statistics-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2a6a8-187">For more information, see [UPDATE STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/statements/update-statistics-transact-sql).</span></span>  
  
 <span data-ttu-id="2a6a8-188">**-RebldIdx** _free_space_</span><span class="sxs-lookup"><span data-stu-id="2a6a8-188">**-RebldIdx** _free_space_</span></span>  
 <span data-ttu-id="2a6a8-189">Specifica che gli indici delle tabelle nel database di destinazione devono essere ricompilati usando il valore percentuale *free_space* come valore inverso del fattore di riempimento.</span><span class="sxs-lookup"><span data-stu-id="2a6a8-189">Specifies that indexes on tables in the target database should be rebuilt by using the *free_space* percent value as the inverse of the fill factor.</span></span> <span data-ttu-id="2a6a8-190">Ad esempio, se la percentuale di *free_space* è 30, viene usato un fattore di riempimento pari a 70.</span><span class="sxs-lookup"><span data-stu-id="2a6a8-190">For example, if *free_space* percentage is 30, then the fill factor used is 70.</span></span> <span data-ttu-id="2a6a8-191">Se si specifica un valore percentuale *free_space* pari a 100, gli indici vengono ricompilati con il valore del fattore di riempimento originale.</span><span class="sxs-lookup"><span data-stu-id="2a6a8-191">If a *free_space* percentage value of 100 is specified, then the indexes are rebuilt with the original fill factor value.</span></span>  
  
 <span data-ttu-id="2a6a8-192">Se gli indici si trovano in colonne calcolate e si usa **-RebldIdx** , è anche necessario specificare l'argomento **-SupportComputedColumn**.</span><span class="sxs-lookup"><span data-stu-id="2a6a8-192">If the indexes are on computed columns, you must also specify the **-SupportComputedColumn** argument when you use **-RebldIdx**.</span></span>  
  
 <span data-ttu-id="2a6a8-193">**-RebldIdx**</span><span class="sxs-lookup"><span data-stu-id="2a6a8-193">**-SupportComputedColumn**</span></span>  
 <span data-ttu-id="2a6a8-194">Specificare questo argomento per eseguire i comandi di manutenzione DBCC sulle colonne calcolate usando **sqlmaint** .</span><span class="sxs-lookup"><span data-stu-id="2a6a8-194">Must be specified to run DBCC maintenance commands with **sqlmaint** on computed columns.</span></span>  
  
 <span data-ttu-id="2a6a8-195">**-WriteHistory**</span><span class="sxs-lookup"><span data-stu-id="2a6a8-195">**-WriteHistory**</span></span>  
 <span data-ttu-id="2a6a8-196">Specifica l'aggiunta di una voce in msdb.dbo.sysdbmaintplan_history per ogni azione di manutenzione eseguita da **sqlmaint**.</span><span class="sxs-lookup"><span data-stu-id="2a6a8-196">Specifies that an entry be made in msdb.dbo.sysdbmaintplan_history for each maintenance action performed by **sqlmaint**.</span></span> <span data-ttu-id="2a6a8-197">Se si specifica **-PlanName** o **-PlanID** , le voci in sysdbmaintplan_history usano l'ID del piano specificato.</span><span class="sxs-lookup"><span data-stu-id="2a6a8-197">If **-PlanName** or **-PlanID** is specified, the entries in sysdbmaintplan_history use the ID of the specified plan.</span></span> <span data-ttu-id="2a6a8-198">Se si specifica **-D** , l'ID del piano delle voci di sysdbmaintplan_history viene rappresentato da zeri.</span><span class="sxs-lookup"><span data-stu-id="2a6a8-198">If **-D** is specified, the entries in sysdbmaintplan_history are made with zeroes for the plan ID.</span></span>  
  
 <span data-ttu-id="2a6a8-199">**-BkUpDB** [ *backup_path*] |  **-BkUpLog** [ *backup_path* ]</span><span class="sxs-lookup"><span data-stu-id="2a6a8-199">**-BkUpDB** [ *backup_path*] |  **-BkUpLog** [ *backup_path* ]</span></span>  
 <span data-ttu-id="2a6a8-200">Specifica un'azione di backup.</span><span class="sxs-lookup"><span data-stu-id="2a6a8-200">Specifies a backup action.</span></span> <span data-ttu-id="2a6a8-201">**-BkUpDb** esegue il backup di tutto il database.</span><span class="sxs-lookup"><span data-stu-id="2a6a8-201">**-BkUpDb** backs up the entire database.</span></span> <span data-ttu-id="2a6a8-202">**-BkUpLog** esegue solo il backup del log delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="2a6a8-202">**-BkUpLog** backs up only the transaction log.</span></span>  
  
 <span data-ttu-id="2a6a8-203">*backup_path* specifica la directory di backup.</span><span class="sxs-lookup"><span data-stu-id="2a6a8-203">*backup_path* specifies the directory for the backup.</span></span> <span data-ttu-id="2a6a8-204">*backup_path* non è necessario se si specifica **-UseDefDir** e, se vengono specificati entrambi, **-UseDefDir** è prioritario.</span><span class="sxs-lookup"><span data-stu-id="2a6a8-204">*backup_path* is not needed if **-UseDefDir** is also specified, and is overridden by **-UseDefDir** if both are specified.</span></span> <span data-ttu-id="2a6a8-205">È possibile memorizzare il backup in una directory o usare l'indirizzo di un dispositivo nastro, ad esempio \\\\.\TAPE0.</span><span class="sxs-lookup"><span data-stu-id="2a6a8-205">The backup can be placed in a directory or a tape device address (for example, \\\\.\TAPE0).</span></span> <span data-ttu-id="2a6a8-206">Il nome del file per il backup di un database viene generato automaticamente nel formato seguente:</span><span class="sxs-lookup"><span data-stu-id="2a6a8-206">The file name for a database backup is generated automatically as follows:</span></span>  
  
```  
dbname_db_yyyyMMddhhmm.BAK  
  
```  
  
 <span data-ttu-id="2a6a8-207">dove</span><span class="sxs-lookup"><span data-stu-id="2a6a8-207">where</span></span>  
  
-   <span data-ttu-id="2a6a8-208">*dbname* è il nome del database del quale eseguire il backup.</span><span class="sxs-lookup"><span data-stu-id="2a6a8-208">*dbname* is the name of the database being backed up.</span></span>  
  
-   <span data-ttu-id="2a6a8-209">*yyyyMMddhhmm* rappresenta la data e l'ora dell'operazione di backup in cui *yyyy* = anno, *MM* = mese, *dd* = giorno, *hh* = ora e *mm* = minuto.</span><span class="sxs-lookup"><span data-stu-id="2a6a8-209">*yyyyMMddhhmm* is the time of the backup operation with *yyyy* = year, *MM* = month, *dd* = day, *hh* = hour, and *mm* = minute.</span></span>  
  
 <span data-ttu-id="2a6a8-210">Il nome del file per il backup del log delle transazioni viene generato automaticamente nel formato seguente:</span><span class="sxs-lookup"><span data-stu-id="2a6a8-210">The file name for a transaction backup is generated automatically with a similar format:</span></span>  
  
```  
dbname_log_yyyymmddhhmm.BAK  
  
```  
  
 <span data-ttu-id="2a6a8-211">Se si usa il parametro **-BkUpDB** è anche necessario specificare il supporto con il parametro **-BkUpMedia** .</span><span class="sxs-lookup"><span data-stu-id="2a6a8-211">If you use the **-BkUpDB** parameter, you must also specify the media by using the **-BkUpMedia** parameter.</span></span>  
  
 <span data-ttu-id="2a6a8-212">**-BkUpMedia**</span><span class="sxs-lookup"><span data-stu-id="2a6a8-212">**-BkUpMedia**</span></span>  
 <span data-ttu-id="2a6a8-213">Specifica il tipo di supporto per il backup, ovvero DISK o TAPE.</span><span class="sxs-lookup"><span data-stu-id="2a6a8-213">Specifies the media type of the backup, either DISK or TAPE.</span></span>  
  
 <span data-ttu-id="2a6a8-214">**DISK**</span><span class="sxs-lookup"><span data-stu-id="2a6a8-214">**DISK**</span></span>  
 <span data-ttu-id="2a6a8-215">Indica che il supporto di backup è un disco.</span><span class="sxs-lookup"><span data-stu-id="2a6a8-215">Specifies that the backup medium is disk.</span></span>  
  
 <span data-ttu-id="2a6a8-216">**-DelBkUps**\< *time_period* ></span><span class="sxs-lookup"><span data-stu-id="2a6a8-216">**-DelBkUps**\< *time_period* ></span></span>  
 <span data-ttu-id="2a6a8-217">Per i backup su disco, specifica che è necessario eliminare dalla directory di backup tutti i file di backup se l'intervallo di tempo dopo la creazione del backup supera \<*time_period*>.</span><span class="sxs-lookup"><span data-stu-id="2a6a8-217">For disk backups, specifies that any backup file in the backup directory be deleted if the time interval after the creation of the backup exceeds the \<*time_period*>.</span></span>  
  
 <span data-ttu-id="2a6a8-218">**-CrBkSubDir**</span><span class="sxs-lookup"><span data-stu-id="2a6a8-218">**-CrBkSubDir**</span></span>  
 <span data-ttu-id="2a6a8-219">Per i backup su disco, specifica la creazione di una sottodirectory nella directory [*backup_path*] o nella directory di backup predefinita, se si usa anche **-UseDefDir** .</span><span class="sxs-lookup"><span data-stu-id="2a6a8-219">For disk backups, specifies that a subdirectory be created in the [*backup_path*] directory or in the default backup directory if **-UseDefDir** is also specified.</span></span> <span data-ttu-id="2a6a8-220">Il nome della sottodirectory viene generato in base al nome del database specificato in **-D**.</span><span class="sxs-lookup"><span data-stu-id="2a6a8-220">The name of the subdirectory is generated from the database name specified in **-D**.</span></span> <span data-ttu-id="2a6a8-221">**-CrBkSubDir** consente di memorizzare in modo semplice tutti i backup di database diversi in sottodirectory separate senza dover modificare il parametro *backup_path* .</span><span class="sxs-lookup"><span data-stu-id="2a6a8-221">**-CrBkSubDir** offers an easy way to put all the backups for different databases into separate subdirectories without having to change the *backup_path* parameter.</span></span>  
  
 <span data-ttu-id="2a6a8-222">**-UseDefDir**</span><span class="sxs-lookup"><span data-stu-id="2a6a8-222">**-UseDefDir**</span></span>  
 <span data-ttu-id="2a6a8-223">Per i backup su disco, specifica la creazione del file di backup nella directory di backup predefinita.</span><span class="sxs-lookup"><span data-stu-id="2a6a8-223">For disk backups, specifies that the backup file be created in the default backup directory.</span></span> <span data-ttu-id="2a6a8-224">Se sono specificati entrambi,**UseDefDir** è prioritario rispetto a *backup_path* .</span><span class="sxs-lookup"><span data-stu-id="2a6a8-224">**UseDefDir** overrides *backup_path* if both are specified.</span></span> <span data-ttu-id="2a6a8-225">Nel caso di un'installazione predefinita di [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], la directory di backup predefinita è C:\Programmi\Microsoft SQL Server\MSSQL10_50.MSSQLSERVER\MSSQL\Backup.</span><span class="sxs-lookup"><span data-stu-id="2a6a8-225">With a default [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] setup, the default backup directory is C:\Program Files\Microsoft SQL Server\MSSQL10_50.MSSQLSERVER\MSSQL\Backup.</span></span>  
  
 <span data-ttu-id="2a6a8-226">**TAPE**</span><span class="sxs-lookup"><span data-stu-id="2a6a8-226">**TAPE**</span></span>  
 <span data-ttu-id="2a6a8-227">Indica che il supporto di backup è un nastro.</span><span class="sxs-lookup"><span data-stu-id="2a6a8-227">Specifies that the backup medium is tape.</span></span>  
  
 <span data-ttu-id="2a6a8-228">**-BkUpOnlyIfClean**</span><span class="sxs-lookup"><span data-stu-id="2a6a8-228">**-BkUpOnlyIfClean**</span></span>  
 <span data-ttu-id="2a6a8-229">Specifica che il backup viene eseguito solo se i controlli **-Ck** specificati non rilevano problemi con i dati.</span><span class="sxs-lookup"><span data-stu-id="2a6a8-229">Specifies that the backup occur only if any specified **-Ck** checks did not find problems with the data.</span></span> <span data-ttu-id="2a6a8-230">Le azioni di manutenzione vengono eseguite nella stessa sequenza in cui sono indicate nel prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="2a6a8-230">Maintenance actions run in the same sequence as they appear in the command prompt.</span></span> <span data-ttu-id="2a6a8-231">Specificare i parametri **-CkDB**, **-CkDBNoIdx**, **-CkAl**, **-CkAlNoIdx**, **-CkTxtAl**o **-CkCat** prima dei parametri **-BkUpDB**/ **-BkUpLog** se si intende specificare anche **- BkUpOnlyIfClean**, oppure il backup verrà eseguito a prescindere dal fatto che il controllo abbia segnalato problemi.</span><span class="sxs-lookup"><span data-stu-id="2a6a8-231">Specify the parameters **-CkDB**, **-CkDBNoIdx**, **-CkAl**, **-CkAlNoIdx**, **-CkTxtAl**, or **-CkCat** before the **-BkUpDB**/**-BkUpLog** parameter(s) if you are also going to specify **-BkUpOnlyIfClean**, or the backup occurs whether or not the check reports problems.</span></span>  
  
 <span data-ttu-id="2a6a8-232">**-VrfyBackup**</span><span class="sxs-lookup"><span data-stu-id="2a6a8-232">**-VrfyBackup**</span></span>  
 <span data-ttu-id="2a6a8-233">Specifica l'esecuzione dell'istruzione RESTORE VERIFYONLY al termine del backup.</span><span class="sxs-lookup"><span data-stu-id="2a6a8-233">Specifies that RESTORE VERIFYONLY be run on the backup when it completes.</span></span>  
  
 <span data-ttu-id="2a6a8-234">*number*[**minutes**| **hours**| **day**| **weeks**| **months**]</span><span class="sxs-lookup"><span data-stu-id="2a6a8-234">*number*[**minutes**| **hours**| **day**| **weeks**| **months**]</span></span>  
 <span data-ttu-id="2a6a8-235">Specifica l'intervallo di tempo trascorso il quale un report o un file di backup può essere eliminato.</span><span class="sxs-lookup"><span data-stu-id="2a6a8-235">Specifies the time interval used to determine if a report or backup file is old enough to be deleted.</span></span> <span data-ttu-id="2a6a8-236">*number* è un numero intero seguito (senza spazi) da un'unità di tempo,</span><span class="sxs-lookup"><span data-stu-id="2a6a8-236">*number* is an integer followed (without a space) by a unit of time.</span></span> <span data-ttu-id="2a6a8-237">ad esempio:</span><span class="sxs-lookup"><span data-stu-id="2a6a8-237">Valid examples:</span></span>  
  
-   <span data-ttu-id="2a6a8-238">**12weeks**</span><span class="sxs-lookup"><span data-stu-id="2a6a8-238">**12weeks**</span></span>  
  
-   <span data-ttu-id="2a6a8-239">**3months**</span><span class="sxs-lookup"><span data-stu-id="2a6a8-239">**3months**</span></span>  
  
-   <span data-ttu-id="2a6a8-240">**15days**</span><span class="sxs-lookup"><span data-stu-id="2a6a8-240">**15days**</span></span>  
  
 <span data-ttu-id="2a6a8-241">Se si specifica solo *number* , l'unità di tempo predefinita è **weeks**.</span><span class="sxs-lookup"><span data-stu-id="2a6a8-241">If only *number* is specified, the default date part is **weeks**.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2a6a8-242">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="2a6a8-242">Remarks</span></span>  
 <span data-ttu-id="2a6a8-243">L'utilità **sqlmaint** consente di eseguire operazioni di manutenzione in uno o più database.</span><span class="sxs-lookup"><span data-stu-id="2a6a8-243">The **sqlmaint** utility performs maintenance operations on one or more databases.</span></span> <span data-ttu-id="2a6a8-244">Se è specificato **-D** , le operazioni indicate nelle altre opzioni vengono eseguite solo nel database specificato.</span><span class="sxs-lookup"><span data-stu-id="2a6a8-244">If **-D** is specified, the operations specified in the remaining switches are performed only on the specified database.</span></span> <span data-ttu-id="2a6a8-245">Se si specifica **-PlanName** o **-PlanID** , **sqlmaint** recupera dal piano di manutenzione solo l'elenco dei database.</span><span class="sxs-lookup"><span data-stu-id="2a6a8-245">If **-PlanName** or **-PlanID** are specified, the only information **sqlmaint** retrieves from the specified maintenance plan is the list of databases in the plan.</span></span> <span data-ttu-id="2a6a8-246">Tutte le operazioni specificate negli altri parametri di **sqlmaint** vengono eseguite in tutti i database dell'elenco ottenuto dal piano.</span><span class="sxs-lookup"><span data-stu-id="2a6a8-246">All operations specified in the remaining **sqlmaint** parameters are applied against each database in the list obtained from the plan.</span></span> <span data-ttu-id="2a6a8-247">L'utilità **sqlmaint** di per sé non esegue nessuna delle attività di manutenzione definite nel piano.</span><span class="sxs-lookup"><span data-stu-id="2a6a8-247">The **sqlmaint** utility does not apply any of the maintenance activities defined in the plan itself.</span></span>  
  
 <span data-ttu-id="2a6a8-248">Se l'esecuzione riesce, l'utilità **sqlmaint** restituisce 0, in caso contrario 1.</span><span class="sxs-lookup"><span data-stu-id="2a6a8-248">The **sqlmaint** utility returns 0 if it runs successfully or 1 if it fails.</span></span> <span data-ttu-id="2a6a8-249">L'esito negativo viene segnalato se:</span><span class="sxs-lookup"><span data-stu-id="2a6a8-249">Failure is reported:</span></span>  
  
-   <span data-ttu-id="2a6a8-250">Una delle azioni di manutenzione ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="2a6a8-250">If any of the maintenance actions fail.</span></span>  
  
-   <span data-ttu-id="2a6a8-251">**-CkDB**, **-CkDBNoIdx**, **-CkAl**, **-CkAlNoIdx**, **-CkTxtAl**o **-CkCat** rileva problemi con i dati.</span><span class="sxs-lookup"><span data-stu-id="2a6a8-251">If **-CkDB**, **-CkDBNoIdx**, **-CkAl**, **-CkAlNoIdx**, **-CkTxtAl**, or **-CkCat** checks find problems with the data.</span></span>  
  
-   <span data-ttu-id="2a6a8-252">Si verifica un errore generale.</span><span class="sxs-lookup"><span data-stu-id="2a6a8-252">If a general failure is encountered.</span></span>  
  
## <a name="permissions"></a><span data-ttu-id="2a6a8-253">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="2a6a8-253">Permissions</span></span>  
 <span data-ttu-id="2a6a8-254">L'utilità **sqlmaint** può essere eseguita da qualsiasi utente di Windows che abbia l'autorizzazione **Lettura/esecuzione** su `sqlmaint.exe`, archiviato nella cartella `x:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER1\MSSQL\Binn` per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="2a6a8-254">The **sqlmaint** utility can be executed by any Windows user with **Read and Execute** permission on `sqlmaint.exe`, which by default is stored in the `x:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER1\MSSQL\Binn` folder.</span></span> <span data-ttu-id="2a6a8-255">L'account di accesso di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] specificato con **-login_ID** deve avere anche le autorizzazioni di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] necessarie per eseguire l'operazione specificata.</span><span class="sxs-lookup"><span data-stu-id="2a6a8-255">Additionally, the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] login specified with **-login_ID** must have the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] permissions required to perform the specified action.</span></span> <span data-ttu-id="2a6a8-256">Se la connessione a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] utilizza l'autenticazione di Windows, l'account di accesso di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] sul quale viene eseguito il mapping all'utente di Windows autenticato deve disporre delle autorizzazioni [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] necessarie per eseguire l'operazione specificata.</span><span class="sxs-lookup"><span data-stu-id="2a6a8-256">If the connection to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] uses Windows Authentication, the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] login mapped to the authenticated Windows user must have the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] permissions required to perform the specified action.</span></span>  
  
 <span data-ttu-id="2a6a8-257">Ad esempio, per usare **-BkUpDB** è necessaria l'autorizzazione per eseguire l'istruzione BACKUP,</span><span class="sxs-lookup"><span data-stu-id="2a6a8-257">For example, using the **-BkUpDB** requires permission to execute the BACKUP statement.</span></span> <span data-ttu-id="2a6a8-258">mentre l'uso dell'argomento **-UpdOptiStats** richiede l'autorizzazione per eseguire l'istruzione UPDATE STATISTICS.</span><span class="sxs-lookup"><span data-stu-id="2a6a8-258">And using the **-UpdOptiStats** argument requires permission to execute the UPDATE STATISTICS statement.</span></span> <span data-ttu-id="2a6a8-259">Per ulteriori informazioni, vedere le sezioni dedicate alle autorizzazioni nei relativi argomenti della documentazione online.</span><span class="sxs-lookup"><span data-stu-id="2a6a8-259">For more information, see the "Permissions" sections of the corresponding topics in Books Online.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="2a6a8-260">Esempi</span><span class="sxs-lookup"><span data-stu-id="2a6a8-260">Examples</span></span>  
  
### <a name="a-performing-dbcc-checks-on-a-database"></a><span data-ttu-id="2a6a8-261">R.</span><span class="sxs-lookup"><span data-stu-id="2a6a8-261">A.</span></span> <span data-ttu-id="2a6a8-262">Esecuzione di controlli DBCC in un database</span><span class="sxs-lookup"><span data-stu-id="2a6a8-262">Performing DBCC checks on a database</span></span>  
  
```  
sqlmaint -S MyServer -D AdventureWorks2012 -CkDB -CkAl -CkCat -Rpt C:\MyReports\AdvWks_chk.rpt  
```  
  
### <a name="b-updating-statistics-using-a-15-sample-in-all-databases-in-a-plan-also-shrink-any-of-the-database-that-have-reached-110-mb-to-having-only-10-free-space"></a><span data-ttu-id="2a6a8-263">B.</span><span class="sxs-lookup"><span data-stu-id="2a6a8-263">B.</span></span> <span data-ttu-id="2a6a8-264">Aggiornamento delle statistiche utilizzando un campione del 15% per tutti i database di un piano</span><span class="sxs-lookup"><span data-stu-id="2a6a8-264">Updating statistics using a 15% sample in all databases in a plan.</span></span> <span data-ttu-id="2a6a8-265">e compattazione dei database che hanno raggiunto dimensioni di 110 MB in modo che lo spazio libero sia pari al 10%</span><span class="sxs-lookup"><span data-stu-id="2a6a8-265">Also, shrink any of the database that have reached 110 MB to having only 10% free space</span></span>  
  
```  
sqlmaint -S MyServer -PlanName MyUserDBPlan -UpdOptiStats 15 -RmUnusedSpace 110 10  
```  
  
### <a name="c-backing-up-all-the-databases-in-a-plan-to-their-individual-subdirectories-in-the-default-xprogram-filesmicrosoft-sql-servermssql12mssqlservermssqlbackup-directory-also-delete-any-backups-older-than-2-weeks"></a><span data-ttu-id="2a6a8-266">C.</span><span class="sxs-lookup"><span data-stu-id="2a6a8-266">C.</span></span> <span data-ttu-id="2a6a8-267">Backup di tutti i database di un piano nelle singole sottodirectory della directory predefinita x:\Programmi\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Backup directory.</span><span class="sxs-lookup"><span data-stu-id="2a6a8-267">Backing up all the databases in a plan to their individual subdirectories in the default x:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Backup directory.</span></span> <span data-ttu-id="2a6a8-268">ed eliminazione delle copie di backup risalenti a più di due settimane prima.</span><span class="sxs-lookup"><span data-stu-id="2a6a8-268">Also, delete any backups older than 2 weeks</span></span>  
  
```  
sqlmaint -S MyServer -PlanName MyUserDBPlan -BkUpDB -BkUpMedia DISK -UseDefDir -CrBkSubDir -DelBkUps 2weeks  
```  
  
### <a name="d-backing-up-a-database-to-the-default-xprogram-filesmicrosoft-sql-servermssql12mssqlservermssqlbackup-directory"></a><span data-ttu-id="2a6a8-269">D.</span><span class="sxs-lookup"><span data-stu-id="2a6a8-269">D.</span></span> <span data-ttu-id="2a6a8-270">Esecuzione del backup di un database nel valore predefinito X:\Programmi\Microsoft Files\Microsoft SQL Server\MSSQL12. Directory MSSQLSERVER\MSSQL\Backup. </span><span class="sxs-lookup"><span data-stu-id="2a6a8-270">Backing up a database to the default x:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Backup directory.</span></span>\  
  
```  
sqlmaint -S MyServer -BkUpDB -BkUpMedia DISK -UseDefDir  
```  
  
## <a name="see-also"></a><span data-ttu-id="2a6a8-271">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2a6a8-271">See Also</span></span>  
 <span data-ttu-id="2a6a8-272">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2a6a8-272">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 [<span data-ttu-id="2a6a8-273">UPDATE STATISTICS &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="2a6a8-273">UPDATE STATISTICS &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/update-statistics-transact-sql)  
  
  
