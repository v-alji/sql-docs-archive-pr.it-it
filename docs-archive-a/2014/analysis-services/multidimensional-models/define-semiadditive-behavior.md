---
title: Definire il comportamento di funzioni semiadditive | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- semiadditive
- Business Intelligence enhancements [Analysis Services], semiadditive behavior
- measures [Analysis Services], semiadditive
ms.assetid: b25726bc-728b-4601-ad87-9015c39dc615
author: minewiskan
ms.author: owend
ms.openlocfilehash: 9c2028c350046fdcc9f98bcd0f0612d6a91ccabb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629088"
---
# <a name="define-semiadditive-behavior"></a><span data-ttu-id="ec3ef-102">Definire una funzione semiadditiva</span><span class="sxs-lookup"><span data-stu-id="ec3ef-102">Define Semiadditive Behavior</span></span>
  <span data-ttu-id="ec3ef-103">Le misure semiadditive, che non aggregano in modo uniforme di tutte le dimensioni, sono molto comuni in numerosi scenari aziendali.</span><span class="sxs-lookup"><span data-stu-id="ec3ef-103">Semiadditive measures, which do not uniformly aggregate across all dimensions, are very common in many business scenarios.</span></span> <span data-ttu-id="ec3ef-104">Ogni cubo basato su snapshot di saldi nel tempo sono caratterizzati da questo problema.</span><span class="sxs-lookup"><span data-stu-id="ec3ef-104">Every cube that is based on snapshots of balances over time exhibits this problem.</span></span> <span data-ttu-id="ec3ef-105">Questi snapshot si trovano in applicazioni per la gestione di titoli, saldi contabili, budget, risorse umane, polizze e risarcimenti assicurativi e numerosi altri scenari aziendali.</span><span class="sxs-lookup"><span data-stu-id="ec3ef-105">You can find these snapshots in applications dealing with securities, account balances, budgeting, human resources, insurance policies and claims, and many other business domains.</span></span>  
  
 <span data-ttu-id="ec3ef-106">L'aggiunta di funzioni semiadditive a un cubo consente di definire un metodo di aggregazione per singole misure o singoli membri dell'attributo del tipo Conto.</span><span class="sxs-lookup"><span data-stu-id="ec3ef-106">Add semiadditive behavior to a cube to define an aggregation method for individual measures or members of the account type attribute.</span></span> <span data-ttu-id="ec3ef-107">Se il cubo contiene una dimensione di tipo Conti, è possibile impostare automaticamente le funzioni semiadditive in base al tipo di conto.</span><span class="sxs-lookup"><span data-stu-id="ec3ef-107">If the cube contains an account dimension, you can automatically set semiadditive behavior based on the account type.</span></span>  
  
 <span data-ttu-id="ec3ef-108">Per aggiungere funzioni semiadditive aprire un cubo in Progettazione cubi e scegliere **Aggiungi funzionalità di Business Intelligence** dal menu Cubo.</span><span class="sxs-lookup"><span data-stu-id="ec3ef-108">To add semiadditive behavior, open a cube in Cube Designer and choose **Add Business Intelligence** from the Cube menu.</span></span> <span data-ttu-id="ec3ef-109">Nella Configurazione guidata funzionalità di Business Intelligence selezionare l'opzione **Definizione funzioni semiadditive** nella pagina **Scelta funzionalità avanzata** .</span><span class="sxs-lookup"><span data-stu-id="ec3ef-109">In the Business Intelligence Wizard, select the **Define semiadditive behavior** option on the **Choose Enhancement** page.</span></span> <span data-ttu-id="ec3ef-110">Questa procedura guidata consente di eseguire in modo semplificato i passaggi necessari per definire le misure contenenti funzioni semiadditive.</span><span class="sxs-lookup"><span data-stu-id="ec3ef-110">This wizard then guides you through the steps of identifying which measures have semiadditive behavior.</span></span>  
  
 <span data-ttu-id="ec3ef-111">Ad eccezione di LastChild disponibile nell'edizione Standard, le funzioni semiadditive sono disponibili solo in Business Intelligence o nelle edizioni Enterprise.</span><span class="sxs-lookup"><span data-stu-id="ec3ef-111">With the exception of LastChild which is available in the standard edition, semi-additive behaviors are only available in the business intelligence or enterprise editions.</span></span>  
  
