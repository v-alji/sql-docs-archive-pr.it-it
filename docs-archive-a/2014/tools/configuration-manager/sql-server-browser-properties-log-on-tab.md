---
title: Proprietà - SQL Server Browser (scheda Accesso) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: c77871ec-c2f4-4e4a-9a10-5aeb4ae70507
author: stevestein
ms.author: sstein
ms.openlocfilehash: 0c1f7d0cfd9e9b05a2a04f3c3e9efba687522298
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711379"
---
# <a name="sql-server-browser-properties-log-on-tab"></a><span data-ttu-id="90879-102">Proprietà - SQL Server Browser (scheda Accesso)</span><span class="sxs-lookup"><span data-stu-id="90879-102">SQL Server Browser Properties (Log On Tab)</span></span>
  <span data-ttu-id="90879-103">Il programma [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser viene eseguito come servizio nel server.</span><span class="sxs-lookup"><span data-stu-id="90879-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser program runs as a service on the server.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="90879-104">Browser rimane in attesa delle richieste in entrata di risorse di [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e fornisce informazioni sulle istanze di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installate nel computer.</span><span class="sxs-lookup"><span data-stu-id="90879-104">Browser listens for incoming requests for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] resources and provides information about [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instances installed on the computer.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="90879-105">SQL Server Browser resta in attesa su una porta UDP e accetta le richieste non autenticate tramite il protocollo SSRP ( [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Resolution Protocol).</span><span class="sxs-lookup"><span data-stu-id="90879-105">Browser listens on a UDP port and accepts unauthenticated requests using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Resolution Protocol (SSRP).</span></span>  
  
 <span data-ttu-id="90879-106">La modifica della password di un account diventa effettiva immediatamente, senza dover riavviare il servizio.</span><span class="sxs-lookup"><span data-stu-id="90879-106">Changing the password of an account takes effect immediately without restarting the service.</span></span>  
  
## <a name="options"></a><span data-ttu-id="90879-107">Opzioni</span><span class="sxs-lookup"><span data-stu-id="90879-107">Options</span></span>  
 <span data-ttu-id="90879-108">**Account di sistema locale**</span><span class="sxs-lookup"><span data-stu-id="90879-108">**Local System account**</span></span>  
 <span data-ttu-id="90879-109">Consente di eseguire il servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser nel contesto di sicurezza dell'account di sistema locale.</span><span class="sxs-lookup"><span data-stu-id="90879-109">Run the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service in the security context of the Local System account.</span></span> <span data-ttu-id="90879-110">È tuttavia consigliabile utilizzare un account con poche autorizzazioni, se possibile.</span><span class="sxs-lookup"><span data-stu-id="90879-110">When possible, use a low-permission account instead.</span></span>  
  
 <span data-ttu-id="90879-111">**Account seguente**</span><span class="sxs-lookup"><span data-stu-id="90879-111">**This account**</span></span>  
 <span data-ttu-id="90879-112">Specificare un account utente locale o di dominio che utilizza l’autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="90879-112">Specify a local or domain user account that uses Windows Authentication.</span></span> <span data-ttu-id="90879-113">È consigliabile usare un account utente di dominio con diritti minimi per i servizi.</span><span class="sxs-lookup"><span data-stu-id="90879-113">We recommend using a domain user account with minimal rights for services.</span></span> <span data-ttu-id="90879-114">Per ulteriori informazioni sulla selezione di un account, vedere "Impostazione di account di servizio Windows" nella documentazione online di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="90879-114">For information about selecting an account, see "Setting Up Windows Service Accounts" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
 <span data-ttu-id="90879-115">**Sfoglia**</span><span class="sxs-lookup"><span data-stu-id="90879-115">**Browse**</span></span>  
 <span data-ttu-id="90879-116">Consente di individuare un utente o un'entità di sicurezza predefinita.</span><span class="sxs-lookup"><span data-stu-id="90879-116">Browse for a user or built-in security principal.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="90879-117">Utilizzare un account con poche autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="90879-117">Use a low-permission account.</span></span> <span data-ttu-id="90879-118">Per informazioni sulle autorizzazioni necessarie per il servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser, vedere la sezione relativa alla sicurezza in [Servizio SQL Server Browser](../../../2014/tools/configuration-manager/sql-server-browser-service.md).</span><span class="sxs-lookup"><span data-stu-id="90879-118">For information about the permissions required for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser Service, see the Security section of [SQL Server Browser Service](../../../2014/tools/configuration-manager/sql-server-browser-service.md).</span></span>  
  
 <span data-ttu-id="90879-119">**Password**</span><span class="sxs-lookup"><span data-stu-id="90879-119">**Password**</span></span>  
 <span data-ttu-id="90879-120">Immettere la password dell'entità di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="90879-120">Enter the password of the security principal.</span></span>  
  
 <span data-ttu-id="90879-121">**Conferma password**</span><span class="sxs-lookup"><span data-stu-id="90879-121">**Confirm password**</span></span>  
 <span data-ttu-id="90879-122">Confermare la password dell'entità di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="90879-122">Confirm the password of the security principal.</span></span>  
  
 <span data-ttu-id="90879-123">**Stato del servizio**</span><span class="sxs-lookup"><span data-stu-id="90879-123">**Service status**</span></span>  
 <span data-ttu-id="90879-124">Indica se il servizio è in esecuzione, arrestato o disabilitato.</span><span class="sxs-lookup"><span data-stu-id="90879-124">Indicates whether this service is running, stopped, or disabled.</span></span> <span data-ttu-id="90879-125">" **...** " indica una modifica di stato in sospeso.</span><span class="sxs-lookup"><span data-stu-id="90879-125">"**...**" indicates a state change is pending.</span></span>  
  
 <span data-ttu-id="90879-126">**Inizia**</span><span class="sxs-lookup"><span data-stu-id="90879-126">**Start**</span></span>  
 <span data-ttu-id="90879-127">Consente di avviare il servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser.</span><span class="sxs-lookup"><span data-stu-id="90879-127">Start the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service.</span></span>  
  
 <span data-ttu-id="90879-128">**Stop**</span><span class="sxs-lookup"><span data-stu-id="90879-128">**Stop**</span></span>  
 <span data-ttu-id="90879-129">Consente di arrestare il servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser.</span><span class="sxs-lookup"><span data-stu-id="90879-129">Stop the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service.</span></span>  
  
 <span data-ttu-id="90879-130">**Sospendi**</span><span class="sxs-lookup"><span data-stu-id="90879-130">**Pause**</span></span>  
 <span data-ttu-id="90879-131">Consente di sospendere il servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser.</span><span class="sxs-lookup"><span data-stu-id="90879-131">Pause the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service.</span></span>  
  
 <span data-ttu-id="90879-132">**Riprendi**</span><span class="sxs-lookup"><span data-stu-id="90879-132">**Resume**</span></span>  
 <span data-ttu-id="90879-133">Consente di riprendere un'istanza del servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser sospesa.</span><span class="sxs-lookup"><span data-stu-id="90879-133">Resume a paused [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90879-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="90879-134">See Also</span></span>  
 [<span data-ttu-id="90879-135">Servizio SQL Server Browser</span><span class="sxs-lookup"><span data-stu-id="90879-135">SQL Server Browser Service</span></span>](../../../2014/tools/configuration-manager/sql-server-browser-service.md)  
  
  
