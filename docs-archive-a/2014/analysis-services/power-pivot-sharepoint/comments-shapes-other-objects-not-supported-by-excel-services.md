---
title: 'Le funzionalità seguenti non sono supportate da Excel Services e potrebbero non essere visualizzate o visualizzate solo parzialmente: commenti, forme o altri oggetti | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: ade92e15-dfbf-496b-9378-a00bd83ba750
author: minewiskan
ms.author: owend
ms.openlocfilehash: 67c2989ab89f242fdce2ca64f3c2f361e17d49ba
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715764"
---
# <a name="the-following-features-are-not-supported-by-excel-services-and-may-not-display-or-may-display-only-partially-comments-shapes-or-other-objects"></a><span data-ttu-id="a078b-102">Le funzionalità seguenti non sono supportate in Excel Services e potrebbero non venire visualizzate del tutto o parzialmente: Commenti, forme o altri oggetti</span><span class="sxs-lookup"><span data-stu-id="a078b-102">The following features are not supported by Excel Services and may not display or may display only partially: Comments, Shapes, or other objects</span></span>
  <span data-ttu-id="a078b-103">Questo errore si verifica quando si aggiungono filtri dei dati a una cartella di lavoro di PowerPivot da un elenco di campi PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="a078b-103">This error occurs when you add Slicers to a PowerPivot workbook from a PowerPivot Field List.</span></span>  
  
## <a name="details"></a><span data-ttu-id="a078b-104">Dettagli</span><span class="sxs-lookup"><span data-stu-id="a078b-104">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a078b-105">Si applica a</span><span class="sxs-lookup"><span data-stu-id="a078b-105">Applies to</span></span>|<span data-ttu-id="a078b-106">PowerPivot per SharePoint</span><span class="sxs-lookup"><span data-stu-id="a078b-106">PowerPivot for SharePoint</span></span>|  
|<span data-ttu-id="a078b-107">Versione prodotto</span><span class="sxs-lookup"><span data-stu-id="a078b-107">Product Version</span></span>|[!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]<span data-ttu-id="a078b-108">, [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a078b-108">, [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span></span>|  
|<span data-ttu-id="a078b-109">Causa</span><span class="sxs-lookup"><span data-stu-id="a078b-109">Cause</span></span>|<span data-ttu-id="a078b-110">In Excel Web Access non è possibile eseguire il rendering dell'oggetto Shape utilizzato per controllare la collocazione e la formattazione dei filtri dei dati aggiunti a una cartella di lavoro dall'elenco campi di PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="a078b-110">Excel Web Access cannot render the Shape object used to control positioning and formatting of Slicers added to a workbook from the PowerPivot Field List.</span></span>|  
|<span data-ttu-id="a078b-111">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="a078b-111">Message Text</span></span>|<span data-ttu-id="a078b-112">Le funzionalità seguenti non sono supportate in Excel Services e potrebbero non venire visualizzate del tutto o parzialmente:</span><span class="sxs-lookup"><span data-stu-id="a078b-112">The following features are not supported by Excel Services and may not display or may display only partially:</span></span><br /><br /> <span data-ttu-id="a078b-113">Commenti, forme o altri oggetti</span><span class="sxs-lookup"><span data-stu-id="a078b-113">Comments, Shapes, or other objects</span></span><br /><br /> <span data-ttu-id="a078b-114">Alcune funzionalità, ad esempio le query su dati esterni, visualizzano i dati memorizzati nella cache che possono essere aggiornati solo in Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="a078b-114">Some features, such as external data queries, display cached data which can only be refreshed in Microsoft Excel.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a078b-115">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="a078b-115">Explanation</span></span>  
 <span data-ttu-id="a078b-116">In Excel Accesso Web questo errore viene visualizzato quando si apre una cartella di lavoro di PowerPivot in un browser e si fa clic sul pulsante **Dettagli** per il messaggio **funzionalità non supportate. questa cartella di lavoro potrebbe non essere visualizzata come previsto**.</span><span class="sxs-lookup"><span data-stu-id="a078b-116">Excel Web Access shows this error when you open a PowerPivot workbook in a browser and you click the **Details** button for the message, **Unsupported Features This workbook may not display as intended**.</span></span>  
  
 <span data-ttu-id="a078b-117">Questo errore si verifica in quanto la cartella di lavoro di PowerPivot contiene filtri dei dati il cui layout viene controllato da un oggetto Shape nascosto in Excel.</span><span class="sxs-lookup"><span data-stu-id="a078b-117">This error occurs because the PowerPivot workbook contains Slicers whose layout is controlled by a hidden Shape object in Excel.</span></span> <span data-ttu-id="a078b-118">L'oggetto Shape controlla la formattazione e la collocazione dei filtri dei dati nelle posizioni orizzontali e verticali.</span><span class="sxs-lookup"><span data-stu-id="a078b-118">The Shape object controls the formatting and positioning of the Slicers in horizontal and vertical placements.</span></span>  
  
 <span data-ttu-id="a078b-119">In Excel Services non è possibile eseguire il rendering di un oggetto Shape ma, poiché l'oggetto è nascosto, il fatto che non venga eseguito il rendering non rappresenta un problema.</span><span class="sxs-lookup"><span data-stu-id="a078b-119">Excel Services cannot render a Shape object, but because the object is hidden, the fact that it does not render is not an issue.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a078b-120">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="a078b-120">User Action</span></span>  
 <span data-ttu-id="a078b-121">Questo errore può essere ignorato.</span><span class="sxs-lookup"><span data-stu-id="a078b-121">This error can be ignored.</span></span> <span data-ttu-id="a078b-122">Fare clic su **OK** per chiudere il messaggio di errore e continuare a usare la cartella di lavoro e i filtri dei dati senza alcun problema.</span><span class="sxs-lookup"><span data-stu-id="a078b-122">Click **OK** to close the error message and proceed to use the workbook and Slicers with no problem.</span></span>  
  
  
