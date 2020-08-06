---
title: Imposta punti di interruzione | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.setbreakpoints.f1
helpviewer_keywords:
- Set Breakpoints dialog box
ms.assetid: 876e61b7-875c-43f4-bbce-d7eeb90f6730
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 8115fcd845ee5ff415d13aa4fe36230234e33ca0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722639"
---
# <a name="set-breakpoints"></a><span data-ttu-id="893ec-102">Imposta punti di interruzione</span><span class="sxs-lookup"><span data-stu-id="893ec-102">Set Breakpoints</span></span>
  <span data-ttu-id="893ec-103">Utilizzare la finestra di dialogo **Imposta punti di interruzione** per specificare gli eventi su cui abilitare i punti di interruzione e per controllarne il funzionamento.</span><span class="sxs-lookup"><span data-stu-id="893ec-103">Use the **Set Breakpoints** dialog box to specify the events on which to enable breakpoints and to control the behavior of the breakpoint.</span></span>  
  
## <a name="options"></a><span data-ttu-id="893ec-104">Opzioni</span><span class="sxs-lookup"><span data-stu-id="893ec-104">Options</span></span>  
 <span data-ttu-id="893ec-105">**Enabled**</span><span class="sxs-lookup"><span data-stu-id="893ec-105">**Enabled**</span></span>  
 <span data-ttu-id="893ec-106">Consente di abilitare un punto di interruzione su un evento.</span><span class="sxs-lookup"><span data-stu-id="893ec-106">Select to enable a breakpoint on an event.</span></span>  
  
 <span data-ttu-id="893ec-107">**Break Condition**</span><span class="sxs-lookup"><span data-stu-id="893ec-107">**Break Condition**</span></span>  
 <span data-ttu-id="893ec-108">Consente di visualizzare un elenco di eventi disponibili sui quali è possibile impostare i punti di interruzione.</span><span class="sxs-lookup"><span data-stu-id="893ec-108">View a list of available events on which to set breakpoints.</span></span>  
  
 <span data-ttu-id="893ec-109">**Hit Count Type**</span><span class="sxs-lookup"><span data-stu-id="893ec-109">**Hit Count Type**</span></span>  
 <span data-ttu-id="893ec-110">Consente di specificare quando il punto di interruzione diventa effettivo.</span><span class="sxs-lookup"><span data-stu-id="893ec-110">Specify when the breakpoint takes effect.</span></span>  
  
|<span data-ttu-id="893ec-111">valore</span><span class="sxs-lookup"><span data-stu-id="893ec-111">Value</span></span>|<span data-ttu-id="893ec-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="893ec-112">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="893ec-113">**Sempre**</span><span class="sxs-lookup"><span data-stu-id="893ec-113">**Always**</span></span>|<span data-ttu-id="893ec-114">L'esecuzione viene sempre sospesa al rilevamento di un punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="893ec-114">Execution is always suspended when the breakpoint is hit.</span></span>|  
|<span data-ttu-id="893ec-115">**Numero di passaggi uguale a**</span><span class="sxs-lookup"><span data-stu-id="893ec-115">**Hit count equals**</span></span>|<span data-ttu-id="893ec-116">L'esecuzione viene sospesa quando il punto di interruzione viene rilevato per un numero di volte uguale al numero di passaggi specificato.</span><span class="sxs-lookup"><span data-stu-id="893ec-116">Execution is suspended when the number of times the breakpoint has occurred is equal to the hit count.</span></span>|  
|<span data-ttu-id="893ec-117">**Numero di passaggi maggiore o uguale a**</span><span class="sxs-lookup"><span data-stu-id="893ec-117">**Hit greater or equal**</span></span>|<span data-ttu-id="893ec-118">L'esecuzione viene sospesa quando il punto di interruzione viene rilevato per un numero di volte maggiore o uguale al numero di passaggi specificato.</span><span class="sxs-lookup"><span data-stu-id="893ec-118">Execution is suspended when the number of times the breakpoint has occurred is equal to or greater than the hit count.</span></span>|  
|<span data-ttu-id="893ec-119">**Numero di passaggi multiplo di**</span><span class="sxs-lookup"><span data-stu-id="893ec-119">**Hit count multiple**</span></span>|<span data-ttu-id="893ec-120">L'esecuzione viene sospesa quando il punto di interruzione viene rilevato per un numero di volte multiplo del numero di passaggi specificato.</span><span class="sxs-lookup"><span data-stu-id="893ec-120">Execution is suspended when a multiple of the hit count occurs.</span></span> <span data-ttu-id="893ec-121">Se ad esempio questa opzione è impostata su 5, l'esecuzione verrà sospesa ogni cinque volte.</span><span class="sxs-lookup"><span data-stu-id="893ec-121">For example, if you set this option to 5, execution is suspended every fifth time.</span></span>|  
  
 <span data-ttu-id="893ec-122">**Passaggi**</span><span class="sxs-lookup"><span data-stu-id="893ec-122">**Hit Count**</span></span>  
 <span data-ttu-id="893ec-123">Consente di specificare il numero di passaggi al raggiungimento del quale attivare un'interruzione.</span><span class="sxs-lookup"><span data-stu-id="893ec-123">Specify the number of hits at which to trigger a break.</span></span> <span data-ttu-id="893ec-124">Questa opzione non è disponibile se il punto di interruzione è sempre attivo.</span><span class="sxs-lookup"><span data-stu-id="893ec-124">This option is not available if the breakpoint is always in effect.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="893ec-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="893ec-125">See Also</span></span>  
 [<span data-ttu-id="893ec-126">Debug del flusso di controllo</span><span class="sxs-lookup"><span data-stu-id="893ec-126">Debugging Control Flow</span></span>](../../../integration-services/troubleshooting/debugging-control-flow.md)  
  
  
