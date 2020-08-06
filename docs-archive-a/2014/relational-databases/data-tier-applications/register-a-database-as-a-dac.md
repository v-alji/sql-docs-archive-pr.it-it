---
title: Registrare un database come applicazione livello dati | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.registerdacwizard.registerdac.f1
- sql12.swb.registerdacwizard.summary.f1
- sql12.swb.registerdacwizard.introduction.f1
- sql12.swb.registerdacwizard.setproperties.f1
helpviewer_keywords:
- wizard [DAC], register
- How to [DAC], register
- register DAC
- data-tier application [SQL Server], register
ms.assetid: 08e52aa6-12f3-41dd-a793-14b99a083fd5
author: stevestein
ms.author: sstein
ms.openlocfilehash: c4e8061362d013dbfbd6cbaba47d0f2cb4d8e83b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637891"
---
# <a name="register-a-database-as-a-dac"></a><span data-ttu-id="ee16a-102">Registrare un database come applicazione livello dati</span><span class="sxs-lookup"><span data-stu-id="ee16a-102">Register a Database As a DAC</span></span>
  <span data-ttu-id="ee16a-103">Utilizzare la **procedura guidata Registra applicazione livello dati** o uno script di Windows PowerShell per compilare una definizione di applicazione livello dati (DAC) che descrive gli oggetti in un database esistente e registrare la definizione DAC nel database di `msdb` sistema (**Master** in [!INCLUDE[ssSDSfull](../../includes/sssdsfull-md.md)] ).</span><span class="sxs-lookup"><span data-stu-id="ee16a-103">Use either the **Register Data-tier Application Wizard** or a Windows PowerShell script to build a data-tier application (DAC) definition that describes the objects in an existing database, and register the DAC definition in the `msdb` system database (**master** in [!INCLUDE[ssSDSfull](../../includes/sssdsfull-md.md)]).</span></span>  
  
