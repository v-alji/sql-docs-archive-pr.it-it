---
title: Specificare i primi e gli ultimi trigger | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- first triggers [SQL Server]
- last triggers
- DML triggers, first or last triggers
- INSTEAD OF triggers
- AFTER triggers
ms.assetid: 9e6c7684-3dd3-46bb-b7be-523b33fae4d5
author: rothja
ms.author: jroth
ms.openlocfilehash: 8ddb352b00dc759362c8f6ef1e861e55b6f184f2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637125"
---
# <a name="specify-first-and-last-triggers"></a><span data-ttu-id="5ff77-102">Specifica dei primi e degli ultimi trigger</span><span class="sxs-lookup"><span data-stu-id="5ff77-102">Specify First and Last Triggers</span></span>
  <span data-ttu-id="5ff77-103">È possibile specificare che uno dei trigger AFTER associati a una tabella sia il primo oppure l'ultimo trigger AFTER che viene attivato per ogni azione di trigger INSERT, DELETE e UPDATE.</span><span class="sxs-lookup"><span data-stu-id="5ff77-103">You can specify that one of the AFTER triggers associated with a table be either the first AFTER trigger or the last AFTER trigger that is fired for each INSERT, DELETE, and UPDATE triggering actions.</span></span> <span data-ttu-id="5ff77-104">I trigger AFTER compresi fra il primo e l'ultimo vengono eseguiti in base a un ordine non definito.</span><span class="sxs-lookup"><span data-stu-id="5ff77-104">The AFTER triggers that are fired between the first and last triggers are executed in undefined order.</span></span>  
  
 <span data-ttu-id="5ff77-105">Per specificare l'ordine per un trigger AFTER, usare la stored procedure **sp_settriggerorder** .</span><span class="sxs-lookup"><span data-stu-id="5ff77-105">To specify the order for an AFTER trigger, use the **sp_settriggerorder** stored procedure.</span></span> <span data-ttu-id="5ff77-106">**sp_settriggerorder** ha le opzioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="5ff77-106">**sp_settriggerorder** has the following options.</span></span>  
  
|<span data-ttu-id="5ff77-107">Opzione</span><span class="sxs-lookup"><span data-stu-id="5ff77-107">Option</span></span>|<span data-ttu-id="5ff77-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5ff77-108">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="5ff77-109">**Primo**</span><span class="sxs-lookup"><span data-stu-id="5ff77-109">**First**</span></span>|<span data-ttu-id="5ff77-110">Specifica che il trigger DML è il primo trigger AFTER attivato per un'azione di trigger.</span><span class="sxs-lookup"><span data-stu-id="5ff77-110">Specifies that the DML trigger is the first AFTER trigger fired for a triggering action.</span></span>|  
|<span data-ttu-id="5ff77-111">**Ultimo**</span><span class="sxs-lookup"><span data-stu-id="5ff77-111">**Last**</span></span>|<span data-ttu-id="5ff77-112">Specifica che il trigger DML è l'ultimo trigger AFTER attivato per un'azione di trigger.</span><span class="sxs-lookup"><span data-stu-id="5ff77-112">Specifies that the DML trigger is the last AFTER trigger fired for a triggering action.</span></span>|  
|<span data-ttu-id="5ff77-113">**Nessuno**</span><span class="sxs-lookup"><span data-stu-id="5ff77-113">**None**</span></span>|<span data-ttu-id="5ff77-114">Specifica che non esiste un ordine specifico per l'attivazione del trigger DML.</span><span class="sxs-lookup"><span data-stu-id="5ff77-114">Specifies that there is no specific order in which the DML trigger should be fired.</span></span> <span data-ttu-id="5ff77-115">Viene utilizzata principalmente per reimpostare un trigger precedentemente designato come primo o ultimo.</span><span class="sxs-lookup"><span data-stu-id="5ff77-115">Used mainly to reset a trigger from being either first or last.</span></span>|  
  
 <span data-ttu-id="5ff77-116">L'esempio seguente mostra l'utilizzo di **sp_settriggerorder**:</span><span class="sxs-lookup"><span data-stu-id="5ff77-116">The following example shows using **sp_settriggerorder**:</span></span>  
  
```  
sp_settriggerorder @triggername = 'MyTrigger', @order = 'first', @stmttype = 'UPDATE'  
```  
  
