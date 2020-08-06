---
title: Utilità di avvio del daemon filtri full-text di SQL (scheda Servizio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: 6aad7ebe-c4be-4d37-8536-61502f51faa2
author: stevestein
ms.author: sstein
ms.openlocfilehash: 8f0d9c76d7d92947dd17fe2ed6e912e3d6baa6bd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636972"
---
# <a name="sql-full-text-filter-daemon-launcher-service-tab"></a><span data-ttu-id="79a00-102">Utilità di avvio del daemon filtri full-text di SQL (scheda Servizio)</span><span class="sxs-lookup"><span data-stu-id="79a00-102">SQL Full-text Filter Daemon Launcher (Service Tab)</span></span>
  <span data-ttu-id="79a00-103">A partire da [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], il servizio Utilità di avvio del daemon filtri full-text di SQL (FDHOST Launcher) viene utilizzato dalla ricerca full-text in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="79a00-103">Beginning in [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], the SQL Full-text Filter Daemon Launcher (FDHOST Launcher) service is used by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] full-text.</span></span> <span data-ttu-id="79a00-104">Se si utilizza la ricerca full-text, questo servizio deve essere in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="79a00-104">This service must be running if you use full-text search.</span></span> <span data-ttu-id="79a00-105">Per informazioni sui processi host del daemon di filtri, vedere "Architettura della ricerca full-text" nella documentazione online di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="79a00-105">For information about the filter daemon host processes, see "Full-Text Search Architecture" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
 <span data-ttu-id="79a00-106">Usare la scheda **Servizio**della finestra di dialogo **Proprietà - Utilità di avvio del daemon filtri full-text di SQL** per visualizzare o specificare le opzioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="79a00-106">Use the **Service**tab on the **SQL Full-text Filter Daemon LauncherProperties** dialog box to view or specify the following options.</span></span>  
  
