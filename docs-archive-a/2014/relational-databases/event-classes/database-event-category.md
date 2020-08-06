---
title: Categoria di eventi Database | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
topic_type:
- apiref
helpviewer_keywords:
- event classes [SQL Server], Database event category
- Database event category [SQL Server]
- SQL Server event classes, Database event category
ms.assetid: b61af738-f144-4992-b0b2-d44cb7240991
author: stevestein
ms.author: sstein
ms.openlocfilehash: 2860e1434611393c941a639280343f736073c709
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635048"
---
# <a name="database-event-category"></a><span data-ttu-id="1193d-102">Categoria di eventi Database</span><span class="sxs-lookup"><span data-stu-id="1193d-102">Database Event Category</span></span>
  <span data-ttu-id="1193d-103">La categoria di eventi **Database** include classi di evento per il monitoraggio del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1193d-103">The **Database** event category contains event classes to monitor the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1193d-104">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="1193d-104">In This Section</span></span>  
  
|<span data-ttu-id="1193d-105">Argomento</span><span class="sxs-lookup"><span data-stu-id="1193d-105">Topic</span></span>|<span data-ttu-id="1193d-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1193d-106">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="1193d-107">Classe di evento Data File Auto Grow</span><span class="sxs-lookup"><span data-stu-id="1193d-107">Data File Auto Grow Event Class</span></span>](data-file-auto-grow-event-class.md)|<span data-ttu-id="1193d-108">Indica che le dimensioni del file di dati sono aumentate automaticamente.</span><span class="sxs-lookup"><span data-stu-id="1193d-108">Indicates that the data file grew automatically.</span></span> <span data-ttu-id="1193d-109">Questo evento non viene generato se le dimensioni del file vengono incrementate in modo esplicito tramite ALTER DATABASE.</span><span class="sxs-lookup"><span data-stu-id="1193d-109">This event is not triggered if the data file is grown explicitly through ALTER DATABASE.</span></span>|  
|[<span data-ttu-id="1193d-110">Classe di evento Data File Auto Shrink</span><span class="sxs-lookup"><span data-stu-id="1193d-110">Data File Auto Shrink Event Class</span></span>](data-file-auto-shrink-event-class.md)|<span data-ttu-id="1193d-111">Indica che il file di dati è stato compattato.</span><span class="sxs-lookup"><span data-stu-id="1193d-111">Indicates that the data file has been shrunk.</span></span>|  
|[<span data-ttu-id="1193d-112">Classe di evento Database Mirroring Connection</span><span class="sxs-lookup"><span data-stu-id="1193d-112">Database Mirroring Connection Event Class</span></span>](database-mirroring-connection-event-class.md)|<span data-ttu-id="1193d-113">Evento generato per indicare lo stato di una connessione di trasporto per il mirroring del database.</span><span class="sxs-lookup"><span data-stu-id="1193d-113">An event generated to report the status of a transport connection for database mirroring.</span></span>|  
|[<span data-ttu-id="1193d-114">Classe di evento Database Mirroring State Change</span><span class="sxs-lookup"><span data-stu-id="1193d-114">Database Mirroring State Change Event Class</span></span>](database-mirroring-state-change-event-class.md)|<span data-ttu-id="1193d-115">Indica quando lo stato di un database con mirroring cambia.</span><span class="sxs-lookup"><span data-stu-id="1193d-115">Indicates when the state of a mirrored database changes.</span></span>|  
|[<span data-ttu-id="1193d-116">Classe di evento Database Suspect Data Page</span><span class="sxs-lookup"><span data-stu-id="1193d-116">Database Suspect Data Page Event Class</span></span>](database-suspect-data-page-event-class.md)|<span data-ttu-id="1193d-117">Indica quando una pagina viene aggiunta alla tabella **suspect_pages** nel database **msdb** .</span><span class="sxs-lookup"><span data-stu-id="1193d-117">Indicates when a page is added to the **suspect_pages** table in the **msdb** database.</span></span>|  
|[<span data-ttu-id="1193d-118">Classe di evento Log File Auto Grow</span><span class="sxs-lookup"><span data-stu-id="1193d-118">Log File Auto Grow Event Class</span></span>](log-file-auto-grow-event-class.md)|<span data-ttu-id="1193d-119">Indica che le dimensioni del file di log sono aumentate automaticamente.</span><span class="sxs-lookup"><span data-stu-id="1193d-119">Indicates that the log file grew automatically.</span></span> <span data-ttu-id="1193d-120">L'evento non viene generato se le dimensioni del file di log vengono incrementate in modo esplicito tramite ALTER DATABASE.</span><span class="sxs-lookup"><span data-stu-id="1193d-120">This event is not triggered if the log file is grown explicitly through ALTER DATABASE.</span></span>|  
|[<span data-ttu-id="1193d-121">Classe di evento Log File Auto Shrink</span><span class="sxs-lookup"><span data-stu-id="1193d-121">Log File Auto Shrink Event Class</span></span>](log-file-auto-shrink-event-class.md)|<span data-ttu-id="1193d-122">Indica che le dimensioni del file di log sono aumentate automaticamente.</span><span class="sxs-lookup"><span data-stu-id="1193d-122">Indicates that the log file grew automatically.</span></span> <span data-ttu-id="1193d-123">L'evento non viene generato se le dimensioni del file di log vengono ridotte in modo esplicito tramite ALTER DATABASE.</span><span class="sxs-lookup"><span data-stu-id="1193d-123">This event is not triggered if the log file shrinks explicitly through ALTER DATABASE.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1193d-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1193d-124">See Also</span></span>  
 [<span data-ttu-id="1193d-125">Eventi estesi</span><span class="sxs-lookup"><span data-stu-id="1193d-125">Extended Events</span></span>](../extended-events/extended-events.md)  
  
  
