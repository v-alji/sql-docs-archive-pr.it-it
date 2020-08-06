---
title: Visualizzatore dati | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.dataviewer.f1
helpviewer_keywords:
- Data Viewer dialog box
ms.assetid: 6351309a-688f-4e82-9697-1712130f10a1
author: chugugrace
ms.author: chugu
ms.openlocfilehash: dc576981e875eade84dd3576f4ed93b66784411f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629527"
---
# <a name="data-viewer"></a><span data-ttu-id="86cb0-102">Visualizzatore dati</span><span class="sxs-lookup"><span data-stu-id="86cb0-102">Data Viewer</span></span>
  <span data-ttu-id="86cb0-103">Se viene configurato un percorso per utilizzare un visualizzatore dati, in quest'ultimo viene visualizzato il buffer di dati in base al buffer durante lo spostamento dei dati tra due componenti di flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="86cb0-103">If a path is configured to use a data viewer, the Data Viewer displays the data buffer by buffer as data moves between two data flow components.</span></span>  
  
## <a name="options"></a><span data-ttu-id="86cb0-104">Opzioni</span><span class="sxs-lookup"><span data-stu-id="86cb0-104">Options</span></span>  
 <span data-ttu-id="86cb0-105">**Freccia verde**</span><span class="sxs-lookup"><span data-stu-id="86cb0-105">**Green arrow**</span></span>  
 <span data-ttu-id="86cb0-106">Fare clic sulla freccia per visualizzare i dati nel buffer successivo.</span><span class="sxs-lookup"><span data-stu-id="86cb0-106">Click to display the data in the next buffer.</span></span> <span data-ttu-id="86cb0-107">Se i dati possono essere spostati in un unico buffer, l'opzione non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="86cb0-107">If the data can be moved in a single buffer, this option is not available.</span></span>  
  
 <span data-ttu-id="86cb0-108">**Scollega**</span><span class="sxs-lookup"><span data-stu-id="86cb0-108">**Detach**</span></span>  
 <span data-ttu-id="86cb0-109">Consente di scollegare il visualizzatore dati.</span><span class="sxs-lookup"><span data-stu-id="86cb0-109">Detach the data viewer.</span></span>  
  
 <span data-ttu-id="86cb0-110">**Nota** Se si scollega un visualizzatore dati, questo non viene eliminato.</span><span class="sxs-lookup"><span data-stu-id="86cb0-110">**Note** Detaching a data viewer does not delete the data viewer.</span></span> <span data-ttu-id="86cb0-111">Se il visualizzatore dati è stato scollegato, il flusso di dati continua attraverso il percorso, ma i dati nel visualizzatore non vengono aggiornati in base a quelli effettivamente presenti nei buffer.</span><span class="sxs-lookup"><span data-stu-id="86cb0-111">If the data viewer has been detached, data continues to flow through the path, but the data in the viewer is not updated to match the data in each buffer.</span></span>  
  
 <span data-ttu-id="86cb0-112">**Collega**</span><span class="sxs-lookup"><span data-stu-id="86cb0-112">**Attach**</span></span>  
 <span data-ttu-id="86cb0-113">Consente di collegare un visualizzatore dati.</span><span class="sxs-lookup"><span data-stu-id="86cb0-113">Attach a data viewer.</span></span>  
  
 <span data-ttu-id="86cb0-114">**Nota** Quando il visualizzatore dati è collegato, vengono visualizzate informazioni derivate da ogni buffer nel flusso di dati e quindi si verifica una sospensione.</span><span class="sxs-lookup"><span data-stu-id="86cb0-114">**Note** When the data viewer is attached, it displays information from each buffer in the data flow and then pauses.</span></span> <span data-ttu-id="86cb0-115">È possibile avanzare attraverso i buffer mediante la freccia verde.</span><span class="sxs-lookup"><span data-stu-id="86cb0-115">You can advance through the buffers by using the green arrow.</span></span>  
  
 <span data-ttu-id="86cb0-116">**Copia dati**</span><span class="sxs-lookup"><span data-stu-id="86cb0-116">**Copy Data**</span></span>  
 <span data-ttu-id="86cb0-117">Consente di copiare i dati nel buffer corrente negli Appunti.</span><span class="sxs-lookup"><span data-stu-id="86cb0-117">Copy data in the current buffer to the Clipboard.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86cb0-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="86cb0-118">See Also</span></span>  
 [<span data-ttu-id="86cb0-119">Debug di un flusso di dati</span><span class="sxs-lookup"><span data-stu-id="86cb0-119">Debugging Data Flow</span></span>](../troubleshooting/debugging-data-flow.md)  
  
  
