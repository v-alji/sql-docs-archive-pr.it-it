---
title: Replicare le modifiche dello schema | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- replication [SQL Server], schema changes
- schemas [SQL Server replication], replicating changes
ms.assetid: c09007f0-9374-4f60-956b-8a87670cd043
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: bec2f363cd8c4f7dea45935568a88722b19323fc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629357"
---
# <a name="replicate-schema-changes"></a><span data-ttu-id="71f61-102">Replica delle modifiche dello schema</span><span class="sxs-lookup"><span data-stu-id="71f61-102">Replicate Schema Changes</span></span>
  <span data-ttu-id="71f61-103">In questo argomento si illustra come replicare le modifiche dello schema in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="71f61-103">This topic describes how to replicate schema changes in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="71f61-104">Se si apportano le seguenti modifiche dello schema a un articolo pubblicato, per impostazione predefinita le modifiche vengono propagate ai Sottoscrittori di [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="71f61-104">If you make the following schema changes to a published article, they are propagated, by default, to [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Subscribers:</span></span>  
  
-   <span data-ttu-id="71f61-105">MODIFICA TABELLA</span><span class="sxs-lookup"><span data-stu-id="71f61-105">ALTER TABLE</span></span>  
  
-   <span data-ttu-id="71f61-106">ALTER VIEW</span><span class="sxs-lookup"><span data-stu-id="71f61-106">ALTER VIEW</span></span>  
  
-   <span data-ttu-id="71f61-107">ALTER PROCEDURE</span><span class="sxs-lookup"><span data-stu-id="71f61-107">ALTER PROCEDURE</span></span>  
  
-   <span data-ttu-id="71f61-108">ALTER FUNCTION</span><span class="sxs-lookup"><span data-stu-id="71f61-108">ALTER FUNCTION</span></span>  
  
-   <span data-ttu-id="71f61-109">ALTER TRIGGER</span><span class="sxs-lookup"><span data-stu-id="71f61-109">ALTER TRIGGER</span></span>  
  
 <span data-ttu-id="71f61-110">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="71f61-110">**In This Topic**</span></span>  
  
-   <span data-ttu-id="71f61-111">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="71f61-111">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="71f61-112">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="71f61-112">Limitations and Restrictions</span></span>](#Restrictions)  
  
-   <span data-ttu-id="71f61-113">**Per replicare le modifiche dello schema, utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="71f61-113">**To replicate schema changes, using:**</span></span>  
  
     [<span data-ttu-id="71f61-114">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="71f61-114">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="71f61-115">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="71f61-115">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="71f61-116">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="71f61-116">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="71f61-117">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="71f61-117">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="71f61-118">L'istruzione ALTER TABLE ... DROP COLUMN viene sempre replicata in tutti i Sottoscrittori la cui sottoscrizione contiene le colonne in corso di eliminazione, anche in caso di disabilitazione della replica delle modifiche dello schema.</span><span class="sxs-lookup"><span data-stu-id="71f61-118">The ALTER TABLE ... DROP COLUMN statement is always replicated to all Subscribers whose subscription contains the columns being dropped, even if you disable the replication of schema changes.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="71f61-119">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="71f61-119">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="71f61-120">Se non si vogliono replicare le modifiche dello schema per una pubblicazione, disabilitare la replica di tali modifiche nella finestra di dialogo **Proprietà pubblicazione - \<Publication>** .</span><span class="sxs-lookup"><span data-stu-id="71f61-120">If you do not want to replicate schema changes for a publication, disable the replication of schema changes in the **Publication Properties - \<Publication>** dialog box.</span></span> <span data-ttu-id="71f61-121">Per ulteriori informazioni sull'accesso a questa finestra di dialogo, vedere [View and Modify Publication Properties](view-and-modify-publication-properties.md).</span><span class="sxs-lookup"><span data-stu-id="71f61-121">For more information about accessing this dialog box, see [View and Modify Publication Properties](view-and-modify-publication-properties.md).</span></span>  
  
#### <a name="to-disable-replication-of-schema-changes"></a><span data-ttu-id="71f61-122">Per disabilitare la replica delle modifiche dello schema</span><span class="sxs-lookup"><span data-stu-id="71f61-122">To disable replication of schema changes</span></span>  
  
1.  <span data-ttu-id="71f61-123">Nella pagina **Opzioni sottoscrizione** della finestra di dialogo **Proprietà pubblicazione - \<Publication>** impostare il valore della proprietà **Replica modifiche dello schema** su **Falso**.</span><span class="sxs-lookup"><span data-stu-id="71f61-123">On the **Subscription Options** page of the **Publication Properties - \<Publication>** dialog box, set the value of the **Replicate schema changes** property to **False**.</span></span>  
  
2.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
     <span data-ttu-id="71f61-124">Per propagare soltanto modifiche dello schema specifiche, impostare la proprietà su **Vero** prima di una modifica dello schema e quindi impostarla su **Falso** al termine della modifica.</span><span class="sxs-lookup"><span data-stu-id="71f61-124">To propagate only specific schema changes, set the property to **True** before a schema change, and then set it to **False** after the change is made.</span></span> <span data-ttu-id="71f61-125">Al contrario, per propagare la maggior parte delle modifiche dello schema ma non una determinata modifica, impostare la proprietà su **Falso** prima della modifica dello schema e quindi impostarla su **Vero** al termine della modifica.</span><span class="sxs-lookup"><span data-stu-id="71f61-125">Conversely, to propagate most schema changes, but not a given change, set the property to **False** before the schema change, and then set it to **True** after the change is made.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="71f61-126">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="71f61-126">Using Transact-SQL</span></span>  
 <span data-ttu-id="71f61-127">È possibile utilizzare le stored procedure di replica per specificare se queste modifiche dello schema vengono replicate.</span><span class="sxs-lookup"><span data-stu-id="71f61-127">You can use replication stored procedures to specify whether these schema changes are replicated.</span></span> <span data-ttu-id="71f61-128">La stored procedure utilizzata dipende del tipo di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="71f61-128">The stored procedure that you use depends on the type of publication.</span></span>  
  
#### <a name="to-create-a-snapshot-or-transactional-publication-that-does-not-replicate-schema-changes"></a><span data-ttu-id="71f61-129">Per creare una pubblicazione snapshot o transazionale che non replica le modifiche dello schema</span><span class="sxs-lookup"><span data-stu-id="71f61-129">To create a snapshot or transactional publication that does not replicate schema changes</span></span>  
  
1.  <span data-ttu-id="71f61-130">Nel database di pubblicazione del server di pubblicazione eseguire [sp_addpublication &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-addpublication-transact-sql), specificando il valore **0** per \*\* \@ replicate_ddl\*\*.</span><span class="sxs-lookup"><span data-stu-id="71f61-130">At the Publisher on the publication database, execute [sp_addpublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addpublication-transact-sql), specifying a value of **0** for **\@replicate_ddl**.</span></span> <span data-ttu-id="71f61-131">Per altre informazioni, vedere [Create a Publication](create-a-publication.md).</span><span class="sxs-lookup"><span data-stu-id="71f61-131">For more information, see [Create a Publication](create-a-publication.md).</span></span>  
  
#### <a name="to-create-a-merge-publication-that-does-not-replicate-schema-changes"></a><span data-ttu-id="71f61-132">Per creare una pubblicazione di tipo merge che non replica le modifiche dello schema</span><span class="sxs-lookup"><span data-stu-id="71f61-132">To create a merge publication that does not replicate schema changes</span></span>  
  
1.  <span data-ttu-id="71f61-133">Nel database di pubblicazione del server di pubblicazione eseguire [sp_addmergepublication &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-addmergepublication-transact-sql), specificando il valore **0** per \*\* \@ replicate_ddl\*\*.</span><span class="sxs-lookup"><span data-stu-id="71f61-133">At the Publisher on the publication database, execute [sp_addmergepublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addmergepublication-transact-sql), specifying a value of **0** for **\@replicate_ddl**.</span></span> <span data-ttu-id="71f61-134">Per altre informazioni, vedere [Create a Publication](create-a-publication.md).</span><span class="sxs-lookup"><span data-stu-id="71f61-134">For more information, see [Create a Publication](create-a-publication.md).</span></span>  
  
#### <a name="to-temporarily-disable-replicating-schema-changes-for-a-snapshot-or-transactional-publication"></a><span data-ttu-id="71f61-135">Per disabilitare temporaneamente la replica delle modifiche dello schema per una pubblicazione snapshot o transazionale</span><span class="sxs-lookup"><span data-stu-id="71f61-135">To temporarily disable replicating schema changes for a snapshot or transactional publication</span></span>  
  
1.  <span data-ttu-id="71f61-136">Per una pubblicazione con replica delle modifiche dello schema, eseguire [sp_changepublication &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-changepublication-transact-sql), specificando il valore **replicate_ddl** per la \*\* \@ Proprietà\*\* e il valore **0** per \*\* \@ value\*\*.</span><span class="sxs-lookup"><span data-stu-id="71f61-136">For a publication with replication of schema changes, execute [sp_changepublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-changepublication-transact-sql), specifying a value of **replicate_ddl** for **\@property** and a value of **0** for **\@value**.</span></span>  
  
2.  <span data-ttu-id="71f61-137">Eseguire il comando DDL sull'oggetto pubblicato.</span><span class="sxs-lookup"><span data-stu-id="71f61-137">Execute the DDL command on the published object.</span></span>  
  
3.  <span data-ttu-id="71f61-138">Opzionale Abilitare di nuovo la replica delle modifiche dello schema eseguendo [sp_changepublication &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-changepublication-transact-sql), specificando il valore **replicate_ddl** per la \*\* \@ Proprietà\*\* e il valore **1** per \*\* \@ value\*\*.</span><span class="sxs-lookup"><span data-stu-id="71f61-138">(Optional) Re-enable replicating schema changes by executing [sp_changepublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-changepublication-transact-sql), specifying a value of **replicate_ddl** for **\@property** and a value of **1** for **\@value**.</span></span>  
  
#### <a name="to-temporarily-disable-replicating-schema-changes-for-a-merge-publication"></a><span data-ttu-id="71f61-139">Per disabilitare temporaneamente la replica delle modifiche dello schema per una pubblicazione di tipo merge</span><span class="sxs-lookup"><span data-stu-id="71f61-139">To temporarily disable replicating schema changes for a merge publication</span></span>  
  
1.  <span data-ttu-id="71f61-140">Per una pubblicazione con replica delle modifiche dello schema, eseguire [sp_changemergepublication &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-changemergepublication-transact-sql), specificando il valore **replicate_ddl** per la \*\* \@ Proprietà\*\* e il valore **0** per \*\* \@ value\*\*.</span><span class="sxs-lookup"><span data-stu-id="71f61-140">For a publication with replication of schema changes, execute [sp_changemergepublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-changemergepublication-transact-sql), specifying a value of **replicate_ddl** for **\@property** and a value of **0** for **\@value**.</span></span>  
  
2.  <span data-ttu-id="71f61-141">Eseguire il comando DDL sull'oggetto pubblicato.</span><span class="sxs-lookup"><span data-stu-id="71f61-141">Execute the DDL command on the published object.</span></span>  
  
3.  <span data-ttu-id="71f61-142">Opzionale Abilitare di nuovo la replica delle modifiche dello schema eseguendo [sp_changemergepublication &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-changemergepublication-transact-sql), specificando il valore **replicate_ddl** per la \*\* \@ Proprietà\*\* e il valore **1** per \*\* \@ value\*\*.</span><span class="sxs-lookup"><span data-stu-id="71f61-142">(Optional) Re-enable replicating schema changes by executing [sp_changemergepublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-changemergepublication-transact-sql), specifying a value of **replicate_ddl** for **\@property** and a value of **1** for **\@value**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71f61-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="71f61-143">See Also</span></span>  
 <span data-ttu-id="71f61-144">[Apportare modifiche allo schema nei database di pubblicazione](make-schema-changes-on-publication-databases.md) </span><span class="sxs-lookup"><span data-stu-id="71f61-144">[Make Schema Changes on Publication Databases](make-schema-changes-on-publication-databases.md) </span></span>  
 [<span data-ttu-id="71f61-145">Apportare modifiche allo schema nei database di pubblicazione</span><span class="sxs-lookup"><span data-stu-id="71f61-145">Make Schema Changes on Publication Databases</span></span>](make-schema-changes-on-publication-databases.md)  
  
  
