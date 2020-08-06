---
title: Utilità di configurazione server (componenti aggiuntivi Data mining per Excel) | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 28435f86-5cec-4a1e-9b7d-b2069c1ddddb
author: minewiskan
ms.author: owend
ms.openlocfilehash: f985338e44bf0f4b591fcb70a4e093901626149f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727191"
---
# <a name="server-configuration-utility-data-mining-add-ins-for-excel"></a><span data-ttu-id="970e1-102">Utilità di configurazione del server (componenti aggiuntivi data mining per Excel)</span><span class="sxs-lookup"><span data-stu-id="970e1-102">Server Configuration Utility (Data Mining Add-ins for Excel)</span></span>
  <span data-ttu-id="970e1-103">Quando si installano i componenti aggiuntivi Data mining per Excel, viene installata anche un'utilità di configurazione del server, che verrà eseguita la prima volta che si aprono i componenti aggiuntivi. In questo argomento viene descritto come utilizzare l'utilità per connettersi a un'istanza di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] e impostare un database per l'utilizzo di modelli di data mining.</span><span class="sxs-lookup"><span data-stu-id="970e1-103">When you install the Data Mining Add-ins for Excel, a Server Configuration Utility is also installed, and will run the first time you open the add-ins. This topic describes how to use the utility to connect to an instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] and set up a database for working with data mining models.</span></span>  
  

  
##  <a name="step-1-connect-to-analysis-services"></a><a name="bkmk_step1"></a><span data-ttu-id="970e1-104">Passaggio 1: connettersi a Analysis Services</span><span class="sxs-lookup"><span data-stu-id="970e1-104">Step 1: Connect to Analysis Services</span></span>  
 <span data-ttu-id="970e1-105">Scegliere il server [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] che fornisce gli algoritmi di data mining e archivia i modelli di data mining.</span><span class="sxs-lookup"><span data-stu-id="970e1-105">Choose the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] server that provides the data mining algorithms and stores your data mining models.</span></span>  
  
 <span data-ttu-id="970e1-106">Quando si crea una connessione per abilitare il data mining, è necessario scegliere un server in cui è possibile provare a utilizzare i modelli di data mining.</span><span class="sxs-lookup"><span data-stu-id="970e1-106">When you create a connection to enable data mining, you should choose a server where you can experiment with data mining models.</span></span> <span data-ttu-id="970e1-107">È consigliabile creare un nuovo database nel server e dedicarlo al data mining oppure chiedere all'amministratore di preparare un server di data mining da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="970e1-107">We recommend that you create a new database on the server and dedicate the new database to data mining, or ask your administrator to prepare a data mining server for you.</span></span> <span data-ttu-id="970e1-108">In tal modo è possibile compilare modelli senza influire sulle prestazioni degli altri servizi.</span><span class="sxs-lookup"><span data-stu-id="970e1-108">That way you can build models without affecting the performance of other services.</span></span>  
  
 <span data-ttu-id="970e1-109">Si noti che il server di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] utilizzato per il data mining non necessariamente deve trovarsi nello stesso server dei dati di origine.</span><span class="sxs-lookup"><span data-stu-id="970e1-109">Note that the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] server that you use for data mining does not need to be on the same server as your source data.</span></span>  
  
 <span data-ttu-id="970e1-110">**Nome server**</span><span class="sxs-lookup"><span data-stu-id="970e1-110">**Server name**</span></span>  
 <span data-ttu-id="970e1-111">Digitare il nome del server contenente l'istanza di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] che verrà utilizzata per il data mining.</span><span class="sxs-lookup"><span data-stu-id="970e1-111">Type the name of the server that contains the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] that you will use for data mining.</span></span>  
  
 <span data-ttu-id="970e1-112">**autenticazione**</span><span class="sxs-lookup"><span data-stu-id="970e1-112">**Authentication**</span></span>  
 <span data-ttu-id="970e1-113">Specificare i metodi di autenticazione.</span><span class="sxs-lookup"><span data-stu-id="970e1-113">Specify the authentication methods.</span></span> <span data-ttu-id="970e1-114">L'autenticazione di Windows è obbligatoria per le connessioni a [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], a meno che l'amministratore non abbia configurato l'accesso al server tramite HTTPPump.</span><span class="sxs-lookup"><span data-stu-id="970e1-114">Windows Authentication is required for connections to [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], unless your administrator has configured access to the server via the HTTPPump.</span></span>  
  
