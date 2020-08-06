---
title: Creare e gestire ruoli (SSAS tabulare) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.rolemanager.f1
- sql12.asvs.bidtoolset.roledb.f1
ms.assetid: e23d27a8-e968-4082-9dbe-963fc724b5d9
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 335e0e311d97ea452449cd0c5d6550f6dbcca4f4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625001"
---
# <a name="create-and-manage-roles-ssas-tabular"></a><span data-ttu-id="5a22b-102">Creare e gestire ruoli (SSAS tabulare)</span><span class="sxs-lookup"><span data-stu-id="5a22b-102">Create and Manage Roles (SSAS Tabular)</span></span>
  <span data-ttu-id="5a22b-103">I ruoli, nei modelli tabulari, consentono di definire le autorizzazioni dei membri per un modello.</span><span class="sxs-lookup"><span data-stu-id="5a22b-103">Roles, in tabular models, define member permissions for a model.</span></span> <span data-ttu-id="5a22b-104">I ruoli vengono definiti per un progetto di modello tramite la finestra di dialogo Gestione ruoli di [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5a22b-104">Roles are defined for a model project by using the Role Manager dialog box in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="5a22b-105">Quando viene distribuito un modello, gli amministratori del database possono gestire i ruoli tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5a22b-105">When a model is deployed, database administrators can manage roles by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="5a22b-106">Le attività di questo argomento descrivono come creare e gestire i ruoli durante la creazione di modelli tramite la finestra di dialogo Gestione ruoli in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5a22b-106">The tasks in this topic describe how to create and manage roles during model authoring by using the Role Manager dialog box in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="5a22b-107">Per altre informazioni sulla gestione dei ruoli in un database modello distribuito, vedere [Ruoli nei modelli tabulari &#40;SSAS Tabulare&#41;](roles-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="5a22b-107">For information about managing roles in a deployed model database, see [Tabular Model Roles &#40;SSAS Tabular&#41;](roles-ssas-tabular.md).</span></span>  
  
## <a name="tasks"></a><span data-ttu-id="5a22b-108">Attività</span><span class="sxs-lookup"><span data-stu-id="5a22b-108">Tasks</span></span>  
 <span data-ttu-id="5a22b-109">Per creare, modificare, copiare ed eliminare ruoli, usare la finestra di dialogo **Gestione ruoli** .</span><span class="sxs-lookup"><span data-stu-id="5a22b-109">To create, edit, copy, and delete roles, you will use the **Role Manager** dialog box.</span></span> <span data-ttu-id="5a22b-110">Per visualizzare la finestra di dialogo **Gestione ruoli** di [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], fare clic sul menu **Modello** e quindi su **Gestione ruoli**.</span><span class="sxs-lookup"><span data-stu-id="5a22b-110">To view the **Role Manager** dialog box, in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], click the **Model** menu, and then click **Role Manager**.</span></span>  
  
###  <a name="to-create-a-new-role"></a><a name="bkmk_new_role"></a><span data-ttu-id="5a22b-111">Per creare un nuovo ruolo</span><span class="sxs-lookup"><span data-stu-id="5a22b-111">To create a new role</span></span>  
  
1.  <span data-ttu-id="5a22b-112">In [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)]fare clic sul menu **Modello** e quindi su **Gestione ruoli**.</span><span class="sxs-lookup"><span data-stu-id="5a22b-112">In [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], click the **Model** menu, and then click **Role Manager**.</span></span>  
  
2.  <span data-ttu-id="5a22b-113">Nella finestra di dialogo **Gestione ruoli** fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="5a22b-113">In the **Role Manager** dialog box, click **New**.</span></span>  
  
     <span data-ttu-id="5a22b-114">All'elenco Ruoli verrà aggiunto un nuovo ruolo evidenziato.</span><span class="sxs-lookup"><span data-stu-id="5a22b-114">A new highlighted role is added to the Roles list.</span></span>  
  
