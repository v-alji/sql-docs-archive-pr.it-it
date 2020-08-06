---
title: Opzioni griglia variabili | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.variableoptionswindow.f1
helpviewer_keywords:
- Choose Variable Columns dialog box
ms.assetid: 7cccc230-3b20-4074-804f-3448d9616a83
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b90e1a3c69e4eaf1f123603e0082ecb1eda4e893
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625443"
---
# <a name="variable-grid-options"></a><span data-ttu-id="76b20-102">Opzioni griglia variabili</span><span class="sxs-lookup"><span data-stu-id="76b20-102">Variable Grid Options</span></span>
  <span data-ttu-id="76b20-103">Utilizzare la finestra di dialogo **Opzioni griglia variabili** per selezionare le colonne che verranno visualizzate nella finestra **Variabili** e per selezionare i filtri da applicare all'elenco di variabili.</span><span class="sxs-lookup"><span data-stu-id="76b20-103">Use the **Variable Grid Options** dialog box to select the columns that will display in the **Variables** window and to select the filters to apply to the list of variables.</span></span> <span data-ttu-id="76b20-104">Per altre informazioni sulle proprietà delle variabili corrispondenti, vedere [Variabili di Integration Services &#40;SSIS&#41;](integration-services-ssis-variables.md).</span><span class="sxs-lookup"><span data-stu-id="76b20-104">For more information about the corresponding variable properties, see [Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md).</span></span>  
  
## <a name="options-for-filter"></a><span data-ttu-id="76b20-105">Opzioni per il filtro</span><span class="sxs-lookup"><span data-stu-id="76b20-105">Options for Filter</span></span>  
 <span data-ttu-id="76b20-106">**Mostra variabili di sistema**</span><span class="sxs-lookup"><span data-stu-id="76b20-106">**Show system variables**</span></span>  
 <span data-ttu-id="76b20-107">Selezionare questa opzione per elencare le variabili di sistema nella finestra **Variabili** .</span><span class="sxs-lookup"><span data-stu-id="76b20-107">Select to list system variables in the **Variables** window.</span></span> <span data-ttu-id="76b20-108">Le variabili di sistema sono predefinite</span><span class="sxs-lookup"><span data-stu-id="76b20-108">System variables are predefined.</span></span> <span data-ttu-id="76b20-109">Non è possibile aggiungere né eliminare le variabili di sistema.</span><span class="sxs-lookup"><span data-stu-id="76b20-109">You cannot add or delete system variables.</span></span> <span data-ttu-id="76b20-110">È possibile modificare l'impostazione della proprietà **RaiseChangedEvent** .</span><span class="sxs-lookup"><span data-stu-id="76b20-110">You can modify the **RaiseChangedEvent** property setting.</span></span>  
  
 <span data-ttu-id="76b20-111">L'elenco è codificato tramite colori:</span><span class="sxs-lookup"><span data-stu-id="76b20-111">This list is color coded.</span></span> <span data-ttu-id="76b20-112">Le variabili di sistema vengono visualizzate in grigio, mentre quelle definite dall'utente in nero.</span><span class="sxs-lookup"><span data-stu-id="76b20-112">System variables are gray, and user-defined variables are black.</span></span>  
  
 <span data-ttu-id="76b20-113">**Mostra variabili di tutti gli ambiti**</span><span class="sxs-lookup"><span data-stu-id="76b20-113">**Show variables of all scopes**</span></span>  
 <span data-ttu-id="76b20-114">Selezionare questa opzione per visualizzare le variabili nell'ambito del pacchetto e nell'ambito di contenitori, attività e gestori eventi del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="76b20-114">Select to show variables within the scope the package, and within the scope of containers, tasks, and event handlers in the package.</span></span> <span data-ttu-id="76b20-115">Deselezionarla per visualizzare le variabili solo nell'ambito del pacchetto e nell'ambito di un contenitore, un'attività o un gestore eventi selezionato.</span><span class="sxs-lookup"><span data-stu-id="76b20-115">Clear this option to show only variables within the scope of the package and within the scope of a selected container, task, or event handler.</span></span>  
  
 <span data-ttu-id="76b20-116">Per altre informazioni sull'ambito delle variabili, vedere [Variabili di Integration Services &#40;SSIS&#41;](integration-services-ssis-variables.md).</span><span class="sxs-lookup"><span data-stu-id="76b20-116">For more information about variable scope, see [Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md).</span></span>  
  
## <a name="options-for-columns"></a><span data-ttu-id="76b20-117">Opzioni per le colonne</span><span class="sxs-lookup"><span data-stu-id="76b20-117">Options for Columns</span></span>  
 <span data-ttu-id="76b20-118">Selezionare le colonne che si desidera visualizzare nella finestra **Variabili** .</span><span class="sxs-lookup"><span data-stu-id="76b20-118">Select the columns that you want to appear in the **Variables** window.</span></span>  
  
-   <span data-ttu-id="76b20-119">**Ambito**</span><span class="sxs-lookup"><span data-stu-id="76b20-119">**Scope**</span></span>  
  
-   <span data-ttu-id="76b20-120">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="76b20-120">**Data type**</span></span>  
  
-   <span data-ttu-id="76b20-121">**Valore**</span><span class="sxs-lookup"><span data-stu-id="76b20-121">**Value**</span></span>  
  
-   <span data-ttu-id="76b20-122">**Spazio dei nomi**</span><span class="sxs-lookup"><span data-stu-id="76b20-122">**Namespace**</span></span>  
  
-   <span data-ttu-id="76b20-123">**Genera evento alla modifica del valore della variabile**</span><span class="sxs-lookup"><span data-stu-id="76b20-123">**Raise event when variable value changes**</span></span>  
  
-   <span data-ttu-id="76b20-124">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="76b20-124">**Description**</span></span>  
  
-   <span data-ttu-id="76b20-125">**Espressione**</span><span class="sxs-lookup"><span data-stu-id="76b20-125">**Expression**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76b20-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="76b20-126">See Also</span></span>  
 <span data-ttu-id="76b20-127">[Finestra variabili](../../2014/integration-services/variables-window.md) </span><span class="sxs-lookup"><span data-stu-id="76b20-127">[Variables Window](../../2014/integration-services/variables-window.md) </span></span>  
 <span data-ttu-id="76b20-128">[Variabili di Integration Services &#40;SSIS&#41;](integration-services-ssis-variables.md) </span><span class="sxs-lookup"><span data-stu-id="76b20-128">[Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md) </span></span>  
 <span data-ttu-id="76b20-129">[Usare variabili nei pacchetti](../../2014/integration-services/use-variables-in-packages.md) </span><span class="sxs-lookup"><span data-stu-id="76b20-129">[Use Variables in Packages](../../2014/integration-services/use-variables-in-packages.md) </span></span>  
 [<span data-ttu-id="76b20-130">Gestori eventi di Integration Services &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="76b20-130">Integration Services &#40;SSIS&#41; Event Handlers</span></span>](integration-services-ssis-event-handlers.md)  
  
  
