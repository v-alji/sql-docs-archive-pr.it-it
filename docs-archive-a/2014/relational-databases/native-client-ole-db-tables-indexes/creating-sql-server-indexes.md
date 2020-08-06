---
title: Creazione di indici di SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- CreateIndex function
- constraints [OLE DB]
- SQL Server Native Client OLE DB provider, indexes
- indexes [OLE DB]
- adding indexes
ms.assetid: 6239d440-2818-4b98-bb79-732dced41952
author: rothja
ms.author: jroth
ms.openlocfilehash: 3693355eec7a290c03658c10db500161aa52062d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723752"
---
# <a name="creating-sql-server-indexes"></a><span data-ttu-id="9e306-102">Creazione di indici SQL Server</span><span class="sxs-lookup"><span data-stu-id="9e306-102">Creating SQL Server Indexes</span></span>
  <span data-ttu-id="9e306-103">Il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native Client espone la funzione **IIndexDefinition:: CreateIndex** , consentendo ai consumer di definire nuovi indici nelle [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tabelle.</span><span class="sxs-lookup"><span data-stu-id="9e306-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider exposes the **IIndexDefinition::CreateIndex** function, allowing consumers to define new indexes on [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tables.</span></span>  
  
 <span data-ttu-id="9e306-104">Il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native client crea indici di tabella come indici o vincoli.</span><span class="sxs-lookup"><span data-stu-id="9e306-104">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider creates table indexes as either indexes or constraints.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="9e306-105">fornisce privilegio di creazione del vincolo al proprietario della tabella, del database e ai membri di determinati ruoli amministrativi.</span><span class="sxs-lookup"><span data-stu-id="9e306-105">gives constraint-creation privilege to the table owner, database owner, and members of certain administrative roles.</span></span> <span data-ttu-id="9e306-106">Per impostazione predefinita, solo il proprietario di tabella può creare un indice in una tabella.</span><span class="sxs-lookup"><span data-stu-id="9e306-106">By default, only the table owner can create an index on a table.</span></span> <span data-ttu-id="9e306-107">L'esito positivo o negativo di **CreateIndex** dipende quindi non solo dai diritti di accesso dell'utente dell'applicazione ma anche dal tipo di indice creato.</span><span class="sxs-lookup"><span data-stu-id="9e306-107">Therefore, the success or failure of **CreateIndex** depends not only on the application user's access rights but also on the type of index created.</span></span>  
  
 <span data-ttu-id="9e306-108">I consumer specificano il nome della tabella come stringa di caratteri Unicode nel membro *pwszName* dell'unione *uName* nel parametro *pTableID*.</span><span class="sxs-lookup"><span data-stu-id="9e306-108">Consumers specify the table name as a Unicode character string in the *pwszName* member of the *uName* union in the *pTableID* parameter.</span></span> <span data-ttu-id="9e306-109">Il membro *eKind* di*pTableID* deve essere DBKIND_NAME.</span><span class="sxs-lookup"><span data-stu-id="9e306-109">The *eKind* member of *pTableID* must be DBKIND_NAME.</span></span>  
  
 <span data-ttu-id="9e306-110">Il parametro *pIndexID* può essere null e, in caso contrario, il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native client crea un nome univoco per l'indice.</span><span class="sxs-lookup"><span data-stu-id="9e306-110">The *pIndexID* parameter can be NULL, and if it is, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider creates a unique name for the index.</span></span> <span data-ttu-id="9e306-111">Il consumer può acquisire il nome dell'indice specificando un puntatore valido a un DBID nel parametro *ppIndexID*.</span><span class="sxs-lookup"><span data-stu-id="9e306-111">The consumer can capture the name of the index by specifying a valid pointer to a DBID in the *ppIndexID* parameter.</span></span>  
  
 <span data-ttu-id="9e306-112">Il consumer può specificare il nome dell'indice come stringa di caratteri Unicode nel membro *pwszName* dell'unione *uName* del parametro *pTableID*.</span><span class="sxs-lookup"><span data-stu-id="9e306-112">The consumer can specify the index name as a Unicode character string in the *pwszName* member of the *uName* union of the *pIndexID* parameter.</span></span> <span data-ttu-id="9e306-113">Il membro *eKind* di *pIndexID* deve essere DBKIND_NAME.</span><span class="sxs-lookup"><span data-stu-id="9e306-113">The *eKind* member of *pIndexID* must be DBKIND_NAME.</span></span>  
  
 <span data-ttu-id="9e306-114">Il consumer specifica la colonna o le colonne utilizzate nell'indice in base al nome.</span><span class="sxs-lookup"><span data-stu-id="9e306-114">The consumer specifies the column or columns participating in the index by name.</span></span> <span data-ttu-id="9e306-115">Per ogni struttura DBINDEXCOLUMNDESC usata in **CreateIndex**, il membro *eKind* di *pColumnID* deve essere DBKIND_NAME.</span><span class="sxs-lookup"><span data-stu-id="9e306-115">For each DBINDEXCOLUMNDESC structure used in **CreateIndex**, the *eKind* member of the *pColumnID* must be DBKIND_NAME.</span></span> <span data-ttu-id="9e306-116">Il nome della colonna viene specificato come stringa di caratteri Unicode nel membro *pwszName* dell'unione *uName* in *pColumnID*.</span><span class="sxs-lookup"><span data-stu-id="9e306-116">The name of the column is specified as a Unicode character string in the *pwszName* member of the *uName* union in the *pColumnID*.</span></span>  
  
 <span data-ttu-id="9e306-117">Il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native client e [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] supporta l'ordinamento crescente in base ai valori dell'indice.</span><span class="sxs-lookup"><span data-stu-id="9e306-117">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] support ascending order on values in the index.</span></span> <span data-ttu-id="9e306-118">Il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native Client restituisce E_INVALIDARG se il consumer specifica DBINDEX_COL_ORDER_DESC in qualsiasi struttura DBINDEXCOLUMNDESC.</span><span class="sxs-lookup"><span data-stu-id="9e306-118">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider returns E_INVALIDARG if the consumer specifies DBINDEX_COL_ORDER_DESC in any DBINDEXCOLUMNDESC structure.</span></span>  
  
 <span data-ttu-id="9e306-119">**CreateIndex** interpreta le proprietà di indice come segue.</span><span class="sxs-lookup"><span data-stu-id="9e306-119">**CreateIndex** interprets index properties as follows.</span></span>  
  
