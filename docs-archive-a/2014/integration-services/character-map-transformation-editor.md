---
title: Editor trasformazione Mappa caratteri | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.charactermaptransformation.f1
helpviewer_keywords:
- Character Map Transformation Editor
ms.assetid: 3f1dbcf9-9cca-4606-bdcc-7ea6ad48cdf3
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c6cdcdba448dafc6ccf03774d4f611dee704b823
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626212"
---
# <a name="character-map-transformation-editor"></a><span data-ttu-id="ad22f-102">Editor trasformazione Mappa caratteri</span><span class="sxs-lookup"><span data-stu-id="ad22f-102">Character Map Transformation Editor</span></span>
  <span data-ttu-id="ad22f-103">Usare la finestra di dialogo **Editor trasformazione Mappa caratteri** per selezionare le funzioni per i valori stringa da applicare ai dati di colonna e per specificare se il mapping è una modifica sul posto o viene aggiunto come nuova colonna.</span><span class="sxs-lookup"><span data-stu-id="ad22f-103">Use the **Character Map Transformation Editor** dialog box to select the string functions to apply to column data and to specify whether mapping is an in-place change or added as a new column.</span></span>  
  
 <span data-ttu-id="ad22f-104">Per ulteriori informazioni sulla trasformazione Mappa caratteri, vedere [Character Map Transformation](data-flow/transformations/character-map-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="ad22f-104">To learn more about the Character Map transformation, see [Character Map Transformation](data-flow/transformations/character-map-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="ad22f-105">Opzioni</span><span class="sxs-lookup"><span data-stu-id="ad22f-105">Options</span></span>  
 <span data-ttu-id="ad22f-106">**Colonne di input disponibili**</span><span class="sxs-lookup"><span data-stu-id="ad22f-106">**Available Input Columns**</span></span>  
 <span data-ttu-id="ad22f-107">Utilizzare le caselle di controllo per selezionare le colonne da trasformare utilizzando le funzioni per i valori stringa.</span><span class="sxs-lookup"><span data-stu-id="ad22f-107">Use the check boxes to select the columns to transform using string functions.</span></span> <span data-ttu-id="ad22f-108">Le selezioni verranno visualizzate nella tabella sottostante.</span><span class="sxs-lookup"><span data-stu-id="ad22f-108">Your selections appear in the table below.</span></span>  
  
 <span data-ttu-id="ad22f-109">**Colonna di input**</span><span class="sxs-lookup"><span data-stu-id="ad22f-109">**Input Column**</span></span>  
 <span data-ttu-id="ad22f-110">Consente di visualizzare le colonne di input selezionate nella tabella precedente.</span><span class="sxs-lookup"><span data-stu-id="ad22f-110">View input columns selected from the table above.</span></span> <span data-ttu-id="ad22f-111">È inoltre possibile modificare o rimuovere una selezione utilizzando l'elenco di colonne di input disponibili.</span><span class="sxs-lookup"><span data-stu-id="ad22f-111">You can also change or remove a selection by using the list of available input columns.</span></span>  
  
 <span data-ttu-id="ad22f-112">**Destinazione**</span><span class="sxs-lookup"><span data-stu-id="ad22f-112">**Destination**</span></span>  
 <span data-ttu-id="ad22f-113">Consente di specificare se salvare i risultati delle operazioni di stringa sul posto, utilizzando la colonna esistente, o se salvare i dati modificati come nuova colonna.</span><span class="sxs-lookup"><span data-stu-id="ad22f-113">Specify whether to save the results of the string operations in place, using the existing column, or to save the modified data as a new column.</span></span>  
  
|<span data-ttu-id="ad22f-114">Valore</span><span class="sxs-lookup"><span data-stu-id="ad22f-114">Value</span></span>|<span data-ttu-id="ad22f-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ad22f-115">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ad22f-116">Nuova colonna</span><span class="sxs-lookup"><span data-stu-id="ad22f-116">New column</span></span>|<span data-ttu-id="ad22f-117">Consente di salvare i dati in una nuova colonna.</span><span class="sxs-lookup"><span data-stu-id="ad22f-117">Save the data in a new column.</span></span> <span data-ttu-id="ad22f-118">Assegnare il nome alla colonna in **Alias di output**.</span><span class="sxs-lookup"><span data-stu-id="ad22f-118">Assign the column name under **Output Alias**.</span></span>|  
|<span data-ttu-id="ad22f-119">Modifica sul posto</span><span class="sxs-lookup"><span data-stu-id="ad22f-119">In-place change</span></span>|<span data-ttu-id="ad22f-120">Consente di salvare i dati modificati nella colonna esistente.</span><span class="sxs-lookup"><span data-stu-id="ad22f-120">Save the modified data in the existing column.</span></span>|  
  
 <span data-ttu-id="ad22f-121">**Operazione**</span><span class="sxs-lookup"><span data-stu-id="ad22f-121">**Operation**</span></span>  
 <span data-ttu-id="ad22f-122">Consente di selezionare nell'elenco le funzioni per i valori stringa da applicare ai dati della colonna.</span><span class="sxs-lookup"><span data-stu-id="ad22f-122">Select from the list the string functions to apply to column data.</span></span>  
  
|<span data-ttu-id="ad22f-123">Valore</span><span class="sxs-lookup"><span data-stu-id="ad22f-123">Value</span></span>|<span data-ttu-id="ad22f-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ad22f-124">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ad22f-125">Lettere minuscole</span><span class="sxs-lookup"><span data-stu-id="ad22f-125">Lowercase</span></span>|<span data-ttu-id="ad22f-126">Consente di convertire la stringa in caratteri minuscoli.</span><span class="sxs-lookup"><span data-stu-id="ad22f-126">Convert to lower case.</span></span>|  
|<span data-ttu-id="ad22f-127">Maiuscolo</span><span class="sxs-lookup"><span data-stu-id="ad22f-127">Uppercase</span></span>|<span data-ttu-id="ad22f-128">Consente di convertire la stringa in caratteri maiuscoli.</span><span class="sxs-lookup"><span data-stu-id="ad22f-128">Convert to upper case.</span></span>|  
|<span data-ttu-id="ad22f-129">Inversione byte</span><span class="sxs-lookup"><span data-stu-id="ad22f-129">Byte reversal</span></span>|<span data-ttu-id="ad22f-130">Consente di eseguire la conversione invertendo l'ordine dei byte.</span><span class="sxs-lookup"><span data-stu-id="ad22f-130">Convert by reversing byte order.</span></span>|  
|<span data-ttu-id="ad22f-131">Hiragana</span><span class="sxs-lookup"><span data-stu-id="ad22f-131">Hiragana</span></span>|<span data-ttu-id="ad22f-132">Consente di convertire i caratteri giapponesi katakana in caratteri hiragana.</span><span class="sxs-lookup"><span data-stu-id="ad22f-132">Convert Japanese katakana characters to hiragana.</span></span>|  
|<span data-ttu-id="ad22f-133">Katakana</span><span class="sxs-lookup"><span data-stu-id="ad22f-133">Katakana</span></span>|<span data-ttu-id="ad22f-134">Consente di convertire i caratteri giapponesi hiragana in caratteri katakana.</span><span class="sxs-lookup"><span data-stu-id="ad22f-134">Convert Japanese hiragana characters to katakana.</span></span>|  
|<span data-ttu-id="ad22f-135">Metà larghezza</span><span class="sxs-lookup"><span data-stu-id="ad22f-135">Half width</span></span>|<span data-ttu-id="ad22f-136">Consente di convertire i caratteri a larghezza intera in caratteri a metà larghezza.</span><span class="sxs-lookup"><span data-stu-id="ad22f-136">Convert full-width characters to half width.</span></span>|  
|<span data-ttu-id="ad22f-137">Larghezza intera</span><span class="sxs-lookup"><span data-stu-id="ad22f-137">Full width</span></span>|<span data-ttu-id="ad22f-138">Consente di convertire i caratteri a metà larghezza in caratteri a larghezza intera.</span><span class="sxs-lookup"><span data-stu-id="ad22f-138">Convert half-width characters to full width.</span></span>|  
|<span data-ttu-id="ad22f-139">Conversione da maiuscole a minuscole (e viceversa) basata sulla lingua</span><span class="sxs-lookup"><span data-stu-id="ad22f-139">Linguistic casing</span></span>|<span data-ttu-id="ad22f-140">Consente di applicare le regole di conversione da maiuscole a minuscole (e viceversa) basata sulla lingua, ovvero il mapping Unicode semplice tra maiuscole e minuscole per il turco e altre impostazioni locali, al posto delle regole di sistema.</span><span class="sxs-lookup"><span data-stu-id="ad22f-140">Apply linguistic rules of casing (Unicode simple case mapping for Turkic and other locales) instead of the system rules.</span></span>|  
|<span data-ttu-id="ad22f-141">Cinese semplificato</span><span class="sxs-lookup"><span data-stu-id="ad22f-141">Simplified Chinese</span></span>|<span data-ttu-id="ad22f-142">Consente di convertire i caratteri in cinese tradizionale in caratteri in cinese semplificato.</span><span class="sxs-lookup"><span data-stu-id="ad22f-142">Convert traditional Chinese characters to simplified Chinese.</span></span>|  
|<span data-ttu-id="ad22f-143">Cinese tradizionale</span><span class="sxs-lookup"><span data-stu-id="ad22f-143">Traditional Chinese</span></span>|<span data-ttu-id="ad22f-144">Consente di convertire i caratteri in cinese semplificato in caratteri in cinese tradizionale.</span><span class="sxs-lookup"><span data-stu-id="ad22f-144">Convert simplified Chinese characters to traditional Chinese.</span></span>|  
  
 <span data-ttu-id="ad22f-145">**Alias di output**</span><span class="sxs-lookup"><span data-stu-id="ad22f-145">**Output Alias**</span></span>  
 <span data-ttu-id="ad22f-146">Consente di digitare un alias per ogni colonna di output.</span><span class="sxs-lookup"><span data-stu-id="ad22f-146">Type an alias for each output column.</span></span> <span data-ttu-id="ad22f-147">L'impostazione predefinita è **Copia di** seguita dal nome della colonna di input.  È comunque possibile scegliere qualsiasi nome descrittivo univoco.</span><span class="sxs-lookup"><span data-stu-id="ad22f-147">The default is **Copy of** followed by the input column name; however, you can choose any unique, descriptive name.</span></span>  
  
 <span data-ttu-id="ad22f-148">**Configura output errori**</span><span class="sxs-lookup"><span data-stu-id="ad22f-148">**Configure Error Output**</span></span>  
 <span data-ttu-id="ad22f-149">Usare la finestra di dialogo [Configura output errori](../../2014/integration-services/configure-error-output.md) per specificare le opzioni di gestione degli errori per la trasformazione corrente.</span><span class="sxs-lookup"><span data-stu-id="ad22f-149">Use the [Configure Error Output](../../2014/integration-services/configure-error-output.md) dialog box to specify error handling options for this transformation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad22f-150">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ad22f-150">See Also</span></span>  
 [<span data-ttu-id="ad22f-151">Guida di riferimento ai messaggi e agli errori di Integration Services</span><span class="sxs-lookup"><span data-stu-id="ad22f-151">Integration Services Error and Message Reference</span></span>](../../2014/integration-services/integration-services-error-and-message-reference.md)  
  
  
