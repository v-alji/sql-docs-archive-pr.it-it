---
title: Configurare un utente per la creazione e la gestione di processi di SQL Server Agent | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent jobs, user configuration
- jobs [SQL Server Agent], user configuration
- SQLAgentUserRole database role
- proxy accounts [SQL Server Agent]
ms.assetid: 67897e3e-b7d0-43dd-a2e2-2840ec4dd1ef
author: stevestein
ms.author: sstein
ms.openlocfilehash: 83313389b3b872004fb23b0babdad19cfb5b8e7d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637584"
---
# <a name="configure-a-user-to-create-and-manage-sql-server-agent-jobs"></a><span data-ttu-id="3e6b7-102">Configure a User to Create and Manage SQL Server Agent Jobs</span><span class="sxs-lookup"><span data-stu-id="3e6b7-102">Configure a User to Create and Manage SQL Server Agent Jobs</span></span>
  <span data-ttu-id="3e6b7-103">In questo argomento viene descritto come configurare un utente per la creazione o l'esecuzione di [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] processi di Agent.</span><span class="sxs-lookup"><span data-stu-id="3e6b7-103">This topic describes how to configure a user to create or execute [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs.</span></span>  
  
-   <span data-ttu-id="3e6b7-104">**Prima di iniziare:**  [Sicurezza](#Security)</span><span class="sxs-lookup"><span data-stu-id="3e6b7-104">**Before you begin:**  [Security](#Security)</span></span>  
  
-   <span data-ttu-id="3e6b7-105">**Per configurare un utente per la creazione e la gestione di processi di SQL Server Agent tramite**  [SQL Server Management Studio](#SSMS)</span><span class="sxs-lookup"><span data-stu-id="3e6b7-105">**To configure a user to create and manage SQL Server Agent jobs, using:**  [SQL Server Management Studio](#SSMS)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="3e6b7-106">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="3e6b7-106">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="3e6b7-107">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="3e6b7-107">Security</span></span>  
 <span data-ttu-id="3e6b7-108">Per configurare un utente per la creazione o l'esecuzione di [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] processi di Agent, è innanzitutto necessario aggiungere un account di accesso SQL Server esistente o un ruolo msdb a uno dei ruoli predefiniti del [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database di Agent seguenti nel database msdb: SQLAgentUserRole, SQLAgentReaderRole o SQLAgentOperatorRole.</span><span class="sxs-lookup"><span data-stu-id="3e6b7-108">To configure a user to create or execute [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs, you must first add an existing SQL Server login or msdb role to one of the following [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent fixed database roles in the msdb database: SQLAgentUserRole, SQLAgentReaderRole, or SQLAgentOperatorRole.</span></span>  
  
 <span data-ttu-id="3e6b7-109">Per impostazione predefinita, i membri di questi ruoli del database possono creare passaggi di processo personalizzati ed eseguirli con il proprio account.</span><span class="sxs-lookup"><span data-stu-id="3e6b7-109">By default, members of these database roles can create their own job steps that run as themselves.</span></span> <span data-ttu-id="3e6b7-110">Per eseguire processi che includono altri tipi di passaggi, ad esempio pacchetti [!INCLUDE[ssIS](../../includes/ssis-md.md)] , questi utenti non amministrativi dovranno avere accesso a un account proxy.</span><span class="sxs-lookup"><span data-stu-id="3e6b7-110">If these non-administrative users want to run jobs that execute other job step types (for example, [!INCLUDE[ssIS](../../includes/ssis-md.md)] packages), they will need to have access to a proxy account.</span></span> <span data-ttu-id="3e6b7-111">Tutti i membri del ruolo predefinito del server sysadmin dispongono dell'autorizzazione per la creazione, la modifica e l'eliminazione degli account proxy.</span><span class="sxs-lookup"><span data-stu-id="3e6b7-111">All members of the sysadmin fixed server role have permission to create, modify, and delete proxy accounts.</span></span> <span data-ttu-id="3e6b7-112">Per altre informazioni sulle autorizzazioni associate con questi ruoli di database predefiniti di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent, vedere [Ruoli di database predefiniti di SQL Server Agent](sql-server-agent-fixed-database-roles.md).</span><span class="sxs-lookup"><span data-stu-id="3e6b7-112">For more information about the permissions that are associated with these [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent fixed database roles, see [SQL Server Agent Fixed Database Roles](sql-server-agent-fixed-database-roles.md).</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="3e6b7-113">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="3e6b7-113">Permissions</span></span>  
 <span data-ttu-id="3e6b7-114">Per informazioni dettagliate, vedere [Implementazione della sicurezza di SQL Server Agent](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="3e6b7-114">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="3e6b7-115">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3e6b7-115">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="3e6b7-116">**Per aggiungere un account di accesso SQL o un ruolo msdb a un ruolo predefinito del database di SQL Server Agent**</span><span class="sxs-lookup"><span data-stu-id="3e6b7-116">**To add a SQL login or msdb role to a SQL Server Agent fixed database role**</span></span>  
  
1.  <span data-ttu-id="3e6b7-117">Espandere un server in **Esplora oggetti**.</span><span class="sxs-lookup"><span data-stu-id="3e6b7-117">In **Object Explorer**, expand a server.</span></span>  
  
2.  <span data-ttu-id="3e6b7-118">Espandere **Sicurezza**e quindi **Account di accesso**.</span><span class="sxs-lookup"><span data-stu-id="3e6b7-118">Expand **Security**, and then expand **Logins**.</span></span>  
  
3.  <span data-ttu-id="3e6b7-119">Fare clic con il pulsante destro del mouse sull'account di accesso che si vuole aggiungere al ruolo predefinito del database di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="3e6b7-119">Right-click the login you wish to add to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent fixed database role, and select **Properties**.</span></span>  
  
4.  <span data-ttu-id="3e6b7-120">Nella pagina **mapping utenti** della finestra di dialogo **Proprietà account di accesso** Selezionare la riga contenente `msdb` .</span><span class="sxs-lookup"><span data-stu-id="3e6b7-120">On the **User Mapping** page of the **Login Properties** dialog box, select the row containing `msdb`.</span></span>  
  
5.  <span data-ttu-id="3e6b7-121">Nell'area **Appartenenza a ruoli del database per: msdb**selezionare il ruolo predefinito del database di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="3e6b7-121">Under **Database role membership for: msdb**, check the appropriate [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent fixed database role.</span></span>  
  
 <span data-ttu-id="3e6b7-122">**Per configurare un account proxy per la creazione e la gestione dei passaggi di processo di SQL Server Agent**</span><span class="sxs-lookup"><span data-stu-id="3e6b7-122">**To configure a proxy account to create and manage SQL Server Agent job steps**</span></span>  
  
1.  <span data-ttu-id="3e6b7-123">Espandere un server in **Esplora oggetti**.</span><span class="sxs-lookup"><span data-stu-id="3e6b7-123">In **Object Explorer**, expand a server.</span></span>  
  
2.  <span data-ttu-id="3e6b7-124">Espandere **SQL Server Agent**.</span><span class="sxs-lookup"><span data-stu-id="3e6b7-124">Expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="3e6b7-125">Fare clic con il pulsante destro del mouse su **Proxy** e scegliere **Nuovo proxy**.</span><span class="sxs-lookup"><span data-stu-id="3e6b7-125">Right-click **Proxies** and select **New Proxy**.</span></span>  
  
4.  <span data-ttu-id="3e6b7-126">Nella pagina **Generale** della finestra **Nuovo account proxy** specificare il nome del proxy, il nome delle credenziali e la descrizione per il nuovo proxy.</span><span class="sxs-lookup"><span data-stu-id="3e6b7-126">On the **General** page of the **New Proxy Account** dialog, specify the proxy name, credential name, and description for the new proxy.</span></span> <span data-ttu-id="3e6b7-127">Si noti che prima di creare un proxy di SQL Server Agent, è necessario innanzitutto creare le credenziali.</span><span class="sxs-lookup"><span data-stu-id="3e6b7-127">Note that you must create a credential first before creating a SQL Server Agent proxy.</span></span> <span data-ttu-id="3e6b7-128">Per ulteriori informazioni sulla creazione di una credenziale, vedere [creare una](../../relational-databases/security/authentication-access/create-a-credential.md) credenziale e [creare credenziali &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-credential-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="3e6b7-128">For more information about creating a credential, see [Create a Credential](../../relational-databases/security/authentication-access/create-a-credential.md) and [CREATE CREDENTIAL &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-credential-transact-sql).</span></span>  
  
5.  <span data-ttu-id="3e6b7-129">Selezionare i sottosistemi appropriati per il proxy.</span><span class="sxs-lookup"><span data-stu-id="3e6b7-129">Check the appropriate subsystems for this proxy.</span></span>  
  
6.  <span data-ttu-id="3e6b7-130">Nella pagina **Entità** aggiungere o rimuovere account di accesso oppure ruoli per concedere o negare l'accesso all'account proxy.</span><span class="sxs-lookup"><span data-stu-id="3e6b7-130">On the **Principals** page, add or remove logins or roles to grant or remove access to the proxy account.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e6b7-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3e6b7-131">See Also</span></span>  
 [<span data-ttu-id="3e6b7-132">Implementazione della sicurezza di SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="3e6b7-132">Implement SQL Server Agent Security</span></span>](implement-sql-server-agent-security.md)  
  
  
