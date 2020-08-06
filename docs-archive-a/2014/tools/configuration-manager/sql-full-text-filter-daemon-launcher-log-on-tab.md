---
title: Utilità di avvio del daemon filtri full-text di SQL (scheda Accesso) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: 13e260f9-a75f-430b-88a3-959ddcead8fe
author: stevestein
ms.author: sstein
ms.openlocfilehash: cb3f23907e96214929617bf2923e46148c0ab1f8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636974"
---
# <a name="sql-full-text-filter-daemon-launcher-log-on-tab"></a><span data-ttu-id="be86e-102">Utilità di avvio del daemon filtri full-text di SQL (scheda Accesso)</span><span class="sxs-lookup"><span data-stu-id="be86e-102">SQL Full-text Filter Daemon Launcher (Log On Tab)</span></span>
  <span data-ttu-id="be86e-103">A partire da [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], il servizio Utilità di avvio del daemon filtri full-text di SQL (FDHOST Launcher) viene utilizzato dalla ricerca full-text in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="be86e-103">Beginning in [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], the SQL Full-text Filter Daemon Launcher (FDHOST Launcher) service is used by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] full-text search.</span></span> <span data-ttu-id="be86e-104">Se si utilizza la ricerca full-text, questo servizio deve essere in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="be86e-104">This service must be running if you use full-text search.</span></span> <span data-ttu-id="be86e-105">Per informazioni sui processi host del daemon di filtri, vedere "Architettura della ricerca full-text" nella documentazione online di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="be86e-105">For information about the filter daemon host processes, see "Full-Text Search Architecture" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
 <span data-ttu-id="be86e-106">Utilizzare la scheda **Accesso** della finestra di dialogo **Proprietà - Utilità di avvio del daemon filtri full-text di SQL** per specificare l'account utilizzato dal servizio full-text di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per modificare la password di un account e per avviare e arrestare il servizio.</span><span class="sxs-lookup"><span data-stu-id="be86e-106">Use the **Log On** tab of the **SQL Full-text Filter Daemon Launcher  Properties** dialog box to specify the account used by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] full-text service, to change the password of an account, and to start and stop the service.</span></span> <span data-ttu-id="be86e-107">La modifica della password di un account diventa effettiva dopo il riavvio del servizio.</span><span class="sxs-lookup"><span data-stu-id="be86e-107">Changing the password of an account takes affect after restarting the service.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="be86e-108">Quando si modifica il nome account utilizzato da un servizio in un'istanza cluster, il nuovo account deve essere membro del gruppo di dominio specificato durante l’installazione per il servizio oppure è necessario disporre dell’autorizzazione per aggiungere membri a tale gruppo.</span><span class="sxs-lookup"><span data-stu-id="be86e-108">When changing the account name used by a service on a clustered instance, either the new account must be a member of the domain group specified during setup for the service, or you must have permission to add members to that group.</span></span> <span data-ttu-id="be86e-109">Se non si dispone dell’autorizzazione per modificare l'appartenenza al gruppo, contattare l’amministratore di dominio.</span><span class="sxs-lookup"><span data-stu-id="be86e-109">If you do not have permission to modify group membership, contact the domain administrator.</span></span>  
