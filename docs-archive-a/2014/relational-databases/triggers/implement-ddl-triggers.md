---
title: Implementare trigger DDL | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- DDL triggers, implementing
ms.assetid: f44e5340-1d18-40e9-828e-0ffcca091ae3
author: rothja
ms.author: jroth
ms.openlocfilehash: 110e69aca31df75d4b4d7a732de5c58556bd3e24
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637132"
---
# <a name="implement-ddl-triggers"></a><span data-ttu-id="5085f-102">Implementazione di trigger DDL</span><span class="sxs-lookup"><span data-stu-id="5085f-102">Implement DDL Triggers</span></span>
  <span data-ttu-id="5085f-103">In questo argomento vengono fornite informazioni sulla creazione, la modifica, la disabilitazione o l'eliminazione di trigger DDL.</span><span class="sxs-lookup"><span data-stu-id="5085f-103">This topic provides information to help you create DDL triggers, modify DDL triggers, and disable or drop DDL triggers.</span></span>  
  
## <a name="creating-ddl-triggers"></a><span data-ttu-id="5085f-104">Creazione di trigger DDL</span><span class="sxs-lookup"><span data-stu-id="5085f-104">Creating DDL Triggers</span></span>  
 <span data-ttu-id="5085f-105">I trigger DDL vengono creati mediante l'istruzione [!INCLUDE[tsql](../../includes/tsql-md.md)] CREATE TRIGGER per trigger DDL.</span><span class="sxs-lookup"><span data-stu-id="5085f-105">DDL triggers are created by using the [!INCLUDE[tsql](../../includes/tsql-md.md)] CREATE TRIGGER statement for DDL triggers.</span></span>  
  
 <span data-ttu-id="5085f-106">**Per creare un trigger DDL**</span><span class="sxs-lookup"><span data-stu-id="5085f-106">**To create a DDL trigger**</span></span>  
  
-   [<span data-ttu-id="5085f-107">CREATE TRIGGER &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="5085f-107">CREATE TRIGGER &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-trigger-transact-sql)  
  
> [!IMPORTANT]  
>  <span data-ttu-id="5085f-108">La restituzione di set di risultati dai trigger verrà rimossa a partire da una delle prossime versioni di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5085f-108">The ability to return result sets from triggers will be removed in a future version of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="5085f-109">I trigger che restituiscono set di risultati possono provocare comportamenti imprevisti nelle applicazioni che non sono state progettate per il loro utilizzo.</span><span class="sxs-lookup"><span data-stu-id="5085f-109">Triggers that return result sets may cause unexpected behavior in applications that are not designed to work with them.</span></span> <span data-ttu-id="5085f-110">Evitare di restituire set di risultati dai trigger in un nuovo progetto di sviluppo e prevedere interventi di modifica nelle applicazioni che attualmente li restituiscono.</span><span class="sxs-lookup"><span data-stu-id="5085f-110">Avoid returning result sets from triggers in new development work, and plan to modify applications that currently do this.</span></span> <span data-ttu-id="5085f-111">Per impedire che i trigger restituiscano set di risultati in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], impostare l'opzione [Disallow Results From Triggers](../../database-engine/configure-windows/disallow-results-from-triggers-server-configuration-option.md) su 1.</span><span class="sxs-lookup"><span data-stu-id="5085f-111">To prevent triggers from returning result sets in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], set the [disallow results from triggers Option](../../database-engine/configure-windows/disallow-results-from-triggers-server-configuration-option.md) to 1.</span></span> <span data-ttu-id="5085f-112">L'impostazione predefinita per questa opzione sarà 1 nella prossima versione di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5085f-112">The default setting of this option will be 1 in a future version of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="modifying-ddl-triggers"></a><span data-ttu-id="5085f-113">Modifica di trigger DDL</span><span class="sxs-lookup"><span data-stu-id="5085f-113">Modifying DDL Triggers</span></span>  
 <span data-ttu-id="5085f-114">Se è necessario modificare la definizione di un trigger DDL, è possibile eliminare e creare nuovamente il trigger oppure ridefinire il trigger esistente in un unico passaggio.</span><span class="sxs-lookup"><span data-stu-id="5085f-114">If you have to modify the definition of a DDL trigger, you can either drop and re-create the trigger or redefine the existing trigger in a single step.</span></span>  
  
 <span data-ttu-id="5085f-115">Se si modifica il nome di un oggetto a cui fa riferimento un trigger DDL, è necessario modificare il trigger in modo che il testo corrisponda al nuovo nome.</span><span class="sxs-lookup"><span data-stu-id="5085f-115">If you change the name of an object that is referenced by a DDL trigger, you must modify the trigger so that its text reflects the new name.</span></span> <span data-ttu-id="5085f-116">Pertanto, prima di rinominare un oggetto, visualizzare le dipendenze dell'oggetto per determinare se la modifica proposta interessa i trigger.</span><span class="sxs-lookup"><span data-stu-id="5085f-116">Therefore, before renaming an object, display the dependencies of the object first to determine whether any triggers are affected by the proposed change.</span></span>  
  
 <span data-ttu-id="5085f-117">È inoltre possibile modificare i trigger per crittografarne la definizione.</span><span class="sxs-lookup"><span data-stu-id="5085f-117">A trigger can also be modified to encrypt its definition.</span></span>  
  
 <span data-ttu-id="5085f-118">**Per modificare un trigger**</span><span class="sxs-lookup"><span data-stu-id="5085f-118">**To modify a trigger**</span></span>  
  
