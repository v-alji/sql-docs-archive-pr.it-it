---
title: Definisci filtri | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.replconflictviewer.definefilters.f1
helpviewer_keywords:
- Define Filters dialog box
ms.assetid: 1fa71d22-ce5a-4aae-ba05-4d755842aeac
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5154f002c5a35bc78e2eb6777f2cc7bb3d56b635
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624643"
---
# <a name="define-filters"></a><span data-ttu-id="5ccc3-102">Definisci filtri</span><span class="sxs-lookup"><span data-stu-id="5ccc3-102">Define Filters</span></span>
  <span data-ttu-id="5ccc3-103">La finestra di dialogo **Definisci filtri** consente di definire i filtri da applicare ai conflitti dei dati per visualizzare un subset dei conflitti nella griglia.</span><span class="sxs-lookup"><span data-stu-id="5ccc3-103">The **Define Filters** dialog box allows you to define filters that you then apply to data conflicts to see a subset of the conflicts in the grid.</span></span> <span data-ttu-id="5ccc3-104">Per definire un filtro, scegliere un operatore nell'elenco a discesa **Operatore** e quindi digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="5ccc3-104">To define a filter, choose an operator from the **Operator** drop-down list box and then enter a value.</span></span> <span data-ttu-id="5ccc3-105">Ad esempio, per visualizzare soltanto i conflitti in cui la riga in conflitto ignorata è il server **ReplTest1**, selezionare l'operatore **Uguale a** nell'elenco a discesa **Operatore** e immettere **ReplTest1** nella prima colonna **Valore** .</span><span class="sxs-lookup"><span data-stu-id="5ccc3-105">For example, to show only those conflicts in which the conflict loser is server **ReplTest1**, select **Equal to** from the **Operator** drop-down list box and enter **ReplTest1** in the first **Value** column.</span></span>  
  
## <a name="options"></a><span data-ttu-id="5ccc3-106">Opzioni</span><span class="sxs-lookup"><span data-stu-id="5ccc3-106">Options</span></span>  
 <span data-ttu-id="5ccc3-107">**Operatore**</span><span class="sxs-lookup"><span data-stu-id="5ccc3-107">**Operator**</span></span>  
 <span data-ttu-id="5ccc3-108">Consente di selezionare un operatore per il filtro, ad esempio **Minore o uguale a**.</span><span class="sxs-lookup"><span data-stu-id="5ccc3-108">Select an operator for the filter, such as **Less than or Equal to**.</span></span>  
  
 <span data-ttu-id="5ccc3-109">**Valore**</span><span class="sxs-lookup"><span data-stu-id="5ccc3-109">**Value**</span></span>  
 <span data-ttu-id="5ccc3-110">Consente di digitare un valore per il filtro.</span><span class="sxs-lookup"><span data-stu-id="5ccc3-110">Enter a value for the filter.</span></span> <span data-ttu-id="5ccc3-111">Per la maggior parte degli operatori è necessario specificare soltanto un valore nella prima colonna **Valore** , tuttavia, gli operatori **Compreso tra** e **Non compreso tra** richiedono un valore in entrambe le colonne **Valore** .</span><span class="sxs-lookup"><span data-stu-id="5ccc3-111">Most operators only require a value in the first **Value** column, but the **Between** and **Not Between** operators require a value in both of the **Value** columns.</span></span>  
  
 <span data-ttu-id="5ccc3-112">**Cancella**</span><span class="sxs-lookup"><span data-stu-id="5ccc3-112">**Clear**</span></span>  
 <span data-ttu-id="5ccc3-113">Fare clic su questo pulsante per cancellare tutti i filtri definiti in precedenza.</span><span class="sxs-lookup"><span data-stu-id="5ccc3-113">Click this button to clear all filters that have been previously defined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ccc3-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5ccc3-114">See Also</span></span>  
 <span data-ttu-id="5ccc3-115">[Visualizzatore conflitti di replica Microsoft &#40;replica di tipo merge&#41;](microsoft-replication-conflict-viewer-merge-replication.md) </span><span class="sxs-lookup"><span data-stu-id="5ccc3-115">[Microsoft Replication Conflict Viewer &#40;Merge Replication&#41;](microsoft-replication-conflict-viewer-merge-replication.md) </span></span>  
 [<span data-ttu-id="5ccc3-116">Visualizzatore conflitti di replica Microsoft &#40;replica di tipo transazionale&#41;</span><span class="sxs-lookup"><span data-stu-id="5ccc3-116">Microsoft Replication Conflict Viewer &#40;Transactional Replication&#41;</span></span>](microsoft-replication-conflict-viewer-transactional-replication.md)  
  
  
