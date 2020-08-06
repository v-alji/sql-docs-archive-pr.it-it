---
title: Modifica della modalità di autenticazione del server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- sa account
- authentication [SQL Server], changing modes
- server authentication mode [SQL Server]
- modifying server authentication mode
ms.assetid: 79babcf8-19fd-4495-b8eb-453dc575cac0
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8bda31ca7d0c5949173a9a3e5ea656c1757c04f7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724199"
---
# <a name="change-server-authentication-mode"></a><span data-ttu-id="ac60a-102">Modifica della modalità di autenticazione del server</span><span class="sxs-lookup"><span data-stu-id="ac60a-102">Change Server Authentication Mode</span></span>
  <span data-ttu-id="ac60a-103">In questo argomento viene descritto come modificare la modalità di autenticazione del server in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ac60a-103">This topic describes how to change the server authentication mode in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="ac60a-104">Durante l'installazione [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] è impostato su **Autenticazione di Windows** o **Autenticazione di SQL Server e di Windows**.</span><span class="sxs-lookup"><span data-stu-id="ac60a-104">During installation, [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] is set to either **Windows Authentication mode** or **SQL Server and Windows Authentication mode**.</span></span> <span data-ttu-id="ac60a-105">Dopo l'installazione, è possibile modificare in qualsiasi momento la modalità di autenticazione.</span><span class="sxs-lookup"><span data-stu-id="ac60a-105">After installation, you can change the authentication mode at any time.</span></span>  
  
 <span data-ttu-id="ac60a-106">Se si seleziona **Modalità di autenticazione di Windows** durante l'installazione, l'account di accesso sa viene disabilitato e il programma di installazione assegna una password.</span><span class="sxs-lookup"><span data-stu-id="ac60a-106">If **Windows Authentication mode** is selected during installation, the sa login is disabled and a password is assigned by setup.</span></span> <span data-ttu-id="ac60a-107">Se in seguito si modifica la modalità di autenticazione in **Autenticazione di SQL Server e di Windows**, l'account di accesso sa resterà disabilitato.</span><span class="sxs-lookup"><span data-stu-id="ac60a-107">If you later change authentication mode to **SQL Server and Windows Authentication mode**, the sa login remains disabled.</span></span> <span data-ttu-id="ac60a-108">Per usare l'account di accesso sa, usare l'istruzione ALTER LOGIN per abilitare l'account sa e assegnare una nuova password.</span><span class="sxs-lookup"><span data-stu-id="ac60a-108">To use the sa login, use the ALTER LOGIN statement to enable the sa login and assign a new password.</span></span> <span data-ttu-id="ac60a-109">È possibile connettersi al server tramite l'account sa solo se si utilizza l'autenticazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ac60a-109">The sa login can only connect to the server by using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span>  
  
 <span data-ttu-id="ac60a-110">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="ac60a-110">**In This Topic**</span></span>  
  
