---
title: Sostituire i parametri del modello | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.swb.templates.replaceparameters.f1
helpviewer_keywords:
- template parameters [Template Explorer]
- templates [Transact-SQL], replacing parameters
- Replace (Query) Template Parameters dialog box
- replacing template parameters
ms.assetid: 1234aa14-3464-4a3e-922a-5cfb8fb23627
author: stevestein
ms.author: sstein
ms.openlocfilehash: 1d87b17a110efe118f7796487448e4d3bae30375
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630221"
---
# <a name="replace-template-parameters"></a><span data-ttu-id="92fa6-102">Sostituisci parametri modello</span><span class="sxs-lookup"><span data-stu-id="92fa6-102">Replace Template Parameters</span></span>
  <span data-ttu-id="92fa6-103">I modelli contengono parametri che possono essere sostituiti da valori specifici dell'implementazione ogni volta che il modello è utilizzato.</span><span class="sxs-lookup"><span data-stu-id="92fa6-103">Templates contain parameters that can be replaced by implementation-specific values each time the template is used.</span></span> <span data-ttu-id="92fa6-104">Dopo avere aperto un modello in un editor di codice, è possibile sostituire i parametri con i valori attinenti all'implementazione.</span><span class="sxs-lookup"><span data-stu-id="92fa6-104">After opening a template in a code editor, you can replace the parameters with values relevant to your implementation.</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="92fa6-105">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="92fa6-105">Before You Begin</span></span>  
 <span data-ttu-id="92fa6-106">La finestra di dialogo **Imposta valori per parametri modello** è una griglia con tre colonne.</span><span class="sxs-lookup"><span data-stu-id="92fa6-106">The **Specify Values for Template Parameters** dialog is a grid with three columns.</span></span> <span data-ttu-id="92fa6-107">Le colonne **Parametro** e **Tipo** sono di sola lettura e non possono essere modificate.</span><span class="sxs-lookup"><span data-stu-id="92fa6-107">The **Parameter** and **Type** columns are read-only and cannot be changed.</span></span> <span data-ttu-id="92fa6-108">Rivedere il contenuto della colonna **Valore** e modificare i valori predefiniti in base all'implementazione.</span><span class="sxs-lookup"><span data-stu-id="92fa6-108">Review the contents of the **Value** column, and change any of the defaults to values appropriate for your implementation.</span></span>  
  
 <span data-ttu-id="92fa6-109">Per usare questa finestra di dialogo, è necessario che i parametri nello script siano racchiusi tra parentesi angolari (`< >`) nel formato `<`*parameter_name*`,` *data_type*`,` *default_value*`>`.</span><span class="sxs-lookup"><span data-stu-id="92fa6-109">To use this dialog box, you must have parameters in your script enclosed in angle brackets (`< >`) in the format `<`*parameter_name*`,` *data_type*`,` *default_value*`>`.</span></span>  
  
## <a name="replace-template-parameters"></a><span data-ttu-id="92fa6-110">Sostituisci parametri modello</span><span class="sxs-lookup"><span data-stu-id="92fa6-110">Replace Template Parameters</span></span>  
 <span data-ttu-id="92fa6-111">Dopo avere aperto il modello in una finestra dell'editor di codice:</span><span class="sxs-lookup"><span data-stu-id="92fa6-111">After opening the template in a code editor window:</span></span>  
  
1.  <span data-ttu-id="92fa6-112">Scegliere **Imposta valori per parametri modello** dal menu **Query**.</span><span class="sxs-lookup"><span data-stu-id="92fa6-112">On the **Query** menu, click **Specify Values for Template Parameters**.</span></span>  
  
2.  <span data-ttu-id="92fa6-113">Nella finestra di dialogo **Imposta valori per parametri modello** la colonna **Valori** contiene un valore suggerito per ogni parametro.</span><span class="sxs-lookup"><span data-stu-id="92fa6-113">In the **Specify Values for Template Parameters** dialog box, the **Values** column contains a suggested value for each parameter.</span></span> <span data-ttu-id="92fa6-114">Accettare il valore o sostituirlo con uno nuovo.</span><span class="sxs-lookup"><span data-stu-id="92fa6-114">Accept the value or replace it with a new value.</span></span>  
  
3.  <span data-ttu-id="92fa6-115">Fare clic su **OK** per chiudere la finestra di dialogo **Replace Template Parameters** (Sostituisci parametri modello) e modificare lo script nell'editor di query.</span><span class="sxs-lookup"><span data-stu-id="92fa6-115">Click **OK** to close the **Replace Template Parameters** dialog box and modify the script in the query editor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92fa6-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="92fa6-116">See Also</span></span>  
 <span data-ttu-id="92fa6-117">[Esplora modelli](template-explorer.md) </span><span class="sxs-lookup"><span data-stu-id="92fa6-117">[Template Explorer](template-explorer.md) </span></span>  
 [<span data-ttu-id="92fa6-118">Aprire un modello</span><span class="sxs-lookup"><span data-stu-id="92fa6-118">Open a Template</span></span>](open-a-template.md)  
  
  
