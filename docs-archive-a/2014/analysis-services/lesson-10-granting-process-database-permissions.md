---
title: Concessione delle autorizzazioni per il database di elaborazione | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 69ba952e-09ae-49a9-9297-00e32e8e89a8
author: minewiskan
ms.author: owend
ms.openlocfilehash: 6ada30e3fb509bd1ffd210485ce0e34b7bf86fb7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623548"
---
# <a name="granting-process-database-permissions"></a><span data-ttu-id="9ceba-102">Concessione di autorizzazioni per l'elaborazione di database</span><span class="sxs-lookup"><span data-stu-id="9ceba-102">Granting Process Database Permissions</span></span>
  <span data-ttu-id="9ceba-103">Dopo l'installazione di un'istanza di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], tutti i membri del ruolo di amministratore del server [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] nell'istanza dispongono di autorizzazioni valide per l'intero server per eseguire qualsiasi attività all'interno dell'istanza di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9ceba-103">After you install an instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], all members of the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] server administrator role in that instance have server-wide permissions to perform any task within the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="9ceba-104">Per impostazione predefinita, nessun altro utente dispone dell'autorizzazione per amministrare o visualizzare gli oggetti nell'istanza di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9ceba-104">By default, no other users have any permission to administer or view any objects in the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span>

 <span data-ttu-id="9ceba-105">Un membro del ruolo di amministratore del server può consentire agli utenti l'accesso amministrativo a livello del server rendendoli membri del ruolo.</span><span class="sxs-lookup"><span data-stu-id="9ceba-105">A member of the server administrator role can grant users administrative access on a server-wide basis by making them members of the role.</span></span> <span data-ttu-id="9ceba-106">Un membro del ruolo di amministratore del server può inoltre concedere agli utenti un accesso più limitato concedendo autorizzazioni amministrative o di accesso limitate o complete a livello di database.</span><span class="sxs-lookup"><span data-stu-id="9ceba-106">A member of the server administrator role can also grant users access on a more limited basis by granting them limited or complete administrative or access permissions at the database level.</span></span> <span data-ttu-id="9ceba-107">Le autorizzazioni amministrative limitate includono autorizzazioni per l'elaborazione o la visualizzazione delle definizioni degli oggetti a livello di database, cubo o dimensione.</span><span class="sxs-lookup"><span data-stu-id="9ceba-107">Limited administrative permissions include process or read definition permissions at the database, cube, or dimension level.</span></span>

 <span data-ttu-id="9ceba-108">Nelle procedure descritte in questo argomento viene definito un ruolo di sicurezza Process Database Objects che concede ai membri del ruolo l'autorizzazione per elaborare tutti gli oggetti di database, ma non concede alcuna autorizzazione per visualizzare i dati nel database.</span><span class="sxs-lookup"><span data-stu-id="9ceba-108">In the tasks in this topic, you will define a Process Database Objects security role that grants members of the role permission to process all database objects, but no permission to view data within the database.</span></span>

## <a name="defining-a-process-database-objects-security-role"></a><span data-ttu-id="9ceba-109">Definizione di un ruolo di sicurezza Process Database Objects</span><span class="sxs-lookup"><span data-stu-id="9ceba-109">Defining a Process Database Objects Security Role</span></span>

1.  <span data-ttu-id="9ceba-110">Fare clic con il pulsante destro del mouse su **Ruoli** in Esplora soluzioni, quindi scegliere **Nuovo ruolo** per aprire Progettazione ruoli.</span><span class="sxs-lookup"><span data-stu-id="9ceba-110">In Solution Explorer, right-click **Roles** and then click **New Role** to open the Role Designer.</span></span>

2.  <span data-ttu-id="9ceba-111">Selezionare la casella di controllo **Elaborazione database** .</span><span class="sxs-lookup"><span data-stu-id="9ceba-111">Click the **Process database** check box.</span></span>

3.  <span data-ttu-id="9ceba-112">Nella Finestra Proprietà modificare la proprietà **Name** del nuovo ruolo in `Process Database Objects Role` .</span><span class="sxs-lookup"><span data-stu-id="9ceba-112">In the Properties window, change the **Name** property for this new role to `Process Database Objects Role`.</span></span>

     <span data-ttu-id="9ceba-113">![Progettazione ruoli](../../2014/tutorials/media/l10-security-1.png "Progettazione ruoli")</span><span class="sxs-lookup"><span data-stu-id="9ceba-113">![Role Designer](../../2014/tutorials/media/l10-security-1.png "Role Designer")</span></span>