## <a name="define-semiadditive-behavior"></a><span data-ttu-id="ec3ef-112">Definire una funzione semiadditiva</span><span class="sxs-lookup"><span data-stu-id="ec3ef-112">Define Semiadditive Behavior</span></span>  
 <span data-ttu-id="ec3ef-113">Nella pagina **Definizione funzioni semiadditive** della procedura guidata selezionare la modalità di definizione delle funzioni semiadditive selezionando una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ec3ef-113">On the **Define Semiadditive Behavior** page of the wizard, you select how to define semiadditivity by selecting one of the following options:</span></span>  
  
 <span data-ttu-id="ec3ef-114">**Disabilita funzioni semiadditive**</span><span class="sxs-lookup"><span data-stu-id="ec3ef-114">**Turn off semiadditive behavior**</span></span>  
 <span data-ttu-id="ec3ef-115">Consente di rimuovere le funzioni semiadditive da un cubo in cui tali funzioni sono state precedentemente definite.</span><span class="sxs-lookup"><span data-stu-id="ec3ef-115">Removes semiadditive behavior from a cube in which semiadditive behavior was previously defined.</span></span> <span data-ttu-id="ec3ef-116">Se si seleziona questa opzione, una misura viene reimpostata su `SUM` se è impostata su uno dei tipi di funzione di aggregazione seguenti:</span><span class="sxs-lookup"><span data-stu-id="ec3ef-116">This selection resets a measure to `SUM` if it is set to any of the following aggregation function types:</span></span>  
  
-   <span data-ttu-id="ec3ef-117">By Account</span><span class="sxs-lookup"><span data-stu-id="ec3ef-117">By Account</span></span>  
  
-   <span data-ttu-id="ec3ef-118">Average of Children</span><span class="sxs-lookup"><span data-stu-id="ec3ef-118">Average of Children</span></span>  
  
-   <span data-ttu-id="ec3ef-119">First Child</span><span class="sxs-lookup"><span data-stu-id="ec3ef-119">First Child</span></span>  
  
-   <span data-ttu-id="ec3ef-120">Last Child</span><span class="sxs-lookup"><span data-stu-id="ec3ef-120">Last Child</span></span>  
  
-   <span data-ttu-id="ec3ef-121">Last Nonempty Child</span><span class="sxs-lookup"><span data-stu-id="ec3ef-121">Last Nonempty Child</span></span>  
  
-   <span data-ttu-id="ec3ef-122">First Nonempty Child</span><span class="sxs-lookup"><span data-stu-id="ec3ef-122">First Nonempty Child</span></span>  
  
