---
title: Ruoli utente per Change Data Capture Service per Oracle da Attunity | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: be0ec384-e03b-4483-96ca-02b289804d6a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e694da0cfd8645fe594b049b6dc2394b55d1bb55
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720292"
---
# <a name="user-roles-for-change-data-capture-service-for-oracle-by-attunity"></a><span data-ttu-id="685cf-102">Ruoli utente per il servizio CDC (Change Data Capture) per Oracle di Attunity</span><span class="sxs-lookup"><span data-stu-id="685cf-102">User Roles for Change Data Capture Service for Oracle by Attunity</span></span>
  <span data-ttu-id="685cf-103">In questa sezione sono descritti i ruoli utente per il servizio Change Data Capture per Oracle di Attunity.</span><span class="sxs-lookup"><span data-stu-id="685cf-103">This section describes the user roles for the Change Data Capture Service for Oracle by Attunity.</span></span> <span data-ttu-id="685cf-104">I ruoli descritti sono ruoli del database [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , ruoli di Windows o ruoli del database Oracle.</span><span class="sxs-lookup"><span data-stu-id="685cf-104">The roles described are [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database roles, Windows roles, or Oracle database roles.</span></span>  
  
## <a name="windows-user-roles"></a><span data-ttu-id="685cf-105">Ruoli utente di Windows</span><span class="sxs-lookup"><span data-stu-id="685cf-105">Windows User Roles</span></span>  
 <span data-ttu-id="685cf-106">Di seguito vengono descritti i ruoli utente di Windows utilizzati dal servizio Oracle CDC.</span><span class="sxs-lookup"><span data-stu-id="685cf-106">The following describes the Windows user roles used by the Oracle CDC Service.</span></span>  
  
### <a name="computer-administrator-oracle-cdc-service"></a><span data-ttu-id="685cf-107">Amministratore del computer: servizio Oracle CDC</span><span class="sxs-lookup"><span data-stu-id="685cf-107">Computer Administrator: Oracle CDC Service</span></span>  
 <span data-ttu-id="685cf-108">L'amministratore del computer è un utente di Windows responsabile della creazione e della gestione del servizio CDC nel computer.</span><span class="sxs-lookup"><span data-stu-id="685cf-108">The computer administrator is a Windows user responsible for creating and maintaining the CDC Service on the computer.</span></span> <span data-ttu-id="685cf-109">Deve appartenere al gruppo di amministratori del computer locale.</span><span class="sxs-lookup"><span data-stu-id="685cf-109">This user must belong to the group of local machine administrators.</span></span>  
  
 <span data-ttu-id="685cf-110">Tra le attività eseguite dall'amministratore del computer del servizio Oracle CDC sono incluse le seguenti:</span><span class="sxs-lookup"><span data-stu-id="685cf-110">The tasks performed by the Oracle CDC Service Computer Administrator include:</span></span>  
  
-   <span data-ttu-id="685cf-111">Installazione del servizio CDC per il software Oracle</span><span class="sxs-lookup"><span data-stu-id="685cf-111">Installing the CDC Service for Oracle software</span></span>  
  
-   <span data-ttu-id="685cf-112">Creazione di un servizio di Windows Oracle CDC</span><span class="sxs-lookup"><span data-stu-id="685cf-112">Creating an Oracle CDC Windows service</span></span>  
  
-   <span data-ttu-id="685cf-113">Impostazione della connessione del servizio CDC all'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] di destinazione (stringa di connessione e credenziali)</span><span class="sxs-lookup"><span data-stu-id="685cf-113">Setting up the CDC Service connection to the target [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance (connection string and credentials)</span></span>  
  
-   <span data-ttu-id="685cf-114">Controllo della password master del servizio CDC con cui vengono protette le credenziali di log mining</span><span class="sxs-lookup"><span data-stu-id="685cf-114">Ensuring that the CDC Service Master Password with which Oracle log mining credentials are protected</span></span>  
  
-   <span data-ttu-id="685cf-115">Eliminazione di un servizio di Windows del servizio CDC</span><span class="sxs-lookup"><span data-stu-id="685cf-115">Deleting a CDC Service Windows service</span></span>  
  
-   <span data-ttu-id="685cf-116">Disinstallazione del servizio CDC per il software Oracle</span><span class="sxs-lookup"><span data-stu-id="685cf-116">Uninstalling the CDC Service for Oracle software</span></span>  
  
-   <span data-ttu-id="685cf-117">Gestione del servizio CDC per il software Oracle (ad esempio installazione degli aggiornamenti)</span><span class="sxs-lookup"><span data-stu-id="685cf-117">Maintaining the CDC Service for Oracle software (for example, installing updates)</span></span>  
  
-   <span data-ttu-id="685cf-118">Avvio e arresto del servizio di Windows del servizio CDC</span><span class="sxs-lookup"><span data-stu-id="685cf-118">Starting and stopping a CDC Service Windows service</span></span>  
  
 <span data-ttu-id="685cf-119">Nelle configurazioni di disponibilità elevata, ad esempio i cluster di failover Microsoft, l'amministratore del computer deve disporre di responsabilità e autorizzazioni aggiuntive quali:</span><span class="sxs-lookup"><span data-stu-id="685cf-119">When working with high-availability configurations, such as Microsoft failover clusters, the computer administrator must have additional responsibilities and permissions such as:</span></span>  
  
-   <span data-ttu-id="685cf-120">Installazione e manutenzione del servizio CDC per il software Oracle in tutti i nodi del cluster.</span><span class="sxs-lookup"><span data-stu-id="685cf-120">Installation and maintenance of the CDC Service for Oracle software on all cluster nodes.</span></span>  
  
-   <span data-ttu-id="685cf-121">Definizione delle risorse generiche del servizio cluster per il servizio di Windows del servizio CDC nei vari nodi del cluster.</span><span class="sxs-lookup"><span data-stu-id="685cf-121">Defining generic cluster service resources for the CDC Service' Windows service on the various cluster nodes.</span></span>  
  
-   <span data-ttu-id="685cf-122">Funzione di amministratore del computer autorizzato come amministratore nel computer in cui è installato il servizio CDC per Oracle.</span><span class="sxs-lookup"><span data-stu-id="685cf-122">Acting as the computer administrator authorized as an administrator on the computer where the CDC Service for Oracle is installed.</span></span> <span data-ttu-id="685cf-123">Questa persona installa il servizio CDC per Oracle e utilizza la console di configurazione del servizio CDC per configurare un servizio CDC per Oracle in un computer locale.</span><span class="sxs-lookup"><span data-stu-id="685cf-123">This person installs the CDC Service for Oracle and uses the CDC Service Configuration Console to configure a CDC Service for Oracle on a local computer.</span></span>  
  
### <a name="service-account-oracle-cdc-service"></a><span data-ttu-id="685cf-124">Account del servizio: servizio Oracle CDC</span><span class="sxs-lookup"><span data-stu-id="685cf-124">Service Account: Oracle CDC Service</span></span>  
 <span data-ttu-id="685cf-125">Si tratta dell'account del servizio di Windows del servizio CDC, un account di Windows utilizzato per l'esecuzione del servizio Oracle CDC (account del servizio).</span><span class="sxs-lookup"><span data-stu-id="685cf-125">This is Oracle CDC Service Windows Service Account is a Windows account used for running the Oracle CDC Service (the Service Account).</span></span>  
  
 <span data-ttu-id="685cf-126">L'unico privilegio obbligatorio necessario per l'account del servizio è la possibilità di utilizzare il client Oracle e il provider ODBC del client nativo [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="685cf-126">The only required privilege necessary for the service account is to be able to use the Oracle client and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] native client ODBC provider.</span></span> <span data-ttu-id="685cf-127">Questo account non necessita dell'accesso ai file a meno che non sia richiesto da provider specifici, ad esempio se la stringa di connessione del client Oracle fa riferimento alle istanze del database Oracle in un file **tnsnames.ora** , nel qual caso il file deve essere accessibile in lettura all'account del servizio.</span><span class="sxs-lookup"><span data-stu-id="685cf-127">This account does not need to access files unless required by specific providers (for example, if the Oracle client connection string references Oracle database instances in a **tnsnames.ora** file, then that file must be read-accessible to the service account).</span></span>  
  
 <span data-ttu-id="685cf-128">Quando si crea un servizio Oracle CDC in Windows Vista o Windows Server 2008, l'account del servizio predefinito è l'account NETWORK SERVICE.</span><span class="sxs-lookup"><span data-stu-id="685cf-128">When creating an Oracle CDC Service on Windows Vista or Windows Server 2008, the default service account is the NETWORK SERVICE account.</span></span>  
  
 <span data-ttu-id="685cf-129">In Windows 7, Windows Server 2008 R2 e versioni successive, l'account del servizio predefinito è Servizio NT\\<nome-servizio>.</span><span class="sxs-lookup"><span data-stu-id="685cf-129">On Windows 7, Windows Server 2008 R2 and later, the default service account is NT Service\\<service-name>.</span></span>  
  
 <span data-ttu-id="685cf-130">Quando [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] è in esecuzione in un altro computer o è un'istanza cluster di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e il servizio richiede la connessione all'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] di destinazione tramite l'autenticazione di Windows, l'account del servizio deve essere un account di dominio.</span><span class="sxs-lookup"><span data-stu-id="685cf-130">When [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] runs on another machine or is a clustered [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance and there the service needs to connect to the target [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using Windows authentication, then the service account should be a domain account.</span></span>  
  
## <a name="sql-server-user-roles"></a><span data-ttu-id="685cf-131">Ruoli utente di SQL Server</span><span class="sxs-lookup"><span data-stu-id="685cf-131">SQL Server User Roles</span></span>  
 <span data-ttu-id="685cf-132">Di seguito vengono descritti i ruoli utente di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utilizzati dal servizio Oracle CDC.</span><span class="sxs-lookup"><span data-stu-id="685cf-132">The following describes the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] user roles used by the Oracle CDC Service.</span></span>  
  
### <a name="oracle-cdc-service-administrator"></a><span data-ttu-id="685cf-133">Amministratore del servizio Oracle CDC</span><span class="sxs-lookup"><span data-stu-id="685cf-133">Oracle CDC Service Administrator</span></span>  
 <span data-ttu-id="685cf-134">L'amministratore del servizio CDC è un utente di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] con controllo completo degli artefatti del servizio Oracle CDC nell'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] di destinazione.</span><span class="sxs-lookup"><span data-stu-id="685cf-134">The CDC Service Administrator is a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] user with full control over the Oracle CDC Service artifacts in the target [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="685cf-135">L'amministratore del servizio CDC utilizza Oracle CDC Designer Console per progettare istanze di Oracle CDC.</span><span class="sxs-lookup"><span data-stu-id="685cf-135">The CDC Service Administrator uses the Oracle CDC Designer Console to design Oracle CDC Instances.</span></span>  
  
 <span data-ttu-id="685cf-136">L'amministratore del servizio CDC deve disporre dei ruoli predefiniti del server [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]**public** e **dbcreator**.</span><span class="sxs-lookup"><span data-stu-id="685cf-136">The CDC Service Administrator should be granted the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fixed server roles **public** and **dbcreator**.</span></span>  
  
 <span data-ttu-id="685cf-137">Tra le attività eseguite dall'amministratore del servizio CDC sono incluse le seguenti:</span><span class="sxs-lookup"><span data-stu-id="685cf-137">The tasks performed by the CDC Service Administrator include:</span></span>  
  
-   <span data-ttu-id="685cf-138">Preparazione di un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per ospitare istanze di Oracle CDC, che sono database di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="685cf-138">Preparing a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance to host Oracle CDC Instances (which are [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases).</span></span> <span data-ttu-id="685cf-139">In questa attività viene creato un database speciale denominato MSXDBCDC nell'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="685cf-139">In this task, a special database called MSXDBCDC is created in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span>  
  
-   <span data-ttu-id="685cf-140">Creazione di un'istanza del database di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] di Oracle CDC.</span><span class="sxs-lookup"><span data-stu-id="685cf-140">Creating an Oracle CDC Instance [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database.</span></span> <span data-ttu-id="685cf-141">L'attività include l'abilitazione del database di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] appena creato per CDC, che richiede un amministratore di sistema di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (**sysadmin**).</span><span class="sxs-lookup"><span data-stu-id="685cf-141">Task includes enabling the newly created [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database for CDC, which requires a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system administrator (**sysadmin**).</span></span>  
  
-   <span data-ttu-id="685cf-142">Progettazione di un'istanza di Oracle CDC.</span><span class="sxs-lookup"><span data-stu-id="685cf-142">Designing an Oracle CDC Instance.</span></span> <span data-ttu-id="685cf-143">Questa attività include la specifica di informazioni relative al database Oracle di origine e alle tabelle acquisite, che richiedono un amministratore del database Oracle.</span><span class="sxs-lookup"><span data-stu-id="685cf-143">This task includes providing information about the source Oracle database and captured tables, which requires an Oracle database administrator.</span></span>  
  
-   <span data-ttu-id="685cf-144">Gestione dell'istanza di Oracle CDC nel tempo, incluse le attività di aggiunta e rimozione delle istanze di acquisizione e l'aggiornamento della configurazione.</span><span class="sxs-lookup"><span data-stu-id="685cf-144">Maintaining the Oracle CDC Instance over time, which includes adding/removing capture instances and updating configuration.</span></span>  
  
-   <span data-ttu-id="685cf-145">Abilitazione o disabilitazione di un'istanza di Oracle CDC.</span><span class="sxs-lookup"><span data-stu-id="685cf-145">Enabling or disabling an Oracle CDC Instance.</span></span>  
  
-   <span data-ttu-id="685cf-146">Monitoraggio dello stato di un'istanza di Oracle CDC.</span><span class="sxs-lookup"><span data-stu-id="685cf-146">Monitoring the state of an Oracle CDC Instance.</span></span>  
  
-   <span data-ttu-id="685cf-147">Risoluzione dei problemi che hanno effetto sull'istanza di Oracle CDC.</span><span class="sxs-lookup"><span data-stu-id="685cf-147">Troubleshooting issues that affect the Oracle CDC Instance.</span></span>  
  
 <span data-ttu-id="685cf-148">Il ruolo predefinito del database dell'amministratore del servizio CDC è, almeno inizialmente, **db_owner** per il database di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] CDC associato all'istanza di Oracle CDC.</span><span class="sxs-lookup"><span data-stu-id="685cf-148">The CDC Service Administrator is, at least initially, in the **db_owner** fixed database role for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] CDC database associated with the Oracle CDC Instance.</span></span> <span data-ttu-id="685cf-149">Ciò consente all'amministratore del servizio CDC di accedere ai dati delle modifiche archiviati nel database CDC.</span><span class="sxs-lookup"><span data-stu-id="685cf-149">This gives the CDC Service Administrator access to the change data stored in the CDC database.</span></span> <span data-ttu-id="685cf-150">Dopo la creazione, è possibile assegnare il ruolo **db_owner** del database CDC a un utente diverso in grado di eseguire tutte le attività elencate in precedenza, tranne la preparazione di un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e la creazione di un'altra istanza di Oracle CDC.</span><span class="sxs-lookup"><span data-stu-id="685cf-150">Once created, the **db_owner** role of the CDC database can be assigned to a different user who can carry out all of the tasks listed above except for preparing a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance and creating another Oracle CDC Instance).</span></span>  
  
 <span data-ttu-id="685cf-151">Non è necessario che l'amministratore del servizio CDC conosca la password master specificata alla creazione del servizio di Windows Oracle CDC.</span><span class="sxs-lookup"><span data-stu-id="685cf-151">The CDC Service Administrator does not need to know the master password specified with the creation of the Oracle CDC Windows service.</span></span>  
  
