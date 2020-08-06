---
title: Interfaccia IMDEmbedded | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
ms.assetid: 9dba8c68-4bef-4c2b-815c-c286f1a1939b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 331f8c33f7748e6591acd6d6ecda7a03ef7d8137
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626938"
---
# <a name="imdembedded-interface"></a><span data-ttu-id="3383b-102">Interfaccia IMDEmbedded</span><span class="sxs-lookup"><span data-stu-id="3383b-102">IMDEmbedded Interface</span></span>
  <span data-ttu-id="3383b-103">L'interfaccia IMDEmbedded è un'interfaccia pubblica utilizzata per gestire un database PowerPivot incorporato o un database modello tabulare.</span><span class="sxs-lookup"><span data-stu-id="3383b-103">The IMDEmbedded interface is a public interface used to manage an embedded PowerPivot database or a tabular model database.</span></span> <span data-ttu-id="3383b-104">L'interfaccia eredita dall'interfaccia `IPersistStream`</span><span class="sxs-lookup"><span data-stu-id="3383b-104">The interface inherits from the `IPersistStream` interface.</span></span> <span data-ttu-id="3383b-105">e consente di effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3383b-105">The interface allows for the following operations:</span></span>  
  
-   <span data-ttu-id="3383b-106">Ottenere un identificatore per il flusso incorporato nel documento contenitore.</span><span class="sxs-lookup"><span data-stu-id="3383b-106">Get an identifier to the embedded stream in the container document.</span></span>  
  
-   <span data-ttu-id="3383b-107">Impostare l'URL del documento contenitore.</span><span class="sxs-lookup"><span data-stu-id="3383b-107">Set the URL of the containing document.</span></span>  
  
-   <span data-ttu-id="3383b-108">Impostare un flag per specificare se l'applicazione in cui viene eseguito l'incorporamento è in ambiente host.</span><span class="sxs-lookup"><span data-stu-id="3383b-108">Set a flag to indicate if the embedding application is in a hosted environment.</span></span>  
  
-   <span data-ttu-id="3383b-109">Impostare il percorso dei file temporanei utilizzati dall'applicazione in cui viene eseguito l'incorporamento.</span><span class="sxs-lookup"><span data-stu-id="3383b-109">Set the path to temporary files used by the embedding application.</span></span>  
  
-   <span data-ttu-id="3383b-110">Annullare l'operazione incorporata corrente.</span><span class="sxs-lookup"><span data-stu-id="3383b-110">Cancel the current embedded operation.</span></span>  
  
-   <span data-ttu-id="3383b-111">Ottenere le dimensioni stimate (in byte) del flusso per il salvataggio dell'oggetto incorporato.</span><span class="sxs-lookup"><span data-stu-id="3383b-111">Get the estimated size (in bytes) of the stream to save the embedded object.</span></span> <span data-ttu-id="3383b-112">Ereditato da `IPersistStream`.</span><span class="sxs-lookup"><span data-stu-id="3383b-112">Inherited from `IPersistStream`.</span></span>  
  
-   <span data-ttu-id="3383b-113">Verificare se il database incorporato è stato modificato rispetto all'ultimo salvataggio.</span><span class="sxs-lookup"><span data-stu-id="3383b-113">Verify if the embedded database has changed since it was last saved.</span></span> <span data-ttu-id="3383b-114">Ereditato da `IPersistStream`.</span><span class="sxs-lookup"><span data-stu-id="3383b-114">Inherited from `IPersistStream`.</span></span>  
  
-   <span data-ttu-id="3383b-115">Caricare il database incorporato nel motore locale o in-process.</span><span class="sxs-lookup"><span data-stu-id="3383b-115">Load the embedded database to the local or in-process engine.</span></span> <span data-ttu-id="3383b-116">Ereditato da `IPersistStream`.</span><span class="sxs-lookup"><span data-stu-id="3383b-116">Inherited from `IPersistStream`.</span></span>  
  
-   <span data-ttu-id="3383b-117">Salvare il database locale o in-process nel flusso incorporato del documento contenitore.</span><span class="sxs-lookup"><span data-stu-id="3383b-117">Save the local or in-process database to the embedded stream in the container document.</span></span> <span data-ttu-id="3383b-118">Ereditato da `IPersistStream`.</span><span class="sxs-lookup"><span data-stu-id="3383b-118">Inherited from `IPersistStream`.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="3383b-119">Informazioni di riferimento</span><span class="sxs-lookup"><span data-stu-id="3383b-119">Reference</span></span>  
 <span data-ttu-id="3383b-120">Il riferimento seguente documenta l' `IMDEmbedded` interfaccia come presentata nel file di intestazione **Msmd. h** .</span><span class="sxs-lookup"><span data-stu-id="3383b-120">The following reference documents the `IMDEmbedded` interface as presented in **msmd.h** header file.</span></span>  
  
