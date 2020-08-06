---
title: Specificare un'immagine come indicatore di misura su un misuratore (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 9d73b3c3-a068-4868-a2be-0cd261b6e92b
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c694cdb90fb668c43eb7e9971bba967bad8dd9cb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719457"
---
# <a name="specify-an-image-as-a-pointer-on-a-gauge-report-builder-and-ssrs"></a><span data-ttu-id="bcbb8-102">Specificare un'immagine come indicatore di misura su un misuratore (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="bcbb8-102">Specify an Image as a Pointer on a Gauge (Report Builder and SSRS)</span></span>
  <span data-ttu-id="bcbb8-103">Il misuratore include tre stili predefiniti utilizzabili per personalizzare l'aspetto dell'indicatore di misura.</span><span class="sxs-lookup"><span data-stu-id="bcbb8-103">The gauge contains three built-in styles that can be used to customize the appearance of the pointer.</span></span> <span data-ttu-id="bcbb8-104">Per un misuratore radiale, gli stili predefiniti sono Lancetta, Marcatore e Barre,</span><span class="sxs-lookup"><span data-stu-id="bcbb8-104">For a radial gauge, the built in styles are: Needle, Marker and Bar.</span></span> <span data-ttu-id="bcbb8-105">mentre quelli per un misuratore lineare sono Marcatore, Barre e Termometro.</span><span class="sxs-lookup"><span data-stu-id="bcbb8-105">For a linear gauge, the built-in styles are Marker, Bar, and Thermometer.</span></span> <span data-ttu-id="bcbb8-106">Se è necessario un indicatore di misura univoco, l'utente può creare e specificare un'immagine utilizzabile come indicatore di misura con funzionalità complete.</span><span class="sxs-lookup"><span data-stu-id="bcbb8-106">If a unique pointer is required, the user can create and specify an image which can be used as a fully functional pointer.</span></span>  
  
 <span data-ttu-id="bcbb8-107">Quando si specifica un'immagine per l'indicatore di misura, tale immagine deve includere le specifiche seguenti:</span><span class="sxs-lookup"><span data-stu-id="bcbb8-107">When you are specifying an image for the pointer, your image must have the following specifications:</span></span>  
  
-   <span data-ttu-id="bcbb8-108">L'origine dell'indicatore di misura, o centro di rotazione, deve trovarsi nella parte superiore dell'immagine.</span><span class="sxs-lookup"><span data-stu-id="bcbb8-108">The origin of the pointer, or center of rotation, must be at the top of the image.</span></span>  
  
-   <span data-ttu-id="bcbb8-109">L'estremità dell'indicatore di misura deve essere rivolta verso il basso.</span><span class="sxs-lookup"><span data-stu-id="bcbb8-109">The end of the pointer must be pointing down.</span></span>  
  
 <span data-ttu-id="bcbb8-110">Poiché l'indicatore di misura è una forma irregolare, sarà necessario specificare un colore di trasparenza per nascondere le parti non necessarie dell'immagine.</span><span class="sxs-lookup"><span data-stu-id="bcbb8-110">Since the pointer is an irregular shape, you will need to specify a transparency color to hide the unnecessary portions of the image.</span></span> <span data-ttu-id="bcbb8-111">Come colore di trasparenza selezionare un colore generalmente non utilizzato per il misuratore, in quanto i colori specificati non verranno visualizzati.</span><span class="sxs-lookup"><span data-stu-id="bcbb8-111">Consider using a color that would not normally be shown on the gauge as the transparency color, since the colors specified will not appear on the gauge.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../includes/ssrbrddup-md.md)]  
  
### <a name="to-specify-an-image-as-a-pointer-on-the-gauge"></a><span data-ttu-id="bcbb8-112">Per specificare un'immagine come indicatore di misura sul misuratore</span><span class="sxs-lookup"><span data-stu-id="bcbb8-112">To specify an image as a pointer on the gauge</span></span>  
  
1.  <span data-ttu-id="bcbb8-113">In visualizzazione della struttura fare clic sull'indicatore di misura del misuratore.</span><span class="sxs-lookup"><span data-stu-id="bcbb8-113">In Design view, click the pointer of the gauge.</span></span>  
  
2.  <span data-ttu-id="bcbb8-114">Opzionale Se sul misuratore non è presente alcun puntatore, fare clic con il pulsante destro del mouse sul misuratore e scegliere **Aggiungi puntatore**.</span><span class="sxs-lookup"><span data-stu-id="bcbb8-114">(Optional) If no pointer exists on the gauge, right-click on the gauge and select **Add Pointer**.</span></span> <span data-ttu-id="bcbb8-115">Al misuratore verrà aggiunto un indicatore di misura.</span><span class="sxs-lookup"><span data-stu-id="bcbb8-115">A pointer is added to the gauge.</span></span>  
  
