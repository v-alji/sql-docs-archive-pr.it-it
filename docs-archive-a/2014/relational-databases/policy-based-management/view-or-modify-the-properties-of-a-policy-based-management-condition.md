---
title: Visualizzare o modificare le proprietà di una condizione della gestione basata su criteri | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Policy-Based Management, view policy conditions
- Policy-Based Management, modify policy conditions
ms.assetid: 890d7384-8444-4767-bb6f-f5debb155747
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 08baec48bd13445ef56ea6a29520d23ebaf683b1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626687"
---
# <a name="view-or-modify-the-properties-of-a-policy-based-management-condition"></a><span data-ttu-id="03e29-102">Visualizzare o modificare le proprietà di una condizione della gestione basata su criteri</span><span class="sxs-lookup"><span data-stu-id="03e29-102">View or Modify the Properties of a Policy-Based Management Condition</span></span>
  <span data-ttu-id="03e29-103">In questo argomento verrà descritto come visualizzare o modificare le proprietà di una condizione della gestione basata su criteri in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="03e29-103">This topic describes how to view or modify the properties of a Policy-Based Management condition in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="03e29-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="03e29-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="03e29-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="03e29-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="03e29-106">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="03e29-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="03e29-107">**Per visualizzare o modificare le proprietà di una condizione tramite:**</span><span class="sxs-lookup"><span data-stu-id="03e29-107">**To view or modify a condition's properties, using:**</span></span>  
  
     [<span data-ttu-id="03e29-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="03e29-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="03e29-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="03e29-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="03e29-110">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="03e29-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="03e29-111">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="03e29-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="03e29-112">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="03e29-112">Permissions</span></span>  
 <span data-ttu-id="03e29-113">È necessaria l'appartenenza al ruolo PolicyAdministratorRole nel database msdb.</span><span class="sxs-lookup"><span data-stu-id="03e29-113">Requires membership in the PolicyAdministratorRole role in the msdb database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="03e29-114">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="03e29-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-or-modify-a-conditions-properties"></a><span data-ttu-id="03e29-115">Per visualizzare o modificare le proprietà di una condizione</span><span class="sxs-lookup"><span data-stu-id="03e29-115">To view or modify a condition's properties</span></span>  
  
1.  <span data-ttu-id="03e29-116">In **Esplora oggetti**fare clic sul segno più per espandere il server contenente la condizione da visualizzare o modificare.</span><span class="sxs-lookup"><span data-stu-id="03e29-116">In **Object Explorer**, click the plus sign to expand the server that contains the condition that you want to view or modify.</span></span>  
  
2.  <span data-ttu-id="03e29-117">Fare clic sul segno più per espandere la cartella **Gestione** .</span><span class="sxs-lookup"><span data-stu-id="03e29-117">Click the plus sign to expand the **Management** folder.</span></span>  
  
3.  <span data-ttu-id="03e29-118">Fare clic sul segno più per espandere la cartella **Gestione criteri**.</span><span class="sxs-lookup"><span data-stu-id="03e29-118">Click the plus sign to expand **Policy Management**.</span></span>  
  
4.  <span data-ttu-id="03e29-119">Fare clic sul segno più per espandere la cartella **Condizioni** .</span><span class="sxs-lookup"><span data-stu-id="03e29-119">Click the plus sign to expand the **Conditions** folder.</span></span>  
  
5.  <span data-ttu-id="03e29-120">Fare clic con il pulsante destro del mouse sulla condizione da visualizzare o modificare e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="03e29-120">Right-click the condition that you want to view or edit and select **Properties**.</span></span> <span data-ttu-id="03e29-121">Per altre informazioni sulle opzioni disponibili nella finestra di dialogo **Apri condizione -**_nome_condizione_, vedere [Finestra di dialogo Crea nuova condizione o Apri condizione, pagina Generale](../../integration-services/general-page-of-integration-services-designers-options.md), [Finestra di dialogo Apri condizione, pagina Criteri dipendenti](open-condition-dialog-box-dependent-policies-page.md), [Finestra di dialogo Crea nuova condizione o Apri condizione, pagina Descrizione](create-new-condition-or-open-condition-dialog-box-description-page.md) e [Finestra di dialogo Modifica avanzata &#40;Condizione&#41;](advanced-edit-condition-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="03e29-121">For more information on the available options in the **Open Condition -**_condition_name_ dialog box, see [Create New Condition or Open Condition Dialog Box, General Page](../../integration-services/general-page-of-integration-services-designers-options.md), [Open Condition Dialog Box, Dependent Policies Page](open-condition-dialog-box-dependent-policies-page.md), [Create New Condition or Open Condition Dialog Box, Description Page](create-new-condition-or-open-condition-dialog-box-description-page.md), and [Advanced Edit &#40;Condition&#41; Dialog Box](advanced-edit-condition-dialog-box.md).</span></span>  
  
6.  <span data-ttu-id="03e29-122">Al termine, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="03e29-122">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="03e29-123">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="03e29-123">Using Transact-SQL</span></span>  
  
#### <a name="to-view-a-conditions-properties"></a><span data-ttu-id="03e29-124">Per visualizzare le proprietà di una condizione</span><span class="sxs-lookup"><span data-stu-id="03e29-124">To view a condition's properties</span></span>  
  
1.  <span data-ttu-id="03e29-125">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="03e29-125">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="03e29-126">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="03e29-126">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="03e29-127">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="03e29-127">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE msdb;  
    GO  
    SELECT name,  
       description,  
       facet,  
       expression,  
       is_name_condition,  
       obj_name  
    FROM syspolicy_conditions;  
    GO  
  
    ```  
  
 <span data-ttu-id="03e29-128">Per altre informazioni, vedere [syspolicy_conditions &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/syspolicy-conditions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="03e29-128">For more information, see [syspolicy_conditions &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/syspolicy-conditions-transact-sql).</span></span>  
  
  
