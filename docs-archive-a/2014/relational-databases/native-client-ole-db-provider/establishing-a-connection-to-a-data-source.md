---
title: Avvio di una connessione a un'origine dati | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- data sources [SQL Server Native Client]
- connections [SQL Server Native Client]
- SQL Server Native Client OLE DB provider, data source connections
- CoCreateInstance method
- OLE DB data sources [SQL Server Native Client]
ms.assetid: 7ebd1394-cc8d-4bcf-92f3-c374a26e7ba0
author: rothja
ms.author: jroth
ms.openlocfilehash: f88454339ee932c38655819cce475ab52d79975f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636045"
---
# <a name="establishing-a-connection-to-a-data-source"></a><span data-ttu-id="cf16d-102">Avvio di una connessione a un'origine dati</span><span class="sxs-lookup"><span data-stu-id="cf16d-102">Establishing a Connection to a Data Source</span></span>
  <span data-ttu-id="cf16d-103">Per accedere al [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider OLE DB di Native client, il consumer deve prima creare un'istanza di un oggetto origine dati chiamando il metodo **CoCreateInstance** .</span><span class="sxs-lookup"><span data-stu-id="cf16d-103">To access the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider, the consumer must first create an instance of a data source object by calling the **CoCreateInstance** method.</span></span> <span data-ttu-id="cf16d-104">Un identificatore univoco di classe (CLSID) identifica ogni provider OLE DB.</span><span class="sxs-lookup"><span data-stu-id="cf16d-104">A unique class identifier (CLSID) identifies each OLE DB provider.</span></span> <span data-ttu-id="cf16d-105">Per il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native client, l'identificatore di classe è CLSID_SQLNCLI10.</span><span class="sxs-lookup"><span data-stu-id="cf16d-105">For the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider, the class identifier is CLSID_SQLNCLI10.</span></span> <span data-ttu-id="cf16d-106">È inoltre possibile utilizzare il simbolo SQLNCLI_CLSID che verrà risolto nel [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider OLE DB di Native client utilizzato nel sqlncli. h a cui si fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="cf16d-106">You can also use the symbol SQLNCLI_CLSID that will resolve to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider that is used in the sqlncli.h that you reference.</span></span>  
  
 <span data-ttu-id="cf16d-107">L'oggetto origine dati espone l'interfaccia **IDBProperties** usata dal consumer per fornire informazioni di base sull'autenticazione, ad esempio il nome del server, il nome del database, l'ID utente e la password.</span><span class="sxs-lookup"><span data-stu-id="cf16d-107">The data source object exposes the **IDBProperties** interface, which the consumer uses to provide basic authentication information such as server name, database name, user ID, and password.</span></span> <span data-ttu-id="cf16d-108">Per impostare queste proprietà, viene chiamato il metodo **IDBProperties::SetProperties**.</span><span class="sxs-lookup"><span data-stu-id="cf16d-108">The **IDBProperties::SetProperties** method is called to set these properties.</span></span>  
  
 <span data-ttu-id="cf16d-109">Se nel computer sono in esecuzione più istanze di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], il nome del server viene specificato come NomeServer\NomeIstanza.</span><span class="sxs-lookup"><span data-stu-id="cf16d-109">If there are multiple instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] running on the computer, the server name is specified as ServerName\InstanceName.</span></span>  
  
 <span data-ttu-id="cf16d-110">L'oggetto origine dati espone anche l'interfaccia **IDBInitialize**.</span><span class="sxs-lookup"><span data-stu-id="cf16d-110">The data source object also exposes the **IDBInitialize** interface.</span></span> <span data-ttu-id="cf16d-111">Dopo aver impostato le proprietà, la connessione all'origine dati viene stabilita chiamando il metodo **IDBInitialize::Initialize**.</span><span class="sxs-lookup"><span data-stu-id="cf16d-111">After the properties are set, connection to the data source is established by calling the **IDBInitialize::Initialize** method.</span></span> <span data-ttu-id="cf16d-112">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="cf16d-112">For example:</span></span>  
  