### <a name="system-administrator"></a><span data-ttu-id="685cf-152">Amministratore sistema</span><span class="sxs-lookup"><span data-stu-id="685cf-152">System Administrator</span></span>  
 <span data-ttu-id="685cf-153">L'amministratore di sistema di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] è un utente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a cui deve essere concesso il ruolo predefinito del server **sysadmin** per l'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] associata al servizio o ai servizi Oracle CDC.</span><span class="sxs-lookup"><span data-stu-id="685cf-153">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system administrator is a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] user and should be granted the fixed server **sysadmin** role on the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance associated with the Oracle CDC Service(s).</span></span>  
  
 <span data-ttu-id="685cf-154">Una sola attività specifica di Oracle CDC viene eseguita dall'amministratore di sistema di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , vale a dire l'abilitazione del database di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per un'istanza di Oracle CDC per [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] CDC.</span><span class="sxs-lookup"><span data-stu-id="685cf-154">There is only one Oracle CDC specific task that carried out with the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] System Administrator and that is to enable the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database for an Oracle CDC Instance for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] CDC.</span></span> <span data-ttu-id="685cf-155">Questa attività viene eseguita utilizzando Oracle CDC Designer Console durante la creazione di una nuova istanza di Oracle CDC.</span><span class="sxs-lookup"><span data-stu-id="685cf-155">This task is performed using the Oracle CDC Designer console when creating a new Oracle CDC Instance.</span></span>  
  