-   <span data-ttu-id="ee16a-104">**Prima di iniziare:**  [Limitazioni e restrizioni](#LimitationsRestrictions), [Autorizzazioni](#Permissions)</span><span class="sxs-lookup"><span data-stu-id="ee16a-104">**Before you begin:**  [Limitations and Restrictions](#LimitationsRestrictions), [Permissions](#Permissions)</span></span>  
  
-   <span data-ttu-id="ee16a-105">**Per aggiornare un'applicazione livello dati tramite la:**  [Procedura guidata Elimina applicazione livello dati](#UsingRegisterDACWizard), [PowerShell](#RegisterDACPowerShell)</span><span class="sxs-lookup"><span data-stu-id="ee16a-105">**To upgrade a DAC, using:**  [The Register Data-tier Application Wizard](#UsingRegisterDACWizard), [PowerShell](#RegisterDACPowerShell)</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="ee16a-106">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="ee16a-106">Before You Begin</span></span>  
 <span data-ttu-id="ee16a-107">Il processo di registrazione genera una definizione di applicazione livello dati che definisce gli oggetti nel database.</span><span class="sxs-lookup"><span data-stu-id="ee16a-107">The registration process creates a DAC definition that defines the objects in the database.</span></span> <span data-ttu-id="ee16a-108">La definizione dell'applicazione livello dati e il database combinati costituiscono un'istanza di applicazione livello dati.</span><span class="sxs-lookup"><span data-stu-id="ee16a-108">The combination of the DAC definition and the database form a DAC instance.</span></span> <span data-ttu-id="ee16a-109">Se si registra un database come applicazione livello dati in un'istanza gestita del Motore di database, l'applicazione livello dati registrata viene incorporata in Utilità SQL Server al successivo invio del set di raccolta dell'utilità dall'istanza al punto di controllo dell'utilità.</span><span class="sxs-lookup"><span data-stu-id="ee16a-109">If you register a database as a DAC on a managed instance of the Database Engine, the registered DAC will be incorporated into the SQL Server Utility the next time the utility collection set is sent from the instance to the Utility Control Point.</span></span> <span data-ttu-id="ee16a-110">L'applicazione livello dati sarà quindi presente nel nodo **Deployed Data-tier Applications** (Applicazioni livello dati distribuite) in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] **Utility Explorer** e segnalata nella pagina dei dettagli **Deployed Data-tier Applications** (Applicazioni livello dati distribuite).</span><span class="sxs-lookup"><span data-stu-id="ee16a-110">The DAC will then be present in the **Deployed Data-tier Applications** node of the [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] **Utility Explorer** and reported in the **Deployed Data-tier Applications** details page.</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="LimitationsRestrictions"></a> <span data-ttu-id="ee16a-111">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="ee16a-111">Limitations and Restrictions</span></span>  
 <span data-ttu-id="ee16a-112">La registrazione di un'applicazione livello dati può essere effettuata solo per un database in [!INCLUDE[ssSDS](../../includes/sssds-md.md)]o [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Service Pack 4 (SP4) o versioni successive.</span><span class="sxs-lookup"><span data-stu-id="ee16a-112">DAC registration can only be performed on a database in [!INCLUDE[ssSDS](../../includes/sssds-md.md)], or [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Service Pack 4 (SP4) or later.</span></span> <span data-ttu-id="ee16a-113">La registrazione di un'applicazione livello dati non può essere eseguita se è stata già registrata un'applicazione livello dati per il database.</span><span class="sxs-lookup"><span data-stu-id="ee16a-113">DAC registration cannot be performed if a DAC is already registered for the database.</span></span> <span data-ttu-id="ee16a-114">Se, ad esempio, il database è stato creato distribuendo un'applicazione livello dati, non è possibile eseguire la procedura guidata **Registra applicazione livello dati**.</span><span class="sxs-lookup"><span data-stu-id="ee16a-114">For example, if the database was created by deploying a DAC, you cannot run the **Register Data-tier Application Wizard**.</span></span>  
  
 <span data-ttu-id="ee16a-115">Non è possibile registrare un'applicazione livello dati se il database include oggetti non supportati nell'applicazione livello dati o utenti contenuti.</span><span class="sxs-lookup"><span data-stu-id="ee16a-115">You cannot register a DAC if the database has objects that are not supported in a DAC, or contained users.</span></span> <span data-ttu-id="ee16a-116">Per ulteriori informazioni sui tipi di oggetti supportati in un'applicazione livello dati, vedere [DAC Support For SQL Server Objects and Versions](dac-support-for-sql-server-objects-and-versions.md).</span><span class="sxs-lookup"><span data-stu-id="ee16a-116">For more information about the types of objects supported in a DAC, see [DAC Support For SQL Server Objects and Versions](dac-support-for-sql-server-objects-and-versions.md).</span></span>  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="ee16a-117">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="ee16a-117">Permissions</span></span>  
 <span data-ttu-id="ee16a-118">La registrazione di un'applicazione livello dati in un'istanza di [!INCLUDE[ssDE](../../includes/ssde-md.md)] richiede almeno autorizzazioni ALTER ANY LOGIN e VIEW DEFINITION per l'ambito del database, nonché autorizzazioni SELECT su **sys.sql_expression_dependencies**, oltre all'appartenenza al ruolo predefinito del server **dbcreator** .</span><span class="sxs-lookup"><span data-stu-id="ee16a-118">Registering a DAC in an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] requires at least ALTER ANY LOGIN and database scope VIEW DEFINITION permissions, SELECT permissions on **sys.sql_expression_dependencies**, and membership in the **dbcreator** fixed server role.</span></span> <span data-ttu-id="ee16a-119">Possono registrare un'applicazione livello dati anche i membri del ruolo predefinito del server **sysadmin** o dell'account amministratore di sistema SQL Server predefinito denominato **sa** .</span><span class="sxs-lookup"><span data-stu-id="ee16a-119">Members of the **sysadmin** fixed server role or the built-in SQL Server system administrator account named **sa** can also register a DAC.</span></span> <span data-ttu-id="ee16a-120">La registrazione di un'applicazione livello dati che non contiene accessi in [!INCLUDE[ssSDS](../../includes/sssds-md.md)] richiede l'appartenenza ai ruoli **dbmanager** o **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="ee16a-120">Registering a DAC that does not contain logins in [!INCLUDE[ssSDS](../../includes/sssds-md.md)] requires membership in the **dbmanager** or **serveradmin** roles.</span></span> <span data-ttu-id="ee16a-121">La registrazione di un'applicazione livello dati che contiene account di accesso in [!INCLUDE[ssSDS](../../includes/sssds-md.md)] richiede l'appartenenza ai ruoli **loginmanager** o **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="ee16a-121">Registering a DAC that contains logins in [!INCLUDE[ssSDS](../../includes/sssds-md.md)] requires membership in the **loginmanager** or **serveradmin** roles.</span></span>  
  
