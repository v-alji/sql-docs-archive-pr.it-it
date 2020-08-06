---
title: Gestione connessione OLE DB | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- OLE DB connection manager
- data sources [Integration Services], connections
- connection managers [Integration Services], OLE DB
- connections [Integration Services], OLE DB
ms.assetid: 91e3622e-4b1a-439a-80c7-a00b90d66979
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5431de956a1039c2978688982792f190b0abc544
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629971"
---
# <a name="ole-db-connection-manager"></a><span data-ttu-id="1b610-102">gestione connessione OLE DB</span><span class="sxs-lookup"><span data-stu-id="1b610-102">OLE DB Connection Manager</span></span>
  <span data-ttu-id="1b610-103">Una gestione connessione OLE DB consente la connessione di un pacchetto a un'origine dati tramite un provider OLE DB.</span><span class="sxs-lookup"><span data-stu-id="1b610-103">An OLE DB connection manager enables a package to connect to a data source by using an OLE DB provider.</span></span> <span data-ttu-id="1b610-104">In una gestione connessione OLE DB tramite che si connette a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , ad esempio, è possibile usare il provider [!INCLUDE[msCoName](../../includes/msconame-md.md)] OLE DB per [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1b610-104">For example, an OLE DB connection manager that connects to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] can use the [!INCLUDE[msCoName](../../includes/msconame-md.md)] OLE DB Provider for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1b610-105">Il provider OLE DB di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client 11.0 non supporta le nuove parole chiave per le stringhe di connessione (MultiSubnetFailover=True) per il clustering di failover su più subnet.</span><span class="sxs-lookup"><span data-stu-id="1b610-105">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client 11.0 OLEDB provider does not support the new connection string key words (MultiSubnetFailover=True) for Multi-Subnet Failover Clustering.</span></span> <span data-ttu-id="1b610-106">Per ulteriori informazioni, vedere le [Note sulla versione di SQL Server](https://go.microsoft.com/fwlink/?LinkId=247824) e il post di Blog relativo al failover su più [subnet AlwaysOn e SSIS](https://www.mattmasson.com/2012/03/alwayson-multi-subnet-failover-and-ssis/)su www.mattmasson.com.</span><span class="sxs-lookup"><span data-stu-id="1b610-106">For more information, see the [SQL Server Release  Notes](https://go.microsoft.com/fwlink/?LinkId=247824) and the blog post, [AlwaysOn Multi-Subnet Failover and SSIS](https://www.mattmasson.com/2012/03/alwayson-multi-subnet-failover-and-ssis/), on www.mattmasson.com.</span></span>  
  
 <span data-ttu-id="1b610-107">Diverse [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] attività e componenti del flusso di dati utilizzano una gestione connessione OLE DB.</span><span class="sxs-lookup"><span data-stu-id="1b610-107">Several [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] tasks and data flow components use an OLE DB connection manager.</span></span> <span data-ttu-id="1b610-108">L'origine e la destinazione OLE DB, ad esempio, usano questa gestione connessione per estrarre e caricare i dati, mentre l'attività Esegui SQL può usarla per connettersi a un database di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per l'esecuzione delle query.</span><span class="sxs-lookup"><span data-stu-id="1b610-108">For example, the OLE DB source and OLE DB destination use this connection manager to extract and load data, and the Execute SQL task can use this connection manager to connect to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database to run queries.</span></span>  
  
 <span data-ttu-id="1b610-109">La gestione connessione OLE DB viene inoltre utilizzata per accedere alle origini dei dati OLE DB nelle attività personalizzate scritte in codice non gestito che utilizza un linguaggio quale C++.</span><span class="sxs-lookup"><span data-stu-id="1b610-109">The OLE DB connection manager is also used to access OLE DB data sources in custom tasks written in unmanaged code that uses a language such as C++.</span></span>  
  
 <span data-ttu-id="1b610-110">Quando si aggiunge una gestione connessione OLE DB a un pacchetto, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] crea una gestione connessione che in fase di esecuzione verrà risolta in una connessione OLE DB, imposta le proprietà di tale gestione connessione e quindi la aggiunge alla raccolta `Connections` del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="1b610-110">When you add an OLE DB connection manager to a package, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] creates a connection manager that will resolve to an OLE DB connection at run time, sets the connection manager properties, and adds the connection manager to the `Connections` collection on the package.</span></span>  
  
 <span data-ttu-id="1b610-111">La proprietà `ConnectionManagerType` della gestione connessione viene impostata su `OLEDB`.</span><span class="sxs-lookup"><span data-stu-id="1b610-111">The `ConnectionManagerType` property of the connection manager is set to `OLEDB`.</span></span>  
  
 <span data-ttu-id="1b610-112">Per configurare la gestione connessione OLE DB, procedere nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="1b610-112">The OLE DB connection manager can be configured in the following ways:</span></span>  
  
-   <span data-ttu-id="1b610-113">Specificare una stringa di connessione configurata in modo da soddisfare i requisiti del provider selezionato.</span><span class="sxs-lookup"><span data-stu-id="1b610-113">Provide a specific connection string configured to meet the requirements of the selected provider.</span></span>  
  
-   <span data-ttu-id="1b610-114">Se richiesto dal provider, includere il nome dell'origine dei dati a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="1b610-114">Depending on the provider, include the name of the data source to connect to.</span></span>  
  