|<span data-ttu-id="9e306-120">ID proprietà</span><span class="sxs-lookup"><span data-stu-id="9e306-120">Property ID</span></span>|<span data-ttu-id="9e306-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9e306-121">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="9e306-122">DBPROP_INDEX_AUTOUPDATE</span><span class="sxs-lookup"><span data-stu-id="9e306-122">DBPROP_INDEX_AUTOUPDATE</span></span>|<span data-ttu-id="9e306-123">R/W (L/S): Lettura/Scrittura</span><span class="sxs-lookup"><span data-stu-id="9e306-123">R/W: Read/write</span></span><br /><br /> <span data-ttu-id="9e306-124">Impostazione predefinita: nessuna</span><span class="sxs-lookup"><span data-stu-id="9e306-124">Default: None</span></span><br /><br /> <span data-ttu-id="9e306-125">Descrizione: il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native client non supporta questa proprietà.</span><span class="sxs-lookup"><span data-stu-id="9e306-125">Description: The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider does not support this property.</span></span> <span data-ttu-id="9e306-126">I tentativi di impostare la proprietà in **CreateIndex** determinano un valore restituito DB_S_ERRORSOCCURRED.</span><span class="sxs-lookup"><span data-stu-id="9e306-126">Attempts to set the property in **CreateIndex** cause a DB_S_ERRORSOCCURRED return value.</span></span> <span data-ttu-id="9e306-127">Il membro *dwStatus* della struttura di proprietà indica DBPROPSTATUS_BADVALUE.</span><span class="sxs-lookup"><span data-stu-id="9e306-127">The *dwStatus* member of the property structure indicates DBPROPSTATUS_BADVALUE.</span></span>|  
|<span data-ttu-id="9e306-128">DBPROP_INDEX_CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="9e306-128">DBPROP_INDEX_CLUSTERED</span></span>|<span data-ttu-id="9e306-129">R/W (L/S): Lettura/Scrittura</span><span class="sxs-lookup"><span data-stu-id="9e306-129">R/W: Read/write</span></span><br /><br /> <span data-ttu-id="9e306-130">Predefinito: VARIANT_FALSE</span><span class="sxs-lookup"><span data-stu-id="9e306-130">Default: VARIANT_FALSE</span></span><br /><br /> <span data-ttu-id="9e306-131">Descrizione: controlla il clustering dell'indice.</span><span class="sxs-lookup"><span data-stu-id="9e306-131">Description: Controls index clustering.</span></span><br /><br /> <span data-ttu-id="9e306-132">VARIANT_TRUE: il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native client tenta di creare un indice cluster nella [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tabella.</span><span class="sxs-lookup"><span data-stu-id="9e306-132">VARIANT_TRUE: The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider attempts to create a clustered index on the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="9e306-133">supporta al massimo un indice con cluster su una tabella.</span><span class="sxs-lookup"><span data-stu-id="9e306-133">supports at most one clustered index on any table.</span></span><br /><br /> <span data-ttu-id="9e306-134">VARIANT_FALSE: il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native client tenta di creare un indice non cluster nella [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tabella.</span><span class="sxs-lookup"><span data-stu-id="9e306-134">VARIANT_FALSE: The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider attempts to create a nonclustered index on the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span>|  
|<span data-ttu-id="9e306-135">DBPROP_INDEX_FILLFACTOR</span><span class="sxs-lookup"><span data-stu-id="9e306-135">DBPROP_INDEX_FILLFACTOR</span></span>|<span data-ttu-id="9e306-136">R/W (L/S): Lettura/Scrittura</span><span class="sxs-lookup"><span data-stu-id="9e306-136">R/W: Read/write</span></span><br /><br /> <span data-ttu-id="9e306-137">Impostazione predefinita: 0</span><span class="sxs-lookup"><span data-stu-id="9e306-137">Default: 0</span></span><br /><br /> <span data-ttu-id="9e306-138">Descrizione: specifica la percentuale di una pagina di indice utilizzata per l'archiviazione.</span><span class="sxs-lookup"><span data-stu-id="9e306-138">Description: Specifies the percentage of an index page used for storage.</span></span> <span data-ttu-id="9e306-139">Per altre informazioni, vedere [CREATE INDEX](/sql/t-sql/statements/create-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="9e306-139">For more information, see [CREATE INDEX](/sql/t-sql/statements/create-index-transact-sql).</span></span><br /><br /> <span data-ttu-id="9e306-140">Il tipo della variante è VT_I4.</span><span class="sxs-lookup"><span data-stu-id="9e306-140">The type of the variant is VT_I4.</span></span> <span data-ttu-id="9e306-141">Deve essere maggiore o uguale a 1 e minore o uguale a 100.</span><span class="sxs-lookup"><span data-stu-id="9e306-141">The value must be greater than or equal to 1 and less than or equal to 100.</span></span>|  
|<span data-ttu-id="9e306-142">DBPROP_INDEX_INITIALIZE</span><span class="sxs-lookup"><span data-stu-id="9e306-142">DBPROP_INDEX_INITIALIZE</span></span>|<span data-ttu-id="9e306-143">R/W (L/S): Lettura/Scrittura</span><span class="sxs-lookup"><span data-stu-id="9e306-143">R/W: Read/write</span></span><br /><br /> <span data-ttu-id="9e306-144">Impostazione predefinita: nessuna</span><span class="sxs-lookup"><span data-stu-id="9e306-144">Default: None</span></span><br /><br /> <span data-ttu-id="9e306-145">Descrizione: il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native client non supporta questa proprietà.</span><span class="sxs-lookup"><span data-stu-id="9e306-145">Description: The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider does not support this property.</span></span> <span data-ttu-id="9e306-146">I tentativi di impostare la proprietà in **CreateIndex** determinano un valore restituito DB_S_ERRORSOCCURRED.</span><span class="sxs-lookup"><span data-stu-id="9e306-146">Attempts to set the property in **CreateIndex** cause a DB_S_ERRORSOCCURRED return value.</span></span> <span data-ttu-id="9e306-147">Il membro *dwStatus* della struttura di proprietà indica DBPROPSTATUS_BADVALUE.</span><span class="sxs-lookup"><span data-stu-id="9e306-147">The *dwStatus* member of the property structure indicates DBPROPSTATUS_BADVALUE.</span></span>|  
|<span data-ttu-id="9e306-148">DBPROP_INDEX_NULLCOLLATION</span><span class="sxs-lookup"><span data-stu-id="9e306-148">DBPROP_INDEX_NULLCOLLATION</span></span>|<span data-ttu-id="9e306-149">R/W (L/S): Lettura/Scrittura</span><span class="sxs-lookup"><span data-stu-id="9e306-149">R/W: Read/write</span></span><br /><br /> <span data-ttu-id="9e306-150">Impostazione predefinita: nessuna</span><span class="sxs-lookup"><span data-stu-id="9e306-150">Default: None</span></span><br /><br /> <span data-ttu-id="9e306-151">Descrizione: il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native client non supporta questa proprietà.</span><span class="sxs-lookup"><span data-stu-id="9e306-151">Description: The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider does not support this property.</span></span> <span data-ttu-id="9e306-152">I tentativi di impostare la proprietà in **CreateIndex** determinano un valore restituito DB_S_ERRORSOCCURRED.</span><span class="sxs-lookup"><span data-stu-id="9e306-152">Attempts to set the property in **CreateIndex** cause a DB_S_ERRORSOCCURRED return value.</span></span> <span data-ttu-id="9e306-153">Il membro *dwStatus* della struttura di proprietà indica DBPROPSTATUS_BADVALUE.</span><span class="sxs-lookup"><span data-stu-id="9e306-153">The *dwStatus* member of the property structure indicates DBPROPSTATUS_BADVALUE.</span></span>|  
|<span data-ttu-id="9e306-154">DBPROP_INDEX_NULLS</span><span class="sxs-lookup"><span data-stu-id="9e306-154">DBPROP_INDEX_NULLS</span></span>|<span data-ttu-id="9e306-155">R/W (L/S): Lettura/Scrittura</span><span class="sxs-lookup"><span data-stu-id="9e306-155">R/W: Read/write</span></span><br /><br /> <span data-ttu-id="9e306-156">Impostazione predefinita: nessuna</span><span class="sxs-lookup"><span data-stu-id="9e306-156">Default: None</span></span><br /><br /> <span data-ttu-id="9e306-157">Descrizione: il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native client non supporta questa proprietà.</span><span class="sxs-lookup"><span data-stu-id="9e306-157">Description: The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider does not support this property.</span></span> <span data-ttu-id="9e306-158">I tentativi di impostare la proprietà in **CreateIndex** determinano un valore restituito DB_S_ERRORSOCCURRED.</span><span class="sxs-lookup"><span data-stu-id="9e306-158">Attempts to set the property in **CreateIndex** cause a DB_S_ERRORSOCCURRED return value.</span></span> <span data-ttu-id="9e306-159">Il membro *dwStatus* della struttura di proprietà indica DBPROPSTATUS_BADVALUE.</span><span class="sxs-lookup"><span data-stu-id="9e306-159">The *dwStatus* member of the property structure indicates DBPROPSTATUS_BADVALUE.</span></span>|  
|<span data-ttu-id="9e306-160">DBPROP_INDEX_PRIMARYKEY</span><span class="sxs-lookup"><span data-stu-id="9e306-160">DBPROP_INDEX_PRIMARYKEY</span></span>|<span data-ttu-id="9e306-161">R/W (L/S): Lettura/Scrittura</span><span class="sxs-lookup"><span data-stu-id="9e306-161">R/W: Read/write</span></span><br /><br /> <span data-ttu-id="9e306-162">Impostazione predefinita: descrizione VARIANT_FALSE: crea l'indice come integrità referenziale, vincolo PRIMARY KEY.</span><span class="sxs-lookup"><span data-stu-id="9e306-162">Default: VARIANT_FALSE Description: Creates the index as a referential integrity, PRIMARY KEY constraint.</span></span><br /><br /> <span data-ttu-id="9e306-163">VARIANT_TRUE: l'indice viene creato per supportare il vincolo PRIMARY KEY della tabella.</span><span class="sxs-lookup"><span data-stu-id="9e306-163">VARIANT_TRUE: The index is created to support the PRIMARY KEY constraint of the table.</span></span> <span data-ttu-id="9e306-164">È necessario che le colonne non ammettano valori Null.</span><span class="sxs-lookup"><span data-stu-id="9e306-164">The columns must be nonnullable.</span></span><br /><br /> <span data-ttu-id="9e306-165">VARIANT_FALSE: l'indice non viene utilizzato come vincolo PRIMARY KEY per i valori di riga nella tabella.</span><span class="sxs-lookup"><span data-stu-id="9e306-165">VARIANT_FALSE: The index is not used as a PRIMARY KEY constraint for row values in the table.</span></span>|  
|<span data-ttu-id="9e306-166">DBPROP_INDEX_SORTBOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="9e306-166">DBPROP_INDEX_SORTBOOKMARKS</span></span>|<span data-ttu-id="9e306-167">R/W (L/S): Lettura/Scrittura</span><span class="sxs-lookup"><span data-stu-id="9e306-167">R/W: Read/write</span></span><br /><br /> <span data-ttu-id="9e306-168">Impostazione predefinita: nessuna</span><span class="sxs-lookup"><span data-stu-id="9e306-168">Default: None</span></span><br /><br /> <span data-ttu-id="9e306-169">Descrizione: il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native client non supporta questa proprietà.</span><span class="sxs-lookup"><span data-stu-id="9e306-169">Description: The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider does not support this property.</span></span> <span data-ttu-id="9e306-170">I tentativi di impostare la proprietà in **CreateIndex** determinano un valore restituito DB_S_ERRORSOCCURRED.</span><span class="sxs-lookup"><span data-stu-id="9e306-170">Attempts to set the property in **CreateIndex** cause a DB_S_ERRORSOCCURRED return value.</span></span> <span data-ttu-id="9e306-171">Il membro *dwStatus* della struttura di proprietà indica DBPROPSTATUS_BADVALUE.</span><span class="sxs-lookup"><span data-stu-id="9e306-171">The *dwStatus* member of the property structure indicates DBPROPSTATUS_BADVALUE.</span></span>|  
|<span data-ttu-id="9e306-172">DBPROP_INDEX_TEMPINDEX</span><span class="sxs-lookup"><span data-stu-id="9e306-172">DBPROP_INDEX_TEMPINDEX</span></span>|<span data-ttu-id="9e306-173">R/W (L/S): Lettura/Scrittura</span><span class="sxs-lookup"><span data-stu-id="9e306-173">R/W: Read/write</span></span><br /><br /> <span data-ttu-id="9e306-174">Impostazione predefinita: nessuna</span><span class="sxs-lookup"><span data-stu-id="9e306-174">Default: None</span></span><br /><br /> <span data-ttu-id="9e306-175">Descrizione: il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native client non supporta questa proprietà.</span><span class="sxs-lookup"><span data-stu-id="9e306-175">Description: The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider does not support this property.</span></span> <span data-ttu-id="9e306-176">I tentativi di impostare la proprietà in **CreateIndex** determinano un valore restituito DB_S_ERRORSOCCURRED.</span><span class="sxs-lookup"><span data-stu-id="9e306-176">Attempts to set the property in **CreateIndex** cause a DB_S_ERRORSOCCURRED return value.</span></span> <span data-ttu-id="9e306-177">Il membro *dwStatus* della struttura di proprietà indica DBPROPSTATUS_BADVALUE.</span><span class="sxs-lookup"><span data-stu-id="9e306-177">The *dwStatus* member of the property structure indicates DBPROPSTATUS_BADVALUE.</span></span>|  
|<span data-ttu-id="9e306-178">DBPROP_INDEX_TYPE</span><span class="sxs-lookup"><span data-stu-id="9e306-178">DBPROP_INDEX_TYPE</span></span>|<span data-ttu-id="9e306-179">R/W (L/S): Lettura/Scrittura</span><span class="sxs-lookup"><span data-stu-id="9e306-179">R/W: Read/write</span></span><br /><br /> <span data-ttu-id="9e306-180">Impostazione predefinita: nessuna</span><span class="sxs-lookup"><span data-stu-id="9e306-180">Default: None</span></span><br /><br /> <span data-ttu-id="9e306-181">Descrizione: il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native client non supporta questa proprietà.</span><span class="sxs-lookup"><span data-stu-id="9e306-181">Description: The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider does not support this property.</span></span> <span data-ttu-id="9e306-182">I tentativi di impostare la proprietà in **CreateIndex** determinano un valore restituito DB_S_ERRORSOCCURRED.</span><span class="sxs-lookup"><span data-stu-id="9e306-182">Attempts to set the property in **CreateIndex** cause a DB_S_ERRORSOCCURRED return value.</span></span> <span data-ttu-id="9e306-183">Il membro *dwStatus* della struttura di proprietà indica DBPROPSTATUS_BADVALUE.</span><span class="sxs-lookup"><span data-stu-id="9e306-183">The *dwStatus* member of the property structure indicates DBPROPSTATUS_BADVALUE.</span></span>|  
|<span data-ttu-id="9e306-184">DBPROP_INDEX_UNIQUE</span><span class="sxs-lookup"><span data-stu-id="9e306-184">DBPROP_INDEX_UNIQUE</span></span>|<span data-ttu-id="9e306-185">R/W (L/S): Lettura/Scrittura</span><span class="sxs-lookup"><span data-stu-id="9e306-185">R/W: Read/write</span></span><br /><br /> <span data-ttu-id="9e306-186">Predefinito: VARIANT_FALSE</span><span class="sxs-lookup"><span data-stu-id="9e306-186">Default: VARIANT_FALSE</span></span><br /><br /> <span data-ttu-id="9e306-187">Descrizione: crea l'indice come vincolo UNIQUE nella colonna o nelle colonne utilizzate.</span><span class="sxs-lookup"><span data-stu-id="9e306-187">Description: Creates the index as a UNIQUE constraint on the participating column or columns.</span></span><br /><br /> <span data-ttu-id="9e306-188">VARIANT_TRUE: l'indice viene utilizzato per vincolare in modo univoco i valori della tabella.</span><span class="sxs-lookup"><span data-stu-id="9e306-188">VARIANT_TRUE: The index is used to uniquely constrain row values in the table.</span></span><br /><br /> <span data-ttu-id="9e306-189">VARIANT_FALSE: l'indice non vincola in modo univoco i valori di riga.</span><span class="sxs-lookup"><span data-stu-id="9e306-189">VARIANT_FALSE: The index does not uniquely constrain row values.</span></span>|  
  
 <span data-ttu-id="9e306-190">Nel set di proprietà specifico del provider DBPROPSET_SQLSERVERINDEX, il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native Client definisce la seguente proprietà delle informazioni sull'origine dati.</span><span class="sxs-lookup"><span data-stu-id="9e306-190">In the provider-specific property set DBPROPSET_SQLSERVERINDEX, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider defines the following data source information property.</span></span>  
  
