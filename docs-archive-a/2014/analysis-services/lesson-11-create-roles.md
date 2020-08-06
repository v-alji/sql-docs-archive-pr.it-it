---
title: 'Lezione 12: creare ruoli | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 984face4-00fc-46d3-8ae1-9755bf737bdf
author: minewiskan
ms.author: owend
ms.openlocfilehash: 962cd19726a5404de81e20a2209b25b9cc277e21
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623543"
---
# <a name="lesson-12-create-roles"></a><span data-ttu-id="ac00b-102">Lezione 12: Creazione di ruoli</span><span class="sxs-lookup"><span data-stu-id="ac00b-102">Lesson 12: Create Roles</span></span>
  <span data-ttu-id="ac00b-103">In questa lezione verranno creati ruoli.</span><span class="sxs-lookup"><span data-stu-id="ac00b-103">In this lesson, you will create roles.</span></span> <span data-ttu-id="ac00b-104">I ruoli forniscono la sicurezza per i dati e gli oggetti del database modello, limitando l'accesso unicamente agli utenti di Windows che sono membri del ruolo.</span><span class="sxs-lookup"><span data-stu-id="ac00b-104">Roles provide model database object and data security by limiting access to only those Windows users which are role members.</span></span> <span data-ttu-id="ac00b-105">Ogni ruolo è definito con una sola autorizzazione: Nessuna, Lettura, Lettura ed elaborazione, Elaborazione o Amministratore.</span><span class="sxs-lookup"><span data-stu-id="ac00b-105">Each role is defined with a single permission: None, Read, Read and Process, Process, or Administrator.</span></span> <span data-ttu-id="ac00b-106">È possibile definire i ruoli durante la creazione del modello tramite la finestra di dialogo Gestione ruoli in [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ac00b-106">Roles can be defined during model authoring by using the Role Manager dialog box in [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)].</span></span> <span data-ttu-id="ac00b-107">Dopo la distribuzione di un modello, è possibile gestire i ruoli tramite [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ac00b-107">After a model has been deployed, you can manage roles by using [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="ac00b-108">Per altre informazioni, vedere [Ruoli &#40;SSAS tabulare&#41;](tabular-models/roles-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="ac00b-108">To learn more, see [Roles &#40;SSAS Tabular&#41;](tabular-models/roles-ssas-tabular.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ac00b-109">La creazione di ruoli non è necessaria per completare questa esercitazione.</span><span class="sxs-lookup"><span data-stu-id="ac00b-109">Creating roles is not necessary to complete this tutorial.</span></span> <span data-ttu-id="ac00b-110">Per impostazione predefinita, l'account con cui si esegue l'accesso avrà i privilegi di Amministratore per il modello.</span><span class="sxs-lookup"><span data-stu-id="ac00b-110">By default, the account you are currently logged in with will have Administrator privileges on the model.</span></span> <span data-ttu-id="ac00b-111">Per consentire ad altri utenti nell'organizzazione di esplorare il modello utilizzando un'applicazione client di creazione di report, è tuttavia necessario creare almeno un ruolo che disponga di autorizzazioni di lettura e aggiungere tali utenti come membri.</span><span class="sxs-lookup"><span data-stu-id="ac00b-111">However, to allow other users in your organization to browse the model by using a reporting client application, you must create at least one role with Read permissions and add those users as members.</span></span>  
  
 <span data-ttu-id="ac00b-112">Verranno creati tre ruoli:</span><span class="sxs-lookup"><span data-stu-id="ac00b-112">You will create three roles:</span></span>  
  
-   <span data-ttu-id="ac00b-113">Responsabile vendite-questo ruolo può includere gli utenti dell'organizzazione per i quali si desidera disporre dell'autorizzazione di lettura per tutti gli oggetti e i dati del modello.</span><span class="sxs-lookup"><span data-stu-id="ac00b-113">Sales Manager - This role can include users in your organization for which you want to have Read permission to all model objects and data.</span></span>  
  
