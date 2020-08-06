---
title: Proprietà server (pagina Sicurezza) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
f1_keywords:
- sql12.swb.serverproperties.security.f1
ms.assetid: b8a131c7-e7bd-4203-bf26-234f1ebfe622
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5f45c0a04a0d7cc627901d8de24175f1d63a99fe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87638093"
---
# <a name="server-properties-security-page"></a><span data-ttu-id="50032-102">Proprietà server (pagina sicurezza)</span><span class="sxs-lookup"><span data-stu-id="50032-102">Server Properties (Security Page)</span></span>
  <span data-ttu-id="50032-103">Utilizzare questa pagina per visualizzare o modificare le opzioni di sicurezza del server.</span><span class="sxs-lookup"><span data-stu-id="50032-103">Use this page to view or modify your server security options.</span></span>  
  
## <a name="server-authentication"></a><span data-ttu-id="50032-104">Autenticazione del server</span><span class="sxs-lookup"><span data-stu-id="50032-104">Server Authentication</span></span>  
 <span data-ttu-id="50032-105">**Autenticazione di Windows**</span><span class="sxs-lookup"><span data-stu-id="50032-105">**Windows Authentication mode**</span></span>  
 <span data-ttu-id="50032-106">Consente di utilizzare l'autenticazione di Windows per convalidare i tentativi di connessione.</span><span class="sxs-lookup"><span data-stu-id="50032-106">Uses Windows Authentication to validate attempted connections.</span></span> <span data-ttu-id="50032-107">Se la password **sa** è vuota quando si modifica la modalità di sicurezza, all'utente viene chiesto di immettere una password **sa** .</span><span class="sxs-lookup"><span data-stu-id="50032-107">If the **sa** password is blank when the security mode is being changed, the user is prompted to enter an **sa** password.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="50032-108">L'autenticazione di Windows offre una sicurezza decisamente maggiore rispetto all'autenticazione di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="50032-108">Windows Authentication is much more secure than SQL Server Authentication.</span></span> <span data-ttu-id="50032-109">Se possibile, utilizzare l'autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="50032-109">When possible, you should use Windows Authentication.</span></span>  
  
 <span data-ttu-id="50032-110">**Autenticazione di SQL Server e di Windows**</span><span class="sxs-lookup"><span data-stu-id="50032-110">**SQL Server and Windows Authentication mode**</span></span>  
 <span data-ttu-id="50032-111">Consente di utilizzare una modalità di autenticazione mista per la verifica dei tentativi di connessione. È disponibile per motivi di compatibilità con le versioni precedenti di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="50032-111">Uses mixed mode authentication to verify attempted connections, for backward compatibility with earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="50032-112">Se la password **sa** è vuota quando si modifica la modalità di sicurezza, all'utente viene chiesto di immettere una password **sa** .</span><span class="sxs-lookup"><span data-stu-id="50032-112">If the **sa** password is blank when the security mode is being changed, the user is prompted to enter an **sa** password.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="50032-113">la modifica della configurazione di sicurezza richiede il riavvio del servizio.</span><span class="sxs-lookup"><span data-stu-id="50032-113">Changing the security configuration requires a restart of the service.</span></span> <span data-ttu-id="50032-114">Quando si passa dall'autenticazione server a SQL Server e all'autenticazione di Windows, l'account SA non viene abilitato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="50032-114">When changing the Server Authentication to SQL Server and Windows Authentication mode the SA account is not automatically enabled.</span></span> <span data-ttu-id="50032-115">Per usare l'account SA, eseguire [ALTER LOGIN](/sql/t-sql/statements/alter-login-transact-sql) con l'opzione ENABLE.</span><span class="sxs-lookup"><span data-stu-id="50032-115">To use the SA account, execute [ALTER LOGIN](/sql/t-sql/statements/alter-login-transact-sql) with the ENABLE option.</span></span>  
  
## <a name="login-auditing"></a><span data-ttu-id="50032-116">Controllo accessi</span><span class="sxs-lookup"><span data-stu-id="50032-116">Login Auditing</span></span>  
 <span data-ttu-id="50032-117">**Nessuno**</span><span class="sxs-lookup"><span data-stu-id="50032-117">**None**</span></span>  
 <span data-ttu-id="50032-118">Consente di disattivare il controllo degli accessi.</span><span class="sxs-lookup"><span data-stu-id="50032-118">Turns off login auditing.</span></span>  
  
 <span data-ttu-id="50032-119">**Solo accessi non riusciti**</span><span class="sxs-lookup"><span data-stu-id="50032-119">**Failed logins only**</span></span>  
 <span data-ttu-id="50032-120">Consente di controllare solo gli accessi non riusciti.</span><span class="sxs-lookup"><span data-stu-id="50032-120">Audits unsuccessful logins only.</span></span>  
  
 <span data-ttu-id="50032-121">**Solo accessi riusciti**</span><span class="sxs-lookup"><span data-stu-id="50032-121">**Successful logins only**</span></span>  
 <span data-ttu-id="50032-122">Consente di controllare solo gli accessi riusciti.</span><span class="sxs-lookup"><span data-stu-id="50032-122">Audits successful logins only.</span></span>  
  
 <span data-ttu-id="50032-123">**Accessi riusciti e non riusciti**</span><span class="sxs-lookup"><span data-stu-id="50032-123">**Both failed and successful logins**</span></span>  
 <span data-ttu-id="50032-124">Consente di controllare tutti i tentativi di accesso.</span><span class="sxs-lookup"><span data-stu-id="50032-124">Audits all login attempts.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="50032-125">la modifica del livello di controllo richiede il riavvio del server.</span><span class="sxs-lookup"><span data-stu-id="50032-125">Changing the audit level requires restarting the service.</span></span>  
  