### <a name="source-file-pxoembeddeddataidl"></a><span data-ttu-id="3383b-121">File di origine: PXOEmbeddedData.idl</span><span class="sxs-lookup"><span data-stu-id="3383b-121">Source file: PXOEmbeddedData.idl</span></span>  
  
```  
[  
  local,                            
  object,                           
  uuid(6B6691CF-5453-41c2-ADD9-4F320B7FD421),                       
  pointer_default(unique)           
]  
interface IMDEmbeddedData : IPersistStream  
{  
 [id(1), helpstring("Set flag indicating if the application is in a hosted environment")]   
 HRESULT SetHosted(  
  [in] BOOL in_fIsHosted);  
  
 [id(2), helpstring("Set the URL for the document containing the embedded stream")]   
 HRESULT SetContainerURL(  
  [in] BSTR in_bstrURL);  
  
 [id(3), helpstring("Get identifier used to look up embedded stream in container document")]   
 HRESULT GetStreamIdentifier(  
  [out, retval] BSTR* out_pbstrStreamId);  
  
 [id(4), helpstring("Set the path used by the embedding application for temporary files")]   
 HRESULT SetTempDirPath(  
  [in]  BSTR in_bstrPath);  
  
 [id(5), helpstring("Cancel the current operation")]   
 HRESULT Cancel();  
};  
```  
  
### <a name="imdembeddeddatagetstreamidentifier"></a><span data-ttu-id="3383b-122">IMDEmbeddedData::GetStreamIdentifier</span><span class="sxs-lookup"><span data-stu-id="3383b-122">IMDEmbeddedData::GetStreamIdentifier</span></span>  
  
```  
HRESULT GetStreamIdentifier (  
    [out, retval] BSTR * out_pbstrStreamId  
    )  
```  
  
#### <a name="description"></a><span data-ttu-id="3383b-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3383b-123">Description</span></span>  
 <span data-ttu-id="3383b-124">Ottiene l'identificatore utilizzato dall'applicazione host per il flusso incorporato nel documento contenitore.</span><span class="sxs-lookup"><span data-stu-id="3383b-124">Gets the identifier used by the host application to the embedded stream in the container document.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="3383b-125">Parametri</span><span class="sxs-lookup"><span data-stu-id="3383b-125">Parameters</span></span>  
 <span data-ttu-id="3383b-126">*out_pbstrStreamId*</span><span class="sxs-lookup"><span data-stu-id="3383b-126">*out_pbstrStreamId*</span></span>  
 <span data-ttu-id="3383b-127">Specifica la posizione dell'identificatore di flusso.</span><span class="sxs-lookup"><span data-stu-id="3383b-127">Specifies the location of the stream identifier.</span></span>  
  
#### <a name="return-value"></a><span data-ttu-id="3383b-128">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="3383b-128">Return Value</span></span>  
 `S_OK`  
 <span data-ttu-id="3383b-129">L'identificatore di flusso è stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="3383b-129">The stream identifier was successfully returned.</span></span>  
  
 `S_FALSE`  
 <span data-ttu-id="3383b-130">Non esiste alcun identificatore di flusso.</span><span class="sxs-lookup"><span data-stu-id="3383b-130">There is no stream identifier.</span></span>  
  
 `E_FAIL`  
 <span data-ttu-id="3383b-131">Si è verificato un errore durante l'accesso all'identificatore di flusso.</span><span class="sxs-lookup"><span data-stu-id="3383b-131">An error occurred accessing the stream identifier.</span></span>  
  
