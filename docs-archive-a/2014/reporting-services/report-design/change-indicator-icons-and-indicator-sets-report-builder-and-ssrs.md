---
title: Modificare le icone degli indicatori e dei set di indicatori (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 8a056adf-4473-473d-9b0c-314675af7bfd
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 398d21319ab6da22f2b10c3607baf8f110d6e65b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722527"
---
# <a name="change-indicator-icons-and-indicator-sets-report-builder-and-ssrs"></a><span data-ttu-id="0b8e8-102">Modificare le icone degli indicatori e dei set di indicatori (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="0b8e8-102">Change Indicator Icons and Indicator Sets (Report Builder and SSRS)</span></span>
  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]<span data-ttu-id="0b8e8-103">In  vengono forniti set di indicatori preconfigurati che potrebbero non raffigurare sempre i dati in maniera efficace né funzionare bene nel report recapitato.</span><span class="sxs-lookup"><span data-stu-id="0b8e8-103">provides preconfigured indicators sets, which might not always depict your data effectively and work well in the delivered report.</span></span> <span data-ttu-id="0b8e8-104">In questo argomento vengono illustrate le procedure per modificare l'aspetto delle icone degli indicatori e i set di indicatori in modo da includere differenti icone degli indicatori o per aumentarne o ridurne il numero.</span><span class="sxs-lookup"><span data-stu-id="0b8e8-104">This topic provides procedures to change the appearance of indicator icons and change the indicator sets to include different, more, or fewer indicator icons.</span></span>  
  
 <span data-ttu-id="0b8e8-105">Opzioni come i colori possono essere impostate tramite espressioni.</span><span class="sxs-lookup"><span data-stu-id="0b8e8-105">Options such as colors can be set by using expressions.</span></span> <span data-ttu-id="0b8e8-106">Per altre informazioni, vedere [Espressioni &#40;Generatore report e SSRS&#41;](expressions-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="0b8e8-106">For more information, see [Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-change-the-color-of-an-indicator-icon"></a><span data-ttu-id="0b8e8-107">Per modificare il colore di un'icona dell'indicatore</span><span class="sxs-lookup"><span data-stu-id="0b8e8-107">To change the color of an indicator icon</span></span>  
  
1.  <span data-ttu-id="0b8e8-108">Fare clic con il pulsante destro del mouse sull'indicatore da modificare e scegliere **Proprietà indicatore**.</span><span class="sxs-lookup"><span data-stu-id="0b8e8-108">Right-click the indicator you want to change and click **Indicator Properties**.</span></span>  
  
2.  <span data-ttu-id="0b8e8-109">Scegliere **Valori e stati** dal riquadro sinistro.</span><span class="sxs-lookup"><span data-stu-id="0b8e8-109">Click **Values and States** in the left pane.</span></span>  
  
3.  <span data-ttu-id="0b8e8-110">Fare clic sulla freccia in giù nella colonna **Colore** accanto all'icona che si desidera modificare e scegliere il colore da usare, **Nessun colore**o **Altri colori**.</span><span class="sxs-lookup"><span data-stu-id="0b8e8-110">Click the down arrow in the **Color** column next to the icon that you want to change and click the color to use, **No Color**, or **More colors**.</span></span>  
  
     <span data-ttu-id="0b8e8-111">Se lo si desidera, fare clic sul pulsante **Espressione** (*fx*) per modificare un'espressione che imposta il valore dell'opzione **Colore** .</span><span class="sxs-lookup"><span data-stu-id="0b8e8-111">Optionally, click the **Expression** (*fx*) button to edit an expression that sets the value of the **Color** option.</span></span>  
  
     <span data-ttu-id="0b8e8-112">Se è stato selezionato **Altri colori**, viene visualizzata la finestra di dialogo **Seleziona colore** in cui è possibile scegliere da un'ampia matrice di colori.</span><span class="sxs-lookup"><span data-stu-id="0b8e8-112">If you clicked **More Colors**, the **Select Color** dialog box opens, where you can choose from a wide array of colors.</span></span> <span data-ttu-id="0b8e8-113">Per altre informazioni sulle opzioni, vedere [Finestra di dialogo Seleziona colore &#40;Generatore report e SSRS&#41;](../select-color-dialog-box-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="0b8e8-113">For more information about its options, see [Select Color Dialog Box &#40;Report Builder and SSRS&#41;](../select-color-dialog-box-report-builder-and-ssrs.md).</span></span> <span data-ttu-id="0b8e8-114">Fare clic su **OK** per chiudere la finestra di dialogo **Seleziona colore** .</span><span class="sxs-lookup"><span data-stu-id="0b8e8-114">Click **OK** to close the **Select Color** dialog box.</span></span>  
  
4.  <span data-ttu-id="0b8e8-115">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="0b8e8-115">Click **OK**.</span></span>  
  
### <a name="to-change-the-icon"></a><span data-ttu-id="0b8e8-116">Per modificare l'icona</span><span class="sxs-lookup"><span data-stu-id="0b8e8-116">To change the icon</span></span>  
  
1.  <span data-ttu-id="0b8e8-117">Fare clic con il pulsante destro del mouse sull'indicatore da modificare e scegliere **Proprietà indicatore**.</span><span class="sxs-lookup"><span data-stu-id="0b8e8-117">Right-click the indicator you want to change and click **Indicator Properties**.</span></span>  
  
2.  <span data-ttu-id="0b8e8-118">Scegliere **Valori e stati** dal riquadro sinistro.</span><span class="sxs-lookup"><span data-stu-id="0b8e8-118">Click **Values and States** in the left pane.</span></span>  
  
3.  <span data-ttu-id="0b8e8-119">Fare clic sulla freccia in giù accanto all'icona che si desidera cambiare e selezionarne una diversa.</span><span class="sxs-lookup"><span data-stu-id="0b8e8-119">Click the down arrow next to the icon that you want to change and select a different icon.</span></span>  
  
     <span data-ttu-id="0b8e8-120">Se lo si desidera, fare clic sul pulsante **Espressione** (*fx*) per modificare un'espressione che consente di impostare il valore dell'opzione **Icona** .</span><span class="sxs-lookup"><span data-stu-id="0b8e8-120">Optionally, click the **Expression** (*fx*) button to edit an expression that sets the value of the **Icon** option.</span></span>  
  
4.  <span data-ttu-id="0b8e8-121">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="0b8e8-121">Click **OK**.</span></span>  
  
### <a name="to-use-a-custom-image-as-an-indicator-icon"></a><span data-ttu-id="0b8e8-122">Per utilizzare un'immagine personalizzata come icona dell'indicatore</span><span class="sxs-lookup"><span data-stu-id="0b8e8-122">To use a custom image as an indicator icon</span></span>  
  
1.  <span data-ttu-id="0b8e8-123">Fare clic con il pulsante destro del mouse sull'indicatore da modificare e scegliere **Proprietà indicatore**.</span><span class="sxs-lookup"><span data-stu-id="0b8e8-123">Right-click the indicator you want to change and click **Indicator Properties**.</span></span>  
  
2.  <span data-ttu-id="0b8e8-124">Scegliere **Valori e stati** dal riquadro sinistro.</span><span class="sxs-lookup"><span data-stu-id="0b8e8-124">Click **Values and States** in the left pane.</span></span>  
  
3.  <span data-ttu-id="0b8e8-125">Fare clic sulla freccia in giù accanto all'icona che si desidera cambiare e selezionare **Immagine**.</span><span class="sxs-lookup"><span data-stu-id="0b8e8-125">Click the down arrow next to the icon that you wan to change and select **Image**.</span></span>  
  
4.  <span data-ttu-id="0b8e8-126">Nell'elenco **Selezionare l'origine dell'immagine** scegliere **Esterno**, **Incorporato**o **Database**.</span><span class="sxs-lookup"><span data-stu-id="0b8e8-126">In the **Select the image source** list, click **External**, **Embedded**, or **Database**.</span></span>  
  
5.  <span data-ttu-id="0b8e8-127">In base all'origine dell'immagine, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0b8e8-127">Depending on the source of the image, do the one of the following:</span></span>  
  
    -   <span data-ttu-id="0b8e8-128">Per usare un'immagine archiviata all'esterno del report, fare clic su **Sfoglia** e individuare l'immagine.</span><span class="sxs-lookup"><span data-stu-id="0b8e8-128">To use an image that is stored externally to the report, click **Browse** and locate the image.</span></span> <span data-ttu-id="0b8e8-129">Nel report verrà incluso un riferimento all'immagine.</span><span class="sxs-lookup"><span data-stu-id="0b8e8-129">The report will include a reference to the image.</span></span>  
  
    -   <span data-ttu-id="0b8e8-130">Per usare un'immagine incorporata nel report, fare clic su **Importa** e individuare l'immagine.</span><span class="sxs-lookup"><span data-stu-id="0b8e8-130">To use an image that is embedded in the report, click **Import** and locate the image.</span></span> <span data-ttu-id="0b8e8-131">L'immagine sarà aggiunta alla definizione del report e salvata insieme a quest'ultima.</span><span class="sxs-lookup"><span data-stu-id="0b8e8-131">The image will be added to the report definition and saved with it.</span></span>  
  
    -   <span data-ttu-id="0b8e8-132">Per usare un'immagine presente in un database, nell'elenco **Utilizza questo campo** .</span><span class="sxs-lookup"><span data-stu-id="0b8e8-132">To use an image that is in a database, in the **Use this field** list.</span></span> <span data-ttu-id="0b8e8-133">selezionare il campo dall'elenco, quindi nell'elenco **Utilizza questo tipo MIME** selezionare il tipo MIME dell'immagine.</span><span class="sxs-lookup"><span data-stu-id="0b8e8-133">select the field from the list and then in the **Use this MIME type** list, select the MIME type of the image.</span></span>  
  
6.  <span data-ttu-id="0b8e8-134">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="0b8e8-134">Click **OK**.</span></span>  
  
### <a name="to-add-an-icon-to-the-indicator-set"></a><span data-ttu-id="0b8e8-135">Per aggiungere un'icona al set di indicatori</span><span class="sxs-lookup"><span data-stu-id="0b8e8-135">To add an icon to the indicator set</span></span>  
  
1.  <span data-ttu-id="0b8e8-136">Fare clic con il pulsante destro del mouse sull'indicatore da modificare e scegliere **Proprietà indicatore**.</span><span class="sxs-lookup"><span data-stu-id="0b8e8-136">Right-click the indicator you want to change and click **Indicator Properties**.</span></span>  
  
2.  <span data-ttu-id="0b8e8-137">Scegliere **Valori e stati** dal riquadro sinistro.</span><span class="sxs-lookup"><span data-stu-id="0b8e8-137">Click **Values and States** in the left pane.</span></span>  
  
3.  <span data-ttu-id="0b8e8-138">Fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="0b8e8-138">Click **Add**.</span></span> <span data-ttu-id="0b8e8-139">Viene aggiunto un indicatore per cui vengono usati l'icona predefinita e l'opzione **Nessun colore** .</span><span class="sxs-lookup"><span data-stu-id="0b8e8-139">An indicator is added, using the default icon and the **No Color** option.</span></span>  
  
     <span data-ttu-id="0b8e8-140">Configurare l'indicatore in modo da utilizzare l'icona e il colore desiderati.</span><span class="sxs-lookup"><span data-stu-id="0b8e8-140">Configure the indictor to use the icon and color you want.</span></span> <span data-ttu-id="0b8e8-141">Nelle procedure riportate in precedenza in questo argomento vengono illustrati i passaggi che consentono di effettuare queste operazioni.</span><span class="sxs-lookup"><span data-stu-id="0b8e8-141">Procedures earlier in this topic describe the steps to do this.</span></span>  
  
4.  <span data-ttu-id="0b8e8-142">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="0b8e8-142">Click **OK**.</span></span>  
  
### <a name="to-delete-an-icon-to-the-indicator-set"></a><span data-ttu-id="0b8e8-143">Per eliminare un'icona dal set di indicatori</span><span class="sxs-lookup"><span data-stu-id="0b8e8-143">To delete an icon to the indicator set</span></span>  
  
1.  <span data-ttu-id="0b8e8-144">Fare clic con il pulsante destro del mouse sull'indicatore da modificare e scegliere **Proprietà indicatore**.</span><span class="sxs-lookup"><span data-stu-id="0b8e8-144">Right-click the indicator you want to change and click **Indicator Properties**.</span></span>  
  
2.  <span data-ttu-id="0b8e8-145">Scegliere **Valori e stati** dal riquadro sinistro.</span><span class="sxs-lookup"><span data-stu-id="0b8e8-145">Click **Values and States** in the left pane.</span></span>  
  
3.  <span data-ttu-id="0b8e8-146">Selezionare l'icona da eliminare e scegliere **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="0b8e8-146">Select the icon to delete, and click **Delete**.</span></span>  
  
4.  <span data-ttu-id="0b8e8-147">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="0b8e8-147">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b8e8-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0b8e8-148">See Also</span></span>  
 [<span data-ttu-id="0b8e8-149">Indicatori &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="0b8e8-149">Indicators &#40;Report Builder and SSRS&#41;</span></span>](indicators-report-builder-and-ssrs.md)  
  
  
