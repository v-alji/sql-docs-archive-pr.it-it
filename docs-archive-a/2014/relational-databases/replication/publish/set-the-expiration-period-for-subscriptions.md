---
title: Impostare il periodo di scadenza per le sottoscrizioni | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- subscriptions [SQL Server replication], expiration
- expiration [SQL Server replication]
- retention periods [SQL Server replication]
- deactivating subscriptions
ms.assetid: 542f0613-5817-42d0-b841-fb2c94010665
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: bc0ecb449af64b88cf3ded032c78c2e399dd4234
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629354"
---
# <a name="set-the-expiration-period-for-subscriptions"></a><span data-ttu-id="0045e-102">Impostazione del periodo di scadenza per le sottoscrizioni</span><span class="sxs-lookup"><span data-stu-id="0045e-102">Set the Expiration Period for Subscriptions</span></span>
  <span data-ttu-id="0045e-103">In questo argomento si illustra come impostare il periodo di scadenza per le sottoscrizioni in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0045e-103">This topic describes how to set the expiration period for subscriptions in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="0045e-104">Il periodo di scadenza per le sottoscrizioni determina il periodo tempo che deve trascorrere prima che una sottoscrizione scada e venga rimossa.</span><span class="sxs-lookup"><span data-stu-id="0045e-104">The expiration period for subscriptions determines the period of time before a subscription expires and is removed.</span></span> <span data-ttu-id="0045e-105">Per altre informazioni, vedere [Subscription Expiration and Deactivation](../subscription-expiration-and-deactivation.md).</span><span class="sxs-lookup"><span data-stu-id="0045e-105">For more information, see [Subscription Expiration and Deactivation](../subscription-expiration-and-deactivation.md).</span></span>  
  
 <span data-ttu-id="0045e-106">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="0045e-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="0045e-107">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="0045e-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="0045e-108">Indicazioni</span><span class="sxs-lookup"><span data-stu-id="0045e-108">Recommendations</span></span>](#Recommendations)  
  
-   <span data-ttu-id="0045e-109">**Per impostare il periodo di scadenza per le sottoscrizioni, utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="0045e-109">**To set the expiration period for subscriptions, using:**</span></span>  
  
     [<span data-ttu-id="0045e-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="0045e-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="0045e-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="0045e-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="0045e-112">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="0045e-112">Before You Begin</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="0045e-113">Indicazioni</span><span class="sxs-lookup"><span data-stu-id="0045e-113">Recommendations</span></span>  
  
-   <span data-ttu-id="0045e-114">Il periodo di scadenza della sottoscrizione viene inoltre denominato *periodo di memorizzazione della pubblicazione*.</span><span class="sxs-lookup"><span data-stu-id="0045e-114">The subscription expiration period is also referred to as the *publication retention period*.</span></span> <span data-ttu-id="0045e-115">La pulizia dei metadati di replica di tipo merge dipende da questa impostazione:</span><span class="sxs-lookup"><span data-stu-id="0045e-115">Cleanup of merge replication metadata is dependent on this setting:</span></span>  
  
    -   <span data-ttu-id="0045e-116">La replica non è in grado di eliminare i metadati dei database di pubblicazione e sottoscrizione prima della scadenza del periodo di memorizzazione.</span><span class="sxs-lookup"><span data-stu-id="0045e-116">Replication cannot clean up metadata in the publication and subscription databases until the retention period is reached.</span></span> <span data-ttu-id="0045e-117">Quando si imposta un valore elevato per il periodo di memorizzazione, verificare che non sia tale da avere effetti negativi sulle prestazioni della replica.</span><span class="sxs-lookup"><span data-stu-id="0045e-117">Use caution in specifying a high value for the retention period, because it can negatively impact replication performance.</span></span> <span data-ttu-id="0045e-118">Se si prevede che la sincronizzazione di tutti i Sottoscrittori verrà eseguita regolarmente entro tale periodo di tempo, è consigliabile specificare un valore inferiore.</span><span class="sxs-lookup"><span data-stu-id="0045e-118">It is recommended that you use a lower setting if you can reliably predict that all Subscribers will synchronize regularly within that time period.</span></span>  
  
         <span data-ttu-id="0045e-119">Il periodo di memorizzazione per le pubblicazioni di tipo merge ha un periodo di prova di 24 ore per adattarsi ai Sottoscrittori dei diversi fusi orari.</span><span class="sxs-lookup"><span data-stu-id="0045e-119">The retention period for merge publications has a 24-hour grace period to accommodate Subscribers in different time zones.</span></span> <span data-ttu-id="0045e-120">Se, ad esempio, si imposta un periodo di memorizzazione di un giorno, il periodo di memorizzazione effettivo sarà di 48 ore.</span><span class="sxs-lookup"><span data-stu-id="0045e-120">If, for example, you set a retention period of one day, the actual retention period is 48 hours.</span></span>  
  
    -   <span data-ttu-id="0045e-121">È possibile specificare che le sottoscrizioni non devono scadere, ma è consigliabile non utilizzare questo valore, perché impedisce l'eliminazione dei metadati.</span><span class="sxs-lookup"><span data-stu-id="0045e-121">It is possible to specify that subscriptions never expire, but it is strongly recommended that you do not use this value, because metadata cannot be cleaned up.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="0045e-122">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="0045e-122">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="0045e-123">Impostare il periodo di scadenza per le sottoscrizioni nella pagina **Generale** della finestra di dialogo **Proprietà pubblicazione - \<Publication>** .</span><span class="sxs-lookup"><span data-stu-id="0045e-123">Set the expiration period for subscriptions on the **General** page of the **Publication Properties - \<Publication>** dialog box.</span></span> <span data-ttu-id="0045e-124">Per ulteriori informazioni sull'accesso a questa finestra di dialogo, vedere [View and Modify Publication Properties](view-and-modify-publication-properties.md).</span><span class="sxs-lookup"><span data-stu-id="0045e-124">For more information about accessing this dialog box, see [View and Modify Publication Properties](view-and-modify-publication-properties.md).</span></span>  
  
#### <a name="to-set-the-expiration-period-for-subscriptions"></a><span data-ttu-id="0045e-125">Per impostare il periodo di scadenza per le sottoscrizioni</span><span class="sxs-lookup"><span data-stu-id="0045e-125">To set the expiration period for subscriptions</span></span>  
  
1.  <span data-ttu-id="0045e-126">Nella sezione **Scadenza sottoscrizione** della pagina **Generale** della finestra di dialogo **Proprietà pubblicazione - \<Publication>** specificare se le sottoscrizioni devono avere una scadenza.</span><span class="sxs-lookup"><span data-stu-id="0045e-126">In the **Subscription expiration** section on the **General** page of the **Publication Properties - \<Publication>** dialog box, specify whether subscriptions should expire.</span></span>  
  
2.  <span data-ttu-id="0045e-127">Se le sottoscrizioni avranno una scadenza, specificarne il periodo di tempo.</span><span class="sxs-lookup"><span data-stu-id="0045e-127">If they should expire, specify an expiration time period.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="0045e-128">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="0045e-128">Using Transact-SQL</span></span>  
 <span data-ttu-id="0045e-129">Per impostare questo valore quando viene creata una pubblicazione o per modificarlo in un secondo momento, è possibile utilizzare le stored procedure di replica.</span><span class="sxs-lookup"><span data-stu-id="0045e-129">You can use replication stored procedures to either set this value when a publication is created or modify this value at a later time.</span></span>  
  
#### <a name="to-set-the-expiration-period-for-a-subscription-to-a-snapshot-or-transactional-publication"></a><span data-ttu-id="0045e-130">Per impostare il periodo di scadenza per una sottoscrizione di una pubblicazione snapshot o transazionale</span><span class="sxs-lookup"><span data-stu-id="0045e-130">To set the expiration period for a subscription to a snapshot or transactional publication</span></span>  
  
1.  <span data-ttu-id="0045e-131">Nel server di pubblicazione eseguire [sp_addpublication](/sql/relational-databases/system-stored-procedures/sp-addpublication-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="0045e-131">At the Publisher, execute [sp_addpublication](/sql/relational-databases/system-stored-procedures/sp-addpublication-transact-sql).</span></span> <span data-ttu-id="0045e-132">Specificare il periodo di scadenza desiderato per la sottoscrizione, in ore, per **\@retention**.</span><span class="sxs-lookup"><span data-stu-id="0045e-132">Specify the desired subscription expiration period, in hours, for **\@retention**.</span></span> <span data-ttu-id="0045e-133">Il periodo di scadenza predefinito è 336 ore.</span><span class="sxs-lookup"><span data-stu-id="0045e-133">The default expiration period is 336 hours.</span></span> <span data-ttu-id="0045e-134">Per altre informazioni, vedere [Create a Publication](create-a-publication.md).</span><span class="sxs-lookup"><span data-stu-id="0045e-134">For more information, see [Create a Publication](create-a-publication.md).</span></span>  
  
#### <a name="to-set-the-expiration-period-for-a-subscription-to-a-merge-publication"></a><span data-ttu-id="0045e-135">Per impostare il periodo di scadenza per una sottoscrizione di una pubblicazione di tipo merge</span><span class="sxs-lookup"><span data-stu-id="0045e-135">To set the expiration period for a subscription to a merge publication</span></span>  
  
1.  <span data-ttu-id="0045e-136">Nel server di pubblicazione eseguire [sp_addmergepublication](/sql/relational-databases/system-stored-procedures/sp-addmergepublication-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="0045e-136">At the Publisher, execute [sp_addmergepublication](/sql/relational-databases/system-stored-procedures/sp-addmergepublication-transact-sql).</span></span> <span data-ttu-id="0045e-137">Specificare il valore desiderato per il periodo di scadenza della sottoscrizione per **\@retention**.</span><span class="sxs-lookup"><span data-stu-id="0045e-137">Specify the desired value for the subscription expiration period for **\@retention**.</span></span> <span data-ttu-id="0045e-138">Specificare per **\@retention_period_unit** le unità in cui esprimere il periodo di scadenza, che possono essere una delle seguenti:</span><span class="sxs-lookup"><span data-stu-id="0045e-138">Specify the units in which the expiration period is expressed for **\@retention_period_unit**, which can be one of the following:</span></span>  
  
    -   <span data-ttu-id="0045e-139">**1** = Settimana</span><span class="sxs-lookup"><span data-stu-id="0045e-139">**1** = week</span></span>  
  
    -   <span data-ttu-id="0045e-140">**2** = Mese</span><span class="sxs-lookup"><span data-stu-id="0045e-140">**2** = month</span></span>  
  
    -   <span data-ttu-id="0045e-141">**3** = Anno</span><span class="sxs-lookup"><span data-stu-id="0045e-141">**3** = year</span></span>  
  
     <span data-ttu-id="0045e-142">Il periodo di scadenza predefinito è 14 giorni.</span><span class="sxs-lookup"><span data-stu-id="0045e-142">The default expiration period is 14 days.</span></span> <span data-ttu-id="0045e-143">Per altre informazioni, vedere [Create a Publication](create-a-publication.md).</span><span class="sxs-lookup"><span data-stu-id="0045e-143">For more information, see [Create a Publication](create-a-publication.md).</span></span>  
  
#### <a name="to-change-the-expiration-period-for-a-subscription-to-a-snapshot-or-transactional-publication"></a><span data-ttu-id="0045e-144">Per modificare il periodo di scadenza per una sottoscrizione di una pubblicazione snapshot o transazionale</span><span class="sxs-lookup"><span data-stu-id="0045e-144">To change the expiration period for a subscription to a snapshot or transactional publication</span></span>  
  
1.  <span data-ttu-id="0045e-145">Nel server di pubblicazione eseguire [sp_changepublication](/sql/relational-databases/system-stored-procedures/sp-changepublication-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="0045e-145">At the Publisher, execute [sp_changepublication](/sql/relational-databases/system-stored-procedures/sp-changepublication-transact-sql).</span></span> <span data-ttu-id="0045e-146">Specificare **retention** per **\@property** e il nuovo periodo di scadenza della sottoscrizione, in ore, per **\@value**.</span><span class="sxs-lookup"><span data-stu-id="0045e-146">Specify **retention** for **\@property** and the new subscription expiration period, in hours, for **\@value**.</span></span>  
  
#### <a name="to-change-the-expiration-period-for-a-subscription-to-a-merge-publication"></a><span data-ttu-id="0045e-147">Per modificare il periodo di scadenza per una sottoscrizione di una pubblicazione di tipo merge</span><span class="sxs-lookup"><span data-stu-id="0045e-147">To change the expiration period for a subscription to a merge publication</span></span>  
  
1.  <span data-ttu-id="0045e-148">Nel server di pubblicazione eseguire [sp_helpmergepublication](/sql/relational-databases/system-stored-procedures/sp-helpmergepublication-transact-sql), specificando **\@publication** e **\@publisher**.</span><span class="sxs-lookup"><span data-stu-id="0045e-148">At the Publisher, execute [sp_helpmergepublication](/sql/relational-databases/system-stored-procedures/sp-helpmergepublication-transact-sql), specifying **\@publication** and **\@publisher**.</span></span> <span data-ttu-id="0045e-149">Si noti il valore di **retention_period_unit** nel set di risultati, che può essere uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="0045e-149">Note the value of **retention_period_unit** in the result set, which can be one of the following:</span></span>  
  
    -   <span data-ttu-id="0045e-150">**0** = giorno</span><span class="sxs-lookup"><span data-stu-id="0045e-150">**0** = day</span></span>  
  
    -   <span data-ttu-id="0045e-151">**1** = Settimana</span><span class="sxs-lookup"><span data-stu-id="0045e-151">**1** = week</span></span>  
  
    -   <span data-ttu-id="0045e-152">**2** = Mese</span><span class="sxs-lookup"><span data-stu-id="0045e-152">**2** = month</span></span>  
  
    -   <span data-ttu-id="0045e-153">**3** = Anno</span><span class="sxs-lookup"><span data-stu-id="0045e-153">**3** = year</span></span>  
  
2.  <span data-ttu-id="0045e-154">Nel server di pubblicazione eseguire [sp_changemergepublication](/sql/relational-databases/system-stored-procedures/sp-changemergepublication-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="0045e-154">At the Publisher, execute [sp_changemergepublication](/sql/relational-databases/system-stored-procedures/sp-changemergepublication-transact-sql).</span></span> <span data-ttu-id="0045e-155">Specificare **retention** per **\@property** e il nuovo periodo di scadenza della sottoscrizione, come testo basato sull'unità del periodo di memorizzazione indicata nel passaggio 1, per **\@value**.</span><span class="sxs-lookup"><span data-stu-id="0045e-155">Specify **retention** for **\@property** and the new subscription expiration period, as text based on the retention period unit from step 1, for **\@value**.</span></span>  
  
3.  <span data-ttu-id="0045e-156">(Facoltativo) Nel server di pubblicazione eseguire [sp_changemergepublication](/sql/relational-databases/system-stored-procedures/sp-changemergepublication-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="0045e-156">(Optional) At the Publisher, execute [sp_changemergepublication](/sql/relational-databases/system-stored-procedures/sp-changemergepublication-transact-sql).</span></span> <span data-ttu-id="0045e-157">Specificare **retention_period_unit** per **\@property** e una nuova unità per il periodo di scadenza della sottoscrizione per **\@value**.</span><span class="sxs-lookup"><span data-stu-id="0045e-157">Specify **retention_period_unit** for **\@property** and a new unit for the subscription expiration period for **\@value**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0045e-158">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0045e-158">See Also</span></span>  
 <span data-ttu-id="0045e-159">[Replication System Stored Procedures Concepts](../concepts/replication-system-stored-procedures-concepts.md) </span><span class="sxs-lookup"><span data-stu-id="0045e-159">[Replication System Stored Procedures Concepts](../concepts/replication-system-stored-procedures-concepts.md) </span></span>  
 [<span data-ttu-id="0045e-160">Scadenza e disattivazione delle sottoscrizioni</span><span class="sxs-lookup"><span data-stu-id="0045e-160">Subscription Expiration and Deactivation</span></span>](../subscription-expiration-and-deactivation.md)  
  
  
