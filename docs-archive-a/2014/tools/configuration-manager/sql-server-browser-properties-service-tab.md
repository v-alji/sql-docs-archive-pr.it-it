---
title: Proprietà - SQL Server Browser (scheda Servizio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: 98ace9b0-72d5-4b72-9b7b-11fbc490981a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 200e45648b94e26c5e808e9a817cfe01866e6a65
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624501"
---
# <a name="sql-server-browser-properties-service-tab"></a><span data-ttu-id="474f4-102">Proprietà - SQL Server Browser (scheda Servizio)</span><span class="sxs-lookup"><span data-stu-id="474f4-102">SQL Server Browser Properties (Service Tab)</span></span>
  <span data-ttu-id="474f4-103">Il programma [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser viene eseguito come servizio nel server.</span><span class="sxs-lookup"><span data-stu-id="474f4-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser program runs as a service on the server.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="474f4-104">Browser rimane in attesa delle richieste in entrata di risorse di [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e fornisce informazioni sulle istanze di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installate nel computer.</span><span class="sxs-lookup"><span data-stu-id="474f4-104">Browser listens for incoming requests for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] resources and provides information about [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instances installed on the computer.</span></span>  
  
 <span data-ttu-id="474f4-105">Utilizzare la scheda **Servizio** della finestra delle proprietà di **SQL Server Browser** per visualizzare le opzioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="474f4-105">Use the **Service** tab on the **SQL Server Browser Properties** dialog box to view the following options.</span></span> <span data-ttu-id="474f4-106">Tutte le proprietà sono in sola lettura, fatta eccezione per **Modalità di avvio** .</span><span class="sxs-lookup"><span data-stu-id="474f4-106">All properties except **Start Mode** are read-only.</span></span>  
  
## <a name="options"></a><span data-ttu-id="474f4-107">Opzioni</span><span class="sxs-lookup"><span data-stu-id="474f4-107">Options</span></span>  
 <span data-ttu-id="474f4-108">**Percorso binario**</span><span class="sxs-lookup"><span data-stu-id="474f4-108">**Binary Path**</span></span>  
 <span data-ttu-id="474f4-109">Visualizza il percorso dei file di programma utilizzati dal servizio.</span><span class="sxs-lookup"><span data-stu-id="474f4-109">Displays the location of the program files used by this service.</span></span>  
  
 <span data-ttu-id="474f4-110">**Controllo errori**</span><span class="sxs-lookup"><span data-stu-id="474f4-110">**Error Control**</span></span>  
 <span data-ttu-id="474f4-111">1 indica `SERVICE_ERROR_NORMAL`.</span><span class="sxs-lookup"><span data-stu-id="474f4-111">1 indicates `SERVICE_ERROR_NORMAL`.</span></span> <span data-ttu-id="474f4-112">In caso di problemi di avvio del servizio durante l'avvio del computer, il programma di avvio registra l'errore e visualizza una finestra di messaggio popup ma continua l'operazione di avvio.</span><span class="sxs-lookup"><span data-stu-id="474f4-112">If the service fails to start during computer start up, the startup program logs the error and displays a pop-up message box but continues the startup operation.</span></span> <span data-ttu-id="474f4-113">Questo valore non può essere modificato.</span><span class="sxs-lookup"><span data-stu-id="474f4-113">This value cannot be changed.</span></span>  
  
 <span data-ttu-id="474f4-114">**Codice di uscita**</span><span class="sxs-lookup"><span data-stu-id="474f4-114">**Exit Code**</span></span>  
 <span data-ttu-id="474f4-115">Quando si verifica un errore, il numero dell'errore viene visualizzato in questa casella.</span><span class="sxs-lookup"><span data-stu-id="474f4-115">When an error occurs, the error number appears in this box.</span></span> <span data-ttu-id="474f4-116">Questo numero può risultare utile per la risoluzione dei problemi. È possibile cercarlo nella [!INCLUDE[msCoName](../../includes/msconame-md.md)] Knowledge Base oppure comunicarlo al personale del supporto tecnico.</span><span class="sxs-lookup"><span data-stu-id="474f4-116">Use this number to troubleshoot failures by searching for the number in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Knowledge Base or provide the number to your technical support staff.</span></span>  
  
 <span data-ttu-id="474f4-117">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="474f4-117">**Host Name**</span></span>  
 <span data-ttu-id="474f4-118">Visualizza il nome del computer o del cluster che esegue il servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser.</span><span class="sxs-lookup"><span data-stu-id="474f4-118">Displays the name of the computer or cluster running the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service.</span></span>  
  
 <span data-ttu-id="474f4-119">**Nome**</span><span class="sxs-lookup"><span data-stu-id="474f4-119">**Name**</span></span>  
 <span data-ttu-id="474f4-120">Indica il nome visualizzato del servizio.</span><span class="sxs-lookup"><span data-stu-id="474f4-120">Indicates the display name of the service.</span></span>  
  
 <span data-ttu-id="474f4-121">**ID processo**</span><span class="sxs-lookup"><span data-stu-id="474f4-121">**Process ID**</span></span>  
 <span data-ttu-id="474f4-122">Visualizza l'ID di processo di Windows.</span><span class="sxs-lookup"><span data-stu-id="474f4-122">Displays the Windows process ID.</span></span>  
  
 <span data-ttu-id="474f4-123">**Tipo di servizio**</span><span class="sxs-lookup"><span data-stu-id="474f4-123">**Service Type**</span></span>  
 <span data-ttu-id="474f4-124">Visualizza il tipo di servizio fornito ai processi chiamanti.</span><span class="sxs-lookup"><span data-stu-id="474f4-124">Displays the type of service provided to calling processes.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="474f4-125">vengono installati diversi servizi.</span><span class="sxs-lookup"><span data-stu-id="474f4-125">installs several services.</span></span>  
  
 <span data-ttu-id="474f4-126">**Modalità di avvio**</span><span class="sxs-lookup"><span data-stu-id="474f4-126">**Start Mode**</span></span>  
 <span data-ttu-id="474f4-127">Impostare una delle opzioni seguenti per il servizio:</span><span class="sxs-lookup"><span data-stu-id="474f4-127">Set this service to the following choices:</span></span>  
  
-   <span data-ttu-id="474f4-128">Manuale: il servizio non viene avviato automaticamente all'avvio del computer.</span><span class="sxs-lookup"><span data-stu-id="474f4-128">Manual: This service does not automatically start when the computer starts.</span></span> <span data-ttu-id="474f4-129">In questo caso è necessario avviare il servizio tramite Gestione configurazione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o un altro strumento.</span><span class="sxs-lookup"><span data-stu-id="474f4-129">You must start the service using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, or some other tool.</span></span>  
  
-   <span data-ttu-id="474f4-130">Automatico: viene eseguito un tentativo automatico di avvio del servizio all'avvio del computer.</span><span class="sxs-lookup"><span data-stu-id="474f4-130">Automatic: This service attempts to start when this computer starts.</span></span>  
  
-   <span data-ttu-id="474f4-131">Disabilitato: il servizio non può essere avviato.</span><span class="sxs-lookup"><span data-stu-id="474f4-131">Disabled: This service cannot be started.</span></span>  
  
 <span data-ttu-id="474f4-132">**State**</span><span class="sxs-lookup"><span data-stu-id="474f4-132">**State**</span></span>  
 <span data-ttu-id="474f4-133">Indica se il servizio è in esecuzione, arrestato o disabilitato.</span><span class="sxs-lookup"><span data-stu-id="474f4-133">Indicates whether this service is running, stopped, or disabled.</span></span> <span data-ttu-id="474f4-134">" **...** " indica una modifica di stato in sospeso.</span><span class="sxs-lookup"><span data-stu-id="474f4-134">"**...**" indicates a state change is pending.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="474f4-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="474f4-135">See Also</span></span>  
 [<span data-ttu-id="474f4-136">Servizio SQL Server Browser</span><span class="sxs-lookup"><span data-stu-id="474f4-136">SQL Server Browser Service</span></span>](../../../2014/tools/configuration-manager/sql-server-browser-service.md)  
  
  
