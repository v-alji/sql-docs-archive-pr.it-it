---
title: Inizializzazione immediata dei file di database | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- initializing files [SQL Server]
- instant file initializations [SQL Server]
- fast file initialization (SQL Server)
- file initialization [SQL Server]
ms.assetid: 1ad468f5-4f75-480b-aac6-0b01b048bd67
author: stevestein
ms.author: sstein
ms.openlocfilehash: dedd2c5b8d075dee8aeeb438904137558c664d95
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627810"
---
# <a name="database-instant-file-initialization"></a><span data-ttu-id="b1796-102">Inizializzazione immediata dei file di database</span><span class="sxs-lookup"><span data-stu-id="b1796-102">Database Instant File Initialization</span></span>
  <span data-ttu-id="b1796-103">I file di dati e di log vengono inizializzati per sovrascrivere eventuali dati esistenti rimasti nel disco in seguito all'eliminazione precedente di file.</span><span class="sxs-lookup"><span data-stu-id="b1796-103">Data and log files are initialized to overwrite any existing data left on the disk from previously deleted files.</span></span> <span data-ttu-id="b1796-104">I file di dati e di log vengono innanzitutto inizializzati riempiendo i file con zeri quando si eseguono le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b1796-104">Data and log files are first initialized by filling the files with zeros when you perform one of the following operations:</span></span>  
  
-   <span data-ttu-id="b1796-105">Creare un database.</span><span class="sxs-lookup"><span data-stu-id="b1796-105">Create a database.</span></span>  
  
-   <span data-ttu-id="b1796-106">Aggiunta di file, log o dati a un database esistente.</span><span class="sxs-lookup"><span data-stu-id="b1796-106">Add files, log or data, to an existing database.</span></span>  
  
-   <span data-ttu-id="b1796-107">Aumento delle dimensioni di un file esistente (incluse operazioni di aumento automatico delle dimensioni).</span><span class="sxs-lookup"><span data-stu-id="b1796-107">Increase the size of an existing file (including autogrow operations).</span></span>  
  
-   <span data-ttu-id="b1796-108">Ripristino di un database o un filegroup.</span><span class="sxs-lookup"><span data-stu-id="b1796-108">Restore a database or filegroup.</span></span>  
  
 <span data-ttu-id="b1796-109">L'inizializzazione dei file richiede una quantità di tempo maggiore per l'esecuzione di tali operazioni.</span><span class="sxs-lookup"><span data-stu-id="b1796-109">File initialization causes these operations to take longer.</span></span> <span data-ttu-id="b1796-110">Quando i dati vengono scritti nei file per la prima volta, tuttavia, il sistema operativo non deve riempire i file con zeri.</span><span class="sxs-lookup"><span data-stu-id="b1796-110">However, when data is written to the files for the first time, the operating system does not have to fill the files with zeros.</span></span>  
  
