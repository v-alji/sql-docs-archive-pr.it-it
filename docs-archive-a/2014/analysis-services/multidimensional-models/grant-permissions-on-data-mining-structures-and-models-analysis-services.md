---
title: Concedere le autorizzazioni per le strutture e i modelli di data mining (Analysis Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.roledesignerdialog.miningmodels.f1
helpviewer_keywords:
- data mining [Analysis Services], security
- permissions [Analysis Services], mining models
- mining models [Analysis Services], security
- mining structures [Analysis Services], security
- permissions [Analysis Services], mining structures
- user access rights [Analysis Services], mining structures
- user access rights [Analysis Services], mining models
ms.assetid: a0008004-e2b7-47db-acad-5fe7e12b130f
author: minewiskan
ms.author: owend
ms.openlocfilehash: d0db849551bdb38615f280b123c98f0e9d3053d6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718798"
---
# <a name="grant-permissions-on-data-mining-structures-and-models-analysis-services"></a><span data-ttu-id="6564c-102">Concedere le autorizzazioni per le strutture e i modelli di data mining (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="6564c-102">Grant permissions on data mining structures and models (Analysis Services)</span></span>
  <span data-ttu-id="6564c-103">Per impostazione predefinita, solo un amministratore del server di Analysis Services dispone delle autorizzazioni per visualizzare strutture di data mining o modelli di data mining nel database.</span><span class="sxs-lookup"><span data-stu-id="6564c-103">By default, only an Analysis Services server administrator has permissions to view data mining structures or mining models in the database.</span></span> <span data-ttu-id="6564c-104">Seguire le istruzioni riportate di seguito per concedere le autorizzazioni agli utenti non amministratori.</span><span class="sxs-lookup"><span data-stu-id="6564c-104">Follow the instructions below to grant permissions to non-administrator users.</span></span>  
  
## <a name="set-permissions-to-access-a-mining-structure"></a><span data-ttu-id="6564c-105">Impostare le autorizzazioni per accedere a una struttura di data mining</span><span class="sxs-lookup"><span data-stu-id="6564c-105">Set permissions to access a mining structure</span></span>  
  
1.  <span data-ttu-id="6564c-106">In SSMS connettersi ad Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="6564c-106">In SSMS, connect to Analysis Services.</span></span> <span data-ttu-id="6564c-107">Se è necessaria assistenza per la procedura, vedere [Connettersi dalle applicazioni client &#40;Analysis Services&#41;](../instances/connect-from-client-applications-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="6564c-107">See [Connect from client applications &#40;Analysis Services&#41;](../instances/connect-from-client-applications-analysis-services.md) if you need help with the steps.</span></span>  
  
2.  <span data-ttu-id="6564c-108">Aprire la cartella **Database** e selezionare un database in Esplora oggetti.</span><span class="sxs-lookup"><span data-stu-id="6564c-108">Open the **Databases** folder, and select a database in Object Explorer.</span></span>  
  
3.  <span data-ttu-id="6564c-109">Fare clic con il pulsante destro del mouse su **Ruoli** e scegliere **Nuovo ruolo**.</span><span class="sxs-lookup"><span data-stu-id="6564c-109">Right-click **Roles** and choose **New Role**.</span></span>  
  
4.  <span data-ttu-id="6564c-110">Nella pagina Generale immettere un nome e, se si vuole, una descrizione.</span><span class="sxs-lookup"><span data-stu-id="6564c-110">In the General page, enter a name, and optionally, a description.</span></span> <span data-ttu-id="6564c-111">Questa pagina contiene anche diverse autorizzazioni per il database quali Controllo completo, Elaborazione database e Lettura definizione.</span><span class="sxs-lookup"><span data-stu-id="6564c-111">The page also contains several database permissions, such as Full Control, Process Database, and Read Definition.</span></span> <span data-ttu-id="6564c-112">Nessuna di tali autorizzazioni è necessaria per l'accesso al data mining.</span><span class="sxs-lookup"><span data-stu-id="6564c-112">None of these permissions are needed for data mining access.</span></span> <span data-ttu-id="6564c-113">Per altre informazioni sulle autorizzazioni per il database, vedere [Concedere autorizzazioni per il database &#40;Analysis Services&#41;](grant-database-permissions-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="6564c-113">See [Grant database permissions &#40;Analysis Services&#41;](grant-database-permissions-analysis-services.md) for more information about database permissions.</span></span>  
  
5.  <span data-ttu-id="6564c-114">Nel riquadro **Struttura di data mining** selezionare **Lettura** o **Lettura/Scrittura**  per ogni struttura di data mining.</span><span class="sxs-lookup"><span data-stu-id="6564c-114">In the **Mining Structure** pane, select **Read** or **Read/Write**  for each data mining structure.</span></span>  
  
6.  <span data-ttu-id="6564c-115">Nel riquadro **Appartenenza** immettere gli account utente e di gruppo di Windows che si connettono ad Analysis Services con questo ruolo.</span><span class="sxs-lookup"><span data-stu-id="6564c-115">In the **Membership** pane, enter the Windows user and group accounts that connect to Analysis Services using this role.</span></span>  
  
7.  <span data-ttu-id="6564c-116">Fare clic su **OK** per completare la creazione del ruolo.</span><span class="sxs-lookup"><span data-stu-id="6564c-116">Click **OK** to finish creating the role.</span></span>  
  
## <a name="set-permissions-to-access-a-mining-model"></a><span data-ttu-id="6564c-117">Impostare le autorizzazione per accedere a un modello di data mining</span><span class="sxs-lookup"><span data-stu-id="6564c-117">Set permissions to access a mining model</span></span>  
 <span data-ttu-id="6564c-118">Un ruolo per un modello di data mining può disporre di autorizzazioni di **Lettura** o **Lettura/Scrittura** , nonché di autorizzazioni di **Drill-through** e **Lettura definizione** che consentono di visualizzare ed esplorare i dati sottostanti.</span><span class="sxs-lookup"><span data-stu-id="6564c-118">For a data mining model, a role can have either **Read** or **Read/Write** permissions, as well as **Drillthrough** and **Read Definition** permissions that allow viewing and browsing the underlying data.</span></span>  
  
 <span data-ttu-id="6564c-119">**Nota** Se si abilita il drill-through nella struttura di data mining e nel modello di data mining, qualsiasi utente membro di un ruolo con autorizzazioni drill-through per il modello di data mining e per la struttura di data mining può anche visualizzare le colonne nella struttura di data mining, anche se tali colonne non sono incluse nel modello di data mining.</span><span class="sxs-lookup"><span data-stu-id="6564c-119">**Note** If you enable drillthrough on both the mining structure and the mining model, any user who is a member of a role that has drillthrough permissions on the mining model and the mining structure can also view columns in the mining structure, even if those columns are not included in the mining model.</span></span> <span data-ttu-id="6564c-120">Pertanto, per proteggere le informazioni riservate, è necessario configurare la vista origine dati per mascherare le informazioni personali e consentire l'accesso drill-through alla struttura di data mining solo quando necessario.</span><span class="sxs-lookup"><span data-stu-id="6564c-120">Therefore, to protect sensitive information, you should set up the data source view to mask personal information, and allow drillthrough access on the mining structure only when necessary.</span></span>  
  
 <span data-ttu-id="6564c-121">Per concedere autorizzazioni di lettura o lettura/scrittura a un ruolo del database, un utente deve essere membro del ruolo del server di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] oppure di un ruolo del database di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] che disponga di autorizzazioni Controllo completo (amministratore).</span><span class="sxs-lookup"><span data-stu-id="6564c-121">To grant read or read/write permissions to a database role, a user must be a member of the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] server role or a member of an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database role that has Full Control (Administrator) permissions.</span></span>  
  
