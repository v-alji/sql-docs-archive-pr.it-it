---
title: Account di accesso per sottoscrizioni aggiornabili | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.newsubwizard.updatablesubscriptionslogin.f1
ms.assetid: 301ea227-0455-40ba-9009-d38f8676b325
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6a5cc9190c77f506b13ba8b5fba0e32d5a925570
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723687"
---
# <a name="login-for-updatable-subscriptions"></a><span data-ttu-id="48ec5-102">Account di accesso per sottoscrizioni aggiornabili</span><span class="sxs-lookup"><span data-stu-id="48ec5-102">Login for Updatable Subscriptions</span></span>
  <span data-ttu-id="48ec5-103">Se si seleziona **Replica** nella pagina **Sottoscrizioni aggiornabili** di questa procedura guidata è necessario specificare un account nel Sottoscrittore nel cui contesto vengono stabilite le connessioni al server di pubblicazione per sottoscrizioni ad aggiornamento immediato.</span><span class="sxs-lookup"><span data-stu-id="48ec5-103">If you selected **Replicate** on the **Updatable Subscriptions** page of this wizard, you must specify an account at the Subscriber under which connections to the Publisher are made for immediate updating subscriptions.</span></span> <span data-ttu-id="48ec5-104">Le connessioni vengono utilizzate dai trigger che si attivano presso il Sottoscrittore e propagano le modifiche al server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="48ec5-104">Connections are used by the triggers that fire at the Subscriber and propagate changes to the Publisher.</span></span> <span data-ttu-id="48ec5-105">Questo account è necessario anche se si seleziona **Accoda le modifiche ed esegui il commit appena possibile** nella pagina **Sottoscrizioni aggiornabili** , perché per impostazione predefinita la Creazione guidata nuova sottoscrizione configura gli aggiornamenti in coda con la possibilità di passare, se necessario, ad aggiornamenti immediati.</span><span class="sxs-lookup"><span data-stu-id="48ec5-105">This account is required even if you selected **Queue changes and commit when possible** on the **Updatable Subscriptions** page, because by default the New Subscription Wizard configures queued updating with the ability to switch to immediate updating if required.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="48ec5-106">È consigliabile concedere all'account specificato per la connessione solo le autorizzazioni necessarie per l'inserimento, l'aggiornamento e l'eliminazione dei dati delle viste create dalla replica nel database di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="48ec5-106">The account specified for the connection should only be granted permission to insert, update, and delete data on the views that replication creates in the publication database; it should not be given any additional permissions.</span></span> <span data-ttu-id="48ec5-107">Concedere autorizzazioni nelle viste del database di pubblicazione con il formato dei nomi **syncobj_** _\<HexadecimalNumber>_ all'account configurato presso ogni Sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="48ec5-107">Grant permissions on views in the publication database that are named in the form **syncobj_**_\<HexadecimalNumber>_ to the account you configured at each Subscriber.</span></span>  
  
 <span data-ttu-id="48ec5-108">Sono disponibili tre opzioni per il tipo di connessione:</span><span class="sxs-lookup"><span data-stu-id="48ec5-108">There are three options available for the type of connection:</span></span>  
  
-   <span data-ttu-id="48ec5-109">Un server collegato o remoto già definito.</span><span class="sxs-lookup"><span data-stu-id="48ec5-109">A linked server or remote server that you have already defined.</span></span>  
  
-   <span data-ttu-id="48ec5-110">Un server collegato creato dalla replica. La connessione viene eseguita con le credenziali specificate in questa procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="48ec5-110">A linked server that replication creates; the connection is made with the credentials you specify in this wizard.</span></span>  
  
