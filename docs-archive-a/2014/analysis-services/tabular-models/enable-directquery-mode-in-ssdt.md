---
title: Abilitare la modalità di progettazione DirectQuery (SSAS tabulare) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 71fc7ebd-2e86-4a76-994b-66d3a57bcc9b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 8ccd2dc88f447e78f6558565a89accc341eac37c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629623"
---
# <a name="enable-directquery-design-mode-ssas-tabular"></a><span data-ttu-id="c0666-102">Abilitare la modalità DirectQuery (SSAS tabulare)</span><span class="sxs-lookup"><span data-stu-id="c0666-102">Enable DirectQuery Design Mode (SSAS Tabular)</span></span>
  <span data-ttu-id="c0666-103">Per creare un modello in modalità DirectQuery, è innanzitutto necessario modificare l'ambiente di progettazione in modo che supporti l'utente della modalità DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="c0666-103">To create a model in DirectQuery mode, you must first change the design-time environment so that it supports the user of DirectQuery mode.</span></span> <span data-ttu-id="c0666-104">Quando si esegue questa operazione, vengono anche eseguite le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c0666-104">When you do so, the designer will also do the following:</span></span>  
  
-   <span data-ttu-id="c0666-105">Abilitazione dell'utilizzo delle proprietà di distribuzione DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="c0666-105">Enable the use of the DirectQuery deployment properties.</span></span>  
  
-   <span data-ttu-id="c0666-106">Modifica del database dell'area di lavoro affinché venga eseguito in una modalità ibrida che utilizza la cache per la progettazione.</span><span class="sxs-lookup"><span data-stu-id="c0666-106">Change the workspace database to run in a hybrid mode that uses the cache for designing.</span></span> <span data-ttu-id="c0666-107">Quando si distribuisce il modello, la modalità verrà nuovamente impostata sul valore specificato nelle proprietà di distribuzione del progetto.</span><span class="sxs-lookup"><span data-stu-id="c0666-107">When you actually deploy the model, the mode will be changed back to whatever value you specified in the project deployment properties.</span></span>  
  
-   <span data-ttu-id="c0666-108">Disabilitazione delle caratteristiche di progettazione incompatibili con la modalità DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="c0666-108">Disable design features that are incompatible with DirectQuery mode.</span></span>  
  
-   <span data-ttu-id="c0666-109">Convalida del modello esistente.</span><span class="sxs-lookup"><span data-stu-id="c0666-109">Validate the existing model.</span></span>  
  
 <span data-ttu-id="c0666-110">Questa procedura descrive come abilitare la modalità DirectQuery nella finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="c0666-110">This procedure describes how to enable DirectQuery mode in the designer.</span></span>  
  
### <a name="to-enable-use-of-directquery-in-a-model"></a><span data-ttu-id="c0666-111">Per abilitare l'utilizzo di DirectQuery in un modello</span><span class="sxs-lookup"><span data-stu-id="c0666-111">To enable use of DirectQuery in a model</span></span>  
  
1.  <span data-ttu-id="c0666-112">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]aprire il file della soluzione.</span><span class="sxs-lookup"><span data-stu-id="c0666-112">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the solution file.</span></span>  
  
2.  <span data-ttu-id="c0666-113">In Esplora oggetti fare doppio clic sul file Model.bim.</span><span class="sxs-lookup"><span data-stu-id="c0666-113">In Object Explorer, double-click the Model.bim file.</span></span>  
  
3.  <span data-ttu-id="c0666-114">Nel riquadro **Proprietà** impostare la proprietà **DirectQueryMode**su **Attivato**.</span><span class="sxs-lookup"><span data-stu-id="c0666-114">In the **Properties** pane, change the property, **DirectQueryMode**, to **On**.</span></span>  
  
4.  <span data-ttu-id="c0666-115">In caso di errori, in Visual Studio aprire il **Elenco errori** e risolvere eventuali problemi che impediscono il passaggio del modello alla modalità DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="c0666-115">If there are errors, in Visual Studio, open the **Error List** and resolve any problems that would prevent the model from being switched to DirectQuery mode.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0666-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c0666-116">See Also</span></span>  
 [<span data-ttu-id="c0666-117">Modalità DirectQuery &#40;SSAS tabulare&#41;</span><span class="sxs-lookup"><span data-stu-id="c0666-117">DirectQuery Mode &#40;SSAS Tabular&#41;</span></span>](directquery-mode-ssas-tabular.md)  
  
  