## <a name="server-proxy-account"></a><span data-ttu-id="50032-126">Account proxy server</span><span class="sxs-lookup"><span data-stu-id="50032-126">Server Proxy Account</span></span>  
 <span data-ttu-id="50032-127">**Abilita account proxy server**</span><span class="sxs-lookup"><span data-stu-id="50032-127">**Enable server proxy account**</span></span>  
 <span data-ttu-id="50032-128">Abilita un account per l'uso da parte di **xp_cmdshell**.</span><span class="sxs-lookup"><span data-stu-id="50032-128">Enables an account for use by **xp_cmdshell**.</span></span> <span data-ttu-id="50032-129">Gli account proxy consentono la rappresentazione di account di accesso, ruoli del server e ruoli del database durante l'esecuzione di un comando del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="50032-129">Proxy accounts allow for the impersonation of logins, server roles, and database roles when an operating system command is being executed.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="50032-130">l'account di accesso utilizzato dall'account proxy server deve disporre dei privilegi minimi necessari per l'esecuzione del lavoro designato.</span><span class="sxs-lookup"><span data-stu-id="50032-130">The login used by the server proxy account should have the least privileges required to perform the intended work.</span></span> <span data-ttu-id="50032-131">Privilegi eccessivi per l'account proxy potrebbero essere utilizzati da utenti malintenzionati per compromettere la sicurezza del sistema.</span><span class="sxs-lookup"><span data-stu-id="50032-131">Excessive privileges for the proxy account could be used by a malicious user to compromise your system security.</span></span>  
  
 <span data-ttu-id="50032-132">**Account proxy**</span><span class="sxs-lookup"><span data-stu-id="50032-132">**Proxy account**</span></span>  
 <span data-ttu-id="50032-133">Consente di specificare l'account proxy utilizzato.</span><span class="sxs-lookup"><span data-stu-id="50032-133">Specify the proxy account used.</span></span>  
  
 <span data-ttu-id="50032-134">**Password**</span><span class="sxs-lookup"><span data-stu-id="50032-134">**Password**</span></span>  
 <span data-ttu-id="50032-135">Consente di specificare la password per l'account proxy.</span><span class="sxs-lookup"><span data-stu-id="50032-135">Specify the password for the proxy account.</span></span>  
  
## <a name="options"></a><span data-ttu-id="50032-136">Opzioni</span><span class="sxs-lookup"><span data-stu-id="50032-136">Options</span></span>  
 <span data-ttu-id="50032-137">**Abilita traccia di controllo C2**</span><span class="sxs-lookup"><span data-stu-id="50032-137">**Enable C2 audit tracing**</span></span>  
 <span data-ttu-id="50032-138">Consente di tenere traccia di tutti i tentativi di accesso a istruzioni e oggetti, nonché di registrarli in un file nella directory \MSSQL\Data per le istanze predefinite di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], o nella directory \MSSQL$*nomeistanza*\Data per le istanze denominate di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="50032-138">Audits all attempts to access statements and objects and records them to a file in the \MSSQL\Data directory for default instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], or the \MSSQL$*instancename*\Data directory for named instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="50032-139">Per altre informazioni, vedere [Opzione di configurazione del server c2 audit mode](c2-audit-mode-server-configuration-option.md).</span><span class="sxs-lookup"><span data-stu-id="50032-139">For more information, see [c2 audit mode Server Configuration Option](c2-audit-mode-server-configuration-option.md).</span></span>  
  
 <span data-ttu-id="50032-140">**Concatenamento della proprietà tra database**</span><span class="sxs-lookup"><span data-stu-id="50032-140">**Cross database ownership chaining**</span></span>  
 <span data-ttu-id="50032-141">Selezionare questa opzione per impostare il database come origine o destinazione di un concatenamento di proprietà tra database.</span><span class="sxs-lookup"><span data-stu-id="50032-141">Select to allow the database to be the source or target of a cross-database ownership chain.</span></span> <span data-ttu-id="50032-142">Per altre informazioni, vedere [Opzione di configurazione del server cross db ownership chaining](cross-db-ownership-chaining-server-configuration-option.md).</span><span class="sxs-lookup"><span data-stu-id="50032-142">For more information, see [cross db ownership chaining Server Configuration Option](cross-db-ownership-chaining-server-configuration-option.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50032-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="50032-143">See Also</span></span>  
 [<span data-ttu-id="50032-144">Opzioni di configurazione del server &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="50032-144">Server Configuration Options &#40;SQL Server&#41;</span></span>](server-configuration-options-sql-server.md)  
  
  