> [!IMPORTANT]  
>  <span data-ttu-id="5ff77-117">Il primo trigger e l'ultimo devono essere due trigger DML distinti.</span><span class="sxs-lookup"><span data-stu-id="5ff77-117">The first and last triggers must be two different DML triggers.</span></span>  
  
 <span data-ttu-id="5ff77-118">Una tabella può includere contemporaneamente trigger INSERT, UPDATE e DELETE.</span><span class="sxs-lookup"><span data-stu-id="5ff77-118">A table can have INSERT, UPDATE, and DELETE triggers defined on it at the same time.</span></span> <span data-ttu-id="5ff77-119">È possibile impostare primo e ultimo trigger per ogni tipo di istruzione, ma non può trattarsi degli stessi trigger.</span><span class="sxs-lookup"><span data-stu-id="5ff77-119">Each statement type can have its own first and last triggers, but they cannot be the same triggers.</span></span>  
  
 <span data-ttu-id="5ff77-120">Se il primo o l'ultimo trigger definito per una tabella non copre un'azione di trigger, ad esempio non copre FOR UPDATE, FOR DELETE o FOR INSERT, per le azioni mancanti non esiste un primo o un ultimo trigger.</span><span class="sxs-lookup"><span data-stu-id="5ff77-120">If the first or last trigger defined for a table does not cover a triggering action, such as not covering FOR UPDATE, FOR DELETE, or FOR INSERT, there is no first or last trigger for the missing actions.</span></span>  
  
 <span data-ttu-id="5ff77-121">Non è possibile specificare i trigger INSTEAD OF come primi o ultimi trigger.</span><span class="sxs-lookup"><span data-stu-id="5ff77-121">INSTEAD OF triggers cannot be specified as first or last triggers.</span></span> <span data-ttu-id="5ff77-122">I trigger INSTEAD OF vengono attivati prima dell'esecuzione degli aggiornamenti sulle tabelle sottostanti.</span><span class="sxs-lookup"><span data-stu-id="5ff77-122">INSTEAD OF triggers are fired before updates are made to the underlying tables.</span></span> <span data-ttu-id="5ff77-123">Se un trigger INSTEAD OF esegue aggiornamenti sulle tabelle sottostanti, tali aggiornamenti vengono eseguiti prima dell'attivazione di qualsiasi trigger AFTER incluso nella tabella.</span><span class="sxs-lookup"><span data-stu-id="5ff77-123">If updates are made by an INSTEAD OF trigger to underlying tables, the updates occur before any AFTER triggers defined on the table are fired.</span></span> <span data-ttu-id="5ff77-124">Ad esempio, se un trigger INSTEAD OF INSERT su una vista inserisce dati in una tabella di base e tale tabella contiene un trigger INSTEAD OF INSERT e tre trigger AFTER INSERT, invece dell'azione di inserimento viene attivato il trigger INSTEAD OF INSERT della tabella di base e i trigger AFTER della tabella di base vengono attivati dopo l'esecuzione di qualsiasi azione di inserimento sulla tabella stessa.</span><span class="sxs-lookup"><span data-stu-id="5ff77-124">For example, if an INSTEAD OF INSERT trigger on a view inserts data into a base table and the base table itself contains an INSTEAD OF INSERT trigger and three AFTER INSERT triggers, the INSTEAD OF INSERT trigger on the base table is fired instead of the inserting action, and the AFTER triggers on the base table are fired after any inserting action on the base table.</span></span> <span data-ttu-id="5ff77-125">Per altre informazioni, vedere [DML Triggers](dml-triggers.md).</span><span class="sxs-lookup"><span data-stu-id="5ff77-125">For more information, see [DML Triggers](dml-triggers.md).</span></span>  
  
 <span data-ttu-id="5ff77-126">Se il primo o l'ultimo trigger viene modificato da un'istruzione ALTER TRIGGER, l'attributo **First** o **Last** viene rimosso e il valore relativo all'ordine viene impostato su **None**.</span><span class="sxs-lookup"><span data-stu-id="5ff77-126">If an ALTER TRIGGER statement changes a first or last trigger, the **First** or **Last** attribute is dropped and the order value is set to **None**.</span></span> <span data-ttu-id="5ff77-127">È necessario reimpostare l'ordine usando **sp_settriggerorder**.</span><span class="sxs-lookup"><span data-stu-id="5ff77-127">The order must be reset by using **sp_settriggerorder**.</span></span>  
  
 <span data-ttu-id="5ff77-128">La funzione OBJECTPROPERTY usa le proprietà **ExecIsFirstTrigger** e **ExecIsLastTrigger**per segnalare se un trigger è primo o ultimo.</span><span class="sxs-lookup"><span data-stu-id="5ff77-128">The OBJECTPROPERTY function reports whether a trigger is a first or last trigger by using the properties **ExecIsFirstTrigger** and **ExecIsLastTrigger**.</span></span>  
  
 <span data-ttu-id="5ff77-129">La replica genera automaticamente un primo trigger per ogni tabella inclusa in una sottoscrizione ad aggiornamento in coda o ad aggiornamento immediato.</span><span class="sxs-lookup"><span data-stu-id="5ff77-129">Replication automatically generates a first trigger for any table that is included in an immediate updating or queued updating subscription.</span></span> <span data-ttu-id="5ff77-130">La replica richiede che il proprio trigger sia il primo trigger.</span><span class="sxs-lookup"><span data-stu-id="5ff77-130">Replication requires that its trigger be the first trigger.</span></span> <span data-ttu-id="5ff77-131">La replica genera un errore se si cerca di includere una tabella con un primo trigger in una sottoscrizione ad aggiornamento immediato o ad aggiornamento in coda.</span><span class="sxs-lookup"><span data-stu-id="5ff77-131">Replication raises an error when you try to include a table with a first trigger in an immediate updating or queued updating subscription.</span></span> <span data-ttu-id="5ff77-132">Se si prova a impostare un trigger come primo dopo l'inclusione di una tabella in una sottoscrizione, **sp_settriggerorder** restituisce un errore.</span><span class="sxs-lookup"><span data-stu-id="5ff77-132">If you try to make a trigger a first trigger after a table has been included in a subscription, **sp_settriggerorder** returns an error.</span></span> <span data-ttu-id="5ff77-133">Se si usa ALTER sul trigger di replica oppure **sp_settriggerorder** per modificare il trigger di replica come ultimo trigger o come trigger senza un ordine di esecuzione specifico, la sottoscrizione non funzionerà in modo corretto.</span><span class="sxs-lookup"><span data-stu-id="5ff77-133">If you use ALTER on the replication trigger or use **sp_settriggerorder** to change the replication trigger to a last or none trigger, the subscription will not function correctly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ff77-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5ff77-134">See Also</span></span>  
 <span data-ttu-id="5ff77-135">[OBJECTPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/objectpropertyex-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="5ff77-135">[OBJECTPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/objectpropertyex-transact-sql) </span></span>  
 [<span data-ttu-id="5ff77-136">sp_settriggerorder &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="5ff77-136">sp_settriggerorder &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-settriggerorder-transact-sql)  
  
  
