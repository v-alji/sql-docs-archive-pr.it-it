---
title: Editor gestione connessione della cache | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.cacheconnection.f1
ms.assetid: 0d8f9324-0c35-4eea-b06d-da3cc2426d2c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 38a858217925496d8dd937d684368bdb2e061b14
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636843"
---
# <a name="cache-connection-manager-editor"></a><span data-ttu-id="28ab3-102">Editor gestione connessione cache</span><span class="sxs-lookup"><span data-stu-id="28ab3-102">Cache Connection Manager Editor</span></span>
  <span data-ttu-id="28ab3-103">La Gestione connessione cache consente di leggere un set di dati di riferimento dalla trasformazione cache o da un file di cache (.caw) e può salvare i dati in un file di cache.</span><span class="sxs-lookup"><span data-stu-id="28ab3-103">The Cache connection manager reads a reference dataset from the Cache transform or from a cache file (.caw), and can save the data to a cache file.</span></span> <span data-ttu-id="28ab3-104">I dati vengono sempre archiviati in memoria.</span><span class="sxs-lookup"><span data-stu-id="28ab3-104">The data is always stored in memory.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="28ab3-105">I tipi di dati BLOB (oggetto binario di grandi dimensioni), ovvero DT_TEXT, DT_NTEXT e DT_IMAGE, non sono supportati nella Gestione connessione cache.</span><span class="sxs-lookup"><span data-stu-id="28ab3-105">The Cache connection manager does not support the Binary Large Object (BLOB) data types DT_TEXT, DT_NTEXT, and DT_IMAGE.</span></span> <span data-ttu-id="28ab3-106">Se il set di dati di riferimento contiene un tipo di dati BLOB, il componente avrà esito negativo quando viene eseguito il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="28ab3-106">If the reference dataset contains a BLOB data type, the component will fail when you run the package.</span></span> <span data-ttu-id="28ab3-107">È possibile utilizzare **Editor gestione connessione cache** per modificare i tipi di dati di colonna.</span><span class="sxs-lookup"><span data-stu-id="28ab3-107">You can use the **Cache Connection Manager Editor** to modify column data types.</span></span>  
  
 <span data-ttu-id="28ab3-108">La trasformazione Ricerca esegue ricerche sul set di dati di riferimento.</span><span class="sxs-lookup"><span data-stu-id="28ab3-108">The Lookup transformation performs lookups on the reference dataset.</span></span>  
  
 <span data-ttu-id="28ab3-109">La finestra di dialogo **Editor gestione connessione della cache** include le schede seguenti:</span><span class="sxs-lookup"><span data-stu-id="28ab3-109">The **Cache Connection ManagerEditor** dialog box includes the following tabs:</span></span>  
  
