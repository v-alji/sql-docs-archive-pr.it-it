---
title: Proprietà - Analysis Server (scheda Accesso) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: a82e0c98-efaa-4b0b-9582-3c879ee42444
author: stevestein
ms.author: sstein
ms.openlocfilehash: 8db5576e48e7f12ef1733175875d2cd065e376fc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725195"
---
# <a name="analysis-server-properties-log-on-tab"></a><span data-ttu-id="ac0a6-102">Proprietà - Analysis Server (scheda Accesso)</span><span class="sxs-lookup"><span data-stu-id="ac0a6-102">Analysis Server Properties (Log On Tab)</span></span>
  <span data-ttu-id="ac0a6-103">Utilizzare la scheda **Accesso** della finestra di dialogo **Proprietà - Analysis Server** per specificare l'account utilizzato dal servizio [!INCLUDE[ssAS](../../includes/ssas-md.md)] e avviare e arrestare il servizio.</span><span class="sxs-lookup"><span data-stu-id="ac0a6-103">Use the **Log On** tab of the **Analysis Server Properties** dialog box to specify the account used by the [!INCLUDE[ssAS](../../includes/ssas-md.md)] service, and to start and stop the service.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ac0a6-104">Quando si modifica il **Nome account** utilizzato da un servizio in un'istanza cluster, il nuovo account deve essere membro del gruppo di dominio specificato durante l'installazione per il servizio in corso di modifica oppure è necessario disporre dell'autorizzazione per aggiungere membri a tale gruppo.</span><span class="sxs-lookup"><span data-stu-id="ac0a6-104">When changing the **Account Name** used by a service on a clustered instance, the new account must either be a member of the domain group specified during setup for the service being changed, or you must have permission to add members to that group.</span></span> <span data-ttu-id="ac0a6-105">Se non si dispone dell’autorizzazione per modificare l'appartenenza al gruppo, contattare l’amministratore di dominio.</span><span class="sxs-lookup"><span data-stu-id="ac0a6-105">If you do not have permission to modify group membership, contact the domain administrator.</span></span>  
  
## <a name="options"></a><span data-ttu-id="ac0a6-106">Opzioni</span><span class="sxs-lookup"><span data-stu-id="ac0a6-106">Options</span></span>  
 <span data-ttu-id="ac0a6-107">**Account di sistema locale**</span><span class="sxs-lookup"><span data-stu-id="ac0a6-107">**Local System account**</span></span>  
 <span data-ttu-id="ac0a6-108">Specificare un account di sistema locale che non richiede una password.</span><span class="sxs-lookup"><span data-stu-id="ac0a6-108">Specify a local system account, which does not require a password.</span></span> <span data-ttu-id="ac0a6-109">Tuttavia, a seconda dei privilegi concessi, l'account di sistema locale può impedire le interazioni tra il servizio e gli altri server.</span><span class="sxs-lookup"><span data-stu-id="ac0a6-109">However, the local system account may restrict the service from interacting with other servers, depending on the privileges granted to the account.</span></span>  
  
 <span data-ttu-id="ac0a6-110">**Account seguente**</span><span class="sxs-lookup"><span data-stu-id="ac0a6-110">**This account**</span></span>  
 <span data-ttu-id="ac0a6-111">Specificare un account utente locale o di dominio che utilizza l'autenticazione di [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="ac0a6-111">Specify a local or domain user account that uses [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Authentication.</span></span> [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="ac0a6-112">consiglia di utilizzare un account utente di dominio con diritti minimi.</span><span class="sxs-lookup"><span data-stu-id="ac0a6-112">recommends using a domain user account with minimal rights for services.</span></span> <span data-ttu-id="ac0a6-113">Per ulteriori informazioni sulla selezione di un account, cercare l'argomento "Impostazione di account di servizio Windows" nella documentazione online.</span><span class="sxs-lookup"><span data-stu-id="ac0a6-113">For information about selecting an account, search Books Online for the topic Setting Up Windows Service Accounts.</span></span>  
  
 <span data-ttu-id="ac0a6-114">**Account Name** (Nome account)</span><span class="sxs-lookup"><span data-stu-id="ac0a6-114">**Account Name**</span></span>  
 <span data-ttu-id="ac0a6-115">Specificare il nome dell'account utente locale o di dominio.</span><span class="sxs-lookup"><span data-stu-id="ac0a6-115">Specify the local or domain user account name.</span></span>  
  
 <span data-ttu-id="ac0a6-116">**Password**</span><span class="sxs-lookup"><span data-stu-id="ac0a6-116">**Password**</span></span>  
 <span data-ttu-id="ac0a6-117">Digitare la password dell'account.</span><span class="sxs-lookup"><span data-stu-id="ac0a6-117">Type the password of the account.</span></span>  
  
 <span data-ttu-id="ac0a6-118">**Conferma password**</span><span class="sxs-lookup"><span data-stu-id="ac0a6-118">**Confirm password**</span></span>  
 <span data-ttu-id="ac0a6-119">Digitare nuovamente la password dell'account.</span><span class="sxs-lookup"><span data-stu-id="ac0a6-119">Type the password of the account again.</span></span>  
  
 <span data-ttu-id="ac0a6-120">**Inizia**</span><span class="sxs-lookup"><span data-stu-id="ac0a6-120">**Start**</span></span>  
 <span data-ttu-id="ac0a6-121">Avviare il servizio.</span><span class="sxs-lookup"><span data-stu-id="ac0a6-121">Start the service.</span></span>  
  
 <span data-ttu-id="ac0a6-122">**Stop**</span><span class="sxs-lookup"><span data-stu-id="ac0a6-122">**Stop**</span></span>  
 <span data-ttu-id="ac0a6-123">Consente di arrestare il servizio.</span><span class="sxs-lookup"><span data-stu-id="ac0a6-123">Stop the service.</span></span>  
  
 <span data-ttu-id="ac0a6-124">**Sospendi**</span><span class="sxs-lookup"><span data-stu-id="ac0a6-124">**Pause**</span></span>  
 <span data-ttu-id="ac0a6-125">Consente di sospendere il servizio.</span><span class="sxs-lookup"><span data-stu-id="ac0a6-125">Pause the service.</span></span>  
  
 <span data-ttu-id="ac0a6-126">**Riprendi**</span><span class="sxs-lookup"><span data-stu-id="ac0a6-126">**Resume**</span></span>  
 <span data-ttu-id="ac0a6-127">Consente di riprendere un servizio sospeso.</span><span class="sxs-lookup"><span data-stu-id="ac0a6-127">Resume a paused service.</span></span>  
  
  
