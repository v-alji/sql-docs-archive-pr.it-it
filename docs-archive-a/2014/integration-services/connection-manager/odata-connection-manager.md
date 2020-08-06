---
title: Gestione connessione OData | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 3caa4372-aff3-4c0f-9ecd-97870948b8d0
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 46eedaa008b284661fd1d364d2e2bc87c373a9f8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629972"
---
# <a name="odata-connection-manager"></a><span data-ttu-id="6c78e-102">Gestione connessione OData</span><span class="sxs-lookup"><span data-stu-id="6c78e-102">OData Connection Manager</span></span>
  <span data-ttu-id="6c78e-103">Con la gestione connessione OData è possibile connettere un pacchetto a un'origine OData.</span><span class="sxs-lookup"><span data-stu-id="6c78e-103">An OData connection manager enables a package to connect to an OData source.</span></span> <span data-ttu-id="6c78e-104">Tramite un componente di origine OData viene eseguita la connessione a un'origine OData mediante una gestione connessione OData e vengono utilizzati i dati del servizio.</span><span class="sxs-lookup"><span data-stu-id="6c78e-104">An OData Source component connects to an OData source using an OData connection manager and consumes data from the service.</span></span> <span data-ttu-id="6c78e-105">Vedere la sezione [origine OData](../data-flow/odata-source.md)per informazioni dettagliate, incluse le istruzioni di installazione per questi componenti.</span><span class="sxs-lookup"><span data-stu-id="6c78e-105">See [OData Source](../data-flow/odata-source.md)section for detailed information including the installation instructions for these components.</span></span>  
  
## <a name="adding-connection-manager-to-an-ssis-package"></a><span data-ttu-id="6c78e-106">Aggiunta di gestione connessione a un pacchetto SSIS</span><span class="sxs-lookup"><span data-stu-id="6c78e-106">Adding Connection Manager to an SSIS Package</span></span>  
 <span data-ttu-id="6c78e-107">È possibile aggiungere una nuova gestione connessione OData a un pacchetto SSIS nelle tre modalità seguenti:</span><span class="sxs-lookup"><span data-stu-id="6c78e-107">You can add a new OData Connection Manager to an SSIS package in three ways:</span></span>  
  
-   <span data-ttu-id="6c78e-108">Fare clic sul pulsante **Nuovo...** in **Editor origine OData**</span><span class="sxs-lookup"><span data-stu-id="6c78e-108">Click the **New...** button in the **OData Source Editor**</span></span>  
  
-   <span data-ttu-id="6c78e-109">Fare clic con il pulsante destro del mouse sulla cartella **gestioni connessioni** nel **Esplora soluzioni** e scegliere **nuova gestione connessione**.</span><span class="sxs-lookup"><span data-stu-id="6c78e-109">Right-click **Connection Managers** folder in the **Solution Explorer** and click **New Connection Manager**.</span></span> <span data-ttu-id="6c78e-110">Selezionare **ODATA** per **Tipo gestione connessione**.</span><span class="sxs-lookup"><span data-stu-id="6c78e-110">Select **ODATA** for **Connection manager type**.</span></span>  
  
-   <span data-ttu-id="6c78e-111">Fare clic con il pulsante destro del mouse nel riquadro **gestioni connessioni** nella parte inferiore della finestra di progettazione del pacchetto e selezionare **nuova connessione.** Selezionare **OData** per **tipo gestione connessione**.</span><span class="sxs-lookup"><span data-stu-id="6c78e-111">Right-click in the **Connection Managers** pane at the bottom of the package designer, and select **New Connection...**. Select **ODATA** for **Connection manager type**.</span></span>  
  
## <a name="connection-manager-authentication"></a><span data-ttu-id="6c78e-112">Autenticazione di gestione connessione</span><span class="sxs-lookup"><span data-stu-id="6c78e-112">Connection Manager Authentication</span></span>  
 <span data-ttu-id="6c78e-113">La gestione connessione OData supporta due modalità di autenticazione.</span><span class="sxs-lookup"><span data-stu-id="6c78e-113">The OData Connection Manager supports two modes of authentication.</span></span>  
  
-   <span data-ttu-id="6c78e-114">Autenticazione di Windows</span><span class="sxs-lookup"><span data-stu-id="6c78e-114">Windows Authentication</span></span>  
  
-   <span data-ttu-id="6c78e-115">Autenticazione di base (nome utente/password)</span><span class="sxs-lookup"><span data-stu-id="6c78e-115">Basic Authentication (username/password)</span></span>  
  
 <span data-ttu-id="6c78e-116">Per l'accesso anonimo, selezionare l'opzione Autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="6c78e-116">For anonymous access, select the Windows Authentication option</span></span>  
  
