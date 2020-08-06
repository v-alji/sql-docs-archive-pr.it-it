---
title: Definire le impostazioni locali per un report o una casella di testo (Reporting Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- locales [Reporting Services]
ms.assetid: df115b01-184b-47f0-b5ec-0ad965ff9bee
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: bb2b0cbd6e4216138520834216358ee455729386
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625143"
---
# <a name="set-the-locale-for-a-report-or-text-box-reporting-services"></a><span data-ttu-id="2c74c-102">Definizione delle impostazioni locali per un report o una casella di testo (Reporting Services)</span><span class="sxs-lookup"><span data-stu-id="2c74c-102">Set the Locale for a Report or Text Box (Reporting Services)</span></span>
  <span data-ttu-id="2c74c-103">Nella proprietà **Language** di un report o di una casella di testo sono contenute le impostazioni locali che determinano i formati predefiniti per la visualizzazione dei dati del report che differiscono in base alla lingua e al paese, ad esempio i valori relativi alla data o alla valuta o quelli numerici.</span><span class="sxs-lookup"><span data-stu-id="2c74c-103">The **Language** property on a report or a text box contains the locale setting, which determines the default formats for displaying report data that differ by language and region, for example, date, currency, or number values.</span></span> <span data-ttu-id="2c74c-104">La proprietà **Language** di una casella di testo ha la priorità rispetto alla proprietà **Language** impostata per il report.</span><span class="sxs-lookup"><span data-stu-id="2c74c-104">The **Language** property on a text box overrides the **Language** property on the report.</span></span> <span data-ttu-id="2c74c-105">Se non viene specificato alcun valore per **Language**, in Reporting Services vengono utilizzate le impostazioni locali del sistema operativo nel server di report per i report pubblicati o del computer di creazione di report per l'anteprima del report.</span><span class="sxs-lookup"><span data-stu-id="2c74c-105">If no value is specified for **Language**, Reporting Services uses the locale of the operating system on the report server for published reports or of the report authoring computer for report preview.</span></span>  
  
 <span data-ttu-id="2c74c-106">Per i report HTML, è possibile ignorare il valore **Language** predefinito e usare la lingua specificata dall'intestazione HTTP del client del browser utilizzando il campo predefinito User!Language in un'espressione per la proprietà **Language** di un report o di una casella di testo.</span><span class="sxs-lookup"><span data-stu-id="2c74c-106">For HTML reports, you can override the default **Language** value and use the language specified by the HTTP header of the browser client by using the built-in field User!Language in an expression for the **Language** property of a report or a text box.</span></span>  
  
 <span data-ttu-id="2c74c-107">È inoltre possibile specificare la proprietà **Language** per un report in un URL.</span><span class="sxs-lookup"><span data-stu-id="2c74c-107">You can also specify the **Language** property for a report in a URL.</span></span> <span data-ttu-id="2c74c-108">Per altre informazioni, vedere [Impostare la lingua per i parametri del report in un URL](../set-the-language-for-report-parameters-in-a-url.md).</span><span class="sxs-lookup"><span data-stu-id="2c74c-108">For more information, see [Set the Language for Report Parameters in a URL](../set-the-language-for-report-parameters-in-a-url.md).</span></span>  
  
### <a name="to-set-the-locale-for-a-report"></a><span data-ttu-id="2c74c-109">Per definire le impostazioni locali per un report</span><span class="sxs-lookup"><span data-stu-id="2c74c-109">To set the locale for a report</span></span>  
  
1.  <span data-ttu-id="2c74c-110">Nella visualizzazione della struttura fare clic all'esterno dell'area di progettazione del report per selezionarlo.</span><span class="sxs-lookup"><span data-stu-id="2c74c-110">In Design view, click outside the report design surface to select the report.</span></span>  
  
2.  <span data-ttu-id="2c74c-111">Nel riquadro Proprietà digitare o selezionare per la proprietà **Language** la lingua da utilizzare per il report.</span><span class="sxs-lookup"><span data-stu-id="2c74c-111">In the Properties pane, for the **Language** property, type or select the language that you want to use for the report.</span></span>  
  
### <a name="to-set-the-locale-for-a-text-box"></a><span data-ttu-id="2c74c-112">Per definire le impostazioni locali per una casella di testo</span><span class="sxs-lookup"><span data-stu-id="2c74c-112">To set the locale for a text box</span></span>  
  
1.  <span data-ttu-id="2c74c-113">Nella visualizzazione della struttura selezionare la casella di testo cui si desidera applicare le impostazioni locali.</span><span class="sxs-lookup"><span data-stu-id="2c74c-113">In Design view, select the text box to which you want to apply the locale settings.</span></span>  
  
2.  <span data-ttu-id="2c74c-114">Nel riquadro Proprietà effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2c74c-114">In the Properties pane, do the following:</span></span>  
  
    -   <span data-ttu-id="2c74c-115">Per la proprietà **Calendar** , digitare o selezionare il calendario che si desidera utilizzare per le date.</span><span class="sxs-lookup"><span data-stu-id="2c74c-115">For the **Calendar** property, type or select the calendar that you want to use for dates.</span></span>  
  
    -   <span data-ttu-id="2c74c-116">Per la proprietà **Direction** digitare o selezionare la direzione in cui è scritto il testo.</span><span class="sxs-lookup"><span data-stu-id="2c74c-116">For the **Direction** property, type or select the direction in which the text is written.</span></span>  
  
    -   <span data-ttu-id="2c74c-117">Per la proprietà **Language** , digitare o selezionare la lingua che si desidera utilizzare per la casella di testo.</span><span class="sxs-lookup"><span data-stu-id="2c74c-117">For the **Language** property, type or select the language that you want to use for the text box.</span></span> <span data-ttu-id="2c74c-118">Questo valore ha la priorità rispetto alla proprietà **Language** per il report.</span><span class="sxs-lookup"><span data-stu-id="2c74c-118">This value overrides the **Language** property for the Report.</span></span>  
  
    -   <span data-ttu-id="2c74c-119">Per la proprietà **NumeralLanguage** , digitare o selezionare il formato da utilizzare per i numeri presenti nella casella di testo.</span><span class="sxs-lookup"><span data-stu-id="2c74c-119">For the **NumeralLanguage** property, type or select the format to use for numbers in the text box.</span></span>  
  
    -   <span data-ttu-id="2c74c-120">Per la proprietà **NumeralVariant** digitare o selezionare la variante del formato da utilizzare per i numeri nella casella di testo.</span><span class="sxs-lookup"><span data-stu-id="2c74c-120">For the **NumeralVariant** property, type or select the variant of the format to use for numbers in the text box.</span></span>  
  
    -   <span data-ttu-id="2c74c-121">Per la proprietà **UnicodeBiDi** selezionare il livello di incorporamento bidirezionale da utilizzare nella casella di testo.</span><span class="sxs-lookup"><span data-stu-id="2c74c-121">For the **UnicodeBiDi** property, select the level of bidirectional embedding to use in the text box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c74c-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2c74c-122">See Also</span></span>  
 [<span data-ttu-id="2c74c-123">Utilizzo delle espressioni nei report &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="2c74c-123">Expression Uses in Reports &#40;Report Builder and SSRS&#41;</span></span>](expression-uses-in-reports-report-builder-and-ssrs.md)  
  
  
