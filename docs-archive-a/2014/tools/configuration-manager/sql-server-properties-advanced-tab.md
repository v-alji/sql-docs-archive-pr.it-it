---
title: Proprietà - SQL Server (scheda Avanzate) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: 2ffd10fd-bac1-478f-9cff-96ed6c8b787f
author: stevestein
ms.author: sstein
ms.openlocfilehash: a9a77fd0a43627b49bb8719f6fa943408f64fcca
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623689"
---
# <a name="sql-server-properties-advanced-tab"></a><span data-ttu-id="158c8-102">Proprietà - SQL Server (scheda Avanzate)</span><span class="sxs-lookup"><span data-stu-id="158c8-102">SQL Server Properties (Advanced Tab)</span></span>
  <span data-ttu-id="158c8-103">Le proprietà descritte di seguito sono presenti nella scheda **Avanzate** per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="158c8-103">The following properties appear on the **Advanced** tab by default.</span></span> <span data-ttu-id="158c8-104">Se sono state definite proprietà personalizzate, verranno visualizzate anche in questa scheda con i rispettivi valori.</span><span class="sxs-lookup"><span data-stu-id="158c8-104">If custom properties are defined, they also appear on this tab, with their values.</span></span>  
  
## <a name="options"></a><span data-ttu-id="158c8-105">Opzioni</span><span class="sxs-lookup"><span data-stu-id="158c8-105">Options</span></span>  
 <span data-ttu-id="158c8-106">**Cluster**</span><span class="sxs-lookup"><span data-stu-id="158c8-106">**Clustered**</span></span>  
 <span data-ttu-id="158c8-107">Indica se il servizio è installato come risorsa di un server di cluster.</span><span class="sxs-lookup"><span data-stu-id="158c8-107">Indicates if this service is installed as a resource of a clustered server.</span></span>  
  
 <span data-ttu-id="158c8-108">**Segnalazione commenti e suggerimenti utenti**</span><span class="sxs-lookup"><span data-stu-id="158c8-108">**Customer Feedback Reporting**</span></span>  
 <span data-ttu-id="158c8-109">Indica se il monitoraggio della qualità del servizio è stato abilitato per il servizio.</span><span class="sxs-lookup"><span data-stu-id="158c8-109">Indicates whether Service Quality Monitoring has been enabled on this service.</span></span> <span data-ttu-id="158c8-110">Per ulteriori informazioni sulla funzionalità di segnalazione del feedback dei clienti, cercare l'argomento "Impostazioni segnalazione errori e utilizzo funzionalità" nella documentazione online.</span><span class="sxs-lookup"><span data-stu-id="158c8-110">For more information on Customer Feedback Reporting, search Books Online for the topic, "Error and Usage Report Settings."</span></span>  
  
 <span data-ttu-id="158c8-111">**Percorso dati**</span><span class="sxs-lookup"><span data-stu-id="158c8-111">**Data Path**</span></span>  
 <span data-ttu-id="158c8-112">Visualizza il percorso dei file binari di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] relativi all'installazione corrente di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="158c8-112">Displays the path to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] binaries for this installation of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="158c8-113">**Directory dump**</span><span class="sxs-lookup"><span data-stu-id="158c8-113">**Dump Directory**</span></span>  
 <span data-ttu-id="158c8-114">Indica la posizione in cui vengono memorizzati i dump di memoria in caso di errore.</span><span class="sxs-lookup"><span data-stu-id="158c8-114">Displays the location where memory dumps are placed in case of an error.</span></span>  
  
 <span data-ttu-id="158c8-115">**Segnalazione errori**</span><span class="sxs-lookup"><span data-stu-id="158c8-115">**Error Reporting**</span></span>  
 <span data-ttu-id="158c8-116">Se l'opzione è impostata su **Sì**, il programma Dr. Watson inoltra le informazioni a [!INCLUDE[msCoName](../../includes/msconame-md.md)] o al server interno per la segnalazione degli errori se si verifica un errore grave.</span><span class="sxs-lookup"><span data-stu-id="158c8-116">When set to **Yes**, the Dr. Watson program forwards information to either [!INCLUDE[msCoName](../../includes/msconame-md.md)] or your error server if a serious failure occurs.</span></span> <span data-ttu-id="158c8-117">Per ulteriori informazioni sulla funzionalità di segnalazione degli errori, cercare l'argomento "Impostazioni segnalazione errori e utilizzo funzionalità" nella documentazione online.</span><span class="sxs-lookup"><span data-stu-id="158c8-117">For more information on Error Reporting, search Books Online for the topic, "Error and Usage Report Settings."</span></span> <span data-ttu-id="158c8-118">Per modificare questo valore, in Esplora oggetti di [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] fare clic con il pulsante destro del mouse sul server, scegliere **Proprietà**e quindi fare clic sulla pagina **Impostazioni varie server** .</span><span class="sxs-lookup"><span data-stu-id="158c8-118">To change this value, in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Object Explorer, right-click your server, click **Properties**, and then click the **Misc. Server Settings** page.</span></span> <span data-ttu-id="158c8-119">Le opzioni verranno visualizzate nell'area **Segnalazione informazioni** .</span><span class="sxs-lookup"><span data-stu-id="158c8-119">The options are presented in the **Information Reporting** area.</span></span>  
  
 <span data-ttu-id="158c8-120">**Versione file**</span><span class="sxs-lookup"><span data-stu-id="158c8-120">**File Version**</span></span>  
 <span data-ttu-id="158c8-121">Visualizza la versione dell'eseguibile di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="158c8-121">Displays the version of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] executable.</span></span>  
  
 <span data-ttu-id="158c8-122">**Percorso installazione**</span><span class="sxs-lookup"><span data-stu-id="158c8-122">**Install Path**</span></span>  
 <span data-ttu-id="158c8-123">Visualizza il percorso dei file binari di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] relativi all'installazione corrente di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="158c8-123">Displays the path to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] binaries for this installation of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="158c8-124">**ID istanza**</span><span class="sxs-lookup"><span data-stu-id="158c8-124">**Instance ID**</span></span>  
 <span data-ttu-id="158c8-125">Indica l'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] che ha usato il servizio.</span><span class="sxs-lookup"><span data-stu-id="158c8-125">Indicates the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance that used this service.</span></span>  
  
 <span data-ttu-id="158c8-126">**Lingua**</span><span class="sxs-lookup"><span data-stu-id="158c8-126">**Language**</span></span>  
 <span data-ttu-id="158c8-127">Visualizza la lingua predefinita dei messaggi del server.</span><span class="sxs-lookup"><span data-stu-id="158c8-127">Displays the default language for server messages.</span></span>  
  
 <span data-ttu-id="158c8-128">**Radice Registro di sistema**</span><span class="sxs-lookup"><span data-stu-id="158c8-128">**Registry Root**</span></span>  
 <span data-ttu-id="158c8-129">Visualizza il percorso delle chiavi del Registro di sistema utilizzate dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="158c8-129">Displays the location of the registry keys used by this application.</span></span>  
  
 <span data-ttu-id="158c8-130">**Livello Service Pack**</span><span class="sxs-lookup"><span data-stu-id="158c8-130">**Service Pack Level**</span></span>  
 <span data-ttu-id="158c8-131">Visualizza il livello di Service Pack dell'istanza corrente di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="158c8-131">Displays the service pack level of this instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="158c8-132">**Nome SKU**</span><span class="sxs-lookup"><span data-stu-id="158c8-132">**SKU Name**</span></span>  
 <span data-ttu-id="158c8-133">Visualizza il codice di riferimento del prodotto (SKU), definito anche edizione del prodotto.</span><span class="sxs-lookup"><span data-stu-id="158c8-133">Displays the product stock keeping unit (SKU), sometimes called the product edition.</span></span>  
  
 <span data-ttu-id="158c8-134">**Parametri di avvio**</span><span class="sxs-lookup"><span data-stu-id="158c8-134">**Startup Parameters**</span></span>  
 <span data-ttu-id="158c8-135">Elenca i parametri di avvio utilizzati dall'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="158c8-135">Lists any startup parameters that are used by this instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="158c8-136">I parametri sono separati da punti e virgola.</span><span class="sxs-lookup"><span data-stu-id="158c8-136">Parameters are separated by semi-colons.</span></span> <span data-ttu-id="158c8-137">I parametri predefiniti includono i percorsi del file di dati del database master (`master.mdf`), del file di log del database master (`mastlog.ldf`) e del file di log degli errori.</span><span class="sxs-lookup"><span data-stu-id="158c8-137">The default parameters include the paths to the data file for the master database (`master.mdf`), the log file for the master database (`mastlog.ldf`), and the error log file.</span></span> <span data-ttu-id="158c8-138">Per informazioni sulla sintassi dei parametri di avvio, cercare l'argomento **Utilizzo delle opzioni di avvio del servizio SQL Server**nella documentazione online.</span><span class="sxs-lookup"><span data-stu-id="158c8-138">For the syntax of startup parameters, search Books Online for the topic **Using the SQL Server Service Startup Options.**</span></span>  
  
 <span data-ttu-id="158c8-139">**SKU**</span><span class="sxs-lookup"><span data-stu-id="158c8-139">**Stock Keeping Unit**</span></span>  
 <span data-ttu-id="158c8-140">Visualizza il numero del codice di riferimento del prodotto (SKU).</span><span class="sxs-lookup"><span data-stu-id="158c8-140">Displays the product stock keeping unit (SKU) number.</span></span>  
  
 <span data-ttu-id="158c8-141">**Version**</span><span class="sxs-lookup"><span data-stu-id="158c8-141">**Version**</span></span>  
 <span data-ttu-id="158c8-142">Visualizza il numero di versione dell'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="158c8-142">Displays the version number of this instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="158c8-143">**Nome server virtuale**</span><span class="sxs-lookup"><span data-stu-id="158c8-143">**Virtual Server Name**</span></span>  
 <span data-ttu-id="158c8-144">**Nome server virtuale** quando [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] è installato in un server di cluster.</span><span class="sxs-lookup"><span data-stu-id="158c8-144">**Virtual Server Name** when [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is installed on a clustered server.</span></span>  
  
  
