---
title: Pubblicazione di dati (Componente aggiuntivo MDS per Excel) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: ea84a9aa-aeec-411b-ab8d-bc1b14f864a3
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: ab37a353469d1902394a3e2cd8060d9be82abb40
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720214"
---
# <a name="publishing-data-mds-add-in-for-excel"></a><span data-ttu-id="d7bd4-102">Pubblicazione dei dati (componente aggiuntivo MDS per Excel)</span><span class="sxs-lookup"><span data-stu-id="d7bd4-102">Publishing Data (MDS Add-in for Excel)</span></span>
  <span data-ttu-id="d7bd4-103">In [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)]pubblicare i dati nel repository MDS per condividerlo con altri utenti.</span><span class="sxs-lookup"><span data-stu-id="d7bd4-103">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], publish data to the MDS repository when you want to share it with other users.</span></span> <span data-ttu-id="d7bd4-104">Appena i dati vengono pubblicati, sono disponibili per essere scaricati dagli altri utenti del componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="d7bd4-104">As soon as data is published, it is available for other users of the Add-in to download.</span></span>  
  
 <span data-ttu-id="d7bd4-105">Quando si pubblicano dati, tutti i dati aggiunti o aggiornati vengono pubblicati nel repository MDS.</span><span class="sxs-lookup"><span data-stu-id="d7bd4-105">When you publish data, any data you've added or updated is published to the MDS repository.</span></span> <span data-ttu-id="d7bd4-106">I dati eliminati non vengono pubblicati; i dati devono essere eliminati separatamente.</span><span class="sxs-lookup"><span data-stu-id="d7bd4-106">Data you've deleted is not published-you must delete data separately.</span></span> <span data-ttu-id="d7bd4-107">Per altre informazioni, vedere [Eliminare una riga &#40;componente aggiuntivo MDS per Excel&#41;](delete-a-row-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="d7bd4-107">For more information, see [Delete a Row &#40;MDS Add-in for Excel&#41;](delete-a-row-mds-add-in-for-excel.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d7bd4-108">La pubblicazione non può essere utilizzata per creare una nuova entità.</span><span class="sxs-lookup"><span data-stu-id="d7bd4-108">Publishing cannot be used to create a new entity.</span></span> <span data-ttu-id="d7bd4-109">Per altre informazioni sulla creazione di entità, vedere [Creare un'entità &#40;componente aggiuntivo MDS per Excel&#41;](create-an-entity-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="d7bd4-109">For more information about creating entities, see [Create an Entity &#40;MDS Add-in for Excel&#41;](create-an-entity-mds-add-in-for-excel.md).</span></span>  
  
## <a name="when-multiple-users-publish-at-the-same-time"></a><span data-ttu-id="d7bd4-110">Quando più utenti pubblicano contemporaneamente</span><span class="sxs-lookup"><span data-stu-id="d7bd4-110">When Multiple Users Publish at the Same Time</span></span>  
 <span data-ttu-id="d7bd4-111">Più utenti possono pubblicare aggiornamenti agli stessi dati.</span><span class="sxs-lookup"><span data-stu-id="d7bd4-111">Multiple users can publish updates to the same data.</span></span> <span data-ttu-id="d7bd4-112">Appena ogni utente pubblica dati, l'aggiornamento viene salvato nel database.</span><span class="sxs-lookup"><span data-stu-id="d7bd4-112">As each user publishes, the update is saved to the database.</span></span> <span data-ttu-id="d7bd4-113">Pertanto, un utente che non sta utilizzando i dati aggiornati più di recente può ancora modificare il valore quando li pubblica.</span><span class="sxs-lookup"><span data-stu-id="d7bd4-113">This means that a user who was not working with the most recently-updated data can still change the value when he or she publishes.</span></span>  
  
 <span data-ttu-id="d7bd4-114">Solo gli aggiornamenti apportati vengono pubblicati nel database.</span><span class="sxs-lookup"><span data-stu-id="d7bd4-114">Only the updates you make are published to the database.</span></span> <span data-ttu-id="d7bd4-115">Tutti i dati non aggiornati nel foglio di lavoro non vengono pubblicati.</span><span class="sxs-lookup"><span data-stu-id="d7bd4-115">Any out-of-date data in the worksheet is not published.</span></span>  
  
## <a name="transactions-and-annotations"></a><span data-ttu-id="d7bd4-116">Transazioni e annotazioni</span><span class="sxs-lookup"><span data-stu-id="d7bd4-116">Transactions and Annotations</span></span>  
 <span data-ttu-id="d7bd4-117">Ogni modifica pubblicata viene salvata come una transazione.</span><span class="sxs-lookup"><span data-stu-id="d7bd4-117">Each published change is saved as a transaction.</span></span> <span data-ttu-id="d7bd4-118">Se lo si desidera, è possibile aggiungere annotazioni (commenti) a una transazione per spiegare il motivo della modifica apportata.</span><span class="sxs-lookup"><span data-stu-id="d7bd4-118">If you choose, you can add annotations (comments) to a transaction, to explain why you made the change.</span></span>  
  
-   <span data-ttu-id="d7bd4-119">Non è possibile annotare eliminazioni, anche se le eliminazioni vengono salvate come transazioni che possono essere annullate da un amministratore.</span><span class="sxs-lookup"><span data-stu-id="d7bd4-119">You cannot annotate deletions, although deletions are saved as transactions that can be reversed by an administrator.</span></span>  
  
-   <span data-ttu-id="d7bd4-120">Se si modifica il valore del **codice** per un membro, questo non viene registrato come transazione e tutte le transazioni precedenti per il membro non sono disponibili.</span><span class="sxs-lookup"><span data-stu-id="d7bd4-120">If you change the **Code** value for a member, it is not recorded as a transaction, and all previous transactions for the member are unavailable.</span></span>  
  
-   <span data-ttu-id="d7bd4-121">È possibile visualizzare le transazioni effettuate per un membro dagli altri utenti.</span><span class="sxs-lookup"><span data-stu-id="d7bd4-121">You can view transactions made to a member by other users.</span></span> <span data-ttu-id="d7bd4-122">È possibile visualizzare anche tutte le transazioni effettuate per un membro, anche se non si dispone più delle autorizzazioni per specifici attributi.</span><span class="sxs-lookup"><span data-stu-id="d7bd4-122">You can also view all transactions you've made to a member, even if you no longer have permission to specific attributes.</span></span>  
  
 <span data-ttu-id="d7bd4-123">È possibile visualizzare tutte le transazioni effettuate per un membro.</span><span class="sxs-lookup"><span data-stu-id="d7bd4-123">You can view all transactions made to a member.</span></span> <span data-ttu-id="d7bd4-124">Per altre informazioni, vedere [Visualizzare tutte le annotazioni o transazioni per un membro &#40;componente aggiuntivo MDS per Excel&#41;](view-all-annotations-or-transactions-for-a-member-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="d7bd4-124">For more information, see [View All Annotations or Transactions for a Member &#40;MDS Add-in for Excel&#41;](view-all-annotations-or-transactions-for-a-member-mds-add-in-for-excel.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="d7bd4-125">Se si immette un'annotazione con una lunghezza superiore a 500 caratteri, l'annotazione viene troncata automaticamente.</span><span class="sxs-lookup"><span data-stu-id="d7bd4-125">If you enter an annotation of more than 500 characters, the annotation is automatically truncated.</span></span>  
  
## <a name="business-rule-and-other-validation"></a><span data-ttu-id="d7bd4-126">Regola business e altre convalide</span><span class="sxs-lookup"><span data-stu-id="d7bd4-126">Business Rule and Other Validation</span></span>  
 <span data-ttu-id="d7bd4-127">Quando si pubblicano dati, la convalida viene eseguita per assicurare che i dati siano esatti prima di aggiungerli al repository MDS.</span><span class="sxs-lookup"><span data-stu-id="d7bd4-127">When you publish data, validation is performed to ensure data is accurate before it's added to the MDS repository.</span></span> <span data-ttu-id="d7bd4-128">Se i dati non soddisfano i criteri specificati, non verranno pubblicati nel repository.</span><span class="sxs-lookup"><span data-stu-id="d7bd4-128">If the data does not meet specified criteria, it will not be published to the repository.</span></span> <span data-ttu-id="d7bd4-129">Per altre informazioni, vedere [Convalida dei dati &#40;componente aggiuntivo MDS per Excel&#41;](validating-data-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="d7bd4-129">For more information, see [Validating Data &#40;MDS Add-in for Excel&#41;](validating-data-mds-add-in-for-excel.md).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="d7bd4-130">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="d7bd4-130">Related Tasks</span></span>  
  
|<span data-ttu-id="d7bd4-131">Descrizione dell'attività</span><span class="sxs-lookup"><span data-stu-id="d7bd4-131">Task Description</span></span>|<span data-ttu-id="d7bd4-132">Argomento</span><span class="sxs-lookup"><span data-stu-id="d7bd4-132">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="d7bd4-133">Pubblicare dati dal foglio di lavoro attivo nel repository MDS.</span><span class="sxs-lookup"><span data-stu-id="d7bd4-133">Publish data from the active worksheet back to the MDS repository.</span></span>|[<span data-ttu-id="d7bd4-134">Pubblicare dati da Excel a MDS &#40;Componente aggiuntivo MDS per Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="d7bd4-134">Publish Data from Excel to MDS &#40;MDS Add-in for Excel&#41;</span></span>](import-data-from-excel-to-master-data-services-mds-add-in-for-excel.md)|  
|<span data-ttu-id="d7bd4-135">Eliminare contemporaneamente una riga dal repository MDS e dal foglio di lavoro.</span><span class="sxs-lookup"><span data-stu-id="d7bd4-135">Delete a row from the MDS repository and from the worksheet at the same time.</span></span>|[<span data-ttu-id="d7bd4-136">Eliminare una riga &#40;componente aggiuntivo MDS per Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="d7bd4-136">Delete a Row &#40;MDS Add-in for Excel&#41;</span></span>](delete-a-row-mds-add-in-for-excel.md)|  
  
## <a name="related-content"></a><span data-ttu-id="d7bd4-137">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="d7bd4-137">Related Content</span></span>  
  
-   [<span data-ttu-id="d7bd4-138">Aggiornamento dei dati &#40;Componente aggiuntivo MDS per Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="d7bd4-138">Refreshing Data &#40;MDS Add-in for Excel&#41;</span></span>](refreshing-data-mds-add-in-for-excel.md)  
  
-   [<span data-ttu-id="d7bd4-139">Componente aggiuntivo Master Data Services per Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="d7bd4-139">Master Data Services Add-in for Microsoft Excel</span></span>](master-data-services-add-in-for-microsoft-excel.md)  
  
  
