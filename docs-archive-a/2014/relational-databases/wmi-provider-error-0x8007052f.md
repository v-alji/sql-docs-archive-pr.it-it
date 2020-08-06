---
title: Errore WMI 0x8007052f | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- 0x8007052f (WMI error)
ms.assetid: a33f12bd-15c4-42a8-b343-de44c3e87729
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: d6e857e0ccaad9b6f34bbdc9b88aea2e6d7291d8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726796"
---
# <a name="wmi-error-0x8007052f"></a><span data-ttu-id="5508b-102">Errore WMI 0x8007052f</span><span class="sxs-lookup"><span data-stu-id="5508b-102">WMI Error 0x8007052f</span></span>
    
## <a name="details"></a><span data-ttu-id="5508b-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="5508b-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5508b-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="5508b-104">Product Name</span></span>|<span data-ttu-id="5508b-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="5508b-105">SQL Server</span></span>|  
|<span data-ttu-id="5508b-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="5508b-106">Event ID</span></span>|<span data-ttu-id="5508b-107">0x8007052f</span><span class="sxs-lookup"><span data-stu-id="5508b-107">0x8007052f</span></span>|  
|<span data-ttu-id="5508b-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="5508b-108">Event Source</span></span>|<span data-ttu-id="5508b-109">Errore del provider WMI</span><span class="sxs-lookup"><span data-stu-id="5508b-109">WMI Provider Error</span></span>|  
|<span data-ttu-id="5508b-110">Componente</span><span class="sxs-lookup"><span data-stu-id="5508b-110">Component</span></span>|<span data-ttu-id="5508b-111">Gestione configurazione SQL Server</span><span class="sxs-lookup"><span data-stu-id="5508b-111">SQL Server Configuration Manager</span></span>|  
|<span data-ttu-id="5508b-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="5508b-112">Symbolic Name</span></span>|<span data-ttu-id="5508b-113">ND</span><span class="sxs-lookup"><span data-stu-id="5508b-113">NA</span></span>|  
|<span data-ttu-id="5508b-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="5508b-114">Message Text</span></span>|<span data-ttu-id="5508b-115">Errore durante l'accesso: restrizione sull'account utente.</span><span class="sxs-lookup"><span data-stu-id="5508b-115">Logon failure: user account restriction.</span></span> <span data-ttu-id="5508b-116">Le possibili cause potrebbero essere: campo della password vuoto non consentito, restrizioni sugli orari di accesso o applicazione di restrizioni di criteri.</span><span class="sxs-lookup"><span data-stu-id="5508b-116">Possible reasons are blank passwords not allowed, login hour restrictions, or a policy restriction has been enforced.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="5508b-117">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="5508b-117">Explanation</span></span>  
 <span data-ttu-id="5508b-118">Questo errore può verificarsi se si utilizza Gestione configurazione [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] per passare agli account predefiniti (Servizio di rete, Servizio locale o Sistema locale) quando [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] è in esecuzione in un cluster o un controller di dominio di Windows Server.</span><span class="sxs-lookup"><span data-stu-id="5508b-118">This error can occur when using [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Configuration Manager to switch to the built-in accounts (Network Service, Local Service, or Local System) when [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] is running on a Windows Server Cluster or Windows Server Domain Controller.</span></span> <span data-ttu-id="5508b-119">Non eseguire i servizi con account predefiniti in un cluster o un controller di dominio di Windows Server 2003.</span><span class="sxs-lookup"><span data-stu-id="5508b-119">Do not run services under built-in accounts on a Windows Server Cluster or Windows Server Domain Controller.</span></span> <span data-ttu-id="5508b-120">Per informazioni sugli account di servizio, vedere l'argomento "Impostazione di account di servizio Windows" nella documentazione online di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5508b-120">For recommendations on service accounts, see the topic Setting Up Windows Service Accounts in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="5508b-121">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="5508b-121">User Action</span></span>  
 <span data-ttu-id="5508b-122">Configurare [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] affinché utilizzi un account di dominio.</span><span class="sxs-lookup"><span data-stu-id="5508b-122">Configure [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] to use a domain account.</span></span>  
  
  
