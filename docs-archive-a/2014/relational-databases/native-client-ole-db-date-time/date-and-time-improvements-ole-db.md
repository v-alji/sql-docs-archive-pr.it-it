---
title: Miglioramenti relativi a data e ora (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- date/time [OLE DB]
- OLE DB, date/time improvements
ms.assetid: 71614aaf-0fa4-4fe0-b522-68e2e0b66f43
author: rothja
ms.author: jroth
ms.openlocfilehash: 16bb9e98691aea829eb71a16ddabddb371d7bcf3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723803"
---
# <a name="date-and-time-improvements-ole-db"></a><span data-ttu-id="e715f-102">Miglioramenti relativi a data e ora (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="e715f-102">Date and Time Improvements (OLE DB)</span></span>
  <span data-ttu-id="e715f-103">In [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] sono stati introdotti nuovi tipi di dati di data e ora.</span><span class="sxs-lookup"><span data-stu-id="e715f-103">[!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] introduces new date and time data types.</span></span> <span data-ttu-id="e715f-104">In questa sezione viene descritto il modo in cui questi nuovi tipi vengono esposti come estensioni in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="e715f-104">This section describes how these new types are exposed as extensions in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span></span> <span data-ttu-id="e715f-105">Per una panoramica del [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] supporto di Native Client per i nuovi tipi di dati di data e ora, vedere [miglioramenti di data e ora](../native-client/features/date-and-time-improvements.md).</span><span class="sxs-lookup"><span data-stu-id="e715f-105">For an overview of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client support for the new date and time data types, see [Date and Time Improvements](../native-client/features/date-and-time-improvements.md).</span></span> <span data-ttu-id="e715f-106">Per un esempio, vedere [Usare le funzionalità avanzate di data e ora &#40;OLE DB&#41;](../native-client-ole-db-how-to/use-enhanced-date-and-time-features-ole-db.md).</span><span class="sxs-lookup"><span data-stu-id="e715f-106">For a sample, see [Use Enhanced Date and Time Features &#40;OLE DB&#41;](../native-client-ole-db-how-to/use-enhanced-date-and-time-features-ole-db.md).</span></span>  
  
 <span data-ttu-id="e715f-107">Per altre informazioni generali sui tipi di dati di data e ora, vedere [datetime &#40;Transact-SQL&#41;](/sql/t-sql/data-types/datetime-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e715f-107">For more general information about date and time data types, see [datetime &#40;Transact-SQL&#41;](/sql/t-sql/data-types/datetime-transact-sql).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e715f-108">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="e715f-108">In This Section</span></span>  
 [<span data-ttu-id="e715f-109">Supporto dei tipi di dati per i miglioramenti relativi a data e ora OLE DB</span><span class="sxs-lookup"><span data-stu-id="e715f-109">Data Type Support for OLE DB Date and Time Improvements</span></span>](../../relational-databases/native-client-ole-db-date-time/data-type-support-for-ole-db-date-and-time-improvements.md)  
 <span data-ttu-id="e715f-110">Vengono fornite informazioni sui tipi OLE DB ( [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client) che supportano [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] i tipi di dati di data e ora.</span><span class="sxs-lookup"><span data-stu-id="e715f-110">Provides information about OLE DB ([!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client) types that support [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] date and time data types.</span></span>  
  
 [<span data-ttu-id="e715f-111">Metadati &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="e715f-111">Metadata &#40;OLE DB&#41;</span></span>](../../database-engine/dev-guide/metadata-ole-db.md)  
 <span data-ttu-id="e715f-112">Contiene informazioni sulla struttura DBBINDING,, `ICommandWithParameters::GetParameterInfo` , `ICommandWithParameters::SetParameterInfo` `IColumnsRowset::GetColumnsRowset` e i `ColumnsInfo::GetColumnInfo` . Vengono inoltre fornite informazioni sugli aggiornamenti dei set di righe dello schema OLE DB.</span><span class="sxs-lookup"><span data-stu-id="e715f-112">Contains information about the DBBINDING structure, `ICommandWithParameters::GetParameterInfo`, `ICommandWithParameters::SetParameterInfo`, `IColumnsRowset::GetColumnsRowset`, and I`ColumnsInfo::GetColumnInfo`. Also provides information about updates to OLE DB schema rowsets.</span></span>  
  
 [<span data-ttu-id="e715f-113">Associazioni e conversioni &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="e715f-113">Bindings and Conversions &#40;OLE DB&#41;</span></span>](../../relational-databases/native-client-ole-db-date-time/conversions-ole-db.md)  
 <span data-ttu-id="e715f-114">Vengono illustrate le regole per la conversione fra server e client per tipi di dati sia nuovi che esistenti.</span><span class="sxs-lookup"><span data-stu-id="e715f-114">Describes the rules for conversion between server and client for both existing and new date types.</span></span>  
  
 [<span data-ttu-id="e715f-115">Modifiche della copia bulk per i tipi di data e ora avanzati &#40;OLE DB e ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="e715f-115">Bulk Copy Changes for Enhanced Date and Time Types &#40;OLE DB and ODBC&#41;</span></span>](../../relational-databases/native-client-odbc-date-time/bulk-copy-changes-for-enhanced-date-and-time-types-ole-db-and-odbc.md)  
 <span data-ttu-id="e715f-116">Vengono descritti i miglioramenti apportati ai tipi di data/ora per supportare le operazioni di copia bulk.</span><span class="sxs-lookup"><span data-stu-id="e715f-116">Describes date/time enhancements to support bulk copy operations.</span></span>  
  
 [<span data-ttu-id="e715f-117">Supporto dell'API OLE DB per i miglioramenti relativi a data e ora</span><span class="sxs-lookup"><span data-stu-id="e715f-117">OLE DB API Support for Date and Time Enhancements</span></span>](ole-db-api-support-for-date-and-time-enhancements.md)  
 <span data-ttu-id="e715f-118">Vengono descritte le API OLE DB che supportano le caratteristiche avanzate dei tipi di dati date/time.</span><span class="sxs-lookup"><span data-stu-id="e715f-118">Describes the OLE DB APIs that support enhanced date/time features.</span></span>  
  
 [<span data-ttu-id="e715f-119">Possibilità di confronto per IRowsetFind</span><span class="sxs-lookup"><span data-stu-id="e715f-119">Comparability for IRowsetFind</span></span>](../../relational-databases/native-client-ole-db-date-time/comparability-for-irowsetfind.md)  
 <span data-ttu-id="e715f-120">Vengono descritti i tipi date/time e `IRowsetFind`.</span><span class="sxs-lookup"><span data-stu-id="e715f-120">Describes date/time types and `IRowsetFind`.</span></span>  
  
 [<span data-ttu-id="e715f-121">Nuove funzionalità di data e ora con versioni precedenti di SQL Server &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="e715f-121">New Date and Time Features with Previous SQL Server Versions &#40;OLE DB&#41;</span></span>](new-date-and-time-features-with-previous-sql-server-versions-ole-db.md)  
 <span data-ttu-id="e715f-122">Viene descritto il comportamento previsto quando un'applicazione client che utilizza le caratteristiche avanzate dei tipi date e time comunica con una versione precedente di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e quando un client compilato con una versione precedente di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client invia comandi a un server che supporta tali caratteristiche avanzate.</span><span class="sxs-lookup"><span data-stu-id="e715f-122">Describes the expected behavior when a client application that uses enhanced date and time features communicates with an older version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], and when a client compiled with an older version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client sends commands to a server that supports enhanced date and time features.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e715f-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e715f-123">See Also</span></span>  
 [<span data-ttu-id="e715f-124">SQL Server Native Client &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="e715f-124">SQL Server Native Client &#40;OLE DB&#41;</span></span>](../../relational-databases/native-client/ole-db/sql-server-native-client-ole-db.md)  
  
  
