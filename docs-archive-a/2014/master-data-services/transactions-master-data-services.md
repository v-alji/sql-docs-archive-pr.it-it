---
title: Transazioni (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- transactions [Master Data Services], about transactions
- transactions [Master Data Services]
ms.assetid: 4cd2fa6f-9c76-4b7a-ae18-d4e5fd2f03f5
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: c693b550e0c1adb8f5910d99c7125c85f41abb8b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723967"
---
# <a name="transactions-master-data-services"></a><span data-ttu-id="41e3c-102">Transazioni (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="41e3c-102">Transactions (Master Data Services)</span></span>
  <span data-ttu-id="41e3c-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], viene registrata una transazione ogni volta che viene eseguita un'azione su un membro.</span><span class="sxs-lookup"><span data-stu-id="41e3c-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], a transaction is recorded each time action is taken on a member.</span></span> <span data-ttu-id="41e3c-104">Le transazioni possono essere visualizzate da tutti gli utenti e possono essere invertite dagli amministratori.</span><span class="sxs-lookup"><span data-stu-id="41e3c-104">Transactions can be viewed by all users and reversed by administrators.</span></span> <span data-ttu-id="41e3c-105">Nelle transazioni vengono indicati, tra gli altri dettagli, anche la data, l'ora e l'utente che ha eseguito l'azione.</span><span class="sxs-lookup"><span data-stu-id="41e3c-105">Transactions show the date, time, and user who took the action, along with other details.</span></span> <span data-ttu-id="41e3c-106">Gli utenti possono aggiungere un'annotazione a una transazione, per indicare il motivo per il quale si è verificata.</span><span class="sxs-lookup"><span data-stu-id="41e3c-106">Users can add an annotation to a transaction, to indicate why a transaction took place.</span></span>  
  
## <a name="when-transaction-are-recorded"></a><span data-ttu-id="41e3c-107">Quando vengono registrate le transazioni</span><span class="sxs-lookup"><span data-stu-id="41e3c-107">When Transaction Are Recorded</span></span>  
 <span data-ttu-id="41e3c-108">Le transazioni vengono registrate quando i membri:</span><span class="sxs-lookup"><span data-stu-id="41e3c-108">Transactions are recorded when members:</span></span>  
  
-   <span data-ttu-id="41e3c-109">Vengono creati, eliminati o riattivati.</span><span class="sxs-lookup"><span data-stu-id="41e3c-109">Are created, deleted, or reactivated.</span></span>  
  
-   <span data-ttu-id="41e3c-110">Vengono modificati i valori dei relativi attributi.</span><span class="sxs-lookup"><span data-stu-id="41e3c-110">Have attribute values changed.</span></span>  
  
-   <span data-ttu-id="41e3c-111">Vengono spostati in una gerarchia.</span><span class="sxs-lookup"><span data-stu-id="41e3c-111">Are moved in a hierarchy.</span></span>  
  
 <span data-ttu-id="41e3c-112">Le transazioni non vengono registrate quando i valori di attributo vengono modificati dalle regole business.</span><span class="sxs-lookup"><span data-stu-id="41e3c-112">Transactions are not recorded when business rules change attribute values.</span></span>  
  
## <a name="view-and-manage-transactions"></a><span data-ttu-id="41e3c-113">Visualizzare e gestire transazioni</span><span class="sxs-lookup"><span data-stu-id="41e3c-113">View and Manage Transactions</span></span>  
 <span data-ttu-id="41e3c-114">Nell'area funzionale **Visualizzatore** è possibile visualizzare e annotare le transazioni create, ovvero aggiungervi commenti.</span><span class="sxs-lookup"><span data-stu-id="41e3c-114">In the **Explorer** functional area, you can view and annotate (add comments to) the transactions that you made yourself.</span></span>  
  
 <span data-ttu-id="41e3c-115">Nell'area funzionale **Gestione versioni** gli amministratori possono visualizzare tutte le transazioni per tutti gli utenti per i modelli a cui possono accedere e invertire una di queste transazioni.</span><span class="sxs-lookup"><span data-stu-id="41e3c-115">In the **Version Management** functional area, administrators can view all transactions for all users for the models they have access to, and reverse any of these transactions.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="41e3c-116">Gli amministratori possono visualizzare tutte le transazioni per tutti gli utenti a condizione che non dispongano dell'autorizzazione di sola lettura applicata nell'area funzionale **Gestione versioni**.</span><span class="sxs-lookup"><span data-stu-id="41e3c-116">Administrators can view all transactions for all users as long as they don't have the read-only permission level applied in the **Version Management** functional area .</span></span> <span data-ttu-id="41e3c-117">Ad esempio, se è impostato il livello di autorizzazione di sola lettura e aggiornamento per l'amministratore, l'amministratore non può visualizzare altre transazioni utente perché l'autorizzazione di sola lettura ha la precedenza sull'autorizzazione di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="41e3c-117">For example, if the read-only permission and update permission level is set for the administrator, the administrator will not be able to see other user transactions because the read-only permission will take precedence over the update permission.</span></span>

