---
title: Align the Data in a Chart in a Table or Matrix (Report Builder and SSRS) (Allineare i dati in un grafico di una tabella o matrice (Generatore report e SSRS)) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 75137575-d1bf-46d6-8527-5afc85eea5e1
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 3e4278cd9f0dd5526770b43d2c6d94a8b87158cc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636592"
---
# <a name="align-the-data-in-a-chart-in-a-table-or-matrix-report-builder-and-ssrs"></a><span data-ttu-id="917fa-102">Allineare i dati in un grafico di una tabella o matrice (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="917fa-102">Align the Data in a Chart in a Table or Matrix (Report Builder and SSRS)</span></span>
  <span data-ttu-id="917fa-103">I grafici sparkline e le barre dei dati sono grafici semplici, di piccole dimensioni, contenenti numerose informazioni poco dettagliate.</span><span class="sxs-lookup"><span data-stu-id="917fa-103">Sparklines and data bars are small, simple charts that convey a lot of information with little extraneous detail.</span></span> <span data-ttu-id="917fa-104">Quando si seleziona questa opzione, i valori presenti nei grafici sparkline e nelle barre dei dati vengono allineati nelle diverse celle della tabella o della matrice, anche se mancano dei valori nei dati su cui si basano.</span><span class="sxs-lookup"><span data-stu-id="917fa-104">When you check this option, the values in your sparklines and data bars will align across the different cells in the table or matrix, even if there are missing values in the data they are based on.</span></span>  
  
 <span data-ttu-id="917fa-105">![rs_SparklineAlignData](../media/rs-sparklinealigndata.gif "rs_SparklineAlignData")</span><span class="sxs-lookup"><span data-stu-id="917fa-105">![rs_SparklineAlignData](../media/rs-sparklinealigndata.gif "rs_SparklineAlignData")</span></span>  
  
 <span data-ttu-id="917fa-106">In questa immagine, nell'istogramma vengono mostrate le vendite giornaliere per ogni dipendente.</span><span class="sxs-lookup"><span data-stu-id="917fa-106">In this image, the column chart shows daily sales for each employee.</span></span> <span data-ttu-id="917fa-107">Nei giorni in cui il dipendente non ha effettuato vendite, nel grafico viene lasciato uno spazio vuoto, mentre i giorni successivi vengono allineati orizzontalmente.</span><span class="sxs-lookup"><span data-stu-id="917fa-107">Note that for days that an employee has no sales, the chart leaves a blank and aligns subsequent days horizontally.</span></span> <span data-ttu-id="917fa-108">I grafici vengono inoltre allineati verticalmente mettendone in relazione le diverse dimensioni.</span><span class="sxs-lookup"><span data-stu-id="917fa-108">It also aligns the charts vertically by making the sizes of the different charts relative to each other.</span></span> <span data-ttu-id="917fa-109">Per altre informazioni, vedere [Grafici sparkline e barre dei dati &#40;Generatore report e SSRS&#41;](sparklines-and-data-bars-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="917fa-109">For more information, see [Sparklines and Data Bars &#40;Report Builder and SSRS&#41;](sparklines-and-data-bars-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="align-the-data-in-a-sparkline-or-data-bar"></a><span data-ttu-id="917fa-110">Allineare i dati in un grafico sparkline o in una barra dei dati</span><span class="sxs-lookup"><span data-stu-id="917fa-110">Align the data in a sparkline or data bar</span></span>  
  
1.  <span data-ttu-id="917fa-111">Fare clic nel grafico sparkline o barra dei dati, quindi selezionare **Proprietà asse orizzontale** o **Proprietà asse verticale**.</span><span class="sxs-lookup"><span data-stu-id="917fa-111">Click in the sparkline or data bar, and then click **Horizontal Axis Properties** or **Vertical Axis Properties**.</span></span>  
  
2.  <span data-ttu-id="917fa-112">Nella scheda **Opzioni asse** selezionare la casella **Align axes in** (Allinea assi in), quindi nella casella a discesa selezionare il gruppo sul quale allineare l'asse.</span><span class="sxs-lookup"><span data-stu-id="917fa-112">On the **Axis Options** tab, check the **Align axes in** box, and then in the dropdown box, select the group on which to align the axis.</span></span>  
  
3.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="917fa-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="917fa-113">See Also</span></span>  
 <span data-ttu-id="917fa-114">[Grafici &#40;Generatore report e SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="917fa-114">[Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="917fa-115">Aggiungere grafici sparkline e barre dei dati &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="917fa-115">Add Sparklines and Data Bars &#40;Report Builder and SSRS&#41;</span></span>](add-sparklines-and-data-bars-report-builder-and-ssrs.md)  
  
  