>   
>  <span data-ttu-id="be86e-110">Per ulteriori informazioni sulla selezione di un account per l'esecuzione del servizio, vedere "Impostazione di account di servizio Windows" nella documentazione online di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="be86e-110">For more information about selecting an account to run the service, see "Setting Up Windows Service Accounts" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="options"></a><span data-ttu-id="be86e-111">Opzioni</span><span class="sxs-lookup"><span data-stu-id="be86e-111">Options</span></span>  
 <span data-ttu-id="be86e-112">**Account predefinito**</span><span class="sxs-lookup"><span data-stu-id="be86e-112">**Built-in account**</span></span>  
 <span data-ttu-id="be86e-113">**Sistema locale**</span><span class="sxs-lookup"><span data-stu-id="be86e-113">**Local System**</span></span>  
 <span data-ttu-id="be86e-114">Specifica l'account di sistema locale.</span><span class="sxs-lookup"><span data-stu-id="be86e-114">Specify the local system account.</span></span> <span data-ttu-id="be86e-115">Per questo account non è necessaria una password.</span><span class="sxs-lookup"><span data-stu-id="be86e-115">This account does not require a password.</span></span> <span data-ttu-id="be86e-116">Tuttavia, a seconda dei privilegi concessi, l'account di sistema locale può impedire le interazioni tra il servizio e gli altri server.</span><span class="sxs-lookup"><span data-stu-id="be86e-116">However, the local system account may prevent the service from interacting with other servers, depending on the privileges granted to the account.</span></span>  
  
 <span data-ttu-id="be86e-117">**Servizio locale**</span><span class="sxs-lookup"><span data-stu-id="be86e-117">**Local Service**</span></span>  
 <span data-ttu-id="be86e-118">Specifica l'account di servizio locale.</span><span class="sxs-lookup"><span data-stu-id="be86e-118">Specify the local service account.</span></span> <span data-ttu-id="be86e-119">Per questo account non è necessaria una password.</span><span class="sxs-lookup"><span data-stu-id="be86e-119">This account does not require a password.</span></span> <span data-ttu-id="be86e-120">Tuttavia, a seconda dei privilegi concessi, l'account di servizio locale può impedire le interazioni tra il servizio e gli altri server.</span><span class="sxs-lookup"><span data-stu-id="be86e-120">However, the local service account may prevent the service from interacting with other servers, depending on the privileges granted to the account.</span></span>  
  
 <span data-ttu-id="be86e-121">**Servizio di rete**</span><span class="sxs-lookup"><span data-stu-id="be86e-121">**Network Service**</span></span>  
 <span data-ttu-id="be86e-122">È consigliabile non utilizzare l'account Servizio di rete per i servizi di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o i servizi [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="be86e-122">We recommend that you do not use the Network Service account for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] services or the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent services.</span></span> <span data-ttu-id="be86e-123">Per questi servizi sono più adatti gli account utente locale o di dominio.</span><span class="sxs-lookup"><span data-stu-id="be86e-123">Local User or Domain User accounts are more appropriate for these services.</span></span>  
  
 <span data-ttu-id="be86e-124">**Account seguente**</span><span class="sxs-lookup"><span data-stu-id="be86e-124">**This account**</span></span>  
 <span data-ttu-id="be86e-125">Specificare un account utente locale o di dominio che utilizza l’autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="be86e-125">Specify a local or domain user account that uses Windows Authentication.</span></span> <span data-ttu-id="be86e-126">È consigliabile utilizzare un account utente di dominio con diritti minimi per i servizi.</span><span class="sxs-lookup"><span data-stu-id="be86e-126">We recommend that you use a domain user account that has minimal rights for services.</span></span>  
  
 <span data-ttu-id="be86e-127">**Account Name** (Nome account)</span><span class="sxs-lookup"><span data-stu-id="be86e-127">**Account Name**</span></span>  
 <span data-ttu-id="be86e-128">Specificare il nome dell'account utente locale o di dominio.</span><span class="sxs-lookup"><span data-stu-id="be86e-128">Specify the local or domain user account name.</span></span>  
  
 <span data-ttu-id="be86e-129">**Password**</span><span class="sxs-lookup"><span data-stu-id="be86e-129">**Password**</span></span>  
 <span data-ttu-id="be86e-130">Digitare la password dell'account.</span><span class="sxs-lookup"><span data-stu-id="be86e-130">Type the password of the account.</span></span>  
  
 <span data-ttu-id="be86e-131">**Conferma password**</span><span class="sxs-lookup"><span data-stu-id="be86e-131">**Confirm password**</span></span>  
 <span data-ttu-id="be86e-132">Digitare nuovamente la password dell'account.</span><span class="sxs-lookup"><span data-stu-id="be86e-132">Type the password of the account again.</span></span>  
  
 <span data-ttu-id="be86e-133">**Inizia**</span><span class="sxs-lookup"><span data-stu-id="be86e-133">**Start**</span></span>  
 <span data-ttu-id="be86e-134">Avviare il servizio.</span><span class="sxs-lookup"><span data-stu-id="be86e-134">Start the service.</span></span>  
  
 <span data-ttu-id="be86e-135">**Stop**</span><span class="sxs-lookup"><span data-stu-id="be86e-135">**Stop**</span></span>  
 <span data-ttu-id="be86e-136">Consente di arrestare il servizio.</span><span class="sxs-lookup"><span data-stu-id="be86e-136">Stop the service.</span></span>  
  
 <span data-ttu-id="be86e-137">**Sospendi**</span><span class="sxs-lookup"><span data-stu-id="be86e-137">**Pause**</span></span>  
 <span data-ttu-id="be86e-138">Consente di sospendere il servizio.</span><span class="sxs-lookup"><span data-stu-id="be86e-138">Pause the service.</span></span> <span data-ttu-id="be86e-139">Non disponibile per questo servizio.</span><span class="sxs-lookup"><span data-stu-id="be86e-139">Not available for this service.</span></span>  
  
 <span data-ttu-id="be86e-140">**Riprendi**</span><span class="sxs-lookup"><span data-stu-id="be86e-140">**Resume**</span></span>  
 <span data-ttu-id="be86e-141">Consente di riprendere un servizio sospeso.</span><span class="sxs-lookup"><span data-stu-id="be86e-141">Resume a paused service.</span></span>  
  
  
