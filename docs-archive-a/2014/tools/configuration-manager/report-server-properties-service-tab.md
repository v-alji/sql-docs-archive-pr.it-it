---
title: Proprietà - Server di report (scheda Servizio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: 2a2e1dbf-02b9-4893-aaf0-c0e4a2c9b4f9
author: stevestein
ms.author: sstein
ms.openlocfilehash: a8d223234e5f53eb087650d0634eb09b520cd21e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630172"
---
# <a name="report-server-properties-service-tab"></a><span data-ttu-id="ad00f-102">Proprietà - Server di report (scheda Servizio)</span><span class="sxs-lookup"><span data-stu-id="ad00f-102">Report Server Properties (Service Tab)</span></span>
  <span data-ttu-id="ad00f-103">Si tratta del servizio del server di report di [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ad00f-103">This service is the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Report Server service.</span></span> <span data-ttu-id="ad00f-104">I valori delle proprietà visualizzati in grigio chiaro non possono essere modificati con questa applicazione.</span><span class="sxs-lookup"><span data-stu-id="ad00f-104">The property values in light gray cannot be changed by using this application.</span></span>  
  
## <a name="options"></a><span data-ttu-id="ad00f-105">Opzioni</span><span class="sxs-lookup"><span data-stu-id="ad00f-105">Options</span></span>  
 <span data-ttu-id="ad00f-106">**Percorso binario**</span><span class="sxs-lookup"><span data-stu-id="ad00f-106">**Binary Path**</span></span>  
 <span data-ttu-id="ad00f-107">Visualizza il percorso dei file di programma utilizzati dal servizio.</span><span class="sxs-lookup"><span data-stu-id="ad00f-107">Displays the location of the program files used by this service.</span></span>  
  
 <span data-ttu-id="ad00f-108">**Controllo errori**</span><span class="sxs-lookup"><span data-stu-id="ad00f-108">**Error Control**</span></span>  
 <span data-ttu-id="ad00f-109">1 indica "SERVICE_ERROR_NORMAL".</span><span class="sxs-lookup"><span data-stu-id="ad00f-109">1 indicates "SERVICE_ERROR_NORMAL".</span></span> <span data-ttu-id="ad00f-110">In caso di problemi di avvio del servizio durante l'avvio del computer, il programma di avvio registra l'errore e visualizza una finestra di messaggio popup ma continua l'operazione di avvio.</span><span class="sxs-lookup"><span data-stu-id="ad00f-110">If the service fails to start during computer start up, the startup program logs the error and displays a pop-up message box but continues the startup operation.</span></span> <span data-ttu-id="ad00f-111">Questo valore non può essere modificato.</span><span class="sxs-lookup"><span data-stu-id="ad00f-111">This value cannot be changed.</span></span>  
  
 <span data-ttu-id="ad00f-112">**Codice di uscita**</span><span class="sxs-lookup"><span data-stu-id="ad00f-112">**Exit Code**</span></span>  
 <span data-ttu-id="ad00f-113">Quando si verifica un errore, il numero dell'errore viene visualizzato in questa casella.</span><span class="sxs-lookup"><span data-stu-id="ad00f-113">When an error occurs, the error number appears in this box.</span></span> <span data-ttu-id="ad00f-114">Questo numero può risultare utile per la risoluzione dei problemi. È possibile cercarlo nella [!INCLUDE[msCoName](../../includes/msconame-md.md)] Knowledge Base oppure comunicarlo al personale del supporto tecnico.</span><span class="sxs-lookup"><span data-stu-id="ad00f-114">Use this number to troubleshoot failures by searching for the number in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Knowledge Base or provide the number to your technical support staff.</span></span>  
  
 <span data-ttu-id="ad00f-115">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="ad00f-115">**Host Name**</span></span>  
 <span data-ttu-id="ad00f-116">Visualizza il nome del computer o del cluster che esegue la ricerca full-text.</span><span class="sxs-lookup"><span data-stu-id="ad00f-116">Displays the name of the computer or cluster running the full text search.</span></span>  
  
 <span data-ttu-id="ad00f-117">**Nome**</span><span class="sxs-lookup"><span data-stu-id="ad00f-117">**Name**</span></span>  
 <span data-ttu-id="ad00f-118">Indica il nome visualizzato del servizio.</span><span class="sxs-lookup"><span data-stu-id="ad00f-118">Indicates the display name of the service.</span></span>  
  
 <span data-ttu-id="ad00f-119">**ID processo**</span><span class="sxs-lookup"><span data-stu-id="ad00f-119">**Process ID**</span></span>  
 <span data-ttu-id="ad00f-120">Visualizza l'ID di processo di [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="ad00f-120">Displays the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows process ID.</span></span>  
  
 <span data-ttu-id="ad00f-121">**Tipo di servizio SQL Server**</span><span class="sxs-lookup"><span data-stu-id="ad00f-121">**SQL Service Type**</span></span>  
 <span data-ttu-id="ad00f-122">Tipo di servizio fornito ai processi chiamanti.</span><span class="sxs-lookup"><span data-stu-id="ad00f-122">Type of service provided to calling processes.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="ad00f-123">vengono installati diversi servizi.</span><span class="sxs-lookup"><span data-stu-id="ad00f-123">installs several services.</span></span>  
  
 <span data-ttu-id="ad00f-124">**Modalità di avvio**</span><span class="sxs-lookup"><span data-stu-id="ad00f-124">**Start Mode**</span></span>  
 <span data-ttu-id="ad00f-125">Impostare una delle opzioni seguenti per il servizio:</span><span class="sxs-lookup"><span data-stu-id="ad00f-125">Set this service to the following choices:</span></span>  
  
-   <span data-ttu-id="ad00f-126">Manuale: il servizio non viene avviato automaticamente all'avvio del computer.</span><span class="sxs-lookup"><span data-stu-id="ad00f-126">Manual: This service does not automatically start when the computer starts.</span></span> <span data-ttu-id="ad00f-127">In questo caso è necessario avviare il servizio tramite Gestione configurazione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o un altro strumento.</span><span class="sxs-lookup"><span data-stu-id="ad00f-127">You must start the service using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, or some other tool.</span></span>  
  
-   <span data-ttu-id="ad00f-128">Automatico: viene eseguito un tentativo automatico di avvio del servizio all'avvio del computer.</span><span class="sxs-lookup"><span data-stu-id="ad00f-128">Automatic: This service attempts to start when this computer starts.</span></span>  
  
-   <span data-ttu-id="ad00f-129">Disabilitato: il servizio non può essere avviato.</span><span class="sxs-lookup"><span data-stu-id="ad00f-129">Disabled: This service cannot be started.</span></span>  
  
 <span data-ttu-id="ad00f-130">**State**</span><span class="sxs-lookup"><span data-stu-id="ad00f-130">**State**</span></span>  
 <span data-ttu-id="ad00f-131">Indica se il servizio è in esecuzione, arrestato o disabilitato.</span><span class="sxs-lookup"><span data-stu-id="ad00f-131">Indicates whether this service is running, stopped, or disabled.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad00f-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ad00f-132">See Also</span></span>  
 [<span data-ttu-id="ad00f-133">Servizi di SQL Server</span><span class="sxs-lookup"><span data-stu-id="ad00f-133">SQL Server Services</span></span>](../../../2014/tools/configuration-manager/sql-server-services.md)  
  
  
