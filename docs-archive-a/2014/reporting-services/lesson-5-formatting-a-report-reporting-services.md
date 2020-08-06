---
title: 'Lezione 5: Formattazione di un report (Reporting Services) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: ae46efa9-6e04-48ec-afb4-5a2314dcb05a
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 00f0d780e957fd9ff995fefb1d033275a7da428d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637090"
---
# <a name="lesson-5-formatting-a-report-reporting-services"></a><span data-ttu-id="7cfb4-102">Lesson 5: Formatting a Report (Reporting Services)</span><span class="sxs-lookup"><span data-stu-id="7cfb4-102">Lesson 5: Formatting a Report (Reporting Services)</span></span>
  <span data-ttu-id="7cfb4-103">Dopo avere aggiunto un'area dati e alcuni campi al report Sales Orders, è possibile formattare i campi relativi a data e valuta e le intestazioni di colonna.</span><span class="sxs-lookup"><span data-stu-id="7cfb4-103">Now that you've added a data region and some fields to the Sales Orders report, you can format the date and currency fields and the column headers.</span></span>  
  
 <span data-ttu-id="7cfb4-104">In questo argomento</span><span class="sxs-lookup"><span data-stu-id="7cfb4-104">In this topic:</span></span>  
  
-   [<span data-ttu-id="7cfb4-105">Formattare la data</span><span class="sxs-lookup"><span data-stu-id="7cfb4-105">Format the Date</span></span>](#bkmk_format_date)  
  
-   [<span data-ttu-id="7cfb4-106">Formattare la valuta</span><span class="sxs-lookup"><span data-stu-id="7cfb4-106">Format the Currency</span></span>](#bkmk_format_currency)  
  
-   [<span data-ttu-id="7cfb4-107">Modifica dello stile del testo e della larghezza delle colonne</span><span class="sxs-lookup"><span data-stu-id="7cfb4-107">Change Text Style and Column Widths</span></span>](#bkmk_change_textstyle)  
  
##  <a name="format-the-date"></a><a name="bkmk_format_date"></a><span data-ttu-id="7cfb4-108">Formattare la data</span><span class="sxs-lookup"><span data-stu-id="7cfb4-108">Format the Date</span></span>  
 <span data-ttu-id="7cfb4-109">Nel campo Date vengono visualizzate la data e l'ora per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="7cfb4-109">The Date field displays date and time information by default.</span></span> <span data-ttu-id="7cfb4-110">È possibile formattare tale campo in modo da visualizzare solo la data.</span><span class="sxs-lookup"><span data-stu-id="7cfb4-110">You can format it to display only the date.</span></span>  
  
#### <a name="to-format-a-date-field"></a><span data-ttu-id="7cfb4-111">Per formattare un campo di tipo data</span><span class="sxs-lookup"><span data-stu-id="7cfb4-111">To format a date field</span></span>  
  
1.  <span data-ttu-id="7cfb4-112">Fare clic sulla scheda **Progettazione** .</span><span class="sxs-lookup"><span data-stu-id="7cfb4-112">Click the **Design** tab.</span></span>  
  
2.  <span data-ttu-id="7cfb4-113">Fare clic con il pulsante destro del mouse nella cella contenente l'espressione per il campo `[Date]` e scegliere **Proprietà casella di testo**.</span><span class="sxs-lookup"><span data-stu-id="7cfb4-113">Right-click the cell with the `[Date]` field expression and then click **Text Box Properties**.</span></span>  
  
3.  <span data-ttu-id="7cfb4-114">Fare clic su **numero**, quindi selezionare nel campo **categoria** `Date` .</span><span class="sxs-lookup"><span data-stu-id="7cfb4-114">Click **Number**, and then in the **Category** field, select `Date`.</span></span>  
  
4.  <span data-ttu-id="7cfb4-115">Nella casella **Tipo** selezionare **31 Gennaio 2000**.</span><span class="sxs-lookup"><span data-stu-id="7cfb4-115">In the **Type** box, select **January 31, 2000**.</span></span>  
  
5.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
6.  <span data-ttu-id="7cfb4-116">Visualizzare un'anteprima del report per vedere la modifica al campo `[Date]` , quindi tornare alla visualizzazione della struttura.</span><span class="sxs-lookup"><span data-stu-id="7cfb4-116">Preview the report to see the change to the `[Date]` field and then change back to design view.</span></span>  
  
##  <a name="format-the-currency"></a><a name="bkmk_format_currency"></a><span data-ttu-id="7cfb4-117">Formattare la valuta</span><span class="sxs-lookup"><span data-stu-id="7cfb4-117">Format the Currency</span></span>  
 <span data-ttu-id="7cfb4-118">Nel campo LineTotal viene visualizzato un numero generico.</span><span class="sxs-lookup"><span data-stu-id="7cfb4-118">The LineTotal field displays a general number.</span></span> <span data-ttu-id="7cfb4-119">È possibile formattare tale numero come valuta.</span><span class="sxs-lookup"><span data-stu-id="7cfb4-119">Format it to display the number as currency.</span></span>  
  
#### <a name="to-format-a-currency-field"></a><span data-ttu-id="7cfb4-120">Per formattare un campo di tipo valuta</span><span class="sxs-lookup"><span data-stu-id="7cfb4-120">To format a currency field</span></span>  
  
1.  <span data-ttu-id="7cfb4-121">Fare clic con il pulsante destro del mouse nella cella contenente l'espressione per il campo `[LineTotal]` e scegliere **Proprietà casella di testo**.</span><span class="sxs-lookup"><span data-stu-id="7cfb4-121">Right-click the cell with the `[LineTotal]` field expression and then click **Text Box Properties**.</span></span>  
  
2.  <span data-ttu-id="7cfb4-122">Fare clic su **Numero**, quindi selezionare **Valuta** nel campo **Categoria**.</span><span class="sxs-lookup"><span data-stu-id="7cfb4-122">Click **Number**, and in the **Category** field, select **Currency**.</span></span>  
  
3.  <span data-ttu-id="7cfb4-123">Se la lingua delle impostazioni locali è l'italiano, le impostazioni predefinite devono essere le seguenti:</span><span class="sxs-lookup"><span data-stu-id="7cfb4-123">If your regional setting is English (United States), the defaults should be:</span></span>  
  
    -   <span data-ttu-id="7cfb4-124">**Cifre decimali: 2**</span><span class="sxs-lookup"><span data-stu-id="7cfb4-124">**Decimal places: 2**</span></span>  
  
    -   <span data-ttu-id="7cfb4-125">**Numeri negativi: (€12345,00)**</span><span class="sxs-lookup"><span data-stu-id="7cfb4-125">**Negative numbers: ($12345.00)**</span></span>  
  
    -   <span data-ttu-id="7cfb4-126">**Simbolo: € italiano**</span><span class="sxs-lookup"><span data-stu-id="7cfb4-126">**Symbol: $ English (United States)**</span></span>  
  
4.  <span data-ttu-id="7cfb4-127">Selezionare **Usa separatore delle migliaia (,)**.</span><span class="sxs-lookup"><span data-stu-id="7cfb4-127">Select **Use 1000 separator (,)**.</span></span>  
  
     <span data-ttu-id="7cfb4-128">Se il testo di esempio è:**$ 12.345,00**, le impostazioni sono corrette.</span><span class="sxs-lookup"><span data-stu-id="7cfb4-128">If the sample text is:**$12,345.00**, then your settings are correct.</span></span>  
  
5.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
6.  <span data-ttu-id="7cfb4-129">Visualizzare un'anteprima del report per vedere la modifica al campo `[LineTotal]` , quindi tornare alla visualizzazione della struttura.</span><span class="sxs-lookup"><span data-stu-id="7cfb4-129">Preview the report to see the change to the `[LineTotal]` field and then change back to design view.</span></span>  
  
##  <a name="change-text-style-and-column-widths"></a><a name="bkmk_change_textstyle"></a><span data-ttu-id="7cfb4-130">Modifica dello stile del testo e della larghezza delle colonne</span><span class="sxs-lookup"><span data-stu-id="7cfb4-130">Change Text Style and Column Widths</span></span>  
 <span data-ttu-id="7cfb4-131">È possibile modificare anche la formattazione della riga dell'intestazione per differenziarla dalle righe di dati nel report.</span><span class="sxs-lookup"><span data-stu-id="7cfb4-131">You can also change the formatting of the header row to differentiate it from the rows of data in the report.</span></span> <span data-ttu-id="7cfb4-132">Come ultima operazione, si potrà regolare la larghezza delle colonne.</span><span class="sxs-lookup"><span data-stu-id="7cfb4-132">Lastly, you will adjust the widths of the columns.</span></span>  
  
#### <a name="to-format-header-rows-and-table-columns"></a><span data-ttu-id="7cfb4-133">Per formattare le righe di intestazione e le colonne di tabella</span><span class="sxs-lookup"><span data-stu-id="7cfb4-133">To format header rows and table columns</span></span>  
  
1.  <span data-ttu-id="7cfb4-134">Fare clic nella tabella in modo che vengano visualizzati gli handle di colonna e riga sopra e accanto alla tabella.</span><span class="sxs-lookup"><span data-stu-id="7cfb4-134">Click the table so that column and row handles appear above and next to the table.</span></span>  
  
     <span data-ttu-id="7cfb4-135">![Progettazione, tabella con riga di intestazione e riga di dettaglio](../../2014/tutorials/media/rs-basictabledetailsdesign.gif "Progettazione, tabella con riga di intestazione e riga di dettaglio")</span><span class="sxs-lookup"><span data-stu-id="7cfb4-135">![Design, Table with header row and detail row](../../2014/tutorials/media/rs-basictabledetailsdesign.gif "Design, Table with header row and detail row")</span></span>  
  
     <span data-ttu-id="7cfb4-136">Le barre grigie lungo la parte superiore e laterale della tabella sono gli handle di riga e di colonna.</span><span class="sxs-lookup"><span data-stu-id="7cfb4-136">The gray bars along the top and side of the table are the column and row handles.</span></span>  
  
2.  <span data-ttu-id="7cfb4-137">Posizionare il puntatore del mouse sulla riga tra gli handle di colonna in modo che il cursore assuma la forma di una doppia freccia.</span><span class="sxs-lookup"><span data-stu-id="7cfb4-137">Point to the line between column handles so that the cursor changes into a double arrow.</span></span> <span data-ttu-id="7cfb4-138">Trascinare le colonne fino a ottenere le dimensioni desiderate.</span><span class="sxs-lookup"><span data-stu-id="7cfb4-138">Drag the columns to the size you want.</span></span>  
  
3.  <span data-ttu-id="7cfb4-139">Selezionare la riga che contiene le etichette dell'intestazione di colonna e scegliere **Carattere** dal menu **Formato** , quindi fare clic su **Grassetto**.</span><span class="sxs-lookup"><span data-stu-id="7cfb4-139">Select the row containing column header labels and from the **Format** menu, point to **Font** and then click **Bold**.</span></span>  
  
4.  <span data-ttu-id="7cfb4-140">Per visualizzare l'anteprima del report, fare clic sulla scheda **Anteprima** . Il risultato dovrebbe essere simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="7cfb4-140">To preview your report, click the **Preview** tab. It should look something like this:</span></span>  
  
     <span data-ttu-id="7cfb4-141">![Anteprima della tabella con intestazioni di colonna in grassetto](../../2014/tutorials/media/rs-basictabledetailsformattedpreview.gif "Anteprima della tabella con intestazioni di colonna in grassetto")</span><span class="sxs-lookup"><span data-stu-id="7cfb4-141">![Preview of table with bold column headers](../../2014/tutorials/media/rs-basictabledetailsformattedpreview.gif "Preview of table with bold column headers")</span></span>  
  
5.  <span data-ttu-id="7cfb4-142">Per salvare il report, scegliere **Salva tutti** nel menu **File** .</span><span class="sxs-lookup"><span data-stu-id="7cfb4-142">On the **File** menu, click **Save All** to save the report.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="7cfb4-143">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="7cfb4-143">Next Steps</span></span>  
 <span data-ttu-id="7cfb4-144">Sono stati formattati le intestazioni di colonna e i valori di data e valuta.</span><span class="sxs-lookup"><span data-stu-id="7cfb4-144">You have successfully formatted column headers and date and currency values.</span></span> <span data-ttu-id="7cfb4-145">È possibile aggiungere gruppi e totali al report.</span><span class="sxs-lookup"><span data-stu-id="7cfb4-145">Next, you will add grouping and totals to your report.</span></span> <span data-ttu-id="7cfb4-146">Vedere [Lezione 6: Aggiunta di gruppi e totali &#40;Reporting Services&#41;](../reporting-services/lesson-6-adding-grouping-and-totals-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="7cfb4-146">See [Lesson 6: Adding Grouping and Totals &#40;Reporting Services&#41;](../reporting-services/lesson-6-adding-grouping-and-totals-reporting-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7cfb4-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7cfb4-147">See Also</span></span>  
 <span data-ttu-id="7cfb4-148">[Formattazione di numeri e date &#40;Generatore report e SSRS&#41;](report-design/formatting-numbers-and-dates-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="7cfb4-148">[Formatting Numbers and Dates &#40;Report Builder and SSRS&#41;](report-design/formatting-numbers-and-dates-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="7cfb4-149">Tipi di rendering &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="7cfb4-149">Rendering Behaviors &#40;Report Builder  and SSRS&#41;</span></span>](report-design/rendering-behaviors-report-builder-and-ssrs.md)  
  
  
