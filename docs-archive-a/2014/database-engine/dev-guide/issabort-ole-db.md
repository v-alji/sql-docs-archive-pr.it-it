---
title: Sasabot (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- ISSAbort interface
ms.assetid: 7c4df482-4a83-4da0-802b-3637b507693a
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 7195311fefe3f0f1b7b4d6d789aa8d8487bc3bfe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726167"
---
# <a name="issabort-ole-db"></a><span data-ttu-id="92c08-102">ISSAbort (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="92c08-102">ISSAbort (OLE DB)</span></span>
  <span data-ttu-id="92c08-103">L'interfaccia **ISSAbort** , esposta nel provider OLE DB di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client, fornisce il metodo [ISSAbort::Abort](../../relational-databases/native-client-ole-db-interfaces/issabort-abort-ole-db.md) che viene utilizzato per annullare il set di righe corrente oltre a qualsiasi comando eseguito in batch insieme al comando che ha inizialmente generato il set di righe e non ha ancora completato l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="92c08-103">The **ISSAbort** interface, which is exposed in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider, provides the [ISSAbort::Abort](../../relational-databases/native-client-ole-db-interfaces/issabort-abort-ole-db.md) method that is used to cancel the current rowset plus any commands batched with the command that initially generated the rowset, and that have not yet completed execution.</span></span>  
  
 <span data-ttu-id="92c08-104">**ISSAbort** è un'interfaccia specifica del provider di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client disponibile mediante **QueryInterface** sull'oggetto **IMultipleResults** restituito da **ICommand::Execute** o **IOpenRowset::OpenRowset**.</span><span class="sxs-lookup"><span data-stu-id="92c08-104">**ISSAbort** is a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client provider-specific interface available by using **QueryInterface** on the **IMultipleResults** object returned by **ICommand::Execute** or **IOpenRowset::OpenRowset**.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="92c08-105">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="92c08-105">In This Section</span></span>  
  
|<span data-ttu-id="92c08-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="92c08-106">Method</span></span>|<span data-ttu-id="92c08-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="92c08-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="92c08-108">Dissabot:: Abort &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="92c08-108">ISSAbort::Abort &#40;OLE DB&#41;</span></span>](../../relational-databases/native-client-ole-db-interfaces/issabort-abort-ole-db.md)|<span data-ttu-id="92c08-109">Annulla il set di righe corrente oltre a qualsiasi comando eseguito in batch associato al comando corrente.</span><span class="sxs-lookup"><span data-stu-id="92c08-109">Cancels the current rowset plus any batched commands associated with the current command.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="92c08-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="92c08-110">See Also</span></span>  
 [<span data-ttu-id="92c08-111">Interfacce &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="92c08-111">Interfaces &#40;OLE DB&#41;</span></span>](../../../2014/database-engine/dev-guide/interfaces-ole-db.md)  
  
  
