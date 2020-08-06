---
title: Creare credenziali | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- credentials [SQL Server], creating
- authentication [SQL Server], credentials
- logins [SQL Server], credentials
ms.assetid: c1e77e91-2a69-40d9-b8b3-97cffc710586
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 23221424699449ac3775b0e805bb02ae0ad233f2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714072"
---
# <a name="create-a-credential"></a><span data-ttu-id="d8f7c-102">Create a Credential</span><span class="sxs-lookup"><span data-stu-id="d8f7c-102">Create a Credential</span></span>
  <span data-ttu-id="d8f7c-103">In questo argomento viene descritto come creare credenziali in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d8f7c-103">This topic describes how to create a credential in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="d8f7c-104">Le credenziali consentono agli utenti che utilizzano l'autenticazione di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] di disporre di un'identità al di fuori di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d8f7c-104">Credentials provide a way to allow [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Authentication users to have an identity outside of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="d8f7c-105">Vengono principalmente utilizzate per eseguire codice negli assembly con set di autorizzazioni EXTERNAL_ACCESS.</span><span class="sxs-lookup"><span data-stu-id="d8f7c-105">This is primarily used to execute code in Assemblies with EXTERNAL_ACCESS permission set.</span></span> <span data-ttu-id="d8f7c-106">È inoltre possibile utilizzare le credenziali quando un utente che utilizza l'autenticazione di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] ha la necessità di accedere a una risorsa di dominio, quale il percorso di un file in cui archiviare un backup.</span><span class="sxs-lookup"><span data-stu-id="d8f7c-106">Credentials can also be used when a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Authentication user needs access to a domain resource, such as a file location to store a backup.</span></span>  
  
 <span data-ttu-id="d8f7c-107">È possibile eseguire il mapping delle credenziali a diversi account di accesso di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="d8f7c-107">A credential can be mapped to several [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] logins at the same time.</span></span> <span data-ttu-id="d8f7c-108">Su un account di accesso di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] è possibile eseguire il mapping a un solo set di credenziali alla volta.</span><span class="sxs-lookup"><span data-stu-id="d8f7c-108">A [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] login can only be mapped to one credential at a time.</span></span> <span data-ttu-id="d8f7c-109">Dopo aver creato le credenziali, usare **Proprietà account di accesso (pagina Generale)** per eseguire il mapping di un account di accesso alle credenziali.</span><span class="sxs-lookup"><span data-stu-id="d8f7c-109">After a credential is created, use the **Login Properties (General Page)** to map a login to a credential.</span></span>  
  
 <span data-ttu-id="d8f7c-110">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="d8f7c-110">**In This Topic**</span></span>  
  
