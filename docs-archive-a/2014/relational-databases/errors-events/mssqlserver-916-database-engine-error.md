---
title: MSSQLSERVER_916 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 916 (Database Engine error)
ms.assetid: 73eb6581-99fe-49a5-9b42-e239d7ffe27f
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ee67c1e2f67c3c7903c67082ec3793d9d9820061
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627745"
---
# <a name="mssqlserver_916"></a><span data-ttu-id="417fa-102">MSSQLSERVER_916</span><span class="sxs-lookup"><span data-stu-id="417fa-102">MSSQLSERVER_916</span></span>
    
## <a name="details"></a><span data-ttu-id="417fa-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="417fa-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="417fa-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="417fa-104">Product Name</span></span>|<span data-ttu-id="417fa-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="417fa-105">SQL Server</span></span>|  
|<span data-ttu-id="417fa-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="417fa-106">Event ID</span></span>|<span data-ttu-id="417fa-107">916</span><span class="sxs-lookup"><span data-stu-id="417fa-107">916</span></span>|  
|<span data-ttu-id="417fa-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="417fa-108">Event Source</span></span>|<span data-ttu-id="417fa-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="417fa-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="417fa-110">Componente</span><span class="sxs-lookup"><span data-stu-id="417fa-110">Component</span></span>|<span data-ttu-id="417fa-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="417fa-111">SQLEngine</span></span>|  
|<span data-ttu-id="417fa-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="417fa-112">Symbolic Name</span></span>|<span data-ttu-id="417fa-113">NOTUSER</span><span class="sxs-lookup"><span data-stu-id="417fa-113">NOTUSER</span></span>|  
|<span data-ttu-id="417fa-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="417fa-114">Message Text</span></span>|<span data-ttu-id="417fa-115">L'entità server "%.\*ls" non è in grado di accedere al database "%.\*ls" nel contesto di sicurezza corrente.</span><span class="sxs-lookup"><span data-stu-id="417fa-115">The server principal "%.\*ls" is not able to access the database "%.\*ls" under the current security context.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="417fa-116">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="417fa-116">Explanation</span></span>  
 <span data-ttu-id="417fa-117">L'accesso non dispone delle autorizzazioni sufficienti per connettersi al database denominato.</span><span class="sxs-lookup"><span data-stu-id="417fa-117">The login does not have sufficient permissions to connect to the named database.</span></span> <span data-ttu-id="417fa-118">Gli account di accesso che possono connettersi a questa istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], ma che non dispongono di autorizzazioni specifiche in un database ricevono le autorizzazioni di utente guest.</span><span class="sxs-lookup"><span data-stu-id="417fa-118">Logins that can connect to this instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] but that do not have specific permissions in a database receive the permissions of the guest user.</span></span> <span data-ttu-id="417fa-119">Si tratta di una misura di sicurezza per impedire agli utenti di un database di connettersi ad altri database per cui non dispongono di privilegi.</span><span class="sxs-lookup"><span data-stu-id="417fa-119">This is a security measure to prevent users in one database from connecting to other databases where they do not have privileges.</span></span> <span data-ttu-id="417fa-120">È possibile ricevere questo messaggio di errore quando l'utente guest non dispone delle autorizzazioni CONNECT per il database denominato e la proprietà TRUSTWORTHY non è impostata.</span><span class="sxs-lookup"><span data-stu-id="417fa-120">This error message can occur when the guest user does not have CONNECT permission to the named database and the trustworthy property is not set.</span></span> <span data-ttu-id="417fa-121">È possibile ricevere questo messaggio di errore quando l'utente guest non dispone delle autorizzazioni CONNECT per il database denominato.</span><span class="sxs-lookup"><span data-stu-id="417fa-121">This error message can occur when the guest user does not have CONNECT permission to the named database.</span></span>  
  
 <span data-ttu-id="417fa-122">Quando l'autorizzazione CONNECT al database msdb viene negata o revocata, [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] può ricevere questo errore quando Esplora oggetti tenta di mostrare lo stato di gestione basata su criteri di ciascun database.</span><span class="sxs-lookup"><span data-stu-id="417fa-122">When CONNECT permission to the msdb database is denied or revoked, [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] can receive this error when Object Explorer tries to show the Policy Based Management status of each database.</span></span> <span data-ttu-id="417fa-123">Esplora oggetti usa le autorizzazioni dell'accesso corrente per cercare nel database msdb queste informazioni, operazione che causa l'errore.</span><span class="sxs-lookup"><span data-stu-id="417fa-123">Object Explorer uses the permissions of the current login to query the msdb database for this information, which causes the error.</span></span> <span data-ttu-id="417fa-124">Viene inoltre visualizzato il messaggio di errore seguente:</span><span class="sxs-lookup"><span data-stu-id="417fa-124">The following error message also occurs:</span></span>  
  
 <span data-ttu-id="417fa-125">Impossibile recuperare i dati per la richiesta specificata.</span><span class="sxs-lookup"><span data-stu-id="417fa-125">Failed to retrieve data for this request.</span></span> <span data-ttu-id="417fa-126">(Microsoft.SqlServer.Management.Sdk.Sfc)</span><span class="sxs-lookup"><span data-stu-id="417fa-126">(Microsoft.SqlServer.Management.Sdk.Sfc)</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="417fa-127">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="417fa-127">User Action</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="417fa-128">Prima di eludere questa misura di sicurezza, assicurarsi di sapere quali utenti sono autenticati in vari database.</span><span class="sxs-lookup"><span data-stu-id="417fa-128">Before circumventing this security measure be sure to have a clear understanding of users are authenticated in various databases.</span></span> <span data-ttu-id="417fa-129">I metodi seguenti consentono agli utenti che dispongono delle autorizzazioni per un database di connettersi ad altri database che potrebbero esporre i dati a utenti malintenzionati.</span><span class="sxs-lookup"><span data-stu-id="417fa-129">The following methods may allow users that have permissions in one database to connect to other databases which could expose data to a malicious user.</span></span> <span data-ttu-id="417fa-130">Quando i database indipendenti sono abilitati, i passaggi seguenti consentono ai proprietari di un database di concedere l'accesso all'altro database nell'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="417fa-130">When contained databases are enabled, the following steps can allow database owners in one database to grant access to other database on the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="417fa-131">È possibile connettersi al database in uno dei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="417fa-131">You can connect to the database in one of the following ways:</span></span>  
  
