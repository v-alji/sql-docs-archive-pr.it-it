---
title: Servizio sconosciuto (scheda accesso) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: e9b35cb5-d8ae-42ea-b59e-deedc99c4823
author: stevestein
ms.author: sstein
ms.openlocfilehash: 0bda49cd95475d4f922f41ebe1701a814c3f60fc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625123"
---
# <a name="unknown-service-log-on-tab"></a><span data-ttu-id="83b18-102">Servizio sconosciuto (scheda Accesso)</span><span class="sxs-lookup"><span data-stu-id="83b18-102">Unknown Service (Log On Tab)</span></span>
  [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="83b18-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] non riesce a identificare il servizio.</span><span class="sxs-lookup"><span data-stu-id="83b18-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager is unable to identify this service.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="83b18-104">riceve informazioni sul servizio dal provider WMI del computer in cui il servizio è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="83b18-104">Configuration Manager receives service information from the WMI provider on the computer running the service.</span></span> <span data-ttu-id="83b18-105">Si è verificato un errore durante la lettura delle proprietà del servizio oppure tali proprietà non sono complete.</span><span class="sxs-lookup"><span data-stu-id="83b18-105">Either there was an error while reading the service properties, or the service properties are not complete.</span></span> <span data-ttu-id="83b18-106">Per risolvere questo problema, provare a chiudere e riaprire Gestione configurazione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] oppure controllare il provider WMI nel computer in cui viene eseguito il servizio.</span><span class="sxs-lookup"><span data-stu-id="83b18-106">To resolve the problem, try closing and reopening [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, or check the WMI provider on the computer running the service.</span></span>  
  
 <span data-ttu-id="83b18-107">Il provider WMI è un componente di Windows.</span><span class="sxs-lookup"><span data-stu-id="83b18-107">The WMI provider is a Windows component.</span></span> <span data-ttu-id="83b18-108">Per informazioni su come controllare le autorizzazioni per il provider WMI, vedere "Procedura: Configurazione di WMI per mostrare lo stato del server in Strumenti SQL Server" nella documentazione online di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="83b18-108">For information on how to check permissions on the WMI provider, see "How to: Configure WMI to Show Server Status in SQL Server Tools" in SQL Server Books Online.</span></span>  
  
 <span data-ttu-id="83b18-109">Se si ritiene che il servizio visualizzato sia corretto, utilizzare la scheda **Accesso** della finestra di dialogo **Proprietà - Servizio sconosciuto** per specificare l'account utilizzato dal servizio e per avviare e arrestare il servizio.</span><span class="sxs-lookup"><span data-stu-id="83b18-109">If you believe you are viewing the correct service, use the **Log On** tab of the **Unknown Service Properties** dialog box to specify the account used by this service, and to start and stop the service.</span></span>  
  
## <a name="options"></a><span data-ttu-id="83b18-110">Opzioni</span><span class="sxs-lookup"><span data-stu-id="83b18-110">Options</span></span>  
 <span data-ttu-id="83b18-111">**Account di sistema locale**</span><span class="sxs-lookup"><span data-stu-id="83b18-111">**Local System account**</span></span>  
 <span data-ttu-id="83b18-112">Specificare un account di sistema locale che non richiede una password.</span><span class="sxs-lookup"><span data-stu-id="83b18-112">Specify a local system account, which does not require a password.</span></span> <span data-ttu-id="83b18-113">Tuttavia, a seconda dei privilegi concessi, l'account di sistema locale può impedire le interazioni tra il servizio e gli altri server.</span><span class="sxs-lookup"><span data-stu-id="83b18-113">However, the local system account may prevent the service from interacting with other servers, depending on the privileges granted to the account.</span></span>  
  
 <span data-ttu-id="83b18-114">**Account seguente**</span><span class="sxs-lookup"><span data-stu-id="83b18-114">**This account**</span></span>  
 <span data-ttu-id="83b18-115">Specificare un account utente locale o di dominio che utilizza l’autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="83b18-115">Specify a local or domain user account that uses Windows Authentication.</span></span> <span data-ttu-id="83b18-116">È consigliabile usare un account utente di dominio con diritti minimi per i servizi.</span><span class="sxs-lookup"><span data-stu-id="83b18-116">We recommend using a domain user account with minimal rights for services.</span></span> <span data-ttu-id="83b18-117">Per ulteriori informazioni sulla selezione di un account, vedere "Impostazione di account di servizio Windows" nella documentazione online di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="83b18-117">For information about selecting an account, "Setting Up Windows Service Accounts" in SQL Server Books Online.</span></span>  
  
 <span data-ttu-id="83b18-118">**Account Name** (Nome account)</span><span class="sxs-lookup"><span data-stu-id="83b18-118">**Account Name**</span></span>  
 <span data-ttu-id="83b18-119">Specificare il nome dell'account utente locale o di dominio.</span><span class="sxs-lookup"><span data-stu-id="83b18-119">Specify the local or domain user account name.</span></span>  
  
 <span data-ttu-id="83b18-120">**Password**</span><span class="sxs-lookup"><span data-stu-id="83b18-120">**Password**</span></span>  
 <span data-ttu-id="83b18-121">Digitare la password dell'account.</span><span class="sxs-lookup"><span data-stu-id="83b18-121">Type the password of the account.</span></span>  
  
 <span data-ttu-id="83b18-122">**Conferma password**</span><span class="sxs-lookup"><span data-stu-id="83b18-122">**Confirm password**</span></span>  
 <span data-ttu-id="83b18-123">Digitare nuovamente la password dell'account.</span><span class="sxs-lookup"><span data-stu-id="83b18-123">Type the password of the account again.</span></span>  
  
 <span data-ttu-id="83b18-124">**Inizia**</span><span class="sxs-lookup"><span data-stu-id="83b18-124">**Start**</span></span>  
 <span data-ttu-id="83b18-125">Avviare il servizio.</span><span class="sxs-lookup"><span data-stu-id="83b18-125">Start the service.</span></span>  
  
 <span data-ttu-id="83b18-126">**Stop**</span><span class="sxs-lookup"><span data-stu-id="83b18-126">**Stop**</span></span>  
 <span data-ttu-id="83b18-127">Consente di arrestare il servizio.</span><span class="sxs-lookup"><span data-stu-id="83b18-127">Stop the service.</span></span>  
  
 <span data-ttu-id="83b18-128">**Sospendi**</span><span class="sxs-lookup"><span data-stu-id="83b18-128">**Pause**</span></span>  
 <span data-ttu-id="83b18-129">Consente di sospendere il servizio.</span><span class="sxs-lookup"><span data-stu-id="83b18-129">Pause the service.</span></span>  
  
 <span data-ttu-id="83b18-130">**Riprendi**</span><span class="sxs-lookup"><span data-stu-id="83b18-130">**Resume**</span></span>  
 <span data-ttu-id="83b18-131">Consente di riprendere un servizio sospeso.</span><span class="sxs-lookup"><span data-stu-id="83b18-131">Resume a paused service.</span></span>  
  
  