-   <span data-ttu-id="ac60a-111">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="ac60a-111">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="ac60a-112">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="ac60a-112">Security</span></span>](#Security)  
  
-   <span data-ttu-id="ac60a-113">**Per modificare la modalità di autenticazione del server utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="ac60a-113">**To change server authentication mode, using:**</span></span>  
  
     [<span data-ttu-id="ac60a-114">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ac60a-114">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="ac60a-115">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ac60a-115">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="ac60a-116">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="ac60a-116">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="ac60a-117">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="ac60a-117">Security</span></span>  
 <span data-ttu-id="ac60a-118">L'account sa è un account noto di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] che viene spesso preso di mira da utenti malintenzionati.</span><span class="sxs-lookup"><span data-stu-id="ac60a-118">The sa account is a well-known [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account and it is often targeted by malicious users.</span></span> <span data-ttu-id="ac60a-119">Non abilitare l'account sa a meno che l'applicazione non lo richieda.</span><span class="sxs-lookup"><span data-stu-id="ac60a-119">Do not enable the sa account unless your application requires it.</span></span> <span data-ttu-id="ac60a-120">È estremamente importante utilizzare una password complessa per l'accesso all'account sa.</span><span class="sxs-lookup"><span data-stu-id="ac60a-120">It is very important that you use a strong password for the sa login.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="ac60a-121">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ac60a-121">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-change-security-authentication-mode"></a><span data-ttu-id="ac60a-122">Per modificare la modalità di autenticazione di sicurezza</span><span class="sxs-lookup"><span data-stu-id="ac60a-122">To change security authentication mode</span></span>  
  
1.  <span data-ttu-id="ac60a-123">In Esplora oggetti di [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] fare clic con il pulsante destro del mouse sul server e quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="ac60a-123">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Object Explorer, right-click the server, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="ac60a-124">Nella pagina **Sicurezza** selezionare la nuova modalità di autenticazione del server dall'elenco **Autenticazione server**e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="ac60a-124">On the **Security** page, under **Server authentication**, select the new server authentication mode, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="ac60a-125">Nella finestra di dialogo [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] fare clic su **OK** per confermare il riavvio di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ac60a-125">In the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] dialog box, click **OK** to acknowledge the requirement to restart [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
4.  <span data-ttu-id="ac60a-126">In Esplora oggetti fare clic con il pulsante destro del mouse sul server e quindi scegliere **Riavvia**.</span><span class="sxs-lookup"><span data-stu-id="ac60a-126">In Object Explorer, right-click your server, and then click **Restart**.</span></span> <span data-ttu-id="ac60a-127">Se è in esecuzione, è necessario riavviare anche [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="ac60a-127">If [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent is running, it must also be restarted.</span></span>  
  
#### <a name="to-enable-the-sa-login"></a><span data-ttu-id="ac60a-128">Per abilitare l'account di accesso sa</span><span class="sxs-lookup"><span data-stu-id="ac60a-128">To enable the sa login</span></span>  
  
1.  <span data-ttu-id="ac60a-129">In Esplora oggetti espandere **sicurezza**, espandere account di accesso, fare clic con il pulsante destro del mouse su `sa` , quindi scegliere **proprietà**.</span><span class="sxs-lookup"><span data-stu-id="ac60a-129">In Object Explorer, expand **Security**, expand Logins, right-click `sa`, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="ac60a-130">Nella pagina **Generale** potrebbe essere necessario creare e confermare una password per l'account di accesso.</span><span class="sxs-lookup"><span data-stu-id="ac60a-130">On the **General** page, you might have to create and confirm a password for the  login.</span></span>  
  
3.  <span data-ttu-id="ac60a-131">Nella pagina **Stato** fare clic su **Abilitato** nella sezione **Account di accesso**, quindi scegliere **OK**.</span><span class="sxs-lookup"><span data-stu-id="ac60a-131">On the **Status** page, in the **Login** section, click **Enabled**, and then click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="ac60a-132">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ac60a-132">Using Transact-SQL</span></span>  
 <span data-ttu-id="ac60a-133">**Per abilitare l'account di accesso sa**</span><span class="sxs-lookup"><span data-stu-id="ac60a-133">**To enable the sa login**</span></span>  
  
1.  <span data-ttu-id="ac60a-134">In Esplora oggetti connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ac60a-134">In Object Explorer, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="ac60a-135">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="ac60a-135">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="ac60a-136">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="ac60a-136">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="ac60a-137">Nell'esempio seguente viene abilitato l'account di accesso sa e viene impostata una nuova password.</span><span class="sxs-lookup"><span data-stu-id="ac60a-137">The following example enables the sa login and sets a new password.</span></span>  
  
    ```  
    ALTER LOGIN sa ENABLE ;  
    GO  
    ALTER LOGIN sa WITH PASSWORD = '<enterStrongPasswordHere>' ;  
    GO  
  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="ac60a-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ac60a-138">See Also</span></span>  
 <span data-ttu-id="ac60a-139">[Password complesse](../../relational-databases/security/strong-passwords.md) </span><span class="sxs-lookup"><span data-stu-id="ac60a-139">[Strong Passwords](../../relational-databases/security/strong-passwords.md) </span></span>  
 <span data-ttu-id="ac60a-140">[Considerazioni sulla sicurezza per un'installazione di SQL Server](../../sql-server/install/security-considerations-for-a-sql-server-installation.md) </span><span class="sxs-lookup"><span data-stu-id="ac60a-140">[Security Considerations for a SQL Server Installation](../../sql-server/install/security-considerations-for-a-sql-server-installation.md) </span></span>  
 <span data-ttu-id="ac60a-141">[ALTER LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-login-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ac60a-141">[ALTER LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-login-transact-sql) </span></span>  
 [<span data-ttu-id="ac60a-142">Connettersi a SQL Server se gli amministratori di sistema sono bloccati</span><span class="sxs-lookup"><span data-stu-id="ac60a-142">Connect to SQL Server When System Administrators Are Locked Out</span></span>](connect-to-sql-server-when-system-administrators-are-locked-out.md)  
  
  