-   <span data-ttu-id="d8f7c-111">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="d8f7c-111">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="d8f7c-112">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="d8f7c-112">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="d8f7c-113">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="d8f7c-113">Security</span></span>](#Security)  
  
-   <span data-ttu-id="d8f7c-114">**Per creare le credenziali utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="d8f7c-114">**To create a credential, using:**</span></span>  
  
     [<span data-ttu-id="d8f7c-115">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d8f7c-115">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="d8f7c-116">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d8f7c-116">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="d8f7c-117">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="d8f7c-117">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="d8f7c-118">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="d8f7c-118">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="d8f7c-119">Se non sono presenti credenziali su cui viene eseguito il mapping a un account accesso per il provider, vengono utilizzate le credenziali sui cui viene eseguito il mapping all'account del servizio [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d8f7c-119">If there is no login mapped credential for the provider, the credential mapped to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service account is used.</span></span>  
  
-   <span data-ttu-id="d8f7c-120">A un account di accesso è possibile eseguire il mapping di più credenziali, a condizione che vengano utilizzate con provider distinti.</span><span class="sxs-lookup"><span data-stu-id="d8f7c-120">A login can have multiple credentials mapped to it as long as they are used with distinctive providers.</span></span> <span data-ttu-id="d8f7c-121">È possibile eseguire il mapping di una sola credenziale per provider per ogni account di accesso.</span><span class="sxs-lookup"><span data-stu-id="d8f7c-121">There must be only one mapped credential per provider per login.</span></span> <span data-ttu-id="d8f7c-122">Sulla stessa credenziale è possibile eseguire il mapping ad altri account di accesso.</span><span class="sxs-lookup"><span data-stu-id="d8f7c-122">The same credential can be mapped to other logins.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="d8f7c-123">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="d8f7c-123">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="d8f7c-124">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="d8f7c-124">Permissions</span></span>  
 <span data-ttu-id="d8f7c-125">Richiede autorizzazione ALTER ANY CREDENTIAL di creare o modificare credenziali e un autorizzazione ALTER ANY LOGIN per eseguire il mapping di un accesso a credenziali.</span><span class="sxs-lookup"><span data-stu-id="d8f7c-125">Requires ALTER ANY CREDENTIAL permission to create or modify a credential and ALTER ANY LOGIN permission to map a login to a credential.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="d8f7c-126">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d8f7c-126">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-credential"></a><span data-ttu-id="d8f7c-127">Per creare una credenziale</span><span class="sxs-lookup"><span data-stu-id="d8f7c-127">To create a credential</span></span>  
  
1.  <span data-ttu-id="d8f7c-128">In Esplora oggetti espandere la cartella **Sicurezza** .</span><span class="sxs-lookup"><span data-stu-id="d8f7c-128">In Object Explorer, expand  the **Security** folder.</span></span>  
  
2.  <span data-ttu-id="d8f7c-129">Fare clic con il pulsante destro del mouse sulla cartella **Credenziali** e scegliere **Nuove credenziali...** .</span><span class="sxs-lookup"><span data-stu-id="d8f7c-129">Right-click the **Credentials** folder and select **New Credential...**.</span></span>  
  
3.  <span data-ttu-id="d8f7c-130">Nella casella **Nome credenziali** della finestra di dialogo **Nuove credenziali** digitare un nome per le credenziali.</span><span class="sxs-lookup"><span data-stu-id="d8f7c-130">In the **New Credential** dialog box, in the **Credential Name** box, type a name for the credential.</span></span>  
  
4.  <span data-ttu-id="d8f7c-131">Nella casella **Identità** digitare il nome dell'account usato per le connessioni in uscita (quando si esce dal contesto di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="d8f7c-131">In the **Identity** box, type the name of the account used for outgoing connections (when leaving the context of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]).</span></span> <span data-ttu-id="d8f7c-132">In genere, sarà un account utente di Windows, ma l'identità può essere un account di altro tipo.</span><span class="sxs-lookup"><span data-stu-id="d8f7c-132">Typically, this will be a Windows user account, but the identity can be an account of another type.</span></span>  
  
     <span data-ttu-id="d8f7c-133">In alternativa, fare clic sui puntini di sospensione **(...)** per aprire la finestra di dialogo **Seleziona utente o gruppo**.</span><span class="sxs-lookup"><span data-stu-id="d8f7c-133">Alternately, click the ellipsis **(...)** to open the **Select User or Group** dialog box.</span></span>  
  
5.  <span data-ttu-id="d8f7c-134">Nelle caselle **Password** e **Conferma password** digitare la password dell'account specificato nella casella **Identità** .</span><span class="sxs-lookup"><span data-stu-id="d8f7c-134">In the **Password** and **Confirm password** boxes, type the password of the account specified in the **Identity** box.</span></span> <span data-ttu-id="d8f7c-135">Se **Identità** corrisponde a un account utente di Windows, è la password di Windows.</span><span class="sxs-lookup"><span data-stu-id="d8f7c-135">If **Identity** is a Windows user account, this is the Windows password.</span></span> <span data-ttu-id="d8f7c-136">Se la password non è necessaria è possibile lasciare vuoto il campo **Password** .</span><span class="sxs-lookup"><span data-stu-id="d8f7c-136">The **Password** can be blank, if no password is required.</span></span>  
  
6.  <span data-ttu-id="d8f7c-137">Selezionare **Usa provider di crittografia** per impostare le credenziali da verificare con un provider EKM (Extensible Key Management).</span><span class="sxs-lookup"><span data-stu-id="d8f7c-137">Select **Use Encryption Provider** to set the credential to be verified by an Extensible Key Management (EKM) Provider.</span></span> <span data-ttu-id="d8f7c-138">Per altre informazioni su Extensible Key Management, vedere [Extensible Key Management &#40;EKM&#41;](../encryption/extensible-key-management-ekm.md)</span><span class="sxs-lookup"><span data-stu-id="d8f7c-138">For more information, see [Extensible Key Management &#40;EKM&#41;](../encryption/extensible-key-management-ekm.md)</span></span>  
  
7.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="d8f7c-139">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d8f7c-139">Using Transact-SQL</span></span>  
  
###  <a name="to-create-a-credential"></a><a name="Credential"></a><span data-ttu-id="d8f7c-140">Per creare una credenziale</span><span class="sxs-lookup"><span data-stu-id="d8f7c-140">To create a credential</span></span>  
  
1.  <span data-ttu-id="d8f7c-141">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d8f7c-141">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="d8f7c-142">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="d8f7c-142">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="d8f7c-143">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="d8f7c-143">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Creates the credential called "AlterEgo.".   
    -- The credential contains the Windows user "Mary5" and a password.  
    CREATE CREDENTIAL AlterEgo WITH IDENTITY = 'Mary5',   
        SECRET = '<EnterStrongPasswordHere>';  
    GO  
    ```  
  
 <span data-ttu-id="d8f7c-144">Per altre informazioni, vedere [CREATE CREDENTIAL &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-credential-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="d8f7c-144">For more information, see [CREATE CREDENTIAL &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-credential-transact-sql).</span></span>  
  
  