-   [<span data-ttu-id="5085f-119">ALTER TRIGGER &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="5085f-119">ALTER TRIGGER &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-trigger-transact-sql)  
  
 <span data-ttu-id="5085f-120">**Per visualizzare le dipendenze di un trigger**</span><span class="sxs-lookup"><span data-stu-id="5085f-120">**To view the dependencies of a trigger**</span></span>  
  
-   [<span data-ttu-id="5085f-121">sys.sql_expression_dependencies &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="5085f-121">sys.sql_expression_dependencies &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-sql-expression-dependencies-transact-sql)  
  
-   [<span data-ttu-id="5085f-122">sys.dm_sql_referenced_entities &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="5085f-122">sys.dm_sql_referenced_entities &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-sql-referenced-entities-transact-sql)  
  
-   [<span data-ttu-id="5085f-123">sys.dm_sql_referencing_entities &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="5085f-123">sys.dm_sql_referencing_entities &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-sql-referencing-entities-transact-sql)  
  
## <a name="disabling-and-dropping-ddl-triggers"></a><span data-ttu-id="5085f-124">Disabilitazione ed eliminazione di trigger DDL</span><span class="sxs-lookup"><span data-stu-id="5085f-124">Disabling and Dropping DDL Triggers</span></span>  
 <span data-ttu-id="5085f-125">Quando un trigger DDL non è più necessario, è possibile disabilitarlo o eliminarlo.</span><span class="sxs-lookup"><span data-stu-id="5085f-125">When a DDL trigger is no longer needed, you can disable it or delete it.</span></span>  
  
 <span data-ttu-id="5085f-126">La disabilitazione di un trigger DDL non ne comporta l'eliminazione.</span><span class="sxs-lookup"><span data-stu-id="5085f-126">Disabling a DDL trigger does not drop it.</span></span> <span data-ttu-id="5085f-127">Il trigger continua a esistere come oggetto nel database corrente</span><span class="sxs-lookup"><span data-stu-id="5085f-127">The trigger still exists as an object in the current database.</span></span> <span data-ttu-id="5085f-128">ma non viene attivato quando viene eseguita una qualsiasi istruzione [!INCLUDE[tsql](../../includes/tsql-md.md)] in cui è stato programmato.</span><span class="sxs-lookup"><span data-stu-id="5085f-128">However, the trigger will not fire when any [!INCLUDE[tsql](../../includes/tsql-md.md)] statements on which it was programmed are run.</span></span> <span data-ttu-id="5085f-129">I trigger DDL disabilitati possono essere riabilitati.</span><span class="sxs-lookup"><span data-stu-id="5085f-129">DDL triggers that are disabled can be reenabled.</span></span> <span data-ttu-id="5085f-130">A seguito di tale operazione, il trigger DDL viene attivato nello stesso modo in cui è stato attivato al momento della creazione.</span><span class="sxs-lookup"><span data-stu-id="5085f-130">Enabling a DDL trigger causes it to fire in the same way the trigger did when it was originally created.</span></span> <span data-ttu-id="5085f-131">Per impostazione predefinita, i trigger DDL vengono abilitati al momento della creazione.</span><span class="sxs-lookup"><span data-stu-id="5085f-131">When DDL triggers are created, they are enabled by default.</span></span>  
  
 <span data-ttu-id="5085f-132">Quando si elimina un trigger DDL, questo viene rimosso dal database corrente.</span><span class="sxs-lookup"><span data-stu-id="5085f-132">When a DDL trigger is deleted, it is dropped from the current database.</span></span> <span data-ttu-id="5085f-133">Ciò non ha alcun effetto sugli oggetti o sui dati per il cui ambito il trigger DDL è stato definito.</span><span class="sxs-lookup"><span data-stu-id="5085f-133">Any objects or data upon which the DDL trigger is scoped are not affected.</span></span>  
  
 <span data-ttu-id="5085f-134">**Per disabilitare un trigger DDL**</span><span class="sxs-lookup"><span data-stu-id="5085f-134">**To disable a DDL trigger**</span></span>  
  
-   [<span data-ttu-id="5085f-135">DISABLE TRIGGER &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="5085f-135">DISABLE TRIGGER &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/disable-trigger-transact-sql)  
  
-   [<span data-ttu-id="5085f-136">ALTER TABLE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="5085f-136">ALTER TABLE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-table-transact-sql)  
  
 <span data-ttu-id="5085f-137">**Per abilitare un trigger DDL**</span><span class="sxs-lookup"><span data-stu-id="5085f-137">**To enable a DDL trigger**</span></span>  
  
-   [<span data-ttu-id="5085f-138">ENABLE TRIGGER &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="5085f-138">ENABLE TRIGGER &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/enable-trigger-transact-sql)  
  
-   [<span data-ttu-id="5085f-139">ALTER TABLE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="5085f-139">ALTER TABLE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-table-transact-sql)  
  
 <span data-ttu-id="5085f-140">**Per eliminare un trigger DDL**</span><span class="sxs-lookup"><span data-stu-id="5085f-140">**To delete a DDL trigger**</span></span>  
  
-   [<span data-ttu-id="5085f-141">DROP TRIGGER &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="5085f-141">DROP TRIGGER &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-trigger-transact-sql)  
  
  
