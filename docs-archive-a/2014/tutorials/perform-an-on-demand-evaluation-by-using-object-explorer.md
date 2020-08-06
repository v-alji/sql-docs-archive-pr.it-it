---
title: Eseguire una valutazione su richiesta utilizzando Esplora oggetti | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
ms.assetid: ee6d3b79-18bc-49d3-8a1d-0c0905b990f0
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: e32876978ac462af361986d84e11ef3dc0f278e2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623663"
---
# <a name="perform-an-on-demand-evaluation-by-using-object-explorer"></a><span data-ttu-id="3bb44-102">Esecuzione di una valutazione su richiesta utilizzando Esplora oggetti</span><span class="sxs-lookup"><span data-stu-id="3bb44-102">Perform an On-Demand Evaluation by Using Object Explorer</span></span>
  <span data-ttu-id="3bb44-103">In questa attività verrà utilizzato Esplora oggetti per eseguire una valutazione su richiesta di criteri per procedure consigliate per il [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)] in una singola istanza di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3bb44-103">In this task, you will use Object Explorer to perform an on-demand evaluation of best practices policies for the [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)] on a single instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3bb44-104">È inoltre possibile valutare criteri in un'istanza singola mediante Server registrati.</span><span class="sxs-lookup"><span data-stu-id="3bb44-104">You can also evaluate policies on a single instance through Registered Servers.</span></span> <span data-ttu-id="3bb44-105">Per ulteriori informazioni, vedere [eseguire una valutazione su richiesta tramite Server registrati](../../2014/tutorials/perform-an-on-demand-evaluation-by-using-registered-servers.md).</span><span class="sxs-lookup"><span data-stu-id="3bb44-105">For more information, see [Perform an On-Demand Evaluation by Using Registered Servers](../../2014/tutorials/perform-an-on-demand-evaluation-by-using-registered-servers.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="3bb44-106">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="3bb44-106">Prerequisites</span></span>  
 <span data-ttu-id="3bb44-107">Questa lezione è basata sulla versione di [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] di [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3bb44-107">This lesson is based on the version of [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] from [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3bb44-108">Per eseguire una valutazione su richiesta dei criteri per procedure consigliate per le istanze in cui è in esecuzione [!INCLUDE[ssVersion2005](../includes/ssversion2005-md.md)] , è necessario utilizzare la procedura descritta nell'argomento [eseguire una valutazione su richiesta tramite Server registrati](../../2014/tutorials/perform-an-on-demand-evaluation-by-using-registered-servers.md).</span><span class="sxs-lookup"><span data-stu-id="3bb44-108">To perform an on-demand evaluation of best practices policies against instances that are running [!INCLUDE[ssVersion2005](../includes/ssversion2005-md.md)], you must use the procedure in the topic [Perform an On-Demand Evaluation by Using Registered Servers](../../2014/tutorials/perform-an-on-demand-evaluation-by-using-registered-servers.md).</span></span>  
  
### <a name="to-perform-an-on-demand-evaluation-by-using-object-explorer"></a><span data-ttu-id="3bb44-109">Per eseguire una valutazione su richiesta utilizzando Esplora oggetti</span><span class="sxs-lookup"><span data-stu-id="3bb44-109">To perform an on-demand evaluation by using Object Explorer</span></span>  
  
1.  <span data-ttu-id="3bb44-110">Avviare [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], quindi connettersi al [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3bb44-110">Start [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], and then connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="3bb44-111">In Esplora oggetti espandere **gestione**, espandere **Gestione criteri**, fare clic con il pulsante destro del mouse su **criteri**, quindi scegliere **valuta**.</span><span class="sxs-lookup"><span data-stu-id="3bb44-111">In Object Explorer, expand **Management**, expand **Policy Management**, right-click **Policies**, and then click **Evaluate**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="3bb44-112">Per impostazione predefinita, l'istanza locale viene utilizzata come origine dei criteri.</span><span class="sxs-lookup"><span data-stu-id="3bb44-112">By default, the local instance is used as the source of the policies.</span></span> <span data-ttu-id="3bb44-113">Se in precedenza sono stati importati criteri per procedure consigliate, questi verranno elencati insieme agli altri criteri creati.</span><span class="sxs-lookup"><span data-stu-id="3bb44-113">If you have previously imported best practices policies, they will be listed, together with any other policies that you have created.</span></span> <span data-ttu-id="3bb44-114">È possibile selezionare uno dei criteri per procedure consigliate importati, quindi fare clic su **valuta**.</span><span class="sxs-lookup"><span data-stu-id="3bb44-114">You can select any of the imported best practices policies, and then click **Evaluate**.</span></span> <span data-ttu-id="3bb44-115">Se non sono stati importati criteri per procedure consigliate, continuare con questa procedura.</span><span class="sxs-lookup"><span data-stu-id="3bb44-115">If you have not imported the best practices policies, continue with this procedure.</span></span>  
  
3.  <span data-ttu-id="3bb44-116">Nella finestra di dialogo **Valuta criteri** , accanto alla casella **origine** , fare clic sul pulsante con i puntini di sospensione (**...**).</span><span class="sxs-lookup"><span data-stu-id="3bb44-116">In the **Evaluate Policies** dialog box, next to the **Source** box, click the ellipsis (**...**) button.</span></span>  
  
4.  <span data-ttu-id="3bb44-117">Nella finestra di dialogo **Seleziona origine** è possibile selezionare i **file** o il **server** come origine dei file di criteri da valutare.</span><span class="sxs-lookup"><span data-stu-id="3bb44-117">In the **Select Source** dialog box, you can select either **Files** or **Server** as the source of the policy files to evaluate.</span></span> <span data-ttu-id="3bb44-118">Se si fa clic su **Server**, è possibile eseguire una valutazione su richiesta dei criteri per procedure consigliate importati in precedenza nella gestione basata su criteri in un server locale o remoto.</span><span class="sxs-lookup"><span data-stu-id="3bb44-118">If you click **Server**, you can perform an on-demand evaluation of any best practices policies that were previously imported into Policy-Based Management on a local or remote server.</span></span> <span data-ttu-id="3bb44-119">In questa esercitazione si fa clic su **file**, quindi si selezionano i singoli file dei criteri che si desidera valutare.</span><span class="sxs-lookup"><span data-stu-id="3bb44-119">In this tutorial, you will click **Files**, and then select the individual policy files that you want to evaluate.</span></span> <span data-ttu-id="3bb44-120">A tale scopo, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3bb44-120">To do this, follow these steps:</span></span>  
  
    1.  <span data-ttu-id="3bb44-121">Fare clic su **file**.</span><span class="sxs-lookup"><span data-stu-id="3bb44-121">Click **Files**.</span></span>  
  
    2.  <span data-ttu-id="3bb44-122">Accanto a **file**fare clic sul pulsante con i puntini di sospensione (**...**).</span><span class="sxs-lookup"><span data-stu-id="3bb44-122">Next to **Files**, click the ellipsis (**...**) button.</span></span>  
  
    3.  <span data-ttu-id="3bb44-123">Nella finestra di dialogo **Seleziona criterio** individuare la cartella seguente, contenente i criteri per procedure consigliate:</span><span class="sxs-lookup"><span data-stu-id="3bb44-123">In the **Select Policy** dialog box, browse to the following folder, which contains the best practices policies:</span></span>  
  
         <span data-ttu-id="3bb44-124">**C:\Programmi (x86)\Microsoft SQL Server\110\Tools\Policies\DatabaseEngine\1033**</span><span class="sxs-lookup"><span data-stu-id="3bb44-124">**C:\Program Files (x86)\Microsoft SQL Server\110\Tools\Policies\DatabaseEngine\1033**</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="3bb44-125">Il percorso del file può variare in base alla posizione in cui sono stati installati i file di programma di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], all'esecuzione di un sistema operativo a 32 o a 64 bit e all'identificatore di lingua.</span><span class="sxs-lookup"><span data-stu-id="3bb44-125">The file path may vary, depending on where you installed the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] program files, whether you are running a 32-bit or 64-bit operating system, and the language identifier.</span></span>  
  
    4.  <span data-ttu-id="3bb44-126">Selezionare uno o più file di criteri con estensione XML da valutare, quindi fare clic su **Apri**.</span><span class="sxs-lookup"><span data-stu-id="3bb44-126">Select one or more .xml policy files to evaluate, and then click **Open**.</span></span>  
  
         <span data-ttu-id="3bb44-127">L'elenco dei file selezionati viene visualizzato nella casella **file** .</span><span class="sxs-lookup"><span data-stu-id="3bb44-127">The list of selected files appears in the **Files** box.</span></span>  
  
    5.  <span data-ttu-id="3bb44-128">Nella finestra di dialogo **Seleziona origine** fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="3bb44-128">In the **Select Source** dialog box, click **OK**.</span></span>  
  
    6.  <span data-ttu-id="3bb44-129">Se viene visualizzata la finestra di dialogo **caricamento dei criteri** , fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="3bb44-129">If the **Loading Policies** dialog box appears, click **Close**.</span></span>  
  
     <span data-ttu-id="3bb44-130">I criteri selezionati vengono elencati nella pagina di **selezione dei criteri** .</span><span class="sxs-lookup"><span data-stu-id="3bb44-130">The policies that you selected are listed on the **Policy Selection** page.</span></span> <span data-ttu-id="3bb44-131">L'icona di avviso accanto ai criteri indica che questi contengono script.</span><span class="sxs-lookup"><span data-stu-id="3bb44-131">Be aware that a warning icon next to a policy indicates that the policy contains scripts.</span></span>  
  
