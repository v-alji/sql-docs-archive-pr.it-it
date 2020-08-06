---
title: Connettersi a Microsoft SQL Server Analysis Services (SSAS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.connsqlserveras.f1
ms.assetid: 7f3244ee-b690-471c-893d-68e361c2d416
author: minewiskan
ms.author: owend
ms.openlocfilehash: 984979480e3ea54c86c986fa6dd9771aaf879cb1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625704"
---
# <a name="connect-to-microsoft-sql-server-analysis-services-ssas"></a><span data-ttu-id="d6ec5-102">Connessione a Microsoft SQL Server Analysis Services (SSAS)</span><span class="sxs-lookup"><span data-stu-id="d6ec5-102">Connect to Microsoft SQL Server Analysis Services (SSAS)</span></span>
  <span data-ttu-id="d6ec5-103">Questa pagina dell' **importazione guidata tabella** consente di specificare le impostazioni per l'importazione di dati da un Microsoft SQL Server Analysis Services cubo o da una cartella di lavoro di PowerPivot ospitata in SharePoint.</span><span class="sxs-lookup"><span data-stu-id="d6ec5-103">This page of the **Table Import Wizard** enables you to specify settings to import data from a Microsoft SQL Server Analysis Services cube or a PowerPivot workbook that is hosted on SharePoint.</span></span> <span data-ttu-id="d6ec5-104">Per accedere alla procedura guidata da [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], dal menu **Modello** selezionare **Importa da origine dati**.</span><span class="sxs-lookup"><span data-stu-id="d6ec5-104">To access the wizard from the [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], on the **Model** menu, click **Import from Data Source**.</span></span>  
  
 <span data-ttu-id="d6ec5-105">Per connettersi a un'origine dati, è necessario che nel computer sia installato il provider appropriato.</span><span class="sxs-lookup"><span data-stu-id="d6ec5-105">To connect to a data source, you must have the appropriate provider installed on your computer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d6ec5-106">Le credenziali dell'utente corrente vengono utilizzate in caso di selezione di un database in questa pagina.</span><span class="sxs-lookup"><span data-stu-id="d6ec5-106">The credentials of the current user are used when selecting a database in this page.</span></span> <span data-ttu-id="d6ec5-107">Tuttavia, l'importazione non verrà completata se l'utente specificato nella pagina Impostazioni di rappresentazione non dispone di privilegi sufficienti per leggere dal database selezionato.</span><span class="sxs-lookup"><span data-stu-id="d6ec5-107">However, import will not succeed if the user specified in the Impersonation Information page does not have sufficient privileges to read from the selected database.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="d6ec5-108">Elenco di elementi dell'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="d6ec5-108">UI element list</span></span>  
 <span data-ttu-id="d6ec5-109">**Nome descrittivo connessione**</span><span class="sxs-lookup"><span data-stu-id="d6ec5-109">**Friendly connection name**</span></span>  
 <span data-ttu-id="d6ec5-110">Digitare un nome univoco per questa connessione all'origine dati.</span><span class="sxs-lookup"><span data-stu-id="d6ec5-110">Type a unique name for this data source connection.</span></span> <span data-ttu-id="d6ec5-111">Questo campo è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="d6ec5-111">This is a required field.</span></span>  
  
 <span data-ttu-id="d6ec5-112">**Nome file o server**</span><span class="sxs-lookup"><span data-stu-id="d6ec5-112">**Server or File Name**</span></span>  
 <span data-ttu-id="d6ec5-113">Eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d6ec5-113">Enter one of the following:</span></span>  
  
-   <span data-ttu-id="d6ec5-114">Digitare il nome o l'indirizzo IP del server SQL Server Analysis Services al quale connettersi.</span><span class="sxs-lookup"><span data-stu-id="d6ec5-114">Type the name or IP address of the SQL Server Analysis Services server to connect to.</span></span>  
  
     <span data-ttu-id="d6ec5-115">Per specificare il server locale, è possibile digitare un punto (.), (locale) o localhost.</span><span class="sxs-lookup"><span data-stu-id="d6ec5-115">You can use a period (.), (local), or localhost to indicate the local server.</span></span>  
  
-   <span data-ttu-id="d6ec5-116">Digitare l'URL di una cartella di lavoro PowerPivot pubblicata in SharePoint.</span><span class="sxs-lookup"><span data-stu-id="d6ec5-116">Type the URL of a PowerPivot workbook that is published to SharePoint.</span></span>  
  
 <span data-ttu-id="d6ec5-117">**Usa autenticazione di Windows**</span><span class="sxs-lookup"><span data-stu-id="d6ec5-117">**Use Windows Authentication**</span></span>  
 <span data-ttu-id="d6ec5-118">Specificare se utilizzare l'autenticazione di Windows per connettersi a un server SQL Server Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="d6ec5-118">Specify whether Windows Authentication is used to connect to a SQL Server Analysis Services server.</span></span>  
  
 <span data-ttu-id="d6ec5-119">La modalità di autenticazione di Windows consente a un utente di connettersi mediante un account utente di Windows.</span><span class="sxs-lookup"><span data-stu-id="d6ec5-119">Windows Authentication mode enables a user to connect through a Windows user account.</span></span> <span data-ttu-id="d6ec5-120">Se possibile, è consigliabile utilizzare l'autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="d6ec5-120">Whenever possible, use Windows Authentication.</span></span>  
  
 <span data-ttu-id="d6ec5-121">Quando viene utilizzato questo tipo di autenticazione, le credenziali dell'utente corrente vengono utilizzate in caso di visualizzazione in anteprima e filtro dei dati nella finestra Proprietà tabella e nell'Importazione guidata.</span><span class="sxs-lookup"><span data-stu-id="d6ec5-121">When Windows Authentication is used, the credentials of the current user are used when previewing and filtering data in the Table Properties window and in the Import Wizard.</span></span> <span data-ttu-id="d6ec5-122">Non vengono utilizzate per importare o aggiornare dati; in tal caso vengono infatti utilizzate le credenziali di Windows specificate nella pagina Impostazioni di rappresentazione.</span><span class="sxs-lookup"><span data-stu-id="d6ec5-122">These credentials are not used to import or refresh data; the Windows credentials specified on the Impersonation Information page are used instead.</span></span>  
  
 <span data-ttu-id="d6ec5-123">**Usa autenticazione di SQL Server**</span><span class="sxs-lookup"><span data-stu-id="d6ec5-123">**Use SQL Server Authentication**</span></span>  
 <span data-ttu-id="d6ec5-124">Specificare se utilizzare l'autenticazione di SQL Server per connettersi a un server SQL Server Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="d6ec5-124">Specify whether SQL Server Authentication is used to connect to a SQL Server Analysis Services server.</span></span>  
  
 <span data-ttu-id="d6ec5-125">Con questo tipo di autenticazione, in SQL Server l'autenticazione viene eseguita verificando che sia stato impostato un account di accesso di SQL Server e che la password specificata corrisponda a quella registrata in precedenza.</span><span class="sxs-lookup"><span data-stu-id="d6ec5-125">With SQL Server Authentication, SQL Server performs the authentication itself by checking to see if a SQL Server login account has been set up and if the specified password matches the one previously recorded.</span></span>  
  
 <span data-ttu-id="d6ec5-126">L'autenticazione di SQL Server viene utilizzata quando si crea la stringa di connessione per l'origine dati.</span><span class="sxs-lookup"><span data-stu-id="d6ec5-126">SQL Server Authentication is used to construct the connection string for the data source.</span></span> <span data-ttu-id="d6ec5-127">Queste credenziali vengono utilizzate anche in caso di visualizzazione in anteprima e filtro dei dati nella finestra Proprietà tabella e nell'Importazione guidata.</span><span class="sxs-lookup"><span data-stu-id="d6ec5-127">These credentials are also used when previewing and filtering data in the Table Properties window and in the Import Wizard.</span></span> <span data-ttu-id="d6ec5-128">Non vengono utilizzate per importare o aggiornare dati; in tal caso vengono infatti utilizzate le credenziali di Windows specificate nella pagina Impostazioni di rappresentazione.</span><span class="sxs-lookup"><span data-stu-id="d6ec5-128">These credentials are not used to import or refresh data; the Windows credentials specified on the Impersonation Information page are used instead.</span></span>  
  
 <span data-ttu-id="d6ec5-129">**Nome utente**</span><span class="sxs-lookup"><span data-stu-id="d6ec5-129">**User name**</span></span>  
 <span data-ttu-id="d6ec5-130">Specificare un nome utente per la connessione al database.</span><span class="sxs-lookup"><span data-stu-id="d6ec5-130">Specify a user name for the database connection.</span></span> <span data-ttu-id="d6ec5-131">Questa opzione è disponibile solo si è scelto di utilizzare l'autenticazione di Windows per la connessione.</span><span class="sxs-lookup"><span data-stu-id="d6ec5-131">This option is only available if you have selected to connect using Windows Authentication.</span></span>  
  
 <span data-ttu-id="d6ec5-132">**Password**</span><span class="sxs-lookup"><span data-stu-id="d6ec5-132">**Password**</span></span>  
 <span data-ttu-id="d6ec5-133">Specificare una password per la connessione al database.</span><span class="sxs-lookup"><span data-stu-id="d6ec5-133">Specify a password for the database connection.</span></span> <span data-ttu-id="d6ec5-134">Questa opzione è modificabile solo se è stata selezionata l'autenticazione di SQL Server per la connessione.</span><span class="sxs-lookup"><span data-stu-id="d6ec5-134">This option is only editable if you have selected to connect using SQL Server Authentication.</span></span>  
  
 <span data-ttu-id="d6ec5-135">**Salva password**</span><span class="sxs-lookup"><span data-stu-id="d6ec5-135">**Save my password**</span></span>  
 <span data-ttu-id="d6ec5-136">Specificare se la password immessa nella casella **Password** è stata archiviata.</span><span class="sxs-lookup"><span data-stu-id="d6ec5-136">Specify whether the password you have entered in the **Password** box is stored.</span></span> <span data-ttu-id="d6ec5-137">Questa opzione è disponibile solo se è stata selezionata l'autenticazione di SQL Server per la connessione.</span><span class="sxs-lookup"><span data-stu-id="d6ec5-137">This option is only available if you have selected to connect using SQL Server Authentication.</span></span>  
  
 <span data-ttu-id="d6ec5-138">**Nome database**</span><span class="sxs-lookup"><span data-stu-id="d6ec5-138">**Database name**</span></span>  
 <span data-ttu-id="d6ec5-139">Selezionare un database dall'elenco di database.</span><span class="sxs-lookup"><span data-stu-id="d6ec5-139">Select a database from the list of databases.</span></span>  
  
 <span data-ttu-id="d6ec5-140">**Funzionalità avanzate**</span><span class="sxs-lookup"><span data-stu-id="d6ec5-140">**Advanced**</span></span>  
 <span data-ttu-id="d6ec5-141">Per impostare ulteriori proprietà della connessione, utilizzare la finestra di dialogo **Imposta proprietà avanzate** .</span><span class="sxs-lookup"><span data-stu-id="d6ec5-141">Set additional connection properties by using the **Set Advanced Properties** dialog box.</span></span> <span data-ttu-id="d6ec5-142">Per altre informazioni, vedere [Impostazione delle proprietà avanzate &#40;SSAS&#41;](set-advanced-properties-ssas.md).</span><span class="sxs-lookup"><span data-stu-id="d6ec5-142">For more information, see [Set Advanced Properties &#40;SSAS&#41;](set-advanced-properties-ssas.md).</span></span>  
  
 <span data-ttu-id="d6ec5-143">**Test connessione**</span><span class="sxs-lookup"><span data-stu-id="d6ec5-143">**Test Connection**</span></span>  
 <span data-ttu-id="d6ec5-144">Provare a stabilire una connessione all'origine dati utilizzando le impostazioni correnti.</span><span class="sxs-lookup"><span data-stu-id="d6ec5-144">Attempt to establish a connection to the data source using the current settings.</span></span> <span data-ttu-id="d6ec5-145">Viene visualizzato un messaggio che indica se la connessione è stata stabilita.</span><span class="sxs-lookup"><span data-stu-id="d6ec5-145">A message is displayed indicating whether the connection is successful.</span></span>  
  
  
