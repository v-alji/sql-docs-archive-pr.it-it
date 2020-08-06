---
title: Proprietà - SQL Server Integration Services (scheda Servizio) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: 37f0acd9-c96f-48fd-9b53-2ca0097af242
author: stevestein
ms.author: sstein
ms.openlocfilehash: a752bdeab3c99ac97445e3281d3165a2d8f79866
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636967"
---
# <a name="sql-server-integration-services-properties-service-tab"></a><span data-ttu-id="578af-102">Proprietà - SQL Server Integration Services (scheda Servizio)</span><span class="sxs-lookup"><span data-stu-id="578af-102">SQL Server Integration Services Properties (Service Tab)</span></span>
  <span data-ttu-id="578af-103">Usare la scheda **Servizio** nella finestra di dialogo [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]Proprietà**di** per visualizzare o specificare le opzioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="578af-103">Use the **Service**tab on the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] **Properties** dialog box to view or specify the following options.</span></span>  
  
## <a name="options"></a><span data-ttu-id="578af-104">Opzioni</span><span class="sxs-lookup"><span data-stu-id="578af-104">Options</span></span>  
 <span data-ttu-id="578af-105">**Percorso binario**</span><span class="sxs-lookup"><span data-stu-id="578af-105">**Binary Path**</span></span>  
 <span data-ttu-id="578af-106">Visualizza il percorso dei file di programma utilizzati dal servizio.</span><span class="sxs-lookup"><span data-stu-id="578af-106">Displays the location of the program files used by this service.</span></span>  
  
 <span data-ttu-id="578af-107">**Controllo errori**</span><span class="sxs-lookup"><span data-stu-id="578af-107">**Error Control**</span></span>  
 <span data-ttu-id="578af-108">1 indica `SERVICE_ERROR_NORMAL`.</span><span class="sxs-lookup"><span data-stu-id="578af-108">1 indicates `SERVICE_ERROR_NORMAL`.</span></span> <span data-ttu-id="578af-109">In caso di problemi di avvio del servizio durante l'avvio del computer, il programma di avvio registra l'errore e visualizza una finestra di messaggio popup ma continua l'operazione di avvio.</span><span class="sxs-lookup"><span data-stu-id="578af-109">If the service fails to start during computer start up, the startup program logs the error and displays a pop-up message box but continues the startup operation.</span></span> <span data-ttu-id="578af-110">Questo valore non può essere modificato.</span><span class="sxs-lookup"><span data-stu-id="578af-110">This value cannot be changed.</span></span>  
  
 <span data-ttu-id="578af-111">**Codice di uscita**</span><span class="sxs-lookup"><span data-stu-id="578af-111">**Exit Code**</span></span>  
 <span data-ttu-id="578af-112">Codice di errore di [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows che definisce eventuali problemi verificatisi durante l'avvio o l'arresto del servizio.</span><span class="sxs-lookup"><span data-stu-id="578af-112">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows error code defining any problems encountered in starting or stopping the service.</span></span> <span data-ttu-id="578af-113">Questa proprietà viene impostata su **ERROR_SERVICE_SPECIFIC_ERROR** (1066) quando l'errore è univoco per il servizio rappresentato da questa classe. Le informazioni relative all'errore sono disponibili nella proprietà **ServiceSpecificExitCode** .</span><span class="sxs-lookup"><span data-stu-id="578af-113">This property is set to **ERROR_SERVICE_SPECIFIC_ERROR** (1066) when the error is unique to the service represented by this class, and information about the error is available in the **ServiceSpecificExitCode** property.</span></span> <span data-ttu-id="578af-114">Il servizio imposta questo valore su NO_ERROR (0) in fase di esecuzione e di nuovo al termine.</span><span class="sxs-lookup"><span data-stu-id="578af-114">The service sets this value to NO_ERROR (0) when running, and again upon normal termination.</span></span>  
  
 <span data-ttu-id="578af-115">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="578af-115">**Host Name**</span></span>  
 <span data-ttu-id="578af-116">Visualizza il nome del computer o del cluster che esegue il servizio [!INCLUDE[ssIS](../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="578af-116">Displays the name of the computer or cluster running the [!INCLUDE[ssIS](../../includes/ssis-md.md)] service.</span></span>  
  
 <span data-ttu-id="578af-117">**Nome**</span><span class="sxs-lookup"><span data-stu-id="578af-117">**Name**</span></span>  
 <span data-ttu-id="578af-118">Indica il nome visualizzato del servizio.</span><span class="sxs-lookup"><span data-stu-id="578af-118">Indicates the display name of the service.</span></span>  
  
 <span data-ttu-id="578af-119">**ID processo**</span><span class="sxs-lookup"><span data-stu-id="578af-119">**Process ID**</span></span>  
 <span data-ttu-id="578af-120">Visualizza l'ID di processo di Windows.</span><span class="sxs-lookup"><span data-stu-id="578af-120">Displays the Windows process ID.</span></span>  
  
 <span data-ttu-id="578af-121">**Tipo di servizio SQL Server**</span><span class="sxs-lookup"><span data-stu-id="578af-121">**SQL Service Type**</span></span>  
 <span data-ttu-id="578af-122">Visualizza il tipo di servizio fornito ai processi chiamanti.</span><span class="sxs-lookup"><span data-stu-id="578af-122">Displays the type of service provided to calling processes.</span></span> [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="578af-123">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installa diversi servizi.</span><span class="sxs-lookup"><span data-stu-id="578af-123">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installs several services.</span></span>  
  
 <span data-ttu-id="578af-124">**Modalità di avvio**</span><span class="sxs-lookup"><span data-stu-id="578af-124">**Start Mode**</span></span>  
 <span data-ttu-id="578af-125">Impostare una delle opzioni seguenti per il servizio:</span><span class="sxs-lookup"><span data-stu-id="578af-125">Set this service to the following choices:</span></span>  
  
-   <span data-ttu-id="578af-126">Manuale: il servizio non viene avviato automaticamente all'avvio del computer.</span><span class="sxs-lookup"><span data-stu-id="578af-126">Manual: This service does not automatically start when the computer starts.</span></span> <span data-ttu-id="578af-127">In questo caso è necessario avviare il servizio tramite Gestione configurazione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o un altro strumento.</span><span class="sxs-lookup"><span data-stu-id="578af-127">You must start the service using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, or some other tool.</span></span>  
  
-   <span data-ttu-id="578af-128">Automatico: viene eseguito un tentativo automatico di avvio del servizio all'avvio del computer.</span><span class="sxs-lookup"><span data-stu-id="578af-128">Automatic: This service attempts to start when this computer starts.</span></span>  
  
-   <span data-ttu-id="578af-129">Disabilitato: il servizio non può essere avviato.</span><span class="sxs-lookup"><span data-stu-id="578af-129">Disabled: This service cannot be started.</span></span>  
  
 <span data-ttu-id="578af-130">**State**</span><span class="sxs-lookup"><span data-stu-id="578af-130">**State**</span></span>  
 <span data-ttu-id="578af-131">Indica se il servizio è in esecuzione, arrestato o disabilitato.</span><span class="sxs-lookup"><span data-stu-id="578af-131">Indicates whether this service is running, stopped, or disabled.</span></span> <span data-ttu-id="578af-132">" **...** " indica una modifica di stato in sospeso.</span><span class="sxs-lookup"><span data-stu-id="578af-132">"**...**" indicates a state change is pending.</span></span>  
  
  