-   <span data-ttu-id="48ec5-111">Un server collegato creato dalla replica. La connessione viene eseguita con le credenziali dell'utente che apporta la modifica presso il Sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="48ec5-111">A linked server that replication creates; the connection is made with the credentials of the user making the change at the Subscriber.</span></span>  
  
 <span data-ttu-id="48ec5-112">In questa procedura guidata è possibile specificare le prime due opzioni.</span><span class="sxs-lookup"><span data-stu-id="48ec5-112">The first two options can be specified in this wizard.</span></span> <span data-ttu-id="48ec5-113">L'ultima opzione può essere specificata solo utilizzando [sp_link_publication &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-link-publication-transact-sql); specificare il valore **1** per il parametro **@security_mode** .</span><span class="sxs-lookup"><span data-stu-id="48ec5-113">The last option can only be specified using [sp_link_publication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-link-publication-transact-sql); specify a value of **1** for the parameter **@security_mode**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="48ec5-114">Opzioni</span><span class="sxs-lookup"><span data-stu-id="48ec5-114">Options</span></span>  
 <span data-ttu-id="48ec5-115">**Crea un server collegato che stabilisce la connessione utilizzando l'autenticazione di SQL Server**</span><span class="sxs-lookup"><span data-stu-id="48ec5-115">**Create a linked server that connects using the following SQL Server Authentication login:**</span></span>  
 <span data-ttu-id="48ec5-116">La replica crea un server collegato utilizzando le credenziali specificate nei campi **Nome account di accesso** e **Password** .</span><span class="sxs-lookup"><span data-stu-id="48ec5-116">Replication creates a linked server using the credentials specified in the **Login** and **Password** fields.</span></span>  
  
 <span data-ttu-id="48ec5-117">**Accesso**</span><span class="sxs-lookup"><span data-stu-id="48ec5-117">**Login**</span></span>  
 <span data-ttu-id="48ec5-118">Consente di immettere un account di accesso di [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] che dispone solo delle autorizzazioni descritte in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="48ec5-118">Enter a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login that has only the permissions described in this topic.</span></span>  
  
 <span data-ttu-id="48ec5-119">**Password**</span><span class="sxs-lookup"><span data-stu-id="48ec5-119">**Password**</span></span>  
 <span data-ttu-id="48ec5-120">Consente di immettere una password complessa per l'account di accesso specificato nel campo **Nome account di accesso**.</span><span class="sxs-lookup"><span data-stu-id="48ec5-120">Enter a strong password for the login specified in **Login**.</span></span>  
  
 <span data-ttu-id="48ec5-121">**Conferma password**</span><span class="sxs-lookup"><span data-stu-id="48ec5-121">**Confirm Password**</span></span>  
 <span data-ttu-id="48ec5-122">Consente di immettere nuovamente la password per confermarla.</span><span class="sxs-lookup"><span data-stu-id="48ec5-122">Re-enter the password to confirm that it was entered correctly.</span></span>  
  
 <span data-ttu-id="48ec5-123">**Usa un server collegato o remoto già definito**</span><span class="sxs-lookup"><span data-stu-id="48ec5-123">**Use a linked server or remote server that you have already defined.**</span></span>  
 <span data-ttu-id="48ec5-124">Per questa opzione è necessario un server collegato o remoto già definito.</span><span class="sxs-lookup"><span data-stu-id="48ec5-124">This option requires a linked server or remote server that you have already defined.</span></span> <span data-ttu-id="48ec5-125">Per altre informazioni, vedere [Server collegati &#40;motore di database&#41;](../linked-servers/linked-servers-database-engine.md) e [Server remoti](../../database-engine/configure-windows/remote-servers.md).</span><span class="sxs-lookup"><span data-stu-id="48ec5-125">For more information, see [Linked Servers &#40;Database Engine&#41;](../linked-servers/linked-servers-database-engine.md) and [Remote Servers](../../database-engine/configure-windows/remote-servers.md).</span></span> <span data-ttu-id="48ec5-126">Accertarsi che l'account di accesso utilizzato per il server collegato o remoto disponga di una password complessa e delle sole autorizzazioni descritte in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="48ec5-126">Ensure that the login used for the linked server or remote server has a strong password and has only the permissions described in this topic.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48ec5-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="48ec5-127">See Also</span></span>  
 <span data-ttu-id="48ec5-128">[Create an Updatable Subscription to a Transactional Publication](publish/create-an-updatable-subscription-to-a-transactional-publication.md) </span><span class="sxs-lookup"><span data-stu-id="48ec5-128">[Create an Updatable Subscription to a Transactional Publication](publish/create-an-updatable-subscription-to-a-transactional-publication.md) </span></span>  
 <span data-ttu-id="48ec5-129">[Visualizzare e modificare le impostazioni di sicurezza della replica](security/view-and-modify-replication-security-settings.md) </span><span class="sxs-lookup"><span data-stu-id="48ec5-129">[View and Modify Replication Security Settings](security/view-and-modify-replication-security-settings.md) </span></span>  
 <span data-ttu-id="48ec5-130">[Updatable Subscriptions for Transactional Replication](transactional/updatable-subscriptions-for-transactional-replication.md) </span><span class="sxs-lookup"><span data-stu-id="48ec5-130">[Updatable Subscriptions for Transactional Replication](transactional/updatable-subscriptions-for-transactional-replication.md) </span></span>  
 [<span data-ttu-id="48ec5-131">Sottoscrizione delle pubblicazioni</span><span class="sxs-lookup"><span data-stu-id="48ec5-131">Subscribe to Publications</span></span>](subscribe-to-publications.md)  
  
  
