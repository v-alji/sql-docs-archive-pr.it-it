---
title: Supporto dell'API OLE DB per i miglioramenti relativi a data e ora | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- OLE DB, date/time improvements
ms.assetid: e65c9253-bd99-4dc3-9cb8-7613f754c966
author: rothja
ms.author: jroth
ms.openlocfilehash: cdb17f0d2104373ea797ff9403cc417dfaa3d868
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636061"
---
# <a name="ole-db-api-support-for-date-and-time-enhancements"></a><span data-ttu-id="4c1bf-102">Supporto dell'API OLE DB per i miglioramenti relativi a data e ora</span><span class="sxs-lookup"><span data-stu-id="4c1bf-102">OLE DB API Support for Date and Time Enhancements</span></span>
  <span data-ttu-id="4c1bf-103">Le caratteristiche avanzate di data e ora sono supportate dalle seguenti API OLE DB.</span><span class="sxs-lookup"><span data-stu-id="4c1bf-103">The following OLE DB APIs support enhanced date/time features.</span></span>  
  
|<span data-ttu-id="4c1bf-104">Funzione</span><span class="sxs-lookup"><span data-stu-id="4c1bf-104">Function</span></span>|<span data-ttu-id="4c1bf-105">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4c1bf-105">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="4c1bf-106">IAccessor::CreateAccessor</span><span class="sxs-lookup"><span data-stu-id="4c1bf-106">IAccessor::CreateAccessor</span></span>|<span data-ttu-id="4c1bf-107">Un flag viene aggiunto nella struttura DBBINDING per consentire alle applicazioni di distinguere tra i valori `datetime`, `datetime2` e `smalldatetime`.</span><span class="sxs-lookup"><span data-stu-id="4c1bf-107">A flag is added in the DBBINDING structure to enable applications to discriminate between `datetime`, `datetime2`, and `smalldatetime` values.</span></span> <span data-ttu-id="4c1bf-108">Per altre informazioni, vedere [Metadati per parametri e set di righe](metadata-parameter-and-rowset.md).</span><span class="sxs-lookup"><span data-stu-id="4c1bf-108">For more information, see [Parameter and Rowset Metadata](metadata-parameter-and-rowset.md).</span></span>|  
|<span data-ttu-id="4c1bf-109">IBCPSession::BCPColFmt</span><span class="sxs-lookup"><span data-stu-id="4c1bf-109">IBCPSession::BCPColFmt</span></span>|<span data-ttu-id="4c1bf-110">Per ulteriori informazioni, vedere la pagina relativa alle [modifiche di copia bulk per i tipi di data e ora avanzati &#40;OLE DB e&#41;ODBC ](../native-client-odbc-date-time/bulk-copy-changes-for-enhanced-date-and-time-types-ole-db-and-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="4c1bf-110">For more information, see [Bulk Copy Changes for Enhanced Date and Time Types &#40;OLE DB and ODBC&#41;](../native-client-odbc-date-time/bulk-copy-changes-for-enhanced-date-and-time-types-ole-db-and-odbc.md).</span></span>|  
|<span data-ttu-id="4c1bf-111">ICommandWithParameters::GetParameterInfo</span><span class="sxs-lookup"><span data-stu-id="4c1bf-111">ICommandWithParameters::GetParameterInfo</span></span>|<span data-ttu-id="4c1bf-112">Per altre informazioni, vedere [Metadati per parametri e set di righe](metadata-parameter-and-rowset.md).</span><span class="sxs-lookup"><span data-stu-id="4c1bf-112">For more information, see[Parameter and Rowset Metadata](metadata-parameter-and-rowset.md).</span></span>|  
|<span data-ttu-id="4c1bf-113">ICommandWithParameters::SetParameterinfo</span><span class="sxs-lookup"><span data-stu-id="4c1bf-113">ICommandWithParameters::SetParameterinfo</span></span>|<span data-ttu-id="4c1bf-114">Per altre informazioni, vedere [Metadati per parametri e set di righe](metadata-parameter-and-rowset.md).</span><span class="sxs-lookup"><span data-stu-id="4c1bf-114">For more information, see[Parameter and Rowset Metadata](metadata-parameter-and-rowset.md).</span></span>|  
|<span data-ttu-id="4c1bf-115">IColumnsRowset::GetColumnsRowset</span><span class="sxs-lookup"><span data-stu-id="4c1bf-115">IColumnsRowset::GetColumnsRowset</span></span>|<span data-ttu-id="4c1bf-116">Per altre informazioni, vedere [Metadati per parametri e set di righe](metadata-parameter-and-rowset.md).</span><span class="sxs-lookup"><span data-stu-id="4c1bf-116">For more information, see[Parameter and Rowset Metadata](metadata-parameter-and-rowset.md).</span></span>|  
|<span data-ttu-id="4c1bf-117">IColumnsInfo::GetColumnInfo</span><span class="sxs-lookup"><span data-stu-id="4c1bf-117">IColumnsInfo::GetColumnInfo</span></span>|<span data-ttu-id="4c1bf-118">Per altre informazioni, vedere [Metadati per parametri e set di righe](metadata-parameter-and-rowset.md).</span><span class="sxs-lookup"><span data-stu-id="4c1bf-118">For more information, see[Parameter and Rowset Metadata](metadata-parameter-and-rowset.md).</span></span>|  
|<span data-ttu-id="4c1bf-119">IDBSchemaRowset::GetRowset</span><span class="sxs-lookup"><span data-stu-id="4c1bf-119">IDBSchemaRowset::GetRowset</span></span>|<span data-ttu-id="4c1bf-120">Per informazioni dettagliate sui set di righe dello schema interessati, vedere[Set di righe dello schema e dei tipi Date e Time](../native-client-ole-db-rowsets/rowsets.md).</span><span class="sxs-lookup"><span data-stu-id="4c1bf-120">For details of the affected schema rowsets, see[Date and Time and Schema Rowsets](../native-client-ole-db-rowsets/rowsets.md).</span></span>|  
|<span data-ttu-id="4c1bf-121">IRowsetFastLoad</span><span class="sxs-lookup"><span data-stu-id="4c1bf-121">IRowsetFastLoad</span></span>|<span data-ttu-id="4c1bf-122">Questa interfaccia supporta i nuovi tipi di data/ora, ma non è stata apportata alcuna modifica all'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="4c1bf-122">This interface supports the new date/time types, but there is no change to its interface.</span></span>|  
|<span data-ttu-id="4c1bf-123">ITableDefinition::CreateTable</span><span class="sxs-lookup"><span data-stu-id="4c1bf-123">ITableDefinition::CreateTable</span></span>|<span data-ttu-id="4c1bf-124">Per altre informazioni, vedere [Supporto dei tipi di dati per i miglioramenti relativi a data e ora OLE DB](data-type-support-for-ole-db-date-and-time-improvements.md).</span><span class="sxs-lookup"><span data-stu-id="4c1bf-124">For more information, see [Data Type Support for OLE DB Date and Time Improvements](data-type-support-for-ole-db-date-and-time-improvements.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4c1bf-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4c1bf-125">See Also</span></span>  
 [<span data-ttu-id="4c1bf-126">Miglioramenti relativi a data e ora &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="4c1bf-126">Date and Time Improvements &#40;OLE DB&#41;</span></span>](date-and-time-improvements-ole-db.md)  
  
  
