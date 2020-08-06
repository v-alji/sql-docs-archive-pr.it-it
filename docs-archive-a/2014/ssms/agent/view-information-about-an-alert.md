---
title: Visualizzare informazioni su un avviso | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent, alerts
- viewing alerts
- alerts [SQL Server], viewing
- displaying alerts
- status information [SQL Server], alerts
ms.assetid: a0e3a8c4-e3c2-42a5-b2f8-aa06061d3fa6
author: stevestein
ms.author: sstein
ms.openlocfilehash: ee72512a507299e71f13fee689709a9403bb04e4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627026"
---
# <a name="view-information-about-an-alert"></a><span data-ttu-id="5f9b5-102">Visualizzare informazioni su un avviso</span><span class="sxs-lookup"><span data-stu-id="5f9b5-102">View Information About an Alert</span></span>
  <span data-ttu-id="5f9b5-103">In questo argomento viene descritto come visualizzare le informazioni sugli [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] avvisi [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] di Agent in tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5f9b5-103">This topic describes how to view information about [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent alerts in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="5f9b5-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="5f9b5-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="5f9b5-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="5f9b5-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="5f9b5-106">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="5f9b5-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="5f9b5-107">**Per visualizzare informazioni su un avviso utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="5f9b5-107">**To view information about an alert, using:**</span></span>  
  
     [<span data-ttu-id="5f9b5-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5f9b5-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="5f9b5-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5f9b5-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="5f9b5-110">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="5f9b5-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="5f9b5-111">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="5f9b5-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="5f9b5-112">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="5f9b5-112">Permissions</span></span>  
 <span data-ttu-id="5f9b5-113">Per impostazione predefinita, i membri del ruolo predefinito del server **sysadmin** possono visualizzare le informazioni su un avviso.</span><span class="sxs-lookup"><span data-stu-id="5f9b5-113">By default, members of the **sysadmin** fixed server role can view information about an alert.</span></span> <span data-ttu-id="5f9b5-114">Gli altri utenti devono appartenere al ruolo predefinito del database **SQLAgentOperatorRole** nel database **msdb** .</span><span class="sxs-lookup"><span data-stu-id="5f9b5-114">Other users must be granted the **SQLAgentOperatorRole** fixed database role in the **msdb** database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="5f9b5-115">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5f9b5-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-information-about-an-alert"></a><span data-ttu-id="5f9b5-116">Per visualizzare informazioni su un avviso</span><span class="sxs-lookup"><span data-stu-id="5f9b5-116">To view information about an alert</span></span>  
  
1.  <span data-ttu-id="5f9b5-117">In **Esplora oggetti** fare clic sul segno più per espandere il server in cui si desidera visualizzare le informazioni su un avviso.</span><span class="sxs-lookup"><span data-stu-id="5f9b5-117">In **Object Explorer,** click the plus sign to expand the server where you want to view information about an alert.</span></span>  
  
2.  <span data-ttu-id="5f9b5-118">Fare clic sul segno più per espandere **SQL Server Agent**.</span><span class="sxs-lookup"><span data-stu-id="5f9b5-118">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="5f9b5-119">Fare clic sul segno più per espandere la cartella **Avvisi** .</span><span class="sxs-lookup"><span data-stu-id="5f9b5-119">Click the plus sign to expand the **Alerts** folder.</span></span>  
  
4.  <span data-ttu-id="5f9b5-120">Fare clic con il pulsante destro del mouse sull'avviso con le informazioni da visualizzare e selezionare **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="5f9b5-120">Right-click the alert that has the information you want to view and select **Properties**.</span></span>  
  
     <span data-ttu-id="5f9b5-121">Per altre informazioni sulle opzioni disponibili contenute nella finestra di dialogo dell'interfaccia utente nella finestra di dialogo _Proprietà dell'avviso_**nome_avviso** , vedere:</span><span class="sxs-lookup"><span data-stu-id="5f9b5-121">For more information on the available options contained in the _alert_name_**alert properties** dialog box, see:</span></span>  
  
    -   [<span data-ttu-id="5f9b5-122">Proprietà avviso-nuovo avviso &#40;pagina generale&#41;</span><span class="sxs-lookup"><span data-stu-id="5f9b5-122">Alert Properties-New Alert &#40;General Page&#41;</span></span>](../../integration-services/general-page-of-integration-services-designers-options.md)  
  
    -   [<span data-ttu-id="5f9b5-123">Proprietà avviso-pagina nuova risposta avviso &#40;&#41;</span><span class="sxs-lookup"><span data-stu-id="5f9b5-123">Alert Properties-New Alert &#40;Response Page&#41;</span></span>](alert-properties-new-alert-response-page.md)  
  
    -   [<span data-ttu-id="5f9b5-124">Proprietà avviso: nuova pagina Opzioni &#40;avvisi&#41;</span><span class="sxs-lookup"><span data-stu-id="5f9b5-124">Alert Properties: New Alert &#40;Options Page&#41;</span></span>](alert-properties-new-alert-options-page.md)  
  
    -   [<span data-ttu-id="5f9b5-125">Proprietà avviso &#40;pagina Cronologia&#41;</span><span class="sxs-lookup"><span data-stu-id="5f9b5-125">Alert Properties &#40;History Page&#41;</span></span>](alert-properties-history-page.md)  
  
5.  <span data-ttu-id="5f9b5-126">Al termine, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="5f9b5-126">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="5f9b5-127">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5f9b5-127">Using Transact-SQL</span></span>  
  
#### <a name="to-view-information-about-an-alert"></a><span data-ttu-id="5f9b5-128">Per visualizzare informazioni su un avviso</span><span class="sxs-lookup"><span data-stu-id="5f9b5-128">To view information about an alert</span></span>  
  
1.  <span data-ttu-id="5f9b5-129">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5f9b5-129">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="5f9b5-130">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="5f9b5-130">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="5f9b5-131">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="5f9b5-131">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- reports information about the Demo: Sev. 25 Errors alert  
    -- This example assumes that the 'Demo: Sev. 25 Errors' alert exists.  
    USE msdb ;  
    GO  
  
    EXEC sp_help_alert @alert_name = 'Demo: Sev. 25 Errors'  
    GO  
    ```  
  
 <span data-ttu-id="5f9b5-132">Per ulteriori informazioni, vedere [sp_help_alert &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-help-alert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="5f9b5-132">For more information, see [sp_help_alert &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-alert-transact-sql).</span></span>  
  
  
