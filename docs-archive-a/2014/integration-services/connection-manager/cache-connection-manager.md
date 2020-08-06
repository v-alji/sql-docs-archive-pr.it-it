---
title: Gestione connessione della cache | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Cache connection manager
ms.assetid: bdc92038-3720-4795-8a5c-79b963f2c952
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b8a7cc8bbe9e93c385fca6257e0be2e79bd3148a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628921"
---
# <a name="cache-connection-manager"></a><span data-ttu-id="cc186-102">gestione connessione della cache</span><span class="sxs-lookup"><span data-stu-id="cc186-102">Cache Connection Manager</span></span>
  <span data-ttu-id="cc186-103">La gestione connessione della cache consente di leggere i dati dalla trasformazione cache o da un file di cache (con estensione caw) e di salvarli in un file di cache.</span><span class="sxs-lookup"><span data-stu-id="cc186-103">The Cache connection manager reads data from the Cache transform or from a cache file (.caw), and can save the data to a cache file.</span></span> <span data-ttu-id="cc186-104">Se si configura la gestione connessione della cache in modo da utilizzare un file di cache, i dati sono archiviati sempre in memoria.</span><span class="sxs-lookup"><span data-stu-id="cc186-104">Whether you configure the Cache connection manager to use a cache file, the data is always stored in memory.</span></span>  
  
 <span data-ttu-id="cc186-105">La trasformazione Trasformazione cache consente di scrivere i dati da un'origine dati connessa nel flusso di dati a una gestione connessione della cache.</span><span class="sxs-lookup"><span data-stu-id="cc186-105">The Cache Transform transformation writes data from a connected data source in the data flow to a Cache connection manager.</span></span> <span data-ttu-id="cc186-106">La trasformazione Ricerca in un pacchetto consente di effettuare ricerche nei dati.</span><span class="sxs-lookup"><span data-stu-id="cc186-106">The Lookup transformation in a package performs lookups on the data.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cc186-107">I tipi di dati BLOB (oggetto binario di grandi dimensioni), ovvero DT_TEXT, DT_NTEXT e DT_IMAGE, non sono supportati nella Gestione connessione cache.</span><span class="sxs-lookup"><span data-stu-id="cc186-107">The Cache connection manager does not support the Binary Large Object (BLOB) data types DT_TEXT, DT_NTEXT, and DT_IMAGE.</span></span> <span data-ttu-id="cc186-108">Se il set di dati di riferimento contiene un tipo di dati BLOB, il componente avrà esito negativo quando viene eseguito il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="cc186-108">If the reference dataset contains a BLOB data type, the component will fail when you run the package.</span></span> <span data-ttu-id="cc186-109">È possibile utilizzare **Editor gestione connessione cache** per modificare i tipi di dati di colonna.</span><span class="sxs-lookup"><span data-stu-id="cc186-109">You can use the **Cache Connection Manager Editor** to modify column data types.</span></span> <span data-ttu-id="cc186-110">Per altre informazioni, vedere [Editor gestione connessione cache](../cache-connection-manager-editor.md).</span><span class="sxs-lookup"><span data-stu-id="cc186-110">For more information, see [Cache Connection Manager Editor](../cache-connection-manager-editor.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cc186-111">Il livello di protezione del pacchetto non si applica al file di cache.</span><span class="sxs-lookup"><span data-stu-id="cc186-111">The protection level of the package does not apply to the cache file.</span></span> <span data-ttu-id="cc186-112">Se il file di cache contiene informazioni riservate, utilizzare un elenco di controllo di accesso (ACL) per limitare l'accesso al percorso o alla cartella nella quale verrà archiviato il file.</span><span class="sxs-lookup"><span data-stu-id="cc186-112">If the cache file contains sensitive information, use an access control list (ACL) to restrict access to the location or folder in which you store the file.</span></span> <span data-ttu-id="cc186-113">È consigliabile consentire l'accesso solo a determinati account.</span><span class="sxs-lookup"><span data-stu-id="cc186-113">You should enable access only to certain accounts.</span></span> <span data-ttu-id="cc186-114">Per altre informazioni, vedere [Accesso ai file utilizzati dai pacchetti](../access-to-files-used-by-packages.md).</span><span class="sxs-lookup"><span data-stu-id="cc186-114">For more information, see [Access to Files Used by Packages](../access-to-files-used-by-packages.md).</span></span>  
  
