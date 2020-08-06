---
title: Proprietà delle informazioni sulle origini dati | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client OLE DB provider, data source properties
- properties [OLE DB]
- data source properties [OLE DB]
- information properties [OLE DB]
- OLE DB data source properties [SQL Server Native Client]
ms.assetid: 7fd80e47-5bd9-41e2-a3d3-091a7c8c5f2b
author: rothja
ms.author: jroth
ms.openlocfilehash: c10a4e762bbe3421e720753941f5e0a5702832ad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724559"
---
# <a name="data-source-information-properties"></a><span data-ttu-id="82ae8-102">Proprietà delle informazioni sulle origini dati</span><span class="sxs-lookup"><span data-stu-id="82ae8-102">Data Source Information Properties</span></span>
  <span data-ttu-id="82ae8-103">Nel set di proprietà DBPROPSET_SQLSERVERDATASOURCEINFO specifico del provider il provider OLE DB di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client definisce le seguenti proprietà delle informazioni sulle origini dati.</span><span class="sxs-lookup"><span data-stu-id="82ae8-103">In the provider-specific property set DBPROPSET_SQLSERVERDATASOURCEINFO, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider defines the following data source information properties.</span></span>  
  
|<span data-ttu-id="82ae8-104">ID proprietà</span><span class="sxs-lookup"><span data-stu-id="82ae8-104">Property ID</span></span>|<span data-ttu-id="82ae8-105">Descrizione</span><span class="sxs-lookup"><span data-stu-id="82ae8-105">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="82ae8-106">SSPROP_COLUMNLEVELCOLLATION</span><span class="sxs-lookup"><span data-stu-id="82ae8-106">SSPROP_COLUMNLEVELCOLLATION</span></span>|<span data-ttu-id="82ae8-107">Digitare: VT_BOOL</span><span class="sxs-lookup"><span data-stu-id="82ae8-107">Type: VT_BOOL</span></span><br /><br /> <span data-ttu-id="82ae8-108">L/S: Lettura</span><span class="sxs-lookup"><span data-stu-id="82ae8-108">R/W: Read</span></span><br /><br /> <span data-ttu-id="82ae8-109">Impostazione predefinita: VARIANT_TRUE</span><span class="sxs-lookup"><span data-stu-id="82ae8-109">Default: VARIANT_TRUE</span></span><br /><br /> <span data-ttu-id="82ae8-110">Descrizione: utilizzato per determinare se le regole di confronto a livello di colonna sono supportate.</span><span class="sxs-lookup"><span data-stu-id="82ae8-110">Description: Used to determine if column collation is supported.</span></span><br /><br /> <span data-ttu-id="82ae8-111">VARIANT_TRUE: le regole di confronto a livello di colonna sono supportate.</span><span class="sxs-lookup"><span data-stu-id="82ae8-111">VARIANT_TRUE: Column level collation is supported.</span></span><br /><br /> <span data-ttu-id="82ae8-112">VARIANT_FALSE: le regole di confronto a livello di colonna non sono supportate.</span><span class="sxs-lookup"><span data-stu-id="82ae8-112">VARIANT_FALSE: Column level collation is not supported.</span></span>|  
|<span data-ttu-id="82ae8-113">SSPROP_UNICODELCID</span><span class="sxs-lookup"><span data-stu-id="82ae8-113">SSPROP_UNICODELCID</span></span>|<span data-ttu-id="82ae8-114">Tipo: VT_I4 L/S: Lettura</span><span class="sxs-lookup"><span data-stu-id="82ae8-114">Type: VT_I4 R/W: Read</span></span><br /><br /> <span data-ttu-id="82ae8-115">Descrizione: ID delle impostazioni locali Unicode.</span><span class="sxs-lookup"><span data-stu-id="82ae8-115">Description: Unicode locale ID.</span></span><br /><br /> <span data-ttu-id="82ae8-116">Si tratta delle impostazioni locali utilizzate per l'ordinamento dei dati Unicode.</span><span class="sxs-lookup"><span data-stu-id="82ae8-116">This is the locale used for Unicode data sorting.</span></span>|  
|<span data-ttu-id="82ae8-117">SSPROP_UNICODECOMPARISONSTYLE</span><span class="sxs-lookup"><span data-stu-id="82ae8-117">SSPROP_UNICODECOMPARISONSTYLE</span></span>|<span data-ttu-id="82ae8-118">Tipo: VT_I4 L/S: Lettura</span><span class="sxs-lookup"><span data-stu-id="82ae8-118">Type: VT_I4 R/W: Read</span></span><br /><br /> <span data-ttu-id="82ae8-119">Descrizione: stile di confronto Unicode.</span><span class="sxs-lookup"><span data-stu-id="82ae8-119">Description: Unicode comparison style.</span></span><br /><br /> <span data-ttu-id="82ae8-120">Opzioni di ordinamento utilizzate per l'ordinamento dei dati Unicode.</span><span class="sxs-lookup"><span data-stu-id="82ae8-120">The sorting options used for Unicode data sorting.</span></span>|  
  
 <span data-ttu-id="82ae8-121">Nel set di proprietà DBPROPSET_SQLSERVERSTREAM specifico del provider il provider OLE DB di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client definisce le proprietà di sessione aggiuntive indicate di seguito.</span><span class="sxs-lookup"><span data-stu-id="82ae8-121">In the provider-specific property set DBPROPSET_SQLSERVERSTREAM, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider defines the following additional property.</span></span>  
  
