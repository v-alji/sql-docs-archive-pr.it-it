---
title: Creare un modello utilizzando Gestione report | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- report models [Reporting Services], creating
- Report Manager [Reporting Services], model creation
ms.assetid: 8e5d2bd3-48ec-45f3-afee-6d86797c8f28
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 59ce278a22ec9797b001ca37a0bde576483cf5d6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719692"
---
# <a name="create-a-model-using-report-manager"></a><span data-ttu-id="ec079-102">Creare un modello tramite Gestione report</span><span class="sxs-lookup"><span data-stu-id="ec079-102">Create a Model Using Report Manager</span></span>
  <span data-ttu-id="ec079-103">È possibile generare modelli da un cubo di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , da un database di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] o da un database Oracle utilizzando Gestione report.</span><span class="sxs-lookup"><span data-stu-id="ec079-103">You can generate models from an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] cube, a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] database, or an Oracle database using Report Manager.</span></span> <span data-ttu-id="ec079-104">I modelli di report vengono generati da origini dei dati condivise che vengono pubblicate nel server di report.</span><span class="sxs-lookup"><span data-stu-id="ec079-104">Report models are generated from shared data sources that are published on the report server.</span></span> <span data-ttu-id="ec079-105">Se non esiste un'origine dei dati condivisa, è necessario crearla.</span><span class="sxs-lookup"><span data-stu-id="ec079-105">If you do not already have a shared data source, you must create one.</span></span>  
  
 <span data-ttu-id="ec079-106">Il modello di report che viene generato si basa interamente sullo schema dell'origine dei dati condivisa.</span><span class="sxs-lookup"><span data-stu-id="ec079-106">The report model that you generate is based entirely on the schema of the shared data source.</span></span> <span data-ttu-id="ec079-107">Non è possibile scegliere quali parti dell'origine dei dati includere nel modello, né modificare le regole o i metadati del modello generato.</span><span class="sxs-lookup"><span data-stu-id="ec079-107">You cannot choose which parts of the data source are included in the model, nor can you edit the rules or metadata of a generated model.</span></span> <span data-ttu-id="ec079-108">È tuttavia possibile impostare le proprietà del modello dopo che quest'ultimo è stato generato e definire le assegnazioni di ruolo che limitano l'accesso all'intero modello o a parte di esso.</span><span class="sxs-lookup"><span data-stu-id="ec079-108">However, you can set properties on the model after it is generated and define role assignments that restrict access to all or part of the model.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ec079-109">Un modello basato su Oracle generato utilizzando Gestione report o [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[offSPServ](../includes/offspserv-md.md)] 2007 [!INCLUDE[SPS2010](../includes/sps2010-md.md)] includerà oggetti di database che fanno parte dello schema per l'account utente utilizzato per la connessione all'origine dati Oracle.</span><span class="sxs-lookup"><span data-stu-id="ec079-109">An Oracle-based model generated using Report Manager or [!INCLUDE[msCoName](../includes/msconame-md.md)][!INCLUDE[offSPServ](../includes/offspserv-md.md)] 2007 [!INCLUDE[SPS2010](../includes/sps2010-md.md)] will include database objects that are a part of the schema for the user account used to connect to the Oracle data source.</span></span> <span data-ttu-id="ec079-110">Il nome dell'account utente viene specificato nelle credenziali delle proprietà per l'origine dei dati.</span><span class="sxs-lookup"><span data-stu-id="ec079-110">The user account name is specified in the data source properties credentials.</span></span>  
  
### <a name="to-create-a-new-data-source-for-a-report-model-using-report-manager"></a><span data-ttu-id="ec079-111">Per creare una nuova origine dei dati per un modello di report tramite Gestione report</span><span class="sxs-lookup"><span data-stu-id="ec079-111">To create a new data source for a report model using Report Manager</span></span>  
  
1.  <span data-ttu-id="ec079-112">Digitare l'URL per il server di report nella barra degli indirizzi del browser.</span><span class="sxs-lookup"><span data-stu-id="ec079-112">In your Web browser, type the URL for your report server in the address bar.</span></span>  
  
