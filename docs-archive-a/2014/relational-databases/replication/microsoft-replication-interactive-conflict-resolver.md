---
title: Sistema di risoluzione dei conflitti di replica interattivo Microsoft | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.replconflictviewer.interactiveresolver.f1
ms.assetid: d3d4a480-782b-4b1d-b839-565c8cf6cb24
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c8cbd2231ab1ab357321f9887bced986e182e608
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725524"
---
# <a name="microsoft-replication-interactive-conflict-resolver"></a><span data-ttu-id="cd243-102">Sistema di risoluzione dei conflitti di replica interattivo Microsoft</span><span class="sxs-lookup"><span data-stu-id="cd243-102">Microsoft Replication Interactive Conflict Resolver</span></span>
  <span data-ttu-id="cd243-103">Il sistema di risoluzione dei conflitti interattivo può essere utilizzato per le sottoscrizioni di tipo merge sincronizzate tramite Gestione sincronizzazione Microsoft Windows</span><span class="sxs-lookup"><span data-stu-id="cd243-103">The Interactive Conflict Resolver can be used for merge subscriptions that are synchronized using Windows Synchronization Manager.</span></span> <span data-ttu-id="cd243-104">e consente di visualizzare, confrontare, modificare e selezionare i risultati dei conflitti di dati.</span><span class="sxs-lookup"><span data-stu-id="cd243-104">It allows you to view, compare, edit, and select the outcome for data conflicts.</span></span> <span data-ttu-id="cd243-105">È inoltre disponibile il Visualizzatore conflitti, che consente di visualizzare e modificare i risultati dei conflitti dopo il commit.</span><span class="sxs-lookup"><span data-stu-id="cd243-105">Replication also includes the Conflict Viewer, which allows you to view and modify conflict outcomes after they have been committed.</span></span> <span data-ttu-id="cd243-106">Con il sistema di risoluzione dei conflitti interattivo è possibile selezionare il risultato durante la sincronizzazione.</span><span class="sxs-lookup"><span data-stu-id="cd243-106">The Interactive Conflict Resolver allows you to select the outcome during synchronization.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cd243-107">I conflitti a livello di record logici non vengono visualizzati nel sistema di risoluzione interattivo.</span><span class="sxs-lookup"><span data-stu-id="cd243-107">Conflicts that involve logical records are not displayed in the Interactive Resolver.</span></span> <span data-ttu-id="cd243-108">Per visualizzare informazioni relative a questi conflitti, utilizzare le stored procedure di replica.</span><span class="sxs-lookup"><span data-stu-id="cd243-108">To view information about these conflicts, use replication stored procedures.</span></span> <span data-ttu-id="cd243-109">Per altre informazioni, vedere [Visualizzare le informazioni sui conflitti per le pubblicazioni di tipo merge &#40;programmazione Transact-SQL della replica&#41;](view-conflict-information-for-merge-publications.md).</span><span class="sxs-lookup"><span data-stu-id="cd243-109">For more information, see [View Conflict Information for Merge Publications &#40;Replication Transact-SQL Programming&#41;](view-conflict-information-for-merge-publications.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="cd243-110">Opzioni</span><span class="sxs-lookup"><span data-stu-id="cd243-110">Options</span></span>  
 <span data-ttu-id="cd243-111">**Nome colonna**</span><span class="sxs-lookup"><span data-stu-id="cd243-111">**Column name**</span></span>  
 <span data-ttu-id="cd243-112">Nome di tutte le colonne nella tabella.</span><span class="sxs-lookup"><span data-stu-id="cd243-112">The name of all columns in the table.</span></span> <span data-ttu-id="cd243-113">È possibile che una o più colonne contengano dati in conflitto.</span><span class="sxs-lookup"><span data-stu-id="cd243-113">One or more columns might have conflicting data.</span></span> <span data-ttu-id="cd243-114">Indipendentemente da quali siano le colonne in conflitto, l'intera riga confermata sovrascriverà l'intera riga non confermata.</span><span class="sxs-lookup"><span data-stu-id="cd243-114">Regardless of which columns conflict, the entire winning row will overwrite the entire losing row.</span></span>  
  
 <span data-ttu-id="cd243-115">**Risoluzione suggerita**</span><span class="sxs-lookup"><span data-stu-id="cd243-115">**Suggested Resolution**</span></span>  
 <span data-ttu-id="cd243-116">Risoluzione suggerita indicata dal sistema di risoluzione dei conflitti per l'articolo.</span><span class="sxs-lookup"><span data-stu-id="cd243-116">The suggested resolution provided by the conflict resolver for the article.</span></span>  
  
 <span data-ttu-id="cd243-117">**Autore**</span><span class="sxs-lookup"><span data-stu-id="cd243-117">**Publisher**</span></span>  
 <span data-ttu-id="cd243-118">Il valore di dati nel server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="cd243-118">The data value at the Publisher.</span></span>  
  
 <span data-ttu-id="cd243-119">**Sottoscrittore**</span><span class="sxs-lookup"><span data-stu-id="cd243-119">**Subscriber**</span></span>  
 <span data-ttu-id="cd243-120">Il valore di dati nel Sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="cd243-120">The data value at the Subscriber.</span></span>  
  
 <span data-ttu-id="cd243-121">**Accetta soluzione proposta**, **Accetta server di pubblicazione**e **Accetta Sottoscrittore**</span><span class="sxs-lookup"><span data-stu-id="cd243-121">**Accept Suggested**, **Accept Publisher**, and **Accept Subscriber**</span></span>  
 <span data-ttu-id="cd243-122">Fare clic su questo pulsante per accettare la riga che verrà applicata al server di pubblicazione o al Sottoscrittore, a seconda della riga che prevale nel conflitto.</span><span class="sxs-lookup"><span data-stu-id="cd243-122">Click to accept the row that will be applied at either the Publisher or the Subscriber, depending on which one lost the conflict.</span></span> <span data-ttu-id="cd243-123">Se la riga del server di pubblicazione non viene confermata, tutti gli altri Sottoscrittori riceveranno la riga confermata durante la successiva sincronizzazione con il server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="cd243-123">If the Publisher lost the conflict, all other Subscribers will receive the winning row the next time they synchronize with the Publisher.</span></span>  
  
 <span data-ttu-id="cd243-124">**Risoluzione automatica conflitti rimanenti**</span><span class="sxs-lookup"><span data-stu-id="cd243-124">**Resolve remaining conflicts automatically**</span></span>  
 <span data-ttu-id="cd243-125">Risolve tutti i conflitti rimanenti utilizzando la risoluzione suggerita indicata dal sistema di risoluzione dei conflitti per l'articolo.</span><span class="sxs-lookup"><span data-stu-id="cd243-125">Resolve all remaining conflicts using the suggested resolution provided by the conflict resolver for the article.</span></span>  
  
 <span data-ttu-id="cd243-126">**Registra informazioni dettagliate sul conflitto per riferimenti futuri**</span><span class="sxs-lookup"><span data-stu-id="cd243-126">**Log the details of the conflict for later reference**</span></span>  
 <span data-ttu-id="cd243-127">Registra informazioni dettagliate sul conflitto nelle tabelle di sistema.</span><span class="sxs-lookup"><span data-stu-id="cd243-127">Logs the details of the conflict in system tables.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd243-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cd243-128">See Also</span></span>  
 <span data-ttu-id="cd243-129">[Risoluzione interattiva dei conflitti](merge/advanced-merge-replication-conflict-interactive-resolution.md) </span><span class="sxs-lookup"><span data-stu-id="cd243-129">[Interactive Conflict Resolution](merge/advanced-merge-replication-conflict-interactive-resolution.md) </span></span>  
 <span data-ttu-id="cd243-130">[Visualizzare e risolvere i conflitti di dati per le pubblicazioni di tipo merge &#40;SQL Server Management Studio&#41;](view-and-resolve-data-conflicts-for-merge-publications.md) </span><span class="sxs-lookup"><span data-stu-id="cd243-130">[View and Resolve Data Conflicts for Merge Publications &#40;SQL Server Management Studio&#41;](view-and-resolve-data-conflicts-for-merge-publications.md) </span></span>  
 <span data-ttu-id="cd243-131">[Sincronizzare una sottoscrizione mediante Gestione sincronizzazione Microsoft Windows &#40;Gestione sincronizzazione Microsoft&#41;](synchronize-a-subscription-using-windows-synchronization-manager.md) </span><span class="sxs-lookup"><span data-stu-id="cd243-131">[Synchronize a Subscription Using Windows Synchronization Manager &#40;Windows Synchronization Manager&#41;](synchronize-a-subscription-using-windows-synchronization-manager.md) </span></span>  
 [<span data-ttu-id="cd243-132">Rilevamento e risoluzione avanzati dei conflitti nella replica di tipo merge</span><span class="sxs-lookup"><span data-stu-id="cd243-132">Advanced Merge Replication Conflict Detection and Resolution</span></span>](merge/advanced-merge-replication-conflict-detection-and-resolution.md)  
  
  