|<span data-ttu-id="9e306-191">ID proprietà</span><span class="sxs-lookup"><span data-stu-id="9e306-191">Property ID</span></span>|<span data-ttu-id="9e306-192">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9e306-192">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="9e306-193">SSPROP_INDEX_XML</span><span class="sxs-lookup"><span data-stu-id="9e306-193">SSPROP_INDEX_XML</span></span>|<span data-ttu-id="9e306-194">Tipo: VT_BOOL (L/S)</span><span class="sxs-lookup"><span data-stu-id="9e306-194">Type: VT_BOOL (R/W)</span></span><br /><br /> <span data-ttu-id="9e306-195">Predefinito: VARIANT_FALSE</span><span class="sxs-lookup"><span data-stu-id="9e306-195">Default: VARIANT_FALSE</span></span><br /><br /> <span data-ttu-id="9e306-196">Descrizione: quando questa proprietà viene specificata con un valore VARIANT_TRUE con IIndexDefinition::CreateIndex, determina la creazione di un indice xml primario corrispondente alla colonna indicizzata.</span><span class="sxs-lookup"><span data-stu-id="9e306-196">Description: When this property is specified with a value of VARIANT_TRUE with IIndexDefinition::CreateIndex, it results in a primary xml index being created corresponding to the column being indexed.</span></span> <span data-ttu-id="9e306-197">Se questa proprietà è VARIANT_TRUE, cIndexColumnDescs deve essere 1, in caso contrario si tratta di un errore.</span><span class="sxs-lookup"><span data-stu-id="9e306-197">If this property is VARIANT_TRUE, cIndexColumnDescs should be 1, otherwise it is an error.</span></span>|  
  
 <span data-ttu-id="9e306-198">In questo esempio viene creato un indice di chiave primaria:</span><span class="sxs-lookup"><span data-stu-id="9e306-198">This example creates a primary key index:</span></span>  
  