3.  <span data-ttu-id="5a22b-115">Nel campo **Nome** dell'elenco **Ruoli** digitare un nome per il ruolo.</span><span class="sxs-lookup"><span data-stu-id="5a22b-115">In the **Roles** list, in the **Name** field, type a name for the role.</span></span>  
  
     <span data-ttu-id="5a22b-116">Per impostazione predefinita, il nome del ruolo predefinito sarà numerato in modo incrementale per ogni nuovo ruolo.</span><span class="sxs-lookup"><span data-stu-id="5a22b-116">By default, the name of the default role will be incrementally numbered for each new role.</span></span> <span data-ttu-id="5a22b-117">È consigliabile digitare un nome che consente di identificare chiaramente il tipo di membro, ad esempio Responsabili finanze o Esperti di risorse umane.</span><span class="sxs-lookup"><span data-stu-id="5a22b-117">It is recommended you type a name that clearly identifies the member type, for example, Finance Managers or Human Resources Specialists.</span></span>  
  
4.  <span data-ttu-id="5a22b-118">Nel campo **Autorizzazioni** fare clic sulla freccia GIÙ e quindi selezionare uno dei tipi di autorizzazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5a22b-118">In the **Permissions** field, click the down arrow and then select one of the following permission types:</span></span>  
  
    |<span data-ttu-id="5a22b-119">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="5a22b-119">Permission</span></span>|<span data-ttu-id="5a22b-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5a22b-120">Description</span></span>|  
    |----------------|-----------------|  
    |<span data-ttu-id="5a22b-121">**Nessuno**</span><span class="sxs-lookup"><span data-stu-id="5a22b-121">**None**</span></span>|<span data-ttu-id="5a22b-122">I membri non possono apportare alcuna modifica allo schema del modello, né eseguire query sui dati.</span><span class="sxs-lookup"><span data-stu-id="5a22b-122">Members cannot make any modifications to the model schema and cannot query data.</span></span>|  
    |<span data-ttu-id="5a22b-123">**Lettura**</span><span class="sxs-lookup"><span data-stu-id="5a22b-123">**Read**</span></span>|<span data-ttu-id="5a22b-124">I membri possono eseguire query sui dati in base ai filtri di riga, ma non possono apportare alcuna modifica allo schema del modello.</span><span class="sxs-lookup"><span data-stu-id="5a22b-124">Members are allowed to query data (based on row filters) but cannot make any changes to the model schema.</span></span>|  
    |<span data-ttu-id="5a22b-125">**Lettura ed elaborazione**</span><span class="sxs-lookup"><span data-stu-id="5a22b-125">**Read and Process**</span></span>|<span data-ttu-id="5a22b-126">I membri possono eseguire query sui dati in base ai filtri a livello di riga ed effettuare le operazioni relative alle opzioni Elabora ed Elabora tutto, ma non possono apportare alcuna modifica allo schema del modello.</span><span class="sxs-lookup"><span data-stu-id="5a22b-126">Members are allowed to query data (based on row-level filters) and run Process and Process All operations, but cannot make any changes to the model schema.</span></span>|  
    |<span data-ttu-id="5a22b-127">**Processo**</span><span class="sxs-lookup"><span data-stu-id="5a22b-127">**Process**</span></span>|<span data-ttu-id="5a22b-128">I membri possono effettuare le operazioni relative alle opzioni Elabora ed Elabora tutto,</span><span class="sxs-lookup"><span data-stu-id="5a22b-128">Members can run Process and Process All operations.</span></span> <span data-ttu-id="5a22b-129">ma non possono modificare lo schema del modello, né eseguire query sui dati.</span><span class="sxs-lookup"><span data-stu-id="5a22b-129">Cannot modify the model schema and cannot query data.</span></span>|  
    |<span data-ttu-id="5a22b-130">**Amministratore**</span><span class="sxs-lookup"><span data-stu-id="5a22b-130">**Administrator**</span></span>|<span data-ttu-id="5a22b-131">I membri possono apportare modifiche allo schema del modello ed eseguire query su tutti i dati.</span><span class="sxs-lookup"><span data-stu-id="5a22b-131">Members can make modifications to the model schema and can query all data.</span></span>|  
  
