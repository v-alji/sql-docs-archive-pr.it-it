---
title: Scrittura di eventi di controllo di SQL Server nel registro di sicurezza | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- logs [SQL Server], Security Log
- server audit [SQL Server]
- audits [SQL Server], writing to Security Log
- security logs [SQL Server]
ms.assetid: 6fabeea3-7a42-4769-a0f3-7e04daada314
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: d59134b278f29c9b604208d8cab7e982144b9c9a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625276"
---
# <a name="write-sql-server-audit-events-to-the-security-log"></a><span data-ttu-id="50217-102">Scrittura di eventi di controllo di SQL Server nel registro di sicurezza</span><span class="sxs-lookup"><span data-stu-id="50217-102">Write SQL Server Audit Events to the Security Log</span></span>
  <span data-ttu-id="50217-103">In un ambiente con sicurezza elevata il registro di sicurezza di Windows rappresenta la posizione appropriata per la scrittura di eventi che registrano l'accesso agli oggetti.</span><span class="sxs-lookup"><span data-stu-id="50217-103">In a high security environment, the Windows Security log is the appropriate location to write events that record object access.</span></span> <span data-ttu-id="50217-104">Sono supportati altre posizioni di controllo che tuttavia sono più soggette alla manomissione.</span><span class="sxs-lookup"><span data-stu-id="50217-104">Other audit locations are supported but are more subject to tampering.</span></span>  
  
 <span data-ttu-id="50217-105">La scrittura dei controlli del server [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] nel registro di sicurezza di Windows prevede due requisiti fondamentali:</span><span class="sxs-lookup"><span data-stu-id="50217-105">There are two key requirements for writing [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] server audits to the Windows Security log:</span></span>  
  
-   <span data-ttu-id="50217-106">È necessario configurare l'impostazione di controllo dell'accesso agli oggetti per l'acquisizione degli eventi.</span><span class="sxs-lookup"><span data-stu-id="50217-106">The audit object access setting must be configured to capture the events.</span></span> <span data-ttu-id="50217-107">Lo strumento dei criteri di controllo (`auditpol.exe`) espone varie impostazioni di criteri secondari nella categoria **controllo dell'accesso agli oggetti** .</span><span class="sxs-lookup"><span data-stu-id="50217-107">The audit policy tool (`auditpol.exe`) exposes a variety of sub-policies settings in the **audit object access** category.</span></span> <span data-ttu-id="50217-108">Per consentire il controllo dell'accesso agli oggetti in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , configurare l'impostazione **generata dall'applicazione** .</span><span class="sxs-lookup"><span data-stu-id="50217-108">To allow [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to audit object access, configure the **application generated** setting.</span></span>  
  
-   <span data-ttu-id="50217-109">L'account in cui viene eseguito il servizio di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] deve disporre dell'autorizzazione **generazione controlli di sicurezza** per scrivere nel registro di sicurezza di Windows.</span><span class="sxs-lookup"><span data-stu-id="50217-109">The account that the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service is running under must have the **generate security audits** permission to write to the Windows Security log.</span></span> <span data-ttu-id="50217-110">Per impostazione predefinita, gli account LOCAL SERVICE e NETWORK SERVICE dispongono di questa autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="50217-110">By default, the LOCAL SERVICE and the NETWORK SERVICE accounts have this permission.</span></span> <span data-ttu-id="50217-111">Questo passaggio non è obbligatorio se [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] viene eseguito in uno di questi account.</span><span class="sxs-lookup"><span data-stu-id="50217-111">This step is not required if [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] is running under one of those accounts.</span></span>  
  
 <span data-ttu-id="50217-112">I criteri di controllo di Windows possono influire sul controllo di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] se sono configurati per scrivere nel registro di sicurezza di Windows. Se i criteri di controllo non sono configurati in modo corretto, potrebbe verificarsi la perdita di eventi.</span><span class="sxs-lookup"><span data-stu-id="50217-112">The Windows audit policy can affect [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] auditing if it is configured to write to the Windows Security log, with the potential of losing events if the audit policy is incorrectly configured.</span></span> <span data-ttu-id="50217-113">In genere il registro di sicurezza di Windows è impostato in modo che gli eventi meno recenti vengano sovrascritti</span><span class="sxs-lookup"><span data-stu-id="50217-113">Typically, the Windows Security log is set to overwrite the older events.</span></span> <span data-ttu-id="50217-114">e vengano mantenuti quelli più recenti.</span><span class="sxs-lookup"><span data-stu-id="50217-114">This preserves the most recent events.</span></span> <span data-ttu-id="50217-115">Tuttavia, se il registro di sicurezza di Windows è impostato in modo diverso e il registro di sicurezza è pieno, verrà generato l'evento di Windows 1104 che indica che il registro è pieno.</span><span class="sxs-lookup"><span data-stu-id="50217-115">However, if the Windows Security log is not set to overwrite older events, then if the Security log is full, the system will issue Windows event 1104 (Log is full).</span></span> <span data-ttu-id="50217-116">A questo punto si verificano le situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="50217-116">At that point:</span></span>  
  