## <a name="system-settings"></a><span data-ttu-id="41e3c-118">Impostazioni sistema</span><span class="sxs-lookup"><span data-stu-id="41e3c-118">System Settings</span></span>  
 <span data-ttu-id="41e3c-119">In [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] è disponibile un'impostazione che determina se le transazioni vengono registrate quando i record vengono gestiti in modo temporaneo.</span><span class="sxs-lookup"><span data-stu-id="41e3c-119">There is a setting in [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] that affects whether or not transactions are recorded when records are staged.</span></span> <span data-ttu-id="41e3c-120">Questa impostazione influisce solo su SQL Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="41e3c-120">This setting affects SQL Server 2008 R2 only.</span></span> <span data-ttu-id="41e3c-121">È possibile regolare questa impostazione in [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] o direttamente nella tabella Impostazioni sistema del database [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="41e3c-121">You can adjust this setting in [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] or directly in the System Settings table in the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database.</span></span> <span data-ttu-id="41e3c-122">Per altre informazioni, vedere [Impostazioni di sistema &#40;Master Data Services&#41;](system-settings-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="41e3c-122">For more information, see [System Settings &#40;Master Data Services&#41;](system-settings-master-data-services.md).</span></span>  
  
 <span data-ttu-id="41e3c-123">In caso di importazione di dati in questa versione di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], è possibile specificare se registrare transazioni all'avvio della stored procedure.</span><span class="sxs-lookup"><span data-stu-id="41e3c-123">When importing data in this version of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], you can specify whether or not to log transactions when initiating the stored procedure.</span></span> <span data-ttu-id="41e3c-124">Per altre informazioni, vedere [Stored procedure di gestione temporanea &#40;Master Data Services&#41;](../../2014/master-data-services/staging-stored-procedure-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="41e3c-124">For more information, see [Staging Stored Procedure &#40;Master Data Services&#41;](../../2014/master-data-services/staging-stored-procedure-master-data-services.md).</span></span>  
  
## <a name="concurrency"></a><span data-ttu-id="41e3c-125">Concorrenza</span><span class="sxs-lookup"><span data-stu-id="41e3c-125">Concurrency</span></span>  
 <span data-ttu-id="41e3c-126">Se un particolare valore dell'entità viene mostrato contemporaneamente in più di una sessione dello strumento di esplorazione, sono possibili modifiche simultanee allo stesso valore.</span><span class="sxs-lookup"><span data-stu-id="41e3c-126">If a particular entity value is shown simultaneously in more than one Explorer session, concurrent edits to the same value are possible.</span></span> <span data-ttu-id="41e3c-127">Le modifiche simultanee non verranno rilevate automaticamente da MDS.</span><span class="sxs-lookup"><span data-stu-id="41e3c-127">Concurrent edits will not be detected automatically by MDS.</span></span> <span data-ttu-id="41e3c-128">Questa situazione si può verificare quando più utenti utilizzano Esplora di MDS nel Web browser da più sessioni, ad esempio da più computer, più schede o finestre del browser o più account utente.</span><span class="sxs-lookup"><span data-stu-id="41e3c-128">This can occur when multiple users use the MDS Explorer in the Web browser from multiple sessions, for example from multiple computers, multiple browser tabs or windows, or multiple user accounts.</span></span>  
  
 <span data-ttu-id="41e3c-129">Più utenti possono aggiornare gli stessi valori dell'entità senza errore, nonostante transazioni abilitate.</span><span class="sxs-lookup"><span data-stu-id="41e3c-129">More than one user can update the same entity values without error despite transactions being enabled.</span></span> <span data-ttu-id="41e3c-130">In genere, l'ultima modifica al valore in una sequenza di tempo avrà la precedenza.</span><span class="sxs-lookup"><span data-stu-id="41e3c-130">Typically the last edit to the value in a sequence of time will take precedence.</span></span> <span data-ttu-id="41e3c-131">Il conflitto duplicato delle modifiche può essere osservato manualmente nella cronologia delle transazioni e invertito manualmente dall'amministratore.</span><span class="sxs-lookup"><span data-stu-id="41e3c-131">The duplicate edit conflict can be manually observed in the transaction history and can be reversed manually by the administrator.</span></span> <span data-ttu-id="41e3c-132">La cronologia delle transazioni mostra le singole transazioni in base a **Valore precedente** e **Nuovo valore** per l'attributo in questione di ogni sessione, ma non risolve automaticamente il conflitto se esistono più valori **Nuovi valori** per lo stesso valore precedente.</span><span class="sxs-lookup"><span data-stu-id="41e3c-132">The transaction history will show the individual transactions for the **Prior value** and **New value** for the attribute in question from each session, but will not automatically resolve the conflict when multiple **New Values** exist for the same old value.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="41e3c-133">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="41e3c-133">Related Tasks</span></span>  
  
|<span data-ttu-id="41e3c-134">Descrizione dell'attività</span><span class="sxs-lookup"><span data-stu-id="41e3c-134">Task Description</span></span>|<span data-ttu-id="41e3c-135">Argomento</span><span class="sxs-lookup"><span data-stu-id="41e3c-135">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="41e3c-136">Annullare un'azione invertendo una transazione (solo amministratori).</span><span class="sxs-lookup"><span data-stu-id="41e3c-136">Undo an action by reversing a transaction (administrators only).</span></span>|[<span data-ttu-id="41e3c-137">Invertire una transazione &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="41e3c-137">Reverse a Transaction &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/reverse-a-transaction-master-data-services.md)|  
  
## <a name="related-content"></a><span data-ttu-id="41e3c-138">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="41e3c-138">Related Content</span></span>  
  
-   [<span data-ttu-id="41e3c-139">Amministratori &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="41e3c-139">Administrators &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/administrators-master-data-services.md)  
  
-   [<span data-ttu-id="41e3c-140">Annotazioni &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="41e3c-140">Annotations &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/annotations-master-data-services.md)  
  
  