##  <a name="step-2-allow-temporary-models"></a><a name="bkmk_step2"></a><span data-ttu-id="970e1-115">Passaggio 2: consentire i modelli temporanei</span><span class="sxs-lookup"><span data-stu-id="970e1-115">Step 2: Allow Temporary Models</span></span>  
 <span data-ttu-id="970e1-116">Per poter utilizzare i componenti aggiuntivi, è necessario modificare una proprietà del server di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] per consentire la creazione di modelli di data mining temporanei.</span><span class="sxs-lookup"><span data-stu-id="970e1-116">Before you can use the add-ins, an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] server property must be changed to permit the creation of temporary mining models.</span></span>  
  
 <span data-ttu-id="970e1-117">I modelli di data mining temporanei sono anche denominati *modelli di sessione*.</span><span class="sxs-lookup"><span data-stu-id="970e1-117">Temporary mining models are also called *session models*.</span></span> <span data-ttu-id="970e1-118">in quanto i modelli rimangono archiviati solo fino a quando la sessione corrente è aperta.</span><span class="sxs-lookup"><span data-stu-id="970e1-118">This is because the models are stored only as long as your current session is open.</span></span> <span data-ttu-id="970e1-119">Quando si chiude la connessione al server, la sessione viene terminata e i modelli utilizzati durante la sessione vengono eliminati.</span><span class="sxs-lookup"><span data-stu-id="970e1-119">When you close your connection to the server, the session is ended and any models used during the session are deleted.</span></span>  
  
 <span data-ttu-id="970e1-120">L'utilizzo di modelli di data mining di sessione non influisce sullo spazio di archiviazione del server, mentre l'overhead causato dalla creazione di modelli di data mining può ridurre le prestazioni del server.</span><span class="sxs-lookup"><span data-stu-id="970e1-120">The use of session mining models does not affect storage space on the server, but the overhead involved in creating data mining models may affect the performance of the server.</span></span>  
  
 <span data-ttu-id="970e1-121">Durante la procedura guidata vengono innanzitutto rilevate le impostazioni specificate nel server.</span><span class="sxs-lookup"><span data-stu-id="970e1-121">The wizard first detects the settings on the server that you specified.</span></span> <span data-ttu-id="970e1-122">Se il server consente già i modelli di data mining temporanei, è possibile fare clic su **Avanti** per continuare.</span><span class="sxs-lookup"><span data-stu-id="970e1-122">If the server already allows temporary mining models, you can click **Next** to continue.</span></span> <span data-ttu-id="970e1-123">La procedura guidata fornisce inoltre le istruzioni relative all'abilitazione dei modelli di data mining temporanei nel server di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] specificato o le indicazioni per effettuare una richiesta all'amministratore di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="970e1-123">The wizard also provides instructions for how to enable temporary mining models on the specified [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] server, or how to make a request to your [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] administrator.</span></span>  
  
