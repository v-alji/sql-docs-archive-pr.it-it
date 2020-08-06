---
title: Supporto di query distribuite nei set di righe dello schema | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- DBPROPSET_SQLSERVERSESSION property
- schema rowsets [OLE DB]
- distributed queries [SQL Server], SQL Server Native Client OLE DB provider
- OLE DB, schema rowsets
- OLE DB rowsets, schema
- rowsets [OLE DB], schema
ms.assetid: 11354bb6-be42-4d8d-854c-42dd3dc38656
author: rothja
ms.author: jroth
ms.openlocfilehash: 48b57bbf40590f8ad5c049268f25fe66d2f94357
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625358"
---
# <a name="distributed-query-support-in-schema-rowsets"></a><span data-ttu-id="63424-102">Supporto di query distribuite nei set di righe dello schema</span><span class="sxs-lookup"><span data-stu-id="63424-102">Distributed Query Support in Schema Rowsets</span></span>
  <span data-ttu-id="63424-103">Per supportare [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] le query distribuite, l' [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] interfaccia **IDBSchemaRowset** del provider di OLE DB di Native Client restituisce i metadati nei server collegati.</span><span class="sxs-lookup"><span data-stu-id="63424-103">To support [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] distributed queries, the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider **IDBSchemaRowset** interface returns metadata on linked servers.</span></span>  
  
 <span data-ttu-id="63424-104">Se la proprietà SSPROP_QUOTEDCATALOGNAMES di DBPROPSET_SQLSERVERSESSION è VARIANT_TRUE, è possibile utilizzare un identificatore tra virgolette per specificare il nome di catalogo (ad esempio "catalogo.personale").</span><span class="sxs-lookup"><span data-stu-id="63424-104">If the DBPROPSET_SQLSERVERSESSION property SSPROP_QUOTEDCATALOGNAMES is VARIANT_TRUE, a quoted identifier can be specified for the catalog name (for example "my.catalog").</span></span> <span data-ttu-id="63424-105">Quando si limita l'output del set di righe dello schema per Catalog, il [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] provider di OLE DB di Native Client riconosce un nome in due parti contenente il nome del catalogo e del server collegato.</span><span class="sxs-lookup"><span data-stu-id="63424-105">When restricting schema rowset output by catalog, the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider recognizes a two-part name containing the linked server and catalog name.</span></span> <span data-ttu-id="63424-106">Per i set di righe dello schema nella tabella seguente, specificando un nome di catalogo in due parti come _linked_server_**.** il _Catalogo_ limita l'output al catalogo applicabile del server collegato denominato.</span><span class="sxs-lookup"><span data-stu-id="63424-106">For the schema rowsets in the table below, specifying a two-part catalog name as _linked_server_**.**_catalog_ restricts output to the applicable catalog of the named linked server.</span></span>  
  
|<span data-ttu-id="63424-107">Set di righe dello schema</span><span class="sxs-lookup"><span data-stu-id="63424-107">Schema rowset</span></span>|<span data-ttu-id="63424-108">Restrizione per catalogo</span><span class="sxs-lookup"><span data-stu-id="63424-108">Catalog restriction</span></span>|  
|-------------------|-------------------------|  
|<span data-ttu-id="63424-109">DBSCHEMA_CATALOGS</span><span class="sxs-lookup"><span data-stu-id="63424-109">DBSCHEMA_CATALOGS</span></span>|<span data-ttu-id="63424-110">CATALOG_NAME</span><span class="sxs-lookup"><span data-stu-id="63424-110">CATALOG_NAME</span></span>|  
|<span data-ttu-id="63424-111">DBSCHEMA_COLUMNS</span><span class="sxs-lookup"><span data-stu-id="63424-111">DBSCHEMA_COLUMNS</span></span>|<span data-ttu-id="63424-112">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="63424-112">TABLE_CATALOG</span></span>|  
|<span data-ttu-id="63424-113">DBSCHEMA_PRIMARY_KEYS</span><span class="sxs-lookup"><span data-stu-id="63424-113">DBSCHEMA_PRIMARY_KEYS</span></span>|<span data-ttu-id="63424-114">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="63424-114">TABLE_CATALOG</span></span>|  
|<span data-ttu-id="63424-115">DBSCHEMA_TABLES</span><span class="sxs-lookup"><span data-stu-id="63424-115">DBSCHEMA_TABLES</span></span>|<span data-ttu-id="63424-116">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="63424-116">TABLE_CATALOG</span></span>|  
|<span data-ttu-id="63424-117">DBSCHEMA_FOREIGN_KEYS</span><span class="sxs-lookup"><span data-stu-id="63424-117">DBSCHEMA_FOREIGN_KEYS</span></span>|<span data-ttu-id="63424-118">PK_TABLE_CATALOG FK_TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="63424-118">PK_TABLE_CATALOG FK_TABLE_CATALOG</span></span>|  
|<span data-ttu-id="63424-119">DBSCHEMA_INDEXES</span><span class="sxs-lookup"><span data-stu-id="63424-119">DBSCHEMA_INDEXES</span></span>|<span data-ttu-id="63424-120">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="63424-120">TABLE_CATALOG</span></span>|  
|<span data-ttu-id="63424-121">DBSCHEMA_COLUMN_PRIVILEGES</span><span class="sxs-lookup"><span data-stu-id="63424-121">DBSCHEMA_COLUMN_PRIVILEGES</span></span>|<span data-ttu-id="63424-122">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="63424-122">TABLE_CATALOG</span></span>|  
|<span data-ttu-id="63424-123">DBSCHEMA_TABLE_PRIVILEGES</span><span class="sxs-lookup"><span data-stu-id="63424-123">DBSCHEMA_TABLE_PRIVILEGES</span></span>|<span data-ttu-id="63424-124">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="63424-124">TABLE_CATALOG</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="63424-125">Per limitare un set di righe dello schema a tutti i cataloghi di un server collegato, utilizzare la sintassi *linked_server* (dove il separatore punto fa parte della specifica del nome).</span><span class="sxs-lookup"><span data-stu-id="63424-125">To restrict a schema rowset to all catalogs from a linked server, use the syntax *linked_server* (where the period separator is part of the name specification).</span></span> <span data-ttu-id="63424-126">Questa sintassi è equivalente alla specifica di NULL come restrizione del nome di catalogo e viene utilizzata anche quando il server collegato indica un'origine dati che non supporta cataloghi.</span><span class="sxs-lookup"><span data-stu-id="63424-126">This syntax is equivalent to specifying NULL for the catalog name restriction and is also used when the linked server indicates a data source that does not support catalogs.</span></span>  
  
 <span data-ttu-id="63424-127">Il [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] provider di OLE DB di Native Client definisce il set di righe dello schema LinkedServers, restituendo un elenco di OLE DB origini dati registrate come server collegati.</span><span class="sxs-lookup"><span data-stu-id="63424-127">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider defines the schema rowset LINKEDSERVERS, returning a list of OLE DB data sources registered as linked servers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63424-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="63424-128">See Also</span></span>  
 <span data-ttu-id="63424-129">[&#40;OLE DB di supporto per set di righe dello schema&#41;](schema-rowset-support-ole-db.md) </span><span class="sxs-lookup"><span data-stu-id="63424-129">[Schema Rowset Support &#40;OLE DB&#41;](schema-rowset-support-ole-db.md) </span></span>  
 [<span data-ttu-id="63424-130">Set di righe LINKEDSERVERS &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="63424-130">LINKEDSERVERS Rowset &#40;OLE DB&#41;</span></span>](schema-rowsets-linkedservers-rowset.md)  
  
  