### <a name="specifying-and-securing-credentials"></a><span data-ttu-id="6c78e-117">Specifica e protezione delle credenziali</span><span class="sxs-lookup"><span data-stu-id="6c78e-117">Specifying and Securing Credentials</span></span>  
 <span data-ttu-id="6c78e-118">Se il servizio OData richiede l'autenticazione di base, è possibile specificare un nome utente e una password nell' [Editor gestione connessione OData](../odata-connection-manager-editor.md).</span><span class="sxs-lookup"><span data-stu-id="6c78e-118">If your OData service requires basic authentication, you can specify a username and password in the [OData Connection Manager Editor](../odata-connection-manager-editor.md).</span></span> <span data-ttu-id="6c78e-119">I valori immessi nell'editor sono persistenti nel pacchetto.</span><span class="sxs-lookup"><span data-stu-id="6c78e-119">The values you enter in the editor are persisted in the package.</span></span> <span data-ttu-id="6c78e-120">Il valore della password è crittografato in base al livello di protezione del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="6c78e-120">The password value is encrypted according to the package protection level.</span></span>  
  
 <span data-ttu-id="6c78e-121">È possibile esternalizzare/impostare i parametri dei valori del nome utente e della password in più modalità.</span><span class="sxs-lookup"><span data-stu-id="6c78e-121">There are multiple ways to externalize/parameterize the username and password values.</span></span> <span data-ttu-id="6c78e-122">Le due modalità principali per eseguire questa operazione in [!INCLUDE[ssISversion11](../../includes/ssisversion11-md.md)] consistono nell'utilizzo dei parametri oppure nell'impostare le proprietà di gestione connessione direttamente quando si esegue il pacchetto mediante SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="6c78e-122">The two primary ways of doing this in [!INCLUDE[ssISversion11](../../includes/ssisversion11-md.md)] are by using parameters, or by setting the connection manager properties directly when you run the package using SQL Server Management Studio.</span></span>  
  
## <a name="odata-connection-manager-properties"></a><span data-ttu-id="6c78e-123">Proprietà di gestione connessione OData</span><span class="sxs-lookup"><span data-stu-id="6c78e-123">OData Connection Manager Properties</span></span>  
 <span data-ttu-id="6c78e-124">Nell'elenco seguente vengono descritte alcune delle proprietà di gestione connessione OData che è possibile modificare.</span><span class="sxs-lookup"><span data-stu-id="6c78e-124">The following list describes some of the OData Connection Manager properties that you may want to change.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6c78e-125">Proprietà</span><span class="sxs-lookup"><span data-stu-id="6c78e-125">Property</span></span>|<span data-ttu-id="6c78e-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6c78e-126">Description</span></span>|  
|<span data-ttu-id="6c78e-127">URL</span><span class="sxs-lookup"><span data-stu-id="6c78e-127">Url</span></span>|<span data-ttu-id="6c78e-128">URL del documento di servizio.</span><span class="sxs-lookup"><span data-stu-id="6c78e-128">URL to the service document.</span></span>|  
|<span data-ttu-id="6c78e-129">UserName</span><span class="sxs-lookup"><span data-stu-id="6c78e-129">UserName</span></span>|<span data-ttu-id="6c78e-130">Nome utente da utilizzare per l'autenticazione di base.</span><span class="sxs-lookup"><span data-stu-id="6c78e-130">Username to use for Basic Authentication.</span></span>|  
|<span data-ttu-id="6c78e-131">Password</span><span class="sxs-lookup"><span data-stu-id="6c78e-131">Password</span></span>|<span data-ttu-id="6c78e-132">Password da utilizzare per l'autenticazione di base.</span><span class="sxs-lookup"><span data-stu-id="6c78e-132">Password to use for Basic Authentication.</span></span>|  
|<span data-ttu-id="6c78e-133">ConnectionString</span><span class="sxs-lookup"><span data-stu-id="6c78e-133">ConnectionString</span></span>|<span data-ttu-id="6c78e-134">Riflette altre proprietà della gestione connessione.</span><span class="sxs-lookup"><span data-stu-id="6c78e-134">Reflects other properties of the connection manager.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6c78e-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6c78e-135">See Also</span></span>  
 [<span data-ttu-id="6c78e-136">Editor gestione connessione OData</span><span class="sxs-lookup"><span data-stu-id="6c78e-136">OData Connection Manager Editor</span></span>](../odata-connection-manager-editor.md)  
  
  