### <a name="oracle-cdc-service-user"></a><span data-ttu-id="685cf-156">Utente del servizio Oracle CDC</span><span class="sxs-lookup"><span data-stu-id="685cf-156">Oracle CDC Service User</span></span>  
 <span data-ttu-id="685cf-157">L'utente del servizio Oracle CDC di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] è un account di accesso di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utilizzato dal servizio Oracle CDC per eseguire il lavoro in MSXDBCDC e in tutte le istanze di Oracle CDC (database CDC) gestite da questo servizio.</span><span class="sxs-lookup"><span data-stu-id="685cf-157">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Oracle CDC Service user is a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login which is used by the Oracle CDC Service to perform its work against the MSXDBCDC and all of the Oracle CDC Instances (CDC databases) handled by this service.</span></span>  
  
 <span data-ttu-id="685cf-158">L'utente del servizio Oracle CDC di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="685cf-158">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Oracle CDC Service user should be granted the following:</span></span>  
  
-   <span data-ttu-id="685cf-159">Deve essere membro dei ruoli predefiniti del database **db_dlladmin**, **db_datareader**e **db_datawriter** per tutti i database CDC gestiti dal server.</span><span class="sxs-lookup"><span data-stu-id="685cf-159">Member of the fixed database roles **db_dlladmin**, **db_datareader**, and **db_datawriter** for all CDC databases handled by the server.</span></span>  
  