-   <span data-ttu-id="ac00b-114">Sales Analyst US: questo ruolo può includere gli utenti dell'organizzazione per i quali si desidera solo essere in grado di esplorare i dati relativi alle vendite negli Stati Uniti (Stati Uniti).</span><span class="sxs-lookup"><span data-stu-id="ac00b-114">Sales Analyst US - This role can include users in your organization for which you want only to be able to browse data related to sales in the US (United States).</span></span> <span data-ttu-id="ac00b-115">Per questo ruolo, si utilizzerà una formula DAX per definire un *Filtro di riga*che consente ai membri di esplorare solo i dati per gli Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="ac00b-115">For this role, you will use a DAX formula to define a *Row Filter*, which restricts members to browse data only for the United States.</span></span>  
  
-   <span data-ttu-id="ac00b-116">Amministratore: questo ruolo può includere gli utenti per i quali si desidera disporre dell'autorizzazione di amministratore, che consente l'accesso illimitato e autorizzazioni per l'esecuzione di attività amministrative sul database modello.</span><span class="sxs-lookup"><span data-stu-id="ac00b-116">Administrator - This role can include users for which you want to have Administrator permission, which allows unlimited access and permissions to perform administrative tasks on the model database.</span></span>  
  
 <span data-ttu-id="ac00b-117">Poiché gli account di gruppo e utente di Windows nell'organizzazione sono univoci, è possibile aggiungere account dell'organizzazione specifica ai membri.</span><span class="sxs-lookup"><span data-stu-id="ac00b-117">Because Windows user and group accounts in your organization are unique, you can add accounts from your particular organization to members.</span></span> <span data-ttu-id="ac00b-118">Tuttavia, per questa esercitazione, è anche possibile lasciare i membri vuoti.</span><span class="sxs-lookup"><span data-stu-id="ac00b-118">However, for this tutorial, you can also leave the members blank.</span></span> <span data-ttu-id="ac00b-119">Sarà ancora possibile verificare gli effetti di ciascun ruolo più avanti nella Lezione 12: Analizzare in Excel.</span><span class="sxs-lookup"><span data-stu-id="ac00b-119">You will still be able to test the effect of each role later in Lesson 12: Analyze in Excel.</span></span>  
  
 <span data-ttu-id="ac00b-120">Tempo previsto per il completamento della lezione: **15 minuti**</span><span class="sxs-lookup"><span data-stu-id="ac00b-120">Estimated time to complete this lesson: **15 minutes**</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="ac00b-121">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="ac00b-121">Prerequisites</span></span>  
 <span data-ttu-id="ac00b-122">Questo argomento fa parte di un'esercitazione sulla creazione di modelli tabulari, con lezioni che è consigliabile completare nell'ordine indicato.</span><span class="sxs-lookup"><span data-stu-id="ac00b-122">This topic is part of a tabular modeling tutorial, which should be completed in order.</span></span> <span data-ttu-id="ac00b-123">Prima di eseguire le attività in questa lezione è necessario aver completato la lezione precedente: [Lezione 11: Creare partizioni](lesson-10-create-partitions.md).</span><span class="sxs-lookup"><span data-stu-id="ac00b-123">Before performing the tasks in this lesson, you should have completed the previous lesson: [Lesson 11: Create Partitions](lesson-10-create-partitions.md).</span></span>  
  
## <a name="create-roles"></a><span data-ttu-id="ac00b-124">Creazione di ruoli</span><span class="sxs-lookup"><span data-stu-id="ac00b-124">Create Roles</span></span>  
  
#### <a name="to-create-a-sales-manager-user-role"></a><span data-ttu-id="ac00b-125">Per creare un ruolo utente Sales Manager</span><span class="sxs-lookup"><span data-stu-id="ac00b-125">To create a Sales Manager user role</span></span>  
  
1.  <span data-ttu-id="ac00b-126">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]scegliere **Ruoli** dal menu **Modello**.</span><span class="sxs-lookup"><span data-stu-id="ac00b-126">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], click on the **Model** menu, and then click **Roles**.</span></span>  
  
