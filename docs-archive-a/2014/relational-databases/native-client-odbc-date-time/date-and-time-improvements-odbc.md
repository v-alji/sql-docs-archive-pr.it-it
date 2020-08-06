---
title: Miglioramenti di data e ora (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- date/time [ODBC]
- ODBC, date/time improvements
ms.assetid: e31d5ca5-2103-498f-954c-1ee93e217186
author: rothja
ms.author: jroth
ms.openlocfilehash: 6ce8f906fc1949a80bfa8e5a541ecf1e83878775
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628645"
---
# <a name="date-and-time-improvements-odbc"></a><span data-ttu-id="3e0a1-102">Miglioramenti relativi a data e ora (ODBC)</span><span class="sxs-lookup"><span data-stu-id="3e0a1-102">Date and Time Improvements (ODBC)</span></span>
  <span data-ttu-id="3e0a1-103">In [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] sono stati introdotti nuovi tipi di dati di data e ora.</span><span class="sxs-lookup"><span data-stu-id="3e0a1-103">[!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] introduced new date and time data types.</span></span> <span data-ttu-id="3e0a1-104">In questa sezione viene descritto il modo in cui questi nuovi tipi vengono esposti come estensioni in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="3e0a1-104">This section describes how these new types are exposed as extensions in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span></span> <span data-ttu-id="3e0a1-105">Per una panoramica del [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] supporto di Native Client per i nuovi tipi di dati di data e ora, vedere [miglioramenti di data e ora](../native-client/features/date-and-time-improvements.md).</span><span class="sxs-lookup"><span data-stu-id="3e0a1-105">For an overview of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client support for the new date and time data types, see [Date and Time Improvements](../native-client/features/date-and-time-improvements.md).</span></span> <span data-ttu-id="3e0a1-106">Per un esempio che illustra il supporto ODBC per data/ora, vedere [usare i tipi di data e ora](../native-client-odbc-how-to/use-date-and-time-types.md).</span><span class="sxs-lookup"><span data-stu-id="3e0a1-106">For a sample demonstrating ODBC date/time support, see [Use Date and Time Types](../native-client-odbc-how-to/use-date-and-time-types.md).</span></span>  
  
 <span data-ttu-id="3e0a1-107">Per altre informazioni generali sui tipi di dati di data e ora, vedere [datetime &#40;Transact-SQL&#41;](/sql/t-sql/data-types/datetime-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="3e0a1-107">For more general information about date and time data types, see [datetime &#40;Transact-SQL&#41;](/sql/t-sql/data-types/datetime-transact-sql).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3e0a1-108">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="3e0a1-108">In This Section</span></span>  
 [<span data-ttu-id="3e0a1-109">Supporto dei tipi di dati per i miglioramenti relativi a data e ora ODBC</span><span class="sxs-lookup"><span data-stu-id="3e0a1-109">Data Type Support for ODBC Date and Time Improvements</span></span>](../../relational-databases/native-client-odbc-date-time/data-type-support-for-odbc-date-and-time-improvements.md)  
 <span data-ttu-id="3e0a1-110">Vengono fornite informazioni sui tipi ODBC che supportano i tipi di dati [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] di data e ora.</span><span class="sxs-lookup"><span data-stu-id="3e0a1-110">Provides information about ODBC types that support [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] date and time data types.</span></span>  
  
 [<span data-ttu-id="3e0a1-111">Metadati &#40;&#41;ODBC</span><span class="sxs-lookup"><span data-stu-id="3e0a1-111">Metadata &#40;ODBC&#41;</span></span>](../../database-engine/dev-guide/metadata-odbc.md)  
 <span data-ttu-id="3e0a1-112">Vengono descritte le informazioni restituite nei campi di descrizione del parametro di implementazione (IPD, Implementation Parameter Descriptor) e di descrizione della riga di implementazione (IRD, Implementation Row Descriptor) nonché i metadati della colonna restituiti da `SQLColumns` e `SQLProcedureColumns`.</span><span class="sxs-lookup"><span data-stu-id="3e0a1-112">Describes information returned in the implementation parameter descriptor (IPD) and implementation row descriptor (IRD) fields, as well as column metadata returned by `SQLColumns` and `SQLProcedureColumns`.</span></span> <span data-ttu-id="3e0a1-113">Vengono inoltre descritti i metadati del tipo di dati restituiti da `SQLGetTypeInfo`.</span><span class="sxs-lookup"><span data-stu-id="3e0a1-113">Also describes data type metadata returned by `SQLGetTypeInfo`.</span></span>  
  
 [<span data-ttu-id="3e0a1-114">conversioni di tipi di dati DateTime &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="3e0a1-114">datetime Data Type Conversions &#40;ODBC&#41;</span></span>](datetime-data-type-conversions-odbc.md)  
 <span data-ttu-id="3e0a1-115">Viene descritto come eseguire la conversione tra i valori datetime e datetimeoffset.</span><span class="sxs-lookup"><span data-stu-id="3e0a1-115">Describes how to convert between datetime and datetimeoffset values.</span></span>  
  
 [<span data-ttu-id="3e0a1-116">Supporto sql_variant per i tipi di data e ora</span><span class="sxs-lookup"><span data-stu-id="3e0a1-116">sql_variant Support for Date and Time Types</span></span>](sql-variant-support-for-date-and-time-types.md)  
 <span data-ttu-id="3e0a1-117">Viene descritto il supporto della funzione SQL_VARIANT per la funzionalità avanzata di data e ora.</span><span class="sxs-lookup"><span data-stu-id="3e0a1-117">Describes SQL_VARIANT function support for enhanced date and time functionality.</span></span>  
  
 [<span data-ttu-id="3e0a1-118">Modifiche della copia bulk per i tipi di data e ora avanzati &#40;OLE DB e ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="3e0a1-118">Bulk Copy Changes for Enhanced Date and Time Types &#40;OLE DB and ODBC&#41;</span></span>](../../relational-databases/native-client-odbc-date-time/bulk-copy-changes-for-enhanced-date-and-time-types-ole-db-and-odbc.md)  
 <span data-ttu-id="3e0a1-119">Vengono descritti i miglioramenti apportati ai tipi di data/ora per supportare le operazioni di copia bulk.</span><span class="sxs-lookup"><span data-stu-id="3e0a1-119">Describes date/time enhancements to support bulk copy operations.</span></span>  
  
 [<span data-ttu-id="3e0a1-120">Comportamento del tipo di data e ora migliorato con le versioni precedenti di SQL Server &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="3e0a1-120">Enhanced Date and Time Type Behavior with Previous SQL Server Versions &#40;ODBC&#41;</span></span>](enhanced-date-and-time-type-behavior-with-previous-sql-server-versions-odbc.md)  
 <span data-ttu-id="3e0a1-121">Viene descritto il comportamento previsto quando un'applicazione client che utilizza le caratteristiche avanzate di data e ora comunica con una versione precedente di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e quando un client compilato con una versione precedente di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client invia comandi a un server che supporta le caratteristiche avanzate di data e ora.</span><span class="sxs-lookup"><span data-stu-id="3e0a1-121">Describes the expected behavior when a client application using enhanced date and time features communicates with an older version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], and when a client compiled with an older version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client sends commands to a server that supports enhanced date and time features.</span></span>  
  
 [<span data-ttu-id="3e0a1-122">Supporto delle API ODBC per le funzionalità avanzate di data e ora</span><span class="sxs-lookup"><span data-stu-id="3e0a1-122">ODBC API Support for Enhanced Date and Time Features</span></span>](odbc-api-support-for-enhanced-date-and-time-features.md)  
 <span data-ttu-id="3e0a1-123">Vengono elencate le funzioni ODBC che supportano la funzionalità avanzata di data e ora.</span><span class="sxs-lookup"><span data-stu-id="3e0a1-123">Lists the ODBC functions that support enhanced date and time functionality.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e0a1-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3e0a1-124">See Also</span></span>  
 [<span data-ttu-id="3e0a1-125">SQL Server Native Client &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="3e0a1-125">SQL Server Native Client &#40;ODBC&#41;</span></span>](../../relational-databases/native-client/odbc/sql-server-native-client-odbc.md)  
  
  
