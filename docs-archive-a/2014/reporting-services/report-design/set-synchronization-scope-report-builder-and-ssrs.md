---
title: Impostare l'ambito di sincronizzazione (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 6f4a11e6-6151-47be-a43f-e3dbf6c0e737
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 3efbb7774d5116c9b3a18457291434f2a05aac7f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623790"
---
# <a name="set-synchronization-scope-report-builder-and-ssrs"></a><span data-ttu-id="8632f-102">Impostare l'ambito di sincronizzazione (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="8632f-102">Set Synchronization Scope (Report Builder and SSRS)</span></span>
  <span data-ttu-id="8632f-103">Gli indicatori consentono di visualizzare i valori dei dati eseguendo la sincronizzazione nell'intervallo di valori dell'indicatore in un ambito specificato.</span><span class="sxs-lookup"><span data-stu-id="8632f-103">Indicators convey data values by synchronizing across the range of indicator values within a specified scope.</span></span> <span data-ttu-id="8632f-104">Per impostazione predefinita, l'ambito è il contenitore padre dell'indicatore, ad esempio la tabella o la matrice in cui è contenuto l'indicatore.</span><span class="sxs-lookup"><span data-stu-id="8632f-104">By default, the scope is the parent container of the indicator such as the table or matrix that contains the indicator.</span></span> <span data-ttu-id="8632f-105">È possibile modificare la sincronizzazione dell'indicatore a seconda del layout del report.</span><span class="sxs-lookup"><span data-stu-id="8632f-105">You can change the synchronization of the indicator depending on the layout of your report.</span></span> <span data-ttu-id="8632f-106">Se, ad esempio, un'area dati quale una tabella dispone di un gruppo di righe, è possibile specificare il gruppo come ambito dell'indicatore.</span><span class="sxs-lookup"><span data-stu-id="8632f-106">For example, if a data region such as a table has a row group, you can specify the group as the indicator scope.</span></span> <span data-ttu-id="8632f-107">L'indicatore può inoltre omettere la sincronizzazione.</span><span class="sxs-lookup"><span data-stu-id="8632f-107">The indicator can also omit synchronization.</span></span>  
  
 <span data-ttu-id="8632f-108">Opzioni come le unità di misura possono essere impostate tramite espressioni.</span><span class="sxs-lookup"><span data-stu-id="8632f-108">Options such as measurement units can be set by using expressions.</span></span> <span data-ttu-id="8632f-109">Per altre informazioni, vedere [Espressioni &#40;Generatore report e SSRS&#41;](expressions-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="8632f-109">For more information, see [Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="8632f-110">Per informazioni generali sull'impostazione dell'ambito all'interno dei report, vedere [Ambito di espressioni per totali, aggregazioni e raccolte predefinite &#40;Generatore report e SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span><span class="sxs-lookup"><span data-stu-id="8632f-110">For general information about understanding and setting scope within reports, see [Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-change-the-synchronization-scope-of-an-indicator"></a><span data-ttu-id="8632f-111">Per modificare l'ambito di sincronizzazione di un indicatore</span><span class="sxs-lookup"><span data-stu-id="8632f-111">To change the synchronization scope of an indicator</span></span>  
  
1.  <span data-ttu-id="8632f-112">Fare clic con il pulsante destro del mouse sull'indicatore che si desidera modificare e scegliere **Proprietà indicatore**.</span><span class="sxs-lookup"><span data-stu-id="8632f-112">Right click the indicator you want to change and click **Indicator Properties**.</span></span>  
  
2.  <span data-ttu-id="8632f-113">Scegliere **Valori e stati** dal riquadro sinistro.</span><span class="sxs-lookup"><span data-stu-id="8632f-113">Click **Values and States** in the left pane.</span></span>  
  
3.  <span data-ttu-id="8632f-114">Nell'elenco **Ambito sincronizzazione** fare clic sull'ambito da applicare.</span><span class="sxs-lookup"><span data-stu-id="8632f-114">In the **Synchronization scope** list, click the scope that you want to apply.</span></span>  
  
     <span data-ttu-id="8632f-115">L'opzione **(nessuno)** , che consente di rimuovere l'ambito di sincronizzazione dall'indicatore, è sempre disponibile.</span><span class="sxs-lookup"><span data-stu-id="8632f-115">The **(None)** option, which removes synchronization scope from the indicator, is always available.</span></span> <span data-ttu-id="8632f-116">Le altre opzioni dipendono dal layout del report.</span><span class="sxs-lookup"><span data-stu-id="8632f-116">Other options depend on the layout of your report.</span></span>  
  
     <span data-ttu-id="8632f-117">È possibile fare clic sul pulsante **Espressione** (*fx*) per modificare un'espressione che imposta l'ambito.</span><span class="sxs-lookup"><span data-stu-id="8632f-117">Optionally, click the **Expression** (*fx*) button to edit an expression that sets the scope.</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8632f-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8632f-118">See Also</span></span>  
 [<span data-ttu-id="8632f-119">Indicatori &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="8632f-119">Indicators &#40;Report Builder and SSRS&#41;</span></span>](indicators-report-builder-and-ssrs.md)  
  
  
