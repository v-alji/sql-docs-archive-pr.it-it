---
title: Creare un controllo del server e una specifica del controllo del server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- SQL12.SWB.SQLAUDIT.FILTER.F1
- sql12.swb.sqlaudit.srvaudit.general.f1
- sql12.swb.sqlaudit.general.f1
helpviewer_keywords:
- server audit [SQL Server]
- audits [SQL Server], specification
ms.assetid: 6624b1ab-7ec8-44ce-8292-397edf644394
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: a648a975ae9f2c4139a8ebd584f6998f4d0fa1a0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716195"
---
# <a name="create-a-server-audit-and-server-audit-specification"></a><span data-ttu-id="d8e7f-102">Creazione di un controllo del server e di una specifica del controllo del server</span><span class="sxs-lookup"><span data-stu-id="d8e7f-102">Create a Server Audit and Server Audit Specification</span></span>
  <span data-ttu-id="d8e7f-103">In questo argomento viene illustrato come creare un controllo del server e la specifica di un controllo del server in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d8e7f-103">This topic describes how to create a server audit and server audit specification in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="d8e7f-104">Il*controllo* di un'istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] o di un database di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] comporta il rilevamento e la registrazione di eventi che si verificano nel sistema.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-104">*Auditing* an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] or a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] database involves tracking and logging events that occur on the system.</span></span> <span data-ttu-id="d8e7f-105">L'oggetto *SQL Server Audit* raccoglie un'unica istanza di azioni a livello di server o di database e gruppi di azioni da monitorare.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-105">The *SQL Server Audit* object collects a single instance of server- or database-level actions and groups of actions to monitor.</span></span> <span data-ttu-id="d8e7f-106">Il controllo si trova a livello dell'istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d8e7f-106">The audit is at the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance level.</span></span> <span data-ttu-id="d8e7f-107">Per ogni istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] è possibile disporre di più controlli.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-107">You can have multiple audits per [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="d8e7f-108">L'oggetto *specifica controllo server* appartiene a un controllo.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-108">The *Server Audit Specification* object belongs to an audit.</span></span> <span data-ttu-id="d8e7f-109">È possibile creare una specifica del controllo del server per ogni controllo, poiché entrambi vengono creati nell'ambito dell'istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d8e7f-109">You can create one server audit specification per audit, because both are created at the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance scope.</span></span> <span data-ttu-id="d8e7f-110">Per altre informazioni, vedere [SQL Server Audit &#40;Motore di database&#41;](sql-server-audit-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="d8e7f-110">For more information, see [SQL Server Audit &#40;Database Engine&#41;](sql-server-audit-database-engine.md).</span></span>  
  
 <span data-ttu-id="d8e7f-111">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="d8e7f-111">**In This Topic**</span></span>  
  
