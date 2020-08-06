---
title: Gestire i ruoli tramite SSMS (SSAS tabulare) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 652faac0-1cfc-438b-8119-2f4b090a2381
author: minewiskan
ms.author: owend
ms.openlocfilehash: 4ee34d5e75d5d4ce3679d46d29af3215852d2bbe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712484"
---
# <a name="manage-roles-by-using-ssms-ssas-tabular"></a><span data-ttu-id="9a38c-102">Gestire ruoli tramite (SSAS tabulare)</span><span class="sxs-lookup"><span data-stu-id="9a38c-102">Manage Roles by using SSMS (SSAS Tabular)</span></span>
  <span data-ttu-id="9a38c-103">È possibile creare, modificare e gestire ruoli per un modello tabulare distribuito tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9a38c-103">You can create, edit, and manage roles for a deployed tabular model by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="9a38c-104">Attività dell'argomento:</span><span class="sxs-lookup"><span data-stu-id="9a38c-104">Tasks in this topic:</span></span>  
  
-   [<span data-ttu-id="9a38c-105">Per creare un nuovo ruolo</span><span class="sxs-lookup"><span data-stu-id="9a38c-105">To create a new role</span></span>](#bkmk_new_role)  
  
-   [<span data-ttu-id="9a38c-106">Per copiare un ruolo</span><span class="sxs-lookup"><span data-stu-id="9a38c-106">To copy a role</span></span>](#bkmk_copy_role)  
  
-   [<span data-ttu-id="9a38c-107">Per modificare un ruolo</span><span class="sxs-lookup"><span data-stu-id="9a38c-107">To edit a role</span></span>](#bkmk_edit_role)  
  
-   [<span data-ttu-id="9a38c-108">Per eliminare un ruolo</span><span class="sxs-lookup"><span data-stu-id="9a38c-108">To delete a role</span></span>](#bkmk_deletet_role)  
  
> [!CAUTION]  
>  <span data-ttu-id="9a38c-109">La ridistribuzione di un progetto di modello tabulare con i ruoli definiti tramite Gestione ruoli in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)] sovrascriverà i ruoli definiti in un modello tabulare distribuito.</span><span class="sxs-lookup"><span data-stu-id="9a38c-109">Re-deploying a tabular model project with roles defined by using Role Manager in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)] will overwrite roles defined in a deployed tabular model.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="9a38c-110">L'utilizzo di [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] per gestire un database dell'area di lavoro del modello tabulare mentre il progetto di modello è aperto in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] può causare il danneggiamento del file Model.bim.</span><span class="sxs-lookup"><span data-stu-id="9a38c-110">Using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to manage a tabular model workspace database while the model project is open in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] may cause the Model.bim file to become corrupted.</span></span> <span data-ttu-id="9a38c-111">Quando si creano e gestiscono ruoli per un database dell'area di lavoro del modello tabulare, utilizzare Gestione ruoli di [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9a38c-111">When creating and managing roles for a tabular model workspace database, use Role Manager in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)].</span></span>  
  
###  <a name="to-create-a-new-role"></a><a name="bkmk_new_role"></a><span data-ttu-id="9a38c-112">Per creare un nuovo ruolo</span><span class="sxs-lookup"><span data-stu-id="9a38c-112">To create a new role</span></span>  
  
1.  <span data-ttu-id="9a38c-113">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]espandere il database del modello tabulare per cui si vuole creare un nuovo ruolo, fare clic con il pulsante destro del mouse su **Ruoli**e quindi fare clic su **Nuovo ruolo**.</span><span class="sxs-lookup"><span data-stu-id="9a38c-113">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expand the tabular model database for which you want to create a new role, then right click on **Roles**, and then click **New Role**.</span></span>  
  
2.  <span data-ttu-id="9a38c-114">Nella finestra Selezione pagina della finestra di dialogo **Crea ruolo** fare clic su **Generale**.</span><span class="sxs-lookup"><span data-stu-id="9a38c-114">In the **Create Role** dialog box, in the Select a page window, click **General**.</span></span>  
  
