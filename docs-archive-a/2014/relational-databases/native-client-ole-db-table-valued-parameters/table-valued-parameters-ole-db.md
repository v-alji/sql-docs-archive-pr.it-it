---
title: Parametri con valori di tabella (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- OLE DB, table-valued parameters
- table-valued parameters (OLE DB)
ms.assetid: 4298b73d-615b-4d28-9843-03b4d5fc489e
author: rothja
ms.author: jroth
ms.openlocfilehash: 41d125bcb254125d7f7562ca1873e8af03dab929
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722731"
---
# <a name="table-valued-parameters-ole-db"></a><span data-ttu-id="eaa81-102">Parametri con valori di tabella (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="eaa81-102">Table-Valued Parameters (OLE DB)</span></span>
  <span data-ttu-id="eaa81-103">In questa sezione viene illustrato il supporto per i parametri con valori di tabella nel provider OLE DB di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="eaa81-103">This section describes support for table-valued parameters in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB Provider.</span></span> <span data-ttu-id="eaa81-104">Per ulteriori informazioni sulla panoramica, vedere [parametri con valori di tabella &#40;SQL Server Native Client&#41;](../native-client/features/table-valued-parameters-sql-server-native-client.md).</span><span class="sxs-lookup"><span data-stu-id="eaa81-104">For additional overview information, see [Table-Valued Parameters &#40;SQL Server Native Client&#41;](../native-client/features/table-valued-parameters-sql-server-native-client.md).</span></span> <span data-ttu-id="eaa81-105">Per un esempio, vedere [Usare parametri con valori di tabella &#40;OLE DB&#41;](../native-client-ole-db-how-to/use-table-valued-parameters-ole-db.md).</span><span class="sxs-lookup"><span data-stu-id="eaa81-105">For a sample, see [Use Table-Valued Parameters &#40;OLE DB&#41;](../native-client-ole-db-how-to/use-table-valued-parameters-ole-db.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eaa81-106">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="eaa81-106">Remarks</span></span>  
 <span data-ttu-id="eaa81-107">Attualmente, è possibile inviare al server dati a più righe come parametri di una procedura con set di parametri (parametro DBPARAMS in `ICommand::Execute`).</span><span class="sxs-lookup"><span data-stu-id="eaa81-107">Currently, you can send multirow data to the server as parameters to a procedure with parameter sets (the DBPARAMS parameter in `ICommand::Execute`).</span></span> <span data-ttu-id="eaa81-108">Con i set di parametri, ogni elemento del set deve essere inviato al server in una richiesta di chiamata di procedura remota (RPC) separata.</span><span class="sxs-lookup"><span data-stu-id="eaa81-108">With parameter sets, every element of the set has to be sent in a separate remote procedure call (RPC) request to the server.</span></span> <span data-ttu-id="eaa81-109">I parametri con valori di tabella forniscono funzionalità simili, ma offrono una maggiore integrazione con il server.</span><span class="sxs-lookup"><span data-stu-id="eaa81-109">Table-valued parameters provide similar functionality, but there is better integration with the server.</span></span> <span data-ttu-id="eaa81-110">Questa caratteristica determina la riduzione del numero di richieste RPC e l'abilitazione delle operazioni basate sul set nel server.</span><span class="sxs-lookup"><span data-stu-id="eaa81-110">This reduces the number of RPC requests and enables set-based operations on the server.</span></span>  
  
 <span data-ttu-id="eaa81-111">I parametri con valori di tabella sono supportati nel provider OLE DB di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client come oggetti OLE DB di tipo `Rowset`.</span><span class="sxs-lookup"><span data-stu-id="eaa81-111">Table-value parameters are supported in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB Provider as OLE DB `Rowset` objects.</span></span> <span data-ttu-id="eaa81-112">Gli oggetti `Rowset` possono essere forniti dal consumer, ovvero dall'applicazione client che utilizza il provider OLE DB di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client, come segnaposto per i parametri con valori di tabella.</span><span class="sxs-lookup"><span data-stu-id="eaa81-112">Any `Rowset` object could be provided by the consumer (that is, the client application using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB Provider) as a placeholder for table-valued parameter parameters.</span></span> <span data-ttu-id="eaa81-113">I parametri con valori di tabella vengono considerati come gli altri tipi di parametro di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="eaa81-113">Table-valued parameters are treated like other [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] parameter types.</span></span> <span data-ttu-id="eaa81-114">Il provider OLE DB di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client fornisce interfacce per gli schemi, l'associazione, la specifica, l'individuazione e la creazione.</span><span class="sxs-lookup"><span data-stu-id="eaa81-114">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB Provider provides creation, discovery, specification, binding and schema interfaces.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="eaa81-115">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="eaa81-115">In This Section</span></span>  
  
-   [<span data-ttu-id="eaa81-116">Creazione di un set di righe di parametri con valori di tabella</span><span class="sxs-lookup"><span data-stu-id="eaa81-116">Table-Valued Parameter Rowset Creation</span></span>](table-valued-parameter-rowset-creation.md)  
  
-   [<span data-ttu-id="eaa81-117">Individuazione del tipo di parametro con valori di tabella</span><span class="sxs-lookup"><span data-stu-id="eaa81-117">Table-Valued Parameter Type Discovery</span></span>](../../database-engine/dev-guide/table-valued-parameter-type-discovery.md)  
  
-   [<span data-ttu-id="eaa81-118">Esecuzione di comandi contenenti parametri con valori di tabella</span><span class="sxs-lookup"><span data-stu-id="eaa81-118">Executing Commands Containing Table-Valued Parameters</span></span>](executing-commands-containing-table-valued-parameters.md)  
  
-   [<span data-ttu-id="eaa81-119">Inserimento di dati in parametri con valori di tabella</span><span class="sxs-lookup"><span data-stu-id="eaa81-119">Inserting Data into Table-Valued Parameters</span></span>](inserting-data-into-table-valued-parameters.md)  
  
-   [<span data-ttu-id="eaa81-120">Set di righe dello schema modificati per i parametri con valori di tabella OLE DB</span><span class="sxs-lookup"><span data-stu-id="eaa81-120">Schema Rowsets Changed for OLE DB Table-Valued Parameters</span></span>](schema-rowsets-changed-for-ole-db-table-valued-parameters.md)  
  
-   [<span data-ttu-id="eaa81-121">Supporto del tipo di parametro con valori di tabella OLE DB</span><span class="sxs-lookup"><span data-stu-id="eaa81-121">OLE DB Table-Valued Parameter Type Support</span></span>](ole-db-table-valued-parameter-type-support.md)  
  
-   [<span data-ttu-id="eaa81-122">Supporto dei tipi di parametro con valori di tabella OLE DB &#40;metodi&#41;</span><span class="sxs-lookup"><span data-stu-id="eaa81-122">OLE DB Table-Valued Parameter Type Support &#40;Methods&#41;</span></span>](ole-db-table-valued-parameter-type-support-methods.md)  
  
-   [<span data-ttu-id="eaa81-123">Supporto dei tipi di parametro con valori di tabella OLE DB &#40;proprietà&#41;</span><span class="sxs-lookup"><span data-stu-id="eaa81-123">OLE DB Table-Valued Parameter Type Support &#40;Properties&#41;</span></span>](ole-db-table-valued-parameter-type-support-properties.md)  
  
## <a name="see-also"></a><span data-ttu-id="eaa81-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eaa81-124">See Also</span></span>  
 <span data-ttu-id="eaa81-125">[SQL Server Native Client &#40;OLE DB&#41;](../native-client/ole-db/sql-server-native-client-ole-db.md) </span><span class="sxs-lookup"><span data-stu-id="eaa81-125">[SQL Server Native Client &#40;OLE DB&#41;](../native-client/ole-db/sql-server-native-client-ole-db.md) </span></span>  
 [<span data-ttu-id="eaa81-126">Usare parametri con valori di tabella &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="eaa81-126">Use Table-Valued Parameters &#40;OLE DB&#41;</span></span>](../native-client-ole-db-how-to/use-table-valued-parameters-ole-db.md)  
  
  
