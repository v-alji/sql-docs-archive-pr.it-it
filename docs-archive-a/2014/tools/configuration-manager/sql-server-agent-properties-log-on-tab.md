---
title: Proprietà - SQL Server Agent (scheda Accesso) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: 01fc6329-5d6b-4186-9565-395f375477bb
author: stevestein
ms.author: sstein
ms.openlocfilehash: cd899e8824adacd07fa1d8d7d51b2143d10cadd4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628040"
---
# <a name="sql-server-agent-properties-log-on-tab"></a><span data-ttu-id="cccf3-102">Proprietà - SQL Server Agent (scheda Accesso)</span><span class="sxs-lookup"><span data-stu-id="cccf3-102">SQL Server Agent Properties (Log On Tab)</span></span>
  <span data-ttu-id="cccf3-103">Utilizzare la scheda **Accesso** della finestra di dialogo **Proprietà SQL Server Agent** per specificare l'account utilizzato dal servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent e per avviare e arrestare il servizio.</span><span class="sxs-lookup"><span data-stu-id="cccf3-103">Use the **Log On** tab of the **SQL Server Agent Properties** dialog box to specify the account used by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service, and to start and stop the service.</span></span> <span data-ttu-id="cccf3-104">La modifica della password di un account diventa effettiva immediatamente, senza dover riavviare il servizio.</span><span class="sxs-lookup"><span data-stu-id="cccf3-104">Changing the password of an account takes effect immediately without restarting the service.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cccf3-105">Quando si modifica il nome account utilizzato da un servizio in un'istanza cluster, il nuovo account deve essere membro del gruppo di dominio specificato durante l’installazione per il servizio in corso di modifica oppure è necessario disporre dell’autorizzazione per aggiungere membri a tale gruppo.</span><span class="sxs-lookup"><span data-stu-id="cccf3-105">When changing the account name used by a service on a clustered instance, the new account must be a member of the domain group specified during setup for the service being changed, or you must have permission to add members to that group.</span></span> <span data-ttu-id="cccf3-106">Se non si dispone dell’autorizzazione per modificare l'appartenenza al gruppo, contattare l’amministratore di dominio.</span><span class="sxs-lookup"><span data-stu-id="cccf3-106">If you do not have permission to modify group membership, contact the domain administrator.</span></span>  
  
## <a name="options"></a><span data-ttu-id="cccf3-107">Opzioni</span><span class="sxs-lookup"><span data-stu-id="cccf3-107">Options</span></span>  
 <span data-ttu-id="cccf3-108">**Account di sistema locale**</span><span class="sxs-lookup"><span data-stu-id="cccf3-108">**Local System account**</span></span>  
 <span data-ttu-id="cccf3-109">Specificare un account di sistema locale che non richiede una password.</span><span class="sxs-lookup"><span data-stu-id="cccf3-109">Specify a local system account, which does not require a password.</span></span> <span data-ttu-id="cccf3-110">Tuttavia, a seconda dei privilegi concessi, l'account di sistema locale può impedire le interazioni tra il servizio e gli altri server.</span><span class="sxs-lookup"><span data-stu-id="cccf3-110">However, the local system account may restrict the service from interacting with other servers, depending on the privileges granted to the account.</span></span>  
  
 <span data-ttu-id="cccf3-111">**Account seguente**</span><span class="sxs-lookup"><span data-stu-id="cccf3-111">**This account**</span></span>  
 <span data-ttu-id="cccf3-112">Specificare un account utente locale o di dominio che utilizza l’autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="cccf3-112">Specify a local or domain user account that uses Windows Authentication.</span></span> [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="cccf3-113">consiglia di utilizzare un account utente di dominio con diritti minimi.</span><span class="sxs-lookup"><span data-stu-id="cccf3-113">recommends using a domain user account with minimal rights for services.</span></span> <span data-ttu-id="cccf3-114">Per ulteriori informazioni sulla selezione di un account, vedere l'argomento "Impostazione di account di Windows per i servizi" nella documentazione online.</span><span class="sxs-lookup"><span data-stu-id="cccf3-114">For information about selecting an account, search Books Online for "Setting Up Windows Service Accounts."</span></span>  
  
 <span data-ttu-id="cccf3-115">**Account Name** (Nome account)</span><span class="sxs-lookup"><span data-stu-id="cccf3-115">**Account Name**</span></span>  
 <span data-ttu-id="cccf3-116">Specificare il nome dell'account utente locale o di dominio.</span><span class="sxs-lookup"><span data-stu-id="cccf3-116">Specify the local or domain user account name.</span></span>  
  
 <span data-ttu-id="cccf3-117">**Password**</span><span class="sxs-lookup"><span data-stu-id="cccf3-117">**Password**</span></span>  
 <span data-ttu-id="cccf3-118">Digitare la password dell'account.</span><span class="sxs-lookup"><span data-stu-id="cccf3-118">Type the password of the account.</span></span>  
  
 <span data-ttu-id="cccf3-119">**Conferma password**</span><span class="sxs-lookup"><span data-stu-id="cccf3-119">**Confirm password**</span></span>  
 <span data-ttu-id="cccf3-120">Digitare nuovamente la password dell'account.</span><span class="sxs-lookup"><span data-stu-id="cccf3-120">Type the password of the account again.</span></span>  
  
 <span data-ttu-id="cccf3-121">**Inizia**</span><span class="sxs-lookup"><span data-stu-id="cccf3-121">**Start**</span></span>  
 <span data-ttu-id="cccf3-122">Avviare il servizio.</span><span class="sxs-lookup"><span data-stu-id="cccf3-122">Start the service.</span></span>  
  
 <span data-ttu-id="cccf3-123">**Stop**</span><span class="sxs-lookup"><span data-stu-id="cccf3-123">**Stop**</span></span>  
 <span data-ttu-id="cccf3-124">Consente di arrestare il servizio.</span><span class="sxs-lookup"><span data-stu-id="cccf3-124">Stop the service.</span></span>  
  
 <span data-ttu-id="cccf3-125">**Sospendi**</span><span class="sxs-lookup"><span data-stu-id="cccf3-125">**Pause**</span></span>  
 <span data-ttu-id="cccf3-126">Consente di sospendere il servizio.</span><span class="sxs-lookup"><span data-stu-id="cccf3-126">Pause the service.</span></span>  
  
 <span data-ttu-id="cccf3-127">**Riprendi**</span><span class="sxs-lookup"><span data-stu-id="cccf3-127">**Resume**</span></span>  
 <span data-ttu-id="cccf3-128">Consente di riprendere un servizio sospeso.</span><span class="sxs-lookup"><span data-stu-id="cccf3-128">Resume a paused service.</span></span>  
  
  