4.  <span data-ttu-id="9ceba-114">Passare alla scheda **Appartenenze** di Progettazione ruoli e fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="9ceba-114">Switch to the **Membership** tab of Role Designer and click **Add**.</span></span>

5.  <span data-ttu-id="9ceba-115">Immettere gli account di utenti o gruppi di dominio Windows che saranno membri di questo ruolo.</span><span class="sxs-lookup"><span data-stu-id="9ceba-115">Enter the accounts of the Windows domain users or groups who will be members of this role.</span></span> <span data-ttu-id="9ceba-116">Fare clic su **Verifica nomi** per verificare le informazioni sull'account, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="9ceba-116">Click **Check Names** to verify the account information, and then click **OK**.</span></span>

6.  <span data-ttu-id="9ceba-117">Passare alla scheda **Cubi** di Progettazione ruoli.</span><span class="sxs-lookup"><span data-stu-id="9ceba-117">Switch to the **Cubes** tab of Role Designer.</span></span>

     <span data-ttu-id="9ceba-118">Si noti che i membri di questo ruolo dispongono delle autorizzazioni per elaborare questo database, ma non per accedere ai dati nel cubo [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial né dispongono dell'accesso locale al cubo/drill-through, come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="9ceba-118">Notice that members of this role have permissions to process this database, but have no permission to access the data in the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube and have no local cube/drillthrough access, as shown in the following image.</span></span>

     <span data-ttu-id="9ceba-119">![Scheda Cubi di Progettazione ruoli](../../2014/tutorials/media/l10-security-2.png "Scheda Cubi di Progettazione ruoli")</span><span class="sxs-lookup"><span data-stu-id="9ceba-119">![Cubes tab of Role Designer](../../2014/tutorials/media/l10-security-2.png "Cubes tab of Role Designer")</span></span>

7.  <span data-ttu-id="9ceba-120">Passare alla scheda **Dimensioni** di Progettazione ruoli.</span><span class="sxs-lookup"><span data-stu-id="9ceba-120">Switch to the **Dimensions** tab of Role Designer.</span></span>

     <span data-ttu-id="9ceba-121">Si noti che i membri di questo ruolo dispongono delle autorizzazioni per elaborare tutti gli oggetti dimensione in questo database e, per impostazione predefinita, delle autorizzazioni di lettura per accedere a ogni oggetto dimensione nel database di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial.</span><span class="sxs-lookup"><span data-stu-id="9ceba-121">Notice that members of this role have permissions to process all dimension objects in this database, and, by default, have read permissions to access each dimension object in the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial database.</span></span>

8.  <span data-ttu-id="9ceba-122">Scegliere **Distribuisci Analysis Services Tutorial** dal menu **Compila**.</span><span class="sxs-lookup"><span data-stu-id="9ceba-122">On the **Build** menu, click **Deploy Analysis Services Tutorial**.</span></span>

     <span data-ttu-id="9ceba-123">La definizione e la distribuzione del ruolo di sicurezza Process Database Objects sono state portate a termine con successo.</span><span class="sxs-lookup"><span data-stu-id="9ceba-123">You have now successfully defined and deployed the Process Database Objects security role.</span></span> <span data-ttu-id="9ceba-124">Quando un cubo viene distribuito nell'ambiente di produzione gli amministratori del cubo distribuito possono aggiungere utenti al ruolo, allo scopo di delegare le responsabilità di elaborazione a utenti specifici.</span><span class="sxs-lookup"><span data-stu-id="9ceba-124">After a cube is deployed to the production environment, the administrators of the deployed cube can add users to this role as required to delegate processing responsibilities to specific users.</span></span>

> [!NOTE]
>  <span data-ttu-id="9ceba-125">È possibile ottenere un progetto completo per la lezione 10 scaricando e installando gli esempi aggiornati.</span><span class="sxs-lookup"><span data-stu-id="9ceba-125">A completed project for Lesson 10 is available by downloading and installing the samples.</span></span> <span data-ttu-id="9ceba-126">Per altre informazioni, vedere [Installare dati di esempio e progetti per l'esercitazione di modellazione multidimensionale di Analysis Services](install-sample-data-and-projects.md).</span><span class="sxs-lookup"><span data-stu-id="9ceba-126">For more information, see [Install Sample Data and Projects for the Analysis Services Multidimensional Modeling Tutorial](install-sample-data-and-projects.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="9ceba-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9ceba-127">See Also</span></span>
 [<span data-ttu-id="9ceba-128">Ruoli e autorizzazioni &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="9ceba-128">Roles and Permissions &#40;Analysis Services&#41;</span></span>](multidimensional-models/roles-and-permissions-analysis-services.md)


