---
title: Connettersi a un database SQL di Azure (SSAS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.connsqlazure.f1
ms.assetid: 4e0344e9-1822-4698-ad22-05f1f341ced7
author: minewiskan
ms.author: owend
ms.openlocfilehash: 91ae6f0f5ab95d3013b6348bd43ddb746fff1c22
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625717"
---
# <a name="connect-to-an-azure-sql-database-ssas"></a><span data-ttu-id="a4b64-102">Connessione a un database SQL di Azure (SSAS)</span><span class="sxs-lookup"><span data-stu-id="a4b64-102">Connect to an Azure SQL Database (SSAS)</span></span>
  <span data-ttu-id="a4b64-103">Questa pagina dell' **Importazione guidata tabella** consente di connettersi a un [!INCLUDE[ssSDSfull](../includes/sssdsfull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a4b64-103">This page of the **Table Import Wizard** enables you to connect to a [!INCLUDE[ssSDSfull](../includes/sssdsfull-md.md)].</span></span> <span data-ttu-id="a4b64-104">Per accedere alla procedura guidata da [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], dal menu **Modello** selezionare **Importa da origine dati**.</span><span class="sxs-lookup"><span data-stu-id="a4b64-104">To access the wizard from the [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], on the **Model** menu, click **Import from Data Source**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a4b64-105">Per la connessione a un set di dati di Azure DataMarket, vedere [Connettersi a un report o a un feed di dati &#40;SSAS&#41;](connect-to-a-report-or-data-feed-ssas.md).</span><span class="sxs-lookup"><span data-stu-id="a4b64-105">If you are connecting to an Azure DataMarket dataset, see [Connect to a Report or Data Feed &#40;SSAS&#41;](connect-to-a-report-or-data-feed-ssas.md).</span></span>  
  
 <span data-ttu-id="a4b64-106">[!INCLUDE[ssSDS](../includes/sssds-md.md)] è un database ospitato relazionale a cui è possibile connettersi tramite l'autenticazione di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a4b64-106">The [!INCLUDE[ssSDS](../includes/sssds-md.md)] is a hosted, relational database that you connect to by using SQL Server Authentication.</span></span> <span data-ttu-id="a4b64-107">Per altre informazioni su [!INCLUDE[ssSDS](../includes/sssds-md.md)], visitare il sito Web relativo al [database SQL](https://go.microsoft.com/fwlink/?LinkID=157856).</span><span class="sxs-lookup"><span data-stu-id="a4b64-107">For more information about [!INCLUDE[ssSDS](../includes/sssds-md.md)], see the web site [SQL Database](https://go.microsoft.com/fwlink/?LinkID=157856).</span></span> <span data-ttu-id="a4b64-108">Per connettersi a un'origine dati, è necessario che nel computer sia installato il provider appropriato.</span><span class="sxs-lookup"><span data-stu-id="a4b64-108">To connect to a data source, you must have the appropriate provider installed on your computer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a4b64-109">Le credenziali dell'utente corrente vengono utilizzate in caso di selezione di un database in questa pagina.</span><span class="sxs-lookup"><span data-stu-id="a4b64-109">The credentials of the current user are used when selecting a database in this page.</span></span> <span data-ttu-id="a4b64-110">Tuttavia, l'importazione non verrà completata se l'utente specificato nella pagina Impostazioni di rappresentazione non dispone di privilegi sufficienti per leggere dal database selezionato.</span><span class="sxs-lookup"><span data-stu-id="a4b64-110">However, import will not succeed if the user specified in the Impersonation Information page does not have sufficient privileges to read from the selected database.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="a4b64-111">Elenco di elementi dell'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="a4b64-111">UI element list</span></span>  
 <span data-ttu-id="a4b64-112">**Nome descrittivo connessione**</span><span class="sxs-lookup"><span data-stu-id="a4b64-112">**Friendly connection name**</span></span>  
 <span data-ttu-id="a4b64-113">Digitare un nome univoco per questa connessione all'origine dati.</span><span class="sxs-lookup"><span data-stu-id="a4b64-113">Type a unique name for this data source connection.</span></span> <span data-ttu-id="a4b64-114">Questo campo è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="a4b64-114">This is a required field.</span></span>  
  
 <span data-ttu-id="a4b64-115">**Nome server**</span><span class="sxs-lookup"><span data-stu-id="a4b64-115">**Server name**</span></span>  
 <span data-ttu-id="a4b64-116">Digitare il nome, o indirizzo IP, del server a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="a4b64-116">Type the name, or IP address, of the server to connect to.</span></span>  
  
 <span data-ttu-id="a4b64-117">**Nome utente**</span><span class="sxs-lookup"><span data-stu-id="a4b64-117">**User name**</span></span>  
 <span data-ttu-id="a4b64-118">Specificare un nome utente per la connessione al database.</span><span class="sxs-lookup"><span data-stu-id="a4b64-118">Specify a user name for the database connection.</span></span>  
  
 <span data-ttu-id="a4b64-119">Questo nome utente viene utilizzato quando si crea la stringa di connessione per l'origine dati.</span><span class="sxs-lookup"><span data-stu-id="a4b64-119">This user name is used when constructing the connection string for the data source.</span></span> <span data-ttu-id="a4b64-120">Queste credenziali vengono utilizzate anche in caso di visualizzazione in anteprima e filtro dei dati nella finestra Proprietà tabella e nell'Importazione guidata.</span><span class="sxs-lookup"><span data-stu-id="a4b64-120">These credentials are also used when previewing and filtering data in the Table Properties window and in the Import Wizard.</span></span> <span data-ttu-id="a4b64-121">Non vengono utilizzate per importare o aggiornare dati; in tal caso vengono infatti utilizzate le credenziali di Windows specificate nella pagina Impostazioni di rappresentazione.</span><span class="sxs-lookup"><span data-stu-id="a4b64-121">These credentials are not used to import or refresh data; the Windows credentials specified on the Impersonation Information page are used instead.</span></span>  
  
 <span data-ttu-id="a4b64-122">**Password**</span><span class="sxs-lookup"><span data-stu-id="a4b64-122">**Password**</span></span>  
 <span data-ttu-id="a4b64-123">Specificare una password per la connessione al database.</span><span class="sxs-lookup"><span data-stu-id="a4b64-123">Specify a password for the database connection.</span></span>  
  
 <span data-ttu-id="a4b64-124">**Salva password**</span><span class="sxs-lookup"><span data-stu-id="a4b64-124">**Save my password**</span></span>  
 <span data-ttu-id="a4b64-125">Specificare se la password immessa nella casella **Password** è stata archiviata.</span><span class="sxs-lookup"><span data-stu-id="a4b64-125">Specify whether the password you have entered in the **Password** box is stored.</span></span>  
  
 <span data-ttu-id="a4b64-126">**Nome database**</span><span class="sxs-lookup"><span data-stu-id="a4b64-126">**Database name**</span></span>  
 <span data-ttu-id="a4b64-127">Selezionare un database dall'elenco di database.</span><span class="sxs-lookup"><span data-stu-id="a4b64-127">Select a database from the list of databases.</span></span>  
  
 <span data-ttu-id="a4b64-128">**Funzionalità avanzate**</span><span class="sxs-lookup"><span data-stu-id="a4b64-128">**Advanced**</span></span>  
 <span data-ttu-id="a4b64-129">Per impostare ulteriori proprietà della connessione, utilizzare la finestra di dialogo **Imposta proprietà avanzate** .</span><span class="sxs-lookup"><span data-stu-id="a4b64-129">Set additional connection properties by using the **Set Advanced Properties** dialog box.</span></span> <span data-ttu-id="a4b64-130">Per altre informazioni, vedere [Impostazione delle proprietà avanzate &#40;SSAS&#41;](set-advanced-properties-ssas.md).</span><span class="sxs-lookup"><span data-stu-id="a4b64-130">For more information, see [Set Advanced Properties &#40;SSAS&#41;](set-advanced-properties-ssas.md).</span></span>  
  
 <span data-ttu-id="a4b64-131">**Test connessione**</span><span class="sxs-lookup"><span data-stu-id="a4b64-131">**Test Connection**</span></span>  
 <span data-ttu-id="a4b64-132">Provare a stabilire una connessione all'origine dati utilizzando le impostazioni correnti.</span><span class="sxs-lookup"><span data-stu-id="a4b64-132">Attempt to establish a connection to the data source using the current settings.</span></span> <span data-ttu-id="a4b64-133">Viene visualizzato un messaggio che indica se la connessione è stata stabilita.</span><span class="sxs-lookup"><span data-stu-id="a4b64-133">A message is displayed indicating whether the connection is successful.</span></span>  
  
  