-   <span data-ttu-id="ec3ef-123">Nessuno</span><span class="sxs-lookup"><span data-stu-id="ec3ef-123">None</span></span>  
  
 <span data-ttu-id="ec3ef-124">Questa opzione non modifica le misure con una funzione di aggregazione regolare: `Sum` ,, `Min` `Max` , `Count` o `Distinct``Count` .</span><span class="sxs-lookup"><span data-stu-id="ec3ef-124">This option does not change measures with a regular aggregation function: `Sum`, `Min`, `Max`, `Count`, or `Distinct``Count`.</span></span>  
  
 <span data-ttu-id="ec3ef-125">**La procedura guidata ha rilevato la dimensione di tipo Conti ' account ', che contiene membri funzioni semiadditive. Il server aggrega i membri di questa dimensione in base al comportamento funzioni semiadditive specificato per ogni tipo di conto.**</span><span class="sxs-lookup"><span data-stu-id="ec3ef-125">**The wizard has detected the 'Account" account dimension, which contains semiadditive members. The server will aggregate members of this dimension according to the semiadditive behavior specified for each account type.**</span></span>  
 <span data-ttu-id="ec3ef-126">Tutte le misure di un gruppo di misure dimensionate in base a una dimensione di tipo Conti verranno impostate dal sistema sulla funzione di aggregazione By Account e i membri della dimensione verranno aggregati dal server in base alle funzioni semiadditive specificate per ogni tipo di conto.</span><span class="sxs-lookup"><span data-stu-id="ec3ef-126">Causes the system to set all measures from a measure group dimensioned by an Account type dimension to the By Account aggregation function and the server will aggregate members of the dimension according to the semiadditive behavior specified for each account type.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ec3ef-127">Questa opzione è selezionata per impostazione predefinita se la procedura guidata rileva una dimensione di tipo Conti.</span><span class="sxs-lookup"><span data-stu-id="ec3ef-127">This option is selected by default if the wizard detects an Account type dimension.</span></span>  
  
 <span data-ttu-id="ec3ef-128">**Definisci funzioni semiadditive per singole misure**</span><span class="sxs-lookup"><span data-stu-id="ec3ef-128">**Define semiadditive behavior for individual measures**</span></span>  
 <span data-ttu-id="ec3ef-129">Consente di selezionare individualmente le funzioni semiadditive di ogni misura.</span><span class="sxs-lookup"><span data-stu-id="ec3ef-129">Selects the semiadditive behavior of each measure individually.</span></span> <span data-ttu-id="ec3ef-130">L'impostazione predefinita è `SUM` (additività completa).</span><span class="sxs-lookup"><span data-stu-id="ec3ef-130">The default setting is `SUM` (fully additive).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ec3ef-131">Questa opzione è selezionata per impostazione predefinita se la procedura guidata non rileva una dimensione di tipo Conti.</span><span class="sxs-lookup"><span data-stu-id="ec3ef-131">This option is selected by default if the wizard does not detect an Account type dimension.</span></span>  
  
 <span data-ttu-id="ec3ef-132">Per ogni misura è possibile selezionare tra i tipi di funzionalità semiadditive descritti nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="ec3ef-132">For each measure, you can select from the types of semiadditive functionality described in the following table.</span></span>  
  
