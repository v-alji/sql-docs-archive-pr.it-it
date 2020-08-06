---
title: Attività Notifica operatori (piano di manutenzione) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.maint.notifyoperator.f1
helpviewer_keywords:
- Notify Operator Task dialog box
ms.assetid: 39c0797c-ad2b-4591-85c9-a23a7f902895
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 4feb59622c2a42de67193c75d545a6b8a2a08863
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629821"
---
# <a name="notify-operator-task-maintenance-plan"></a><span data-ttu-id="c10e1-102">Attività Notifica operatori (Piano di manutenzione)</span><span class="sxs-lookup"><span data-stu-id="c10e1-102">Notify Operator Task (Maintenance Plan)</span></span>
  <span data-ttu-id="c10e1-103">Usare la finestra di dialogo **Attività Notifica operatori** per aggiungere una notifica automatica al piano di manutenzione corrente.</span><span class="sxs-lookup"><span data-stu-id="c10e1-103">Use the **Notify Operators Task** dialog to add an automatic notification to this maintenance plan.</span></span> <span data-ttu-id="c10e1-104">Per usare questa attività l'applicazione Posta elettronica database deve essere abilitata e configurata correttamente con MSDB come host della posta elettronica ed è necessario disporre di un operatore [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent con un indirizzo di posta elettronica valido.</span><span class="sxs-lookup"><span data-stu-id="c10e1-104">To use this task you must have Database Mail enabled and properly configured with MSDB as a Mail Host Database, and have a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent operator with a valid e-mail address.</span></span>  
  
 <span data-ttu-id="c10e1-105">Questa attività utilizza la stored procedure sp_notify_operator.</span><span class="sxs-lookup"><span data-stu-id="c10e1-105">This task uses the sp_notify_operator stored procedure.</span></span>  
  
## <a name="options"></a><span data-ttu-id="c10e1-106">Opzioni</span><span class="sxs-lookup"><span data-stu-id="c10e1-106">Options</span></span>  
 <span data-ttu-id="c10e1-107">**Connection**</span><span class="sxs-lookup"><span data-stu-id="c10e1-107">**Connection**</span></span>  
 <span data-ttu-id="c10e1-108">Consente di selezionare la connessione server da utilizzare per l'esecuzione dell'attività.</span><span class="sxs-lookup"><span data-stu-id="c10e1-108">Select the server connection to use when performing this task.</span></span>  
  
 <span data-ttu-id="c10e1-109">**Nuovo**</span><span class="sxs-lookup"><span data-stu-id="c10e1-109">**New**</span></span>  
 <span data-ttu-id="c10e1-110">Consente di creare una nuova connessione server da utilizzare per l'esecuzione dell'attività.</span><span class="sxs-lookup"><span data-stu-id="c10e1-110">Create a new server connection to use when performing this task.</span></span> <span data-ttu-id="c10e1-111">La finestra di dialogo **Nuova connessione** è descritta di seguito.</span><span class="sxs-lookup"><span data-stu-id="c10e1-111">The **New Connection** dialog box is described below.</span></span>  
  
 <span data-ttu-id="c10e1-112">**Operatori da notificare**</span><span class="sxs-lookup"><span data-stu-id="c10e1-112">**Operators to notify**</span></span>  
 <span data-ttu-id="c10e1-113">Consente di specificare il destinatario del messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="c10e1-113">Specify the recipient of the e-mail.</span></span>  
  
 <span data-ttu-id="c10e1-114">**Oggetto messaggio di notifica**</span><span class="sxs-lookup"><span data-stu-id="c10e1-114">**Notification message subject**</span></span>  
 <span data-ttu-id="c10e1-115">Consente di specificare il testo da includere nella riga dell'oggetto del messaggio di notifica.</span><span class="sxs-lookup"><span data-stu-id="c10e1-115">Specify the text to include in the notification message subject line.</span></span>  
  
 <span data-ttu-id="c10e1-116">**Corpo messaggio di notifica**</span><span class="sxs-lookup"><span data-stu-id="c10e1-116">**Notification message body**</span></span>  
 <span data-ttu-id="c10e1-117">Consente di specificare il testo da includere nel corpo del messaggio di notifica.</span><span class="sxs-lookup"><span data-stu-id="c10e1-117">Specify the text to include in the notification message body.</span></span>  
  
 <span data-ttu-id="c10e1-118">**Visualizza codice T-SQL**</span><span class="sxs-lookup"><span data-stu-id="c10e1-118">**View T-SQL**</span></span>  
 <span data-ttu-id="c10e1-119">Consente di visualizzare le istruzioni [!INCLUDE[tsql](../../includes/tsql-md.md)] eseguite sul server per questa attività, in base alle opzioni selezionate.</span><span class="sxs-lookup"><span data-stu-id="c10e1-119">View the [!INCLUDE[tsql](../../includes/tsql-md.md)] statements performed against the server for this task, based on the selected options.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c10e1-120">Se il numero di oggetti interessato dall'attività è elevato, la visualizzazione del codice potrebbe richiedere una considerevole quantità di tempo.</span><span class="sxs-lookup"><span data-stu-id="c10e1-120">When the number of objects affected is large, this display can take a considerable amount of time.</span></span>  
  
