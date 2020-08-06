---
title: Proprietà - SQL Server (scheda Servizio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: e4ae0c6b-6fd8-4325-b54e-1758fc659958
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5822a02d5631e0d0e9318b20a1dcee87b8a4ded1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724316"
---
# <a name="sql-server-properties-service-tab"></a><span data-ttu-id="1f986-102">Proprietà - SQL Server (scheda Servizio)</span><span class="sxs-lookup"><span data-stu-id="1f986-102">SQL Server Properties (Service Tab)</span></span>
  <span data-ttu-id="1f986-103">Usare la scheda **Servizio**della finestra di dialogo **Proprietà - SQL (MSSQLSERVER)** per visualizzare o specificare le opzioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="1f986-103">Use the **Service**tab on the **MSSQLSERVER Properties** dialog box to view or specify the following options.</span></span>  
  
## <a name="options"></a><span data-ttu-id="1f986-104">Opzioni</span><span class="sxs-lookup"><span data-stu-id="1f986-104">Options</span></span>  
 <span data-ttu-id="1f986-105">**Percorso binario**</span><span class="sxs-lookup"><span data-stu-id="1f986-105">**Binary Path**</span></span>  
 <span data-ttu-id="1f986-106">Elenca il percorso dei file di programma utilizzati dal servizio.</span><span class="sxs-lookup"><span data-stu-id="1f986-106">Lists the location of the program files used by this service.</span></span>  
  
 <span data-ttu-id="1f986-107">**Controllo errori**</span><span class="sxs-lookup"><span data-stu-id="1f986-107">**Error Control**</span></span>  
 <span data-ttu-id="1f986-108">1 indica `SERVICE_ERROR_NORMAL`.</span><span class="sxs-lookup"><span data-stu-id="1f986-108">1 indicates `SERVICE_ERROR_NORMAL`.</span></span> <span data-ttu-id="1f986-109">In caso di problemi di avvio del servizio durante l'avvio del computer, il programma di avvio registra l'errore e visualizza una finestra di messaggio popup ma continua l'operazione di avvio.</span><span class="sxs-lookup"><span data-stu-id="1f986-109">If the service fails to start during computer start up, the startup program logs the error and displays a pop-up message box but continues the startup operation.</span></span> <span data-ttu-id="1f986-110">Questo valore non può essere modificato.</span><span class="sxs-lookup"><span data-stu-id="1f986-110">This value cannot be changed.</span></span>  
  
 <span data-ttu-id="1f986-111">**Codice di uscita**</span><span class="sxs-lookup"><span data-stu-id="1f986-111">**Exit Code**</span></span>  
 <span data-ttu-id="1f986-112">Quando si verifica un errore, il numero dell'errore viene visualizzato in questa casella.</span><span class="sxs-lookup"><span data-stu-id="1f986-112">When an error occurs, the error number appears in this box.</span></span> <span data-ttu-id="1f986-113">Questo numero può risultare utile per la risoluzione dei problemi. È possibile cercarlo nella [!INCLUDE[msCoName](../../includes/msconame-md.md)] Knowledge Base oppure comunicarlo al personale del supporto tecnico.</span><span class="sxs-lookup"><span data-stu-id="1f986-113">Use this number to troubleshoot failures by searching for the number in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Knowledge Base or provide the number to your technical support staff.</span></span>  
  
 <span data-ttu-id="1f986-114">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="1f986-114">**Host Name**</span></span>  
 <span data-ttu-id="1f986-115">Visualizza il nome del computer o del cluster che esegue il servizio [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1f986-115">Displays the name of the computer or cluster running the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service.</span></span>  
  
 <span data-ttu-id="1f986-116">**Nome**</span><span class="sxs-lookup"><span data-stu-id="1f986-116">**Name**</span></span>  
 <span data-ttu-id="1f986-117">Indica il nome visualizzato del servizio.</span><span class="sxs-lookup"><span data-stu-id="1f986-117">Indicates the display name of the service.</span></span>  
  
 <span data-ttu-id="1f986-118">**ID processo**</span><span class="sxs-lookup"><span data-stu-id="1f986-118">**Process ID**</span></span>  
 <span data-ttu-id="1f986-119">Visualizza l'ID di processo di Windows.</span><span class="sxs-lookup"><span data-stu-id="1f986-119">Displays the Windows process ID.</span></span>  
  
 <span data-ttu-id="1f986-120">**Tipo di servizio**</span><span class="sxs-lookup"><span data-stu-id="1f986-120">**Service Type**</span></span>  
 <span data-ttu-id="1f986-121">Visualizza il tipo di servizio fornito ai processi chiamanti.</span><span class="sxs-lookup"><span data-stu-id="1f986-121">Displays the type of service provided to calling processes.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="1f986-122">vengono installati diversi servizi.</span><span class="sxs-lookup"><span data-stu-id="1f986-122">installs several services.</span></span>  
  
 <span data-ttu-id="1f986-123">**Modalità di avvio**</span><span class="sxs-lookup"><span data-stu-id="1f986-123">**Start Mode**</span></span>  
 <span data-ttu-id="1f986-124">Impostare una delle opzioni seguenti per il servizio:</span><span class="sxs-lookup"><span data-stu-id="1f986-124">Set this service to the following choices:</span></span>  
  
-   <span data-ttu-id="1f986-125">Manuale: il servizio non viene avviato automaticamente all'avvio del computer.</span><span class="sxs-lookup"><span data-stu-id="1f986-125">Manual: This service does not automatically start when the computer starts.</span></span> <span data-ttu-id="1f986-126">In questo caso è necessario avviare il servizio tramite Gestione configurazione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o un altro strumento.</span><span class="sxs-lookup"><span data-stu-id="1f986-126">You must start the service using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, or some other tool.</span></span>  
  
-   <span data-ttu-id="1f986-127">Automatico: viene eseguito un tentativo automatico di avvio del servizio all'avvio del computer.</span><span class="sxs-lookup"><span data-stu-id="1f986-127">Automatic: This service attempts to start when this computer starts.</span></span>  
  
-   <span data-ttu-id="1f986-128">Disabilitato: il servizio non può essere avviato.</span><span class="sxs-lookup"><span data-stu-id="1f986-128">Disabled: This service cannot be started.</span></span>  
  
 <span data-ttu-id="1f986-129">**State**</span><span class="sxs-lookup"><span data-stu-id="1f986-129">**State**</span></span>  
 <span data-ttu-id="1f986-130">Indica se il servizio è in esecuzione, arrestato o disabilitato.</span><span class="sxs-lookup"><span data-stu-id="1f986-130">Indicates whether this service is running, stopped, or disabled.</span></span> <span data-ttu-id="1f986-131">" **...** " indica una modifica di stato in sospeso.</span><span class="sxs-lookup"><span data-stu-id="1f986-131">"**...**" indicates a state change is pending.</span></span>  
  
  
