---
title: Proprietà - Analysis Server (scheda Servizio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: 8dbe4bc5-6aa9-48ee-857e-0b4ea764b9cb
author: stevestein
ms.author: sstein
ms.openlocfilehash: 91200120d87224c8e7733b0ff41ed423d3086c34
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725191"
---
# <a name="analysis-server-properties-service-tab"></a><span data-ttu-id="5e5c3-102">Proprietà - Analysis Server (scheda Servizio)</span><span class="sxs-lookup"><span data-stu-id="5e5c3-102">Analysis Server Properties (Service Tab)</span></span>
  <span data-ttu-id="5e5c3-103">Si tratta del servizio [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5e5c3-103">This service is the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="5e5c3-104">Questo servizio deve essere eseguito affinché [!INCLUDE[ssAS](../../includes/ssas-md.md)] funzioni in modo corretto.</span><span class="sxs-lookup"><span data-stu-id="5e5c3-104">This service must be running for [!INCLUDE[ssAS](../../includes/ssas-md.md)] to work properly.</span></span> <span data-ttu-id="5e5c3-105">I valori delle proprietà visualizzati in grigio chiaro non possono essere modificati con questa applicazione.</span><span class="sxs-lookup"><span data-stu-id="5e5c3-105">The property values in light gray cannot be changed using this application.</span></span>  
  
## <a name="options"></a><span data-ttu-id="5e5c3-106">Opzioni</span><span class="sxs-lookup"><span data-stu-id="5e5c3-106">Options</span></span>  
 <span data-ttu-id="5e5c3-107">**Percorso binario**</span><span class="sxs-lookup"><span data-stu-id="5e5c3-107">**Binary Path**</span></span>  
 <span data-ttu-id="5e5c3-108">Visualizza il percorso dei file di programma utilizzati dal servizio.</span><span class="sxs-lookup"><span data-stu-id="5e5c3-108">Displays the location of the program files used by this service.</span></span>  
  
 <span data-ttu-id="5e5c3-109">**Controllo errori**</span><span class="sxs-lookup"><span data-stu-id="5e5c3-109">**Error Control**</span></span>  
 <span data-ttu-id="5e5c3-110">1 indica `SERVICE_ERROR_NORMAL`.</span><span class="sxs-lookup"><span data-stu-id="5e5c3-110">1 indicates `SERVICE_ERROR_NORMAL`.</span></span> <span data-ttu-id="5e5c3-111">In caso di problemi di avvio del servizio durante l'avvio del computer, il programma di avvio registra l'errore e visualizza una finestra di messaggio popup ma continua l'operazione di avvio.</span><span class="sxs-lookup"><span data-stu-id="5e5c3-111">If the service fails to start during computer start up, the startup program logs the error and displays a pop-up message box but continues the startup operation.</span></span> <span data-ttu-id="5e5c3-112">Questo valore non può essere modificato.</span><span class="sxs-lookup"><span data-stu-id="5e5c3-112">This value cannot be changed.</span></span>  
  
 <span data-ttu-id="5e5c3-113">**Codice di uscita**</span><span class="sxs-lookup"><span data-stu-id="5e5c3-113">**Exit Code**</span></span>  
 <span data-ttu-id="5e5c3-114">Quando si verifica un errore, il numero dell'errore viene visualizzato in questa casella.</span><span class="sxs-lookup"><span data-stu-id="5e5c3-114">When an error occurs, the error number appears in this box.</span></span> <span data-ttu-id="5e5c3-115">Questo numero può risultare utile per la risoluzione dei problemi. È possibile cercarlo nella [!INCLUDE[msCoName](../../includes/msconame-md.md)] Knowledge Base oppure comunicarlo al personale del supporto tecnico.</span><span class="sxs-lookup"><span data-stu-id="5e5c3-115">Use this number to troubleshoot failures by searching for the number in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Knowledge Base or provide the number to your technical support staff.</span></span>  
  
 <span data-ttu-id="5e5c3-116">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="5e5c3-116">**Host Name**</span></span>  
 <span data-ttu-id="5e5c3-117">Visualizza il nome del computer o del cluster che esegue [!INCLUDE[ssAS](../../includes/ssas-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5e5c3-117">Displays the name of the computer or cluster running [!INCLUDE[ssAS](../../includes/ssas-md.md)].</span></span>  
  
 <span data-ttu-id="5e5c3-118">**Nome**</span><span class="sxs-lookup"><span data-stu-id="5e5c3-118">**Name**</span></span>  
 <span data-ttu-id="5e5c3-119">Indica il nome visualizzato del servizio.</span><span class="sxs-lookup"><span data-stu-id="5e5c3-119">Indicates the display name of the service.</span></span>  
  
 <span data-ttu-id="5e5c3-120">**ID processo**</span><span class="sxs-lookup"><span data-stu-id="5e5c3-120">**Process ID**</span></span>  
 <span data-ttu-id="5e5c3-121">Visualizza il numero usato da [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows per tenere traccia dei processi di questo programma.</span><span class="sxs-lookup"><span data-stu-id="5e5c3-121">Displays the number used by [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows to keep track of this program's processes.</span></span>  
  
 <span data-ttu-id="5e5c3-122">**Tipo di servizio SQL Server**</span><span class="sxs-lookup"><span data-stu-id="5e5c3-122">**SQL Service Type**</span></span>  
 <span data-ttu-id="5e5c3-123">Visualizza il tipo di servizio fornito ai processi chiamanti.</span><span class="sxs-lookup"><span data-stu-id="5e5c3-123">Displays the type of service provided to calling processes.</span></span> [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="5e5c3-124">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installa diversi servizi.</span><span class="sxs-lookup"><span data-stu-id="5e5c3-124">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installs several services.</span></span>  
  
 <span data-ttu-id="5e5c3-125">**Modalità di avvio**</span><span class="sxs-lookup"><span data-stu-id="5e5c3-125">**Start Mode**</span></span>  
 <span data-ttu-id="5e5c3-126">Impostare una delle opzioni seguenti per il servizio:</span><span class="sxs-lookup"><span data-stu-id="5e5c3-126">Set this service to the following choices:</span></span>  
  
-   <span data-ttu-id="5e5c3-127">Manuale: il servizio non viene avviato automaticamente all'avvio del computer.</span><span class="sxs-lookup"><span data-stu-id="5e5c3-127">Manual: This service does not automatically start when the computer starts.</span></span> <span data-ttu-id="5e5c3-128">In questo caso è necessario avviare il servizio tramite Gestione configurazione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o un altro strumento.</span><span class="sxs-lookup"><span data-stu-id="5e5c3-128">You must start the service using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, or some other tool.</span></span>  
  
-   <span data-ttu-id="5e5c3-129">Automatico: viene eseguito un tentativo automatico di avvio del servizio all'avvio del computer.</span><span class="sxs-lookup"><span data-stu-id="5e5c3-129">Automatic: This service attempts to start when this computer starts.</span></span>  
  
-   <span data-ttu-id="5e5c3-130">Disabilitato: il servizio non può essere avviato.</span><span class="sxs-lookup"><span data-stu-id="5e5c3-130">Disabled: This service cannot be started.</span></span>  
  
 <span data-ttu-id="5e5c3-131">**State**</span><span class="sxs-lookup"><span data-stu-id="5e5c3-131">**State**</span></span>  
 <span data-ttu-id="5e5c3-132">Indica se il servizio è in esecuzione, arrestato o disabilitato.</span><span class="sxs-lookup"><span data-stu-id="5e5c3-132">Indicates whether this service is running, stopped, or disabled.</span></span>  
  
  