-   [<span data-ttu-id="28ab3-110">Scheda generale</span><span class="sxs-lookup"><span data-stu-id="28ab3-110">General tab</span></span>](#generaltab)  
  
-   [<span data-ttu-id="28ab3-111">Scheda colonne</span><span class="sxs-lookup"><span data-stu-id="28ab3-111">Columns tab</span></span>](#columnstab)  
  
 <span data-ttu-id="28ab3-112">Per ulteriori informazioni sulla gestione connessione cache, vedere [Cache Connection Manager](connection-manager/cache-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="28ab3-112">To learn more about the Cache Connection Manager, see [Cache Connection Manager](connection-manager/cache-connection-manager.md).</span></span>  
  
##  <a name="general-tab"></a><a name="generaltab"></a><span data-ttu-id="28ab3-113">Scheda generale</span><span class="sxs-lookup"><span data-stu-id="28ab3-113">General Tab</span></span>  
 <span data-ttu-id="28ab3-114">Usare la scheda **Generale** della finestra di dialogo **Editor gestione connessione della cache** per indicare se leggere la cache da un file o salvare la cache in un file.</span><span class="sxs-lookup"><span data-stu-id="28ab3-114">Use the **General** tab of the **Cache Connection ManagerEditor** dialog box to indicate whether to read the cache from a file or save the cache to a file.</span></span>  
  
### <a name="options"></a><span data-ttu-id="28ab3-115">Opzioni</span><span class="sxs-lookup"><span data-stu-id="28ab3-115">Options</span></span>  
 <span data-ttu-id="28ab3-116">**Nome gestione connessione**</span><span class="sxs-lookup"><span data-stu-id="28ab3-116">**Connection manager name**</span></span>  
 <span data-ttu-id="28ab3-117">Consente di specificare un nome univoco per la connessione cache nel flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="28ab3-117">Provide a unique name for the cache connection in the workflow.</span></span> <span data-ttu-id="28ab3-118">Il nome specificato verrà visualizzato in Progettazione [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="28ab3-118">The name provided will be displayed within [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="28ab3-119">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="28ab3-119">**Description**</span></span>  
 <span data-ttu-id="28ab3-120">Consente di aggiungere una descrizione per la connessione.</span><span class="sxs-lookup"><span data-stu-id="28ab3-120">Describe the connection.</span></span> <span data-ttu-id="28ab3-121">È consigliabile includere nella descrizione informazioni sugli scopi della connessione, in modo da ottenere pacchetti autodocumentati e semplificarne quindi la gestione.</span><span class="sxs-lookup"><span data-stu-id="28ab3-121">As a best practice, describe the connection according to its purpose, to make packages self-documenting and easier to maintain.</span></span>  
  
 <span data-ttu-id="28ab3-122">**Usa cache di file**</span><span class="sxs-lookup"><span data-stu-id="28ab3-122">**Use file cache**</span></span>  
 <span data-ttu-id="28ab3-123">Indicare se utilizzare un file di cache.</span><span class="sxs-lookup"><span data-stu-id="28ab3-123">Indicate whether to use a cache file.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="28ab3-124">Il livello di protezione del pacchetto non si applica al file di cache.</span><span class="sxs-lookup"><span data-stu-id="28ab3-124">The protection level of the package does not apply to the cache file.</span></span> <span data-ttu-id="28ab3-125">Se il file di cache contiene informazioni riservate, utilizzare un elenco di controllo di accesso (ACL) per limitare l'accesso al percorso o alla cartella nella quale verrà archiviato il file.</span><span class="sxs-lookup"><span data-stu-id="28ab3-125">If the cache file contains sensitive information, use an access control list (ACL) to restrict access to the location or folder in which you store the file.</span></span> <span data-ttu-id="28ab3-126">È consigliabile consentire l'accesso solo a determinati account.</span><span class="sxs-lookup"><span data-stu-id="28ab3-126">You should enable access only to certain accounts.</span></span> <span data-ttu-id="28ab3-127">Per altre informazioni, vedere [Accesso ai file utilizzati dai pacchetti](../../2014/integration-services/access-to-files-used-by-packages.md).</span><span class="sxs-lookup"><span data-stu-id="28ab3-127">For more information, see [Access to Files Used by Packages](../../2014/integration-services/access-to-files-used-by-packages.md).</span></span>  
  
 <span data-ttu-id="28ab3-128">Se la gestione connessione della cache viene configurata in modo da utilizzare un file di cache, la gestione connessione eseguirà una delle seguenti azioni:</span><span class="sxs-lookup"><span data-stu-id="28ab3-128">If you configure the cache connection manager to use a cache file, the connection manager will do one of the following actions:</span></span>  
  
-   <span data-ttu-id="28ab3-129">Salvare i dati in un file quando la trasformazione Cache viene configurata in modo da scrivere i dati da un'origine dati nel flusso di dati alla gestione connessione della cache.</span><span class="sxs-lookup"><span data-stu-id="28ab3-129">Save data to the file when a Cache Transform transformation is configured to write data from a data source in the data flow to the Cache connection manager.</span></span> <span data-ttu-id="28ab3-130">Per ulteriori informazioni, vedere [Cache Transform](data-flow/transformations/cache-transform.md).</span><span class="sxs-lookup"><span data-stu-id="28ab3-130">For more information, see [Cache Transform](data-flow/transformations/cache-transform.md).</span></span>  
  
-   <span data-ttu-id="28ab3-131">Leggere i dati dal file di cache.</span><span class="sxs-lookup"><span data-stu-id="28ab3-131">Read data from the cache file.</span></span>  
  
 <span data-ttu-id="28ab3-132">**Nome file**</span><span class="sxs-lookup"><span data-stu-id="28ab3-132">**File name**</span></span>  
 <span data-ttu-id="28ab3-133">Digitare il percorso e il nome file del file di cache.</span><span class="sxs-lookup"><span data-stu-id="28ab3-133">Type the path and file name of the cache file.</span></span>  
  
 <span data-ttu-id="28ab3-134">**Sfoglia**</span><span class="sxs-lookup"><span data-stu-id="28ab3-134">**Browse**</span></span>  
 <span data-ttu-id="28ab3-135">Individuare il file di cache.</span><span class="sxs-lookup"><span data-stu-id="28ab3-135">Locate the cache file.</span></span>  
  
 <span data-ttu-id="28ab3-136">**Aggiorna metadati**</span><span class="sxs-lookup"><span data-stu-id="28ab3-136">**Refresh Metadata**</span></span>  
 <span data-ttu-id="28ab3-137">Eliminare i metadati della colonna nella Gestione connessione cache e ripopolare la Gestione connessione cache con i metadati della colonna da un file di cache selezionato.</span><span class="sxs-lookup"><span data-stu-id="28ab3-137">Delete the column metadata in the Cache connection manager and repopulate the Cache connection manager with column metadata from a selected cache file.</span></span>  
  
##  <a name="columns-tab"></a><a name="columnstab"></a><span data-ttu-id="28ab3-138">Scheda colonne</span><span class="sxs-lookup"><span data-stu-id="28ab3-138">Columns Tab</span></span>  
 <span data-ttu-id="28ab3-139">Utilizzare la scheda **Colonne** della finestra di dialogo **Editor gestione connessione cache** per configurare le proprietà di ciascuna colonna nella cache.</span><span class="sxs-lookup"><span data-stu-id="28ab3-139">Use the **Columns** tab of the **Cache Connection Manager Editor** dialog box to configure the properties of each column in the cache.</span></span>  
  
### <a name="options"></a><span data-ttu-id="28ab3-140">Opzioni</span><span class="sxs-lookup"><span data-stu-id="28ab3-140">Options</span></span>  
 <span data-ttu-id="28ab3-141">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="28ab3-141">**Column**</span></span>  
 <span data-ttu-id="28ab3-142">Consente di specificare il nome della colonna.</span><span class="sxs-lookup"><span data-stu-id="28ab3-142">Specify the column name.</span></span>  
  
 <span data-ttu-id="28ab3-143">**Posizione dell'indice**</span><span class="sxs-lookup"><span data-stu-id="28ab3-143">**Index Position**</span></span>  
 <span data-ttu-id="28ab3-144">Consente di specificare quali colonne sono colonne dell'indice specificando la relativa posizione di ogni colonna.</span><span class="sxs-lookup"><span data-stu-id="28ab3-144">Specify which columns are index columns by specifying the index position of each column.</span></span> <span data-ttu-id="28ab3-145">L'indice è un insieme di una o più colonne.</span><span class="sxs-lookup"><span data-stu-id="28ab3-145">The index is a collection of one or more columns.</span></span>  
  
 <span data-ttu-id="28ab3-146">Per le colonne non dell'indice, la posizione è 0.</span><span class="sxs-lookup"><span data-stu-id="28ab3-146">For non-index columns, the index position is 0.</span></span>  
  
 <span data-ttu-id="28ab3-147">Per le colonne di indice, la posizione di indice è un numero sequenziale e positivo.</span><span class="sxs-lookup"><span data-stu-id="28ab3-147">For index columns, the index position is a sequential, positive number.</span></span> <span data-ttu-id="28ab3-148">Questo numero indica l'ordine con cui la trasformazione Ricerca confronta le righe nel set di dati di riferimento alle righe nell'origine dei dati di input.</span><span class="sxs-lookup"><span data-stu-id="28ab3-148">This number indicates the order in which the Lookup transformation compares rows in the reference dataset to rows in the input data source.</span></span> <span data-ttu-id="28ab3-149">La colonna con più valori univoci deve disporre della posizione di indice più bassa.</span><span class="sxs-lookup"><span data-stu-id="28ab3-149">The column with the most unique values should have the lowest index position.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="28ab3-150">Quando la trasformazione Ricerca viene configurata per utilizzare una Gestione connessione cache, è possibile eseguire il mapping solo delle colonne di indice nel set di dati di riferimento alle colonne di input.</span><span class="sxs-lookup"><span data-stu-id="28ab3-150">When the Lookup transformation is configured to use a Cache connection manager, only index columns in the reference dataset can be mapped to input columns.</span></span> <span data-ttu-id="28ab3-151">Inoltre, è necessario eseguire il mapping di tutte le colonne di indice.</span><span class="sxs-lookup"><span data-stu-id="28ab3-151">Also, all index columns must be mapped.</span></span>  
  
 <span data-ttu-id="28ab3-152">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="28ab3-152">**Type**</span></span>  
 <span data-ttu-id="28ab3-153">Consente di specificare il tipo di dati della colonna.</span><span class="sxs-lookup"><span data-stu-id="28ab3-153">Specify the data type of the column.</span></span>  
  
 `Length`  
 <span data-ttu-id="28ab3-154">Specifica il tipo di dati della colonna.</span><span class="sxs-lookup"><span data-stu-id="28ab3-154">Specifies the column data type.</span></span> <span data-ttu-id="28ab3-155">Se applicabile al tipo di dati, è possibile aggiornare `Length`.</span><span class="sxs-lookup"><span data-stu-id="28ab3-155">If applicable to the data type, you can update `Length`.</span></span>  
  
 `Precision`  
 <span data-ttu-id="28ab3-156">Specifica la precisione per certi tipi di dati di colonna.</span><span class="sxs-lookup"><span data-stu-id="28ab3-156">Specifies the precision for certain column data types.</span></span> <span data-ttu-id="28ab3-157">La precisione è il numero di cifre in un numero.</span><span class="sxs-lookup"><span data-stu-id="28ab3-157">Precision is the number of digits in a number.</span></span> <span data-ttu-id="28ab3-158">Se applicabile al tipo di dati, è possibile aggiornare `Precision`.</span><span class="sxs-lookup"><span data-stu-id="28ab3-158">If applicable to the data type, you can update `Precision`.</span></span>  
  
 `Scale`  
 <span data-ttu-id="28ab3-159">Specifica la scala per certi tipi di dati di colonna.</span><span class="sxs-lookup"><span data-stu-id="28ab3-159">Specifies the scale for certain column data types.</span></span> <span data-ttu-id="28ab3-160">La scala è il numero di cifre a destra della virgola decimale in un numero.</span><span class="sxs-lookup"><span data-stu-id="28ab3-160">Scale is the number of digits to the right of the decimal point in a number.</span></span> <span data-ttu-id="28ab3-161">Se applicabile al tipo di dati, è possibile aggiornare `Scale`.</span><span class="sxs-lookup"><span data-stu-id="28ab3-161">If applicable to the data type, you can update `Scale`.</span></span>  
  
 `Code Page`  
 <span data-ttu-id="28ab3-162">Specifica la tabella codici per il tipo di colonna.</span><span class="sxs-lookup"><span data-stu-id="28ab3-162">Specifies the code page for the column type.</span></span> <span data-ttu-id="28ab3-163">Se applicabile al tipo di dati, è possibile aggiornare `Code Page`.</span><span class="sxs-lookup"><span data-stu-id="28ab3-163">If applicable to the data type, you can update `Code Page`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28ab3-164">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="28ab3-164">See Also</span></span>  
 [<span data-ttu-id="28ab3-165">Trasformazione Ricerca</span><span class="sxs-lookup"><span data-stu-id="28ab3-165">Lookup Transformation</span></span>](data-flow/transformations/lookup-transformation.md)  
  
  