-   <span data-ttu-id="1b610-115">Specificare le credenziali di sicurezza come previsto dal provider selezionato.</span><span class="sxs-lookup"><span data-stu-id="1b610-115">Provide security credentials as appropriate for the selected provider.</span></span>  
  
-   <span data-ttu-id="1b610-116">Indicare se la connessione creata dalla gestione connessione deve essere mantenuta in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="1b610-116">Indicate whether the connection that is created from the connection manager is retained at run time.</span></span>  
  
## <a name="logging"></a><span data-ttu-id="1b610-117">Registrazione</span><span class="sxs-lookup"><span data-stu-id="1b610-117">Logging</span></span>  
 <span data-ttu-id="1b610-118">È possibile registrare le chiamate eseguite dalla gestione connessione OLE DB a provider di dati esterni.</span><span class="sxs-lookup"><span data-stu-id="1b610-118">You can log the calls that the OLE DB connection manager makes to external data providers.</span></span> <span data-ttu-id="1b610-119">Questa nuova funzionalità di registrazione può essere utilizzata per risolvere i problemi relativi alle connessioni stabilite dalla gestione connessione OLE DB a origini dati esterne.</span><span class="sxs-lookup"><span data-stu-id="1b610-119">You can use this logging capability to troubleshoot the connections that the OLE DB connection manager makes to external data sources.</span></span> <span data-ttu-id="1b610-120">Per registrare le chiamate eseguite dalla gestione connessione OLE DB a provider di dati esterni, abilitare la registrazione dei pacchetti e selezionare l'evento **Diagnostic** a livello di pacchetto.</span><span class="sxs-lookup"><span data-stu-id="1b610-120">To log the calls that the OLE DB connection manager makes to external data providers, enable package logging and select the **Diagnostic** event at the package level.</span></span> <span data-ttu-id="1b610-121">Per altre informazioni, vedere [Risoluzione dei problemi relativi agli strumenti per l'esecuzione del pacchetto](../troubleshooting/troubleshooting-tools-for-package-execution.md).</span><span class="sxs-lookup"><span data-stu-id="1b610-121">For more information, see [Troubleshooting Tools for Package Execution](../troubleshooting/troubleshooting-tools-for-package-execution.md).</span></span>  
  
## <a name="configuration-of-the-oledb-connection-manager"></a><span data-ttu-id="1b610-122">Configurazione della gestione connessione OLEDB</span><span class="sxs-lookup"><span data-stu-id="1b610-122">Configuration of the OLEDB Connection Manager</span></span>  
 <span data-ttu-id="1b610-123">È possibile impostare le proprietà tramite Progettazione [!INCLUDE[ssIS](../../includes/ssis-md.md)] o a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="1b610-123">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span> <span data-ttu-id="1b610-124">Per altre informazioni sulle proprietà che è possibile impostare in Progettazione [!INCLUDE[ssIS](../../includes/ssis-md.md)] , vedere [Configura gestione connessione OLE DB](../configure-ole-db-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="1b610-124">For more information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, see [Configure OLE DB Connection Manager](../configure-ole-db-connection-manager.md).</span></span> <span data-ttu-id="1b610-125">Per informazioni sulla configurazione di una gestione connessione a livello di programmazione, vedere la documentazione per la classe **T:Microsoft.SqlServer.Dts.Runtime.ConnectionManager** nella Guida per gli sviluppatori.</span><span class="sxs-lookup"><span data-stu-id="1b610-125">For information about configuring a connection manager programmatically, see the documentation for **T:Microsoft.SqlServer.Dts.Runtime.ConnectionManager** class in the Developer Guide.</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="1b610-126">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="1b610-126">Related Content</span></span>  
  
-   <span data-ttu-id="1b610-127">Articolo del wiki, [SSIS con connettori Oracle](https://go.microsoft.com/fwlink/?LinkId=220670) in social.technet.Microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="1b610-127">Wiki article, [SSIS with Oracle Connectors](https://go.microsoft.com/fwlink/?LinkId=220670) on social.technet.microsoft.com.</span></span>  
  
-   <span data-ttu-id="1b610-128">Articolo tecnico [Connection Strings for OLE DB Providers](https://go.microsoft.com/fwlink/?LinkId=220744)(Stringhe di connessione per i provider OLE DB) nel sito Web carlprothman.net.</span><span class="sxs-lookup"><span data-stu-id="1b610-128">Technical article, [Connection Strings for OLE DB Providers](https://go.microsoft.com/fwlink/?LinkId=220744), on carlprothman.net.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b610-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1b610-129">See Also</span></span>  
 <span data-ttu-id="1b610-130">[Origine OLE DB](../data-flow/ole-db-source.md) </span><span class="sxs-lookup"><span data-stu-id="1b610-130">[OLE DB Source](../data-flow/ole-db-source.md) </span></span>  
 <span data-ttu-id="1b610-131">[Destinazione OLE DB](../data-flow/ole-db-destination.md) </span><span class="sxs-lookup"><span data-stu-id="1b610-131">[OLE DB Destination](../data-flow/ole-db-destination.md) </span></span>  
 <span data-ttu-id="1b610-132">[Attività Esegui SQL](../control-flow/execute-sql-task.md) </span><span class="sxs-lookup"><span data-stu-id="1b610-132">[Execute SQL Task](../control-flow/execute-sql-task.md) </span></span>  
 [<span data-ttu-id="1b610-133">Connessioni in Integration Services &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="1b610-133">Integration Services &#40;SSIS&#41; Connections</span></span>](integration-services-ssis-connections.md)  
  
  
