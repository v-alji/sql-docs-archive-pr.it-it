---
title: Proprietà NS $ &lt; nome servizio &gt; (scheda accesso) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: 5e6816ec-d4c5-4429-8033-b97427584890
author: stevestein
ms.author: sstein
ms.openlocfilehash: b175895f2385717a67642a41a44dc0d47a1d8d92
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722112"
---
# <a name="nsltservice-namegt-properties-log-on-tab"></a><span data-ttu-id="27e54-102">Proprietà NS$&lt;nome servizio&gt; (scheda Accesso)</span><span class="sxs-lookup"><span data-stu-id="27e54-102">NS$&lt;service name&gt; Properties (Log On Tab)</span></span>
  <span data-ttu-id="27e54-103">Utilizzare la scheda **Accesso** della finestra di dialogo **Proprietà - Notification Services** per specificare l'account utilizzato dal servizio [!INCLUDE[ssNS](../../includes/ssns-md.md)] e avviare e arrestare il servizio.</span><span class="sxs-lookup"><span data-stu-id="27e54-103">Use the **Log On** tab of the **Notification Services Properties** dialog box to specify the account used by the [!INCLUDE[ssNS](../../includes/ssns-md.md)] service, and to start and stop the service.</span></span>  
  
## <a name="options"></a><span data-ttu-id="27e54-104">Opzioni</span><span class="sxs-lookup"><span data-stu-id="27e54-104">Options</span></span>  
 <span data-ttu-id="27e54-105">**Account di sistema locale**</span><span class="sxs-lookup"><span data-stu-id="27e54-105">**Local System account**</span></span>  
 <span data-ttu-id="27e54-106">Specificare un account di sistema locale che non richiede una password.</span><span class="sxs-lookup"><span data-stu-id="27e54-106">Specify a local system account, which does not require a password.</span></span> <span data-ttu-id="27e54-107">Tuttavia, a seconda dei privilegi concessi, l'account di sistema locale può impedire le interazioni tra il servizio e gli altri server.</span><span class="sxs-lookup"><span data-stu-id="27e54-107">However, the local system account may restrict the service from interacting with other servers, depending on the privileges granted to the account.</span></span>  
  
 <span data-ttu-id="27e54-108">**Account seguente**</span><span class="sxs-lookup"><span data-stu-id="27e54-108">**This account**</span></span>  
 <span data-ttu-id="27e54-109">Specificare un account utente locale o di dominio che utilizza l'autenticazione di [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="27e54-109">Specify a local or domain user account that uses [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Authentication.</span></span> [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="27e54-110">consiglia di utilizzare un account utente di dominio con diritti minimi.</span><span class="sxs-lookup"><span data-stu-id="27e54-110">recommends using a domain user account with minimal rights for services.</span></span> <span data-ttu-id="27e54-111">Per ulteriori informazioni sulla selezione di un account, cercare l'argomento "Impostazione di account di Windows per i servizi" nella documentazione online.</span><span class="sxs-lookup"><span data-stu-id="27e54-111">For information about selecting an account, search Books Online for the topic, "Setting Up Windows Service Accounts."</span></span>  
  
 <span data-ttu-id="27e54-112">**Account Name** (Nome account)</span><span class="sxs-lookup"><span data-stu-id="27e54-112">**Account Name**</span></span>  
 <span data-ttu-id="27e54-113">Specificare il nome dell'account utente locale o di dominio.</span><span class="sxs-lookup"><span data-stu-id="27e54-113">Specify the local or domain user account name.</span></span>  
  
 <span data-ttu-id="27e54-114">**Password**</span><span class="sxs-lookup"><span data-stu-id="27e54-114">**Password**</span></span>  
 <span data-ttu-id="27e54-115">Digitare la password dell'account.</span><span class="sxs-lookup"><span data-stu-id="27e54-115">Type the password of the account.</span></span>  
  
 <span data-ttu-id="27e54-116">**Conferma password**</span><span class="sxs-lookup"><span data-stu-id="27e54-116">**Confirm password**</span></span>  
 <span data-ttu-id="27e54-117">Digitare nuovamente la password dell'account.</span><span class="sxs-lookup"><span data-stu-id="27e54-117">Type the password of the account again.</span></span>  
  
 <span data-ttu-id="27e54-118">**Inizia**</span><span class="sxs-lookup"><span data-stu-id="27e54-118">**Start**</span></span>  
 <span data-ttu-id="27e54-119">Avviare il servizio.</span><span class="sxs-lookup"><span data-stu-id="27e54-119">Start the service.</span></span>  
  
 <span data-ttu-id="27e54-120">**Stop**</span><span class="sxs-lookup"><span data-stu-id="27e54-120">**Stop**</span></span>  
 <span data-ttu-id="27e54-121">Consente di arrestare il servizio.</span><span class="sxs-lookup"><span data-stu-id="27e54-121">Stop the service.</span></span>  
  
 <span data-ttu-id="27e54-122">**Sospendi**</span><span class="sxs-lookup"><span data-stu-id="27e54-122">**Pause**</span></span>  
 <span data-ttu-id="27e54-123">Consente di sospendere il servizio.</span><span class="sxs-lookup"><span data-stu-id="27e54-123">Pause the service.</span></span>  
  
 <span data-ttu-id="27e54-124">**Riprendi**</span><span class="sxs-lookup"><span data-stu-id="27e54-124">**Resume**</span></span>  
 <span data-ttu-id="27e54-125">Consente di riprendere un servizio sospeso.</span><span class="sxs-lookup"><span data-stu-id="27e54-125">Resume a paused service.</span></span>  
  
  