-   <span data-ttu-id="417fa-132">Concedere l'accesso specifico al database denominato.</span><span class="sxs-lookup"><span data-stu-id="417fa-132">Grant the specific login access to the named database.</span></span> <span data-ttu-id="417fa-133">Nell'esempio seguente viene concesso l'accesso `Adventure-Works\Larry` al database `msdb`.</span><span class="sxs-lookup"><span data-stu-id="417fa-133">The following example grants the login `Adventure-Works\Larry` access to the `msdb` database.</span></span>  
  
     <span data-ttu-id="417fa-134">USE msdb ;</span><span class="sxs-lookup"><span data-stu-id="417fa-134">USE msdb ;</span></span>  
  
     <span data-ttu-id="417fa-135">GO</span><span class="sxs-lookup"><span data-stu-id="417fa-135">GO</span></span>  
  
     <span data-ttu-id="417fa-136">GRANT CONNECT TO [Adventure-Works\Larry] ;</span><span class="sxs-lookup"><span data-stu-id="417fa-136">GRANT CONNECT TO [Adventure-Works\Larry] ;</span></span>  
  
-   <span data-ttu-id="417fa-137">Concedere l'autorizzazione CONNECT al database denominato nel messaggio di errore per l'utente guest.</span><span class="sxs-lookup"><span data-stu-id="417fa-137">Grant the CONNECT permission to the database named in the error message for the guest user.</span></span> <span data-ttu-id="417fa-138">Nell'esempio seguente viene concessa l'autorizzazione `CONNECT` per il database `msdb` per l'utente `guest`.</span><span class="sxs-lookup"><span data-stu-id="417fa-138">The following example grants the `CONNECT` permission to the `msdb` database for the user `guest`.</span></span>  
  
     <span data-ttu-id="417fa-139">USE msdb ;</span><span class="sxs-lookup"><span data-stu-id="417fa-139">USE msdb ;</span></span>  
  
     <span data-ttu-id="417fa-140">GO</span><span class="sxs-lookup"><span data-stu-id="417fa-140">GO</span></span>  
  
     <span data-ttu-id="417fa-141">GRANT CONNECT TO guest ;</span><span class="sxs-lookup"><span data-stu-id="417fa-141">GRANT CONNECT TO guest ;</span></span>  
  
-   <span data-ttu-id="417fa-142">Abilitare la proprietà TRUSTWORTHY per il database che ha autenticato l'utente.</span><span class="sxs-lookup"><span data-stu-id="417fa-142">Enable the TRUSTWORTHY property on the database that has authenticated the user.</span></span>  
  
     `ALTER DATABASE AdventureWorks SET TRUSTWORTHY ON;`  
  
  
