---
title: Proprietà - SQL Server (scheda Accesso) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: 405073fc-eaa3-43c6-bf82-2cd58cacc1c3
author: stevestein
ms.author: sstein
ms.openlocfilehash: adec9ed7c69023218baa96ab8f8edbb6f2b365bd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629115"
---
# <a name="sql-server-properties-log-on-tab"></a><span data-ttu-id="be952-102">Proprietà - SQL Server (scheda Accesso)</span><span class="sxs-lookup"><span data-stu-id="be952-102">SQL Server Properties (Log On Tab)</span></span>
  <span data-ttu-id="be952-103">Utilizzare la scheda **Accesso** della finestra di dialogo **Proprietà - SQL Server** per specificare l'account utilizzato dal servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per modificare la password di un account e per avviare e arrestare il servizio.</span><span class="sxs-lookup"><span data-stu-id="be952-103">Use the **Log On** tab of the **SQL Server Properties** dialog box to specify the account used by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service, to change the password of an account, and to start and stop the service.</span></span> <span data-ttu-id="be952-104">La modifica della password di un account ha effetto immediato.</span><span class="sxs-lookup"><span data-stu-id="be952-104">Changing the password of an account takes effect immediately.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="be952-105">Quando si modifica il nome account utilizzato da un servizio in un'istanza cluster, il nuovo account deve essere membro del gruppo di dominio specificato durante l’installazione per il servizio in corso di modifica oppure è necessario disporre dell’autorizzazione per aggiungere membri a tale gruppo.</span><span class="sxs-lookup"><span data-stu-id="be952-105">When changing the account name used by a service on a clustered instance, the new account must be a member of the domain group specified during setup for the service being changed, or you must have permission to add members to that group.</span></span> <span data-ttu-id="be952-106">Se non si dispone dell’autorizzazione per modificare l'appartenenza al gruppo, contattare l’amministratore di dominio.</span><span class="sxs-lookup"><span data-stu-id="be952-106">If you do not have permission to modify group membership, contact the domain administrator.</span></span>  