-   <span data-ttu-id="685cf-160">Deve essere membro dei ruoli predefiniti del database **db_datareader** e **db_datawriter** per il database MSXDBCDC.</span><span class="sxs-lookup"><span data-stu-id="685cf-160">Member of the fixed database roles **db_datareader** and **db_datawriter** for the MSXDBCDC database.</span></span>  
  
 <span data-ttu-id="685cf-161">Poiché il servizio Oracle CDC utilizza un solo account di accesso di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per tutti i database CDC e il database MSXDBCDC, è necessario eseguire il mapping di questo account di accesso in tutti questi database.</span><span class="sxs-lookup"><span data-stu-id="685cf-161">Because the Oracle CDC Service uses a single [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login to work with all CDC databases and the MSXDBCDC database, this login should be mapped in all of these databases.</span></span>  
  
### <a name="oracle-cdc-change-consumer"></a><span data-ttu-id="685cf-162">Consumer delle modifiche Oracle CDC</span><span class="sxs-lookup"><span data-stu-id="685cf-162">Oracle CDC Change Consumer</span></span>  
 <span data-ttu-id="685cf-163">Il consumer delle modifiche Oracle CDC è un utente di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] che utilizza le modifiche archiviate nelle tabelle CDC nel database dell'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Oracle CDC.</span><span class="sxs-lookup"><span data-stu-id="685cf-163">The Oracle CDC Change Consumer is a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] user that consumes changes stored in the CDC tables in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Oracle CDC Instance database.</span></span>  
  
 <span data-ttu-id="685cf-164">Determina il ruolo utente richiesto per l'accesso a ogni tabella CDC tramite le funzioni CDC generate dall'infrastruttura di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] CDC.</span><span class="sxs-lookup"><span data-stu-id="685cf-164">This user determines the user role that is required for accessing each of the CDC tables through the CDC functions generated by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] CDC infrastructure.</span></span> <span data-ttu-id="685cf-165">Se non viene specificato alcun ruolo utente quando viene specificata un'istanza di acquisizione, l'accesso alle modifiche è limitato al membro del ruolo predefinito del database **db_owner** del database CDC.</span><span class="sxs-lookup"><span data-stu-id="685cf-165">If no user role is specified when a capture instance is specified, access to the changes is limited to the member of the **db_owner** fixed database role of the CDC database.</span></span>  
  
