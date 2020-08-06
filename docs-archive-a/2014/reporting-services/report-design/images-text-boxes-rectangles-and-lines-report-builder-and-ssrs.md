---
title: Images, Text Boxes, Rectangles, and Lines (Report Builder and SSRS) (Immagini, caselle di testo, rettangoli e linee (Generatore report e SSRS)) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: aa7ad08f-dd49-401e-9619-522e27055bb9
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2fb9a47bb3b8d68d48be42f8f0a2adddfc3ba130
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713860"
---
# <a name="images-text-boxes-rectangles-and-lines-report-builder-and-ssrs"></a><span data-ttu-id="9b89a-102">Immagini, caselle di testo, rettangoli e linee (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="9b89a-102">Images, Text Boxes, Rectangles, and Lines (Report Builder and SSRS)</span></span>
  <span data-ttu-id="9b89a-103">Oltre alle aree dati quali tabelle, matrici e grafici, nei report vengono utilizzati altri elementi, ad esempio immagini, caselle di testo e rettangoli, per aumentarne l'impatto visivo, evidenziare le informazioni più importanti o fornire informazioni correlate.</span><span class="sxs-lookup"><span data-stu-id="9b89a-103">In addition to data regions like tables, matrices, and charts, reports use other report items like images, text boxes, and rectangles to add visual interest, highlight key information, or provide related information.</span></span> <span data-ttu-id="9b89a-104">È possibile modificare la formattazione di un elemento del report.</span><span class="sxs-lookup"><span data-stu-id="9b89a-104">You can change the formatting of a report item.</span></span> <span data-ttu-id="9b89a-105">È possibile, ad esempio, aggiungere un bordo o un riempimento, modificare la visibilità o la direzione iniziale oppure specificare valori esatti per le dimensioni e la posizione dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="9b89a-105">For example, you can add a border or padding, change the initial visibility or direction, or specify an exact size and location for the item.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="in-this-section"></a><span data-ttu-id="9b89a-106">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="9b89a-106">In This Section</span></span>  
 [<span data-ttu-id="9b89a-107">Caselle di testo &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="9b89a-107">Text Boxes &#40;Report Builder and SSRS&#41;</span></span>](text-boxes-report-builder-and-ssrs.md)  
 <span data-ttu-id="9b89a-108">Le caselle di testo possono essere inserite in qualunque punto del report e possono contenere etichette, campi o dati calcolati.</span><span class="sxs-lookup"><span data-stu-id="9b89a-108">Text boxes can be placed anywhere on a report and can contain labels, fields, or calculated data.</span></span> <span data-ttu-id="9b89a-109">Per definire il valore da visualizzare in una casella di testo quando si apre un report, si utilizzano le espressioni.</span><span class="sxs-lookup"><span data-stu-id="9b89a-109">You use expressions to define the value to display in a text box when you view a report.</span></span>  
  
 <span data-ttu-id="9b89a-110">Ogni cella di una tabella o matrice è anche una casella di testo che può essere formattata esattamente come le caselle di testo autonome.</span><span class="sxs-lookup"><span data-stu-id="9b89a-110">Every cell in a table or matrix is also a text box, which you can format in the same way that you format stand-alone text boxes.</span></span>  
  
 [<span data-ttu-id="9b89a-111">Rettangoli e linee &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="9b89a-111">Rectangles and Lines &#40;Report Builder and SSRS&#41;</span></span>](rectangles-and-lines-report-builder-and-ssrs.md)  
 <span data-ttu-id="9b89a-112">Le**linee** vengono visualizzate in orizzontale, verticale o diagonale.</span><span class="sxs-lookup"><span data-stu-id="9b89a-112">**Lines** display horizontally, vertically, or diagonally.</span></span> <span data-ttu-id="9b89a-113">Una linea è definita da un punto iniziale e un punto finale e da vari stili, ad esempio spessore e colore.</span><span class="sxs-lookup"><span data-stu-id="9b89a-113">A line is defined with a start and end point and can have various styles (for example, weight and color) assigned to it.</span></span> <span data-ttu-id="9b89a-114">A una linea non è associato alcun dato.</span><span class="sxs-lookup"><span data-stu-id="9b89a-114">A line has no data associated with it.</span></span>  
  
 <span data-ttu-id="9b89a-115">I**rettangoli** possono essere utilizzati come elementi grafici o come contenitori per altri elementi del report.</span><span class="sxs-lookup"><span data-stu-id="9b89a-115">**Rectangles** can be used as a graphical element, or as a container for other report items.</span></span> <span data-ttu-id="9b89a-116">Se utilizzato come elemento grafico, un rettangolo ha le stesse proprietà di una linea.</span><span class="sxs-lookup"><span data-stu-id="9b89a-116">As a graphical element, a rectangle has the same properties as a line.</span></span> <span data-ttu-id="9b89a-117">Come contenitore, un rettangolo funge da contenitore padre per tutti gli elementi del report al suo interno.</span><span class="sxs-lookup"><span data-stu-id="9b89a-117">As a container, a rectangle acts as a parent container for all report items inside it.</span></span> <span data-ttu-id="9b89a-118">Posizionando gli elementi del report in un contenitore padre, è possibile controllarne l'aspetto in ogni pagina del report.</span><span class="sxs-lookup"><span data-stu-id="9b89a-118">Placing report items in a parent container helps control how they appear on each report page.</span></span>  
  
 [<span data-ttu-id="9b89a-119">Immagini &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="9b89a-119">Images &#40;Report Builder and SSRS&#41;</span></span>](images-report-builder-and-ssrs.md)  
 <span data-ttu-id="9b89a-120">Le immagini consentono di visualizzare dati di immagine binari in un report.</span><span class="sxs-lookup"><span data-stu-id="9b89a-120">Images display binary image data in a report.</span></span> <span data-ttu-id="9b89a-121">È necessario fornire l'origine per l'immagine,</span><span class="sxs-lookup"><span data-stu-id="9b89a-121">You provide the source for the image.</span></span> <span data-ttu-id="9b89a-122">che può essere un riferimento a un URL di un'immagine archiviata in un server Web, un riferimento a dati immagine incorporati oppure un riferimento a dati immagine binari in un database.</span><span class="sxs-lookup"><span data-stu-id="9b89a-122">The source can be a URL reference to an image stored on a Web server, a reference to embedded image data, or a reference to binary image data in a database.</span></span> <span data-ttu-id="9b89a-123">Generatore report e Progettazione report supportano file con estensione bmp, jpeg, gif e png.</span><span class="sxs-lookup"><span data-stu-id="9b89a-123">Report Builder and Report Designer support .bmp, .jpeg, .gif, and .png files.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b89a-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9b89a-124">See Also</span></span>  
 [<span data-ttu-id="9b89a-125">Formattazione degli elementi del report &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="9b89a-125">Formatting Report Items &#40;Report Builder and SSRS&#41;</span></span>](formatting-report-items-report-builder-and-ssrs.md)  
  
  