2.  <span data-ttu-id="ec079-113">Fare clic su **Nuova origine dati**.</span><span class="sxs-lookup"><span data-stu-id="ec079-113">Click **New Data Source**.</span></span>  
  
3.  <span data-ttu-id="ec079-114">Nella casella di testo **Nome** immettere un nome per l'origine dei dati.</span><span class="sxs-lookup"><span data-stu-id="ec079-114">In the **Name** box, enter a name for the data source.</span></span>  
  
4.  <span data-ttu-id="ec079-115">Nella casella di testo **Descrizione** immettere una breve descrizione facoltativa del modello.</span><span class="sxs-lookup"><span data-stu-id="ec079-115">Optionally, enter a brief description of the mode in the **Description** text box.</span></span>  
  
5.  <span data-ttu-id="ec079-116">Verificare che la casella di controllo **Attiva questa origine dei dati** sia selezionata.</span><span class="sxs-lookup"><span data-stu-id="ec079-116">Verify that the **Enable this data source** check box is selected.</span></span>  
  
6.  <span data-ttu-id="ec079-117">Dalla lista **Tipo di connessione** selezionare il tipo di origine dei dati a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="ec079-117">In the **Connection type** list, select the data source type to which you want to connect.</span></span> <span data-ttu-id="ec079-118">Il tipo di connessione deve essere uno dei seguenti: **Oracle**, **Microsoft SQL Server** o **Microsoft SQL Server Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="ec079-118">The connection type must be one of the following: **Oracle**, **Microsoft SQL Server** or **Microsoft SQL Server Analysis Services**.</span></span>  
  
7.  <span data-ttu-id="ec079-119">Nella casella **Stringa di connessione** specificare la stringa di connessione che punta al database.</span><span class="sxs-lookup"><span data-stu-id="ec079-119">In the **Connection string** box, enter the connection string that points to the database.</span></span>  
  