```  
// This CREATE TABLE statement shows the referential integrity and   
// PRIMARY KEY constraint on the OrderDetails table that will be created   
// by the following example code.  
//  
// CREATE TABLE OrderDetails  
// (  
//    OrderID      int      NOT NULL  
//    ProductID   int      NOT NULL  
//        CONSTRAINT PK_OrderDetails  
//        PRIMARY KEY CLUSTERED (OrderID, ProductID),  
//    UnitPrice   money      NOT NULL,  
//    Quantity   int      NOT NULL,  
//    Discount   decimal(2,2)   NOT NULL  
//        DEFAULT 0  
// )  
//  
HRESULT CreatePrimaryKey  
    (  
    IIndexDefinition* pIIndexDefinition  
    )  
    {  
    HRESULT             hr = S_OK;  
  
    DBID                dbidTable;  
    DBID                dbidIndex;  
    const ULONG         nCols = 2;  
    ULONG               nCol;  
    const ULONG         nProps = 2;  
    ULONG               nProp;  
  
    DBINDEXCOLUMNDESC   dbidxcoldesc[nCols];  
    DBPROP              dbpropIndex[nProps];  
    DBPROPSET           dbpropset;  
  
    DBID*               pdbidIndexOut = NULL;  
  
    // Set up identifiers for the table and index.  
    dbidTable.eKind = DBKIND_NAME;  
    dbidTable.uName.pwszName = L"OrderDetails";  
  
    dbidIndex.eKind = DBKIND_NAME;  
    dbidIndex.uName.pwszName = L"PK_OrderDetails";  
  
    // Set up column identifiers.  
    for (nCol = 0; nCol < nCols; nCol++)  
        {  
        dbidxcoldesc[nCol].pColumnID = new DBID;  
        dbidxcoldesc[nCol].pColumnID->eKind = DBKIND_NAME;  
  
        dbidxcoldesc[nCol].eIndexColOrder = DBINDEX_COL_ORDER_ASC;  
        }  
    dbidxcoldesc[0].pColumnID->uName.pwszName = L"OrderID";  
    dbidxcoldesc[1].pColumnID->uName.pwszName = L"ProductID";  
  
    // Set properties for the index. The index is clustered,  
    // PRIMARY KEY.  
    for (nProp = 0; nProp < nProps; nProp++)  
        {  
        dbpropIndex[nProp].dwOptions = DBPROPOPTIONS_REQUIRED;  
        dbpropIndex[nProp].colid = DB_NULLID;  
  
        VariantInit(&(dbpropIndex[nProp].vValue));  
  
        dbpropIndex[nProp].vValue.vt = VT_BOOL;  
        }  
    dbpropIndex[0].dwPropertyID = DBPROP_INDEX_CLUSTERED;  
    dbpropIndex[0].vValue.boolVal = VARIANT_TRUE;  
  
    dbpropIndex[1].dwPropertyID = DBPROP_INDEX_PRIMARYKEY;  
    dbpropIndex[1].vValue.boolVal = VARIANT_TRUE;  
  
    dbpropset.rgProperties = dbpropIndex;  
    dbpropset.cProperties = nProps;  
    dbpropset.guidPropertySet = DBPROPSET_INDEX;  
  
    hr = pIIndexDefinition->CreateIndex(&dbidTable, &dbidIndex, nCols,  
        dbidxcoldesc, 1, &dbpropset, &pdbidIndexOut);  
  
    // Clean up dynamically allocated DBIDs.  
    for (nCol = 0; nCol < nCols; nCol++)  
        {  
        delete dbidxcoldesc[nCol].pColumnID;  
        }  
  
    return (hr);  
    }  
```  
  
## <a name="see-also"></a><span data-ttu-id="9e306-199">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9e306-199">See Also</span></span>  
 [<span data-ttu-id="9e306-200">Tabelle e indici</span><span class="sxs-lookup"><span data-stu-id="9e306-200">Tables and Indexes</span></span>](../../relational-databases/native-client-ole-db-tables-indexes/tables-and-indexes.md)  
  
  