3.  <span data-ttu-id="bcbb8-116">Fare clic sulla scheda **Inserisci** sulla barra multifunzione e fare doppio clic sull'icona dell'immagine.</span><span class="sxs-lookup"><span data-stu-id="bcbb8-116">Click the **Insert** tab on the ribbon and double-click the image icon.</span></span> <span data-ttu-id="bcbb8-117">Verrà visualizzata la finestra di dialogo **Proprietà immagine**.</span><span class="sxs-lookup"><span data-stu-id="bcbb8-117">The **Image Properties** dialog box opens.</span></span>  
  
4.  <span data-ttu-id="bcbb8-118">Aggiungere un'immagine al report.</span><span class="sxs-lookup"><span data-stu-id="bcbb8-118">Add an image to your report.</span></span> <span data-ttu-id="bcbb8-119">Per ulteriori informazioni, vedere [incorporare un'immagine in un Report &#40;Generatore report e SSRS&#41;](report-design/embed-an-image-in-a-report-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="bcbb8-119">For more information, see [Embed an Image in a Report &#40;Report Builder and SSRS&#41;](report-design/embed-an-image-in-a-report-report-builder-and-ssrs.md).</span></span>  
  
5.  <span data-ttu-id="bcbb8-120">Aprire il riquadro Proprietà.</span><span class="sxs-lookup"><span data-stu-id="bcbb8-120">Open the Properties pane.</span></span>  
  
6.  <span data-ttu-id="bcbb8-121">Nell'area di progettazione fare clic sull'indicatore di misura.</span><span class="sxs-lookup"><span data-stu-id="bcbb8-121">On the design surface, click on the pointer.</span></span> <span data-ttu-id="bcbb8-122">Nel riquadro Proprietà verranno visualizzate le proprietà dell'indicatore di misura.</span><span class="sxs-lookup"><span data-stu-id="bcbb8-122">The properties for the pointer are displayed in the Properties pane.</span></span>  
  
7.  <span data-ttu-id="bcbb8-123">Espandere il nodo PointerImage.</span><span class="sxs-lookup"><span data-stu-id="bcbb8-123">Expand the PointerImage node.</span></span>  
  
8.  <span data-ttu-id="bcbb8-124">In **origine**selezionare **incorporata** dall'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="bcbb8-124">In **Source**, select **Embedded** from the drop-down list.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="bcbb8-125">Se l'immagine viene archiviata nel database o sul Web, è possibile specificare l'opzione adatta per questa proprietà.</span><span class="sxs-lookup"><span data-stu-id="bcbb8-125">If your image is stored in the database or on the web, you can specify the appropriate option for this property.</span></span> <span data-ttu-id="bcbb8-126">Per ulteriori informazioni, vedere finestra di [dialogo Proprietà immagine, generale &#40;Generatore report e SSRS&#41;](../../2014/reporting-services/image-properties-dialog-box-general-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="bcbb8-126">For more information, see [Image Properties Dialog Box, General &#40;Report Builder and SSRS&#41;](../../2014/reporting-services/image-properties-dialog-box-general-report-builder-and-ssrs.md).</span></span>  
  
9. <span data-ttu-id="bcbb8-127">In **valore**selezionare il nome dell'immagine dall'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="bcbb8-127">In **Value**, select the name of your image from the drop-down list.</span></span>  
  
10. <span data-ttu-id="bcbb8-128">In **TransparentColor**selezionare un valore di colore che si desidera rimuovere dall'immagine.</span><span class="sxs-lookup"><span data-stu-id="bcbb8-128">In **TransparentColor**, pick a color value that you want to remove from the image.</span></span> <span data-ttu-id="bcbb8-129">In questo modo, l'aspetto dell'indicatore di misura nel misuratore risulterà migliore.</span><span class="sxs-lookup"><span data-stu-id="bcbb8-129">This will create a seamless appearance for the pointer in the gauge.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bcbb8-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bcbb8-130">See Also</span></span>  
 <span data-ttu-id="bcbb8-131">[Formattazione di puntatori su un misuratore &#40;Generatore report e SSRS&#41;](report-design/formatting-pointers-on-a-gauge-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="bcbb8-131">[Formatting Pointers on a Gauge &#40;Report Builder and SSRS&#41;](report-design/formatting-pointers-on-a-gauge-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="bcbb8-132">[Aggiungere un misuratore a un report &#40;Generatore report e SSRS&#41;](report-design/add-a-gauge-to-a-report-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="bcbb8-132">[Add a Gauge to a Report &#40;Report Builder and SSRS&#41;](report-design/add-a-gauge-to-a-report-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="bcbb8-133">[Formattazione di linee, colori e immagini &#40;Generatore report e SSRS&#41;](report-design/images-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="bcbb8-133">[Formatting Lines, Colors, and Images &#40;Report Builder and SSRS&#41;](report-design/images-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="bcbb8-134">Misuratori &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="bcbb8-134">Gauges &#40;Report Builder and SSRS&#41;</span></span>](report-design/gauges-report-builder-and-ssrs.md)  
  
  