## <a name="oracle-user-roles"></a><span data-ttu-id="685cf-166">Ruoli utente di Oracle</span><span class="sxs-lookup"><span data-stu-id="685cf-166">Oracle User Roles</span></span>  
 <span data-ttu-id="685cf-167">Di seguito vengono descritti i ruoli utente di Oracle utilizzati dal servizio Oracle CDC.</span><span class="sxs-lookup"><span data-stu-id="685cf-167">The following describes the Oracle user roles used by the Oracle CDC Service.</span></span>  
  
### <a name="database-administrator-dba"></a><span data-ttu-id="685cf-168">Amministratore del database</span><span class="sxs-lookup"><span data-stu-id="685cf-168">Database Administrator (DBA)</span></span>  
 <span data-ttu-id="685cf-169">L'amministratore del database Oracle è un utente del database Oracle.</span><span class="sxs-lookup"><span data-stu-id="685cf-169">The Oracle database administrator (DBA) is an Oracle database user.</span></span> <span data-ttu-id="685cf-170">Tra le attività eseguite dall'amministratore del database Oracle sono incluse le seguenti:</span><span class="sxs-lookup"><span data-stu-id="685cf-170">The tasks performed by the Oracle DBA include:</span></span>  
  
-   <span data-ttu-id="685cf-171">Impostazione del database Oracle di origine per l'utilizzo in modalità ARCHIVELOG.</span><span class="sxs-lookup"><span data-stu-id="685cf-171">Setting the source Oracle database to work in ARCHIVELOG mode.</span></span>  
  