1.  <span data-ttu-id="6564c-122">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] connettersi all'istanza di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , espandere **ruoli** per il database appropriato in Esplora oggetti, quindi fare clic su un ruolo del database o creare un nuovo ruolo del database.</span><span class="sxs-lookup"><span data-stu-id="6564c-122">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to the instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], expand **Roles** for the appropriate database in Object Explorer, and then click a database role (or create a new database role).</span></span>  
  
2.  <span data-ttu-id="6564c-123">Nel riquadro **Struttura di data mining** individuare il modello di data mining nell'elenco **Modelli di data mining** e quindi selezionare **Lettura**, **Lettura/Scrittura**, **Drill-through**o **Esplorazione** per il modello di data mining.</span><span class="sxs-lookup"><span data-stu-id="6564c-123">In the **Mining Structure** pane, locate the mining model in the **Mining Models** list, and then select **Read**, **Read/Write**, **Drill Through**, or **Browse** for that mining model.</span></span>  
  
3.  <span data-ttu-id="6564c-124">Nel riquadro **Appartenenza** immettere gli account utente e di gruppo di Windows che si connettono ad Analysis Services con questo ruolo.</span><span class="sxs-lookup"><span data-stu-id="6564c-124">In the **Membership** pane, enter the Windows user and group accounts that connect to Analysis Services using this role.</span></span>  
  