## <a name="instant-file-initialization"></a><span data-ttu-id="b1796-111">Inizializzazione dei file immediata</span><span class="sxs-lookup"><span data-stu-id="b1796-111">Instant File Initialization</span></span>  
 <span data-ttu-id="b1796-112">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]i file di dati possono essere inizializzati immediatamente.</span><span class="sxs-lookup"><span data-stu-id="b1796-112">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], data files can be initialized instantaneously.</span></span> <span data-ttu-id="b1796-113">Questa caratteristica consente l'esecuzione rapida delle operazioni sui file indicate in precedenza.</span><span class="sxs-lookup"><span data-stu-id="b1796-113">This allows for fast execution of the previously mentioned file operations.</span></span> <span data-ttu-id="b1796-114">Tramite l'inizializzazione dei file immediata infatti viene recuperato lo spazio su disco in uso evitando il riempimento di tale spazio con zeri.</span><span class="sxs-lookup"><span data-stu-id="b1796-114">Instant file initialization reclaims used disk space without filling that space with zeros.</span></span> <span data-ttu-id="b1796-115">Il contenuto del disco viene invece sovrascritto via via che nuovi dati vengono scritti nei file.</span><span class="sxs-lookup"><span data-stu-id="b1796-115">Instead, disk content is overwritten as new data is written to the files.</span></span> <span data-ttu-id="b1796-116">Per i file di log non è possibile eseguire l'inizializzazione immediata.</span><span class="sxs-lookup"><span data-stu-id="b1796-116">Log files cannot be initialized instantaneously.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b1796-117">L'inizializzazione immediata dei file è disponibile solo in [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[winxppro](../../includes/winxppro-md.md)] o [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)] o versioni successive.</span><span class="sxs-lookup"><span data-stu-id="b1796-117">Instant file initialization is available only on [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[winxppro](../../includes/winxppro-md.md)] or [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)] or later versions.</span></span>  
  
 <span data-ttu-id="b1796-118">L'inizializzazione immediata dei file è disponibile solo se all'account del servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (MSSQLSERVER) è stato concesso il diritto SE_MANAGE_VOLUME_NAME.</span><span class="sxs-lookup"><span data-stu-id="b1796-118">Instant file initialization is only available if the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (MSSQLSERVER) service account has been granted SE_MANAGE_VOLUME_NAME.</span></span> <span data-ttu-id="b1796-119">I membri del gruppo Administrator di Windows dispongono di questo diritto e possono concederlo ad altri utenti aggiungendoli ai criteri di sicurezza **Esecuzione attività di manutenzione volume** .</span><span class="sxs-lookup"><span data-stu-id="b1796-119">Members of the Windows Administrator group have this right and can grant it to other users by adding them to the **Perform Volume Maintenance Tasks** security policy.</span></span> <span data-ttu-id="b1796-120">Per altre informazioni sull'assegnazione di diritti utente, vedere la documentazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="b1796-120">For more information about assigning user rights, see the Windows documentation.</span></span>  
  
 <span data-ttu-id="b1796-121">L'inizializzazione immediata dei file non è disponibile quando è abilitata la crittografia TDE.</span><span class="sxs-lookup"><span data-stu-id="b1796-121">Instant file initialization is not available when TDE is enabled.</span></span>  
  
 <span data-ttu-id="b1796-122">Per concedere l'autorizzazione `Perform volume maintenance tasks` a un account:</span><span class="sxs-lookup"><span data-stu-id="b1796-122">To grant an account the `Perform volume maintenance tasks` permission:</span></span>  
  
1.  <span data-ttu-id="b1796-123">Nel computer in cui verrà creato il file di backup, aprire l'applicazione `Local Security Policy` (`secpol.msc`).</span><span class="sxs-lookup"><span data-stu-id="b1796-123">On the computer where the backup file will be created, open the `Local Security Policy` application (`secpol.msc`).</span></span>  
  
2.  <span data-ttu-id="b1796-124">Nel riquadro sinistro espandere **Criteri locali**, quindi fare clic su **Assegnazione diritti utente**.</span><span class="sxs-lookup"><span data-stu-id="b1796-124">In the left pane, expand **Local Policies**, and then click **User Rights Assignment**.</span></span>  
  
3.  <span data-ttu-id="b1796-125">Nel riquadro destro fare doppio clic su **Esecuzione attività di manutenzione volume**.</span><span class="sxs-lookup"><span data-stu-id="b1796-125">In the right pane, double-click **Perform volume maintenance tasks**.</span></span>  
  
4.  <span data-ttu-id="b1796-126">Fare clic su **Aggiungi utente o gruppo** e aggiungere tutti gli account utente usati per i backup.</span><span class="sxs-lookup"><span data-stu-id="b1796-126">Click **Add User or Group** and add any user accounts that are used for backups.</span></span>  
  
5.  <span data-ttu-id="b1796-127">Fare clic su **applica**, quindi chiudere tutte le `Local Security Policy` finestre di dialogo.</span><span class="sxs-lookup"><span data-stu-id="b1796-127">Click **Apply**, and then close all `Local Security Policy` dialog boxes.</span></span>  
  
