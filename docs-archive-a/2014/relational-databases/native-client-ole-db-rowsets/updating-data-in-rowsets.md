---
title: Aggiornamento dei dati dei set di righe | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- updating data [SQL Server]
- rowsets [OLE DB], updating data
- SQL Server Native Client OLE DB provider, rowsets
- OLE DB rowsets, updating data
- SQL Server Native Client OLE DB provider, data updates
- data updates [SQL Server], OLE DB
ms.assetid: 37769b1c-c480-419a-8c54-5cc420bf73db
author: rothja
ms.author: jroth
ms.openlocfilehash: 993cfb67d4e6b72eec7cc0537e9b47371e94af10
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718089"
---
# <a name="updating-data-in-rowsets"></a><span data-ttu-id="3e126-102">Aggiornamento dei dati dei set di righe</span><span class="sxs-lookup"><span data-stu-id="3e126-102">Updating Data in Rowsets</span></span>
  <span data-ttu-id="3e126-103">Il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native Client aggiorna [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] i dati quando un consumer aggiorna un set di righe modificabile che contiene i dati.</span><span class="sxs-lookup"><span data-stu-id="3e126-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider updates [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data when a consumer updates a modifiable rowset that contains that data.</span></span> <span data-ttu-id="3e126-104">Un set di righe modificabile viene creato quando il consumer richiede il supporto per l'interfaccia **IRowsetChange** o **IRowsetUpdate**.</span><span class="sxs-lookup"><span data-stu-id="3e126-104">A modifiable rowset is created when the consumer requests support for either the **IRowsetChange** or **IRowsetUpdate** interface.</span></span>  
  
 <span data-ttu-id="3e126-105">Tutti i [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] set di righe modificabili dal provider di Native Client OLE DB utilizzano [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] i cursori per supportare il set di righe.</span><span class="sxs-lookup"><span data-stu-id="3e126-105">All [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider-modifiable rowsets use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cursors to support the rowset.</span></span> <span data-ttu-id="3e126-106">La proprietà del set di righe DBPROP_LOCKMODE modifica il comportamento di controllo della concorrenza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] nei cursori e determina il comportamento di recupero delle righe del set di righe e di generazione degli errori di integrità dei dati nei set di righe aggiornabili.</span><span class="sxs-lookup"><span data-stu-id="3e126-106">The rowset property DBPROP_LOCKMODE alters [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] concurrency control behavior in cursors and determines the behavior of rowset row fetching and data integrity error generation in updatable rowsets.</span></span>  
  
 <span data-ttu-id="3e126-107">Il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native Client supporta la sincronizzazione delle righe prima o dopo un aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="3e126-107">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider supports row synchronization before or after an update.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3e126-108">IRowChange::SetColumns è disponibile per l'impostazione dei valori di una o più colonne denominate di un oggetto riga.</span><span class="sxs-lookup"><span data-stu-id="3e126-108">IRowChange::SetColumns is available to set the values of one or more named columns of a row object.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3e126-109">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="3e126-109">In This Section</span></span>  
  
-   [<span data-ttu-id="3e126-110">Aggiornamento dei dati nei cursori di SQL Server</span><span class="sxs-lookup"><span data-stu-id="3e126-110">Updating Data in SQL Server Cursors</span></span>](updating-data-in-sql-server-cursors.md)  
  
-   [<span data-ttu-id="3e126-111">Risincronizzazione delle righe</span><span class="sxs-lookup"><span data-stu-id="3e126-111">Resynchronizing Rows</span></span>](updating-data-in-rowsets-resynchronizing-rows.md)  
  
## <a name="see-also"></a><span data-ttu-id="3e126-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3e126-112">See Also</span></span>  
 [<span data-ttu-id="3e126-113">Set di righe</span><span class="sxs-lookup"><span data-stu-id="3e126-113">Rowsets</span></span>](rowsets.md)  
  
  