-   <span data-ttu-id="685cf-172">Impostazione di un utente di log mining con le autorizzazioni necessarie.</span><span class="sxs-lookup"><span data-stu-id="685cf-172">Setting up a log mining user with the required permissions.</span></span>  
  
-   <span data-ttu-id="685cf-173">Impostazione della registrazione supplementare per le tabelle acquisite.</span><span class="sxs-lookup"><span data-stu-id="685cf-173">Setting supplemental logging for captured tables.</span></span>  
  
-   <span data-ttu-id="685cf-174">Assistenza nel ripristino dei file di log delle transazioni archiviati che non sono più disponibili per consentirne l'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="685cf-174">Helping to restore archived transaction log files no longer available so they can be processed.</span></span>  
  
 <span data-ttu-id="685cf-175">L'amministratore del database Oracle può ottenere script Oracle SQL da eseguire in modo da poterli valutare prima dell'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="685cf-175">The Oracle database administrator can get Oracle SQL scripts that need to run so they can be evaluated before running them.</span></span> <span data-ttu-id="685cf-176">L'amministratore del database Oracle può inoltre eseguire direttamente script Oracle SQL da Oracle CDC Designer Console.</span><span class="sxs-lookup"><span data-stu-id="685cf-176">The Oracle database administrator can also directly run Oracle SQL scripts from the Oracle CDC Designer console.</span></span>  
  
 <span data-ttu-id="685cf-177">Se l'amministratore del database Oracle sceglie di usare Oracle CDC Designer Console, le credenziali di amministratore non vengono mantenute a eccezione del contesto (finestra di dialogo) in cui vengono usate.</span><span class="sxs-lookup"><span data-stu-id="685cf-177">If the Oracle database administrator chooses to use the Oracle CDC Designer console, administrator's credentials are not kept except for the context (dialog) in which they were used.</span></span>  
  
 <span data-ttu-id="685cf-178">L'amministratore del database Oracle collabora con l'amministratore del servizio Oracle CDC alla configurazione delle istanze di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Oracle CDC.</span><span class="sxs-lookup"><span data-stu-id="685cf-178">The Oracle database administrator works in coordination with the Oracle CDC Service administrator on the configuration of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Oracle CDC Instances.</span></span>  
  
