---
title: Criteri password | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- ALTER LOGIN statement
- passwords [SQL Server], policy enforcement
- logins [SQL Server], passwords
- CHECK_EXPIRATION option
- complex passwords [SQL Server]
- passwords [SQL Server], expiration
- manual bad password count resets
- MUST_CHANGE option
- expiration [SQL Server]
- expired password [SQL Server]
- symbols [SQL Server]
- NetValidatePasswordPolicy() API
- passwords [SQL Server]
- password policy [SQL Server]
- resetting bad password counts
- security [SQL Server], passwords
- CHECK_POLICY option
- passwords [SQL Server], symbols
- bad password counts
- passwords [SQL Server], complexity
- characters [SQL Server], password policies
ms.assetid: c0040c0a-a18f-45b9-9c40-0625685649b1
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 902c46b4609a32139450843414a3c4d97b52fcf7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625264"
---
# <a name="password-policy"></a><span data-ttu-id="5175a-102">Criteri password</span><span class="sxs-lookup"><span data-stu-id="5175a-102">Password Policy</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="5175a-103">può usare i meccanismi di criteri password di Windows.</span><span class="sxs-lookup"><span data-stu-id="5175a-103">can use Windows password policy mechanisms.</span></span> <span data-ttu-id="5175a-104">I criteri password si applicano a un account di accesso che utilizza l'autenticazione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e a un utente del database indipendente con password.</span><span class="sxs-lookup"><span data-stu-id="5175a-104">The password policy applies to a login that uses [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] authentication, and to a contained database user with password.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="5175a-105">può applicare gli stessi criteri di complessità e scadenza utilizzati in Windows alle password all'interno di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5175a-105">can apply the same complexity and expiration policies used in Windows to passwords used inside [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="5175a-106">Questa funzionalità dipende dall'API `NetValidatePasswordPolicy` .</span><span class="sxs-lookup"><span data-stu-id="5175a-106">This functionality depends on the `NetValidatePasswordPolicy` API.</span></span>  
  
## <a name="password-complexity"></a><span data-ttu-id="5175a-107">Complessità delle password</span><span class="sxs-lookup"><span data-stu-id="5175a-107">Password Complexity</span></span>  
 <span data-ttu-id="5175a-108">I criteri di complessità delle password sono progettati per fungere da deterrente agli attacchi a forza bruta aumentando il numero di password possibili.</span><span class="sxs-lookup"><span data-stu-id="5175a-108">Password complexity policies are designed to deter brute force attacks by increasing the number of possible passwords.</span></span> <span data-ttu-id="5175a-109">Quando vengono applicati i criteri di complessità delle password, le nuove password devono soddisfare i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="5175a-109">When password complexity policy is enforced, new passwords must meet the following guidelines:</span></span>  
  
-   <span data-ttu-id="5175a-110">Non devono contenere il nome account dell'utente.</span><span class="sxs-lookup"><span data-stu-id="5175a-110">The password does not contain the account name of the user.</span></span>  
  
-   <span data-ttu-id="5175a-111">Devono essere composte da almeno otto caratteri.</span><span class="sxs-lookup"><span data-stu-id="5175a-111">The password is at least eight characters long.</span></span>  
  