2.  <span data-ttu-id="ac00b-127">Nella finestra di dialogo **Gestione ruoli** fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="ac00b-127">In the **Role Manager** dialog box, click **New**.</span></span>  
  
     <span data-ttu-id="ac00b-128">Un nuovo ruolo con l'autorizzazione Nessuna verrà aggiunto all'elenco.</span><span class="sxs-lookup"><span data-stu-id="ac00b-128">A new role with the None permission is added to the list.</span></span>  
  
3.  <span data-ttu-id="ac00b-129">Fare clic sul nuovo ruolo e quindi nella colonna **nome** rinominare il ruolo in `Internet Sales Manager` .</span><span class="sxs-lookup"><span data-stu-id="ac00b-129">Click on the new role, and then in the **Name** column, rename the role to `Internet Sales Manager`.</span></span>  
  
4.  <span data-ttu-id="ac00b-130">Nella colonna **Autorizzazioni** fare clic nell'elenco a discesa e quindi selezionare l'autorizzazione **Lettura**.</span><span class="sxs-lookup"><span data-stu-id="ac00b-130">In the **Permissions** column, click the dropdown list, and then select the **Read** permission.</span></span>  
  
5.  <span data-ttu-id="ac00b-131">Facoltativo: fare clic sulla scheda **Membri** e quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="ac00b-131">Optional: Click on the **Members** tab, and then click **Add**.</span></span>  
  
6.  <span data-ttu-id="ac00b-132">Nella finestra di dialogo **Seleziona utenti o gruppi** immettere gli utenti o i gruppi di Windows dell'organizzazione che si vuole includere nel ruolo.</span><span class="sxs-lookup"><span data-stu-id="ac00b-132">In the **Select Users or Groups** dialog box, enter the Windows users or groups from your organization you want to include in the role.</span></span>  
  
7.  <span data-ttu-id="ac00b-133">Verificare le selezioni e quindi fare clic su **OK** .</span><span class="sxs-lookup"><span data-stu-id="ac00b-133">Verify your selections, and then click **OK**</span></span>  
  
#### <a name="to-create-a-sales-analyst-us-user-role"></a><span data-ttu-id="ac00b-134">Per creare un ruolo utente Sales Analyst US</span><span class="sxs-lookup"><span data-stu-id="ac00b-134">To create a Sales Analyst US user role</span></span>  
  
1.  <span data-ttu-id="ac00b-135">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]scegliere **Ruoli** dal menu **Modello**.</span><span class="sxs-lookup"><span data-stu-id="ac00b-135">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], click on the **Model** menu, and then click **Roles**.</span></span>  
  
2.  <span data-ttu-id="ac00b-136">Nella finestra di dialogo **Gestione ruoli** fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="ac00b-136">In the **Role Manager** dialog box, click **New**.</span></span>  
  
     <span data-ttu-id="ac00b-137">Un nuovo ruolo con l'autorizzazione Nessuna verrà aggiunto all'elenco.</span><span class="sxs-lookup"><span data-stu-id="ac00b-137">A new role with the None permission is added to the list.</span></span>  
  
3.  <span data-ttu-id="ac00b-138">Fare clic sul nuovo ruolo e quindi nella colonna **nome** rinominare il ruolo in `Internet Sales US` .</span><span class="sxs-lookup"><span data-stu-id="ac00b-138">Click on the new role, and then in the **Name** column, rename the role to `Internet Sales US`.</span></span>  
  
4.  <span data-ttu-id="ac00b-139">Nella colonna **Autorizzazioni** fare clic nell'elenco a discesa e quindi selezionare l'autorizzazione **Lettura**.</span><span class="sxs-lookup"><span data-stu-id="ac00b-139">In the **Permissions** column, click the dropdown list, and then select the **Read** permission.</span></span>  
  