-   <span data-ttu-id="50217-117">Non verranno registrati ulteriori eventi di sicurezza</span><span class="sxs-lookup"><span data-stu-id="50217-117">No further security events will be recorded</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="50217-118">non potrà rilevare che il sistema non è in grado di registrare gli eventi nel registro di sicurezza, causando una perdita potenziale di eventi di controllo</span><span class="sxs-lookup"><span data-stu-id="50217-118">will not be able to detect that the system is not able to record the events in the Security log, resulting in the potential loss of audit events</span></span>  
  
-   <span data-ttu-id="50217-119">Dopo che l'amministratore ha apportato correzioni al registro di sicurezza, il comportamento relativo alla registrazione tornerà normale.</span><span class="sxs-lookup"><span data-stu-id="50217-119">After the box administrator fixes the Security log, the logging behavior will return to normal.</span></span>  
  
 <span data-ttu-id="50217-120">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="50217-120">**In This Topic**</span></span>  
  
-   <span data-ttu-id="50217-121">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="50217-121">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="50217-122">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="50217-122">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="50217-123">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="50217-123">Security</span></span>](#Security)  
  
-   <span data-ttu-id="50217-124">**Per registrare eventi di controllo di SQL Server nel registro di sicurezza:**</span><span class="sxs-lookup"><span data-stu-id="50217-124">**To write SQL Server audit events to the Security Log:**</span></span>  
  
     [<span data-ttu-id="50217-125">Configurare l'impostazione di controllo dell'accesso agli oggetti in Windows mediante auditpol</span><span class="sxs-lookup"><span data-stu-id="50217-125">Configure the audit object access setting in Windows using auditpol</span></span>](#auditpolAccess)  
  
     [<span data-ttu-id="50217-126">Configurare l'impostazione di controllo dell'accesso agli oggetti in Windows mediante secpol</span><span class="sxs-lookup"><span data-stu-id="50217-126">Configure the audit object access setting in Windows using secpol</span></span>](#secpolAccess)  
  
     [<span data-ttu-id="50217-127">Concedere l'autorizzazione di generazione dei controlli di sicurezza a un account mediante secpol</span><span class="sxs-lookup"><span data-stu-id="50217-127">Grant the generate security audits permission to an account using secpol</span></span>](#secpolPermission)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="50217-128">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="50217-128">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="50217-129">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="50217-129">Limitations and Restrictions</span></span>  
 <span data-ttu-id="50217-130">Gli amministratori del computer in cui è in esecuzione [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] devono comprendere che le impostazioni locali relative al registro di sicurezza possono essere sovrascritte da criteri del dominio.</span><span class="sxs-lookup"><span data-stu-id="50217-130">Administrators of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] computer should understand that local settings for the Security log can be overwritten by a domain policy.</span></span> <span data-ttu-id="50217-131">In questo caso i criteri del dominio potrebbero sovrascrivere l'impostazione della sottocategoria (**auditpol/get/subcategory:"application generated"** ).</span><span class="sxs-lookup"><span data-stu-id="50217-131">In this case, the domain policy might overwrite the subcategory setting (**auditpol /get /subcategory:"application generated"**).</span></span> <span data-ttu-id="50217-132">Questa condizione può influire sulla possibilità di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] di registrare eventi senza disporre di alcuna modalità per rilevare che gli eventi che [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] sta tentando di controllare non verranno registrati.</span><span class="sxs-lookup"><span data-stu-id="50217-132">This can affect [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] ability to log events without having any way to detect that the events that [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] is trying to audit are not going to be recorded.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="50217-133">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="50217-133">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="50217-134">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="50217-134">Permissions</span></span>  
 <span data-ttu-id="50217-135">È necessario essere amministratore di Windows per configurare queste impostazioni.</span><span class="sxs-lookup"><span data-stu-id="50217-135">You must be a Windows administrator to configure these settings.</span></span>  
  
##  <a name="to-configure-the-audit-object-access-setting-in-windows-using-auditpol"></a><a name="auditpolAccess"></a> <span data-ttu-id="50217-136">Per configurare l'impostazione di controllo dell'accesso agli oggetti in Windows mediante auditpol</span><span class="sxs-lookup"><span data-stu-id="50217-136">To configure the audit object access setting in Windows using auditpol</span></span>  
  
1.  <span data-ttu-id="50217-137">Aprire un prompt dei comandi con autorizzazioni amministrative.</span><span class="sxs-lookup"><span data-stu-id="50217-137">Open a command prompt with administrative permissions.</span></span>  
  
    1.  <span data-ttu-id="50217-138">Nel menu **Start** scegliere **Tutti i programmi**, **Accessori**, fare clic con il pulsante destro del mouse su **Prompt dei comandi**, quindi fare clic su **Esegui come amministratore**.</span><span class="sxs-lookup"><span data-stu-id="50217-138">On the **Start** menu, point to **All Programs**, point to **Accessories**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>  
  
    2.  <span data-ttu-id="50217-139">Se viene visualizzata la finestra di dialogo **Controllo account utente** , fare clic su **Continua**.</span><span class="sxs-lookup"><span data-stu-id="50217-139">If the **User Account Control** dialog box opens, click **Continue**.</span></span>  
  
2.  <span data-ttu-id="50217-140">Eseguire l'istruzione seguente per abilitare il controllo da [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="50217-140">Execute the following statement to enable auditing from [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
    ```  
    auditpol /set /subcategory:"application generated" /success:enable /failure:enable  
    ```  
  
3.  <span data-ttu-id="50217-141">Chiudere la finestra del prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="50217-141">Close the command prompt window.</span></span>  
  
##  <a name="to-grant-the-generate-security-audits-permission-to-an-account-using-secpol"></a><a name="secpolAccess"></a> <span data-ttu-id="50217-142">Per concedere l'autorizzazione di generazione dei controlli di sicurezza a un account mediante secpol</span><span class="sxs-lookup"><span data-stu-id="50217-142">To grant the generate security audits permission to an account using secpol</span></span>  
  
1.  <span data-ttu-id="50217-143">Per qualsiasi sistema operativo Windows, scegliere **Esegui** dal menu **Start**.</span><span class="sxs-lookup"><span data-stu-id="50217-143">For any Windows operating system, on the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="50217-144">Digitare **secpol.msc** , quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="50217-144">Type **secpol.msc** and then click **OK**.</span></span> <span data-ttu-id="50217-145">Se viene visualizzata la finestra di dialogo **Controllo account utente** , fare clic su **Continua**.</span><span class="sxs-lookup"><span data-stu-id="50217-145">If the **User Access Control** dialog box appears, click **Continue**.</span></span>  
  
3.  <span data-ttu-id="50217-146">Nello strumento Criteri di sicurezza locale espandere **Impostazioni di sicurezza**, **Criteri locali**, quindi fare clic su **Assegnazione diritti utente**.</span><span class="sxs-lookup"><span data-stu-id="50217-146">In the Local Security Policy tool, expand **Security Settings**, expand **Local Policies**, and then click **User Rights Assignment**.</span></span>  
  
4.  <span data-ttu-id="50217-147">Nel riquadro dei risultati fare doppio clic su **Generazione di controlli di sicurezza**.</span><span class="sxs-lookup"><span data-stu-id="50217-147">In the results pane, double-click **Generate security audits**.</span></span>  
  
5.  <span data-ttu-id="50217-148">Nella scheda **Impostazioni di sicurezza locali** fare clic su **Aggiungi utente o gruppo**.</span><span class="sxs-lookup"><span data-stu-id="50217-148">On the **Local Security Setting** tab, click **Add User or Group**.</span></span>  
  
6.  <span data-ttu-id="50217-149">Nella finestra di dialogo **Seleziona utenti, computer o gruppi** digitare il nome dell'account utente, ad esempio **dominio1\utente1** , quindi fare clic su **OK**oppure su **Avanzate** e cercare l'account.</span><span class="sxs-lookup"><span data-stu-id="50217-149">In the **Select Users, Computers, or Groups** dialog box, either type the name of the user account, such as **domain1\user1** and then click **OK**, or click **Advanced** and search for the account.</span></span>  
  
7.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
8.  <span data-ttu-id="50217-150">Chiudere lo strumento Criteri di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="50217-150">Close the Security Policy tool.</span></span>  
  
9. <span data-ttu-id="50217-151">Riavviare [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] per abilitare questa impostazione.</span><span class="sxs-lookup"><span data-stu-id="50217-151">Restart [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to enable this setting.</span></span>  
  
##  <a name="to-configure-the-audit-object-access-setting-in-windows-using-secpol"></a><a name="secpolPermission"></a> <span data-ttu-id="50217-152">Per configurare l'impostazione di controllo dell'accesso agli oggetti in Windows mediante secpol</span><span class="sxs-lookup"><span data-stu-id="50217-152">To configure the audit object access setting in Windows using secpol</span></span>  
  
1.  <span data-ttu-id="50217-153">Se si utilizza un sistema operativo precedente a [!INCLUDE[wiprlhext](../../../includes/wiprlhext-md.md)] o Windows Server 2008, scegliere **Esegui** dal menu **Start**.</span><span class="sxs-lookup"><span data-stu-id="50217-153">If the operating system is earlier than [!INCLUDE[wiprlhext](../../../includes/wiprlhext-md.md)] or Windows Server 2008, on the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="50217-154">Digitare **secpol.msc** , quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="50217-154">Type **secpol.msc** and then click **OK**.</span></span> <span data-ttu-id="50217-155">Se viene visualizzata la finestra di dialogo **Controllo account utente** , fare clic su **Continua**.</span><span class="sxs-lookup"><span data-stu-id="50217-155">If the **User Access Control** dialog box appears, click **Continue**.</span></span>  
  
3.  <span data-ttu-id="50217-156">Nello strumento Criteri di sicurezza locale espandere **Impostazioni di sicurezza**, **Criteri locali**, quindi fare clic su **Criteri di controllo**.</span><span class="sxs-lookup"><span data-stu-id="50217-156">In the Local Security Policy tool, expand **Security Settings**, expand **Local Policies**, and then click **Audit Policy**.</span></span>  
  
4.  <span data-ttu-id="50217-157">Nel riquadro dei risultati fare doppio clic su **Controlla accesso agli oggetti**.</span><span class="sxs-lookup"><span data-stu-id="50217-157">In the results pane, double-click **Audit object access**.</span></span>  
  
5.  <span data-ttu-id="50217-158">Nella scheda **Impostazioni di sicurezza locali** , nell'area **Controlla i seguenti tentativi** selezionare sia **Esito positivo** sia **Esito negativo**.</span><span class="sxs-lookup"><span data-stu-id="50217-158">On the **Local Security Setting** tab, in the **Audit these attempts** area, select both **Success** and **Failure**.</span></span>  
  
6.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
7.  <span data-ttu-id="50217-159">Chiudere lo strumento Criteri di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="50217-159">Close the Security Policy tool.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50217-160">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="50217-160">See Also</span></span>  
 [<span data-ttu-id="50217-161">SQL Server Audit &#40;Database Engine&#41;</span><span class="sxs-lookup"><span data-stu-id="50217-161">SQL Server Audit &#40;Database Engine&#41;</span></span>](sql-server-audit-database-engine.md)  
  
  
