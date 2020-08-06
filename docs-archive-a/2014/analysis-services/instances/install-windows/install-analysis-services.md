---
title: Installare Analysis Services in modalità tabulare | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: cd6ac80d-b735-4e3e-a024-489f1409ad33
author: minewiskan
ms.author: owend
ms.openlocfilehash: a677fd7770f646067cafb8fedf6d3705ccf2de3c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713604"
---
# <a name="install-analysis-services-in-tabular-mode"></a><span data-ttu-id="be02d-102">Installare Analysis Services in modalità Tabella</span><span class="sxs-lookup"><span data-stu-id="be02d-102">Install Analysis Services in Tabular Mode</span></span>
  <span data-ttu-id="be02d-103">Se si sta installando Analysis Services per utilizzare le nuove funzionalità di modelli tabulari, è necessario installarlo in una modalità server che supporti tale tipo di modello.</span><span class="sxs-lookup"><span data-stu-id="be02d-103">If you are installing Analysis Services to use the new tabular modeling features, you must install Analysis Services in a server mode that supports that type of model.</span></span> <span data-ttu-id="be02d-104">La modalità server è Tabella ed è configurata durante l'installazione.</span><span class="sxs-lookup"><span data-stu-id="be02d-104">The server mode is Tabular, and it is configured during installation.</span></span>  
  
 <span data-ttu-id="be02d-105">Dopo aver installato il server in questa modalità, è possibile utilizzare le soluzioni host compilate nella progettazione di modelli tabulari.</span><span class="sxs-lookup"><span data-stu-id="be02d-105">After you install the server in this mode, you can use it host solutions that you build in tabular model designer.</span></span> <span data-ttu-id="be02d-106">Un server in modalità tabulare è necessario se si desidera l'accesso ai dati dei modelli tabulari sulla rete.</span><span class="sxs-lookup"><span data-stu-id="be02d-106">A tabular mode server is required if you want tabular model data access over the network.</span></span>  
  
 <span data-ttu-id="be02d-107">È possibile specificare la modalità Tabella nell'installazione guidata o in un'installazione dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="be02d-107">You can specify Tabular mode in the Installation Wizard or in a command line setup.</span></span> <span data-ttu-id="be02d-108">Nelle sezioni seguenti vengono descritte le diverse modalità.</span><span class="sxs-lookup"><span data-stu-id="be02d-108">The following sections describe each approach.</span></span>  
  
## <a name="installation-wizard"></a><span data-ttu-id="be02d-109">Installazione guidata</span><span class="sxs-lookup"><span data-stu-id="be02d-109">Installation Wizard</span></span>  
 <span data-ttu-id="be02d-110">Nel seguente elenco sono riportate le pagine dell'installazione guidata di SQL Server che vengono utilizzate per installar Analysis Services in modalità Tabella.</span><span class="sxs-lookup"><span data-stu-id="be02d-110">The following list shows you which pages in the SQL Server Installation wizard are used to install Analysis Services in Tabular mode:</span></span>  
  
1.  <span data-ttu-id="be02d-111">Selezionare **Analysis Services** dall'albero delle funzionalità nell'installazione.</span><span class="sxs-lookup"><span data-stu-id="be02d-111">Select **Analysis Services** from the Feature Tree in Setup.</span></span>  
  
     <span data-ttu-id="be02d-112">![Albero delle funzionalità del programma di installazione in cui viene mostrato Analsyis Services](../../../sql-server/install/media/ssas-setupas.gif "Albero delle funzionalità del programma di installazione in cui viene mostrato Analsyis Services")</span><span class="sxs-lookup"><span data-stu-id="be02d-112">![Setup feature tree showing Analsyis Services](../../../sql-server/install/media/ssas-setupas.gif "Setup feature tree showing Analsyis Services")</span></span>  
  