|<span data-ttu-id="82ae8-122">ID proprietà</span><span class="sxs-lookup"><span data-stu-id="82ae8-122">Property ID</span></span>|<span data-ttu-id="82ae8-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="82ae8-123">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="82ae8-124">SSPROP_STREAM_XMLROOT</span><span class="sxs-lookup"><span data-stu-id="82ae8-124">SSPROP_STREAM_XMLROOT</span></span>|<span data-ttu-id="82ae8-125">Tipo: VT_BSTR L/S: Lettura/Scrittura</span><span class="sxs-lookup"><span data-stu-id="82ae8-125">Type: VT_BSTR R/W: Read/Write</span></span><br /><br /> <span data-ttu-id="82ae8-126">Descrizione: il risultato di una query FOR XML potrebbe non essere un documento corretto.</span><span class="sxs-lookup"><span data-stu-id="82ae8-126">Description: The result of a FOR XML query may not be a well-formed document.</span></span> <span data-ttu-id="82ae8-127">Quando questa proprietà viene specificata, viene eseguito il wrapping del risultato di una query 'select ... for XML' nel tag radice fornito dalla proprietà per restituire un documento XML corretto.</span><span class="sxs-lookup"><span data-stu-id="82ae8-127">When this property is specified, the result of a 'select ... for XML' query is wrapped in the root tag provided by this property to return a well formed XML document.</span></span> <span data-ttu-id="82ae8-128">Se la query viene eseguita nel browser, è possibile che nel browser stesso vengano visualizzati errori del parser durante il caricamento del risultato.</span><span class="sxs-lookup"><span data-stu-id="82ae8-128">If the query is executed in the browser it may cause the browser to display parser errors when loading the result.</span></span> <span data-ttu-id="82ae8-129">Per evitare l'errore, SQL ISAPI supporta la parola chiave ROOT che</span><span class="sxs-lookup"><span data-stu-id="82ae8-129">To avoid the error, SQL ISAPI supports the keyword ROOT.</span></span> <span data-ttu-id="82ae8-130">viene mappata alla proprietà SSPROP_STREAM_XMLROOT.</span><span class="sxs-lookup"><span data-stu-id="82ae8-130">This keyword maps to SSPROP_STREAM_XMLROOT property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="82ae8-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="82ae8-131">See Also</span></span>  
 [<span data-ttu-id="82ae8-132">Oggetti di origine dati &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="82ae8-132">Data Source Objects &#40;OLE DB&#41;</span></span>](data-source-objects-ole-db.md)  
  
  
