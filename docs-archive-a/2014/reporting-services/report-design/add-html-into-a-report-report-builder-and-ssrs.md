---
title: Aggiungere il codice HTML a un report (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 30bd631a-f774-48e7-a13a-b6c2eb54d9bb
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 605c84843d62fb664a8a665a3fc3b024f8f87186
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722535"
---
# <a name="add-html-into-a-report-report-builder-and-ssrs"></a><span data-ttu-id="2d325-102">Aggiungere il codice HTML a un report (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="2d325-102">Add HTML into a Report (Report Builder and SSRS)</span></span>
  <span data-ttu-id="2d325-103">Utilizzando un segnaposto, è possibile importare codice HTML da un campo nel set di dati per utilizzarlo nel report.</span><span class="sxs-lookup"><span data-stu-id="2d325-103">Using a placeholder, you can import HTML from a field in your dataset for use in the report.</span></span> <span data-ttu-id="2d325-104">Per impostazione predefinita, un segnaposto rappresenta un testo normale e pertanto è necessario modificarne il tipo di markup in codice HTML.</span><span class="sxs-lookup"><span data-stu-id="2d325-104">By default, a placeholder represents plain text, so you will need to change the placeholder mark-up type to HTML.</span></span> <span data-ttu-id="2d325-105">Per altre informazioni, vedere [Importazione di codice HTML in un report &#40;Generatore report e SSRS&#41;](importing-html-into-a-report-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="2d325-105">For more information, see [Importing HTML into a Report &#40;Report Builder and SSRS&#41;](importing-html-into-a-report-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-html-from-a-field-in-your-dataset-into-a-text-box"></a><span data-ttu-id="2d325-106">Per aggiungere codice HTML da un campo del set di dati in una casella di testo</span><span class="sxs-lookup"><span data-stu-id="2d325-106">To add HTML from a field in your dataset into a text box</span></span>  
  
1.  <span data-ttu-id="2d325-107">Fare clic su **Elenco** nella scheda **Inserisci**.</span><span class="sxs-lookup"><span data-stu-id="2d325-107">On the **Insert** tab, click **List**.</span></span> <span data-ttu-id="2d325-108">Fare clic nell'area di progettazione, quindi trascinare il mouse per creare una casella delle dimensioni desiderate.</span><span class="sxs-lookup"><span data-stu-id="2d325-108">Click the design surface, and then drag to create a box that is the size you want.</span></span>  
  
     <span data-ttu-id="2d325-109">Verrà visualizzata la finestra di dialogo **Proprietà set di dati** .</span><span class="sxs-lookup"><span data-stu-id="2d325-109">The **Dataset Properties** dialog box opens.</span></span> <span data-ttu-id="2d325-110">È possibile utilizzare un set di dati condiviso o un set di dati incorporato nel report.</span><span class="sxs-lookup"><span data-stu-id="2d325-110">You can use a shared dataset or a dataset embedded in your report.</span></span> <span data-ttu-id="2d325-111">Per altre informazioni, fare clic su [Finestra di dialogo Proprietà set di dati, Query &#40;Generatore report&#41;](../report-data/dataset-properties-dialog-box-query-report-builder.md) o [Finestra di dialogo Proprietà set di dati, Query](../dataset-properties-dialog-box-query.md).</span><span class="sxs-lookup"><span data-stu-id="2d325-111">For more information, click [Dataset Properties Dialog Box, Query &#40;Report Builder&#41;](../report-data/dataset-properties-dialog-box-query-report-builder.md) or [Dataset Properties Dialog Box, Query](../dataset-properties-dialog-box-query.md).</span></span>  
  
2.  <span data-ttu-id="2d325-112">Fare clic su **Casella testo** nella scheda **Inserisci**.</span><span class="sxs-lookup"><span data-stu-id="2d325-112">On the **Insert** tab, click **Text Box**.</span></span> <span data-ttu-id="2d325-113">Fare clic nell'elenco, quindi trascinare il mouse per creare una casella con le dimensioni desiderate.</span><span class="sxs-lookup"><span data-stu-id="2d325-113">Click in the list, and then drag to create a box that is the size you want.</span></span>  
  
3.  <span data-ttu-id="2d325-114">Trascinare un campo HTML dal set di dati nella casella di testo.</span><span class="sxs-lookup"><span data-stu-id="2d325-114">Drag an HTML field from your dataset into the text box.</span></span> <span data-ttu-id="2d325-115">Verrà creato un segnaposto per il campo.</span><span class="sxs-lookup"><span data-stu-id="2d325-115">A placeholder is created for your field.</span></span>  
  
4.  <span data-ttu-id="2d325-116">Fare clic con il pulsante destro del mouse sul segnaposto, quindi scegliere **Proprietà segnaposto**.</span><span class="sxs-lookup"><span data-stu-id="2d325-116">Right-click the placeholder, and then click **Placeholder Properties**.</span></span>  
  
5.  <span data-ttu-id="2d325-117">Nella scheda **Generale** verificare che la casella **Valore** contenga un'espressione che restituisce il campo rilasciato nel passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="2d325-117">On the **General** tab, verify that the **Value** box contains an expression that evaluates to the field you dropped in step 3.</span></span>  
  
6.  <span data-ttu-id="2d325-118">Fare clic su **HTML - Interpreta tag HTML come stili**.</span><span class="sxs-lookup"><span data-stu-id="2d325-118">Click **HTML - Interpret HTML tags as styles**.</span></span> <span data-ttu-id="2d325-119">In questo modo il campo verrà valutato come HTML.</span><span class="sxs-lookup"><span data-stu-id="2d325-119">This causes the field to be evaluated as HTML.</span></span>  
  
7.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="2d325-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2d325-120">See Also</span></span>  
 <span data-ttu-id="2d325-121">[Formattazione di numeri e date &#40;Generatore report e SSRS&#41;](formatting-numbers-and-dates-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="2d325-121">[Formatting Numbers and Dates &#40;Report Builder and SSRS&#41;](formatting-numbers-and-dates-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="2d325-122">[Formattazione di linee, colori e immagini &#40;Generatore report e SSRS&#41;](images-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="2d325-122">[Formatting Lines, Colors, and Images &#40;Report Builder and SSRS&#41;](images-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="2d325-123">Finestra di dialogo Proprietà segnaposto, Generale &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="2d325-123">Placeholder Properties Dialog Box, General &#40;Report Builder and SSRS&#41;</span></span>](../placeholder-properties-dialog-box-general-report-builder-and-ssrs.md)  
  
  