## <a name="options"></a><span data-ttu-id="79a00-107">Opzioni</span><span class="sxs-lookup"><span data-stu-id="79a00-107">Options</span></span>  
 <span data-ttu-id="79a00-108">**Percorso binario**</span><span class="sxs-lookup"><span data-stu-id="79a00-108">**Binary Path**</span></span>  
 <span data-ttu-id="79a00-109">Elenca il percorso dei file di programma utilizzati dal servizio.</span><span class="sxs-lookup"><span data-stu-id="79a00-109">Lists the location of the program files used by this service.</span></span>  
  
 <span data-ttu-id="79a00-110">**Controllo errori**</span><span class="sxs-lookup"><span data-stu-id="79a00-110">**Error Control**</span></span>  
 <span data-ttu-id="79a00-111">1 indica `SERVICE_ERROR_NORMAL`.</span><span class="sxs-lookup"><span data-stu-id="79a00-111">1 indicates `SERVICE_ERROR_NORMAL`.</span></span> <span data-ttu-id="79a00-112">In caso di problemi di avvio del servizio durante l'avvio del computer, il programma di avvio registra l'errore e visualizza una finestra di messaggio popup ma continua l'operazione di avvio.</span><span class="sxs-lookup"><span data-stu-id="79a00-112">If the service fails to start during computer start up, the startup program logs the error and displays a pop-up message box but continues the startup operation.</span></span> <span data-ttu-id="79a00-113">Questo valore non può essere modificato.</span><span class="sxs-lookup"><span data-stu-id="79a00-113">This value cannot be changed.</span></span>  
  
 <span data-ttu-id="79a00-114">**Codice di uscita**</span><span class="sxs-lookup"><span data-stu-id="79a00-114">**Exit Code**</span></span>  
 <span data-ttu-id="79a00-115">Quando si verifica un errore, il numero dell'errore viene visualizzato in questa casella.</span><span class="sxs-lookup"><span data-stu-id="79a00-115">When an error occurs, the error number appears in this box.</span></span> <span data-ttu-id="79a00-116">Questo numero può risultare utile per la risoluzione dei problemi. È possibile cercarlo nella [!INCLUDE[msCoName](../../includes/msconame-md.md)] Knowledge Base oppure comunicarlo al personale del supporto tecnico.</span><span class="sxs-lookup"><span data-stu-id="79a00-116">Use this number to troubleshoot failures by searching for the number in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Knowledge Base or provide the number to your technical support staff.</span></span>  
  
 <span data-ttu-id="79a00-117">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="79a00-117">**Host Name**</span></span>  
 <span data-ttu-id="79a00-118">Visualizza il nome del computer o del cluster che esegue il servizio [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="79a00-118">Displays the name of the computer or cluster running the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service.</span></span>  
  
 <span data-ttu-id="79a00-119">**Nome**</span><span class="sxs-lookup"><span data-stu-id="79a00-119">**Name**</span></span>  
 <span data-ttu-id="79a00-120">Indica il nome visualizzato del servizio.</span><span class="sxs-lookup"><span data-stu-id="79a00-120">Indicates the display name of the service.</span></span>  
  
 <span data-ttu-id="79a00-121">**ID processo**</span><span class="sxs-lookup"><span data-stu-id="79a00-121">**Process ID**</span></span>  
 <span data-ttu-id="79a00-122">Visualizza l'ID di processo di Windows.</span><span class="sxs-lookup"><span data-stu-id="79a00-122">Displays the Windows process ID.</span></span>  
  
 <span data-ttu-id="79a00-123">**Tipo di servizio SQL Server**</span><span class="sxs-lookup"><span data-stu-id="79a00-123">**SQL Service Type**</span></span>  
 <span data-ttu-id="79a00-124">Visualizza il tipo di servizio fornito ai processi chiamanti.</span><span class="sxs-lookup"><span data-stu-id="79a00-124">Displays the type of service provided to calling processes.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="79a00-125">vengono installati diversi servizi.</span><span class="sxs-lookup"><span data-stu-id="79a00-125">installs several services.</span></span>  
  
 <span data-ttu-id="79a00-126">**Modalità di avvio**</span><span class="sxs-lookup"><span data-stu-id="79a00-126">**Start Mode**</span></span>  
 <span data-ttu-id="79a00-127">Impostare una delle opzioni seguenti per il servizio:</span><span class="sxs-lookup"><span data-stu-id="79a00-127">Set this service to the following choices:</span></span>  
  
-   <span data-ttu-id="79a00-128">Manuale: il servizio non viene avviato automaticamente all'avvio del computer.</span><span class="sxs-lookup"><span data-stu-id="79a00-128">Manual: This service does not automatically start when the computer starts.</span></span> <span data-ttu-id="79a00-129">In questo caso è necessario avviare il servizio tramite Gestione configurazione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o un altro strumento.</span><span class="sxs-lookup"><span data-stu-id="79a00-129">You must start the service using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, or some other tool.</span></span>  
  
-   <span data-ttu-id="79a00-130">Automatico: viene eseguito un tentativo automatico di avvio del servizio all'avvio del computer.</span><span class="sxs-lookup"><span data-stu-id="79a00-130">Automatic: This service attempts to start when this computer starts.</span></span>  
  
-   <span data-ttu-id="79a00-131">Disabilitato: il servizio non può essere avviato.</span><span class="sxs-lookup"><span data-stu-id="79a00-131">Disabled: This service cannot be started.</span></span>  
  
 <span data-ttu-id="79a00-132">**State**</span><span class="sxs-lookup"><span data-stu-id="79a00-132">**State**</span></span>  
 <span data-ttu-id="79a00-133">Indica se il servizio è in esecuzione, arrestato o disabilitato.</span><span class="sxs-lookup"><span data-stu-id="79a00-133">Indicates whether this service is running, stopped, or disabled.</span></span> <span data-ttu-id="79a00-134">" **...** " indica una modifica di stato in sospeso.</span><span class="sxs-lookup"><span data-stu-id="79a00-134">"**...**" indicates a state change is pending.</span></span>  
  
  