4.  <span data-ttu-id="6564c-125">Fare clic su **OK** per completare la creazione del ruolo.</span><span class="sxs-lookup"><span data-stu-id="6564c-125">Click **OK** to finish creating the role.</span></span>  
  
 <span data-ttu-id="6564c-126">Per usare un'origine dei dati in una query drill-through che usa la clausola OPENQUERY DMX (Data Mining Extensions), è necessario che il ruolo del database abbia anche l'autorizzazione di lettura/scrittura per l'oggetto origine dati appropriato.</span><span class="sxs-lookup"><span data-stu-id="6564c-126">To use a data source in a drillthrough query that uses the Data Mining Extensions (DMX) OPENQUERY clause, the database role also needs read/write permission on the appropriate data source object.</span></span> <span data-ttu-id="6564c-127">Per altre informazioni, vedere [Concedere le autorizzazioni per un oggetto origine dati &#40;Analysis Services&#41;](grant-permissions-on-a-data-source-object-analysis-services.md) e [OPENQUERY &#40;DMX&#41;](/sql/dmx/source-data-query-openquery).</span><span class="sxs-lookup"><span data-stu-id="6564c-127">For more information, see [Grant permissions on a data source object &#40;Analysis Services&#41;](grant-permissions-on-a-data-source-object-analysis-services.md) and [OPENQUERY &#40;DMX&#41;](/sql/dmx/source-data-query-openquery).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6564c-128">Per impostazione predefinita, l'invio delle query DMX tramite OPENROWSET è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="6564c-128">By default, the submission of DMX queries by using OPENROWSET is disabled.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6564c-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6564c-129">See Also</span></span>  
 <span data-ttu-id="6564c-130">[Concedere le autorizzazioni di amministratore del server &#40;Analysis Services&#41;](../instances/grant-server-admin-rights-to-an-analysis-services-instance.md) </span><span class="sxs-lookup"><span data-stu-id="6564c-130">[Grant Server Administrator Permissions &#40;Analysis Services&#41;](../instances/grant-server-admin-rights-to-an-analysis-services-instance.md) </span></span>  
 <span data-ttu-id="6564c-131">[Concedere le autorizzazioni per il cubo o il modello &#40;Analysis Services&#41;](grant-cube-or-model-permissions-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="6564c-131">[Grant cube or model permissions &#40;Analysis Services&#41;](grant-cube-or-model-permissions-analysis-services.md) </span></span>  
 <span data-ttu-id="6564c-132">[Concessione dell'accesso personalizzato ai dati della dimensione &#40;Analysis Services&#41;](grant-custom-access-to-dimension-data-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="6564c-132">[Grant custom access to dimension data &#40;Analysis Services&#41;](grant-custom-access-to-dimension-data-analysis-services.md) </span></span>  
 [<span data-ttu-id="6564c-133">Concedere l'accesso personalizzato ai dati delle celle &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="6564c-133">Grant custom access to cell data &#40;Analysis Services&#41;</span></span>](grant-custom-access-to-cell-data-analysis-services.md)  
  
  
