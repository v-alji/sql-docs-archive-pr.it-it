---
title: Connettersi a un database di Microsoft SQL Server (SSAS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.connsqlserverdb.f1
ms.assetid: 6ebfe029-dbba-4f0d-a556-328e79ef629f
author: minewiskan
ms.author: owend
ms.openlocfilehash: 64267cd65836cf8e6c8d8b26a177de595894b601
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625727"
---
# <a name="connect-to-a-microsoft-sql-server-database-ssas"></a><span data-ttu-id="f46b6-102">Connessione a un database di Microsoft SQL Server (SSAS)</span><span class="sxs-lookup"><span data-stu-id="f46b6-102">Connect to a Microsoft SQL Server Database (SSAS)</span></span>
  <span data-ttu-id="f46b6-103">Questa pagina dell' **Importazione guidata tabella** consente di specificare le impostazioni per connettersi a un database di Microsoft SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f46b6-103">This page of the **Table Import Wizard** enables you to specify settings to connect to a Microsoft SQL Server database.</span></span> <span data-ttu-id="f46b6-104">Per accedere alla procedura guidata da [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], dal menu **Modello** selezionare **Importa da origine dati**.</span><span class="sxs-lookup"><span data-stu-id="f46b6-104">To access the wizard from the [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], on the **Model** menu, click **Import from Data Source**.</span></span>  
  
 <span data-ttu-id="f46b6-105">Per connettersi a un'origine dati, è necessario che nel computer sia installato il provider appropriato.</span><span class="sxs-lookup"><span data-stu-id="f46b6-105">To connect to a data source, you must have the appropriate provider installed on your computer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f46b6-106">Le credenziali dell'utente corrente vengono utilizzate in caso di selezione di un database in questa pagina.</span><span class="sxs-lookup"><span data-stu-id="f46b6-106">The credentials of the current user are used when selecting a database in this page.</span></span> <span data-ttu-id="f46b6-107">Tuttavia, l'importazione non verrà completata se l'utente specificato nella pagina Impostazioni di rappresentazione non dispone di privilegi sufficienti per leggere dal database selezionato.</span><span class="sxs-lookup"><span data-stu-id="f46b6-107">However, import will not succeed if the user specified in the Impersonation Information page does not have sufficient privileges to read from the selected database.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="f46b6-108">Elenco di elementi dell'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="f46b6-108">UI element list</span></span>  
 <span data-ttu-id="f46b6-109">**Nome descrittivo connessione**</span><span class="sxs-lookup"><span data-stu-id="f46b6-109">**Friendly connection name**</span></span>  
 <span data-ttu-id="f46b6-110">Digitare un nome univoco per questa connessione all'origine dati.</span><span class="sxs-lookup"><span data-stu-id="f46b6-110">Type a unique name for this data source connection.</span></span> <span data-ttu-id="f46b6-111">Questo campo è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="f46b6-111">This is a required field.</span></span>  
  
 <span data-ttu-id="f46b6-112">**Nome server**</span><span class="sxs-lookup"><span data-stu-id="f46b6-112">**Server name**</span></span>  
 <span data-ttu-id="f46b6-113">Selezionare il nome o digitare il nome o l'indirizzo IP dell'istanza di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="f46b6-113">Select the name, or type the name or IP address, of the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] instance to connect to.</span></span>  
  
 <span data-ttu-id="f46b6-114">Per specificare il server locale, è possibile digitare un punto (.), (locale) o localhost.</span><span class="sxs-lookup"><span data-stu-id="f46b6-114">You can use a period (.), (local), or localhost to indicate the local server.</span></span>  
  
 <span data-ttu-id="f46b6-115">**Usa autenticazione di Windows**</span><span class="sxs-lookup"><span data-stu-id="f46b6-115">**Use Windows Authentication**</span></span>  
 <span data-ttu-id="f46b6-116">Specificare se usare l'autenticazione di Windows per connettersi a un'istanza di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f46b6-116">Specify whether Windows Authentication is used to connect to an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="f46b6-117">L'autenticazione di Windows consente a un utente di connettersi tramite un account utente di Windows.</span><span class="sxs-lookup"><span data-stu-id="f46b6-117">Windows Authentication mode enables a user to connect by using a Windows user account.</span></span> <span data-ttu-id="f46b6-118">Se possibile, è consigliabile utilizzare l'autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="f46b6-118">Whenever possible, use Windows Authentication.</span></span>  
  
 <span data-ttu-id="f46b6-119">Quando viene utilizzato questo tipo di autenticazione, le credenziali dell'utente corrente vengono utilizzate in caso di visualizzazione in anteprima e filtro dei dati nella finestra Proprietà tabella e nell'Importazione guidata.</span><span class="sxs-lookup"><span data-stu-id="f46b6-119">When Windows Authentication is used, the credentials of the current user are used when previewing and filtering data in the Table Properties window and in the Import Wizard.</span></span> <span data-ttu-id="f46b6-120">Tali credenziali non vengono utilizzate per importare o aggiornare dati; in tal caso vengono infatti utilizzate le credenziali di Windows specificate nella pagina Impostazioni di rappresentazione.</span><span class="sxs-lookup"><span data-stu-id="f46b6-120">These credentials are not used to import or refresh data; the Windows credentials specified on the Impersonation information page are used instead.</span></span>  
  
 <span data-ttu-id="f46b6-121">**Usa autenticazione di SQL Server**</span><span class="sxs-lookup"><span data-stu-id="f46b6-121">**Use SQL Server Authentication**</span></span>  
 <span data-ttu-id="f46b6-122">Specificare se usare l'autenticazione di SQL Server per connettersi a un'istanza di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f46b6-122">Specify whether SQL Server Authentication is used to connect to an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="f46b6-123">Con questo tipo di autenticazione, in SQL Server l'autenticazione viene eseguita verificando che sia stato impostato un account di accesso di SQL Server e che la password specificata corrisponda a quella registrata in precedenza.</span><span class="sxs-lookup"><span data-stu-id="f46b6-123">With SQL Server Authentication, SQL Server performs the authentication itself by checking to see if a SQL Server login account has been set up and if the specified password matches the one previously recorded.</span></span>  
  
 <span data-ttu-id="f46b6-124">L'autenticazione di SQL Server viene utilizzata quando si crea la stringa di connessione per l'origine dati.</span><span class="sxs-lookup"><span data-stu-id="f46b6-124">SQL Server Authentication is used to construct the connection string for the data source.</span></span> <span data-ttu-id="f46b6-125">Queste credenziali vengono utilizzate anche in caso di visualizzazione in anteprima e filtro dei dati nella finestra Proprietà tabella e nell'Importazione guidata.</span><span class="sxs-lookup"><span data-stu-id="f46b6-125">These credentials are also used when previewing and filtering data in the Table Properties window and in the Import Wizard.</span></span> <span data-ttu-id="f46b6-126">Non vengono utilizzate per importare o aggiornare dati; in tal caso vengono infatti utilizzate le credenziali di Windows specificate nella pagina Impostazioni di rappresentazione.</span><span class="sxs-lookup"><span data-stu-id="f46b6-126">These credentials are not used to import or refresh data; the Windows credentials specified on the Impersonation Information page are used instead.</span></span>  
  
 <span data-ttu-id="f46b6-127">**Nome utente**</span><span class="sxs-lookup"><span data-stu-id="f46b6-127">**User name**</span></span>  
 <span data-ttu-id="f46b6-128">Specificare un nome utente per la connessione al database.</span><span class="sxs-lookup"><span data-stu-id="f46b6-128">Specify a user name for the database connection.</span></span> <span data-ttu-id="f46b6-129">Questa opzione è disponibile solo se è stata selezionata l'autenticazione di SQL Server per la connessione.</span><span class="sxs-lookup"><span data-stu-id="f46b6-129">This option is only available if you have selected to connect using SQL Server Authentication.</span></span>  
  
 <span data-ttu-id="f46b6-130">**Password**</span><span class="sxs-lookup"><span data-stu-id="f46b6-130">**Password**</span></span>  
 <span data-ttu-id="f46b6-131">Specificare una password per la connessione al database.</span><span class="sxs-lookup"><span data-stu-id="f46b6-131">Specify a password for the database connection.</span></span> <span data-ttu-id="f46b6-132">Questa opzione è modificabile solo se è stata selezionata l'autenticazione di SQL Server per la connessione.</span><span class="sxs-lookup"><span data-stu-id="f46b6-132">This option is only editable if you have selected to connect using SQL Server Authentication.</span></span>  
  
 <span data-ttu-id="f46b6-133">**Salva password**</span><span class="sxs-lookup"><span data-stu-id="f46b6-133">**Save my password**</span></span>  
 <span data-ttu-id="f46b6-134">Specificare se la password immessa nella casella **Password** è stata archiviata.</span><span class="sxs-lookup"><span data-stu-id="f46b6-134">Specify whether the password you have entered in the **Password** box is stored.</span></span> <span data-ttu-id="f46b6-135">Questa opzione è disponibile solo se è stata selezionata l'autenticazione di SQL Server per la connessione.</span><span class="sxs-lookup"><span data-stu-id="f46b6-135">This option is only available if you have selected to connect using SQL Server Authentication.</span></span>  
  
 <span data-ttu-id="f46b6-136">**Nome database**</span><span class="sxs-lookup"><span data-stu-id="f46b6-136">**Database name**</span></span>  
 <span data-ttu-id="f46b6-137">Selezionare un database dall'elenco di database.</span><span class="sxs-lookup"><span data-stu-id="f46b6-137">Select a database from the list of databases.</span></span>  
  
 <span data-ttu-id="f46b6-138">**Funzionalità avanzate**</span><span class="sxs-lookup"><span data-stu-id="f46b6-138">**Advanced**</span></span>  
 <span data-ttu-id="f46b6-139">Per impostare ulteriori proprietà della connessione, utilizzare la finestra di dialogo **Imposta proprietà avanzate** .</span><span class="sxs-lookup"><span data-stu-id="f46b6-139">Set additional connection properties by using the **Set Advanced Properties** dialog box.</span></span> <span data-ttu-id="f46b6-140">Per altre informazioni, vedere [Impostazione delle proprietà avanzate &#40;SSAS&#41;](set-advanced-properties-ssas.md).</span><span class="sxs-lookup"><span data-stu-id="f46b6-140">For more information, see [Set Advanced Properties &#40;SSAS&#41;](set-advanced-properties-ssas.md).</span></span>  
  
 <span data-ttu-id="f46b6-141">**Test connessione**</span><span class="sxs-lookup"><span data-stu-id="f46b6-141">**Test Connection**</span></span>  
 <span data-ttu-id="f46b6-142">Provare a stabilire una connessione all'origine dati utilizzando le impostazioni correnti.</span><span class="sxs-lookup"><span data-stu-id="f46b6-142">Attempt to establish a connection to the data source using the current settings.</span></span> <span data-ttu-id="f46b6-143">Viene visualizzato un messaggio che indica se la connessione è stata stabilita.</span><span class="sxs-lookup"><span data-stu-id="f46b6-143">A message is displayed indicating whether the connection was successful.</span></span>  
  
  