```  
CoCreateInstance(CLSID_SQLNCLI10,   
                 NULL,   
                 CLSCTX_INPROC_SERVER,  
                 IID_IDBInitialize,   
                 (void **) &pIDBInitialize)  
```  
  
 <span data-ttu-id="cf16d-113">Questa chiamata a **CoCreateInstance** crea un singolo oggetto della classe associata a CLSID_SQLNCLI10 (CSLID associato ai dati e al codice che verranno usati per creare l'oggetto).</span><span class="sxs-lookup"><span data-stu-id="cf16d-113">This call to **CoCreateInstance** creates a single object of the class associated with CLSID_SQLNCLI10 (CSLID associated with the data and code that will be used to create the object).</span></span> <span data-ttu-id="cf16d-114">IID_IDBInitialize è un riferimento all'identificatore dell'interfaccia (**IDBInitialize**) da usare per comunicare con l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="cf16d-114">IID_IDBInitialize is a reference to the identifier of the interface (**IDBInitialize**) to be used to communicate with the object.</span></span>  
  
 <span data-ttu-id="cf16d-115">Di seguito è riportata una funzione di esempio che inizializza e stabilisce una connessione all'origine dati.</span><span class="sxs-lookup"><span data-stu-id="cf16d-115">The following is a sample function that initializes and establishes a connection to the data source.</span></span>  
  
```  
void InitializeAndEstablishConnection() {  
   // Initialize the COM library.  
   CoInitialize(NULL);  
  
   // Obtain access to the SQL Server Native Client OLE DB provider.  
   hr = CoCreateInstance(CLSID_SQLNCLI10,   
                         NULL,   
                         CLSCTX_INPROC_SERVER,  
                         IID_IDBInitialize,   
                         (void **) &pIDBInitialize);  
   // Initialize property values needed to establish connection.  
   for (i = 0 ; i < 4 ; i++)   
      VariantInit(&InitProperties[i].vValue);  
  
   // Server name.  
   // See DBPROP structure for more information on InitProperties  
   InitProperties[0].dwPropertyID  = DBPROP_INIT_DATASOURCE;  
   InitProperties[0].vValue.vt    = VT_BSTR;  
   InitProperties[0].vValue.bstrVal=   
                     SysAllocString(L"Server");  
   InitProperties[0].dwOptions    = DBPROPOPTIONS_REQUIRED;  
   InitProperties[0].colid       = DB_NULLID;  
  
   // Database.  
   InitProperties[1].dwPropertyID  = DBPROP_INIT_CATALOG;  
   InitProperties[1].vValue.vt    = VT_BSTR;  
   InitProperties[1].vValue.bstrVal= SysAllocString(L"database");  
   InitProperties[1].dwOptions    = DBPROPOPTIONS_REQUIRED;  
   InitProperties[1].colid       = DB_NULLID;  
  
   // Username (login).  
   InitProperties[2].dwPropertyID  = DBPROP_AUTH_INTEGRATED;  
   InitProperties[2].vValue.vt    = VT_BSTR;  
   InitProperties[2].vValue.bstrVal= SysAllocString(L"SSPI");  
   InitProperties[2].dwOptions    = DBPROPOPTIONS_REQUIRED;  
   InitProperties[2].colid       = DB_NULLID;  
   InitProperties[3].dwOptions    = DBPROPOPTIONS_REQUIRED;  
   InitProperties[3].colid       = DB_NULLID;  
  
   // Construct the DBPROPSET structure(rgInitPropSet). The   
   // DBPROPSET structure is used to pass an array of DBPROP   
   // structures (InitProperties) to the SetProperties method.  
   rgInitPropSet[0].guidPropertySet = DBPROPSET_DBINIT;  
   rgInitPropSet[0].cProperties   = 4;  
   rgInitPropSet[0].rgProperties   = InitProperties;  
  
   // Set initialization properties.  
   hr = pIDBInitialize->QueryInterface(IID_IDBProperties,   
                           (void **)&pIDBProperties);  
   hr = pIDBProperties->SetProperties(1, rgInitPropSet);   
   pIDBProperties->Release();  
  
   // Now establish the connection to the data source.  
   pIDBInitialize->Initialize();  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="cf16d-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cf16d-116">See Also</span></span>  
 [<span data-ttu-id="cf16d-117">Creazione di un'applicazione del provider OLE DB di SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="cf16d-117">Creating a SQL Server Native Client OLE DB Provider Application</span></span>](creating-a-sql-server-native-client-ole-db-provider-application.md)  
  
  
