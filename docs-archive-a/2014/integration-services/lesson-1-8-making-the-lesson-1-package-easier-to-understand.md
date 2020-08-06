---
title: 'Passaggio 8: Semplificazione della comprensione del pacchetto della lezione 1 | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: e3751e53-77c7-47d0-8fe8-73ed1a53413a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 67fb8e2adb9062b5b777acc14df0ddc5b45884ee
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628830"
---
# <a name="step-8-making-the-lesson-1-package-easier-to-understand"></a><span data-ttu-id="8d0fe-102">Passaggio 8: Semplificazione del pacchetto della lezione 1</span><span class="sxs-lookup"><span data-stu-id="8d0fe-102">Step 8: Making the Lesson 1 Package Easier to Understand</span></span>
  <span data-ttu-id="8d0fe-103">Dopo avere completato la configurazione del pacchetto della lezione 1, può essere utile riordinarne il layout.</span><span class="sxs-lookup"><span data-stu-id="8d0fe-103">Now that you have completed the configuration of the Lesson 1 package, it is a good idea to tidy up the package layout.</span></span> <span data-ttu-id="8d0fe-104">Se le forme nel layout del flusso di controllo e del flusso di dati sono di dimensioni casuali o se non sono allineate o raggruppate, può risultare più difficile comprendere la funzionalità del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="8d0fe-104">If the shapes in the control and data flow layouts are random sizes, or if the shapes are not aligned or grouped, the functionality of package can be more difficult to understand.</span></span>  
  
 [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] <span data-ttu-id="8d0fe-105">Data Tools sono disponibili strumenti che consentono di formattare facilmente e rapidamente il layout dei pacchetti.</span><span class="sxs-lookup"><span data-stu-id="8d0fe-105">Data Tools provides tools that make it easy and quick to format the package layout.</span></span> <span data-ttu-id="8d0fe-106">Le caratteristiche di formattazione includono la possibilità di impostare forme di dimensioni uguali, di allineare le forme e di modificare la spaziatura orizzontale e verticale tra le forme.</span><span class="sxs-lookup"><span data-stu-id="8d0fe-106">The formatting features include the ability to make shapes the same size, align shapes, and manipulate the horizontal and vertical spacing between shapes.</span></span>  
  
 <span data-ttu-id="8d0fe-107">Un altro modo per rendere più comprensibili le funzionalità del pacchetto consiste nell'aggiunta di annotazioni descrittive.</span><span class="sxs-lookup"><span data-stu-id="8d0fe-107">Another way to improve the understanding of package functionality is to add annotations that describe package functionality.</span></span>  
  
 <span data-ttu-id="8d0fe-108">In questa attività verranno utilizzate le funzionalità di formattazione di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Data Tools per migliorare il layout del flusso di dati e aggiungere un'annotazione al flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="8d0fe-108">In this task, you will use the formatting features in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Data Tools to improve the layout of the data flow and also add an annotation to the data flow.</span></span>  
  
### <a name="to-format-the-layout-of-the-data-flow"></a><span data-ttu-id="8d0fe-109">Per formattare il layout del flusso di dati</span><span class="sxs-lookup"><span data-stu-id="8d0fe-109">To format the layout of the data flow</span></span>  
  
1.  <span data-ttu-id="8d0fe-110">Se il pacchetto della lezione 1 non è aperto, fare doppio clic su Lesson 1.dtsx in Esplora soluzioni.</span><span class="sxs-lookup"><span data-stu-id="8d0fe-110">If the Lesson 1 package is not already open, double-click Lesson 1.dtsx in Solution Explorer.</span></span>  
  
2.  <span data-ttu-id="8d0fe-111">Fare clic sulla scheda **Flusso di dati** .</span><span class="sxs-lookup"><span data-stu-id="8d0fe-111">Click the **Data Flow** tab.</span></span>  
  
3.  <span data-ttu-id="8d0fe-112">Posizionare il cursore in alto a destra rispetto alla trasformazione Extract Sample Currency, fare clic e trascinare il cursore su tutti i componenti del flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="8d0fe-112">Place the cursor to the top and to the right of the Extract Sample Currency transformation, click, and then drag the cursor across all the data flow components.</span></span>  
  
4.  <span data-ttu-id="8d0fe-113">Scegliere **Rendi uguali** dal menu **Formato**e quindi fare clic su **Entrambe**.</span><span class="sxs-lookup"><span data-stu-id="8d0fe-113">On the **Format** menu, point to **Make Same Size**, and then click **Both**.</span></span>  
  
5.  <span data-ttu-id="8d0fe-114">Con gli oggetti del flusso di dati selezionati, scegliere **Allinea** dal menu **Formato**e quindi fare clic su **A sinistra**.</span><span class="sxs-lookup"><span data-stu-id="8d0fe-114">With the data flow objects selected, on the **Format** menu, point to **Align**, and then click **Lefts**.</span></span>  
  
### <a name="to-add-an-annotation-to-the-data-flow"></a><span data-ttu-id="8d0fe-115">Per aggiungere un'annotazione al flusso di dati</span><span class="sxs-lookup"><span data-stu-id="8d0fe-115">To add an annotation to the data flow</span></span>  
  
1.  <span data-ttu-id="8d0fe-116">Fare clic con il pulsante destro del mouse in un punto qualsiasi dello sfondo dell'area di progettazione del flusso di dati e quindi scegliere **Aggiungi annotazione**.</span><span class="sxs-lookup"><span data-stu-id="8d0fe-116">Right-click anywhere in the background of the data flow design surface and then click **Add Annotation**.</span></span>  
  
2.  <span data-ttu-id="8d0fe-117">Digitare o incollare il testo seguente nella casella delle annotazioni.</span><span class="sxs-lookup"><span data-stu-id="8d0fe-117">Type or paste the following text in the annotation box.</span></span>  
  
     <span data-ttu-id="8d0fe-118">**Tramite il flusso di dati vengono estratti dati da un file, vengono cercati valori nella colonna CurrencyKey della tabella DimCurrency e nella colonna DateKey della tabella DimDate e vengono scritti i dati nella tabella NewFactCurrencyRate.**</span><span class="sxs-lookup"><span data-stu-id="8d0fe-118">**The data flow extracts data from a file, looks up values in the CurrencyKey column in the DimCurrency table and the DateKey column in the DimDate table, and writes the data to the NewFactCurrencyRate table.**</span></span>  
  
     <span data-ttu-id="8d0fe-119">Per eseguire il wrapping del testo nella casella delle annotazioni, inserire il cursore nel punto in cui si desidera iniziare una nuova riga e premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="8d0fe-119">To wrap the text in the annotation box, place the cursor where you want to start a new line and press the Enter key.</span></span>  
  
     <span data-ttu-id="8d0fe-120">Se non si inserisce alcun testo nella casella delle annotazioni, quest'ultima scomparirà quando si farà clic al suo esterno.</span><span class="sxs-lookup"><span data-stu-id="8d0fe-120">If you do not add text to the annotation box, it disappears when you click outside the box.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="8d0fe-121">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="8d0fe-121">Next Steps</span></span>  
 [<span data-ttu-id="8d0fe-122">Passaggio 9: Test del pacchetto creato nella lezione 1 dell'esercitazione</span><span class="sxs-lookup"><span data-stu-id="8d0fe-122">Step 9: Testing the Lesson 1 Tutorial Package</span></span>](../integration-services/lesson-1-9-testing-the-lesson-1-tutorial-package.md)  
  
  