#### <a name="remarks"></a><span data-ttu-id="3383b-132">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="3383b-132">Remarks</span></span>  
 <span data-ttu-id="3383b-133">Per verificare se la connessione corrente contiene un database incorporato, l'utente deve controllare il valore della proprietà DBPROP_MSMD_EMBEDDED_DATA dalle proprietà di connessione di OLE DB.</span><span class="sxs-lookup"><span data-stu-id="3383b-133">To verify if the current connection contains an embedded database, the user should check the value of the DBPROP_MSMD_EMBEDDED_DATA property from the OLE DB connection properties.</span></span>  
  
 <span data-ttu-id="3383b-134">I valori possibili per DBPROP_MSMD_EMBEDDED_DATA sono:</span><span class="sxs-lookup"><span data-stu-id="3383b-134">The possible values for DBPROP_MSMD_EMBEDDED_DATA are:</span></span>  
  
|<span data-ttu-id="3383b-135">Nome</span><span class="sxs-lookup"><span data-stu-id="3383b-135">Name</span></span>|<span data-ttu-id="3383b-136">valore</span><span class="sxs-lookup"><span data-stu-id="3383b-136">Value</span></span>|<span data-ttu-id="3383b-137">Definizione</span><span class="sxs-lookup"><span data-stu-id="3383b-137">Definition</span></span>|  
|----------|-----------|----------------|  
|<span data-ttu-id="3383b-138">DBPROPVAL_EMBED_NONE</span><span class="sxs-lookup"><span data-stu-id="3383b-138">DBPROPVAL_EMBED_NONE</span></span>|<span data-ttu-id="3383b-139">0x00</span><span class="sxs-lookup"><span data-stu-id="3383b-139">0x00</span></span>|<span data-ttu-id="3383b-140">Nessun database incorporato disponibile</span><span class="sxs-lookup"><span data-stu-id="3383b-140">No embedded database available</span></span>|  
|<span data-ttu-id="3383b-141">DBPROPVAL_EMBED_EMBEDDED</span><span class="sxs-lookup"><span data-stu-id="3383b-141">DBPROPVAL_EMBED_EMBEDDED</span></span>|<span data-ttu-id="3383b-142">0x01</span><span class="sxs-lookup"><span data-stu-id="3383b-142">0x01</span></span>|<span data-ttu-id="3383b-143">L'applicazione corrente contiene il database incorporato</span><span class="sxs-lookup"><span data-stu-id="3383b-143">The current application contains the embedded database</span></span>|  
|<span data-ttu-id="3383b-144">DBPROPVAL_EMBED_LINKED</span><span class="sxs-lookup"><span data-stu-id="3383b-144">DBPROPVAL_EMBED_LINKED</span></span>|<span data-ttu-id="3383b-145">0x02</span><span class="sxs-lookup"><span data-stu-id="3383b-145">0x02</span></span>|<span data-ttu-id="3383b-146">Il database incorporato è ospitato in un'applicazione remota, ad esempio SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="3383b-146">The embedded database is hosted in a remote application (i.e. SharePoint Server)</span></span>|  
  
#### <a name="source"></a><span data-ttu-id="3383b-147">Source (Sorgente)</span><span class="sxs-lookup"><span data-stu-id="3383b-147">Source</span></span>  
  
```  
[id(1), helpstring("Get identifier used to look up embedded stream in container document")]   
 HRESULT GetStreamIdentifier(  
  [out, retval] BSTR* out_pbstrStreamId);  
```  
  
### <a name="imdembeddeddatasetcontainerurl"></a><span data-ttu-id="3383b-148">IMDEmbeddedData::SetContainerURL</span><span class="sxs-lookup"><span data-stu-id="3383b-148">IMDEmbeddedData::SetContainerURL</span></span>  
  
```  
HRESULT SetContainerURL (  
    [in] BSTR in_bstrURL  
    )  
```  
  
#### <a name="description"></a><span data-ttu-id="3383b-149">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3383b-149">Description</span></span>  
 <span data-ttu-id="3383b-150">Viene impostato l'URL per il file in cui è contenuto il flusso incorporato.</span><span class="sxs-lookup"><span data-stu-id="3383b-150">Sets the URL for the file containing the embedded stream.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="3383b-151">Parametri</span><span class="sxs-lookup"><span data-stu-id="3383b-151">Parameters</span></span>  
 <span data-ttu-id="3383b-152">*in_bstrURL*</span><span class="sxs-lookup"><span data-stu-id="3383b-152">*in_bstrURL*</span></span>  
 <span data-ttu-id="3383b-153">Specifica l'URL per il documento contenitore.</span><span class="sxs-lookup"><span data-stu-id="3383b-153">Specifies the URL for the containing document.</span></span>  
  
