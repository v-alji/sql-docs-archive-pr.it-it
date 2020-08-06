---
title: Eseguire una valutazione su richiesta utilizzando Server registrati | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
ms.assetid: c14034ef-6e0b-4df5-8072-bfb8d90b3172
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: a3a06efaabff7e94e5b560744f0e1c739831042a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623664"
---
# <a name="perform-an-on-demand-evaluation-by-using-registered-servers"></a><span data-ttu-id="9ccbb-102">Esecuzione di una valutazione su richiesta utilizzando Server registrati</span><span class="sxs-lookup"><span data-stu-id="9ccbb-102">Perform an On-Demand Evaluation by Using Registered Servers</span></span>

  <span data-ttu-id="9ccbb-103">È possibile eseguire una valutazione su richiesta dei criteri per procedure consigliate in una o più istanze di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] tramite Server registrati.</span><span class="sxs-lookup"><span data-stu-id="9ccbb-103">You can perform an on-demand evaluation of best practices policies against one or more instances of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] by using Registered Servers.</span></span> <span data-ttu-id="9ccbb-104">È possibile utilizzare gruppi di server locali o un server di gestione centrale.</span><span class="sxs-lookup"><span data-stu-id="9ccbb-104">You can use either local server groups or a central management server.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9ccbb-105">È possibile eseguire una valutazione su richiesta dei criteri per procedure consigliate in membri del gruppo di server che eseguono [!INCLUDE[ssVersion2005](../includes/ssversion2005-md.md)] o una versione più recente di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9ccbb-105">You can perform an on-demand evaluation of best practices policies against server group members that are running [!INCLUDE[ssVersion2005](../includes/ssversion2005-md.md)] or a later version of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="9ccbb-106">Tuttavia, è possibile ricevere un errore di eccezione se i criteri fanno riferimento a proprietà non supportate in [!INCLUDE[ssVersion2005](../includes/ssversion2005-md.md)] o [!INCLUDE[ssVersion2000](../includes/ssversion2000-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9ccbb-106">However, you may receive an exception error if there are some properties that are referred to by a policy that are not supported in [!INCLUDE[ssVersion2005](../includes/ssversion2005-md.md)] or [!INCLUDE[ssVersion2000](../includes/ssversion2000-md.md)].</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="9ccbb-107">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="9ccbb-107">Prerequisites</span></span>  
 <span data-ttu-id="9ccbb-108">Per eseguire questa attività è necessario aver configurato una o più registrazioni di server in Server registrati.</span><span class="sxs-lookup"><span data-stu-id="9ccbb-108">To perform this task, you must have configured one or more server registrations in Registered Servers.</span></span> <span data-ttu-id="9ccbb-109">Per altre informazioni, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="9ccbb-109">For more information, see the following topics:</span></span>  
  
-   [<span data-ttu-id="9ccbb-110">Creare o modificare un gruppo di server &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="9ccbb-110">Create or Edit a Server Group &#40;SQL Server Management Studio&#41;</span></span>](../ssms/register-servers/create-or-edit-a-server-group-sql-server-management-studio.md)  
  
-   <span data-ttu-id="9ccbb-111">[Registrare un server connesso &#40;&#41;SQL Server Management Studio ](../ssms/register-servers/register-a-connected-server-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="9ccbb-111">[Register a Connected Server &#40;SQL Server Management Studio&#41;](../ssms/register-servers/register-a-connected-server-sql-server-management-studio.md).</span></span>  
  
-   [<span data-ttu-id="9ccbb-112">Creare un server di gestione centrale e un gruppo di server &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="9ccbb-112">Create a Central Management Server and Server Group &#40;SQL Server Management Studio&#41;</span></span>](../ssms/register-servers/create-a-central-management-server-and-server-group.md)  
  
### <a name="to-evaluate-best-practices-policies-against-a-server-group"></a><span data-ttu-id="9ccbb-113">Per valutare i criteri per procedure consigliate in un gruppo di server</span><span class="sxs-lookup"><span data-stu-id="9ccbb-113">To evaluate best practices policies against a server group</span></span>  
  
1.  <span data-ttu-id="9ccbb-114">In [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]scegliere **Server registrati** dal menu **Visualizza**.</span><span class="sxs-lookup"><span data-stu-id="9ccbb-114">In [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], on the **View** menu, click **Registered Servers**.</span></span>  
  
2.  <span data-ttu-id="9ccbb-115">Espandere **motore di database**, quindi espandere gruppi di **server locali**o server di **gestione centrale**, a seconda della configurazione.</span><span class="sxs-lookup"><span data-stu-id="9ccbb-115">Expand **Database Engine**, and then expand either **Local Server Groups**, or **Central Management Servers**, depending on your configuration.</span></span>  
  
3.  <span data-ttu-id="9ccbb-116">Effettuare una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9ccbb-116">Do either of the following:</span></span>  
  
    -   <span data-ttu-id="9ccbb-117">Per valutare i criteri in tutti i server gestiti dal gruppo di server locale o dal server di gestione centrale, fare clic con il pulsante destro del mouse sul nome del gruppo di server locale o sul nome del server di gestione centrale, quindi scegliere **Valuta criteri**.</span><span class="sxs-lookup"><span data-stu-id="9ccbb-117">To evaluate the policies against all servers that are managed by the local server group or the central management server, right-click the local server group name or the central management server name, and then click **Evaluate Policies**.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="9ccbb-118">Quando si valutano i criteri mediante un server di gestione centrale, tali criteri non vengono valutati nel server di gestione centrale stesso.</span><span class="sxs-lookup"><span data-stu-id="9ccbb-118">When you evaluate policies through a central management server, the policies are not evaluated against the central management server itself.</span></span>  
  
    -   <span data-ttu-id="9ccbb-119">Per valutare i criteri rispetto a un server o a un gruppo di server specifico, espandere **gruppi di server locali** o il nome del server di gestione centrale, fare clic con il pulsante destro del mouse sul server o sul gruppo di server a cui si desidera valutare i criteri, quindi scegliere **Valuta criteri**.</span><span class="sxs-lookup"><span data-stu-id="9ccbb-119">To evaluate the policies against a specific server or server group, expand **Local Server Groups** or the central management server name, right-click the server or server group that you want to evaluate policies against, and then click **Evaluate Policies**.</span></span>  
  
4.  <span data-ttu-id="9ccbb-120">Nella finestra di dialogo **Valuta criteri** , accanto alla casella **origine** , fare clic sul pulsante con i puntini di sospensione (**...**).</span><span class="sxs-lookup"><span data-stu-id="9ccbb-120">In the **Evaluate Policies** dialog box, next to the **Source** box, click the ellipsis (**...**) button.</span></span>  
  
5.  <span data-ttu-id="9ccbb-121">Nella finestra di dialogo **Seleziona origine** è possibile selezionare i **file** o il **server** come origine dei file di criteri da valutare.</span><span class="sxs-lookup"><span data-stu-id="9ccbb-121">In the **Select Source** dialog box, you can select either **Files** or **Server** as the source of the policy files to evaluate.</span></span> <span data-ttu-id="9ccbb-122">Se si fa clic su **Server**, è possibile eseguire una valutazione su richiesta dei criteri per procedure consigliate importati in precedenza nella gestione basata su criteri in un server locale o remoto.</span><span class="sxs-lookup"><span data-stu-id="9ccbb-122">If you click **Server**, you can perform an on-demand evaluation of any best practices policies that were previously imported into Policy-Based Management on a local or remote server.</span></span> <span data-ttu-id="9ccbb-123">In questa esercitazione si fa clic su **file**, quindi si selezionano i singoli file dei criteri che si desidera valutare.</span><span class="sxs-lookup"><span data-stu-id="9ccbb-123">In this tutorial, you will click **Files**, and then select the individual policy files that you want to evaluate.</span></span> <span data-ttu-id="9ccbb-124">A tale scopo, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9ccbb-124">To do this, follow these steps:</span></span>  
  
    1.  <span data-ttu-id="9ccbb-125">Fare clic su **file**.</span><span class="sxs-lookup"><span data-stu-id="9ccbb-125">Click **Files**.</span></span>  
  
    2.  <span data-ttu-id="9ccbb-126">Accanto a **file**fare clic sul pulsante con i puntini di sospensione (**...**).</span><span class="sxs-lookup"><span data-stu-id="9ccbb-126">Next to **Files**, click the ellipsis (**...**) button.</span></span>  
  
    3.  <span data-ttu-id="9ccbb-127">Selezionare uno o più file di criteri con estensione XML da valutare, quindi fare clic su **Apri**.</span><span class="sxs-lookup"><span data-stu-id="9ccbb-127">Select one or more .xml policy files to evaluate, and then click **Open**.</span></span>  
  
         <span data-ttu-id="9ccbb-128">L'elenco dei file selezionati viene visualizzato nella casella **file** .</span><span class="sxs-lookup"><span data-stu-id="9ccbb-128">The list of selected files appears in the **Files** box.</span></span>  
  
    4.  <span data-ttu-id="9ccbb-129">Nella finestra di dialogo **Seleziona origine** fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="9ccbb-129">In the **Select Source** dialog box, click **OK**.</span></span>  
  
    5.  <span data-ttu-id="9ccbb-130">Se viene visualizzata la finestra di dialogo **caricamento dei criteri** , fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="9ccbb-130">If the **Loading Policies** dialog box appears, click **Close**.</span></span>  
  
     <span data-ttu-id="9ccbb-131">I criteri selezionati vengono elencati nella pagina di **selezione dei criteri** .</span><span class="sxs-lookup"><span data-stu-id="9ccbb-131">The policies that you selected are listed on the **Policy Selection** page.</span></span> <span data-ttu-id="9ccbb-132">L'icona di avviso accanto ai criteri indica che questi contengono script.</span><span class="sxs-lookup"><span data-stu-id="9ccbb-132">Be aware that a warning icon next to a policy indicates that the policy contains scripts.</span></span>  
  
6.  <span data-ttu-id="9ccbb-133">Fare clic su **valuta** per valutare i criteri.</span><span class="sxs-lookup"><span data-stu-id="9ccbb-133">Click **Evaluate** to evaluate the policies.</span></span>  
  
7.  <span data-ttu-id="9ccbb-134">Per alcuni errori relativi ai criteri, la gestione basata su criteri consente di applicare immediatamente la conformità di criteri nella destinazione.</span><span class="sxs-lookup"><span data-stu-id="9ccbb-134">For some policy failures, Policy-Based Management enables you to immediately enforce policy compliance on the target.</span></span> <span data-ttu-id="9ccbb-135">Per questo tipo di errori verrà visualizzata una casella di controllo accanto ai criteri che presentano errori.</span><span class="sxs-lookup"><span data-stu-id="9ccbb-135">For such failures, a check box will appear next to the failed policy.</span></span> <span data-ttu-id="9ccbb-136">Se si seleziona la casella di controllo o si fa clic sulla riga con il criterio non riuscito, le caselle di controllo vengono visualizzate nel riquadro dei **Dettagli di destinazione** accanto alle istanze di destinazione che non hanno superato la valutazione.</span><span class="sxs-lookup"><span data-stu-id="9ccbb-136">If you select the check box, or click the row with the failed policy, check boxes appear in the **Target details** pane next to the target instances that failed the evaluation.</span></span> <span data-ttu-id="9ccbb-137">Se una delle caselle di controllo è selezionata, il pulsante **applica** diventa disponibile.</span><span class="sxs-lookup"><span data-stu-id="9ccbb-137">If any of the check boxes are selected, the **Apply** button becomes available.</span></span> <span data-ttu-id="9ccbb-138">Quando si fa clic su **applica**, l'impostazione non conforme verrà automaticamente aggiornata nelle istanze di destinazione selezionate.</span><span class="sxs-lookup"><span data-stu-id="9ccbb-138">When you click **Apply**, the noncompliant setting will be automatically updated on the target instances that you selected.</span></span>  
  
    > [!CAUTION]  
    >  <span data-ttu-id="9ccbb-139">Assicurarsi di aver compreso a pieno tutte le impostazioni dei criteri prima di aggiornare automaticamente un'istanza di destinazione.</span><span class="sxs-lookup"><span data-stu-id="9ccbb-139">Make sure that you fully understand the policy setting before automatically updating a target instance.</span></span> <span data-ttu-id="9ccbb-140">Dopo aver selezionato una o più caselle di controllo, è consigliabile fare clic su **script**e scegliere un percorso di output in modo che sia possibile esaminare il [!INCLUDE[tsql](../includes/tsql-md.md)] codice sottostante prima di applicare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="9ccbb-140">We recommend that after you select one or more check boxes, you click **Script**, and choose an output location so that you can review the underlying [!INCLUDE[tsql](../includes/tsql-md.md)] code before you apply the changes.</span></span>  
  
8.  <span data-ttu-id="9ccbb-141">Per visualizzare i risultati dettagliati per un criterio, fare clic sul criterio nella tabella **dei risultati** .</span><span class="sxs-lookup"><span data-stu-id="9ccbb-141">To view detailed results for a policy, click the policy in the **Results** table.</span></span> <span data-ttu-id="9ccbb-142">La tabella **Dettagli destinazione** Mostra i dettagli per ogni istanza.</span><span class="sxs-lookup"><span data-stu-id="9ccbb-142">The **Target details** table shows the details for each instance.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="9ccbb-143">Lezione successiva</span><span class="sxs-lookup"><span data-stu-id="9ccbb-143">Next Lesson</span></span>  
 [<span data-ttu-id="9ccbb-144">Lezione 2: Valutazione di criteri per procedure consigliate in base a una pianificazione</span><span class="sxs-lookup"><span data-stu-id="9ccbb-144">Lesson 2: Evaluate Best Practices Policies on a Scheduled Basis</span></span>](../../2014/tutorials/lesson-2-evaluate-best-practices-policies-on-a-scheduled-basis.md)  
  
## <a name="see-also"></a><span data-ttu-id="9ccbb-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9ccbb-145">See Also</span></span>  
 <span data-ttu-id="9ccbb-146">[Monitorare e applicare le procedure consigliate tramite la gestione basata su criteri](../relational-databases/policy-based-management/monitor-and-enforce-best-practices-by-using-policy-based-management.md) </span><span class="sxs-lookup"><span data-stu-id="9ccbb-146">[Monitor and Enforce Best Practices by Using Policy-Based Management](../relational-databases/policy-based-management/monitor-and-enforce-best-practices-by-using-policy-based-management.md) </span></span>  
 [<span data-ttu-id="9ccbb-147">Amministrare più server tramite server di gestione centrale</span><span class="sxs-lookup"><span data-stu-id="9ccbb-147">Administer Multiple Servers Using Central Management Servers</span></span>](../relational-databases/administer-multiple-servers-using-central-management-servers.md)  
  
  
