---
title: Impostare l'orientamento della casella di testo (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 64bd53f4-2f31-4732-8c2e-64c7b54b6972
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d509f1df29203fa5def79b61b74ae9db8f40d204
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623786"
---
# <a name="set-text-box-orientation-report-builder-and-ssrs"></a><span data-ttu-id="75004-102">Impostare l'orientamento della casella di testo (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="75004-102">Set Text Box Orientation (Report Builder and SSRS)</span></span>
  <span data-ttu-id="75004-103">Una casella di testo può essere orientata in direzioni diverse: orizzontalmente, verticalmente (testo leggibile dall'alto in basso) o ruotata di 270 gradi (testo leggibile dal basso in alto).</span><span class="sxs-lookup"><span data-stu-id="75004-103">A text box can be oriented in different directions: horizontally, vertically (text reading from top to bottom), or rotated by 270 degrees (text reading from bottom to top).</span></span> <span data-ttu-id="75004-104">Poiché l'orientamento è impostato sulla casella di testo e non sul testo, questa modifica viene applicata a tutto il testo nella casella.</span><span class="sxs-lookup"><span data-stu-id="75004-104">Because orientation is set on the text box not the text, the orientation applies to all the text in the text box.</span></span> <span data-ttu-id="75004-105">Non è possibile specificare orientamenti diversi per parti del testo.</span><span class="sxs-lookup"><span data-stu-id="75004-105">You cannot specify different orientations for parts of the text.</span></span> <span data-ttu-id="75004-106">Per adattare il testo ruotato ridimensionare manualmente la larghezza della colonna e l'altezza della riga.</span><span class="sxs-lookup"><span data-stu-id="75004-106">Size the column width and the row height manually to accommodate the rotated text.</span></span>  
  
 <span data-ttu-id="75004-107">La proprietà WritingMode, utilizzata per specificare l'orientamento del testo, non è disponibile nella finestra di dialogo **Proprietà casella di testo** .</span><span class="sxs-lookup"><span data-stu-id="75004-107">The WritingMode property, which you use to specify text orientation, is not available in the **Text Box Properties** dialog box.</span></span> <span data-ttu-id="75004-108">Per impostarla, è necessario aprire il riquadro Proprietà.</span><span class="sxs-lookup"><span data-stu-id="75004-108">You need to open the Properties pane and set the property there.</span></span> <span data-ttu-id="75004-109">I valori disponibili per la proprietà WritingMode sono **orizzontali** (testo leggibile da sinistra verso destra), **verticale** (testo leggibile dall'alto in basso), **Rotate270** (testo leggibile dal basso verso l'alto).</span><span class="sxs-lookup"><span data-stu-id="75004-109">The available values for the WritingMode property are **Horizontal** (text reading left to right), **Vertical** (text reading top to bottom), **Rotate270** (text reading bottom to top).</span></span> <span data-ttu-id="75004-110">Per adattare il testo è necessario ridimensionare manualmente la larghezza della colonna e l'altezza della riga.</span><span class="sxs-lookup"><span data-stu-id="75004-110">You must manually size the column width and the row height to accommodate the text.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-set-text-orientation"></a><span data-ttu-id="75004-111">Per impostare l'orientamento del testo</span><span class="sxs-lookup"><span data-stu-id="75004-111">To set text orientation</span></span>  
  
1.  <span data-ttu-id="75004-112">Creare un nuovo report o aprirne uno esistente.</span><span class="sxs-lookup"><span data-stu-id="75004-112">Create a new report or open an existing report.</span></span>  
  
2.  <span data-ttu-id="75004-113">Se il riquadro Proprietà non è aperto, fare clic sulla scheda **Visualizza** e selezionare la casella di controllo **Proprietà** .</span><span class="sxs-lookup"><span data-stu-id="75004-113">If the Properties pane is not open, click the **View** tab and select the **Properties** check box.</span></span>  
  
3.  <span data-ttu-id="75004-114">Fare clic sulla casella di testo di cui si desidera modificare l'orientamento del testo.</span><span class="sxs-lookup"><span data-stu-id="75004-114">Click the text box for which you want to change text orientation.</span></span>  
  
4.  <span data-ttu-id="75004-115">Individuare la proprietà WritingMode nel riquadro proprietà e nell'elenco a discesa selezionare l'orientamento del testo da applicare alla casella di testo.</span><span class="sxs-lookup"><span data-stu-id="75004-115">Locate the WritingMode property in the Properties pane and in the drop-down list select the text orientation to apply to the text box.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="75004-116">Se le proprietà nel riquadro Proprietà sono organizzate in categorie, WritingMode si trova nella categoria **Localizzazione** .</span><span class="sxs-lookup"><span data-stu-id="75004-116">When the properties in the Properties pane are organized into categories, WritingMode is in the **Localization** category.</span></span>  
  
5.  <span data-ttu-id="75004-117">Nella casella di riepilogo selezionare **Horizontal**, **Vertical**o **Rotate270**.</span><span class="sxs-lookup"><span data-stu-id="75004-117">In the list box, select **Horizontal**, **Vertical**, or **Rotate270**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75004-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="75004-118">See Also</span></span>  
 <span data-ttu-id="75004-119">[Caselle di testo &#40;Generatore report e SSRS&#41;](text-boxes-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="75004-119">[Text Boxes &#40;Report Builder and SSRS&#41;](text-boxes-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="75004-120">Esercitazione: Formattazione di testo &#40;Generatore report&#41;</span><span class="sxs-lookup"><span data-stu-id="75004-120">Tutorial: Format Text &#40;Report Builder&#41;</span></span>](../tutorial-format-text-report-builder.md)  
  
  
