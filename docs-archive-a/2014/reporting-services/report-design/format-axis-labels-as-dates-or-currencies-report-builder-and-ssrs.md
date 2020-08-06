---
title: Formattazione delle etichette degli assi come date o valute (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: e9a01a74-2f51-4b35-be3a-a6138568f6cf
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: ffe9d903a2271db95d4b1c2ef6201d2b0f3edab3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627092"
---
# <a name="format-axis-labels-as-dates-or-currencies-report-builder-and-ssrs"></a><span data-ttu-id="d0cf7-102">Formattazione delle etichette degli assi come date o valute (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="d0cf7-102">Format Axis Labels as Dates or Currencies (Report Builder and SSRS)</span></span>
  <span data-ttu-id="d0cf7-103">Quando i valori DateTime sono formattati correttamente su un asse, vengono visualizzati automaticamente in un grafico come giorni.</span><span class="sxs-lookup"><span data-stu-id="d0cf7-103">When you show properly formatted DateTime values on an axis, a chart will automatically display these values as days.</span></span> <span data-ttu-id="d0cf7-104">Per specificare un intervallo di data o ora per l'asse X, ad esempio un intervallo di mesi o di ore, è necessario formattare le etichette dell'asse e impostare il tipo di intervallo dell'asse su un intervallo di data o ora valido.</span><span class="sxs-lookup"><span data-stu-id="d0cf7-104">To specify a date/time interval for the x-axis, such as an interval of months or an interval of hours, you must format the axis labels and set the type of axis interval to a valid date or time interval.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d0cf7-105">Nei grafici a dispersione e negli istogrammi, l'asse orizzontale, o asse x, è l'asse delle categorie.</span><span class="sxs-lookup"><span data-stu-id="d0cf7-105">In column and scatter charts, the horizontal, or x-axis, is the category axis.</span></span> <span data-ttu-id="d0cf7-106">Nei grafici a barre l'asse delle categorie è l'asse verticale, ovvero l'asse y.</span><span class="sxs-lookup"><span data-stu-id="d0cf7-106">In bar charts, the vertical, or y-axis, is the category axis.</span></span>  
  
 <span data-ttu-id="d0cf7-107">Per formattare correttamente gli intervalli di tempo, i valori visualizzati sull'asse X devono restituire un tipo di dati <xref:System.DateTime> .</span><span class="sxs-lookup"><span data-stu-id="d0cf7-107">In order to format time intervals correctly, the values displayed on the x-axis must evaluate to a <xref:System.DateTime> data type.</span></span> <span data-ttu-id="d0cf7-108">Se il campo dispone di un tipo di dati <xref:System.String>, il grafico non calcolerà gli intervalli come date o ore.</span><span class="sxs-lookup"><span data-stu-id="d0cf7-108">If your field has a data type of <xref:System.String>, the chart will not calculate intervals as dates or times.</span></span> <span data-ttu-id="d0cf7-109">Per altre informazioni, vedere [Grafici &#40;Generatore report e SSRS&#41;](charts-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="d0cf7-109">For more information, see [Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="d0cf7-110">Quando un valore numerico viene aggiunto all'asse Y, per impostazione predefinita il grafico non formatta il numero prima di visualizzarlo.</span><span class="sxs-lookup"><span data-stu-id="d0cf7-110">When a numeric value is added to the y-axis, by default, the chart does not format the number before displaying it.</span></span> <span data-ttu-id="d0cf7-111">Se il campo numerico è una cifra relativa alle vendite, è possibile formattare i numeri come valute per migliorare la leggibilità del grafico.</span><span class="sxs-lookup"><span data-stu-id="d0cf7-111">If your numeric field is a sales figure, consider formatting the numbers as currencies to increase the readability of the chart.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-format-x-axis-labels-as-monthly-intervals"></a><span data-ttu-id="d0cf7-112">Per formattare le etichette dell'asse X come intervalli mensili</span><span class="sxs-lookup"><span data-stu-id="d0cf7-112">To format x-axis labels as monthly intervals</span></span>  
  
1.  <span data-ttu-id="d0cf7-113">Fare clic con il pulsante destro del mouse sull'asse orizzontale o asse X, del grafico e scegliere **Proprietà asse orizzontale**.</span><span class="sxs-lookup"><span data-stu-id="d0cf7-113">Right-click the horizontal, or x-axis, of the chart, and select **HorizontalAxis Properties**.</span></span>  
  
2.  <span data-ttu-id="d0cf7-114">Nella finestra di dialogo **Proprietà asse orizzontale** selezionare l'opzione **Numero**.</span><span class="sxs-lookup"><span data-stu-id="d0cf7-114">In the **HorizontalAxis Properties** dialog box, select **Number**.</span></span>  
  
3.  <span data-ttu-id="d0cf7-115">Nell'elenco **Categoria** selezionare **Data**.</span><span class="sxs-lookup"><span data-stu-id="d0cf7-115">From the **Category** list, select **Date**.</span></span> <span data-ttu-id="d0cf7-116">Nell'elenco **Tipo** selezionare un formato di data da applicare alle etichette dell'asse X.</span><span class="sxs-lookup"><span data-stu-id="d0cf7-116">From the **Type** list, select a date format to apply to the x-axis labels.</span></span>  
  
4.  <span data-ttu-id="d0cf7-117">Selezionare **Opzioni asse**.</span><span class="sxs-lookup"><span data-stu-id="d0cf7-117">Select **Axis Options.**</span></span>  
  
5.  <span data-ttu-id="d0cf7-118">In **Intervallo**digitare **1**.</span><span class="sxs-lookup"><span data-stu-id="d0cf7-118">In **Interval**, type **1**.</span></span> <span data-ttu-id="d0cf7-119">Nella proprietà **Tipo intervallo** selezionare **Mesi**.</span><span class="sxs-lookup"><span data-stu-id="d0cf7-119">In **Interval type** property, select **Months**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d0cf7-120">Se non si specifica un tipo di intervallo, il grafico calcolerà gli intervalli in termini di giorni.</span><span class="sxs-lookup"><span data-stu-id="d0cf7-120">If you do not specify an interval type, the chart will calculate intervals in terms of days.</span></span>  
  
6.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-format-y-axis-labels-using-a-currency-format"></a><span data-ttu-id="d0cf7-121">Per formattare le etichette dell'asse Y utilizzando un formato di valuta</span><span class="sxs-lookup"><span data-stu-id="d0cf7-121">To format y-axis labels using a currency format</span></span>  
  
1.  <span data-ttu-id="d0cf7-122">Fare clic con il pulsante destro del mouse sull'asse verticale o asse Y, del grafico e scegliere **Proprietà asse verticale**.</span><span class="sxs-lookup"><span data-stu-id="d0cf7-122">Right-click the vertical, or y-axis, of the chart, and select **VerticalAxis Properties**.</span></span>  
  
2.  <span data-ttu-id="d0cf7-123">Nella finestra di dialogo **Proprietà asse verticale** selezionare l'opzione **Numero**.</span><span class="sxs-lookup"><span data-stu-id="d0cf7-123">In the **VerticalAxis Properties** dialog box, select **Number**.</span></span>  
  
3.  <span data-ttu-id="d0cf7-124">Nell'elenco **Categoria** selezionare **Valuta**.</span><span class="sxs-lookup"><span data-stu-id="d0cf7-124">From the **Category** list, select **Currency**.</span></span> <span data-ttu-id="d0cf7-125">Nell'elenco **Simbolo** selezionare un formato di valuta da applicare alle etichette dell'asse Y.</span><span class="sxs-lookup"><span data-stu-id="d0cf7-125">From the **Symbol** list, select a currency format to apply to the y-axis labels.</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d0cf7-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d0cf7-126">See Also</span></span>  
 <span data-ttu-id="d0cf7-127">[Formattazione delle etichette degli assi in un grafico &#40;Generatore report e SSRS&#41;](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="d0cf7-127">[Formatting Axis Labels on a Chart &#40;Report Builder and SSRS&#41;](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="d0cf7-128">[Formattazione di un grafico &#40;Generatore report e SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="d0cf7-128">[Formatting a Chart &#40;Report Builder and SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="d0cf7-129">[Specificare una scala logaritmica &#40;Generatore report e SSRS&#41;](specify-a-logarithmic-scale-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="d0cf7-129">[Specify a Logarithmic Scale &#40;Report Builder and SSRS&#41;](specify-a-logarithmic-scale-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="d0cf7-130">Specificare un intervallo dell'asse &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="d0cf7-130">Specify an Axis Interval &#40;Report Builder and SSRS&#41;</span></span>](specify-an-axis-interval-report-builder-and-ssrs.md)  
  
  
