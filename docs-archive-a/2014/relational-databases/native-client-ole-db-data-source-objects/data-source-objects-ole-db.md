---
title: Oggetti di origine dati (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- data access [SQL Server Native Client], data source objects
- SQL Server Native Client, data source objects
- SQLNCLI, data source objects
- SQL Server Native Client OLE DB provider, data source objects
- OLE DB data source objects [SQL Server Native Client]
- data source objects [OLE DB]
- CLSID
ms.assetid: c1d4ed20-ad3b-4e33-a26b-38d7517237b7
author: rothja
ms.author: jroth
ms.openlocfilehash: 9cf3f0b0308d655b50149c174547c19966f550ba
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711908"
---
# <a name="data-source-objects-ole-db"></a><span data-ttu-id="af49f-102">Oggetti origine dati (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="af49f-102">Data Source Objects (OLE DB)</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="af49f-103">Native client usa il termine origine dati per il set di interfacce di OLE DB utilizzate per stabilire un collegamento a un archivio dati, ad esempio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="af49f-103">Native Client uses the term data source for the set of OLE DB interfaces used to establish a link to a data store, such as [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="af49f-104">La creazione di un'istanza dell'oggetto origine dati del provider è la prima attività di un [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] consumer di Native Client.</span><span class="sxs-lookup"><span data-stu-id="af49f-104">Creating an instance of the data source object of the provider is the first task of a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client consumer.</span></span>  
  
 <span data-ttu-id="af49f-105">Ogni provider OLE DB dichiara un identificatore di classe (CLSID) per se stesso.</span><span class="sxs-lookup"><span data-stu-id="af49f-105">Every OLE DB provider declares a class identifier (CLSID) for itself.</span></span> <span data-ttu-id="af49f-106">Il CLSID per il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native Client è il GUID C/C++ CLSID_SQLNCLI10 (il simbolo SQLNCLI_CLSID verrà risolto nel ProgID corretto nel file sqlncli. h a cui si fa riferimento).</span><span class="sxs-lookup"><span data-stu-id="af49f-106">The CLSID for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider is the C/C++ GUID CLSID_SQLNCLI10 (the symbol SQLNCLI_CLSID will resolve to the correct progid in the sqlncli.h file that you reference).</span></span> <span data-ttu-id="af49f-107">Con il CLSID, il consumer usa la funzione OLE **CoCreateInstance** per produrre un'istanza dell'oggetto origine dati.</span><span class="sxs-lookup"><span data-stu-id="af49f-107">With the CLSID, the consumer uses the OLE **CoCreateInstance** function to manufacture an instance of the data source object.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="af49f-108">Native Client è un server in-process.</span><span class="sxs-lookup"><span data-stu-id="af49f-108">Native Client is an in-process server.</span></span> <span data-ttu-id="af49f-109">Le istanze di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB oggetti provider vengono creati utilizzando la macro CLSCTX_INPROC_SERVER per indicare il contesto eseguibile.</span><span class="sxs-lookup"><span data-stu-id="af49f-109">Instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider objects are created using the CLSCTX_INPROC_SERVER macro to indicate the executable context.</span></span>  
  
 <span data-ttu-id="af49f-110">L' [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] oggetto origine dati del provider OLE DB di Native Client espone le interfacce di inizializzazione OLE DB che consentono al consumer di connettersi ai [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database esistenti.</span><span class="sxs-lookup"><span data-stu-id="af49f-110">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider data source object exposes the OLE DB initialization interfaces that allow the consumer to connect to existing [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases.</span></span>  
  
 <span data-ttu-id="af49f-111">Ogni connessione effettuata tramite il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native Client imposta automaticamente queste opzioni:</span><span class="sxs-lookup"><span data-stu-id="af49f-111">Every connection made through the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider sets these options automatically:</span></span>  
  
-   <span data-ttu-id="af49f-112">SET ANSI_WARNINGS ON</span><span class="sxs-lookup"><span data-stu-id="af49f-112">SET ANSI_WARNINGS ON</span></span>  
  
-   <span data-ttu-id="af49f-113">SET ANSI_NULLS ON</span><span class="sxs-lookup"><span data-stu-id="af49f-113">SET ANSI_NULLS ON</span></span>  
  
-   <span data-ttu-id="af49f-114">SET ANSI_PADDING ON</span><span class="sxs-lookup"><span data-stu-id="af49f-114">SET ANSI_PADDING ON</span></span>  
  
-   <span data-ttu-id="af49f-115">SET ANSI_NULL_DFLT_ON ON</span><span class="sxs-lookup"><span data-stu-id="af49f-115">SET ANSI_NULL_DFLT_ON ON</span></span>  
  
-   <span data-ttu-id="af49f-116">SET QUOTED_IDENTIFIER ON</span><span class="sxs-lookup"><span data-stu-id="af49f-116">SET QUOTED_IDENTIFIER ON</span></span>  
  
-   <span data-ttu-id="af49f-117">SET CONCAT_OF_NULL_YIELDS_NULL ON</span><span class="sxs-lookup"><span data-stu-id="af49f-117">SET CONCAT_OF_NULL_YIELDS_NULL ON</span></span>  
  
 <span data-ttu-id="af49f-118">Questo esempio usa la macro identificatore di classe per creare un [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] oggetto origine dati del provider OLE DB di Native client e ottenere un riferimento all'interfaccia **IDBInitialize** .</span><span class="sxs-lookup"><span data-stu-id="af49f-118">This example uses the class identifier macro to create a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider data source object and get a reference to its **IDBInitialize** interface.</span></span>  
  
```  
IDBInitialize*   pIDBInitialize;  
HRESULT          hr;  
  
hr = CoCreateInstance(CLSID_SQLNCLI10, NULL, CLSCTX_INPROC_SERVER,  
    IID_IDBInitialize, (void**) &pIDBInitialize);  
  
if (SUCCEEDED(hr))  
{  
    //  Perform necessary processing with the interface.  
    pIDBInitialize->Uninitialize();  
    pIDBInitialize->Release();  
}  
else  
{  
    // Display error from CoCreateInstance.  
}  
```  
  
 <span data-ttu-id="af49f-119">Con la corretta creazione di un'istanza di un [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] oggetto origine dati del provider OLE DB di Native client, l'applicazione consumer può continuare inizializzando l'origine dati e creando sessioni.</span><span class="sxs-lookup"><span data-stu-id="af49f-119">With successful creation of an instance of a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider data source object, the consumer application can continue by initializing the data source and creating sessions.</span></span> <span data-ttu-id="af49f-120">Le sessioni OLE DB presentano le interfacce che consentono l'accesso ai dati e la relativa modifica.</span><span class="sxs-lookup"><span data-stu-id="af49f-120">OLE DB sessions present the interfaces that allow data access and manipulation.</span></span>  
  
 <span data-ttu-id="af49f-121">Il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native client effettua la prima connessione a un'istanza specificata di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] come parte di un'inizializzazione dell'origine dati completata correttamente.</span><span class="sxs-lookup"><span data-stu-id="af49f-121">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider makes its first connection to a specified instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] as part of a successful data source initialization.</span></span> <span data-ttu-id="af49f-122">La connessione viene mantenuta a condizione che venga mantenuto un riferimento in una delle interfacce di inizializzazione dell'origine dati o fino a quando non viene chiamato il metodo **IDBInitialize::Uninitialize**.</span><span class="sxs-lookup"><span data-stu-id="af49f-122">The connection is maintained as long as a reference is maintained on any data source initialization interface, or until the **IDBInitialize::Uninitialize** method is called.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="af49f-123">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="af49f-123">In This Section</span></span>  
  
-   [<span data-ttu-id="af49f-124">Proprietà delle origini dati &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="af49f-124">Data Source Properties &#40;OLE DB&#41;</span></span>](data-source-properties-ole-db.md)  
  
-   [<span data-ttu-id="af49f-125">Proprietà delle informazioni sulle origini dati</span><span class="sxs-lookup"><span data-stu-id="af49f-125">Data Source Information Properties</span></span>](data-source-information-properties.md)  
  
-   [<span data-ttu-id="af49f-126">Proprietà di inizializzazione e di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="af49f-126">Initialization and Authorization Properties</span></span>](initialization-and-authorization-properties.md)  
  
-   [<span data-ttu-id="af49f-127">Sessioni</span><span class="sxs-lookup"><span data-stu-id="af49f-127">Sessions</span></span>](sessions.md)  
  
-   [<span data-ttu-id="af49f-128">Proprietà di sessione</span><span class="sxs-lookup"><span data-stu-id="af49f-128">Session Properties</span></span>](session-properties-sql-server-native-client-ole-db-provider.md)  
  
-   [<span data-ttu-id="af49f-129">Oggetti origine dati persistenti</span><span class="sxs-lookup"><span data-stu-id="af49f-129">Persisted Data Source Objects</span></span>](persisted-data-source-objects.md)  
  
## <a name="see-also"></a><span data-ttu-id="af49f-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="af49f-130">See Also</span></span>  
 [<span data-ttu-id="af49f-131">SQL Server Native Client &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="af49f-131">SQL Server Native Client &#40;OLE DB&#41;</span></span>](../native-client/ole-db/sql-server-native-client-ole-db.md)  
  
  