### <a name="security-considerations"></a><span data-ttu-id="b1796-128">Considerazioni relative alla sicurezza</span><span class="sxs-lookup"><span data-stu-id="b1796-128">Security Considerations</span></span>  
 <span data-ttu-id="b1796-129">Poiché il contenuto eliminato del disco viene sovrascritto solo quando vengono scritti nuovi dati nei file, il contenuto eliminato potrebbe essere accessibile a utenti o servizi non autorizzati.</span><span class="sxs-lookup"><span data-stu-id="b1796-129">Because the deleted disk content is overwritten only as new data is written to the files, the deleted content might be accessed by an unauthorized principal.</span></span> <span data-ttu-id="b1796-130">Finché il file di database è collegato all'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], questa minaccia di accesso alle informazioni è ridotta dall'elenco di controllo di accesso discrezionale (DACL) per il file.</span><span class="sxs-lookup"><span data-stu-id="b1796-130">While the database file is attached to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], this information disclosure threat is reduced by the discretionary access control list (DACL) on the file.</span></span> <span data-ttu-id="b1796-131">Questo elenco consente l'accesso al file solo all'account del servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e all'amministratore locale.</span><span class="sxs-lookup"><span data-stu-id="b1796-131">This DACL allows file access only to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service account and the local administrator.</span></span> <span data-ttu-id="b1796-132">Quando il file viene scollegato, tuttavia, diventa accessibile a un utente o a un servizio privo del diritto SE_MANAGE_VOLUME_NAME.</span><span class="sxs-lookup"><span data-stu-id="b1796-132">However, when the file is detached, it may be accessed by a user or service that does not have SE_MANAGE_VOLUME_NAME.</span></span> <span data-ttu-id="b1796-133">Una minaccia analoga è presente quando si esegue il backup del database.</span><span class="sxs-lookup"><span data-stu-id="b1796-133">A similar threat exists when the database is backed up.</span></span> <span data-ttu-id="b1796-134">Il contenuto eliminato può diventare disponibile a un utente o a un servizio non autorizzato se il file di backup non è protetto con un elenco di controllo di accesso discrezionale (DACL) appropriato.</span><span class="sxs-lookup"><span data-stu-id="b1796-134">The deleted content can become available to an unauthorized user or service if the backup file is not protected with an appropriate DACL.</span></span>  
  
 <span data-ttu-id="b1796-135">Se la potenziale diffusione del contenuto eliminato rappresenta un problema, è consigliabile eseguire una o entrambe le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b1796-135">If the potential for disclosing deleted content is a concern, you should do one or both of the following:</span></span>  
  
-   <span data-ttu-id="b1796-136">Assicurarsi sempre che i file di dati e i file di backup scollegati presentino elenchi di controllo di accesso discrezionale (DACL) restrittivi.</span><span class="sxs-lookup"><span data-stu-id="b1796-136">Always make sure that any detached data files and backup files have restrictive DACLs.</span></span>  
  
-   <span data-ttu-id="b1796-137">Disabilitare l'inizializzazione immediata dei file per l'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] revocando il diritto SE_MANAGE_VOLUME_NAME dall'account del servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b1796-137">Disable instant file initialization for the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by revoking SE_MANAGE_VOLUME_NAME from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service account.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b1796-138">La disabilitazione dell'inizializzazione immediata dei file ha effetto solo sui file che sono stati creati o le cui dimensioni sono aumentate dopo la revoca del diritto utente.</span><span class="sxs-lookup"><span data-stu-id="b1796-138">Disabling instant file initialization only affects files that are created or increased in size after the user right is revoked.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1796-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b1796-139">See Also</span></span>  
 [<span data-ttu-id="b1796-140">CREATE DATABASE &#40;SQL Server Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b1796-140">CREATE DATABASE &#40;SQL Server Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-database-sql-server-transact-sql)  
  
  
