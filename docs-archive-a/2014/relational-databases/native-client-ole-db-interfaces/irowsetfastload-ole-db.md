---
title: IRowsetFastLoad (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- IRowsetFastLoad interface
ms.assetid: d19a7097-48d9-409a-aff9-277891b7aca7
author: rothja
ms.author: jroth
ms.openlocfilehash: 7ecf72f0015d9ed197b3b7a33d4f9bb3246134b1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636693"
---
# <a name="irowsetfastload-ole-db"></a><span data-ttu-id="90729-102">IRowsetFastLoad (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="90729-102">IRowsetFastLoad (OLE DB)</span></span>
  <span data-ttu-id="90729-103">L' `IRowsetFastLoad` interfaccia espone il supporto per [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] le operazioni di copia bulk basate sulla memoria.</span><span class="sxs-lookup"><span data-stu-id="90729-103">The `IRowsetFastLoad` interface exposes support for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] memory-based bulk-copy operations.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="90729-104">I consumer del provider OLE DB di Native client utilizzano l'interfaccia per aggiungere rapidamente dati a una [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tabella esistente.</span><span class="sxs-lookup"><span data-stu-id="90729-104">Native Client OLE DB provider consumers use the interface to rapidly add data to an existing [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span>  
  
 <span data-ttu-id="90729-105">Se si imposta SSPROP_ENABLEFASTLOAD su VARIANT_TRUE per una sessione, non è possibile leggere dati dai set di righe restituiti successivamente dalla sessione.</span><span class="sxs-lookup"><span data-stu-id="90729-105">If you set SSPROP_ENABLEFASTLOAD to VARIANT_TRUE for a session, you cannot read data from rowsets subsequently returned from that session.</span></span> <span data-ttu-id="90729-106">Quando SSPROP_ENABLEFASTLOAD è impostato su VARIANT_TRUE, tutti i set di righe creati nella sessione saranno del tipo IRowsetFastLoad.</span><span class="sxs-lookup"><span data-stu-id="90729-106">When SSPROP_ENABLEFASTLOAD is set to VARIANT_TRUE, all rowsets created on the session will be of type IRowsetFastLoad.</span></span> <span data-ttu-id="90729-107">I set di righe IRowsetFastLoad non supportano la funzionalità di recupero del set di righe, quindi non è possibile leggere i set di righe.</span><span class="sxs-lookup"><span data-stu-id="90729-107">IRowsetFastLoad rowsets do not support rowset fetch functionality; therefore, data from these rowsets cannot be read.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="90729-108">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="90729-108">In This Section</span></span>  
  
|<span data-ttu-id="90729-109">Metodo</span><span class="sxs-lookup"><span data-stu-id="90729-109">Method</span></span>|<span data-ttu-id="90729-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="90729-110">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="90729-111">IRowsetFastLoad::Commit &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="90729-111">IRowsetFastLoad::Commit &#40;OLE DB&#41;</span></span>](irowsetfastload-commit-ole-db.md)|<span data-ttu-id="90729-112">Contrassegna la fine di un batch di righe inserite e scrive le righe nella tabella di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="90729-112">Marks the end of a batch of inserted rows and writes the rows to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span>|  
|[<span data-ttu-id="90729-113">IRowsetFastLoad::InsertRow &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="90729-113">IRowsetFastLoad::InsertRow &#40;OLE DB&#41;</span></span>](irowsetfastload-insertrow-ole-db.md)|<span data-ttu-id="90729-114">Aggiunge una riga al set di righe della copia bulk.</span><span class="sxs-lookup"><span data-stu-id="90729-114">Adds a row to the bulk copy rowset.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="90729-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="90729-115">See Also</span></span>  
 <span data-ttu-id="90729-116">[Interfacce &#40;OLE DB&#41;](../../database-engine/dev-guide/interfaces-ole-db.md) </span><span class="sxs-lookup"><span data-stu-id="90729-116">[Interfaces &#40;OLE DB&#41;](../../database-engine/dev-guide/interfaces-ole-db.md) </span></span>  
 <span data-ttu-id="90729-117">[Copia dati bulk con IRowsetFastLoad &#40;OLE DB&#41;](../native-client-ole-db-how-to/bulk-copy-data-using-irowsetfastload-ole-db.md) </span><span class="sxs-lookup"><span data-stu-id="90729-117">[Bulk Copy Data Using IRowsetFastLoad &#40;OLE DB&#41;](../native-client-ole-db-how-to/bulk-copy-data-using-irowsetfastload-ole-db.md) </span></span>  
 [<span data-ttu-id="90729-118">Inviare dati BLOB a SQL Server usando IROWSETFASTLOAD e ISEQUENTIALSTREAM &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="90729-118">Send BLOB Data to SQL SERVER Using IROWSETFASTLOAD and ISEQUENTIALSTREAM &#40;OLE DB&#41;</span></span>](../native-client-ole-db-how-to/send-blob-data-to-sql-server-using-irowsetfastload-and-isequentialstream-ole-db.md)  
  
  
