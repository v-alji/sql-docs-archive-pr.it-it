---
title: MSSQLSERVER_18452 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 18456 (Database Engine error)
- 18452 (Database Engine error)
ms.assetid: 21da332c-e81d-4dee-a9d2-95598911b3be
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5786d5de4748f6bbf59d2bd4acecd7ca77977f11
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629852"
---
# <a name="mssqlserver_18452"></a><span data-ttu-id="3c523-102">MSSQLSERVER_18452</span><span class="sxs-lookup"><span data-stu-id="3c523-102">MSSQLSERVER_18452</span></span>
    
## <a name="details"></a><span data-ttu-id="3c523-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="3c523-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3c523-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="3c523-104">Product Name</span></span>|<span data-ttu-id="3c523-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="3c523-105">SQL Server</span></span>|  
|<span data-ttu-id="3c523-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="3c523-106">Event ID</span></span>|<span data-ttu-id="3c523-107">18452</span><span class="sxs-lookup"><span data-stu-id="3c523-107">18452</span></span>|  
|<span data-ttu-id="3c523-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="3c523-108">Event Source</span></span>|<span data-ttu-id="3c523-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="3c523-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="3c523-110">Componente</span><span class="sxs-lookup"><span data-stu-id="3c523-110">Component</span></span>|<span data-ttu-id="3c523-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="3c523-111">SQLEngine</span></span>|  
|<span data-ttu-id="3c523-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="3c523-112">Symbolic Name</span></span>|<span data-ttu-id="3c523-113">LOGON_INVALID_CONNECT</span><span class="sxs-lookup"><span data-stu-id="3c523-113">LOGON_INVALID_CONNECT</span></span>|  
|<span data-ttu-id="3c523-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="3c523-114">Message Text</span></span>|<span data-ttu-id="3c523-115">Accesso non riuscito per l'utente '%.\*ls'.</span><span class="sxs-lookup"><span data-stu-id="3c523-115">Login failed for user '%.\*ls'.</span></span> <span data-ttu-id="3c523-116">L'accesso è un accesso di SQL Server e non può essere usato con l'autenticazione di Windows %.\*ls</span><span class="sxs-lookup"><span data-stu-id="3c523-116">The login is a SQL Server login and cannot be used with Windows Authentication.%.\*ls</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="3c523-117">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="3c523-117">Explanation</span></span>  
 <span data-ttu-id="3c523-118">L'utente ha tentato di effettuare l'accesso con credenziali che non è possibile convalidare.</span><span class="sxs-lookup"><span data-stu-id="3c523-118">The user attempted to login with credentials that cannot be validated.</span></span> <span data-ttu-id="3c523-119">Le cause possibili sono:</span><span class="sxs-lookup"><span data-stu-id="3c523-119">Possible causes are:</span></span>  
  
-   <span data-ttu-id="3c523-120">L'account di accesso può essere un account di accesso di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ma il server accetta solo l'autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="3c523-120">The login may be a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login but the server only accepts Windows Authentication.</span></span>  
  
-   <span data-ttu-id="3c523-121">Si sta tentando di effettuare la connessione mediante l'autenticazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ma l'account di accesso utilizzato non esiste in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3c523-121">You are trying to connect using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication but the login used does not exist on [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="3c523-122">L'account di accesso può utilizzare l'autenticazione di Windows ma è un'entità di Windows non riconosciuta.</span><span class="sxs-lookup"><span data-stu-id="3c523-122">The login may use Windows Authentication but the login is an unrecognized Windows principal.</span></span> <span data-ttu-id="3c523-123">Un'entità di Windows non riconosciuta indica che l'account di accesso non può essere verificato da Windows.</span><span class="sxs-lookup"><span data-stu-id="3c523-123">An unrecognized Windows principal means that the login cannot be verified by Windows.</span></span> <span data-ttu-id="3c523-124">La causa potrebbe essere la provenienza dell'account di accesso di Windows da un dominio non attendibile.</span><span class="sxs-lookup"><span data-stu-id="3c523-124">This could be because the Windows login is from an untrusted domain.</span></span>  
  
 <span data-ttu-id="3c523-125">Problemi simili possono provocare l'errore 18456 meno specifico.</span><span class="sxs-lookup"><span data-stu-id="3c523-125">Similar problems can cause the less-specific error 18456.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="3c523-126">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="3c523-126">User Action</span></span>  
 <span data-ttu-id="3c523-127">Se si sta tentando di effettuare la connessione mediante l'autenticazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], verificare che [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sia configurato in modalità Autenticazione mista.</span><span class="sxs-lookup"><span data-stu-id="3c523-127">If you are trying to connect using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication, verify that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is configured in Mixed Authentication Mode.</span></span>  
  
 <span data-ttu-id="3c523-128">Se si sta tentando di effettuare la connessione mediante l'autenticazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , verificare l'esistenza dell'account di accesso a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3c523-128">If you are trying to connect using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication, verify that the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login exists.</span></span>  
  
 <span data-ttu-id="3c523-129">Se si sta tentando di effettuare la connessione mediante l'autenticazione di Windows, verificare di essere connessi al dominio corretto.</span><span class="sxs-lookup"><span data-stu-id="3c523-129">If you are trying to connect using Windows Authentication, verify that you are properly logged into the correct domain.</span></span>  
  
  
