---
title: Creare un account di Posta elettronica database | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- Database Mail [SQL Server], accounts
- accounts [Database Mail]
ms.assetid: c07abbc6-fc6a-470b-8fa3-532f2e06b16a
author: stevestein
ms.author: sstein
ms.openlocfilehash: ec7d1c9147998b5a19cc0e6af13220bd64e165fd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626807"
---
# <a name="create-a-database-mail-account"></a><span data-ttu-id="96790-102">Creare un account di Posta elettronica database.</span><span class="sxs-lookup"><span data-stu-id="96790-102">Create a Database Mail Account</span></span>
  <span data-ttu-id="96790-103">Per creare un account di Posta elettronica database, utilizzare la **Configurazione guidata Posta elettronica database** o [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="96790-103">Use either the **Database Mail Configuration Wizard** or [!INCLUDE[tsql](../../includes/tsql-md.md)] to create a Database Mail account.</span></span>  
  
-   <span data-ttu-id="96790-104">**Prima di iniziare:**  [Prerequisiti](#Prerequisites)</span><span class="sxs-lookup"><span data-stu-id="96790-104">**Before you begin:**  [Prerequisites](#Prerequisites)</span></span>  
  
-   <span data-ttu-id="96790-105">**Per creare un account di Posta elettronica database usando:**  [Configurazione guidata Posta elettronica database](#SSMSProcedure), [Transact-SQL](#TsqlProcedure)</span><span class="sxs-lookup"><span data-stu-id="96790-105">**To Create a Database Mail Account, using:**  [Database Mail Configuration Wizard](#SSMSProcedure), [Transact-SQL](#TsqlProcedure)</span></span>  
  
-   <span data-ttu-id="96790-106">**Completamento:**  [Passaggi successivi per configurare Posta elettronica database](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="96790-106">**Follow Up:**  [Next Steps to Configure the Database Mail](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="96790-107">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="96790-107">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="96790-108">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="96790-108">Prerequisites</span></span>  
  
-   <span data-ttu-id="96790-109">Determinare il nome del server e il numero di porta per il server SMTP (Simple Mail Transfer Protocol) utilizzato per inviare e-mail. Se il server SMTP richiede l'autenticazione, determinare il nome utente e la password per il server SMTP.</span><span class="sxs-lookup"><span data-stu-id="96790-109">Determine the server name and port number for the Simple Mail Transfer Protocol (SMTP) server you use to send e-mail.If the SMTP server requires authentication, determine the user name and password for the SMTP server.</span></span>  
  
-   <span data-ttu-id="96790-110">Se lo si desidera, è possibile specificare il tipo e il numero di porta del server.</span><span class="sxs-lookup"><span data-stu-id="96790-110">Optionally, you may also specify the type of the server and the port number for the server.</span></span> <span data-ttu-id="96790-111">Il tipo di server per la posta in uscita è sempre SMTP.</span><span class="sxs-lookup"><span data-stu-id="96790-111">The server type is always 'SMTP' for outgoing mail.</span></span> <span data-ttu-id="96790-112">La maggior parte dei server SMTP utilizza la porta predefinita, ovvero la 25.</span><span class="sxs-lookup"><span data-stu-id="96790-112">Most SMTP servers use port 25, the default.</span></span>  
  
##  <a name="using-database-mail-configuration-wizard"></a><a name="SSMSProcedure"></a> <span data-ttu-id="96790-113">Utilizzo della Configurazione guidata Posta elettronica database</span><span class="sxs-lookup"><span data-stu-id="96790-113">Using Database Mail Configuration Wizard</span></span>  
 <span data-ttu-id="96790-114">**Per creare un account di Posta elettronica database utilizzando una procedura guidata**</span><span class="sxs-lookup"><span data-stu-id="96790-114">**To create a Database Mail account using a Wizard**</span></span>  
  
-   <span data-ttu-id="96790-115">In Esplora oggetti, connettersi all'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] su cui si desidera configurare Posta elettronica database ed espandere l'albero di server.</span><span class="sxs-lookup"><span data-stu-id="96790-115">In Object Explorer, connect to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance you want to configure Database Mail on, and expand the server tree.</span></span>  
  
-   <span data-ttu-id="96790-116">Espandere il nodo **Gestione**</span><span class="sxs-lookup"><span data-stu-id="96790-116">Expand the **Management** node</span></span>  
  
-   <span data-ttu-id="96790-117">Fare doppio clic su Posta elettronica database per aprire la Configurazione guidata Posta elettronica database.</span><span class="sxs-lookup"><span data-stu-id="96790-117">Double Click Database Mail to open the Database Mail Configuration Wizard.</span></span>  
  
-   <span data-ttu-id="96790-118">Nella pagina **Selezione attività di configurazione** selezionare l'opzione **Gestisci account e profili di Posta elettronica database**e fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="96790-118">On the **Select Configuration Task** page, select **Manage Database Mail accounts and profiles**, and click **Next**.</span></span>  
  
-   <span data-ttu-id="96790-119">Nella pagina **Gestione profili e account** selezionare l'opzione **Crea un nuovo account** e fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="96790-119">On the **Manage Profiles and Accounts** page, select **Create a new account** and click **Next**.</span></span>  
  
-   <span data-ttu-id="96790-120">Nella pagina **Nuovo account** , specificare il nome dell'account, la descrizione, informazione sul server di posta elettronica e tipo di autenticazione.</span><span class="sxs-lookup"><span data-stu-id="96790-120">On the **New Account** page, specify the account name, description, mail server information, and authentication type.</span></span> <span data-ttu-id="96790-121">Scegliere **Avanti**</span><span class="sxs-lookup"><span data-stu-id="96790-121">Click **Next**</span></span>  
  
-   <span data-ttu-id="96790-122">Per completare la creazione del nuovo account, rivedere le azioni da eseguire nella pagina **Completamento procedura guidata** quindi fare clic su **Fine** .</span><span class="sxs-lookup"><span data-stu-id="96790-122">On the **Complete the Wizard** page, review the actions to be performed and click **Finish** to complete creating the new account.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="96790-123">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="96790-123">Using Transact-SQL</span></span>  
 <span data-ttu-id="96790-124">**Per creare un account di Posta elettronica database utilizzando Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="96790-124">**To Create a Database Mail account using Transact-SQL**</span></span>  
  
 <span data-ttu-id="96790-125">Eseguire la stored procedure **msdb.dbo.sysmail_add_account_sp** per creare l'account, specificando le seguenti informazioni:</span><span class="sxs-lookup"><span data-stu-id="96790-125">Execute the stored procedure **msdb.dbo.sysmail_add_account_sp** to create the account and specify the following information:</span></span>  
  
-   <span data-ttu-id="96790-126">Nome dell'account da creare.</span><span class="sxs-lookup"><span data-stu-id="96790-126">The name of the account to create.</span></span>  
  
-   <span data-ttu-id="96790-127">Descrizione dell'account (facoltativa).</span><span class="sxs-lookup"><span data-stu-id="96790-127">An optional description of the account.</span></span>  
  
-   <span data-ttu-id="96790-128">Indirizzo di posta elettronica visualizzato nei messaggi in uscita.</span><span class="sxs-lookup"><span data-stu-id="96790-128">The e-mail address to show on outgoing e-mail messages.</span></span>  
  
-   <span data-ttu-id="96790-129">Nome visualizzato nei messaggi in uscita.</span><span class="sxs-lookup"><span data-stu-id="96790-129">The display name to show on outgoing e-mail messages.</span></span>  
  
-   <span data-ttu-id="96790-130">Nome del server SMTP.</span><span class="sxs-lookup"><span data-stu-id="96790-130">The server name of the SMTP server.</span></span>  
  
-   <span data-ttu-id="96790-131">Nome utente da utilizzare per l'accesso se il server SMTP richiede l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="96790-131">The user name to use to log on to the SMTP server, if the SMTP server requires authentication.</span></span>  
  
-   <span data-ttu-id="96790-132">Password da utilizzare per l'accesso se il server SMTP richiede l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="96790-132">The password to use to log on to the SMTP server, if the SMTP server requires authentication.</span></span>  
  
 <span data-ttu-id="96790-133">Nell'esempio seguente viene creato un nuovo account di Posta elettronica database.</span><span class="sxs-lookup"><span data-stu-id="96790-133">The following example creates a new Database Mail account.</span></span>  
  
```  
EXECUTE msdb.dbo.sysmail_add_account_sp  
    @account_name = 'AdventureWorks Administrator',  
    @description = 'Mail account for administrative e-mail.',  
    @email_address = 'dba@Adventure-Works.com',  
    @display_name = 'AdventureWorks Automated Mailer',  
    @mailserver_name = 'smtp.Adventure-Works.com' ;  
```  
  
##  <a name="follow-up-next-steps-to-configuring-the-database-mail"></a><a name="FollowUp"></a> <span data-ttu-id="96790-134">Completamento: Passaggi successivi per configurare Posta elettronica database</span><span class="sxs-lookup"><span data-stu-id="96790-134">Follow Up: Next Steps to Configuring the Database Mail</span></span>  
  
-   [<span data-ttu-id="96790-135">Creare un profilo di Posta elettronica database</span><span class="sxs-lookup"><span data-stu-id="96790-135">Create a Database Mail Profile</span></span>](create-a-database-mail-profile.md)  
  
  