2.  <span data-ttu-id="be02d-113">Nella pagina configurazione Analysis Services assicurarsi di selezionare la **modalità tabulare**.</span><span class="sxs-lookup"><span data-stu-id="be02d-113">On the Analysis Services Configuration page, be sure to select **Tabular Mode**.</span></span>  
  
     <span data-ttu-id="be02d-114">![Pagina di installazione con le opzioni di configurazione di Analysis Services](../../../sql-server/install/media/ssas-setupasconfig.gif "Pagina di installazione con le opzioni di configurazione di Analysis Services")</span><span class="sxs-lookup"><span data-stu-id="be02d-114">![Setup page with Analysis Services config options](../../../sql-server/install/media/ssas-setupasconfig.gif "Setup page with Analysis Services config options")</span></span>  
  
 <span data-ttu-id="be02d-115">Tramite questa modalità viene utilizzato il motore di analisi in memoria xVelocity (VertiPaq) che costituisce l'archivio predefinito per i modelli tabulari distribuiti in Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="be02d-115">Tabular mode uses the xVelocity in-memory analytics engine (VertiPaq), which is the default storage for tabular models that you deploy to Analysis Services.</span></span> <span data-ttu-id="be02d-116">Una volta distribuite le soluzioni del modello tabulare nel server, è possibile configurare selettivamente le soluzioni tabulari per utilizzare l'archivio su disco DirectQuery in alternativa allo spazio di archiviazione associato alla memoria.</span><span class="sxs-lookup"><span data-stu-id="be02d-116">After you deploy tabular model solutions to the server, you can selectively configure tabular solutions to use DirectQuery disk storage as an alternative to memory-bound storage.</span></span>  
  
## <a name="command-line-setup"></a><span data-ttu-id="be02d-117">Installazione dalla riga di comando</span><span class="sxs-lookup"><span data-stu-id="be02d-117">Command Line Setup</span></span>  
 <span data-ttu-id="be02d-118">Nell'installazione di SQL Server è incluso un nuovo parametro (`ASSERVERMODE`) mediante il quale viene specificata la modalità server.</span><span class="sxs-lookup"><span data-stu-id="be02d-118">SQL Server Setup includes a new parameter (`ASSERVERMODE`) that specifies the server mode.</span></span> <span data-ttu-id="be02d-119">Nell'esempio seguente viene illustrata un'istallazione dalla riga di comando che installa Analysis Services nella modalità server Tabella.</span><span class="sxs-lookup"><span data-stu-id="be02d-119">The following example illustrates a command line setup that installs Analysis Services in Tabular server mode.</span></span>  
  
```  
  
Setup.exe /q /IAcceptSQLServerLicenseTerms /ACTION=install /FEATURES=AS /ASSERVERMODE=TABULAR /INSTANCENAME=ASTabular /INDICATEPROGRESS/ASSVCACCOUNT=<DomainName\UserName> /ASSVCPASSWORD=<StrongPassword> /ASSYSADMINACCOUNTS=<DomainName\UserName>   
```  
  
 <span data-ttu-id="be02d-120">`INSTANCENAME` deve contenere meno di 17 caratteri.</span><span class="sxs-lookup"><span data-stu-id="be02d-120">`INSTANCENAME` must be less than 17 characters.</span></span>  
  
 <span data-ttu-id="be02d-121">Tutti i valori segnaposto degli account devono essere sostituiti con password e account validi.</span><span class="sxs-lookup"><span data-stu-id="be02d-121">All placeholder account values must be replaced with valid accounts and password.</span></span>  
  
 <span data-ttu-id="be02d-122">Strumenti come SQL Server Management Studio o [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)] non vengono installati utilizzando la sintassi della riga di comando di esempio fornita.</span><span class="sxs-lookup"><span data-stu-id="be02d-122">Tools such as SQL Server Management Studio or [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)] are not installed using the example command line syntax that is provided.</span></span> <span data-ttu-id="be02d-123">Per ulteriori informazioni sull'aggiunta di funzionalità, vedere [Install SQL Server 2014 dal prompt dei comandi](../../../database-engine/install-windows/install-sql-server-from-the-command-prompt.md).</span><span class="sxs-lookup"><span data-stu-id="be02d-123">For more information about adding features, see [Install SQL Server 2014 from the Command Prompt](../../../database-engine/install-windows/install-sql-server-from-the-command-prompt.md).</span></span>  
  
 <span data-ttu-id="be02d-124">`ASSERVERMODE` supporta la distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="be02d-124">`ASSERVERMODE` is case-sensitive.</span></span>  <span data-ttu-id="be02d-125">È necessario esprimere tutti i valori in lettere maiuscole.</span><span class="sxs-lookup"><span data-stu-id="be02d-125">All values must be expressed in upper case.</span></span> <span data-ttu-id="be02d-126">Nella tabella seguente vengono descritti i valori validi per `ASSERVERMODE`.</span><span class="sxs-lookup"><span data-stu-id="be02d-126">The following table describes the valid values for `ASSERVERMODE`.</span></span>  
  
