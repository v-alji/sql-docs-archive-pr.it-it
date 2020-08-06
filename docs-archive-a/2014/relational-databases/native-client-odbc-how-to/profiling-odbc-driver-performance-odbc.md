---
title: Procedure per la profilatura delle prestazioni del driver ODBC (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
ms.assetid: 0e6d7aed-28d2-419e-be6a-f60d3729bfd0
author: rothja
ms.author: jroth
ms.openlocfilehash: d27547862138b511a4defaa3cae80f48f69fdc4f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624133"
---
# <a name="profiling-odbc-driver-performance-how-to-topics-odbc"></a><span data-ttu-id="0ec05-102">Procedure di analisi delle prestazioni del driver ODBC (ODBC)</span><span class="sxs-lookup"><span data-stu-id="0ec05-102">Profiling ODBC Driver Performance How-to Topics (ODBC)</span></span>
  <span data-ttu-id="0ec05-103">Sono disponibili due opzioni specifiche che possono essere utilizzate dal driver ODBC di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per l'analisi delle prestazioni del driver.</span><span class="sxs-lookup"><span data-stu-id="0ec05-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ODBC driver has two driver-specific options for profiling the performance of the driver.</span></span>  
  
 <span data-ttu-id="0ec05-104">Il driver ODBC di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] può registrare statistiche sulle prestazioni nei file.</span><span class="sxs-lookup"><span data-stu-id="0ec05-104">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ODBC driver can log performance statistics in file.</span></span> <span data-ttu-id="0ec05-105">Il file di log delle statistiche è un file delimitato da tabulazioni che può essere analizzato in qualsiasi foglio di calcolo in grado di supportare i file delimitati da tabulazioni, come Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="0ec05-105">The log file is a tab-delimited file that can be analyzed in any spreadsheet supporting tab-delimited files, such as Microsoft Excel.</span></span>  
  
 <span data-ttu-id="0ec05-106">Il driver può registrare anche query con esecuzione prolungata (query che non ottengono una risposta dal server entro un periodo di tempo specificato).</span><span class="sxs-lookup"><span data-stu-id="0ec05-106">The driver can also log long-running queries (queries that do not get a response from the server in a specified length of time).</span></span> <span data-ttu-id="0ec05-107">Tali query possono essere analizzate in un secondo momento da programmatori e amministratori del database.</span><span class="sxs-lookup"><span data-stu-id="0ec05-107">These queries can later be analyzed by programmers and database administrators.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0ec05-108">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="0ec05-108">In This Section</span></span>  
  
-   [<span data-ttu-id="0ec05-109">Dati sulle prestazioni del driver del profilo &#40;&#41;ODBC</span><span class="sxs-lookup"><span data-stu-id="0ec05-109">Profile Driver Performance Data &#40;ODBC&#41;</span></span>](profiling-odbc-driver-performance-data.md)  
  
-   [<span data-ttu-id="0ec05-110">Registrare query con esecuzione prolungata &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="0ec05-110">Log Long-Running Queries &#40;ODBC&#41;</span></span>](profiling-odbc-driver-performance-data-log-long-running-queries.md)  
  
## <a name="see-also"></a><span data-ttu-id="0ec05-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0ec05-111">See Also</span></span>  
 [<span data-ttu-id="0ec05-112">Procedure per l'utilizzo di ODBC</span><span class="sxs-lookup"><span data-stu-id="0ec05-112">ODBC How-to Topics</span></span>](odbc-how-to-topics.md)  
  
  
