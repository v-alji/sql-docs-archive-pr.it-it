---
title: Visualizzare o modificare le proprietà dei criteri della gestione basata su criteri | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Policy-Based Management, modify policies
- Policy-Based Management, view policies
ms.assetid: ba805504-5db5-4731-a8da-a0e89cb20c37
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: da2226d3049a84098eb8e561635161f73b71ab10
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626688"
---
# <a name="view-or-modify-the-properties-of-a-policy-based-management-policy"></a><span data-ttu-id="7b7f7-102">Visualizzare o modificare le proprietà dei criteri della gestione basata su criteri</span><span class="sxs-lookup"><span data-stu-id="7b7f7-102">View or Modify the Properties of a Policy-Based Management Policy</span></span>
  <span data-ttu-id="7b7f7-103">In questo argomento verrà descritto come visualizzare o modificare le proprietà dei criteri della gestione basata su criteri in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7b7f7-103">This topic describes how to view or modify a Policy-Based Management policy's properties in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="7b7f7-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="7b7f7-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="7b7f7-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="7b7f7-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="7b7f7-106">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="7b7f7-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="7b7f7-107">**Per visualizzare o modificare le proprietà dei criteri tramite:**</span><span class="sxs-lookup"><span data-stu-id="7b7f7-107">**To view or modify a policy's properties, using:**</span></span>  
  
     [<span data-ttu-id="7b7f7-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7b7f7-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="7b7f7-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7b7f7-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="7b7f7-110">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="7b7f7-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="7b7f7-111">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="7b7f7-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="7b7f7-112">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="7b7f7-112">Permissions</span></span>  
 <span data-ttu-id="7b7f7-113">È necessaria l'appartenenza al ruolo PolicyAdministratorRole nel database msdb.</span><span class="sxs-lookup"><span data-stu-id="7b7f7-113">Requires membership in the PolicyAdministratorRole role in the msdb database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="7b7f7-114">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7b7f7-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-the-properties-of-all-policies-on-an-object"></a><span data-ttu-id="7b7f7-115">Per visualizzare le proprietà di tutti i criteri in un oggetto</span><span class="sxs-lookup"><span data-stu-id="7b7f7-115">To view the properties of all policies on an object</span></span>  
  
1.  <span data-ttu-id="7b7f7-116">In Esplora oggetti fare clic con il pulsante destro del mouse su un server, un oggetto server, un database o un oggetto di database, scegliere **Criteri** , quindi fare clic su **Visualizza**.</span><span class="sxs-lookup"><span data-stu-id="7b7f7-116">In Object Explorer, right-click a server, server object, database, or database object, point to **Policies** and select **View**.</span></span> <span data-ttu-id="7b7f7-117">Per altre informazioni sulle opzioni disponibili nella finestra di dialogo **Visualizza criteri -**_nome_oggetto_, vedere [Finestra di dialogo Visualizza criteri](view-policies-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="7b7f7-117">For more information on the available options in the **View Policies -**_object_name_ dialog box, see [View Policies Dialog Box](view-policies-dialog-box.md).</span></span>  
  
2.  <span data-ttu-id="7b7f7-118">Al termine, fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="7b7f7-118">When finished, click **Close**.</span></span>  
  
#### <a name="to-view-or-modify-a-specific-policys-properties"></a><span data-ttu-id="7b7f7-119">Per visualizzare o modificare le proprietà di criteri specifici:</span><span class="sxs-lookup"><span data-stu-id="7b7f7-119">To view or modify a specific policy's properties</span></span>  
  
1.  <span data-ttu-id="7b7f7-120">In **Esplora oggetti**fare clic sul segno più per espandere il server contenente i criteri della gestione basata su criteri da visualizzare o modificare.</span><span class="sxs-lookup"><span data-stu-id="7b7f7-120">In **Object Explorer**, click the plus sign to expand the server that contains the Policy-Based Management policy that you want to view or modify.</span></span>  
  
2.  <span data-ttu-id="7b7f7-121">Fare clic sul segno più per espandere la cartella **Gestione** .</span><span class="sxs-lookup"><span data-stu-id="7b7f7-121">Click the plus sign to expand the **Management** folder.</span></span>  
  
3.  <span data-ttu-id="7b7f7-122">Fare clic sul segno più per espandere la cartella **Gestione criteri**.</span><span class="sxs-lookup"><span data-stu-id="7b7f7-122">Click the plus sign to expand **Policy Management**.</span></span>  
  
4.  <span data-ttu-id="7b7f7-123">Fare clic sul segno più per espandere la cartella **Criteri** .</span><span class="sxs-lookup"><span data-stu-id="7b7f7-123">Click the plus sign to expand the **Policies** folder.</span></span>  
  
5.  <span data-ttu-id="7b7f7-124">Fare clic con il pulsante destro del mouse sui criteri da visualizzare o modificare e selezionare **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="7b7f7-124">Right-click the policy that you want to view or modify and select **Properties**.</span></span> <span data-ttu-id="7b7f7-125">Per altre informazioni sulle opzioni disponibili nella finestra di dialogo **Apri criteri -**_nome_criteri_, vedere [Finestra di dialogo Crea nuovi criteri o Apri criteri, pagina Generale](../../integration-services/general-page-of-integration-services-designers-options.md) e [Finestra di dialogo Crea nuovi criteri o Apri criteri, pagina Descrizione](create-new-policy-or-open-policy-dialog-box-description-page.md).</span><span class="sxs-lookup"><span data-stu-id="7b7f7-125">For more information on the available options in the **Open Policy -**_policy_name_ dialog box, see [Create New Policy or Open Policy Dialog Box, General Page](../../integration-services/general-page-of-integration-services-designers-options.md) and [Create New Policy or Open Policy Dialog Box, Description Page](create-new-policy-or-open-policy-dialog-box-description-page.md).</span></span>  
  
6.  <span data-ttu-id="7b7f7-126">Al termine, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="7b7f7-126">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="7b7f7-127">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7b7f7-127">Using Transact-SQL</span></span>  
  
#### <a name="to-view-a-policys-properties"></a><span data-ttu-id="7b7f7-128">Per visualizzare le proprietà dei criteri</span><span class="sxs-lookup"><span data-stu-id="7b7f7-128">To view a policy's properties</span></span>  
  
1.  <span data-ttu-id="7b7f7-129">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7b7f7-129">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="7b7f7-130">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="7b7f7-130">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="7b7f7-131">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="7b7f7-131">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE msdb;  
    GO  
    SELECT name,  
       execution_mode,  
       description,  
       is_enabled,  
       job_id  
    FROM syspolicy_policies;  
    GO  
    ```  
  
 <span data-ttu-id="7b7f7-132">Per altre informazioni, vedere [syspolicy_policies &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/syspolicy-policies-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="7b7f7-132">For more information, see [syspolicy_policies &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/syspolicy-policies-transact-sql).</span></span>  
  
  
