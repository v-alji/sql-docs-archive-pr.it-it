---
title: Visualizzare le informazioni relative a un operatore | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent jobs, operators
- viewing operators
- operators (users) [Database Engine], viewing with Management Studio
- jobs [SQL Server Agent], operators
- notifications [SQL Server], job status
- displaying operators
ms.assetid: 92c82cdf-f704-444e-9539-82aea7fe6fb7
author: stevestein
ms.author: sstein
ms.openlocfilehash: 680b90401f800a9c435bdae33b8e55385541cc4c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627023"
---
# <a name="view-information-about-an-operator"></a><span data-ttu-id="10541-102">Visualizzazione delle informazioni relative a un operatore</span><span class="sxs-lookup"><span data-stu-id="10541-102">View Information About an Operator</span></span>
  <span data-ttu-id="10541-103">In questo argomento viene descritto come visualizzare le informazioni relative a un [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] operatore di Agent in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="10541-103">This topic describes how to view information about a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent operator in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="10541-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="10541-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="10541-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="10541-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="10541-106">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="10541-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="10541-107">**Per visualizzare le informazioni relative a un operatore utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="10541-107">**To view information about an operator, using:**</span></span>  
  
     [<span data-ttu-id="10541-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="10541-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="10541-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="10541-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="10541-110">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="10541-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="10541-111">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="10541-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="10541-112">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="10541-112">Permissions</span></span>  
 <span data-ttu-id="10541-113">Per impostazione predefinita, questa stored procedure può essere eseguita dai membri del ruolo predefinito del server **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="10541-113">By default, members of the **sysadmin** fixed server role can execute this stored procedure.</span></span> <span data-ttu-id="10541-114">Gli altri utenti devono essere membri di uno dei ruoli predefiniti del database di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent seguenti nel database **msdb** :</span><span class="sxs-lookup"><span data-stu-id="10541-114">Other users must be granted one of the following [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent fixed database roles in the **msdb** database:</span></span>  
  
-   <span data-ttu-id="10541-115">**SQLAgentUserRole**</span><span class="sxs-lookup"><span data-stu-id="10541-115">**SQLAgentUserRole**</span></span>  
  
-   <span data-ttu-id="10541-116">**SQLAgentReaderRole**</span><span class="sxs-lookup"><span data-stu-id="10541-116">**SQLAgentReaderRole**</span></span>  
  
-   <span data-ttu-id="10541-117">**SQLAgentOperatorRole**</span><span class="sxs-lookup"><span data-stu-id="10541-117">**SQLAgentOperatorRole**</span></span>  
  
 <span data-ttu-id="10541-118">Per informazioni dettagliate sulle autorizzazioni di questi ruoli, vedere [Ruoli di database predefiniti di SQL Server Agent](sql-server-agent-fixed-database-roles.md).</span><span class="sxs-lookup"><span data-stu-id="10541-118">For details about the permissions of these roles, see [SQL Server Agent Fixed Database Roles](sql-server-agent-fixed-database-roles.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="10541-119">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="10541-119">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-information-about-an-operator"></a><span data-ttu-id="10541-120">Per visualizzare le informazioni relative a un operatore</span><span class="sxs-lookup"><span data-stu-id="10541-120">To view information about an operator</span></span>  
  
1.  <span data-ttu-id="10541-121">In **Esplora oggetti**fare clic sul segno più per espandere il server che contiene l'operatore da visualizzare.</span><span class="sxs-lookup"><span data-stu-id="10541-121">In **Object Explorer**, click the plus sign to expand the server that contains the operator you want to view.</span></span>  
  
2.  <span data-ttu-id="10541-122">Fare clic sul segno più per espandere **SQL Server Agent**.</span><span class="sxs-lookup"><span data-stu-id="10541-122">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="10541-123">Fare clic sul segno più per espandere la cartella **Operatori** .</span><span class="sxs-lookup"><span data-stu-id="10541-123">Click the plus sign to expand the **Operators** folder.</span></span>  
  
4.  <span data-ttu-id="10541-124">Fare clic con il pulsante destro del mouse sull'operatore da visualizzare e selezionare **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="10541-124">Right-click the operator that you want to view and select **Properties**.</span></span>  
  
     <span data-ttu-id="10541-125">Per altre informazioni sulle opzioni disponibili contenute nella finestra di dialogo _Proprietà_**nome_operatore** , vedere:</span><span class="sxs-lookup"><span data-stu-id="10541-125">For more information on the available options contained in the _operator_name_**Properties** dialog box, see:</span></span>  
  
    -   [<span data-ttu-id="10541-126">Proprietà operatore e nuovo operatore &#40;pagina generale&#41;</span><span class="sxs-lookup"><span data-stu-id="10541-126">Operator Properties and New Operator &#40;General Page&#41;</span></span>](../../integration-services/general-page-of-integration-services-designers-options.md)  
  
    -   [<span data-ttu-id="10541-127">Proprietà operatore: pagina nuove notifiche operatore &#40;&#41;</span><span class="sxs-lookup"><span data-stu-id="10541-127">Operator Properties: New Operator &#40;Notifications Page&#41;</span></span>](operator-properties-new-operator-notifications-page.md)  
  
    -   [<span data-ttu-id="10541-128">Proprietà operatore &#40;pagina Cronologia&#41;</span><span class="sxs-lookup"><span data-stu-id="10541-128">Operator Properties &#40;History Page&#41;</span></span>](operator-properties-history-page.md)  
  
5.  <span data-ttu-id="10541-129">Al termine, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="10541-129">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="10541-130">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="10541-130">Using Transact-SQL</span></span>  
  
#### <a name="to-view-information-about-an-operator"></a><span data-ttu-id="10541-131">Per visualizzare le informazioni relative a un operatore</span><span class="sxs-lookup"><span data-stu-id="10541-131">To view information about an operator</span></span>  
  
1.  <span data-ttu-id="10541-132">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="10541-132">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="10541-133">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="10541-133">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="10541-134">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="10541-134">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- reports information about operator Fran??ois Ajenstat   
    -- This example assumes that the operator exists.  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_help_operator  
        @operator_name = N'Fran??ois Ajenstat' ;  
    GO  
    ```  
  
 <span data-ttu-id="10541-135">Per ulteriori informazioni, vedere [sp_help_operator &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-help-operator-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="10541-135">For more information, see [sp_help_operator &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-operator-transact-sql).</span></span>  
  
  
