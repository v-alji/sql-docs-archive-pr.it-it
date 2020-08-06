---
title: Supporto dei tipi di parametri con valori di tabella OLE DB | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- table-valued parameters (OLE DB), API support (OLE DB)
ms.assetid: 147036a0-260e-4f81-8b3b-89209e023a32
author: rothja
ms.author: jroth
ms.openlocfilehash: 48d5fd780b2eaa2fc18e39071d3b10fde897b82c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626729"
---
# <a name="ole-db-table-valued-parameter-type-support"></a><span data-ttu-id="61a10-102">Supporto del tipo di parametro con valori di tabella OLE DB</span><span class="sxs-lookup"><span data-stu-id="61a10-102">OLE DB Table-Valued Parameter Type Support</span></span>
  <span data-ttu-id="61a10-103">In questo argomento viene descritto il supporto del tipo OLE DB per i parametri con valori di tabella.</span><span class="sxs-lookup"><span data-stu-id="61a10-103">This topic describes OLE DB type support for table-value parameters.</span></span>  
  
## <a name="table-valued-parameter-rowset-object"></a><span data-ttu-id="61a10-104">Oggetto set di righe di parametri con valori di tabella</span><span class="sxs-lookup"><span data-stu-id="61a10-104">Table-Valued Parameter Rowset Object</span></span>  
 <span data-ttu-id="61a10-105">È possibile creare un oggetto set di righe specifico per i parametri con valori di tabella.</span><span class="sxs-lookup"><span data-stu-id="61a10-105">You can create a specialized rowset object for table-valued parameters.</span></span> <span data-ttu-id="61a10-106">Per creare l'oggetto set di righe per i parametri con valori di tabella, usare ITableDefinitionWithConstraints::CreateTableWithConstraints o IOpenRowset::OpenRowset.</span><span class="sxs-lookup"><span data-stu-id="61a10-106">You create the table-valued parameter rowset object by using ITableDefinitionWithConstraints::CreateTableWithConstraints or IOpenRowset::OpenRowset.</span></span> <span data-ttu-id="61a10-107">A questo scopo, impostare il membro *eKind* del parametro *pTableID* su DBKIND_GUID_NAME e specificare CLSID_ROWSET_INMEMORY come membro *guid*.</span><span class="sxs-lookup"><span data-stu-id="61a10-107">To do this, set the *eKind* member of the *pTableID* parameter to DBKIND_GUID_NAME, and provide the CLSID_ROWSET_INMEMORY as the *guid* member.</span></span> <span data-ttu-id="61a10-108">Il nome del tipo di server per il parametro con valori di tabella deve essere specificato nel membro *pwszName* di *pTableID* quando si usa IOpenRowset::OpenRowset.</span><span class="sxs-lookup"><span data-stu-id="61a10-108">The server type name for the table-valued parameter must be specified in the *pwszName* member of *pTableID* when using IOpenRowset::OpenRowset.</span></span> <span data-ttu-id="61a10-109">L'oggetto set di righe di parametri con valori di tabella si comporta come un normale oggetto del provider OLE DB di SQL Server Native Client.</span><span class="sxs-lookup"><span data-stu-id="61a10-109">The table-valued parameter rowset object behaves like a regular SQL Server Native Client OLE DB Provider object.</span></span>  
  
```  
const GUID CLSID_ROWSET_TVP =   
{0xc7ef28d5, 0x7bee, 0x443f, {0x86, 0xda, 0xe3, 0x98, 0x4f, 0xcd, 0x4d, 0xf9}};  
  
CoType RowsetTVP  
{  
[mandatory] interface IAccessor;  
[mandatory] interface IColumnsInfo;  
[mandatory] interface IConvertType;  
[mandatory] interface IRowset;  
[mandatory] interface IRowsetInfo;  
[optional]  interface IColumnsRowset;  
[optional]  interface IRowsetChange;  
[optional]  interface ISupportErrorInfo;  
};  
```  
  
## <a name="dbtype_table"></a><span data-ttu-id="61a10-110">DBTYPE_TABLE</span><span class="sxs-lookup"><span data-stu-id="61a10-110">DBTYPE_TABLE</span></span>  
 <span data-ttu-id="61a10-111">Un nuovo tipo, DBTYPE_TABLE, rappresenta un tipo di tabella.</span><span class="sxs-lookup"><span data-stu-id="61a10-111">A new type, DBTYPE_TABLE, represents a table type.</span></span> <span data-ttu-id="61a10-112">Tale tipo specifica i parametri con valori di tabella nelle varie interfacce OLE DB in cui è richiesto un oggetto DBTYPE.</span><span class="sxs-lookup"><span data-stu-id="61a10-112">This type specifies table-valued parameters in various OLE DB interfaces where a DBTYPE is required.</span></span>  
  