|<span data-ttu-id="be02d-127">Valore</span><span class="sxs-lookup"><span data-stu-id="be02d-127">Value</span></span>|<span data-ttu-id="be02d-128">Descrizione</span><span class="sxs-lookup"><span data-stu-id="be02d-128">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="be02d-129">MULTIDIMENSIONAL</span><span class="sxs-lookup"><span data-stu-id="be02d-129">MULTIDIMENSIONAL</span></span>|<span data-ttu-id="be02d-130">Rappresenta il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="be02d-130">This is the default value.</span></span> <span data-ttu-id="be02d-131">Se `ASSERVERMODE` non viene impostato, il server viene installato nella modalità server Multidimensionale.</span><span class="sxs-lookup"><span data-stu-id="be02d-131">If you do not set `ASSERVERMODE`, the server is installed in Multidimensional server mode.</span></span>|  
|<span data-ttu-id="be02d-132">POWERPIVOT</span><span class="sxs-lookup"><span data-stu-id="be02d-132">POWERPIVOT</span></span>|<span data-ttu-id="be02d-133">Questo valore è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="be02d-133">This value is optional.</span></span> <span data-ttu-id="be02d-134">In pratica, se si imposta il parametro `ROLE`, la modalità del server è automaticamente impostata su 1, rendendo `ASSERVERMODE` facoltativo per un'installazione di PowerPivot per SharePoint.</span><span class="sxs-lookup"><span data-stu-id="be02d-134">In practice, if you set the `ROLE` parameter, the server mode is automatically set to 1, making `ASSERVERMODE` optional for a PowerPivot for SharePoint installation.</span></span> <span data-ttu-id="be02d-135">Per ulteriori informazioni, vedere [installare PowerPivot dal prompt dei comandi](../../../sql-server/install/install-powerpivot-from-the-command-prompt.md).</span><span class="sxs-lookup"><span data-stu-id="be02d-135">For more information, see [Install PowerPivot from the Command Prompt](../../../sql-server/install/install-powerpivot-from-the-command-prompt.md).</span></span>|  
|<span data-ttu-id="be02d-136">TABULAR</span><span class="sxs-lookup"><span data-stu-id="be02d-136">TABULAR</span></span>|<span data-ttu-id="be02d-137">Questo valore è obbligatorio se si installa Analysis Services nella modalità Tabella tramite l'installazione dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="be02d-137">This value is required if you are installing Analysis Services in Tabular mode using command line setup.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="be02d-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="be02d-138">See Also</span></span>  
 <span data-ttu-id="be02d-139">[Determinare la modalità server di un'istanza di Analysis Services](../determine-the-server-mode-of-an-analysis-services-instance.md) </span><span class="sxs-lookup"><span data-stu-id="be02d-139">[Determine the Server Mode of an Analysis Services Instance](../determine-the-server-mode-of-an-analysis-services-instance.md) </span></span>  
 <span data-ttu-id="be02d-140">[Configurare l'accesso in memoria o DirectQuery per un database modello tabulare](../../tabular-models/enable-directquery-mode-in-ssms.md) </span><span class="sxs-lookup"><span data-stu-id="be02d-140">[Configure In-Memory or DirectQuery Access for a Tabular Model Database](../../tabular-models/enable-directquery-mode-in-ssms.md) </span></span>  
 [<span data-ttu-id="be02d-141">Modellazione tabulare &#40;SSAS tabulare&#41;</span><span class="sxs-lookup"><span data-stu-id="be02d-141">Tabular Modeling &#40;SSAS Tabular&#41;</span></span>](../../tabular-models/tabular-models-ssas.md)  
  
  