##  <a name="using-the-register-data-tier-application-wizard"></a><a name="UsingRegisterDACWizard"></a> <span data-ttu-id="ee16a-122">Utilizzo della procedura guidata Registra applicazione livello dati</span><span class="sxs-lookup"><span data-stu-id="ee16a-122">Using the Register Data-tier Application Wizard</span></span>  
 <span data-ttu-id="ee16a-123">**Per registrare un'applicazione livello dati tramite procedura guidata**</span><span class="sxs-lookup"><span data-stu-id="ee16a-123">**To Register a DAC Using a Wizard**</span></span>  
  
1.  <span data-ttu-id="ee16a-124">In **Esplora oggetti**espandere il nodo dell'istanza contenente il database per il quale registrare l'applicazione livello dati.</span><span class="sxs-lookup"><span data-stu-id="ee16a-124">In **Object Explorer**, expand the node for the instance containing the database to be registered as a DAC.</span></span>  
  
2.  <span data-ttu-id="ee16a-125">Espandere il nodo di **Database** .</span><span class="sxs-lookup"><span data-stu-id="ee16a-125">Expand the **Databases** node.</span></span>  
  
3.  <span data-ttu-id="ee16a-126">Fare clic con il pulsante destro del mouse sul database da registrare, scegliere **Attività** e quindi selezionare **Registra come applicazione livello dati**.</span><span class="sxs-lookup"><span data-stu-id="ee16a-126">Right-click the database to be registered, point to **Tasks**, and then select **Register As Data-tier Application...**</span></span>  
  