3.  <span data-ttu-id="9a38c-115">Nel campo **Nome** della finestra delle impostazioni generali digitare un nome per il ruolo.</span><span class="sxs-lookup"><span data-stu-id="9a38c-115">In the general settings window, in the **Name** field, type a name for the role.</span></span>  
  
     <span data-ttu-id="9a38c-116">Per impostazione predefinita, il nome del ruolo predefinito sarà numerato in modo incrementale per ogni nuovo ruolo.</span><span class="sxs-lookup"><span data-stu-id="9a38c-116">By default, the name of the default role will be incrementally numbered for each new role.</span></span> <span data-ttu-id="9a38c-117">È consigliabile digitare un nome che consente di identificare chiaramente il tipo di membro, ad esempio Responsabili finanze o Esperti di risorse umane.</span><span class="sxs-lookup"><span data-stu-id="9a38c-117">It is recommended you type a name that clearly identifies the member type, for example, Finance Managers or Human Resources Specialists.</span></span>  
  
4.  <span data-ttu-id="9a38c-118">In **Impostare le autorizzazioni del ruolo per il database**selezionare una delle opzioni delle autorizzazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9a38c-118">In **Set the database permissions for this role**, select one of the following permissions options:</span></span>  
  
    |<span data-ttu-id="9a38c-119">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="9a38c-119">Permission</span></span>|<span data-ttu-id="9a38c-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9a38c-120">Description</span></span>|  
    |----------------|-----------------|  
    |<span data-ttu-id="9a38c-121">**Controllo completo (amministratore)**</span><span class="sxs-lookup"><span data-stu-id="9a38c-121">**Full control (Administrator)**</span></span>|<span data-ttu-id="9a38c-122">I membri possono apportare modifiche allo schema del modello e visualizzare tutti i dati.</span><span class="sxs-lookup"><span data-stu-id="9a38c-122">Members can make modifications to the model schema and can view all data.</span></span>|  
    |<span data-ttu-id="9a38c-123">**Elaborazione database**</span><span class="sxs-lookup"><span data-stu-id="9a38c-123">**Process database**</span></span>|<span data-ttu-id="9a38c-124">I membri possono effettuare le operazioni relative alle opzioni Elabora ed Elabora tutto,</span><span class="sxs-lookup"><span data-stu-id="9a38c-124">Members can run Process and Process All operations.</span></span> <span data-ttu-id="9a38c-125">ma non possono modificare lo schema del modello, né visualizzare dati.</span><span class="sxs-lookup"><span data-stu-id="9a38c-125">Cannot modify the model schema and cannot view data.</span></span>|  
    |<span data-ttu-id="9a38c-126">**Lettura**</span><span class="sxs-lookup"><span data-stu-id="9a38c-126">**Read**</span></span>|<span data-ttu-id="9a38c-127">I membri possono visualizzare i dati in base ai filtri di riga, ma non possono apportare alcuna modifica allo schema del modello.</span><span class="sxs-lookup"><span data-stu-id="9a38c-127">Members are allowed to view data (based on row filters) but cannot make any changes to the model schema.</span></span>|  
  
5.  <span data-ttu-id="9a38c-128">Nella finestra Selezione pagina della finestra di dialogo **Crea ruolo** fare clic su **Appartenenze**.</span><span class="sxs-lookup"><span data-stu-id="9a38c-128">In the **Create Role** dialog box, in the Select a page window, click **Membership**.</span></span>  
  
6.  <span data-ttu-id="9a38c-129">Nella finestra delle impostazioni di appartenenza fare clic su **Aggiungi**e quindi, nella finestra di dialogo **Seleziona utenti o gruppi** , aggiungere gli utenti o i gruppi di Windows che si vuole aggiungere come membri.</span><span class="sxs-lookup"><span data-stu-id="9a38c-129">In the membership settings window, click **Add**, and then in the **Select Users or Groups** dialog box, add the Windows users or groups you want to add as members.</span></span>  
  
7.  <span data-ttu-id="9a38c-130">Se il ruolo in fase di creazione dispone dell'autorizzazione Lettura, è possibile aggiungere filtri di riga per qualsiasi tabella utilizzando una formula DAX.</span><span class="sxs-lookup"><span data-stu-id="9a38c-130">If the role you are creating has Read permissions, you can add row filters for any table using a DAX formula.</span></span> <span data-ttu-id="9a38c-131">Per aggiungere filtri di riga, nella finestra di dialogo \*\*Proprietà ruolo- \<rolename> \*\* in **Selezione pagina**fare clic su **filtri di riga**.</span><span class="sxs-lookup"><span data-stu-id="9a38c-131">To add row filters, in the **Role Properties - \<rolename>** dialog box, in **Select a page**, click on **Row Filters**.</span></span>  
  