|<span data-ttu-id="ec3ef-133">Funzione semiadditiva</span><span class="sxs-lookup"><span data-stu-id="ec3ef-133">Semiadditive function</span></span>|<span data-ttu-id="ec3ef-134">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ec3ef-134">Description</span></span>|  
|---------------------------|-----------------|  
|<span data-ttu-id="ec3ef-135">Average of Children</span><span class="sxs-lookup"><span data-stu-id="ec3ef-135">Average of Children</span></span>|<span data-ttu-id="ec3ef-136">La funzione di aggregazione di un membro corrisponde alla media dei relativi figli.</span><span class="sxs-lookup"><span data-stu-id="ec3ef-136">The aggregation of a member is the average of its children.</span></span>|  
|<span data-ttu-id="ec3ef-137">ByAccount</span><span class="sxs-lookup"><span data-stu-id="ec3ef-137">ByAccount</span></span>|<span data-ttu-id="ec3ef-138">Il sistema legge le funzioni semiadditive specificate per il tipo di conto.</span><span class="sxs-lookup"><span data-stu-id="ec3ef-138">The system reads the semiadditive behavior specified for the account type.</span></span>|  
|<span data-ttu-id="ec3ef-139">Conteggio</span><span class="sxs-lookup"><span data-stu-id="ec3ef-139">Count</span></span>|<span data-ttu-id="ec3ef-140">La funzione di aggregazione corrisponde a un conteggio dei membri.</span><span class="sxs-lookup"><span data-stu-id="ec3ef-140">The aggregation is a count of members.</span></span>|  
|<span data-ttu-id="ec3ef-141">Distinct Count</span><span class="sxs-lookup"><span data-stu-id="ec3ef-141">Distinct Count</span></span>|<span data-ttu-id="ec3ef-142">La funzione di aggregazione corrisponde a un conteggio dei membri univoci.</span><span class="sxs-lookup"><span data-stu-id="ec3ef-142">The aggregation is a count of unique members.</span></span>|  
|<span data-ttu-id="ec3ef-143">First Child</span><span class="sxs-lookup"><span data-stu-id="ec3ef-143">First Child</span></span>|<span data-ttu-id="ec3ef-144">Il valore del membro viene valutato come il valore del relativo primo figlio assieme alla dimensione temporale.</span><span class="sxs-lookup"><span data-stu-id="ec3ef-144">The member value is evaluated as the value of its first child along the time dimension.</span></span>|  
|<span data-ttu-id="ec3ef-145">FirstNonEmpty</span><span class="sxs-lookup"><span data-stu-id="ec3ef-145">FirstNonEmpty</span></span>|<span data-ttu-id="ec3ef-146">Il valore del membro viene valutato come il valore del relativo primo figlio assieme alla dimensione temporale contenente dati.</span><span class="sxs-lookup"><span data-stu-id="ec3ef-146">The member value is evaluated as the value of its first child along the time dimension that contains data.</span></span>|  
|<span data-ttu-id="ec3ef-147">LastChild</span><span class="sxs-lookup"><span data-stu-id="ec3ef-147">LastChild</span></span>|<span data-ttu-id="ec3ef-148">Il valore del membro viene valutato come il valore del relativo ultimo figlio assieme alla dimensione temporale.</span><span class="sxs-lookup"><span data-stu-id="ec3ef-148">The member value is evaluated as the value of its last child along the time dimension.</span></span>|  
|<span data-ttu-id="ec3ef-149">LastNonEmpty</span><span class="sxs-lookup"><span data-stu-id="ec3ef-149">LastNonEmpty</span></span>|<span data-ttu-id="ec3ef-150">Il valore del membro viene valutato come il valore del relativo ultimo figlio assieme alla dimensione temporale contenente dati.</span><span class="sxs-lookup"><span data-stu-id="ec3ef-150">The member value is evaluated as the value of its last child along the time dimension that contains data.</span></span>|  
|<span data-ttu-id="ec3ef-151">Max</span><span class="sxs-lookup"><span data-stu-id="ec3ef-151">Max</span></span>|<span data-ttu-id="ec3ef-152">Viene applicata la funzione di aggregazione massima standard.</span><span class="sxs-lookup"><span data-stu-id="ec3ef-152">The standard maximum aggregation function is applied.</span></span>|  
|<span data-ttu-id="ec3ef-153">Min</span><span class="sxs-lookup"><span data-stu-id="ec3ef-153">Min</span></span>|<span data-ttu-id="ec3ef-154">Viene applicata la funzione di aggregazione minima standard.</span><span class="sxs-lookup"><span data-stu-id="ec3ef-154">The standard minimum aggregation function is applied.</span></span>|  
|<span data-ttu-id="ec3ef-155">Nessuno</span><span class="sxs-lookup"><span data-stu-id="ec3ef-155">None</span></span>|<span data-ttu-id="ec3ef-156">Non viene applicata alcuna funzione di aggregazione.</span><span class="sxs-lookup"><span data-stu-id="ec3ef-156">No aggregation is applied.</span></span>|  
|<span data-ttu-id="ec3ef-157">Somma</span><span class="sxs-lookup"><span data-stu-id="ec3ef-157">Sum</span></span>|<span data-ttu-id="ec3ef-158">Viene applicata la funzione di somma standard.</span><span class="sxs-lookup"><span data-stu-id="ec3ef-158">The standard summation function is applied.</span></span>|  
  
 <span data-ttu-id="ec3ef-159">Al termine della procedura guidata le funzioni semiadditive esistenti vengono sovrascritte.</span><span class="sxs-lookup"><span data-stu-id="ec3ef-159">Any existing semiadditive behavior is overwritten when you complete the wizard.</span></span>  
  
  