4.  <span data-ttu-id="ee16a-127">Completare le finestre di dialogo della procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="ee16a-127">Complete the wizard dialogs:</span></span>  
  
    1.  [<span data-ttu-id="ee16a-128">Pagina Introduzione</span><span class="sxs-lookup"><span data-stu-id="ee16a-128">Introduction Page</span></span>](#Introduction)  
  
    2.  [<span data-ttu-id="ee16a-129">Pagina Imposta proprietà</span><span class="sxs-lookup"><span data-stu-id="ee16a-129">Set Properties Page</span></span>](#Set_properties)  
  
    3.  [<span data-ttu-id="ee16a-130">Pagina Convalida e riepilogo</span><span class="sxs-lookup"><span data-stu-id="ee16a-130">Validation and Summary Page</span></span>](#Summary)  
  
    4.  [<span data-ttu-id="ee16a-131">Pagina Registra DAC</span><span class="sxs-lookup"><span data-stu-id="ee16a-131">Register DAC Page</span></span>](#Register)  
  
##  <a name="introduction-page"></a><a name="Introduction"></a> <span data-ttu-id="ee16a-132">Pagina Introduzione</span><span class="sxs-lookup"><span data-stu-id="ee16a-132">Introduction Page</span></span>  
 <span data-ttu-id="ee16a-133">In questa pagina vengono descritti i passaggi per la registrazione di un'applicazione livello dati.</span><span class="sxs-lookup"><span data-stu-id="ee16a-133">This page describes the steps for registering a data-tier application.</span></span>  
  
 <span data-ttu-id="ee16a-134">**Non visualizzare più questa pagina**</span><span class="sxs-lookup"><span data-stu-id="ee16a-134">**Do not show this page again.**</span></span> <span data-ttu-id="ee16a-135">- Fare clic sulla casella di controllo per evitare che la pagina venga visualizzata nuovamente in futuro.</span><span class="sxs-lookup"><span data-stu-id="ee16a-135">- Click the check box to stop the page from being displayed in the future.</span></span>  
  
 <span data-ttu-id="ee16a-136">**Avanti >** : consente di passare alla pagina **Imposta proprietà**.</span><span class="sxs-lookup"><span data-stu-id="ee16a-136">**Next >** - Proceeds to the **Set Properties** page.</span></span>  
  
 <span data-ttu-id="ee16a-137">**Annulla** : consente di terminare la procedura guidata senza registrare un'applicazione livello dati.</span><span class="sxs-lookup"><span data-stu-id="ee16a-137">**Cancel** - Terminates the wizard without registering a DAC.</span></span>  
  
##  <a name="set-properties-page"></a><a name="Set_properties"></a> <span data-ttu-id="ee16a-138">Pagina Imposta proprietà</span><span class="sxs-lookup"><span data-stu-id="ee16a-138">Set Properties Page</span></span>  
 <span data-ttu-id="ee16a-139">Utilizzare questa pagina per specificare le proprietà a livello di applicazione livello dati quali il nome dell'applicazione e la versione.</span><span class="sxs-lookup"><span data-stu-id="ee16a-139">Use this page to specify DAC-level properties such as the application name and version.</span></span>  
  
 <span data-ttu-id="ee16a-140">**Nome applicazione**</span><span class="sxs-lookup"><span data-stu-id="ee16a-140">**Application name.**</span></span> <span data-ttu-id="ee16a-141">- Stringa che specifica il nome usato per identificare la definizione dell'applicazione livello dati; il campo viene popolato con il nome del database.</span><span class="sxs-lookup"><span data-stu-id="ee16a-141">- A string that specifies the name used to identify the DAC definition, the field is been populated with the database name.</span></span>  
  
 <span data-ttu-id="ee16a-142">**Versione.**</span><span class="sxs-lookup"><span data-stu-id="ee16a-142">**Version.**</span></span> <span data-ttu-id="ee16a-143">- Valore numerico che identifica la versione dell'applicazione livello dati.</span><span class="sxs-lookup"><span data-stu-id="ee16a-143">- A numeric value that identifies the version of the DAC.</span></span> <span data-ttu-id="ee16a-144">La versione DAC viene utilizzata in Visual Studio per identificare la versione della DAC alla quale stanno lavorando gli sviluppatori.</span><span class="sxs-lookup"><span data-stu-id="ee16a-144">The DAC version is used in Visual Studio to identify the version of the DAC that developers are working on.</span></span> <span data-ttu-id="ee16a-145">Quando si distribuisce un'applicazione livello dati, la versione viene archiviata nel `msdb` database e può essere visualizzata successivamente nel nodo **applicazioni livello dati** in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ee16a-145">When deploying a DAC, the version is stored in the `msdb` database and can later be viewed under the **Data-tier Applications** node in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="ee16a-146">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="ee16a-146">**Description.**</span></span> <span data-ttu-id="ee16a-147">- (Facoltativa).</span><span class="sxs-lookup"><span data-stu-id="ee16a-147">- Optional.</span></span> <span data-ttu-id="ee16a-148">Testo che illustra lo scopo dell'applicazione livello dati.</span><span class="sxs-lookup"><span data-stu-id="ee16a-148">Text that explains the purpose of the DAC.</span></span> <span data-ttu-id="ee16a-149">Quando si distribuisce un'applicazione livello dati, la descrizione viene archiviata nel `msdb` database e può essere visualizzata successivamente nel nodo **applicazioni livello dati** in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ee16a-149">When deploying a DAC, the description is stored in the `msdb` database and can later be viewed under the **Data-tier Applications** node in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span>  
  
 <span data-ttu-id="ee16a-150">\*\* \< Indietro\*\* : consente di tornare alla pagina **Introduzione** .</span><span class="sxs-lookup"><span data-stu-id="ee16a-150">**\< Previous** - Returns you to the **Introduction** page.</span></span>  
  
 <span data-ttu-id="ee16a-151">**Avanti >** : consente di verificare che sia possibile compilare un'applicazione livello dati dagli oggetti nel database e di visualizzare i risultati nella pagina **Convalida e riepilogo**.</span><span class="sxs-lookup"><span data-stu-id="ee16a-151">**Next >** - Verifies that a DAC can be built from the objects in the database, and displays the results in the **Validation and Summary** page.</span></span>  
  
 <span data-ttu-id="ee16a-152">**Annulla** : consente di terminare la procedura guidata senza registrare l'applicazione livello dati.</span><span class="sxs-lookup"><span data-stu-id="ee16a-152">**Cancel** - Terminates the wizard without registering the DAC.</span></span>  
  
##  <a name="validation-and-summary-page"></a><a name="Summary"></a> <span data-ttu-id="ee16a-153">Pagina Convalida e riepilogo</span><span class="sxs-lookup"><span data-stu-id="ee16a-153">Validation and Summary Page</span></span>  
 <span data-ttu-id="ee16a-154">Utilizzare questa pagina per verificare le azioni eseguite dalla procedura guidata durante la registrazione dell'applicazione livello dati.</span><span class="sxs-lookup"><span data-stu-id="ee16a-154">Use this page to review the actions the wizard will take when registering the DAC.</span></span> <span data-ttu-id="ee16a-155">La pagina passa attraverso tre stati per verificare se un'applicazione livello dati possa essere compilata dagli oggetti contenuti nel database.</span><span class="sxs-lookup"><span data-stu-id="ee16a-155">The page transitions through three states as it verifies that a DAC can be built from the objects in the database.</span></span>  
  
### <a name="retrieving-objects"></a><span data-ttu-id="ee16a-156">Recupero degli oggetti</span><span class="sxs-lookup"><span data-stu-id="ee16a-156">Retrieving Objects</span></span>  
 <span data-ttu-id="ee16a-157">**Recupero di oggetti database e server.**</span><span class="sxs-lookup"><span data-stu-id="ee16a-157">**Retrieving database and server objects.**</span></span> <span data-ttu-id="ee16a-158">- Consente di visualizzare un indicatore di stato durante il recupero di tutti gli oggetti richiesti dal database e dall'istanza del Motore di database.</span><span class="sxs-lookup"><span data-stu-id="ee16a-158">- Displays a progress bar as the wizard retrieves all of the required objects from the database and the instance of the Database Engine.</span></span>  
  
 <span data-ttu-id="ee16a-159">\*\* \< Indietro\*\* : consente di tornare alla pagina **Imposta proprietà** per modificare le voci.</span><span class="sxs-lookup"><span data-stu-id="ee16a-159">**\< Previous** - Returns you to the **Set Properties** page to change your entries.</span></span>  
  
 <span data-ttu-id="ee16a-160">**Avanti>** : consente di registrare l'applicazione livello dati e visualizzare i risultati nella pagina **Registra applicazione livello dati**.</span><span class="sxs-lookup"><span data-stu-id="ee16a-160">**Next >** - Registers the DAC and displays the results in the **Register DAC** page.</span></span>  
  
 <span data-ttu-id="ee16a-161">**Annulla** : consente di terminare la procedura guidata senza registrare l'applicazione livello dati.</span><span class="sxs-lookup"><span data-stu-id="ee16a-161">**Cancel** - Terminates the wizard without registering the DAC.</span></span>  
  
### <a name="validating-objects"></a><span data-ttu-id="ee16a-162">Convalida degli oggetti</span><span class="sxs-lookup"><span data-stu-id="ee16a-162">Validating Objects</span></span>  
 <span data-ttu-id="ee16a-163">**Verifica**  _NomeSchema_ **.**</span><span class="sxs-lookup"><span data-stu-id="ee16a-163">**Checking**  _SchemaName_ **.**</span></span> <span data-ttu-id="ee16a-164">_NomeOggetto_ **.**</span><span class="sxs-lookup"><span data-stu-id="ee16a-164">_ObjectName_ **.**</span></span> <span data-ttu-id="ee16a-165">- Consente di visualizzare un indicatore di stato durante la verifica delle dipendenze degli oggetti recuperati e della loro validità per l'applicazione livello dati.</span><span class="sxs-lookup"><span data-stu-id="ee16a-165">- Displays a progress bar as the wizard verifies the dependencies of the retrieved objects, and verifies that they are all valid objects for a DAC.</span></span> <span data-ttu-id="ee16a-166">_NomeSchema_ **.** _NomeOggetto_ identifica l'oggetto attualmente sottoposto a verifica.</span><span class="sxs-lookup"><span data-stu-id="ee16a-166">_SchemaName_**.**_ObjectName_ identify which object is currently being verified.</span></span>  
  
 <span data-ttu-id="ee16a-167">\*\* \< Indietro\*\* : consente di tornare alla pagina **Imposta proprietà** per modificare le voci.</span><span class="sxs-lookup"><span data-stu-id="ee16a-167">**\< Previous** - Returns you to the **Set Properties** page to change your entries.</span></span>  
  
 <span data-ttu-id="ee16a-168">**Avanti>** : consente di registrare l'applicazione livello dati e visualizzare i risultati nella pagina **Registra applicazione livello dati**.</span><span class="sxs-lookup"><span data-stu-id="ee16a-168">**Next >** - Registers the DAC and displays the results in the **Register DAC** page.</span></span>  
  
 <span data-ttu-id="ee16a-169">**Annulla** : consente di terminare la procedura guidata senza registrare l'applicazione livello dati.</span><span class="sxs-lookup"><span data-stu-id="ee16a-169">**Cancel** - Terminates the wizard without registering the DAC.</span></span>  
  
### <a name="summary"></a><span data-ttu-id="ee16a-170">Summary</span><span class="sxs-lookup"><span data-stu-id="ee16a-170">Summary</span></span>  
 <span data-ttu-id="ee16a-171">**Per la registrazione dell'applicazione livello dati verranno utilizzate le impostazioni seguenti.**</span><span class="sxs-lookup"><span data-stu-id="ee16a-171">**The following setting will be used to register your DAC.**</span></span> <span data-ttu-id="ee16a-172">- Consente di visualizzare un report delle proprietà e degli oggetti che verranno inclusi nell'applicazione livello dati.</span><span class="sxs-lookup"><span data-stu-id="ee16a-172">- Displays a report of the properties and objects that will be included in the DAC.</span></span>  
  
 <span data-ttu-id="ee16a-173">**Salva report** consente di salvare una copia del report di convalida come file HTML.</span><span class="sxs-lookup"><span data-stu-id="ee16a-173">**Save Report** - Select this button to save a copy of the validation report to an HTML file.</span></span> <span data-ttu-id="ee16a-174">La cartella predefinita, **SQL Server Management Studio\DAC Packages** , si trova all'interno della cartella Documenti dell'account di Windows.</span><span class="sxs-lookup"><span data-stu-id="ee16a-174">The default folder is a **SQL Server Management Studio\DAC Packages** folder in the Documents folder of your Windows account.</span></span>  
  
 <span data-ttu-id="ee16a-175">\*\* \< Indietro\*\* : consente di tornare alla pagina **Imposta proprietà** per modificare le voci.</span><span class="sxs-lookup"><span data-stu-id="ee16a-175">**\< Previous** - Returns you to the **Set Properties** page to change your entries.</span></span>  
  
 <span data-ttu-id="ee16a-176">**Avanti>** : consente di registrare l'applicazione livello dati e visualizzare i risultati nella pagina **Registra applicazione livello dati**.</span><span class="sxs-lookup"><span data-stu-id="ee16a-176">**Next >** - Registers the DAC and displays the results in the **Register DAC** page.</span></span>  
  
 <span data-ttu-id="ee16a-177">**Annulla** : consente di terminare la procedura guidata senza registrare l'applicazione livello dati.</span><span class="sxs-lookup"><span data-stu-id="ee16a-177">**Cancel** - Terminates the wizard without registering the DAC.</span></span>  
  
##  <a name="register-dac-page"></a><a name="Register"></a> <span data-ttu-id="ee16a-178">Pagina Registra DAC</span><span class="sxs-lookup"><span data-stu-id="ee16a-178">Register DAC Page</span></span>  
 <span data-ttu-id="ee16a-179">In questa pagina viene riportato l'esito positivo o negativo della registrazione.</span><span class="sxs-lookup"><span data-stu-id="ee16a-179">This page reports the success or failure of the registration.</span></span>  
  
 <span data-ttu-id="ee16a-180">**Registrazione dell'applicazione livello dati** : consente di visualizzare l'esito positivo o negativo di ogni azione eseguita per la registrazione dell'applicazione livello dati.</span><span class="sxs-lookup"><span data-stu-id="ee16a-180">**Registering the DAC** - Reports the success or failure of each action taken to register the DAC.</span></span> <span data-ttu-id="ee16a-181">Verificare le informazioni che determinano l'esito positivo o negativo di ciascuna azione.</span><span class="sxs-lookup"><span data-stu-id="ee16a-181">Review the information to determine the success or failure of each action.</span></span> <span data-ttu-id="ee16a-182">Ogni azione che ha rilevato un errore avrà un collegamento nella colonna **Risultato** .</span><span class="sxs-lookup"><span data-stu-id="ee16a-182">Any action that encountered an error will have a link in the **Result** column.</span></span> <span data-ttu-id="ee16a-183">Selezionare il collegamento per visualizzare un report dell'errore per l'azione.</span><span class="sxs-lookup"><span data-stu-id="ee16a-183">Select the link to view a report of the error for that action.</span></span>  
  
 <span data-ttu-id="ee16a-184">**Salva report** consente di salvare il report della registrazione come file HTML.</span><span class="sxs-lookup"><span data-stu-id="ee16a-184">**Save Report** - Select this button to save the registration report to an HTML file.</span></span> <span data-ttu-id="ee16a-185">Nel file viene riportato lo stato di ogni azione, inclusi tutti gli errori generati da qualsiasi azione.</span><span class="sxs-lookup"><span data-stu-id="ee16a-185">The file reports the status of each action, including all errors generated by any of the actions.</span></span> <span data-ttu-id="ee16a-186">La cartella predefinita, **SQL Server Management Studio\DAC Packages** , si trova all'interno della cartella Documenti dell'account di Windows.</span><span class="sxs-lookup"><span data-stu-id="ee16a-186">The default folder is a **SQL Server Management Studio\DAC Packages** folder in the Documents folder of your Windows account.</span></span> <span data-ttu-id="ee16a-187">Il nome del file è nel formato \<DACPackageName>_RegisterDACReport_aaaammgg.html, dove \<*DACPackageName*> è il nome del pacchetto da distribuire, *aaaa* indica l'anno corrente, *mm* il mese corrente e *gg* il giorno corrente.</span><span class="sxs-lookup"><span data-stu-id="ee16a-187">The file name is in the format \<DACPackageName>_RegisterDACReport_yyyymmdd.html, where \<*DACPackageName*> is the name of the package being deployed, *yyyy* = the current year, *mm* = the current month, and *dd* = the current day.</span></span>  
  
 <span data-ttu-id="ee16a-188">**Fine** : consente di terminare la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="ee16a-188">**Finish** - Terminates the wizard.</span></span>  
  
##  <a name="register-a-dac-using-powershell"></a><a name="RegisterDACPowerShell"></a> <span data-ttu-id="ee16a-189">Registrare un'applicazione livello dati tramite PowerShell</span><span class="sxs-lookup"><span data-stu-id="ee16a-189">Register a DAC Using PowerShell</span></span>  
 <span data-ttu-id="ee16a-190">**Per registrare un database come applicazione livello dati usando il metodo Register() in uno script di PowerShell**</span><span class="sxs-lookup"><span data-stu-id="ee16a-190">**To register a database as a DAC using the Register() method in a PowerShell script**</span></span>  
  
1.  <span data-ttu-id="ee16a-191">Creare un oggetto server SMO e impostarlo sull'istanza contenente il database che si desidera registrare come applicazione livello dati.</span><span class="sxs-lookup"><span data-stu-id="ee16a-191">Create a SMO Server object and set it to the instance that contains the database to be registered as a DAC.</span></span>  
  
2.  <span data-ttu-id="ee16a-192">Aggiungere una variabile che specifichi il nome del database.</span><span class="sxs-lookup"><span data-stu-id="ee16a-192">Add a variable that specifies the name of the database.</span></span>  
  
3.  <span data-ttu-id="ee16a-193">Specificare i metadati per l'applicazione livello dati, quali nome dell'applicazione livello dati, versione e descrizione.</span><span class="sxs-lookup"><span data-stu-id="ee16a-193">Specify the metadata for the DAC, such as the DAC name, version, and description.</span></span>  
  
4.  <span data-ttu-id="ee16a-194">Eseguire il metodo Register con le informazioni specificate in precedenza.</span><span class="sxs-lookup"><span data-stu-id="ee16a-194">Run the Register method with the information specified above.</span></span>  
  
### <a name="example-powershell"></a><span data-ttu-id="ee16a-195">Esempio (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="ee16a-195">Example (PowerShell)</span></span>  
 <span data-ttu-id="ee16a-196">Nell'esempio seguente viene registrato un database denominato MyDB come applicazione livello dati.</span><span class="sxs-lookup"><span data-stu-id="ee16a-196">The following example registers a database named MyDB as a DAC.</span></span>  
  
```powershell
## Set a SMO Server object to the default instance on the local computer.  
CD SQLSERVER:\SQL\localhost\DEFAULT  
$srv = Get-Item .  
  
## Specify the database to register as a DAC.  
$dbname = "MyDB"  
  
## Specify the DAC metadata.  
$applicationname = "MyApplication"  
$version = "1.0.0.0"  
$description = "This DAC defines the database used by my application."  
  
## Register the DAC.  
$registerunit = New-Object Microsoft.SqlServer.Management.Dac.DacExtractionUnit($srv, $dbname, $applicationname, $version)  
$registerunit.Description = $description  
$registerunit.Register()  
```  
  
## <a name="see-also"></a><span data-ttu-id="ee16a-197">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ee16a-197">See Also</span></span>  
 [<span data-ttu-id="ee16a-198">Applicazioni livello dati</span><span class="sxs-lookup"><span data-stu-id="ee16a-198">Data-tier Applications</span></span>](data-tier-applications.md)  