8.  <span data-ttu-id="9a38c-132">Nella finestra filtri di riga selezionare una tabella, fare clic sul campo **Filtro DAX** e quindi digitare una formula DAX nel campo \*\* \<tablename> Filtro DAX\*\* .</span><span class="sxs-lookup"><span data-stu-id="9a38c-132">In the row filters window, select a table, then click on the **DAX Filter** field, and then in the **DAX Filter - \<tablename>** field, type a DAX formula.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9a38c-133">Il campo Filtro DAX \<tablename> non contiene un editor di query di completamento automatico o una funzione Inserisci funzione.</span><span class="sxs-lookup"><span data-stu-id="9a38c-133">The DAX Filter - \<tablename> field does not contain an AutoComplete query editor or insert function feature.</span></span> <span data-ttu-id="9a38c-134">Per usare il completamento automatico quando si scrive una formula DAX, è necessario usare un editor di formule DAX in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9a38c-134">To use AutoComplete when writing a DAX formula, you must use a DAX formula editor in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)].</span></span>  
  
9. <span data-ttu-id="9a38c-135">Fare clic su **OK** per salvare il ruolo.</span><span class="sxs-lookup"><span data-stu-id="9a38c-135">Click **Ok** to save the role.</span></span>  
  
###  <a name="to-copy-a-role"></a><a name="bkmk_copy_role"></a> <span data-ttu-id="9a38c-136">Per copiare un ruolo</span><span class="sxs-lookup"><span data-stu-id="9a38c-136">To copy a role</span></span>  
  
1.  <span data-ttu-id="9a38c-137">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]espandere il database del modello tabulare che contiene il ruolo da copiare, espandere **Ruoli**, quindi fare clic con il pulsante destro del mouse sul ruolo e fare clic su **Duplica**.</span><span class="sxs-lookup"><span data-stu-id="9a38c-137">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expand the tabular model database that contains the role you want to copy, then expand **Roles**, then right click on the role, and then click **Duplicate**.</span></span>  
  
###  <a name="to-edit-a-role"></a><a name="bkmk_edit_role"></a><span data-ttu-id="9a38c-138">Per modificare un ruolo</span><span class="sxs-lookup"><span data-stu-id="9a38c-138">To edit a role</span></span>  
  
-   <span data-ttu-id="9a38c-139">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]espandere il database del modello tabulare che contiene il ruolo da modificare, espandere **Ruoli**, quindi fare clic con il pulsante destro del mouse sul ruolo e fare clic su **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="9a38c-139">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expand the tabular model database that contains the role you want to edit, then expand **Roles**, then right click on the role, and then click **Properties**.</span></span>  
  
     <span data-ttu-id="9a38c-140">Nella finestra di dialogo **Proprietà ruolo** \<rolename> è possibile modificare le autorizzazioni, aggiungere o rimuovere membri e aggiungere o modificare i filtri di riga.</span><span class="sxs-lookup"><span data-stu-id="9a38c-140">In the **Role Properties** \<rolename> dialog box, you can change permissions, add or remove members, and add/edit row filters.</span></span>  
  
###  <a name="to-delete-a-role"></a><a name="bkmk_deletet_role"></a><span data-ttu-id="9a38c-141">Per eliminare un ruolo</span><span class="sxs-lookup"><span data-stu-id="9a38c-141">To delete a role</span></span>  
  
-   <span data-ttu-id="9a38c-142">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]espandere il database del modello tabulare che contiene il ruolo da eliminare, espandere **Ruoli**, quindi fare clic con il pulsante destro del mouse sul ruolo e fare clic su **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="9a38c-142">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expand the tabular model database that contains the role you want to delete, then expand **Roles**, then right click on the role, and then click **Delete**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a38c-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9a38c-143">See Also</span></span>  
 [<span data-ttu-id="9a38c-144">Ruoli &#40;SSAS tabulare&#41;</span><span class="sxs-lookup"><span data-stu-id="9a38c-144">Roles &#40;SSAS Tabular&#41;</span></span>](roles-ssas-tabular.md)  
  
  