5.  <span data-ttu-id="ac00b-140">Fare clic sulla scheda Filtri di riga, quindi, solo per la tabella **Geography** , digitare la formula seguente nella colonna Filtro DAX:</span><span class="sxs-lookup"><span data-stu-id="ac00b-140">Click on the Row Filters tab, and then for the **Geography** table only, in the DAX Filter column, type the following formula:</span></span>  
  
     `=Geography[Country Region Code] = "US"`  
  
     <span data-ttu-id="ac00b-141">Una formula per il filtro di riga deve restituire un valore booleano (TRUE/FALSE).</span><span class="sxs-lookup"><span data-stu-id="ac00b-141">A Row Filter formula must resolve to a Boolean (TRUE/FALSE) value.</span></span> <span data-ttu-id="ac00b-142">Con questa formula, si specifica che solo le righe con il valore "US" del codice dell'area paese saranno visibili all'utente.</span><span class="sxs-lookup"><span data-stu-id="ac00b-142">With this formula, you are specifying that only rows with the Country Region Code value of "US" be visible to the user.</span></span>  
  
     <span data-ttu-id="ac00b-143">Dopo avere completato la compilazione della formula, premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="ac00b-143">When you have finished building the formula, press ENTER.</span></span>  
  
6.  <span data-ttu-id="ac00b-144">Facoltativo: fare clic sulla scheda **Membri** e quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="ac00b-144">Optional: Click on the **Members** tab, and then click **Add**.</span></span>  
  
7.  <span data-ttu-id="ac00b-145">Nella finestra di dialogo **Seleziona utenti o gruppi** immettere gli utenti o i gruppi di Windows dell'organizzazione che si vuole includere nel ruolo.</span><span class="sxs-lookup"><span data-stu-id="ac00b-145">In the **Select Users or Groups** dialog box, enter the Windows users or groups from your organization you want to include in the role.</span></span>  
  
8.  <span data-ttu-id="ac00b-146">Verificare le selezioni e quindi fare clic su **OK** .</span><span class="sxs-lookup"><span data-stu-id="ac00b-146">Verify your selections, and then click **OK**</span></span>  
  
#### <a name="to-create-an-administrator-role"></a><span data-ttu-id="ac00b-147">Per creare un ruolo di amministratore</span><span class="sxs-lookup"><span data-stu-id="ac00b-147">To create an Administrator role</span></span>  
  
1.  <span data-ttu-id="ac00b-148">Nella finestra di dialogo **Gestione ruoli** fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="ac00b-148">In the **Role Manager** dialog box, click **New**.</span></span>  
  
2.  <span data-ttu-id="ac00b-149">Fare clic sul nuovo ruolo e quindi nella colonna **nome** rinominare il ruolo in `Internet Sales Administrator` .</span><span class="sxs-lookup"><span data-stu-id="ac00b-149">Click on the new role, and then in the **Name** column, rename the role to `Internet Sales Administrator`.</span></span>  
  
3.  <span data-ttu-id="ac00b-150">Nella colonna **Autorizzazioni** fare clic nell'elenco a discesa, quindi selezionare l'autorizzazione **Amministratore** .</span><span class="sxs-lookup"><span data-stu-id="ac00b-150">In the **Permissions** column, click the dropdown list, and then select the **Administrator** permission.</span></span>  
  
4.  <span data-ttu-id="ac00b-151">Fare clic sulla scheda **Membri** , quindi su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="ac00b-151">Click on the **Members** tab, and then click **Add**.</span></span>  
  
5.  <span data-ttu-id="ac00b-152">Facoltativo: nella finestra di dialogo **Seleziona utenti o gruppi** immettere i gruppi o gli utenti di Windows dell'organizzazione da includere nel ruolo.</span><span class="sxs-lookup"><span data-stu-id="ac00b-152">Optional: In the **Select Users or Groups** dialog box, enter the Windows users or groups from your organization you want to include in the role.</span></span>  
  
6.  <span data-ttu-id="ac00b-153">Verificare le selezioni e quindi fare clic su **OK** .</span><span class="sxs-lookup"><span data-stu-id="ac00b-153">Verify your selections, and then click **OK**</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="ac00b-154">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="ac00b-154">Next Steps</span></span>  
 <span data-ttu-id="ac00b-155">Per continuare questa esercitazione, passare alla lezione successiva: [Lezione 13: Analizza in Excel](lesson-12-analyze-in-excel.md).</span><span class="sxs-lookup"><span data-stu-id="ac00b-155">To continue this tutorial, go to the next lesson: Lesson: [Lesson 13: Analyze in Excel](lesson-12-analyze-in-excel.md).</span></span>  
  
  