-   <span data-ttu-id="d8e7f-112">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="d8e7f-112">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="d8e7f-113">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="d8e7f-113">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="d8e7f-114">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="d8e7f-114">Security</span></span>](#Security)  
  
-   <span data-ttu-id="d8e7f-115">**Per creare un controllo del server e una specifica del controllo del server utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="d8e7f-115">**To create a server audit and server audit specification, using:**</span></span>  
  
     [<span data-ttu-id="d8e7f-116">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d8e7f-116">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="d8e7f-117">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d8e7f-117">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="d8e7f-118">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="d8e7f-118">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="d8e7f-119">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="d8e7f-119">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="d8e7f-120">È necessario che un controllo esista prima che sia possibile creare la specifica del controllo del server.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-120">An audit must exist before creating a server audit specification for it.</span></span> <span data-ttu-id="d8e7f-121">Quando viene creata una specifica del controllo del server, il relativo stato è disabilitato.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-121">When a server audit specification is created, it is in a disabled state.</span></span>  
  
-   <span data-ttu-id="d8e7f-122">L'istruzione CREATE SERVER AUDIT è nell'ambito di una transazione.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-122">The CREATE SERVER AUDIT statement is in a transaction's scope.</span></span> <span data-ttu-id="d8e7f-123">L'esecuzione del rollback della transazione comporta il rollback anche per l'istruzione.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-123">If the transaction is rolled back, the statement is also rolled back.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="d8e7f-124">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="d8e7f-124">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="d8e7f-125">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="d8e7f-125">Permissions</span></span>  
  
-   <span data-ttu-id="d8e7f-126">Per creare, modificare o eliminare un controllo del server, le entità devono disporre dell'autorizzazione ALTER ANY SERVER AUDIT o CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-126">To create, alter, or drop a server audit, principals require the ALTER ANY SERVER AUDIT or the CONTROL SERVER permission.</span></span>  
  
-   <span data-ttu-id="d8e7f-127">Gli utenti che dispongono dell'autorizzazione ALTER ANY SERVER AUDIT possono creare specifiche del controllo del server e associarle a qualsiasi controllo.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-127">Users with the ALTER ANY SERVER AUDIT permission can create server audit specifications and bind them to any audit.</span></span>  
  
-   <span data-ttu-id="d8e7f-128">Dopo essere stata creata, la specifica del controllo del server può essere visualizzata dalle entità con autorizzazione CONTROL SERVER o ALTER ANY SERVER AUDIT, dell'account sysadmin oppure dalle entità che possono accedere esplicitamente al controllo.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-128">After a server audit specification is created, it can be viewed by principals with the CONTROL SERVER or ALTER ANY SERVER AUDIT permissions, the sysadmin account, or principals having explicit access to the audit.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="d8e7f-129">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d8e7f-129">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-server-audit"></a><span data-ttu-id="d8e7f-130">Per creare un controllo del server</span><span class="sxs-lookup"><span data-stu-id="d8e7f-130">To create a server audit</span></span>  
  
1.  <span data-ttu-id="d8e7f-131">In Esplora oggetti espandere la cartella **Sicurezza** .</span><span class="sxs-lookup"><span data-stu-id="d8e7f-131">In Object Explorer, expand the **Security** folder.</span></span>  
  
2.  <span data-ttu-id="d8e7f-132">Fare clic con il pulsante destro del mouse sulla cartella **Controlli** e scegliere **Nuovo controllo...** .</span><span class="sxs-lookup"><span data-stu-id="d8e7f-132">Right-click the **Audits** folder and select **New Audit...**.</span></span>  
  
     <span data-ttu-id="d8e7f-133">Nella pagina **Generale** della finestra di dialogo **Crea controllo** sono disponibili le opzioni indicate di seguito.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-133">The following options are available on the **General** page of the **Create Audit** dialog box.</span></span>  
  
     <span data-ttu-id="d8e7f-134">**Nome controllo**</span><span class="sxs-lookup"><span data-stu-id="d8e7f-134">**Audit name**</span></span>  
     <span data-ttu-id="d8e7f-135">Nome del controllo.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-135">The name of the audit.</span></span> <span data-ttu-id="d8e7f-136">Tale nome viene generato automaticamente quando si crea un nuovo controllo, ma è modificabile.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-136">This is generated automatically when you create a new audit but is editable.</span></span>  
  
     <span data-ttu-id="d8e7f-137">**Ritardo coda (in millisecondi)**</span><span class="sxs-lookup"><span data-stu-id="d8e7f-137">**Queue delay (in milliseconds)**</span></span>  
     <span data-ttu-id="d8e7f-138">Indica la quantità di tempo in millisecondi che può trascorrere prima che venga forzata l'elaborazione delle azioni di controllo.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-138">Specifies the amount of time in milliseconds that can elapse before audit actions are forced to be processed.</span></span>  <span data-ttu-id="d8e7f-139">Il valore 0 indica un recapito sincrono.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-139">A value of 0 indicates synchronous delivery.</span></span> <span data-ttu-id="d8e7f-140">Il valore minimo predefinito è **1000** (1 secondo).</span><span class="sxs-lookup"><span data-stu-id="d8e7f-140">The default minimum value is **1000** (1 second).</span></span> <span data-ttu-id="d8e7f-141">Il valore massimo è 2.147.483.647 (2.147.483,647 secondi o 24 giorni, 20 ore, 31 minuti e 23,647 secondi).</span><span class="sxs-lookup"><span data-stu-id="d8e7f-141">The maximum is 2,147,483,647 (2,147,483.647 seconds or 24 days, 20 hours, 31 minutes, 23.647 seconds).</span></span>  
  
     <span data-ttu-id="d8e7f-142">**In caso di errore del log di controllo:**</span><span class="sxs-lookup"><span data-stu-id="d8e7f-142">**On Audit Log Failure:**</span></span>  
     <span data-ttu-id="d8e7f-143">**Continua**</span><span class="sxs-lookup"><span data-stu-id="d8e7f-143">**Continue**</span></span>  
     [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="d8e7f-144">Le operazioni di SQL Server continuano.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-144">operations continue.</span></span> <span data-ttu-id="d8e7f-145">I record di controllo non vengono mantenuti.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-145">Audit records are not retained.</span></span> <span data-ttu-id="d8e7f-146">Il controllo consente di continuare il tentativo di registrazione di eventi e verrà ripreso se viene risolta la condizione di errore.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-146">The audit continues to attempt to log events and will resume if the failure condition is resolved.</span></span> <span data-ttu-id="d8e7f-147">Selezionando l'opzione **Continua** si potrà consentire un'attività non certificata che potrebbe violare i criteri di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-147">Selecting the **Continue** option can allow unaudited activity which could violate your security policies.</span></span> <span data-ttu-id="d8e7f-148">Selezionare questa opzione quando il funzionamento del [!INCLUDE[ssDE](../../../includes/ssde-md.md)] è più importante della gestione di un controllo completo.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-148">Select this option when continuing operation of the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] is more important than maintaining a complete audit.</span></span> <span data-ttu-id="d8e7f-149">Si tratta della selezione predefinita.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-149">This is the default selection.</span></span>  
  
     <span data-ttu-id="d8e7f-150">**Arresta server**</span><span class="sxs-lookup"><span data-stu-id="d8e7f-150">**Shut down server**</span></span>  
     <span data-ttu-id="d8e7f-151">Viene forzata la chiusura del server quando risulta impossibile scrivere dati nella destinazione di controllo da parte dell'istanza del server preposta a tale compito.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-151">Forces a server shut down when the server instance writing to the target cannot write data to the audit target.</span></span> <span data-ttu-id="d8e7f-152">L'account di accesso che esegue questa operazione deve disporre dell'autorizzazione `SHUTDOWN`.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-152">The login issuing this must have the `SHUTDOWN` permission.</span></span> <span data-ttu-id="d8e7f-153">In caso contrario, questa funzione non verrà eseguita e verrà generato un messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-153">If the logon does not have this permission, this function will fail and an error message will be raised.</span></span> <span data-ttu-id="d8e7f-154">Non viene generato alcun evento controllato.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-154">No audited events occur.</span></span> <span data-ttu-id="d8e7f-155">Selezionare questa opzione quando un errore a livello di controllo potrebbe compromettere la sicurezza o l'integrità del sistema.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-155">Select this option when an audit failure could compromise the security or integrity of the system.</span></span>  
  
     <span data-ttu-id="d8e7f-156">**Errore operazione**</span><span class="sxs-lookup"><span data-stu-id="d8e7f-156">**Fail operation**</span></span>  
     <span data-ttu-id="d8e7f-157">Nei casi in cui non è possibile scrivere nel log di controllo tramite [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Audit, questa opzione può impedire le azioni del database qualora provocassero eventi controllati.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-157">In cases where the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Audit cannot write to the audit log this option causes database actions to fail if they would otherwise cause audited events.</span></span> <span data-ttu-id="d8e7f-158">Non viene generato alcun evento controllato.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-158">No audited events occur.</span></span> <span data-ttu-id="d8e7f-159">Le azioni che non provocano eventi controllati possono continuare.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-159">Actions which do not cause audited events can continue.</span></span> <span data-ttu-id="d8e7f-160">Il controllo consente di continuare il tentativo di registrazione di eventi e verrà ripreso se viene risolta la condizione di errore.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-160">The audit continues to attempt to log events and will resume if the failure condition is resolved.</span></span> <span data-ttu-id="d8e7f-161">Selezionare questa opzione quando la gestione di un controllo completo è più importante dell'accesso completo al [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d8e7f-161">Select this option when maintaining a complete audit is more important than full access to the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="d8e7f-162">Quando il controllo è in uno stato di errore, l'esecuzione di eventi controllati può continuare tramite la connessione amministrativa dedicata.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-162">When the audit is in a failed state, the Dedicated Administrator Connection can continue to perform audited events.</span></span>  
  
     <span data-ttu-id="d8e7f-163">Elenco**Destinazione controllo**</span><span class="sxs-lookup"><span data-stu-id="d8e7f-163">**Audit destination** list</span></span>  
     <span data-ttu-id="d8e7f-164">Indica la destinazione per i dati del controllo.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-164">Specifies the target for auditing data.</span></span> <span data-ttu-id="d8e7f-165">Le opzioni disponibili sono un file binario, il registro applicazioni di Windows o il registro di sicurezza di Windows.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-165">The available options are a binary file, the Windows Application log, or the Windows Security log.</span></span> [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="d8e7f-166">Se non si configurano impostazioni aggiuntive in Windows, non sarà possibile scrivere nel registro di sicurezza di Windows.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-166">cannot write to the Windows Security log without configuring additional settings in Windows.</span></span> <span data-ttu-id="d8e7f-167">Per altre informazioni, vedere [Scrivere eventi di controllo di SQL Server nel registro di sicurezza](write-sql-server-audit-events-to-the-security-log.md).</span><span class="sxs-lookup"><span data-stu-id="d8e7f-167">For more information, see [Write SQL Server Audit Events to the Security Log](write-sql-server-audit-events-to-the-security-log.md).</span></span>  
  
     <span data-ttu-id="d8e7f-168">**Percorso file**</span><span class="sxs-lookup"><span data-stu-id="d8e7f-168">**File path**</span></span>  
     <span data-ttu-id="d8e7f-169">Indica il percorso della cartella in cui vengono scritti i dati del controllo quando in **Destinazione controllo** è specificato un file.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-169">Specifies the location of the folder where audit data is written when the **Audit destination** is a file.</span></span>  
  
     <span data-ttu-id="d8e7f-170">**Puntini di sospensione (...)**</span><span class="sxs-lookup"><span data-stu-id="d8e7f-170">**Ellipsis (...)**</span></span>  
     <span data-ttu-id="d8e7f-171">Apre la finestra di dialogo **Individua cartella-**_server_name_ per specificare un percorso di file o creare una cartella in cui viene scritto il file di controllo.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-171">Opens the **Locate Folder -**_server_name_ dialog box to specify a file path or create a folder where the audit file is written.</span></span>  
  
     <span data-ttu-id="d8e7f-172">**Limite massimo di file di controllo:**</span><span class="sxs-lookup"><span data-stu-id="d8e7f-172">**Audit File Maximum Limit:**</span></span>  
     <span data-ttu-id="d8e7f-173">**Numero massimo file di rollover**</span><span class="sxs-lookup"><span data-stu-id="d8e7f-173">**Maximum rollover files**</span></span>  
     <span data-ttu-id="d8e7f-174">Specifica che quando viene raggiunto il numero massimo di file di controllo, i file di controllo meno recenti vengono sovrascritti dal nuovo contenuto del file.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-174">Specifies that, when the maximum number of audit files is reached, the oldest audit files are overwritten by new file content.</span></span>  
  
     <span data-ttu-id="d8e7f-175">**Numero massimo di file**</span><span class="sxs-lookup"><span data-stu-id="d8e7f-175">**Maximum files**</span></span>  
     <span data-ttu-id="d8e7f-176">Specifica che quando viene raggiunto il numero massimo di file di controllo, qualsiasi azione che causa la generazione di eventi di controllo aggiuntivi avrà esito negativo e verrà visualizzato un errore.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-176">Specifies that, when the maximum number of audit files is reached, any action that causes additional audit events to be generated will fail with an error.</span></span>  
  
     <span data-ttu-id="d8e7f-177">Casella di controllo**Senza limiti**</span><span class="sxs-lookup"><span data-stu-id="d8e7f-177">**Unlimited** check box</span></span>  
     <span data-ttu-id="d8e7f-178">Quando si seleziona la casella di controllo **Senza limiti** in **Numero massimo file di rollover** , non viene applicato alcun limite al numero di file di controllo che verranno creati.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-178">When the **Unlimited** check box under **Maximum rollover files** is selected, there is no limit imposed on the number of audit files that will be created.</span></span> <span data-ttu-id="d8e7f-179">La casella di controllo **Senza limiti** viene selezionata per impostazione predefinita e si applica alle selezioni **Numero massimo file di rollover** e **Numero massimo di file** .</span><span class="sxs-lookup"><span data-stu-id="d8e7f-179">The **Unlimited** check box is selected by default and applies to both the **Maximum rollover files** and **Maximum files** selections.</span></span>  
  
     <span data-ttu-id="d8e7f-180">Casella**Numero di file**</span><span class="sxs-lookup"><span data-stu-id="d8e7f-180">**Number of files** box</span></span>  
     <span data-ttu-id="d8e7f-181">Specifica il numero di file di controllo da creare, fino a un massimo di 2.147.483.647.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-181">Specifies the number of audit files to be created, up to 2,147,483,647.</span></span> <span data-ttu-id="d8e7f-182">Questa opzione è disponibile solo se non è selezionato **Senza limiti** .</span><span class="sxs-lookup"><span data-stu-id="d8e7f-182">This option is only available if **Unlimited** is unchecked.</span></span>  
  
     <span data-ttu-id="d8e7f-183">**Dimensioni massime del file**</span><span class="sxs-lookup"><span data-stu-id="d8e7f-183">**Maximum file size**</span></span>  
     <span data-ttu-id="d8e7f-184">Specifica la dimensione massima per un file di controllo in megabyte (MB), gigabyte (GB) o terabyte (TB).</span><span class="sxs-lookup"><span data-stu-id="d8e7f-184">Specifies the maximum size for an audit file in either megabytes (MB), gigabytes (GB), or terabytes (TB).</span></span> <span data-ttu-id="d8e7f-185">È possibile specificare una dimensione compresa tra 1024 MB e 2.147.483.647 TB.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-185">You can specify between 1024 MB and 2,147,483,647 TB.</span></span> <span data-ttu-id="d8e7f-186">Se si seleziona la casella di controllo **Senza limiti** non si impono alcun limite alle dimensioni del file.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-186">Selecting the **Unlimited** check box does not place a limit on the size of the file.</span></span> <span data-ttu-id="d8e7f-187">Se si specifica un valore minore di 1024 MB, verrà restituito un errore.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-187">Specifying a value lower than 1024 MB will fail, returning an error.</span></span> <span data-ttu-id="d8e7f-188">La casella di controllo **Senza limiti** è selezionata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-188">The **Unlimited** check box is selected by default.</span></span>  
  
     <span data-ttu-id="d8e7f-189">Casella di controllo**Riserva spazio su disco**</span><span class="sxs-lookup"><span data-stu-id="d8e7f-189">**Reserve disk space** check box</span></span>  
     <span data-ttu-id="d8e7f-190">Indica che sul disco viene preallocata una quantità di spazio uguale alle dimensioni massime del file specificate.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-190">Specifies that space is pre-allocated on the disk equal to the specified maximum file size.</span></span> <span data-ttu-id="d8e7f-191">Questa impostazione può essere utilizzata solo se non è selezionata la casella di controllo **Senza limiti** in **Dimensioni massime file** .</span><span class="sxs-lookup"><span data-stu-id="d8e7f-191">This setting can only be used if the **Unlimited** check box under **Maximum file size** is not selected.</span></span> <span data-ttu-id="d8e7f-192">Questa casella di controllo non è selezionata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-192">This check box is not selected by default.</span></span>  
  
3.  <span data-ttu-id="d8e7f-193">Facoltativamente, nella pagina **Filtro** , immettere un predicato o clausola `WHERE` per il controllo del server per specificare opzioni aggiuntive non disponibili nella pagina **Generale** .</span><span class="sxs-lookup"><span data-stu-id="d8e7f-193">Optionally, on the **Filter** page, enter a predicate, or `WHERE` clause, to the server audit to specify additional options not available from the **General** page.</span></span> <span data-ttu-id="d8e7f-194">Racchiudere il predicato tra le parentesi, ad esempio `(object_name = 'EmployeesTable')`.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-194">Enclose the predicate in parentheses; for example: `(object_name = 'EmployeesTable')`.</span></span>  
  
4.  <span data-ttu-id="d8e7f-195">Una volta selezionate le opzioni, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-195">When you are finished selecting options, click **OK**.</span></span>  
  
#### <a name="to-create-a-server-audit-specification"></a><span data-ttu-id="d8e7f-196">Per creare una specifica del controllo del server</span><span class="sxs-lookup"><span data-stu-id="d8e7f-196">To create a server audit specification</span></span>  
  
1.  <span data-ttu-id="d8e7f-197">In Esplora oggetti fare clic sul segno più per espandere la cartella **Sicurezza** .</span><span class="sxs-lookup"><span data-stu-id="d8e7f-197">In Object Explorer, click the plus sign to expand the **Security** folder.</span></span>  
  
2.  <span data-ttu-id="d8e7f-198">Fare clic con il pulsante destro del mouse sulla cartella **Specifiche controllo server** e selezionare **Nuova specifica controllo server...** .</span><span class="sxs-lookup"><span data-stu-id="d8e7f-198">Right-click the **Server Audit Specifications** folder and select **New Server Audit Specification...**.</span></span>  
  
     <span data-ttu-id="d8e7f-199">Nella finestra di dialogo **Crea specifica controllo server** sono disponibili le opzioni indicate di seguito.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-199">The following options are available on the **Create Server Audit Specification** dialog box.</span></span>  
  
     <span data-ttu-id="d8e7f-200">**Nome**</span><span class="sxs-lookup"><span data-stu-id="d8e7f-200">**Name**</span></span>  
     <span data-ttu-id="d8e7f-201">Nome della specifica del controllo del server.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-201">The name of the server audit specification.</span></span> <span data-ttu-id="d8e7f-202">Tale nome viene generato automaticamente quando si crea una nuova specifica del controllo del server, ma è modificabile.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-202">This is generated automatically when you create a new server audit specification but is editable.</span></span>  
  
     <span data-ttu-id="d8e7f-203">**Controllo**</span><span class="sxs-lookup"><span data-stu-id="d8e7f-203">**Audit**</span></span>  
     <span data-ttu-id="d8e7f-204">Nome di un controllo server esistente.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-204">The name of an existing server audit.</span></span> <span data-ttu-id="d8e7f-205">Digitare il nome del controllo o selezionarlo nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-205">Either type in the name of the audit or select it from the list.</span></span>  
  
     <span data-ttu-id="d8e7f-206">**Tipo di azione di controllo**</span><span class="sxs-lookup"><span data-stu-id="d8e7f-206">**Audit Action Type**</span></span>  
     <span data-ttu-id="d8e7f-207">Specifica i gruppi di azioni di controllo a livello di server e le azioni di controllo da acquisire.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-207">Specifies the server-level audit action groups and audit actions to capture.</span></span> <span data-ttu-id="d8e7f-208">Per l'elenco di gruppi di azioni di controllo a livello di server e di azioni di controllo e una descrizione degli eventi contenuti, vedere [Azioni e gruppi di azioni di SQL Server Audit](sql-server-audit-action-groups-and-actions.md).</span><span class="sxs-lookup"><span data-stu-id="d8e7f-208">For the list of server-level audit action groups and audit actions and a description of the events they contain, see [SQL Server Audit Action Groups and Actions](sql-server-audit-action-groups-and-actions.md).</span></span>  
  
     <span data-ttu-id="d8e7f-209">**Schema dell'oggetto**</span><span class="sxs-lookup"><span data-stu-id="d8e7f-209">**Object Schema**</span></span>  
     <span data-ttu-id="d8e7f-210">Consente di visualizzare lo schema per il **nome oggetto**specificato.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-210">Displays the schema for the specified **Object Name**.</span></span>  
  
     <span data-ttu-id="d8e7f-211">**nome oggetto**</span><span class="sxs-lookup"><span data-stu-id="d8e7f-211">**Object Name**</span></span>  
     <span data-ttu-id="d8e7f-212">Nome dell'oggetto da controllare.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-212">The name of the object to audit.</span></span> <span data-ttu-id="d8e7f-213">Tale opzione è disponibile solo per le azioni di controllo e non si applica ai gruppi di controllo.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-213">This is only available for audit actions; it does not apply to audit groups.</span></span>  
  
     <span data-ttu-id="d8e7f-214">**Puntini di sospensione (...)**</span><span class="sxs-lookup"><span data-stu-id="d8e7f-214">**Ellipsis (...)**</span></span>  
     <span data-ttu-id="d8e7f-215">Consente di visualizzare la finestra di dialogo **Seleziona oggetti** per eseguire la ricerca e la selezione di un oggetto disponibile, in base all'opzione **Tipo di azione di controllo**.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-215">Opens the **Select Objects** dialog to browse for and select an available object, based on the specified **Audit Action Type**.</span></span>  
  
     <span data-ttu-id="d8e7f-216">**Nome entità**</span><span class="sxs-lookup"><span data-stu-id="d8e7f-216">**Principal Name**</span></span>  
     <span data-ttu-id="d8e7f-217">Account per filtrare il controllo per l'oggetto da controllare.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-217">The account to filter the audit by for the object being audited.</span></span>  
  
     <span data-ttu-id="d8e7f-218">**Puntini di sospensione (...)**</span><span class="sxs-lookup"><span data-stu-id="d8e7f-218">**Ellipsis (...)**</span></span>  
     <span data-ttu-id="d8e7f-219">Viene visualizzata la finestra di dialogo **Seleziona oggetti** per eseguire la ricerca e selezionare un oggetto disponibile, in base all'opzione **Nome oggetto**specificata.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-219">Opens the **Select Objects** dialog to browse for and select an available object, based on the specified **Object Name**.</span></span>  
  
3.  <span data-ttu-id="d8e7f-220">Al termine, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-220">When you are finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="d8e7f-221">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d8e7f-221">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-server-audit"></a><span data-ttu-id="d8e7f-222">Per creare un controllo del server</span><span class="sxs-lookup"><span data-stu-id="d8e7f-222">To create a server audit</span></span>  
  
1.  <span data-ttu-id="d8e7f-223">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d8e7f-223">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="d8e7f-224">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-224">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="d8e7f-225">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-225">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Creates a server audit called "HIPAA_Audit" with a binary file as the target and no options.  
    CREATE SERVER AUDIT HIPAA_Audit  
        TO FILE ( FILEPATH ='\\SQLPROD_1\Audit\' );  
    ```  
  
#### <a name="to-create-a-server-audit-specification"></a><span data-ttu-id="d8e7f-226">Per creare una specifica del controllo del server</span><span class="sxs-lookup"><span data-stu-id="d8e7f-226">To create a server audit specification</span></span>  
  
1.  <span data-ttu-id="d8e7f-227">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d8e7f-227">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="d8e7f-228">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-228">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="d8e7f-229">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="d8e7f-229">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    /*Creates a server audit specification called "HIPAA_Audit_Specification" that audits failed logins for the SQL Server audit "HIPAA_Audit" created above.  
    */  
  
    CREATE SERVER AUDIT SPECIFICATION HIPAA_Audit_Specification  
    FOR SERVER AUDIT HIPAA_Audit  
        ADD (FAILED_LOGIN_GROUP);  
    GO  
    -- Enables the audit.   
  
    ALTER SERVER AUDIT HIPAA_Audit  
    WITH (STATE = ON);  
    GO  
    ```  
  
 <span data-ttu-id="d8e7f-230">Per altre informazioni, vedere [CREATE SERVER AUDIT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-server-audit-transact-sql) e [CREATE SERVER AUDIT SPECIFICATION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-server-audit-specification-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="d8e7f-230">For more information, see [CREATE SERVER AUDIT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-server-audit-transact-sql) and [CREATE SERVER AUDIT SPECIFICATION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-server-audit-specification-transact-sql).</span></span>  
  
  
