---
title: Parametri con valori di tabella (SQL Server Native Client) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client, table-valued parameters
- table-valued parameters (SQL Server Native Client)
ms.assetid: 5ee6bdcd-0309-4a20-b5c2-0e6b6839f34f
author: rothja
ms.author: jroth
ms.openlocfilehash: 6af4979b9a77c94f52be5197b01179007a971283
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625365"
---
# <a name="table-valued-parameters-sql-server-native-client"></a><span data-ttu-id="b2a02-102">Parametri con valori di tabella (SQL Server Native Client)</span><span class="sxs-lookup"><span data-stu-id="b2a02-102">Table-Valued Parameters (SQL Server Native Client)</span></span>
  <span data-ttu-id="b2a02-103">I parametri con valori di tabella sono stati introdotti in [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)] e offrono una modalità efficiente per passare più righe di dati al server.</span><span class="sxs-lookup"><span data-stu-id="b2a02-103">Table-valued parameters were introduced in [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)], and provide an efficient way to pass multiple rows of data to the server.</span></span> <span data-ttu-id="b2a02-104">Tali parametri offrono funzionalità simili a quelle delle matrici di parametri, ma garantiscono una maggiore flessibilità e integrazione con [!INCLUDE[tsql](../../../includes/tsql-md.md)] e spesso anche prestazioni migliori.</span><span class="sxs-lookup"><span data-stu-id="b2a02-104">Table-valued parameters provide functionality similar to parameter arrays, but they offer more flexibility and closer integration with [!INCLUDE[tsql](../../../includes/tsql-md.md)], and can frequently improve performance.</span></span> <span data-ttu-id="b2a02-105">Diversamente dalle matrici di parametri, i parametri con valori di tabella possono anche partecipare alle operazioni basate su set.</span><span class="sxs-lookup"><span data-stu-id="b2a02-105">Table-valued parameters can also participate in set-based operations, whereas parameter arrays cannot.</span></span>  
  
 <span data-ttu-id="b2a02-106">Per informazioni sui parametri con valori di tabella e ODBC, vedere [parametri con valori di tabella &#40;&#41;ODBC ](../../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="b2a02-106">For information about table-valued parameters and ODBC, see [Table-Valued Parameters &#40;ODBC&#41;](../../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span></span>  
  
 <span data-ttu-id="b2a02-107">Per informazioni sui parametri con valori di tabella e OLE DB, vedere [Parametri con valori di tabella &#40;OLE DB&#41;](../../native-client-ole-db-table-valued-parameters/table-valued-parameters-ole-db.md).</span><span class="sxs-lookup"><span data-stu-id="b2a02-107">For information about table-valued parameters and OLE DB, see [Table-Valued Parameters &#40;OLE DB&#41;](../../native-client-ole-db-table-valued-parameters/table-valued-parameters-ole-db.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2a02-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b2a02-108">See Also</span></span>  
 [<span data-ttu-id="b2a02-109">Funzionalità di SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="b2a02-109">SQL Server Native Client Features</span></span>](sql-server-native-client-features.md)  
  
  
