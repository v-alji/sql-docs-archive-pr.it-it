---
title: Creazione di un account di accesso | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- creating a login
ms.assetid: a2512310-bdb6-41dc-858a-e866b2b58afc
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 400a57693fbea10270a51f5735a19b9639112ce9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722132"
---
# <a name="creating-a-login"></a><span data-ttu-id="e02a9-102">Creazione di un account di accesso</span><span class="sxs-lookup"><span data-stu-id="e02a9-102">Creating a Login</span></span>
  <span data-ttu-id="e02a9-103">Per accedere a [!INCLUDE[ssDE](../includes/ssde-md.md)]è necessario che gli utenti dispongano di un account di accesso.</span><span class="sxs-lookup"><span data-stu-id="e02a9-103">To access the [!INCLUDE[ssDE](../includes/ssde-md.md)], users require a login.</span></span> <span data-ttu-id="e02a9-104">L'account di accesso può rappresentare l'identità dell'utente come un account di Windows o come membro di un gruppo di Windows oppure un account di accesso di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] esistente solo in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e02a9-104">The login can represent the user's identity as a Windows account or as a member of a Windows group, or the login can be a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] login that exists only in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="e02a9-105">Se possibile, è consigliabile utilizzare l'autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="e02a9-105">Whenever possible you should use Windows Authentication.</span></span>  
  
 <span data-ttu-id="e02a9-106">Per impostazione predefinita, gli amministratori del computer dispongono di accesso completo a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e02a9-106">By default, administrators on your computer have full access to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="e02a9-107">Ai fini di questa lezione, è sufficiente un utente che dispone di minori privilegi e verrà pertanto creato un nuovo account dell'autenticazione di Windows locale nel computer in uso.</span><span class="sxs-lookup"><span data-stu-id="e02a9-107">For this lesson, we want to have a less privileged user; therefore, you will create a new local Windows Authentication account on your computer.</span></span> <span data-ttu-id="e02a9-108">A tale scopo, è necessario essere un amministratore del computer.</span><span class="sxs-lookup"><span data-stu-id="e02a9-108">To do this, you must be an administrator on your computer.</span></span> <span data-ttu-id="e02a9-109">Al nuovo utente verrà quindi concesso l'accesso a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e02a9-109">Then you will grant that new user access to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
### <a name="to-create-a-new-windows-account"></a><span data-ttu-id="e02a9-110">Per creare un nuovo account di Windows</span><span class="sxs-lookup"><span data-stu-id="e02a9-110">To create a new Windows account</span></span>  
  
1.  <span data-ttu-id="e02a9-111">Fare clic sul pulsante **Start**, scegliere **Esegui**, digitare nella casella **Apri** `%SystemRoot%\system32\compmgmt.msc /s` e quindi fare clic su **OK** per aprire il programma di gestione computer.</span><span class="sxs-lookup"><span data-stu-id="e02a9-111">Click **Start**, click **Run**, in the **Open** box, type `%SystemRoot%\system32\compmgmt.msc /s`, and then click **OK** to open the Computer Management program.</span></span>  
  
2.  <span data-ttu-id="e02a9-112">In **Utilità di sistema**espandere **Utenti e gruppi locali**, fare clic con il pulsante destro del mouse su **Utenti**e quindi scegliere **Nuovo utente**.</span><span class="sxs-lookup"><span data-stu-id="e02a9-112">Under **System Tools**, expand **Local Users and Groups**, right-click **Users**, and then click **New User**.</span></span>  
  
3.  <span data-ttu-id="e02a9-113">Nella casella **Nome utente** digitare **Mary**.</span><span class="sxs-lookup"><span data-stu-id="e02a9-113">In the **User name** box type **Mary**.</span></span>  
  
4.  <span data-ttu-id="e02a9-114">Nelle caselle **Password** e **Conferma password** digitare una password complessa e quindi fare clic su **Crea** per creare un nuovo utente locale di Windows.</span><span class="sxs-lookup"><span data-stu-id="e02a9-114">In the **Password** and **Confirm password** box, type a strong password, and then click **Create** to create a new local Windows user.</span></span>  
  
### <a name="to-create-a-login"></a><span data-ttu-id="e02a9-115">Per creare un account di accesso</span><span class="sxs-lookup"><span data-stu-id="e02a9-115">To create a login</span></span>  
  
1.  <span data-ttu-id="e02a9-116">Nella finestra dell'editor di query di [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]digitare ed eseguire il codice seguente sostituendo `computer_name` con il nome del computer.</span><span class="sxs-lookup"><span data-stu-id="e02a9-116">In a Query Editor window of [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], type and execute the following code replacing `computer_name` with the name of your computer.</span></span> <span data-ttu-id="e02a9-117">`FROM WINDOWS` indica che Windows autenticherà l'utente.</span><span class="sxs-lookup"><span data-stu-id="e02a9-117">`FROM WINDOWS` indicates that Windows will authenticate the user.</span></span> <span data-ttu-id="e02a9-118">L'argomento facoltativo `DEFAULT_DATABASE` connette l'utente `Mary` al database `TestData` a meno che la relativa stringa di connessione indichi un altro database.</span><span class="sxs-lookup"><span data-stu-id="e02a9-118">The optional `DEFAULT_DATABASE` argument connects `Mary` to the `TestData` database, unless her connection string indicates another database.</span></span> <span data-ttu-id="e02a9-119">Questa istruzione introduce il punto e virgola come carattere di fine facoltativo per un'istruzione [!INCLUDE[tsql](../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e02a9-119">This statement introduces the semicolon as an optional termination for a [!INCLUDE[tsql](../includes/tsql-md.md)] statement.</span></span>  
  
    ```  
    CREATE LOGIN [computer_name\Mary]  
        FROM WINDOWS  
        WITH DEFAULT_DATABASE = [TestData];  
    GO  
    ```  
  
     <span data-ttu-id="e02a9-120">Ciò autorizza il nome utente `Mary`, autenticato dal computer in uso, ad accedere all'istanza di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e02a9-120">This authorizes a user name `Mary`, authenticated by your computer, to access this instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="e02a9-121">Se sono presenti più istanze di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] nel computer, è necessario creare l'account di accesso in ogni istanza a cui l'utente `Mary` deve accedere.</span><span class="sxs-lookup"><span data-stu-id="e02a9-121">If there is more than one instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] on the computer, you must create the login on each instance that `Mary` must access.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e02a9-122">Poiché `Mary` non è un account di dominio, il nome utente può essere autenticato solo nel computer in questione.</span><span class="sxs-lookup"><span data-stu-id="e02a9-122">Because `Mary` is not a domain account, this user name can only be authenticated on this computer.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="e02a9-123">Attività successiva della lezione</span><span class="sxs-lookup"><span data-stu-id="e02a9-123">Next Task in Lesson</span></span>  
 [<span data-ttu-id="e02a9-124">Concessione dell'accesso a un database</span><span class="sxs-lookup"><span data-stu-id="e02a9-124">Granting Access to a Database</span></span>](lesson-2-2-granting-access-to-a-database.md)  
  
## <a name="see-also"></a><span data-ttu-id="e02a9-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e02a9-125">See Also</span></span>  
 <span data-ttu-id="e02a9-126">[CREATE LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-login-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e02a9-126">[CREATE LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-login-transact-sql) </span></span>  
 [<span data-ttu-id="e02a9-127">Scegliere una modalità di autenticazione</span><span class="sxs-lookup"><span data-stu-id="e02a9-127">Choose an Authentication Mode</span></span>](../relational-databases/security/choose-an-authentication-mode.md)  
  
  