8.  <span data-ttu-id="ec079-120">Selezionare il metodo di connessione che gli utenti di Generatore report dovranno utilizzare per connettersi al database.</span><span class="sxs-lookup"><span data-stu-id="ec079-120">Select the connection method that Report Builder users will need to use to connect to the database.</span></span>  
  
    -   <span data-ttu-id="ec079-121">Autenticazione di Windows: selezionare questa opzione affinché gli utenti di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] vengano autenticati dal sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="ec079-121">Windows Authentication: Select this option when you want the operating system to authenticate [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] users.</span></span> <span data-ttu-id="ec079-122">Questa opzione consente l'utilizzo in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] delle caratteristiche di sicurezza di Windows, ad esempio la crittografia della password, per l'autenticazione degli utenti.</span><span class="sxs-lookup"><span data-stu-id="ec079-122">This option allows [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] to use Windows security features, such as password encryption, to authenticate users.</span></span> <span data-ttu-id="ec079-123">Si consiglia di selezionare questa opzione.</span><span class="sxs-lookup"><span data-stu-id="ec079-123">It is strongly recommended that you select this option.</span></span>  
  
    -   [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]<span data-ttu-id="ec079-124">Autenticazione: selezionare questa opzione se si desidera che gli utenti usino un [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] account di accesso creato.</span><span class="sxs-lookup"><span data-stu-id="ec079-124">Authentication: Select this option when you want users to use a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] login account that you created.</span></span> <span data-ttu-id="ec079-125">Gli utenti dovranno fornire un nome e una password di accesso validi per [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ec079-125">Users must supply a valid [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] login name and password.</span></span>  
  
        > [!CAUTION]  
        >  <span data-ttu-id="ec079-126">Se possibile, è consigliabile utilizzare l'autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="ec079-126">Whenever possible, use Windows Authentication.</span></span>  
  
9. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
### <a name="to-create-a-report-model-using-report-manager"></a><span data-ttu-id="ec079-127">Per creare un modello di report tramite Gestione report</span><span class="sxs-lookup"><span data-stu-id="ec079-127">To create a report model using Report Manager</span></span>  
  
1.  <span data-ttu-id="ec079-128">In Gestione report selezionare l'origine dei dati che si desidera utilizzare per il modello.</span><span class="sxs-lookup"><span data-stu-id="ec079-128">In Report Manager, select the data source that you want to use for your model.</span></span>  
  
     <span data-ttu-id="ec079-129">Verrà visualizzata la pagina Proprietà.</span><span class="sxs-lookup"><span data-stu-id="ec079-129">The Properties page is displayed.</span></span>  
  
2.  <span data-ttu-id="ec079-130">Verificare quali opzioni si intende utilizzare per l'origine dei dati.</span><span class="sxs-lookup"><span data-stu-id="ec079-130">Verify that you want to use the options specified for the data source.</span></span>  
  
3.  <span data-ttu-id="ec079-131">Fare clic su **Genera modello**.</span><span class="sxs-lookup"><span data-stu-id="ec079-131">Click **Generate Model**.</span></span>  
  
     <span data-ttu-id="ec079-132">Verrà visualizzata la pagina Generale per l'origine dei dati.</span><span class="sxs-lookup"><span data-stu-id="ec079-132">The General page is displayed for the data source.</span></span>  
  
4.  <span data-ttu-id="ec079-133">Nella casella di testo **Nome** immettere un nome per il modello di report.</span><span class="sxs-lookup"><span data-stu-id="ec079-133">In the **Name** box, enter a name for the report model.</span></span>  
  
5.  <span data-ttu-id="ec079-134">Nella casella **Descrizione** immettere una breve descrizione del modello.</span><span class="sxs-lookup"><span data-stu-id="ec079-134">In the **Description** box, enter a brief description of the model.</span></span>  
  
6.  <span data-ttu-id="ec079-135">Per specificare un nuovo percorso in cui salvare il modello di report fare clic su **Cambia percorso**.</span><span class="sxs-lookup"><span data-stu-id="ec079-135">To specify a new location to save the report model to, click **Change Location**.</span></span>  
  
     <span data-ttu-id="ec079-136">Per impostazione predefinita, il modello di report viene salvato nella cartella Home di Gestione report.</span><span class="sxs-lookup"><span data-stu-id="ec079-136">By default, the report model is saved to Report Manager Home.</span></span>  
  
7.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
     <span data-ttu-id="ec079-137">Il modello di report verrà creato e salvato nel percorso specificato.</span><span class="sxs-lookup"><span data-stu-id="ec079-137">The report model is created and saved to the location that you specified.</span></span> <span data-ttu-id="ec079-138">È possibile assegnare autorizzazioni a questo modello utilizzando Gestione report.</span><span class="sxs-lookup"><span data-stu-id="ec079-138">You can assign permissions to this model by using Report Manager.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec079-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ec079-139">See Also</span></span>  
 <span data-ttu-id="ec079-140">[Concessione di autorizzazioni in un server di report in modalità nativa](security/granting-permissions-on-a-native-mode-report-server.md) </span><span class="sxs-lookup"><span data-stu-id="ec079-140">[Granting Permissions on a Native Mode Report Server](security/granting-permissions-on-a-native-mode-report-server.md) </span></span>  
 <span data-ttu-id="ec079-141">[Connessioni dati, origini dati e stringhe di connessione in Reporting Services](../../2014/reporting-services/data-connections-data-sources-and-connection-strings-in-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="ec079-141">[Data Connections, Data Sources, and Connection Strings in Reporting Services](../../2014/reporting-services/data-connections-data-sources-and-connection-strings-in-reporting-services.md) </span></span>  
 [<span data-ttu-id="ec079-142">Pagina Nuova origine dati &#40;Gestione report&#41;</span><span class="sxs-lookup"><span data-stu-id="ec079-142">New Data Source Page &#40;Report Manager&#41;</span></span>](../../2014/reporting-services/new-data-source-page-report-manager.md)  
  
  