-   <span data-ttu-id="5175a-112">Devono contenere caratteri di almeno tre delle quattro categorie seguenti:</span><span class="sxs-lookup"><span data-stu-id="5175a-112">The password contains characters from three of the following four categories:</span></span>  
  
    -   <span data-ttu-id="5175a-113">Lettere maiuscole dell'alfabeto latino (dalla A alla Z)</span><span class="sxs-lookup"><span data-stu-id="5175a-113">Latin uppercase letters (A through Z)</span></span>  
  
    -   <span data-ttu-id="5175a-114">Lettere minuscole dell'alfabeto latino (dalla a alla z)</span><span class="sxs-lookup"><span data-stu-id="5175a-114">Latin lowercase letters (a through z)</span></span>  
  
    -   <span data-ttu-id="5175a-115">Numeri in base 10 (da 0 a 9)</span><span class="sxs-lookup"><span data-stu-id="5175a-115">Base 10 digits (0 through 9)</span></span>  
  
    -   <span data-ttu-id="5175a-116">Caratteri non alfanumerici, ad esempio punto esclamativo (!), dollaro ($), simbolo di cancelletto (#) o percentuale (%).</span><span class="sxs-lookup"><span data-stu-id="5175a-116">Non-alphanumeric characters such as: exclamation point (!), dollar sign ($), number sign (#), or percent (%).</span></span>  
  
 <span data-ttu-id="5175a-117">Le password possono contenere fino a 128 caratteri.</span><span class="sxs-lookup"><span data-stu-id="5175a-117">Passwords can be up to 128 characters long.</span></span> <span data-ttu-id="5175a-118">È consigliabile utilizzare password più lunghe e complesse possibile.</span><span class="sxs-lookup"><span data-stu-id="5175a-118">You should use passwords that are as long and complex as possible.</span></span>  
  
## <a name="password-expiration"></a><span data-ttu-id="5175a-119">Scadenza delle password</span><span class="sxs-lookup"><span data-stu-id="5175a-119">Password Expiration</span></span>  
 <span data-ttu-id="5175a-120">I criteri di scadenza delle password consentono di gestire l'intervallo di validità di una password.</span><span class="sxs-lookup"><span data-stu-id="5175a-120">Password expiration policies are used to manage the lifespan of a password.</span></span> <span data-ttu-id="5175a-121">Se in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] vengono applicati i criteri di scadenza delle password, gli utenti ricevono un promemoria per la modifica delle vecchie password e gli account con password scadute vengono disabilitati.</span><span class="sxs-lookup"><span data-stu-id="5175a-121">When [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] enforces password expiration policy, users are reminded to change old passwords, and accounts that have expired passwords are disabled.</span></span>  
  
## <a name="policy-enforcement"></a><span data-ttu-id="5175a-122">Applicazione dei criteri</span><span class="sxs-lookup"><span data-stu-id="5175a-122">Policy Enforcement</span></span>  
 <span data-ttu-id="5175a-123">L'applicazione dei criteri password può essere configurata separatamente per ogni account di accesso di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5175a-123">The enforcement of password policy can be configured separately for each SQL Server login.</span></span> <span data-ttu-id="5175a-124">Usare [ALTER LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-login-transact-sql) per configurare i criteri password di un account di accesso di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5175a-124">Use [ALTER LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-login-transact-sql) to configure the password policy options of a SQL Server login.</span></span> <span data-ttu-id="5175a-125">Le regole seguenti sono valide per la configurazione dell'applicazione dei criteri password:</span><span class="sxs-lookup"><span data-stu-id="5175a-125">The following rules apply to the configuration of password policy enforcement:</span></span>  
  
-   <span data-ttu-id="5175a-126">Quando l'opzione CHECK_POLICY viene impostata su ON, si ottiene il comportamento seguente:</span><span class="sxs-lookup"><span data-stu-id="5175a-126">When CHECK_POLICY is changed to ON, the following behaviors occur:</span></span>  
  
    -   <span data-ttu-id="5175a-127">Anche CHECK_EXPIRATION viene impostato su ON, a meno che non lo si imposti esplicitamente su OFF.</span><span class="sxs-lookup"><span data-stu-id="5175a-127">CHECK_EXPIRATION is also set to ON unless it is explicitly set to OFF.</span></span>  
  
    -   <span data-ttu-id="5175a-128">La cronologia delle password viene inizializzata con il valore dell'hash della password corrente.</span><span class="sxs-lookup"><span data-stu-id="5175a-128">The password history is initialized with the value of the current password hash.</span></span>  
  
    -   <span data-ttu-id="5175a-129">Vengono inoltre abilitate le opzioni**Durata blocco account**, **Soglia di blocchi dell'account**e **Reimposta blocco account dopo** .</span><span class="sxs-lookup"><span data-stu-id="5175a-129">**Account lockout duration**, **account lockout threshold**, and **reset account lockout counter after** are also enabled.</span></span>  
  
-   <span data-ttu-id="5175a-130">Quando l'opzione CHECK_POLICY viene impostata su OFF, si ottiene il comportamento seguente:</span><span class="sxs-lookup"><span data-stu-id="5175a-130">When CHECK_POLICY is changed to OFF, the following behaviors occur:</span></span>  
  
    -   <span data-ttu-id="5175a-131">Anche l'opzione CHECK_EXPIRATION viene impostata su OFF.</span><span class="sxs-lookup"><span data-stu-id="5175a-131">CHECK_EXPIRATION is also set to OFF.</span></span>  
  
    -   <span data-ttu-id="5175a-132">Viene cancellata la cronologia delle password.</span><span class="sxs-lookup"><span data-stu-id="5175a-132">The password history is cleared.</span></span>  
  
    -   <span data-ttu-id="5175a-133">Viene reimpostato il valore di `lockout_time` .</span><span class="sxs-lookup"><span data-stu-id="5175a-133">The value of `lockout_time` is reset.</span></span>  
  
 <span data-ttu-id="5175a-134">Alcune combinazioni di criteri non sono supportate.</span><span class="sxs-lookup"><span data-stu-id="5175a-134">Some combinations of policy options are not supported.</span></span>  
  
-   <span data-ttu-id="5175a-135">Se si specifica MUST_CHANGE, è necessario impostare CHECK_EXPIRATION e CHECK_POLICY su ON.</span><span class="sxs-lookup"><span data-stu-id="5175a-135">If MUST_CHANGE is specified, CHECK_EXPIRATION and CHECK_POLICY must be set to ON.</span></span> <span data-ttu-id="5175a-136">In caso contrario, l'istruzione non verrà eseguita correttamente.</span><span class="sxs-lookup"><span data-stu-id="5175a-136">Otherwise, the statement will fail.</span></span>  
  
-   <span data-ttu-id="5175a-137">Se l'opzione CHECK_POLICY è impostata su OFF, non è possibile impostare CHECK_EXPIRATION su ON.</span><span class="sxs-lookup"><span data-stu-id="5175a-137">If CHECK_POLICY is set to OFF, CHECK_EXPIRATION cannot be set to ON.</span></span> <span data-ttu-id="5175a-138">Un'istruzione ALTER LOGIN che presenta questa combinazione di opzioni avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="5175a-138">An ALTER LOGIN statement that has this combination of options will fail.</span></span>  
  
 <span data-ttu-id="5175a-139">L'impostazione di CHECK_POLICY su ON impedirà la creazione di password:</span><span class="sxs-lookup"><span data-stu-id="5175a-139">Setting CHECK_POLICY = ON will prevent the creation of passwords that are:</span></span>  
  
-   <span data-ttu-id="5175a-140">Null o vuote</span><span class="sxs-lookup"><span data-stu-id="5175a-140">Null or empty</span></span>  
  
-   <span data-ttu-id="5175a-141">Equivalenti al nome del computer o dell'account di accesso</span><span class="sxs-lookup"><span data-stu-id="5175a-141">Same as name of computer or login</span></span>  
  
-   <span data-ttu-id="5175a-142">Equivalenti a parole quali "password", "admin", "administrator", "sa", "sysadmin"</span><span class="sxs-lookup"><span data-stu-id="5175a-142">Any of the following: "password", "admin", "administrator", "sa", "sysadmin"</span></span>  
  
 <span data-ttu-id="5175a-143">I criteri di sicurezza possono essere impostati in Windows o essere ricevuti dal dominio.</span><span class="sxs-lookup"><span data-stu-id="5175a-143">The security policy might be set in Windows, or might be received from the domain.</span></span> <span data-ttu-id="5175a-144">Per visualizzare i criteri password nel computer, usare lo snap-in MMC Criteri di sicurezza locali (**secpol.msc**).</span><span class="sxs-lookup"><span data-stu-id="5175a-144">To view the password policy on the computer, use the Local Security Policy MMC snap-in (**secpol.msc**).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="5175a-145">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="5175a-145">Related Tasks</span></span>  
 [<span data-ttu-id="5175a-146">CREATE LOGIN &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="5175a-146">CREATE LOGIN &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-login-transact-sql)  
  
 [<span data-ttu-id="5175a-147">ALTER LOGIN &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="5175a-147">ALTER LOGIN &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-login-transact-sql)  
  
 [<span data-ttu-id="5175a-148">CREATE USER &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="5175a-148">CREATE USER &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-user-transact-sql)  
  
 [<span data-ttu-id="5175a-149">ALTER USER &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="5175a-149">ALTER USER &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-user-transact-sql)  
  
 [<span data-ttu-id="5175a-150">Creare un account di accesso</span><span class="sxs-lookup"><span data-stu-id="5175a-150">Create a Login</span></span>](authentication-access/create-a-login.md)  
  
 [<span data-ttu-id="5175a-151">Creazione di un utente di database</span><span class="sxs-lookup"><span data-stu-id="5175a-151">Create a Database User</span></span>](authentication-access/create-a-database-user.md)  
  
## <a name="related-content"></a><span data-ttu-id="5175a-152">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="5175a-152">Related Content</span></span>  
 [<span data-ttu-id="5175a-153">Password complesse</span><span class="sxs-lookup"><span data-stu-id="5175a-153">Strong Passwords</span></span>](strong-passwords.md)  
  
  