5.  <span data-ttu-id="5a22b-132">Per immettere una descrizione per il ruolo, fare clic sul campo **Descrizione** e quindi digitare una descrizione.</span><span class="sxs-lookup"><span data-stu-id="5a22b-132">To enter a description for the role, click the **Description** field, and then type a description.</span></span>  
  
6.  <span data-ttu-id="5a22b-133">Se il ruolo in fase di creazione dispone dell'autorizzazione Lettura o di lettura ed elaborazione, è possibile aggiungere filtri di riga utilizzando una formula DAX.</span><span class="sxs-lookup"><span data-stu-id="5a22b-133">If the role you are creating has Read or Read and Process permission, you can add row filters using a DAX formula.</span></span> <span data-ttu-id="5a22b-134">Per aggiungere filtri di riga, fare clic sulla scheda **Filtri di riga** , selezionare una tabella, fare clic sul campo **Filtro DAX** e quindi digitare una formula DAX.</span><span class="sxs-lookup"><span data-stu-id="5a22b-134">To add row filters, click the **Row Filters** tab, then select a table, then click the **DAX Filter** field, and then type a DAX formula.</span></span>  
  
7.  <span data-ttu-id="5a22b-135">Per aggiungere membri al ruolo, fare clic sulla scheda **Membri** e quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="5a22b-135">To add members to the role, click the **Members** tab, and then click **Add**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5a22b-136">I membri dei ruoli possono anche essere aggiunti a un modello distribuito tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5a22b-136">Role members can also be added to a deployed model by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="5a22b-137">Per altre informazioni, vedere [Gestire ruoli tramite SSMS &#40;SSAS tabulare&#41;](manage-roles-by-using-ssms-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="5a22b-137">For more information, see [Manage Roles by using SSMS &#40;SSAS Tabular&#41;](manage-roles-by-using-ssms-ssas-tabular.md).</span></span>  
  
8.  <span data-ttu-id="5a22b-138">Nella finestra di dialogo **Selezione utenti o gruppi** immettere oggetti utente o gruppo di Windows come membri.</span><span class="sxs-lookup"><span data-stu-id="5a22b-138">In the **Select Users or Groups** dialog box, enter Windows user or Windows group objects as members.</span></span>  
  
9. <span data-ttu-id="5a22b-139">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="5a22b-139">Click **Ok**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a22b-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5a22b-140">See Also</span></span>  
 <span data-ttu-id="5a22b-141">[Ruoli &#40;SSAS tabulare&#41;](roles-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="5a22b-141">[Roles &#40;SSAS Tabular&#41;](roles-ssas-tabular.md) </span></span>  
 <span data-ttu-id="5a22b-142">[Prospettive &#40;SSAS tabulare&#41;](perspectives-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="5a22b-142">[Perspectives &#40;SSAS Tabular&#41;](perspectives-ssas-tabular.md) </span></span>  
 <span data-ttu-id="5a22b-143">[Analizza in Excel &#40;SSAS tabulare&#41;](analyze-in-excel-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="5a22b-143">[Analyze in Excel &#40;SSAS Tabular&#41;](analyze-in-excel-ssas-tabular.md) </span></span>  
 <span data-ttu-id="5a22b-144">[Funzione USERNAME &#40;&#41;DAX](/dax/username-function-dax) </span><span class="sxs-lookup"><span data-stu-id="5a22b-144">[USERNAME Function &#40;DAX&#41;](/dax/username-function-dax) </span></span>  
 [<span data-ttu-id="5a22b-145">Funzione CUSTOMDATA &#40;&#41;DAX</span><span class="sxs-lookup"><span data-stu-id="5a22b-145">CUSTOMDATA Function &#40;DAX&#41;</span></span>](/dax/customdata-function-dax)  
  
  
