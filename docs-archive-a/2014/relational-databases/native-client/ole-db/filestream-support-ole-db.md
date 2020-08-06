---
title: Supporto FILESTREAM (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- OLE DB [FILESTREAM support]
- FILESTREAM [SQL Server], OLE DB
ms.assetid: c2bd3dfd-6103-43d1-859e-8ed8d19c58d3
author: rothja
ms.author: jroth
ms.openlocfilehash: cde3c2cd1b72773cfcf17eacedeb3276dd2f63da
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635002"
---
# <a name="filestream-support-ole-db"></a><span data-ttu-id="89a89-102">Supporto FILESTREAM (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="89a89-102">FILESTREAM Support (OLE DB)</span></span>
  <span data-ttu-id="89a89-103">A partire da [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)] e [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client 10,0, OLE DB supporta la funzionalità FILESTREAM avanzata.</span><span class="sxs-lookup"><span data-stu-id="89a89-103">Beginning with [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)] and [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client 10.0, OLE DB supports the enhanced FILESTREAM feature.</span></span> <span data-ttu-id="89a89-104">Per ulteriori informazioni su questa funzionalità, vedere [supporto FILESTREAM](../features/filestream-support.md).</span><span class="sxs-lookup"><span data-stu-id="89a89-104">For more information about this feature, see [FILESTREAM Support](../features/filestream-support.md).</span></span> <span data-ttu-id="89a89-105">Per gli esempi, vedere [FILESTREAM e OLE DB](../../native-client-ole-db-how-to/filestream/filestream-and-ole-db.md).</span><span class="sxs-lookup"><span data-stu-id="89a89-105">For samples, see [Filestream and OLE DB](../../native-client-ole-db-how-to/filestream/filestream-and-ole-db.md).</span></span>  
  
 <span data-ttu-id="89a89-106">Per inviare e ricevere valori `varbinary(max)` maggiori di 2 GB, un'applicazione utilizza `DBTYPE_IUNKNOWN` in associazioni di parametri e di risultati.</span><span class="sxs-lookup"><span data-stu-id="89a89-106">To send and receive `varbinary(max)` values greater than 2 GB, an application uses `DBTYPE_IUNKNOWN` in parameter and result bindings.</span></span> <span data-ttu-id="89a89-107">Per i parametri il provider deve chiamare IUnknown::QueryInterface per ISequentialStream e per i risultati che restituiscono ISequentialStream.</span><span class="sxs-lookup"><span data-stu-id="89a89-107">For parameters the provider must call IUnknown::QueryInterface for ISequentialStream and for results that return ISequentialStream.</span></span>  
  
 <span data-ttu-id="89a89-108">Per OLE DB il controllo relativo ai valori ISequentialStream diventa meno rigido.</span><span class="sxs-lookup"><span data-stu-id="89a89-108">For OLE DB, checking related to ISequentialStream values will be relaxed.</span></span> <span data-ttu-id="89a89-109">Quando *wType* è `DBTYPE_IUNKNOWN` nello `DBBINDING` struct, il controllo della lunghezza può essere disabilitato omettendo `DBPART_LENGTH` da *dwPart* o impostando la lunghezza dei dati (in corrispondenza dell'offset *obLength* nel buffer di dati) su ~ 0.</span><span class="sxs-lookup"><span data-stu-id="89a89-109">When *wType* is `DBTYPE_IUNKNOWN` in the `DBBINDING` struct, length checking can be disabled either by omitting `DBPART_LENGTH` from *dwPart* or by setting the length of the data (at offset *obLength* in the data buffer) to ~0.</span></span> <span data-ttu-id="89a89-110">In questo caso, il provider non controllerà la lunghezza del valore e richiederà e restituirà tutti i dati disponibili tramite il flusso.</span><span class="sxs-lookup"><span data-stu-id="89a89-110">In this case, the provider will not check the length of the value and will request and return all of the data available through the stream.</span></span> <span data-ttu-id="89a89-111">Questa modifica verrà applicata a tutti i tipi LOB (Large Object) e XML, ma solo in caso di connessione a server [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="89a89-111">This change will be applied to all large object (LOB) types and XML, but only when connected to [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] (or later) servers.</span></span> <span data-ttu-id="89a89-112">In questo modo, gli sviluppatori disporranno di maggiore flessibilità, mantenendo la coerenza e la compatibilità con le versioni precedenti per applicazioni esistenti e server legacy.</span><span class="sxs-lookup"><span data-stu-id="89a89-112">This will provide greater flexibility for developers, while maintaining consistency and backwards compatibility for existing applications and downlevel servers.</span></span>  
  
 <span data-ttu-id="89a89-113">Questa modifica ha effetto su tutte le interfacce che trasferiscono dati, principalmente IRowset::GetData, ICommand::Execute e IRowsetFastLoad::InsertRow.</span><span class="sxs-lookup"><span data-stu-id="89a89-113">This change affects all interfaces that transfer data, principally IRowset::GetData, ICommand::Execute, and IRowsetFastLoad::InsertRow.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89a89-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="89a89-114">See Also</span></span>  
 [<span data-ttu-id="89a89-115">Programmazione in SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="89a89-115">SQL Server Native Client Programming</span></span>](../sql-server-native-client-programming.md)  
  
  