##  <a name="step-3-create-database-for-add-in-users"></a><a name="bkmk_step3"></a><span data-ttu-id="970e1-124">Passaggio 3: creare il database per gli utenti dei componenti aggiuntivi</span><span class="sxs-lookup"><span data-stu-id="970e1-124">Step 3: Create Database for Add-in Users</span></span>  
 <span data-ttu-id="970e1-125">In questa pagina della procedura guidata di installazione e configurazione è possibile creare un nuovo database dedicato al data mining o selezionare un database di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] esistente.</span><span class="sxs-lookup"><span data-stu-id="970e1-125">On this page of the setup and configuration wizard, you can create a new database that is dedicated to data mining, or select an existing [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="970e1-126">Per il data mining è richiesta un'istanza di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] in esecuzione in modalità multidimensionale.</span><span class="sxs-lookup"><span data-stu-id="970e1-126">Data mining requires an instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] that is running in multidimensional mode.</span></span> <span data-ttu-id="970e1-127">La modalità tabulare non supporta il data mining.</span><span class="sxs-lookup"><span data-stu-id="970e1-127">Tabular mode does not support data mining.</span></span>  
  
 <span data-ttu-id="970e1-128">È consigliabile creare un database separato dedicato al data mining.</span><span class="sxs-lookup"><span data-stu-id="970e1-128">We recommend that you create a separate database dedicated to data mining.</span></span> <span data-ttu-id="970e1-129">In questo modo è possibile provare a utilizzare i modelli di data mining senza influire su altri oggetti della soluzione.</span><span class="sxs-lookup"><span data-stu-id="970e1-129">This lets you experiment with data mining models without affecting other solution objects.</span></span>  
  
 <span data-ttu-id="970e1-130">Se si sceglie un database in un'istanza di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], è possibile sovrascrivere i modelli esistenti se si utilizzano i componenti aggiuntivi per creare un modello il cui nome corrisponde a quello di un modello già esistente.</span><span class="sxs-lookup"><span data-stu-id="970e1-130">If you choose an existing database on an instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], note that it is possible to overwrite existing models if you use the add-ins to create a model and a model of that name already exists.</span></span>  
  
 <span data-ttu-id="970e1-131">**Creare il nuovo database**</span><span class="sxs-lookup"><span data-stu-id="970e1-131">**Create new database**</span></span>  
 <span data-ttu-id="970e1-132">Selezionare questa opzione per creare un nuovo database nel server selezionato.</span><span class="sxs-lookup"><span data-stu-id="970e1-132">Select this option to create a new database on the selected server.</span></span> <span data-ttu-id="970e1-133">In un database di data mining vengono archiviati origini dati, strutture e modelli di data mining.</span><span class="sxs-lookup"><span data-stu-id="970e1-133">A data mining database will store your data sources, mining structures, and mining models.</span></span>  
  
 <span data-ttu-id="970e1-134">**Nome database**</span><span class="sxs-lookup"><span data-stu-id="970e1-134">**Database name**</span></span>  
 <span data-ttu-id="970e1-135">Digitare il nome del nuovo database.</span><span class="sxs-lookup"><span data-stu-id="970e1-135">Type the name of the new database.</span></span> <span data-ttu-id="970e1-136">Se il nome non è già in uso, verrà creato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="970e1-136">If the name is not already in use, it will be created for you.</span></span>  
  
 <span data-ttu-id="970e1-137">**Utilizza database esistente**</span><span class="sxs-lookup"><span data-stu-id="970e1-137">**Use existing database**</span></span>  
 <span data-ttu-id="970e1-138">Selezionare questa opzione per utilizzare un database di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] esistente.</span><span class="sxs-lookup"><span data-stu-id="970e1-138">Select this option to use an existing [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database.</span></span>  
  
 <span data-ttu-id="970e1-139">**Database**</span><span class="sxs-lookup"><span data-stu-id="970e1-139">**Database**</span></span>  
 <span data-ttu-id="970e1-140">Se si sceglie l'opzione per utilizzare un database esistente, è necessario selezionare il nome del database nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="970e1-140">If you chose the option to use an existing database, you must select the database name from the list.</span></span>  
  
##  <a name="step-4-give-add-in-users-appropriate-permissions"></a><a name="bkmk_step4"></a><span data-ttu-id="970e1-141">Passaggio 4: concedere agli utenti del componente aggiuntivo le autorizzazioni appropriate</span><span class="sxs-lookup"><span data-stu-id="970e1-141">Step 4: Give Add-in Users Appropriate Permissions</span></span>  
 <span data-ttu-id="970e1-142">È necessario verificare che tutti gli utenti dei componenti aggiuntivi dispongano delle autorizzazioni necessarie per esplorare, modificare, elaborare o creare strutture e modelli di data mining.</span><span class="sxs-lookup"><span data-stu-id="970e1-142">You must ensure that you (and any other users of the add-ins) have the necessary permissions to browse, edit, process, or create data mining structures and models.</span></span>  
  
 <span data-ttu-id="970e1-143">Per impostazione predefinita, per utilizzare i componenti aggiuntivi è necessaria l'autenticazione integrata di Windows.</span><span class="sxs-lookup"><span data-stu-id="970e1-143">By default, integrated Windows Authentication is required to use the add-ins.</span></span>  
  
 <span data-ttu-id="970e1-144">**Assegna le autorizzazioni di amministratore del database agli utenti dei componenti aggiuntivi**</span><span class="sxs-lookup"><span data-stu-id="970e1-144">**Give add-in users database administration permissions**</span></span>  
 <span data-ttu-id="970e1-145">Selezionare questa opzione per concedere l'accesso amministrativo al database agli utenti elencati.</span><span class="sxs-lookup"><span data-stu-id="970e1-145">Select this option to give the listed users administrative access to the database.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="970e1-146">Queste autorizzazioni si applicano solo al database elencato nella casella **nome database** .</span><span class="sxs-lookup"><span data-stu-id="970e1-146">These permissions apply only to the database listed in the **Database name** box.</span></span>  
  
 <span data-ttu-id="970e1-147">**Nome database**</span><span class="sxs-lookup"><span data-stu-id="970e1-147">**Database name**</span></span>  
 <span data-ttu-id="970e1-148">Consente di visualizzare il nome del database selezionato.</span><span class="sxs-lookup"><span data-stu-id="970e1-148">Displays the name of the selected database.</span></span>  
  
 <span data-ttu-id="970e1-149">**Specificare gli utenti o i gruppi da aggiungere**</span><span class="sxs-lookup"><span data-stu-id="970e1-149">**Specify users or groups to add**</span></span>  
 <span data-ttu-id="970e1-150">Selezionare gli account di accesso che potranno accedere al database utilizzato per il data mining.</span><span class="sxs-lookup"><span data-stu-id="970e1-150">Select the logins that will have access to the database used for data mining.</span></span>  
  
 <span data-ttu-id="970e1-151">**Aggiungere**</span><span class="sxs-lookup"><span data-stu-id="970e1-151">**Add**</span></span>  
 <span data-ttu-id="970e1-152">Fare clic per aprire una finestra di dialogo e aggiungere utenti o gruppi.</span><span class="sxs-lookup"><span data-stu-id="970e1-152">Click to open a dialog box and add users or groups.</span></span>  
  
 <span data-ttu-id="970e1-153">**Rimuovi**</span><span class="sxs-lookup"><span data-stu-id="970e1-153">**Remove**</span></span>  
 <span data-ttu-id="970e1-154">Fare clic per rimuovere l'utente o il gruppo selezionato dall'elenco di utenti con autorizzazioni di amministratore.</span><span class="sxs-lookup"><span data-stu-id="970e1-154">Click to remove the selected user or group from the list of users with administration permissions.</span></span>  
  
  