## <a name="configuration-of-the-cache-connection-manager"></a><span data-ttu-id="cc186-115">Configurazione della gestione connessione cache</span><span class="sxs-lookup"><span data-stu-id="cc186-115">Configuration of the Cache Connection Manager</span></span>  
 <span data-ttu-id="cc186-116">Per configurare la gestione connessione cache, procedere nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="cc186-116">You can configure the Cache connection manager in the following ways:</span></span>  
  
-   <span data-ttu-id="cc186-117">Indicare se utilizzare un file di cache.</span><span class="sxs-lookup"><span data-stu-id="cc186-117">Indicate whether to use a cache file.</span></span>  
  
     <span data-ttu-id="cc186-118">Se la gestione connessione della cache viene configurata in modo da utilizzare un file di cache, la gestione connessione eseguirà una delle seguenti azioni:</span><span class="sxs-lookup"><span data-stu-id="cc186-118">If you configure the cache connection manager to use a cache file, the connection manager will do one of the following actions:</span></span>  
  
    -   <span data-ttu-id="cc186-119">Salvare i dati in un file quando la trasformazione Cache viene configurata in modo da scrivere i dati da un'origine dati nel flusso di dati alla gestione connessione della cache.</span><span class="sxs-lookup"><span data-stu-id="cc186-119">Save data to the file when a Cache Transform transformation is configured to write data from a data source in the data flow to the Cache connection manager.</span></span>  
  
    -   <span data-ttu-id="cc186-120">Leggere i dati dal file di cache.</span><span class="sxs-lookup"><span data-stu-id="cc186-120">Read data from the cache file.</span></span>  
  
     <span data-ttu-id="cc186-121">Per ulteriori informazioni, vedere [Cache Transform](../data-flow/transformations/cache-transform.md).</span><span class="sxs-lookup"><span data-stu-id="cc186-121">For more information, see [Cache Transform](../data-flow/transformations/cache-transform.md).</span></span>  
  
-   <span data-ttu-id="cc186-122">Modificare i metadati per le colonne archiviate nella cache.</span><span class="sxs-lookup"><span data-stu-id="cc186-122">Change metadata for the columns stored in the cache.</span></span>  
  
-   <span data-ttu-id="cc186-123">Aggiornare il nome del file di cache in fase di esecuzione usando un'espressione per impostare la proprietà ConnectionString.</span><span class="sxs-lookup"><span data-stu-id="cc186-123">Update the cache file name at runtime by using an expression to set the ConnectionString property.</span></span> <span data-ttu-id="cc186-124">Per altre informazioni, vedere [Utilizzo delle espressioni di proprietà nei pacchetti](../expressions/use-property-expressions-in-packages.md).</span><span class="sxs-lookup"><span data-stu-id="cc186-124">For more information, see [Use Property Expressions in Packages](../expressions/use-property-expressions-in-packages.md).</span></span>  
  
 <span data-ttu-id="cc186-125">È possibile impostare le proprietà tramite Progettazione [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] o a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="cc186-125">You can set properties through [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="cc186-126">Per altre informazioni sulle proprietà che è possibile impostare in Progettazione [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , vedere [Editor gestione connessione cache](../cache-connection-manager-editor.md).</span><span class="sxs-lookup"><span data-stu-id="cc186-126">For more information about the properties that you can set in [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] Designer, see [Cache Connection Manager Editor](../cache-connection-manager-editor.md).</span></span>  
  
 <span data-ttu-id="cc186-127">Per informazioni su come configurare una gestione connessione a livello di programmazione, vedere <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> e [Aggiunta di connessioni a livello di programmazione](../building-packages-programmatically/adding-connections-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="cc186-127">For information about how to configure a connection manager programmatically, see <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> and [Adding Connections Programmatically](../building-packages-programmatically/adding-connections-programmatically.md).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="cc186-128">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="cc186-128">Related Tasks</span></span>  
 [<span data-ttu-id="cc186-129">Implementazione di una trasformazione Ricerca in modalità Full Cache utilizzando la gestione connessione della cache</span><span class="sxs-lookup"><span data-stu-id="cc186-129">Implement a Lookup Transformation in Full Cache Mode Using the Cache Connection Manager</span></span>](lookup-transformation-full-cache-mode-ole-db-connection-manager.md)  
  
  
