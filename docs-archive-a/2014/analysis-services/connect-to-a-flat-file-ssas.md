---
title: Connettersi a un file flat (SSAS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.connflatfile.f1
ms.assetid: a365991e-eded-4cd8-89c0-0daf6d658d15
author: minewiskan
ms.author: owend
ms.openlocfilehash: e6bee3c8f7f4b255e6985e8d783365bc8a47599e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625730"
---
# <a name="connect-to-a-flat-file-ssas"></a><span data-ttu-id="b084e-102">Connessione a un file flat (SSAS)</span><span class="sxs-lookup"><span data-stu-id="b084e-102">Connect to a Flat File (SSAS)</span></span>
  <span data-ttu-id="b084e-103">Questa pagina dell' **Importazione guidata tabella** consente di connettersi a un file flat (con estensione txt), a un file con valori delimitati da tabulazioni (con estensione tab) o a un file con valori delimitati da virgole (con estensione csv).</span><span class="sxs-lookup"><span data-stu-id="b084e-103">This page of the **Table Import Wizard** enables you to connect to a flat file (.txt), tab-separated file (.tab), or a comma-separated file (.csv).</span></span> <span data-ttu-id="b084e-104">Per accedere alla procedura guidata da [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], dal menu **Modello** selezionare **Importa da origine dati**.</span><span class="sxs-lookup"><span data-stu-id="b084e-104">To access the wizard from the [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], on the **Model** menu, click **Import from Data Source**.</span></span>  
  
 <span data-ttu-id="b084e-105">Per connettersi a un file flat, è necessario che nel computer sia installato il provider ACE.</span><span class="sxs-lookup"><span data-stu-id="b084e-105">To connect to a flat file, you must have the ACE provider installed on your computer.</span></span> <span data-ttu-id="b084e-106">Per altre informazioni, vedere [Origini dati supportate &#40;SSAS tabulare&#41;](tabular-models/data-sources-supported-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="b084e-106">For more information, see [Data Sources Supported &#40;SSAS Tabular&#41;](tabular-models/data-sources-supported-ssas-tabular.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b084e-107">Le credenziali dell'utente corrente vengono utilizzate in caso di selezione di un file in questa pagina.</span><span class="sxs-lookup"><span data-stu-id="b084e-107">The credentials of the current user are used when selecting a file in this page.</span></span> <span data-ttu-id="b084e-108">Tuttavia, l'importazione non verrà completata se l'utente specificato nella pagina Impostazioni di rappresentazione non dispone di privilegi sufficienti per leggere dal file selezionato.</span><span class="sxs-lookup"><span data-stu-id="b084e-108">However, import will not succeed if the user specified in the Impersonation Information page does not have sufficient privileges to read from the selected file.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="b084e-109">Elenco di elementi dell'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="b084e-109">UI element list</span></span>  
 <span data-ttu-id="b084e-110">**Nome descrittivo connessione**</span><span class="sxs-lookup"><span data-stu-id="b084e-110">**Friendly connection name**</span></span>  
 <span data-ttu-id="b084e-111">Digitare un nome univoco per questa connessione all'origine dati.</span><span class="sxs-lookup"><span data-stu-id="b084e-111">Type a unique name for this data source connection.</span></span> <span data-ttu-id="b084e-112">Questo campo è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="b084e-112">This is a required field.</span></span>  
  
 <span data-ttu-id="b084e-113">**Percorso file**</span><span class="sxs-lookup"><span data-stu-id="b084e-113">**File Path**</span></span>  
 <span data-ttu-id="b084e-114">Specificare un percorso completo per il file.</span><span class="sxs-lookup"><span data-stu-id="b084e-114">Specify a full path for the file.</span></span>  
  
 <span data-ttu-id="b084e-115">**Sfoglia**</span><span class="sxs-lookup"><span data-stu-id="b084e-115">**Browse**</span></span>  
 <span data-ttu-id="b084e-116">Selezionare il percorso in cui è disponibile un file.</span><span class="sxs-lookup"><span data-stu-id="b084e-116">Navigate to a location where a file is available.</span></span>  
  
 <span data-ttu-id="b084e-117">**Separatore colonne**</span><span class="sxs-lookup"><span data-stu-id="b084e-117">**Column Separator**</span></span>  
 <span data-ttu-id="b084e-118">Selezionare i separatori di colonna disponibili da un apposito elenco.</span><span class="sxs-lookup"><span data-stu-id="b084e-118">Select from a list of available column separators.</span></span> <span data-ttu-id="b084e-119">Scegliere un separatore che non sia già presente nel testo.</span><span class="sxs-lookup"><span data-stu-id="b084e-119">Choose a separator that is not likely to occur in the text.</span></span>  
  
|<span data-ttu-id="b084e-120">Valore</span><span class="sxs-lookup"><span data-stu-id="b084e-120">Value</span></span>|<span data-ttu-id="b084e-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b084e-121">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b084e-122">Tabulazione (t)</span><span class="sxs-lookup"><span data-stu-id="b084e-122">Tab (t)</span></span>|<span data-ttu-id="b084e-123">Le colonne sono separate da un carattere di tabulazione (t).</span><span class="sxs-lookup"><span data-stu-id="b084e-123">Columns are separated by a tab (t).</span></span>|  
|<span data-ttu-id="b084e-124">Virgola (,)</span><span class="sxs-lookup"><span data-stu-id="b084e-124">Comma (,)</span></span>|<span data-ttu-id="b084e-125">Le colonne sono separate da una virgola (,).</span><span class="sxs-lookup"><span data-stu-id="b084e-125">Columns are separated by a comma (,).</span></span>|  
|<span data-ttu-id="b084e-126">Punto e virgola (;)</span><span class="sxs-lookup"><span data-stu-id="b084e-126">Semicolon (;)</span></span>|<span data-ttu-id="b084e-127">Le colonne sono separate da un punto e virgola (;).</span><span class="sxs-lookup"><span data-stu-id="b084e-127">Columns are separated by a semicolon (;).</span></span>|  
|<span data-ttu-id="b084e-128">Spazio ( )</span><span class="sxs-lookup"><span data-stu-id="b084e-128">Space ( )</span></span>|<span data-ttu-id="b084e-129">Le colonne sono separate da uno spazio ( ).</span><span class="sxs-lookup"><span data-stu-id="b084e-129">Columns are separated by a space ( ).</span></span>|  
|<span data-ttu-id="b084e-130">Due punti (:)</span><span class="sxs-lookup"><span data-stu-id="b084e-130">Colon (:)</span></span>|<span data-ttu-id="b084e-131">Le colonne sono separate da due punti (:).</span><span class="sxs-lookup"><span data-stu-id="b084e-131">Columns are separated by a colon (:).</span></span>|  
|<span data-ttu-id="b084e-132">Barra verticale (&#124;)</span><span class="sxs-lookup"><span data-stu-id="b084e-132">Vertical Bar (&#124;)</span></span>|<span data-ttu-id="b084e-133">Le colonne sono separate da una barra verticale (&#124;).</span><span class="sxs-lookup"><span data-stu-id="b084e-133">Columns are separated by a vertical bar (&#124;).</span></span>|  
  
 <span data-ttu-id="b084e-134">**Funzionalità avanzate**</span><span class="sxs-lookup"><span data-stu-id="b084e-134">**Advanced**</span></span>  
 <span data-ttu-id="b084e-135">Specificare la codifica e le opzioni delle impostazioni locali per il file flat.</span><span class="sxs-lookup"><span data-stu-id="b084e-135">Specify the encoding and locale options for the flat file.</span></span>  
  
 <span data-ttu-id="b084e-136">**Utilizza la prima riga per le intestazioni di colonna**</span><span class="sxs-lookup"><span data-stu-id="b084e-136">**Use first row as column headers**</span></span>  
 <span data-ttu-id="b084e-137">Specificare se utilizzare la prima riga di dati per le intestazioni di colonna della tabella di destinazione.</span><span class="sxs-lookup"><span data-stu-id="b084e-137">Specify whether to use the first data row as the column headers of the destination table.</span></span>  
  
 <span data-ttu-id="b084e-138">**Anteprima dati**</span><span class="sxs-lookup"><span data-stu-id="b084e-138">**Data preview**</span></span>  
 <span data-ttu-id="b084e-139">Consente di visualizzare in anteprima i dati nel file selezionato e di utilizzare le opzioni seguenti per modificare l'importazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="b084e-139">Preview the data in the selected file, and use the following options to modify the data import.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b084e-140">Solo le prime 50 righe nel file vengono visualizzate in questa anteprima.</span><span class="sxs-lookup"><span data-stu-id="b084e-140">Only the first 50 rows in the file are displayed in this preview.</span></span>  
  
|<span data-ttu-id="b084e-141">Opzione</span><span class="sxs-lookup"><span data-stu-id="b084e-141">Option</span></span>|<span data-ttu-id="b084e-142">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b084e-142">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="b084e-143">**Casella di controllo nell'intestazione di colonna**</span><span class="sxs-lookup"><span data-stu-id="b084e-143">**Checkbox in the column header**</span></span>|<span data-ttu-id="b084e-144">Selezionare la casella di controllo per includere la colonna nell'importazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="b084e-144">Select the checkbox to include the column in the data import.</span></span> <span data-ttu-id="b084e-145">Deselezionare la casella di controllo per rimuovere la colonna dall'importazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="b084e-145">Clear the checkbox to remove the column from the data import.</span></span>|  
|<span data-ttu-id="b084e-146">**Pulsante freccia in giù nell'intestazione di colonna**</span><span class="sxs-lookup"><span data-stu-id="b084e-146">**Down-arrow button in the column header**</span></span>|<span data-ttu-id="b084e-147">Consente di ordinare e filtrare i dati nella colonna.</span><span class="sxs-lookup"><span data-stu-id="b084e-147">Sort and filter data in the column.</span></span>|  
  
 <span data-ttu-id="b084e-148">**Cancella filtri di riga**</span><span class="sxs-lookup"><span data-stu-id="b084e-148">**Clear Row Filters**</span></span>  
 <span data-ttu-id="b084e-149">Consente di rimuovere tutti i filtri applicati ai dati nelle colonne.</span><span class="sxs-lookup"><span data-stu-id="b084e-149">Remove all filters that were applied to the data in the columns.</span></span>  
  
  