### <a name="log-mining-user"></a><span data-ttu-id="685cf-179">Utente di log mining</span><span class="sxs-lookup"><span data-stu-id="685cf-179">Log Mining User</span></span>  
 <span data-ttu-id="685cf-180">L'utente di log mining Oracle è un utente speciale del database Oracle cui vengono concessi i privilegi necessari per l'accesso e l'elaborazione dei log delle transazioni Oracle.</span><span class="sxs-lookup"><span data-stu-id="685cf-180">The Oracle Log Miner user is a special Oracle database user that is granted the required privileges for accessing and processing the Oracle transaction logs.</span></span>  
  
 <span data-ttu-id="685cf-181">Le credenziali per questo utente vengono archiviate nel database dell'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Oracle CDC mediante la crittografia a chiavi asimmetriche.</span><span class="sxs-lookup"><span data-stu-id="685cf-181">The credentials for this user are stored in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Oracle CDC Instance database using asymmetric key encryption.</span></span> <span data-ttu-id="685cf-182">Sono accessibili solo al servizio Oracle CDC, ma non al proprietario del database dell'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Oracle CDC.</span><span class="sxs-lookup"><span data-stu-id="685cf-182">They are accessible only to the Oracle CDC Service but not to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Oracle CDC Instance database owner.</span></span>  
  
 <span data-ttu-id="685cf-183">Nell'elenco seguente vengono descritti i privilegi che è necessario concedere all'utente di log mining:</span><span class="sxs-lookup"><span data-stu-id="685cf-183">The following list describes the required privileges of the log mining user should be granted:</span></span>  
  
-   <span data-ttu-id="685cf-184">SELECT per \<any-captured-table></span><span class="sxs-lookup"><span data-stu-id="685cf-184">SELECT on \<any-captured-table></span></span>  
  
-   <span data-ttu-id="685cf-185">SELECT ANY TRANSACTION</span><span class="sxs-lookup"><span data-stu-id="685cf-185">SELECT ANY TRANSACTION</span></span>  
  
-   <span data-ttu-id="685cf-186">EXECUTE on DBMS_LOGMNR</span><span class="sxs-lookup"><span data-stu-id="685cf-186">EXECUTE on DBMS_LOGMNR</span></span>  
  
-   <span data-ttu-id="685cf-187">SELECT on V$LOGMNR_CONTENTS</span><span class="sxs-lookup"><span data-stu-id="685cf-187">SELECT on V$LOGMNR_CONTENTS</span></span>  
  
-   <span data-ttu-id="685cf-188">SELECT on V$ARCHIVED_LOG</span><span class="sxs-lookup"><span data-stu-id="685cf-188">SELECT on V$ARCHIVED_LOG</span></span>  
  