#### <a name="return-value"></a><span data-ttu-id="3383b-154">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="3383b-154">Return Value</span></span>  
 `S_OK`  
 <span data-ttu-id="3383b-155">L'URL del contenitore è stato impostato correttamente.</span><span class="sxs-lookup"><span data-stu-id="3383b-155">The container URL was successfully set.</span></span>  
  
 `E_FAIL`  
 <span data-ttu-id="3383b-156">Si è verificato un errore durante l'impostazione dell'URL del contenitore.</span><span class="sxs-lookup"><span data-stu-id="3383b-156">An error occurred while setting the container URL.</span></span>  
  
#### <a name="source"></a><span data-ttu-id="3383b-157">Source (Sorgente)</span><span class="sxs-lookup"><span data-stu-id="3383b-157">Source</span></span>  
  
```  
[id(2), helpstring("Set the URL for the document containing the embedded stream")]   
 HRESULT SetContainerURL(  
  [in] BSTR in_bstrURL);  
```  
  
### <a name="imdembeddeddatasethosted"></a><span data-ttu-id="3383b-158">IMDEmbeddedData::SetHosted</span><span class="sxs-lookup"><span data-stu-id="3383b-158">IMDEmbeddedData::SetHosted</span></span>  
  
```  
HRESULT SetHosted (  
    [in] BOOL in_fIsHosted  
    )  
```  
  
#### <a name="description"></a><span data-ttu-id="3383b-159">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3383b-159">Description</span></span>  
 <span data-ttu-id="3383b-160">Impostare un flag per specificare se l'applicazione in cui viene eseguito l'incorporamento è in ambiente host.</span><span class="sxs-lookup"><span data-stu-id="3383b-160">Set a flag to indicate if the embedding application is in a hosted environment.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="3383b-161">Parametri</span><span class="sxs-lookup"><span data-stu-id="3383b-161">Parameters</span></span>  
 <span data-ttu-id="3383b-162">*in_ftHosted*</span><span class="sxs-lookup"><span data-stu-id="3383b-162">*in_ftHosted*</span></span>  
 <span data-ttu-id="3383b-163">TRUE se il chiamante è in un ambiente host in un'applicazione di servizio (come IIS).</span><span class="sxs-lookup"><span data-stu-id="3383b-163">TRUE if caller is in a hosted in a service application (like IIS).</span></span>  
  
#### <a name="return-value"></a><span data-ttu-id="3383b-164">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="3383b-164">Return Value</span></span>  
 `S_OK`  
 <span data-ttu-id="3383b-165">Il flag è stato impostato correttamente.</span><span class="sxs-lookup"><span data-stu-id="3383b-165">The flag was successfully set.</span></span>  
  
 `E_FAIL`  
 <span data-ttu-id="3383b-166">Si è verificato un errore durante l'impostazione del flag.</span><span class="sxs-lookup"><span data-stu-id="3383b-166">An error occurred while setting the flag.</span></span>  
  
#### <a name="source"></a><span data-ttu-id="3383b-167">Source (Sorgente)</span><span class="sxs-lookup"><span data-stu-id="3383b-167">Source</span></span>  
  
```  
[id(5), helpstring("Set flag indicating if the application is in a hosted environment")]   
 HRESULT SetHosted(  
  [in]  BOOL in_fIsHosted);  
```  
  
### <a name="imdembeddeddatasettempdirpath"></a><span data-ttu-id="3383b-168">IMDEmbeddedData::SetTempDirPath</span><span class="sxs-lookup"><span data-stu-id="3383b-168">IMDEmbeddedData::SetTempDirPath</span></span>  
  
```  
HRESULT SetTempDirPath (  
    [in] BSTR in_bstrPath  
    )  
```  
  
#### <a name="description"></a><span data-ttu-id="3383b-169">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3383b-169">Description</span></span>  
 <span data-ttu-id="3383b-170">Impostare il percorso dei file temporanei utilizzati dall'applicazione in cui viene eseguito l'incorporamento.</span><span class="sxs-lookup"><span data-stu-id="3383b-170">Set the path to temporary files used by the embedding application.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="3383b-171">Parametri</span><span class="sxs-lookup"><span data-stu-id="3383b-171">Parameters</span></span>  
 <span data-ttu-id="3383b-172">*in_bstrPath*</span><span class="sxs-lookup"><span data-stu-id="3383b-172">*in_bstrPath*</span></span>  
 <span data-ttu-id="3383b-173">Il percorso dei file temporanei utilizzato dall'applicazione host.</span><span class="sxs-lookup"><span data-stu-id="3383b-173">The path used by the host application for temporary files.</span></span>  
  
