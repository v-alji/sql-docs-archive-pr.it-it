---
title: Concedere un'autorizzazione a un'entità| Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Grant permission to a principal
ms.assetid: 4107389d-05b6-4aa3-9fa8-95b40cdf05dc
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 4256d62bdeac2d79c51e5f3792c991e0e3b15096
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725415"
---
# <a name="grant-a-permission-to-a-principal"></a><span data-ttu-id="f83c7-102">Concedere un'autorizzazione a un'entità</span><span class="sxs-lookup"><span data-stu-id="f83c7-102">Grant a Permission to a Principal</span></span>
  <span data-ttu-id="f83c7-103">In questo argomento viene descritto come concedere un'autorizzazione a un'entità in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f83c7-103">This topic describes how to grant permission to a principal in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="f83c7-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="f83c7-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="f83c7-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="f83c7-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="f83c7-106">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="f83c7-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="f83c7-107">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="f83c7-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="f83c7-108">**Per concedere un'autorizzazione a un'entità utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="f83c7-108">**To grant permission to a principal, using:**</span></span>  
  
     [<span data-ttu-id="f83c7-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f83c7-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="f83c7-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f83c7-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="f83c7-111">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="f83c7-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="f83c7-112">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="f83c7-112">Limitations and Restrictions</span></span>  
 <span data-ttu-id="f83c7-113">Le procedure consigliate riportate di seguito consentono di gestire più facilmente le autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="f83c7-113">Consider the following best practices that can make managing permissions easier.</span></span>  
  
-   <span data-ttu-id="f83c7-114">Concedere autorizzazione a ruoli, anziché a singoli account di accesso o utenti.</span><span class="sxs-lookup"><span data-stu-id="f83c7-114">Grant permission to roles, instead of individual logins or users.</span></span> <span data-ttu-id="f83c7-115">Quando un singolo utente viene sostituito da un altro, rimuovere l'utente che non è più incluso nel ruolo e aggiungere il nuovo utente al ruolo.</span><span class="sxs-lookup"><span data-stu-id="f83c7-115">When one individual is replaced by another, remove the departing individual from the role and add the new individual to the role.</span></span> <span data-ttu-id="f83c7-116">Le numerose autorizzazioni eventualmente associate al ruolo saranno automaticamente disponibili per il nuovo utente.</span><span class="sxs-lookup"><span data-stu-id="f83c7-116">The many permissions that might be associated with the role will automatically be available to the new individual.</span></span> <span data-ttu-id="f83c7-117">Se diverse persone in un'organizzazione richiedono le stesse autorizzazioni, l'aggiunta di ciascuna persona al ruolo comporterà la concessione automatica delle stesse autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="f83c7-117">If several people in an organization require the same permissions, adding each of them to the role will grant them the same permissions.</span></span>  
  
-   <span data-ttu-id="f83c7-118">Configurare entità a protezione diretta simili, quali tabelle, viste e procedure, come di proprietà di uno schema, quindi concedere le autorizzazioni allo schema.</span><span class="sxs-lookup"><span data-stu-id="f83c7-118">Configure similar securables (tables, views, and procedures) to be owned by a schema, then grant permissions to the schema.</span></span> <span data-ttu-id="f83c7-119">Ad esempio, lo schema del libro paga potrebbe possedere diverse tabelle, viste e stored procedure.</span><span class="sxs-lookup"><span data-stu-id="f83c7-119">For example, the payroll schema might own several tables, views, and stored procedures.</span></span> <span data-ttu-id="f83c7-120">Concedendo l'accesso allo schema, verranno concesse simultaneamente tutte le necessarie autorizzazioni per eseguire la funzione di retribuzione.</span><span class="sxs-lookup"><span data-stu-id="f83c7-120">By granting access to the schema, all the necessary permissions to perform the payroll function can be granted at the same time.</span></span> <span data-ttu-id="f83c7-121">Per ulteriori informazioni sulle entità a protezione diretta a cui è possibile concedere le autorizzazioni, vedere [Securables](../securables.md).</span><span class="sxs-lookup"><span data-stu-id="f83c7-121">For more information about what securables can be granted permissions, see [Securables](../securables.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="f83c7-122">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="f83c7-122">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="f83c7-123">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="f83c7-123">Permissions</span></span>  
 <span data-ttu-id="f83c7-124">L'utente che concede le autorizzazioni (o l'entità specificata con l'opzione AS) deve disporre della relativa autorizzazione con GRANT OPTION oppure di un'autorizzazione di livello superiore che include l'autorizzazione che viene concessa.</span><span class="sxs-lookup"><span data-stu-id="f83c7-124">The grantor (or the principal specified with the AS option) must have either the permission itself with GRANT OPTION or a higher permission that implies the permission being granted.</span></span> <span data-ttu-id="f83c7-125">I membri del ruolo predefinito del server **sysadmin** possono concedere qualsiasi autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="f83c7-125">Members of the **sysadmin** fixed server role can grant any permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="f83c7-126">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f83c7-126">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-grant-permission-to-a-principal"></a><span data-ttu-id="f83c7-127">Per concedere un'autorizzazione a un'entità</span><span class="sxs-lookup"><span data-stu-id="f83c7-127">To grant permission to a principal</span></span>  
  
1.  <span data-ttu-id="f83c7-128">In Esplora oggetti espandere il database contenente l'oggetto a cui si desiderano concedere autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="f83c7-128">In Object Explorer, expand the database that contains the object to which you want to grant permissions.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f83c7-129">In questi passaggi viene trattata specificatamente la concessione delle autorizzazioni a una stored procedure, ma è possibile utilizzare passaggi simili per aggiungere autorizzazioni a tabelle, viste, funzioni e assembly e altre entità a protezione diretta.</span><span class="sxs-lookup"><span data-stu-id="f83c7-129">These steps deal specifically with granting permissions to a stored procedure, but you can use similar steps to add permissions to tables, views, functions, and assemblies, as well as other securables.</span></span> <span data-ttu-id="f83c7-130">Per altre informazioni, vedere [GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="f83c7-130">For more information, see [GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql)</span></span>  
  
2.  <span data-ttu-id="f83c7-131">Espandere la cartella **Programmabilità** .</span><span class="sxs-lookup"><span data-stu-id="f83c7-131">Expand the **Programmability** folder.</span></span>  
  
3.  <span data-ttu-id="f83c7-132">Espandere la cartella **Stored procedure** .</span><span class="sxs-lookup"><span data-stu-id="f83c7-132">Expand the **Stored Procedures** folder.</span></span>  
  
4.  <span data-ttu-id="f83c7-133">Fare clic con il pulsante destro del mouse su una stored procedure e selezionare **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="f83c7-133">Right-click a stored procedure and select **Properties**.</span></span>  
  
5.  <span data-ttu-id="f83c7-134">In selezione pagina nella finestra di dialogo **proprietà stored procedure-**_stored_procedure_name_ Selezionare **autorizzazioni**.</span><span class="sxs-lookup"><span data-stu-id="f83c7-134">In the **Stored Procedure Properties -**_stored_procedure_name_ dialog box, under select a page, select **Permissions**.</span></span> <span data-ttu-id="f83c7-135">Utilizzare questa pagina per aggiungere utenti o ruoli alla stored procedure e specificare le autorizzazioni degli utenti o dei ruoli.</span><span class="sxs-lookup"><span data-stu-id="f83c7-135">Use this page to add users or roles to the stored procedure and specify the permissions those users or roles have.</span></span>  
  
6.  <span data-ttu-id="f83c7-136">Al termine, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="f83c7-136">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="f83c7-137">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f83c7-137">Using Transact-SQL</span></span>  
  
#### <a name="to-grant-permission-to-a-principal"></a><span data-ttu-id="f83c7-138">Per concedere un'autorizzazione a un'entità</span><span class="sxs-lookup"><span data-stu-id="f83c7-138">To grant permission to a principal</span></span>  
  
1.  <span data-ttu-id="f83c7-139">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f83c7-139">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="f83c7-140">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="f83c7-140">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="f83c7-141">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="f83c7-141">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Grants EXECUTE permission on stored procedure HumanResources.uspUpdateEmployeeHireInfo to an application role called Recruiting11.   
    USE AdventureWorks2012;  
    GO  
    GRANT EXECUTE ON OBJECT::HumanResources.uspUpdateEmployeeHireInfo  
        TO Recruiting11;  
    GO  
    ```  
  
 <span data-ttu-id="f83c7-142">Per altre informazioni, vedere [GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql) e [GRANT - autorizzazioni per oggetti &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-object-permissions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="f83c7-142">For more information, see [GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql) and [GRANT Object Permissions &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-object-permissions-transact-sql).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f83c7-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f83c7-143">See Also</span></span>  
 [<span data-ttu-id="f83c7-144">Entità &#40;motore di database&#41;</span><span class="sxs-lookup"><span data-stu-id="f83c7-144">Principals &#40;Database Engine&#41;</span></span>](principals-database-engine.md)  
  
  
