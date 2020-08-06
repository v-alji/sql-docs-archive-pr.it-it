---
title: Connettersi a un Microsoft SQL Server Parallel Data Warehouse (SSAS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.connsqlparadatawh.f1
ms.assetid: 98c879ee-7257-40c9-bc85-6766bd3b4885
author: minewiskan
ms.author: owend
ms.openlocfilehash: 082d6b34077d1bde11b527d3bfff907073eed16e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625720"
---
# <a name="connect-to-a-microsoft-sql-server-parallel-data-warehouse-ssas"></a><span data-ttu-id="965dc-102">Connettersi a Microsoft SQL Server Parallel Data Warehouse (SSAS)</span><span class="sxs-lookup"><span data-stu-id="965dc-102">Connect to a Microsoft SQL Server Parallel Data Warehouse (SSAS)</span></span>
  <span data-ttu-id="965dc-103">Questa pagina dell' **Importazione guidata tabella** consente di specificare le impostazioni per connettersi a Microsoft SQL Server Parallel Data Warehouse (PDW).</span><span class="sxs-lookup"><span data-stu-id="965dc-103">This page of the **Table Import Wizard** enables you to specify settings to connect to a Microsoft SQL Server Parallel Data Warehouse (PDW).</span></span> <span data-ttu-id="965dc-104">Per accedere alla procedura guidata da [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], dal menu **Modello** selezionare **Importa da origine dati**.</span><span class="sxs-lookup"><span data-stu-id="965dc-104">To access the wizard from the [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], on the **Model** menu, click **Import from Data Source**.</span></span>  
  
 <span data-ttu-id="965dc-105">SQL Server PDW è uno strumento estremamente scalabile che offre prestazioni a basso costo tramite un sistema di elaborazione parallela massiva.</span><span class="sxs-lookup"><span data-stu-id="965dc-105">SQL Server PDW is a highly scalable appliance that delivers performance at low cost through massively parallel processing.</span></span> <span data-ttu-id="965dc-106">Per altre informazioni su SQL Server PDW, vedere il sito Web [SQL Server 2008 R2 Parallel Data Warehouse](https://go.microsoft.com/fwlink/?LinkId=150895).</span><span class="sxs-lookup"><span data-stu-id="965dc-106">For more information about SQL Server PDW, see the web site [SQL Server 2008 R2 Parallel Data Warehouse](https://go.microsoft.com/fwlink/?LinkId=150895).</span></span> <span data-ttu-id="965dc-107">È possibile connettersi al data warehouse tramite l'autenticazione SQL Server.</span><span class="sxs-lookup"><span data-stu-id="965dc-107">You connect to the data warehouse by using SQL Server Authentication.</span></span> <span data-ttu-id="965dc-108">Per connettersi a un'origine dati, è necessario che nel computer sia installato il provider appropriato.</span><span class="sxs-lookup"><span data-stu-id="965dc-108">To connect to a data source, you must have the appropriate provider installed on your computer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="965dc-109">Le credenziali dell'utente corrente vengono utilizzate in caso di selezione di un database in questa pagina.</span><span class="sxs-lookup"><span data-stu-id="965dc-109">The credentials of the current user are used when selecting a database in this page.</span></span> <span data-ttu-id="965dc-110">Tuttavia, l'importazione non verrà completata se l'utente specificato nella pagina Impostazioni di rappresentazione non dispone di privilegi sufficienti per leggere dal database selezionato.</span><span class="sxs-lookup"><span data-stu-id="965dc-110">However, import will not succeed if the user specified in the Impersonation Information page does not have sufficient privileges to read from the selected database.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="965dc-111">Elenco di elementi dell'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="965dc-111">UI element list</span></span>  
 <span data-ttu-id="965dc-112">**Nome descrittivo connessione**</span><span class="sxs-lookup"><span data-stu-id="965dc-112">**Friendly connection name**</span></span>  
 <span data-ttu-id="965dc-113">Digitare un nome univoco per questa connessione all'origine dati.</span><span class="sxs-lookup"><span data-stu-id="965dc-113">Type a unique name for this data source connection.</span></span> <span data-ttu-id="965dc-114">Questo campo è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="965dc-114">This is a required field.</span></span>  
  
 <span data-ttu-id="965dc-115">**Nome server**</span><span class="sxs-lookup"><span data-stu-id="965dc-115">**Server name**</span></span>  
 <span data-ttu-id="965dc-116">Digitare il nome, o indirizzo IP, del server a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="965dc-116">Type the name, or IP address, of the server to connect to.</span></span>  
  
 <span data-ttu-id="965dc-117">**Nome utente**</span><span class="sxs-lookup"><span data-stu-id="965dc-117">**User name**</span></span>  
 <span data-ttu-id="965dc-118">Specificare un nome utente per la connessione al database.</span><span class="sxs-lookup"><span data-stu-id="965dc-118">Specify a user name for the database connection.</span></span>  
  
 <span data-ttu-id="965dc-119">Questo nome utente viene utilizzato quando si crea la stringa di connessione per l'origine dati.</span><span class="sxs-lookup"><span data-stu-id="965dc-119">This user name is used when constructing the connection string for the data source.</span></span> <span data-ttu-id="965dc-120">Queste credenziali vengono utilizzate anche in caso di visualizzazione in anteprima e filtro dei dati nella finestra Proprietà tabella e nell'Importazione guidata.</span><span class="sxs-lookup"><span data-stu-id="965dc-120">These credentials are also used when previewing and filtering data in the Table Properties window and in the Import Wizard.</span></span> <span data-ttu-id="965dc-121">Non vengono utilizzate per importare o aggiornare dati; in tal caso vengono infatti utilizzate le credenziali di Windows specificate nella pagina Impostazioni di rappresentazione.</span><span class="sxs-lookup"><span data-stu-id="965dc-121">These credentials are not used to import or refresh data; the Windows credentials specified on the Impersonation Information page are used instead.</span></span>  
  
 <span data-ttu-id="965dc-122">**Password**</span><span class="sxs-lookup"><span data-stu-id="965dc-122">**Password**</span></span>  
 <span data-ttu-id="965dc-123">Specificare una password per la connessione al database.</span><span class="sxs-lookup"><span data-stu-id="965dc-123">Specify a password for the database connection.</span></span>  
  
 <span data-ttu-id="965dc-124">**Salva password**</span><span class="sxs-lookup"><span data-stu-id="965dc-124">**Save my password**</span></span>  
 <span data-ttu-id="965dc-125">Specificare se la password immessa nella casella **Password** è stata archiviata.</span><span class="sxs-lookup"><span data-stu-id="965dc-125">Specify whether the password you have entered in the **Password** box is stored.</span></span>  
  
 <span data-ttu-id="965dc-126">**Nome database**</span><span class="sxs-lookup"><span data-stu-id="965dc-126">**Database name**</span></span>  
 <span data-ttu-id="965dc-127">Selezionare un database dall'elenco di database.</span><span class="sxs-lookup"><span data-stu-id="965dc-127">Select a database from the list of databases.</span></span>  
  
 <span data-ttu-id="965dc-128">**Funzionalità avanzate**</span><span class="sxs-lookup"><span data-stu-id="965dc-128">**Advanced**</span></span>  
 <span data-ttu-id="965dc-129">Per impostare ulteriori proprietà della connessione, utilizzare la finestra di dialogo **Imposta proprietà avanzate** .</span><span class="sxs-lookup"><span data-stu-id="965dc-129">Set additional connection properties by using the **Set Advanced Properties** dialog box.</span></span> <span data-ttu-id="965dc-130">Per altre informazioni, vedere [Impostazione delle proprietà avanzate &#40;SSAS&#41;](set-advanced-properties-ssas.md).</span><span class="sxs-lookup"><span data-stu-id="965dc-130">For more information, see [Set Advanced Properties &#40;SSAS&#41;](set-advanced-properties-ssas.md).</span></span>  
  
 <span data-ttu-id="965dc-131">**Test connessione**</span><span class="sxs-lookup"><span data-stu-id="965dc-131">**Test Connection**</span></span>  
 <span data-ttu-id="965dc-132">Provare a stabilire una connessione all'origine dati utilizzando le impostazioni correnti.</span><span class="sxs-lookup"><span data-stu-id="965dc-132">Attempt to establish a connection to the data source using the current settings.</span></span> <span data-ttu-id="965dc-133">Viene visualizzato un messaggio che indica se la connessione è stata stabilita.</span><span class="sxs-lookup"><span data-stu-id="965dc-133">A message displays and indicates whether the connection is successful.</span></span>  
  
  