## <a name="new-connection-dialog-box"></a><span data-ttu-id="c10e1-121">Finestra di dialogo Nuova connessione</span><span class="sxs-lookup"><span data-stu-id="c10e1-121">New Connection Dialog Box</span></span>  
 <span data-ttu-id="c10e1-122">**Nome connessione**</span><span class="sxs-lookup"><span data-stu-id="c10e1-122">**Connection name**</span></span>  
 <span data-ttu-id="c10e1-123">Consente di immettere un nome per la nuova connessione.</span><span class="sxs-lookup"><span data-stu-id="c10e1-123">Enter a name for the new connection.</span></span>  
  
 <span data-ttu-id="c10e1-124">**Selezionare o immettere il nome di un server**</span><span class="sxs-lookup"><span data-stu-id="c10e1-124">**Select or enter a server name**</span></span>  
 <span data-ttu-id="c10e1-125">Consente di selezionare il server a cui connettersi per l'esecuzione dell'attività.</span><span class="sxs-lookup"><span data-stu-id="c10e1-125">Select a server to connect to when performing this task.</span></span>  
  
 <span data-ttu-id="c10e1-126">**Aggiorna**</span><span class="sxs-lookup"><span data-stu-id="c10e1-126">**Refresh**</span></span>  
 <span data-ttu-id="c10e1-127">Consente di aggiornare l'elenco dei server disponibili.</span><span class="sxs-lookup"><span data-stu-id="c10e1-127">Refresh the list of available servers.</span></span>  
  
 <span data-ttu-id="c10e1-128">**Immettere le informazioni per l'accesso al server**</span><span class="sxs-lookup"><span data-stu-id="c10e1-128">**Enter information to log on to the server**</span></span>  
 <span data-ttu-id="c10e1-129">Consente di specificare le opzioni di autenticazione per l'accesso al server.</span><span class="sxs-lookup"><span data-stu-id="c10e1-129">Specify how to authenticate against the server.</span></span>  
  
 <span data-ttu-id="c10e1-130">**Usa la sicurezza integrata di Windows NT**</span><span class="sxs-lookup"><span data-stu-id="c10e1-130">**Use Windows integrated security**</span></span>  
 <span data-ttu-id="c10e1-131">Consente di connettersi a un'istanza del [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] di [!INCLUDE[ssDE](../../includes/ssde-md.md)] usando l'autenticazione di [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="c10e1-131">Connect to an instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] with [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Authentication.</span></span>  
  
 <span data-ttu-id="c10e1-132">**Usa nome utente e password specifici**</span><span class="sxs-lookup"><span data-stu-id="c10e1-132">**Use a specific user name and password**</span></span>  
 <span data-ttu-id="c10e1-133">Consente di connettersi a un'istanza del [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] di [!INCLUDE[ssDE](../../includes/ssde-md.md)] usando l'autenticazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c10e1-133">Connect to an instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="c10e1-134">Questa opzione non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="c10e1-134">This option is not available.</span></span>  
  
 <span data-ttu-id="c10e1-135">**Nome utente**</span><span class="sxs-lookup"><span data-stu-id="c10e1-135">**User name**</span></span>  
 <span data-ttu-id="c10e1-136">Consente di specificare un account di accesso di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] da utilizzare per l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="c10e1-136">Provide a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login to use when authenticating.</span></span> <span data-ttu-id="c10e1-137">Questa opzione non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="c10e1-137">This option is not available.</span></span>  
  
 <span data-ttu-id="c10e1-138">**Password**</span><span class="sxs-lookup"><span data-stu-id="c10e1-138">**Password**</span></span>  
 <span data-ttu-id="c10e1-139">Consente di specificare una password da utilizzare per l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="c10e1-139">Provide a password to use when authenticating.</span></span> <span data-ttu-id="c10e1-140">Questa opzione non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="c10e1-140">This option is not available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c10e1-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c10e1-141">See Also</span></span>  
 <span data-ttu-id="c10e1-142">[Posta elettronica database](../database-mail/database-mail.md) </span><span class="sxs-lookup"><span data-stu-id="c10e1-142">[Database Mail](../database-mail/database-mail.md) </span></span>  
 [<span data-ttu-id="c10e1-143">sp_notify_operator &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c10e1-143">sp_notify_operator &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-notify-operator-transact-sql)  
  
  