#### <a name="return-value"></a><span data-ttu-id="3383b-174">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="3383b-174">Return Value</span></span>  
 `S_OK`  
 <span data-ttu-id="3383b-175">La directory dei file temporanei è stata impostata correttamente.</span><span class="sxs-lookup"><span data-stu-id="3383b-175">The temporary file directory was successfully set.</span></span>  
  
 `E_FAIL`  
 <span data-ttu-id="3383b-176">Si è verificato un errore durante l'impostazione del percorso.</span><span class="sxs-lookup"><span data-stu-id="3383b-176">An error occurred while setting the path.</span></span>  
  
#### <a name="source"></a><span data-ttu-id="3383b-177">Source (Sorgente)</span><span class="sxs-lookup"><span data-stu-id="3383b-177">Source</span></span>  
  
```  
[id(4), helpstring("Set the path used by the host application for temporary files")]   
 HRESULT SetTempDirPath(  
  [in]  BSTR in_bstrPath);  
```  
  
### <a name="imdembeddeddatacancel"></a><span data-ttu-id="3383b-178">IMDEmbeddedData::Cancel</span><span class="sxs-lookup"><span data-stu-id="3383b-178">IMDEmbeddedData::Cancel</span></span>  
  
```  
HRESULT Cancel ( void )  
```  
  
#### <a name="description"></a><span data-ttu-id="3383b-179">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3383b-179">Description</span></span>  
 <span data-ttu-id="3383b-180">Annulla l'operazione del database incorporato corrente.</span><span class="sxs-lookup"><span data-stu-id="3383b-180">Cancels the current embedded database operation</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="3383b-181">Parametri</span><span class="sxs-lookup"><span data-stu-id="3383b-181">Parameters</span></span>  
 <span data-ttu-id="3383b-182">No.</span><span class="sxs-lookup"><span data-stu-id="3383b-182">None.</span></span>  
  
#### <a name="return-value"></a><span data-ttu-id="3383b-183">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="3383b-183">Return Value</span></span>  
 `S_OK`  
 <span data-ttu-id="3383b-184">L'operazione è stata annullata correttamente.</span><span class="sxs-lookup"><span data-stu-id="3383b-184">The operation was successfully cancelled.</span></span>  
  
 `DB_E_CANTCANCEL`  
 <span data-ttu-id="3383b-185">Non è in corso alcuna operazione annullabile.</span><span class="sxs-lookup"><span data-stu-id="3383b-185">No cancellable operation is currently in progress.</span></span>  
  
 `E_FAIL`  
 <span data-ttu-id="3383b-186">Si verificato un errore durante l'annullamento dell'operazione incorporata.</span><span class="sxs-lookup"><span data-stu-id="3383b-186">An error occurred while cancelling the embedded operation.</span></span>  
  
#### <a name="source"></a><span data-ttu-id="3383b-187">Source (Sorgente)</span><span class="sxs-lookup"><span data-stu-id="3383b-187">Source</span></span>  
  
```  
[id(5), helpstring("Cancel the current operation")]   
 HRESULT Cancel();  
```  
  
### <a name="imdembeddeddatagetsizemax-ipersiststreamgetsizemax"></a><span data-ttu-id="3383b-188">IMDEmbeddedData::GetSizeMax (IPersistStream::GetSizeMax)</span><span class="sxs-lookup"><span data-stu-id="3383b-188">IMDEmbeddedData::GetSizeMax (IPersistStream::GetSizeMax)</span></span>  
  
```  
HRESULT GetSizeMax (  
    [out] ULARGE_INTEGER * out_pcbSize  
    )  
```  
  
#### <a name="description"></a><span data-ttu-id="3383b-189">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3383b-189">Description</span></span>  
 <span data-ttu-id="3383b-190">Ottiene la dimensione stimata (in byte) del flusso per il salvataggio dell'oggetto incorporato.</span><span class="sxs-lookup"><span data-stu-id="3383b-190">Gets the estimated size (in bytes) of the stream to save the embedded object.</span></span> <span data-ttu-id="3383b-191">Ereditato da `IPersistStream`.</span><span class="sxs-lookup"><span data-stu-id="3383b-191">Inherited from `IPersistStream`.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="3383b-192">Parametri</span><span class="sxs-lookup"><span data-stu-id="3383b-192">Parameters</span></span>  
 <span data-ttu-id="3383b-193">*in_bstrPath*</span><span class="sxs-lookup"><span data-stu-id="3383b-193">*in_bstrPath*</span></span>  
 <span data-ttu-id="3383b-194">La dimensione stimata (in byte) dell'immagine del database incorporato.</span><span class="sxs-lookup"><span data-stu-id="3383b-194">The estimated size (in bytes) of the embedded database image.</span></span>  
  