5.  <span data-ttu-id="3bb44-132">Fare clic su **valuta** per valutare i criteri.</span><span class="sxs-lookup"><span data-stu-id="3bb44-132">Click **Evaluate** to evaluate the policies.</span></span>  
  
     <span data-ttu-id="3bb44-133">Nella tabella dei **risultati** vengono elencati i risultati per ogni criterio.</span><span class="sxs-lookup"><span data-stu-id="3bb44-133">In the **Results** table, the results for each policy are listed.</span></span> <span data-ttu-id="3bb44-134">Un'icona "x" rossa indica che la conformità di criteri non è riuscita.</span><span class="sxs-lookup"><span data-stu-id="3bb44-134">A red "x" icon indicates that policy compliance failed.</span></span>  
  
6.  <span data-ttu-id="3bb44-135">Per alcuni errori relativi ai criteri, la gestione basata su criteri consente di applicare immediatamente la conformità di criteri nella destinazione.</span><span class="sxs-lookup"><span data-stu-id="3bb44-135">For some policy failures, Policy-Based Management enables you to immediately enforce policy compliance on the target.</span></span> <span data-ttu-id="3bb44-136">Per questo tipo di errori verrà visualizzata una casella di controllo accanto ai criteri che presentano errori.</span><span class="sxs-lookup"><span data-stu-id="3bb44-136">For such failures, a check box will appear next to the failed policy.</span></span> <span data-ttu-id="3bb44-137">Se si seleziona la casella di controllo, il pulsante **applica** diventa disponibile.</span><span class="sxs-lookup"><span data-stu-id="3bb44-137">If you select the check box, the **Apply** button becomes available.</span></span> <span data-ttu-id="3bb44-138">Quando si fa clic su **applica**, l'impostazione non conforme verrà automaticamente aggiornata nell'istanza di di destinazione.</span><span class="sxs-lookup"><span data-stu-id="3bb44-138">When you click **Apply**, the noncompliant setting will be automatically updated on the target instance.</span></span>  
  
    > [!CAUTION]  
    >  <span data-ttu-id="3bb44-139">Assicurarsi di aver compreso a pieno tutte le impostazioni dei criteri prima di aggiornare automaticamente un'istanza di destinazione.</span><span class="sxs-lookup"><span data-stu-id="3bb44-139">Make sure that you fully understand the policy setting before automatically updating a target instance.</span></span> <span data-ttu-id="3bb44-140">Dopo aver selezionato una o più caselle di controllo, è consigliabile fare clic su **script**e scegliere un percorso di output in modo che sia possibile esaminare il [!INCLUDE[tsql](../includes/tsql-md.md)] codice sottostante prima di applicare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="3bb44-140">We recommend that after you select one or more check boxes, you click **Script**, and choose an output location so that you can review the underlying [!INCLUDE[tsql](../includes/tsql-md.md)] code before you apply the changes.</span></span>  
  
7.  <span data-ttu-id="3bb44-141">Per visualizzare i risultati dettagliati per un criterio, fare clic sul criterio nella tabella **dei risultati** .</span><span class="sxs-lookup"><span data-stu-id="3bb44-141">To view detailed results for a policy, click the policy in the **Results** table.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="3bb44-142">Attività successiva della lezione</span><span class="sxs-lookup"><span data-stu-id="3bb44-142">Next Task in Lesson</span></span>  
 [<span data-ttu-id="3bb44-143">Esecuzione di una valutazione su richiesta utilizzando Server registrati</span><span class="sxs-lookup"><span data-stu-id="3bb44-143">Perform an On-Demand Evaluation by Using Registered Servers</span></span>](../../2014/tutorials/perform-an-on-demand-evaluation-by-using-registered-servers.md)  
  
  