>   
>  <span data-ttu-id="be952-107">Per ulteriori informazioni sulla selezione di un account per l'esecuzione del servizio, vedere "Impostazione di account di servizio Windows" nella documentazione online di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="be952-107">For more information about selecting an account to run the service, see "Setting Up Windows Service Accounts" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="options"></a><span data-ttu-id="be952-108">Opzioni</span><span class="sxs-lookup"><span data-stu-id="be952-108">Options</span></span>  
 <span data-ttu-id="be952-109">**Account predefinito**</span><span class="sxs-lookup"><span data-stu-id="be952-109">**Built-in account**</span></span>  
 <span data-ttu-id="be952-110">**Sistema locale**</span><span class="sxs-lookup"><span data-stu-id="be952-110">**Local System**</span></span>  
 -   <span data-ttu-id="be952-111">Specifica l'account di sistema locale.</span><span class="sxs-lookup"><span data-stu-id="be952-111">Specify the local system account.</span></span> <span data-ttu-id="be952-112">Per questo account non è necessaria una password.</span><span class="sxs-lookup"><span data-stu-id="be952-112">This account does not require a password.</span></span> <span data-ttu-id="be952-113">Tuttavia, a seconda dei privilegi concessi, l'account di sistema locale può impedire le interazioni tra il servizio e gli altri server.</span><span class="sxs-lookup"><span data-stu-id="be952-113">However, the local system account may prevent the service from interacting with other servers, depending on the privileges granted to the account.</span></span>  
  
 <span data-ttu-id="be952-114">**Servizio locale**</span><span class="sxs-lookup"><span data-stu-id="be952-114">**Local Service**</span></span>  
 -   <span data-ttu-id="be952-115">Specifica l'account di servizio locale.</span><span class="sxs-lookup"><span data-stu-id="be952-115">Specify the local service account.</span></span> <span data-ttu-id="be952-116">Per questo account non è necessaria una password.</span><span class="sxs-lookup"><span data-stu-id="be952-116">This account does not require a password.</span></span> <span data-ttu-id="be952-117">Tuttavia, a seconda dei privilegi concessi, l'account di servizio locale può impedire le interazioni tra il servizio e gli altri server.</span><span class="sxs-lookup"><span data-stu-id="be952-117">However, the local service account may prevent the service from interacting with other servers, depending on the privileges granted to the account.</span></span>  
  
 <span data-ttu-id="be952-118">**Servizio di rete**</span><span class="sxs-lookup"><span data-stu-id="be952-118">**Network Service**</span></span>  
 -   <span data-ttu-id="be952-119">È consigliabile non utilizzare l'account Servizio di rete per i servizi [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent e [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="be952-119">We recommend that you do not use the Network Service account for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent services.</span></span> <span data-ttu-id="be952-120">Per questi servizi sono più adatti gli account utente locale o di dominio.</span><span class="sxs-lookup"><span data-stu-id="be952-120">Local User or Domain User accounts are more appropriate for these services.</span></span>  
  
 <span data-ttu-id="be952-121">**Account seguente**</span><span class="sxs-lookup"><span data-stu-id="be952-121">**This account**</span></span>  
 <span data-ttu-id="be952-122">Specificare un account utente locale o di dominio che utilizza l’autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="be952-122">Specify a local or domain user account that uses Windows Authentication.</span></span> <span data-ttu-id="be952-123">È consigliabile utilizzare un account utente di dominio con diritti minimi per i servizi.</span><span class="sxs-lookup"><span data-stu-id="be952-123">We recommend that you use a domain user account that has minimal rights for services.</span></span>  
  
 <span data-ttu-id="be952-124">**Account Name** (Nome account)</span><span class="sxs-lookup"><span data-stu-id="be952-124">**Account Name**</span></span>  
 <span data-ttu-id="be952-125">Specificare il nome dell'account utente locale o di dominio.</span><span class="sxs-lookup"><span data-stu-id="be952-125">Specify the local or domain user account name.</span></span>  
  
 <span data-ttu-id="be952-126">**Password**</span><span class="sxs-lookup"><span data-stu-id="be952-126">**Password**</span></span>  
 <span data-ttu-id="be952-127">Digitare la password dell'account.</span><span class="sxs-lookup"><span data-stu-id="be952-127">Type the password of the account.</span></span>  
  
 <span data-ttu-id="be952-128">**Conferma password**</span><span class="sxs-lookup"><span data-stu-id="be952-128">**Confirm password**</span></span>  
 <span data-ttu-id="be952-129">Digitare nuovamente la password dell'account.</span><span class="sxs-lookup"><span data-stu-id="be952-129">Type the password of the account again.</span></span>  
  
 <span data-ttu-id="be952-130">**Inizia**</span><span class="sxs-lookup"><span data-stu-id="be952-130">**Start**</span></span>  
 <span data-ttu-id="be952-131">Avviare il servizio.</span><span class="sxs-lookup"><span data-stu-id="be952-131">Start the service.</span></span>  
  
 <span data-ttu-id="be952-132">**Stop**</span><span class="sxs-lookup"><span data-stu-id="be952-132">**Stop**</span></span>  
 <span data-ttu-id="be952-133">Consente di arrestare il servizio.</span><span class="sxs-lookup"><span data-stu-id="be952-133">Stop the service.</span></span>  
  
 <span data-ttu-id="be952-134">**Sospendi**</span><span class="sxs-lookup"><span data-stu-id="be952-134">**Pause**</span></span>  
 <span data-ttu-id="be952-135">Consente di sospendere il servizio.</span><span class="sxs-lookup"><span data-stu-id="be952-135">Pause the service.</span></span>  
  
 <span data-ttu-id="be952-136">**Riprendi**</span><span class="sxs-lookup"><span data-stu-id="be952-136">**Resume**</span></span>  
 <span data-ttu-id="be952-137">Consente di riprendere un servizio sospeso.</span><span class="sxs-lookup"><span data-stu-id="be952-137">Resume a paused service.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="be952-138">Per impostazione predefinita, solo i membri del gruppo di amministratori locale possono avviare, arrestare, mettere in pausa, riprendere o riavviare un servizio.</span><span class="sxs-lookup"><span data-stu-id="be952-138">By default, only members of the local administrators group can start, stop, pause, resume or restart a service.</span></span> <span data-ttu-id="be952-139">Per concedere a utenti non amministratori la possibilità di gestire servizi, vedere [Concedere agli utenti i privilegi per gestire i servizi in Windows Server 2003](https://support.microsoft.com/kb/325349).</span><span class="sxs-lookup"><span data-stu-id="be952-139">To grant non-administrators the ability to manage services, see [How to grant users rights to manage services in Windows Server 2003](https://support.microsoft.com/kb/325349).</span></span> <span data-ttu-id="be952-140">Il processo è analogo ad altre versioni di Windows.</span><span class="sxs-lookup"><span data-stu-id="be952-140">(The process is similar on other versions of Windows.)</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="be952-141">Quando si avvia [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], un errore WMI contenente la frase "non implementato [0x80004001]" può indicare che [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] non è installato nel computer di destinazione.</span><span class="sxs-lookup"><span data-stu-id="be952-141">When starting [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], a WMI error containing the phrase "not implemented [0x80004001]" may indicate that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is not installed on the target computer.</span></span>  
  
  