#### <a name="return-value"></a><span data-ttu-id="3383b-195">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="3383b-195">Return Value</span></span>  
 `S_OK`  
 <span data-ttu-id="3383b-196">La dimensione è stata ottenuta correttamente.</span><span class="sxs-lookup"><span data-stu-id="3383b-196">The size was successfully obtained.</span></span>  
  
 `E_FAIL`  
 <span data-ttu-id="3383b-197">Errore durante il calcolo della dimensione.</span><span class="sxs-lookup"><span data-stu-id="3383b-197">An error occurred while obtaining the size.</span></span>  
  
### <a name="imdembeddeddataisdirty-ipersiststreamisdirty"></a><span data-ttu-id="3383b-198">IMDEmbeddedData::IsDirty (IPersistStream::IsDirty)</span><span class="sxs-lookup"><span data-stu-id="3383b-198">IMDEmbeddedData::IsDirty (IPersistStream::IsDirty)</span></span>  
  
```  
HRESULT IsDirty ( void )  
```  
  
#### <a name="description"></a><span data-ttu-id="3383b-199">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3383b-199">Description</span></span>  
 <span data-ttu-id="3383b-200">Verifica se il database incorporato è stato modificato rispetto all'ultimo salvataggio.</span><span class="sxs-lookup"><span data-stu-id="3383b-200">Verifies if the embedded database has changed since it was last saved.</span></span> <span data-ttu-id="3383b-201">Ereditato da `IPersistStream`.</span><span class="sxs-lookup"><span data-stu-id="3383b-201">Inherited from `IPersistStream`.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="3383b-202">Parametri</span><span class="sxs-lookup"><span data-stu-id="3383b-202">Parameters</span></span>  
 <span data-ttu-id="3383b-203">none</span><span class="sxs-lookup"><span data-stu-id="3383b-203">none</span></span>  
  
#### <a name="return-values"></a><span data-ttu-id="3383b-204">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="3383b-204">Return Value(s)</span></span>  
 `S_OK`  
 <span data-ttu-id="3383b-205">Il database è stato modificato rispetto all'ultimo salvataggio.</span><span class="sxs-lookup"><span data-stu-id="3383b-205">The database has changed since it was last saved.</span></span>  
  
 `S_FALSE`  
 <span data-ttu-id="3383b-206">Il database non è stato modificato rispetto all'ultimo salvataggio.</span><span class="sxs-lookup"><span data-stu-id="3383b-206">The database has not changed since it was last saved.</span></span>  
  
 `E_FAIL`  
 <span data-ttu-id="3383b-207">Si è verificato un errore durante il recupero dello stato del database.</span><span class="sxs-lookup"><span data-stu-id="3383b-207">An error occurred while obtaining the database state.</span></span>  
  
### <a name="imdembeddeddataload-ipersiststreamload"></a><span data-ttu-id="3383b-208">IMDEmbeddedData::Load (IPersistStream::Load)</span><span class="sxs-lookup"><span data-stu-id="3383b-208">IMDEmbeddedData::Load (IPersistStream::Load)</span></span>  
  
```  
HRESULT Load (   
    [in] IStream * in_pStm   
    )  
```  
  
#### <a name="description"></a><span data-ttu-id="3383b-209">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3383b-209">Description</span></span>  
 <span data-ttu-id="3383b-210">Carica il database incorporato sul motore locale o in-process.</span><span class="sxs-lookup"><span data-stu-id="3383b-210">Loads the embedded database to the local or in-process engine.</span></span> <span data-ttu-id="3383b-211">Ereditato da `IPersistStream`.</span><span class="sxs-lookup"><span data-stu-id="3383b-211">Inherited from `IPersistStream`.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="3383b-212">Parametri</span><span class="sxs-lookup"><span data-stu-id="3383b-212">Parameters</span></span>  
 <span data-ttu-id="3383b-213">*in_pStm*</span><span class="sxs-lookup"><span data-stu-id="3383b-213">*in_pStm*</span></span>  
 <span data-ttu-id="3383b-214">Un puntatore a un'interfaccia del flusso da cui caricare il database incorporato.</span><span class="sxs-lookup"><span data-stu-id="3383b-214">A pointer to a stream interface from where to load the embedded database.</span></span>  
  