```  
#define DBTYPE_TABLE (143)  
```  
  
 <span data-ttu-id="61a10-113">Il formato di DBTYPE_TABLE è identico a quello di DBTYPE_IUNKNOWN.</span><span class="sxs-lookup"><span data-stu-id="61a10-113">DBTYPE_TABLE has the same format as DBTYPE_IUNKNOWN.</span></span> <span data-ttu-id="61a10-114">Si tratta di un puntatore a un oggetto nel buffer di dati.</span><span class="sxs-lookup"><span data-stu-id="61a10-114">It is a pointer to an object in the data buffer.</span></span> <span data-ttu-id="61a10-115">Per una specifica completa nelle associazioni, il consumer inserisce dati nel buffer DBOBJECT, con *iid* impostato su una delle interfacce dell'oggetto set di righe (IID_IRowset).</span><span class="sxs-lookup"><span data-stu-id="61a10-115">For complete specification in the bindings, the consumer fills up the DBOBJECT buffer, with *iid* set to one of the rowset object interfaces (IID_IRowset).</span></span> <span data-ttu-id="61a10-116">Se non viene specificato alcun oggetto DBOBJECT nelle associazioni, si presuppone che l'oggetto sia IID_IRowset.</span><span class="sxs-lookup"><span data-stu-id="61a10-116">If no DBOBJECT is specified in the bindings, IID_IRowset will be assumed.</span></span>  
  
 <span data-ttu-id="61a10-117">Le conversioni da e verso DBTYPE_TABLE per altri tipi non sono supportate.</span><span class="sxs-lookup"><span data-stu-id="61a10-117">Conversions to and from DBTYPE_TABLE for any other types are not supported.</span></span> <span data-ttu-id="61a10-118">IConvertType::CanConvert restituisce S_FALSE per la conversione non supportata per tutte le richieste diverse dalla conversione da DBTYPE_TABLE a DBTYPE_TABLE.</span><span class="sxs-lookup"><span data-stu-id="61a10-118">IConvertType::CanConvert will return S_FALSE for unsupported conversion for any request other than DBTYPE_TABLE to DBTYPE_TABLE conversion.</span></span> <span data-ttu-id="61a10-119">In questa situazione si presuppone l'uso di DBCONVERTFLAGS_PARAMETER sull'oggetto Command.</span><span class="sxs-lookup"><span data-stu-id="61a10-119">This assumes DBCONVERTFLAGS_PARAMETER on the Command object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="61a10-120">Metodi</span><span class="sxs-lookup"><span data-stu-id="61a10-120">Methods</span></span>  
 <span data-ttu-id="61a10-121">Per informazioni sui metodi di OLE DB che supportano i parametri con valori di tabella, vedere [Supporto dei tipi di parametri con valori di tabella OLE DB &#40;metodi&#41;](ole-db-table-valued-parameter-type-support-methods.md).</span><span class="sxs-lookup"><span data-stu-id="61a10-121">For information about OLE DB methods that support table-valued parameters, see [OLE DB Table-Valued Parameter Type Support &#40;Methods&#41;](ole-db-table-valued-parameter-type-support-methods.md).</span></span>  
  
## <a name="properties"></a><span data-ttu-id="61a10-122">Proprietà</span><span class="sxs-lookup"><span data-stu-id="61a10-122">Properties</span></span>  
 <span data-ttu-id="61a10-123">Per informazioni sulle proprietà di OLE DB che supportano i parametri con valori di tabella, vedere [Supporto dei tipi di parametri con valori di tabella OLE DB &#40;proprietà&#41;](ole-db-table-valued-parameter-type-support-properties.md).</span><span class="sxs-lookup"><span data-stu-id="61a10-123">For information about OLE DB properties that support table-valued parameters, see [OLE DB Table-Valued Parameter Type Support &#40;Properties&#41;](ole-db-table-valued-parameter-type-support-properties.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61a10-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="61a10-124">See Also</span></span>  
 <span data-ttu-id="61a10-125">[Parametri con valori di tabella &#40;OLE DB&#41;](table-valued-parameters-ole-db.md) </span><span class="sxs-lookup"><span data-stu-id="61a10-125">[Table-Valued Parameters &#40;OLE DB&#41;](table-valued-parameters-ole-db.md) </span></span>  
 [<span data-ttu-id="61a10-126">Usare parametri con valori di tabella &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="61a10-126">Use Table-Valued Parameters &#40;OLE DB&#41;</span></span>](../native-client-ole-db-how-to/use-table-valued-parameters-ole-db.md)  
  
  