-   <span data-ttu-id="685cf-189">SELECT on V$LOG</span><span class="sxs-lookup"><span data-stu-id="685cf-189">SELECT on V$LOG</span></span>  
  
-   <span data-ttu-id="685cf-190">SELECT on V$LOGFILE</span><span class="sxs-lookup"><span data-stu-id="685cf-190">SELECT on V$LOGFILE</span></span>  
  
-   <span data-ttu-id="685cf-191">SELECT on V$DATABASE</span><span class="sxs-lookup"><span data-stu-id="685cf-191">SELECT on V$DATABASE</span></span>  
  
-   <span data-ttu-id="685cf-192">SELECT on V$THREAD</span><span class="sxs-lookup"><span data-stu-id="685cf-192">SELECT on V$THREAD</span></span>  
  
-   <span data-ttu-id="685cf-193">SELECT on V$PARAMETER</span><span class="sxs-lookup"><span data-stu-id="685cf-193">SELECT on V$PARAMETER</span></span>  
  
-   <span data-ttu-id="685cf-194">SELECT on DBA_REGISTRY</span><span class="sxs-lookup"><span data-stu-id="685cf-194">SELECT on DBA_REGISTRY</span></span>  
  
-   <span data-ttu-id="685cf-195">SELECT on ALL_INDEXES</span><span class="sxs-lookup"><span data-stu-id="685cf-195">SELECT on ALL_INDEXES</span></span>  
  
-   <span data-ttu-id="685cf-196">SELECT on ALL_OBJECTS</span><span class="sxs-lookup"><span data-stu-id="685cf-196">SELECT on ALL_OBJECTS</span></span>  
  
-   <span data-ttu-id="685cf-197">SELECT on DBA_OBJECTS</span><span class="sxs-lookup"><span data-stu-id="685cf-197">SELECT on DBA_OBJECTS</span></span>  
  
-   <span data-ttu-id="685cf-198">SELECT on ALL_TABLES</span><span class="sxs-lookup"><span data-stu-id="685cf-198">SELECT on ALL_TABLES</span></span>  
  
 <span data-ttu-id="685cf-199">Se non è possibile concedere alcuni di questi privilegi a un V$xxx, è necessario concederli a V_$xxx.</span><span class="sxs-lookup"><span data-stu-id="685cf-199">If any of these privileges cannot be granted to a V$xxx, then they should be granted to the V $xxx.</span></span>  
  
### <a name="schema-user"></a><span data-ttu-id="685cf-200">Utente dello schema</span><span class="sxs-lookup"><span data-stu-id="685cf-200">Schema User</span></span>  
 <span data-ttu-id="685cf-201">L'utente dello schema Oracle dispone di accesso in lettura allo schema delle tabelle Oracle da acquisire.</span><span class="sxs-lookup"><span data-stu-id="685cf-201">The Oracle Schema User is an Oracle user with read access to the schema of the Oracle tables to be captured.</span></span> <span data-ttu-id="685cf-202">Si tratta di un utente necessario quando si utilizza Oracle CDC Designer Console per recuperare l'elenco dello schema Oracle, tabelle da acquisire con colonne, indici e chiavi associati.</span><span class="sxs-lookup"><span data-stu-id="685cf-202">This user is necessary when working with the Oracle CDC Designer console to retrieve the list of Oracle schema, tables to be captured and their columns, indexes and keys.</span></span>  
  
 <span data-ttu-id="685cf-203">Le credenziali per questo utente non vengono mai archiviate.</span><span class="sxs-lookup"><span data-stu-id="685cf-203">The credentials for this user are never stored.</span></span> <span data-ttu-id="685cf-204">Sono richieste da CDC Designer Console ogni volta che sono necessarie e vengono conservate per la durata delle sessioni dell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="685cf-204">They are requested by the CDC Designer console each time they are needed and they are kept for the rest of the UI sessions.</span></span>  
  
  
