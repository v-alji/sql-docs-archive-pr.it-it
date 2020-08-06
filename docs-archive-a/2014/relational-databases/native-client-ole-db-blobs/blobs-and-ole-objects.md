---
title: BLOB e oggetti OLE | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- BLOBs, OLE objects
- BLOBs
- storage object [OLE DB]
- SQL Server Native Client OLE DB provider, BLOBs
- large data, OLE objects
ms.assetid: 767fa2f6-9cd2-436f-add5-e760bed29a58
author: rothja
ms.author: jroth
ms.openlocfilehash: 15f8b4915ba9b05a5be19854a2e27a2e8ff3a346
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725604"
---
# <a name="blobs-and-ole-objects"></a><span data-ttu-id="a09a6-102">Oggetti BLOB e OLE</span><span class="sxs-lookup"><span data-stu-id="a09a6-102">BLOBs and OLE Objects</span></span>
  <span data-ttu-id="a09a6-103">Il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native Client espone l'interfaccia **ISequentialStream** per supportare l'accesso del consumer ai [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tipi di dati **ntext**, **Text**, **Image**, **varchar (max)**, **nvarchar (max)**, **varbinary (max)** e XML come oggetti binari di grandi dimensioni (BLOB).</span><span class="sxs-lookup"><span data-stu-id="a09a6-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider exposes the **ISequentialStream** interface to support consumer access to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **ntext**, **text**, **image**, **varchar(max)**, **nvarchar(max)**, **varbinary(max)**, and xml data types as binary large objects (BLOBs).</span></span> <span data-ttu-id="a09a6-104">Il metodo **Read** in **ISequentialStream** consente al consumer di recuperare una quantità elevata di dati in blocchi gestibili.</span><span class="sxs-lookup"><span data-stu-id="a09a6-104">The **Read** method on **ISequentialStream** lets the consumer retrieve much data in manageable chunks.</span></span>  
  
 <span data-ttu-id="a09a6-105">Per un esempio che illustra questa funzionalità, vedere [Impostare dati di grandi dimensioni &#40;OLE DB&#41;](../native-client-ole-db-how-to/set-large-data-ole-db.md).</span><span class="sxs-lookup"><span data-stu-id="a09a6-105">For a sample demonstrating this feature, see [Set Large Data &#40;OLE DB&#41;](../native-client-ole-db-how-to/set-large-data-ole-db.md).</span></span>  
  
 <span data-ttu-id="a09a6-106">Il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native client può utilizzare un'interfaccia **IStorage** implementata dal consumer quando il consumer fornisce il puntatore di interfaccia in una funzione di accesso associata per la modifica dei dati.</span><span class="sxs-lookup"><span data-stu-id="a09a6-106">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider can use a consumer-implemented **IStorage** interface when the consumer provides the interface pointer in an accessor bound for data modification.</span></span>  
  
 <span data-ttu-id="a09a6-107">Per i tipi di dati con valori di grandi dimensioni, il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native Client controlla i presupposti della dimensione del tipo nelle interfacce **IROWSET** e DDL.</span><span class="sxs-lookup"><span data-stu-id="a09a6-107">For large value data types, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider checks for type size assumptions in **IRowset** and DDL interfaces.</span></span> <span data-ttu-id="a09a6-108">Le colonne con tipi di dati **varchar**, **nvarchar**e **varbinary** con dimensioni massime impostate su Unlimited verranno rappresentate come Long lungo i set di righe dello schema e le interfacce che restituiscono i tipi di dati della colonna.</span><span class="sxs-lookup"><span data-stu-id="a09a6-108">Columns with **varchar**, **nvarchar**, and **varbinary** data types with max size set to unlimited will be represented as ISLONG through the schema rowsets and interfaces returning column data types.</span></span>  
  
 <span data-ttu-id="a09a6-109">Il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native Client espone rispettivamente i tipi **varchar (max**), **varbinary (max)** e **nvarchar (max)** come DBTYPE_STR, DBTYPE_BYTES e DBTYPE_WSTR.</span><span class="sxs-lookup"><span data-stu-id="a09a6-109">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider exposes the **varchar(max)**, **varbinary(max)** and **nvarchar(max)** types as DBTYPE_STR, DBTYPE_BYTES and DBTYPE_WSTR respectively.</span></span>  
  
 <span data-ttu-id="a09a6-110">In un'applicazione è possibile utilizzare questi tipi nei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="a09a6-110">To work with these types an application has the following options:</span></span>  
  
-   <span data-ttu-id="a09a6-111">Eseguire l'associazione come tipo (DBTYPE_STR, DBTYPE_BYTES, DBTYPE_WSTR).</span><span class="sxs-lookup"><span data-stu-id="a09a6-111">Bind as the type (DBTYPE_STR, DBTYPE_BYTES, DBTYPE_WSTR).</span></span> <span data-ttu-id="a09a6-112">Se le dimensioni de buffer non sono sufficienti, si verificherà il troncamento, esattamente come accade per questi tipi nelle release precedenti, anche se ora sono disponibili valori più grandi.</span><span class="sxs-lookup"><span data-stu-id="a09a6-112">If the buffer is not big enough truncation will occur, exactly as for these types in previous releases (although larger values are now available).</span></span>  
  
-   <span data-ttu-id="a09a6-113">Eseguire l'associazione come tipo e specificare DBTYPE_BYREF.</span><span class="sxs-lookup"><span data-stu-id="a09a6-113">Bind as the type and also specify DBTYPE_BYREF.</span></span>  
  
-   <span data-ttu-id="a09a6-114">Eseguire l'associazione come DBTYPE_IUNKNOWN e utilizzare il flusso.</span><span class="sxs-lookup"><span data-stu-id="a09a6-114">Bind as DBTYPE_IUNKNOWN and use streaming.</span></span>  
  
 <span data-ttu-id="a09a6-115">Se si esegue l'associazione a DBTYPE_IUNKNOWN, viene utilizzata la funzionalità di flusso di ISequentialStream.</span><span class="sxs-lookup"><span data-stu-id="a09a6-115">If bound to DBTYPE_IUNKNOWN, ISequentialStream stream functionality is used.</span></span> <span data-ttu-id="a09a6-116">Il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native Client supporta l'associazione di parametri di output come DBTYPE_IUNKNOWN per i tipi di dati con valori di grandi dimensioni per semplificare gli scenari in cui un stored procedure restituisce questi tipi di dati come valori restituiti che verranno esposti come DBTYPE_IUNKNOWN al client.</span><span class="sxs-lookup"><span data-stu-id="a09a6-116">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider supports binding output parameters as DBTYPE_IUNKNOWN for large value data types to facilitate scenarios where a stored procedure returns these data types as return values which will be exposed as DBTYPE_IUNKNOWN to the client.</span></span>  
  
## <a name="storage-object-limitations"></a><span data-ttu-id="a09a6-117">Limitazioni degli oggetti di archiviazione</span><span class="sxs-lookup"><span data-stu-id="a09a6-117">Storage Object Limitations</span></span>  
  
-   <span data-ttu-id="a09a6-118">Il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native client può supportare solo un singolo oggetto di archiviazione aperto.</span><span class="sxs-lookup"><span data-stu-id="a09a6-118">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider can support only a single open storage object.</span></span> <span data-ttu-id="a09a6-119">I tentativi di aprire più di un oggetto di archiviazione (per ottenere un riferimento su più di un puntatore di interfaccia **ISequentialStream**) restituiscono DBSTATUS_E_CANTCREATE.</span><span class="sxs-lookup"><span data-stu-id="a09a6-119">Attempts to open more than one storage object (to get a reference on more than one **ISequentialStream** interface pointer) return DBSTATUS_E_CANTCREATE.</span></span>  
  
-   <span data-ttu-id="a09a6-120">Nel [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native client, il valore predefinito della proprietà di sola lettura DBPROP_BLOCKINGSTORAGEOBJECTS è VARIANT_TRUE.</span><span class="sxs-lookup"><span data-stu-id="a09a6-120">In the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider, the default value of the DBPROP_BLOCKINGSTORAGEOBJECTS read-only property is VARIANT_TRUE.</span></span> <span data-ttu-id="a09a6-121">Tale valore indica che se un oggetto di archiviazione è attivo, alcuni metodi (diversi da quelli degli oggetti di archiviazione) non riusciranno e verrà restituito E_UNEXPECTED.</span><span class="sxs-lookup"><span data-stu-id="a09a6-121">This indicates that if a storage object is active, some methods (other than those on the storage objects) will fail with E_UNEXPECTED.</span></span>  
  
-   <span data-ttu-id="a09a6-122">La lunghezza dei dati presentati da un oggetto di archiviazione implementato dal consumer deve essere resa nota al [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider OLE DB di Native client quando viene creata la funzione di accesso Row che fa riferimento all'oggetto di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="a09a6-122">The length of data presented by a consumer-implemented storage object must be made known to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider when the row accessor that references the storage object is created.</span></span> <span data-ttu-id="a09a6-123">Il consumer deve associare un indicatore di lunghezza nella struttura DBBINDING utilizzata per la creazione della funzione di accesso.</span><span class="sxs-lookup"><span data-stu-id="a09a6-123">The consumer must bind a length indicator in the DBBINDING structure used for accessor creation.</span></span>  
  
-   <span data-ttu-id="a09a6-124">Se una riga contiene più di un singolo valore di dati di grandi dimensioni e DBPROP_ACCESSORDER non è DBPROPVAL_AO_RANDOM, il consumer deve utilizzare un [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] set di righe supportato dal cursore del provider OLE DB Native Client per recuperare i dati delle righe o elaborare tutti i valori di dati di grandi dimensioni prima di recuperare altri valori di riga.</span><span class="sxs-lookup"><span data-stu-id="a09a6-124">If a row contains more than a single large data value and DBPROP_ACCESSORDER is not DBPROPVAL_AO_RANDOM, the consumer must either use a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider cursor-supported rowset to retrieve row data or process all large data values before retrieving other row values.</span></span> <span data-ttu-id="a09a6-125">Se DBPROP_ACCESSORDER è DBPROPVAL_AO_RANDOM, il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider OLE DB di Native Client memorizza nella cache tutti i tipi di dati XML come oggetti binari di grandi dimensioni (BLOB), in modo che sia possibile accedervi in qualsiasi ordine.</span><span class="sxs-lookup"><span data-stu-id="a09a6-125">If DBPROP_ACCESSORDER is DBPROPVAL_AO_RANDOM, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider caches all the xml data types as binary large objects (BLOBs) so that it can be accessed in any order.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a09a6-126">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="a09a6-126">In This Section</span></span>  
  
-   [<span data-ttu-id="a09a6-127">Recupero di dati di grandi dimensioni</span><span class="sxs-lookup"><span data-stu-id="a09a6-127">Getting Large Data</span></span>](getting-large-data.md)  
  
-   [<span data-ttu-id="a09a6-128">Impostazione di dati di grandi dimensioni</span><span class="sxs-lookup"><span data-stu-id="a09a6-128">Setting Large Data</span></span>](setting-large-data.md)  
  
-   [<span data-ttu-id="a09a6-129">Supporto del flusso per parametri di output BLOB</span><span class="sxs-lookup"><span data-stu-id="a09a6-129">Streaming Support for BLOB Output Parameters</span></span>](streaming-support-for-blob-output-parameters.md)  
  
## <a name="see-also"></a><span data-ttu-id="a09a6-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a09a6-130">See Also</span></span>  
 <span data-ttu-id="a09a6-131">[SQL Server Native Client &#40;OLE DB&#41;](../native-client/ole-db/sql-server-native-client-ole-db.md) </span><span class="sxs-lookup"><span data-stu-id="a09a6-131">[SQL Server Native Client &#40;OLE DB&#41;](../native-client/ole-db/sql-server-native-client-ole-db.md) </span></span>  
 [<span data-ttu-id="a09a6-132">Utilizzo di tipi di dati per valori di grandi dimensioni</span><span class="sxs-lookup"><span data-stu-id="a09a6-132">Using Large Value Types</span></span>](../native-client/features/using-large-value-types.md)  
  
  
