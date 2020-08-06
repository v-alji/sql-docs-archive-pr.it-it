---
title: Verificare i problemi di ritardo di I/O nel sottosistema di I/O del disco | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 23863340-d8e0-48d6-928b-462745885d37
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: a0ae8dc0d1a93f8150ccbeab73ed8aa918d1f495
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715204"
---
# <a name="check-disk-input-and-output-subsystem-for-io-delay-problems"></a><span data-ttu-id="e1446-102">Verifica dei problemi di ritardo di I/O nel sottosistema di I/O del disco</span><span class="sxs-lookup"><span data-stu-id="e1446-102">Check Disk Input and Output Subsystem for IO Delay Problems</span></span>
  <span data-ttu-id="e1446-103">Questa regola consente di controllare il messaggio di errore 833 nel registro eventi.</span><span class="sxs-lookup"><span data-stu-id="e1446-103">This rule checks the event log for error message 833.</span></span> <span data-ttu-id="e1446-104">Questo messaggio indica che [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ha eseguito una richiesta di lettura o scrittura dal disco e che la durata dell'operazione è stata superiore a 15 secondi.</span><span class="sxs-lookup"><span data-stu-id="e1446-104">This message indicates that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has issued a read or write request from disk, and that the request has taken longer than 15 seconds to return.</span></span> <span data-ttu-id="e1446-105">Questo errore viene segnalato da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e indica un problema relativo al sottosistema di I/O.</span><span class="sxs-lookup"><span data-stu-id="e1446-105">This error is reported by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and indicates a problem with the disk I/O subsystem.</span></span> <span data-ttu-id="e1446-106">Ritardi così prolungati possono influire gravemente sulle prestazioni dell'ambiente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e1446-106">Delays this long can severely damage the performance of your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] environment.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="e1446-107">Procedure consigliate</span><span class="sxs-lookup"><span data-stu-id="e1446-107">Best Practices Recommendations</span></span>  
 <span data-ttu-id="e1446-108">Per risolvere il problema che ha causato questo errore, individuare nel registro eventi di sistema i messaggi di errore correlati all'hardware.</span><span class="sxs-lookup"><span data-stu-id="e1446-108">Troubleshoot this error by examining the system event log for hardware-related error messages.</span></span> <span data-ttu-id="e1446-109">Esaminare inoltre eventuali log specifici dei componenti hardware se disponibili.</span><span class="sxs-lookup"><span data-stu-id="e1446-109">Also, examine hardware-specific logs if they are available.</span></span>  
  
 <span data-ttu-id="e1446-110">Utilizzare Performance Monitor per esaminare i contatori seguenti:</span><span class="sxs-lookup"><span data-stu-id="e1446-110">Use Performance Monitor to examine the following counters:</span></span>  
  
-   <span data-ttu-id="e1446-111">Media secondi/trasf. disco</span><span class="sxs-lookup"><span data-stu-id="e1446-111">Average Disk Sec/Transfer</span></span>  
  
-   <span data-ttu-id="e1446-112">Lunghezza media coda del disco</span><span class="sxs-lookup"><span data-stu-id="e1446-112">Average Disk Queue Length</span></span>  
  
-   <span data-ttu-id="e1446-113">Lunghezza corrente coda del disco</span><span class="sxs-lookup"><span data-stu-id="e1446-113">Current Disk Queue Length</span></span>  
  
 <span data-ttu-id="e1446-114">Il valore della durata media, ad esempio, di Disco sec/trasferimento in un computer che esegue [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] è in genere inferiore a 15 millisecondi.</span><span class="sxs-lookup"><span data-stu-id="e1446-114">For example, the Average Disk Sec/Transfer time on a computer that is running [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is typically less than 15 milliseconds.</span></span> <span data-ttu-id="e1446-115">L'aumento di tale valore indica che il sottosistema di I/O del disco non è in grado di soddisfare in modo ottimale le richieste di I/O.</span><span class="sxs-lookup"><span data-stu-id="e1446-115">If the Average Disk Sec/Transfer value increases, this indicates that the disk I/O subsystem is not optimally keeping up with the I/O demand.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="e1446-116">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="e1446-116">For More Information</span></span>  
 [<span data-ttu-id="e1446-117">MSSQLSERVER_833</span><span class="sxs-lookup"><span data-stu-id="e1446-117">MSSQLSERVER_833</span></span>](../errors-events/mssqlserver-833-database-engine-error.md)  
  
 [<span data-ttu-id="e1446-118">Articolo 897284 della Microsoft Knowledge Base</span><span class="sxs-lookup"><span data-stu-id="e1446-118">Microsoft Knowledge Base article 897284</span></span>](https://go.microsoft.com/fwlink/?linkid=117743)  
  
 <span data-ttu-id="e1446-119">[SQL Server I/O Basics, Chapter 2](/previous-versions/sql/sql-server-2005/administrator/cc917726(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="e1446-119">[SQL Server I/O Basics, Chapter 2](/previous-versions/sql/sql-server-2005/administrator/cc917726(v=technet.10))</span></span>  
  
  
