---
title: Modificare vincoli CHECK | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- CHECK constraints, modifying
- modifying constraints
- constraints [SQL Server], check
- constraints [SQL Server], modifying
ms.assetid: f22daef8-e350-40ef-8ff0-b5f87d1d9e56
author: stevestein
ms.author: sstein
ms.openlocfilehash: 8377c80590612c8b68c315f7c37823eb8f5c5093
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629737"
---
# <a name="modify-check-constraints"></a><span data-ttu-id="4d39f-102">Modifica di vincoli CHECK</span><span class="sxs-lookup"><span data-stu-id="4d39f-102">Modify Check Constraints</span></span>
  <span data-ttu-id="4d39f-103">È possibile modificare un vincolo CHECK in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)] quando si desidera modificare l'espressione del vincolo o le opzioni che lo abilitano o disabilitano al verificarsi di specifiche condizioni.</span><span class="sxs-lookup"><span data-stu-id="4d39f-103">You can modify a check constraint in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)] when you want to change the constraint expression or the options that enable or disable the constraint for specific conditions.</span></span>  
  
 <span data-ttu-id="4d39f-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="4d39f-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="4d39f-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="4d39f-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="4d39f-106">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="4d39f-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="4d39f-107">**Per modificare un vincolo CHECK:**</span><span class="sxs-lookup"><span data-stu-id="4d39f-107">**To modify a check constraint using:**</span></span>  
  
     [<span data-ttu-id="4d39f-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4d39f-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="4d39f-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4d39f-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="4d39f-110">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="4d39f-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="4d39f-111">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="4d39f-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="4d39f-112">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="4d39f-112">Permissions</span></span>  
 <span data-ttu-id="4d39f-113">È necessario disporre dell'autorizzazione ALTER per la tabella.</span><span class="sxs-lookup"><span data-stu-id="4d39f-113">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="4d39f-114">Con SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4d39f-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-modify-a-check-constraint"></a><span data-ttu-id="4d39f-115">Per modificare un vincolo CHECK</span><span class="sxs-lookup"><span data-stu-id="4d39f-115">To modify a check constraint</span></span>  
  
1.  <span data-ttu-id="4d39f-116">In **Esplora oggetti**fare clic con il pulsante destro del mouse sulla tabella che contiene il vincolo CHECK e selezionare **Progetta**.</span><span class="sxs-lookup"><span data-stu-id="4d39f-116">In the **Object Explorer**, right-click the table containing the check constraint and select **Design**.</span></span>  
  
2.  <span data-ttu-id="4d39f-117">Scegliere **Vincoli CHECK** nel menu **Progettazione tabelle**.</span><span class="sxs-lookup"><span data-stu-id="4d39f-117">On the **Table Designer** menu, click **Check Constraints...**.</span></span>  
  
3.  <span data-ttu-id="4d39f-118">Nella finestra di dialogo **Vincoli CHECK** selezionare il vincolo che si desidera modificare in **Vincolo CHECK selezionato**.</span><span class="sxs-lookup"><span data-stu-id="4d39f-118">In the **Check Constraints** dialog box, under **Selected Check Constraint**, select the constraint you wish to edit.</span></span>  
  
4.  <span data-ttu-id="4d39f-119">Completare un'operazione dalla tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="4d39f-119">Complete an action from the following table:</span></span>  
  
    |<span data-ttu-id="4d39f-120">A</span><span class="sxs-lookup"><span data-stu-id="4d39f-120">To</span></span>|<span data-ttu-id="4d39f-121">seguire le operazioni di seguito riportate</span><span class="sxs-lookup"><span data-stu-id="4d39f-121">Follow these steps</span></span>|  
    |--------|------------------------|  
    |<span data-ttu-id="4d39f-122">Modificare l'espressione del vincolo</span><span class="sxs-lookup"><span data-stu-id="4d39f-122">Edit the constraint expression</span></span>|<span data-ttu-id="4d39f-123">Digitare la nuova espressione nel campo **Espressione** .</span><span class="sxs-lookup"><span data-stu-id="4d39f-123">Type the new expression in the **Expression** field.</span></span>|  
    |<span data-ttu-id="4d39f-124">Rinominare il vincolo</span><span class="sxs-lookup"><span data-stu-id="4d39f-124">Rename the constraint</span></span>|<span data-ttu-id="4d39f-125">Digitare un nuovo nome nel campo **Nome** .</span><span class="sxs-lookup"><span data-stu-id="4d39f-125">Type a new name in the **Name** field.</span></span>|  
    |<span data-ttu-id="4d39f-126">Applicare il vincolo a dati esistenti</span><span class="sxs-lookup"><span data-stu-id="4d39f-126">Apply the constraint to existing data</span></span>|<span data-ttu-id="4d39f-127">Selezionare l'opzione **Verifica dati esistenti durante la creazione o l'attivazione** .</span><span class="sxs-lookup"><span data-stu-id="4d39f-127">Select the **Check Existing Data on Creation or Enabling** option.</span></span>|  
    |<span data-ttu-id="4d39f-128">Disabilitare il vincolo in caso di aggiunta di nuovi dati alla tabella o di aggiornamento di dati esistenti nella tabella</span><span class="sxs-lookup"><span data-stu-id="4d39f-128">Disable the constraint when new data is added to the table or when existing data is updated in the table.</span></span>|<span data-ttu-id="4d39f-129">Deselezionare l'opzione **Attiva vincolo per istruzioni INSERT e UPDATE** .</span><span class="sxs-lookup"><span data-stu-id="4d39f-129">Clear the **Enforce Constraint for INSERTs and UPDATEs** option.</span></span>|  
    |<span data-ttu-id="4d39f-130">Disabilitare il vincolo quando un agente di replica accoda o aggiorna dati nella tabella.</span><span class="sxs-lookup"><span data-stu-id="4d39f-130">Disable the constraint when a replication agent inserts or updates data in your table.</span></span>|<span data-ttu-id="4d39f-131">Deselezionare l'opzione **Attiva per replica** .</span><span class="sxs-lookup"><span data-stu-id="4d39f-131">Clear the **Enforce For Replication** option.</span></span>|  
  
    > [!NOTE]  
    >  <span data-ttu-id="4d39f-132">Alcuni database dispongono di funzionalità differenti per i vincoli CHECK.</span><span class="sxs-lookup"><span data-stu-id="4d39f-132">Some databases have different functionality for check constraints.</span></span>  
  
5.  <span data-ttu-id="4d39f-133">Fare clic su **Close**.</span><span class="sxs-lookup"><span data-stu-id="4d39f-133">Click **Close**.</span></span>  
  
6.  <span data-ttu-id="4d39f-134">Scegliere **Salva**_nome tabella_ dal menu **File**.</span><span class="sxs-lookup"><span data-stu-id="4d39f-134">On the **File** menu, click **Save**_table name_.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="4d39f-135">Con Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4d39f-135">Using Transact-SQL</span></span>  
 <span data-ttu-id="4d39f-136">**Per modificare un vincolo CHECK**</span><span class="sxs-lookup"><span data-stu-id="4d39f-136">**To modify a check constraint**</span></span>  
  
 <span data-ttu-id="4d39f-137">Per modificare un vincolo `CHECK` utilizzando [!INCLUDE[tsql](../../includes/tsql-md.md)], è innanzitutto necessario eliminare il vincolo `CHECK` esistente e quindi crearlo di nuovo con la nuova definizione.</span><span class="sxs-lookup"><span data-stu-id="4d39f-137">To modify a `CHECK` constraint using [!INCLUDE[tsql](../../includes/tsql-md.md)], you must first delete the existing `CHECK` constraint and then re-create it with the new definition.</span></span> <span data-ttu-id="4d39f-138">Per altre informazioni, vedere [Eliminazione dei vincoli CHECK](delete-check-constraints.md) e [Creare vincoli CHECK](create-check-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="4d39f-138">For more information, see [Delete Check Constraints](delete-check-constraints.md) and [Create Check Constraints](create-check-constraints.md).</span></span>  
  
###  <a name="TsqlExample"></a>  