#### <a name="return-values"></a><span data-ttu-id="3383b-215">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="3383b-215">Return Value(s)</span></span>  
 `S_OK`  
 <span data-ttu-id="3383b-216">Il database è stato caricato correttamente.</span><span class="sxs-lookup"><span data-stu-id="3383b-216">The database was successfully loaded.</span></span>  
  
 `E_OUTOFMEMORY`  
 <span data-ttu-id="3383b-217">Memoria insufficiente per il caricamento del database.</span><span class="sxs-lookup"><span data-stu-id="3383b-217">Not enough memory to load the database.</span></span>  
  
 `E_FAIL`  
 <span data-ttu-id="3383b-218">Si verificato un errore durante il caricamento del database, diverso da `E_OUTOFMEMORY`.</span><span class="sxs-lookup"><span data-stu-id="3383b-218">An error occurred while loading the database, different than `E_OUTOFMEMORY`.</span></span>  
  
### <a name="imdembeddeddatasave-ipersiststreamsave"></a><span data-ttu-id="3383b-219">IMDEmbeddedData::Save (IPersistStream::Save)</span><span class="sxs-lookup"><span data-stu-id="3383b-219">IMDEmbeddedData::Save (IPersistStream::Save)</span></span>  
  
```  
HRESULT Save (   
    [in] IStream * in_pStm,  
    [in] BOOL in_fClearDirty  
    )  
```  
  
#### <a name="description"></a><span data-ttu-id="3383b-220">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3383b-220">Description</span></span>  
 <span data-ttu-id="3383b-221">Salva il database locale o in-process nel flusso incorporato del documento contenitore.</span><span class="sxs-lookup"><span data-stu-id="3383b-221">Saves the local or in-process database to the embedded stream in the container document.</span></span> <span data-ttu-id="3383b-222">Ereditato da `IPersistStream`.</span><span class="sxs-lookup"><span data-stu-id="3383b-222">Inherited from `IPersistStream`.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="3383b-223">Parametri</span><span class="sxs-lookup"><span data-stu-id="3383b-223">Parameters</span></span>  
 <span data-ttu-id="3383b-224">*in_pStm*</span><span class="sxs-lookup"><span data-stu-id="3383b-224">*in_pStm*</span></span>  
 <span data-ttu-id="3383b-225">Un puntatore a un'interfaccia del flusso in cui salvare il database incorporato.</span><span class="sxs-lookup"><span data-stu-id="3383b-225">A pointer to a stream interface to where to save the embedded database.</span></span>  
  
 <span data-ttu-id="3383b-226">*in_fClearDirty*</span><span class="sxs-lookup"><span data-stu-id="3383b-226">*in_fClearDirty*</span></span>  
 <span data-ttu-id="3383b-227">Un flag che indica se il flag modificato deve essere eliminato dopo questa operazione.</span><span class="sxs-lookup"><span data-stu-id="3383b-227">A flag that indicates whether the dirty flag should be cleared after this operation.</span></span>  
  
#### <a name="return-values"></a><span data-ttu-id="3383b-228">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="3383b-228">Return Value(s)</span></span>  
 `S_OK`  
 <span data-ttu-id="3383b-229">Il database è stato salvato correttamente.</span><span class="sxs-lookup"><span data-stu-id="3383b-229">The database was successfully saved.</span></span>  
  
 `STG_E_CANTSAVE`  
 <span data-ttu-id="3383b-230">Si verificato un errore durante il salvataggio del database, diverso da `STG_E_MEDIUMFULL`.</span><span class="sxs-lookup"><span data-stu-id="3383b-230">An error occurred while saving the database, different than `STG_E_MEDIUMFULL`.</span></span>  
  
 `STG_E_MEDIUMFULL`  
 <span data-ttu-id="3383b-231">Non è possibile salvare il database perché lo spazio sul dispositivo di memorizzazione è esaurito.</span><span class="sxs-lookup"><span data-stu-id="3383b-231">The database could not be saved because there is no space left on the storage device.</span></span>  
  
  
