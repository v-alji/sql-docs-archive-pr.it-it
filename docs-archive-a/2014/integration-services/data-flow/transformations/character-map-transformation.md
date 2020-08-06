---
title: Trasformazione Mappa caratteri | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.charactertrans.f1
helpviewer_keywords:
- mutually exclusive mapping [Integration Services]
- mapping data [Integration Services]
- string functions
- Character Map transformation [Integration Services]
ms.assetid: e0f50eb6-b893-400f-bb8c-fb3072cc2620
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b5fc31e1a3500a7a7b023e43a968e70e5b438dec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629950"
---
# <a name="character-map-transformation"></a><span data-ttu-id="3e3b4-102">Trasformazione Mappa caratteri</span><span class="sxs-lookup"><span data-stu-id="3e3b4-102">Character Map Transformation</span></span>
  <span data-ttu-id="3e3b4-103">La trasformazione Mappa caratteri consente di applicare funzioni per i valori stringa, quale la conversione da minuscolo a maiuscolo, a dati di tipo carattere.</span><span class="sxs-lookup"><span data-stu-id="3e3b4-103">The Character Map transformation applies string functions, such as conversion from lowercase to uppercase, to character data.</span></span> <span data-ttu-id="3e3b4-104">È possibile utilizzare questa trasformazione solo su dati di colonna con un tipo di dati string.</span><span class="sxs-lookup"><span data-stu-id="3e3b4-104">This transformation operates only on column data with a string data type.</span></span>  
  
 <span data-ttu-id="3e3b4-105">La trasformazione Mappa caratteri consente di convertire dati di colonna sul posto oppure di aggiungere una colonna all'output della trasformazione e inserire i dati convertiti nella nuova colonna.</span><span class="sxs-lookup"><span data-stu-id="3e3b4-105">The Character Map transformation can convert column data in place or add a column to the transformation output and put the converted data in the new column.</span></span> <span data-ttu-id="3e3b4-106">È possibile applicare vari set di operazioni di mapping alla stessa colonna di input e inserire i risultati in colonne diverse.</span><span class="sxs-lookup"><span data-stu-id="3e3b4-106">You can apply different sets of mapping operations to the same input column and put the results in different columns.</span></span> <span data-ttu-id="3e3b4-107">È ad esempio possibile convertire la stessa colonna in maiuscolo e minuscolo, quindi inserire i risultati in due colonne diverse.</span><span class="sxs-lookup"><span data-stu-id="3e3b4-107">For example, you can convert the same column to uppercase and lowercase and put the results in two different columns.</span></span>  
  
 <span data-ttu-id="3e3b4-108">In alcune circostanze il mapping può causare il troncamento dei dati.</span><span class="sxs-lookup"><span data-stu-id="3e3b4-108">Mapping can, under some circumstances, cause data to be truncated.</span></span> <span data-ttu-id="3e3b4-109">Può verificarsi un troncamento ad esempio in caso di mapping da caratteri a un byte a caratteri con rappresentazione MBCS (Multibyte Character Set).</span><span class="sxs-lookup"><span data-stu-id="3e3b4-109">For example, truncation can occur when single-byte characters are mapped to characters with a multibyte representation.</span></span> <span data-ttu-id="3e3b4-110">La trasformazione Mappa caratteri include un output degli errori, che può essere utilizzato per dirigere i dati troncati a un output distinto.</span><span class="sxs-lookup"><span data-stu-id="3e3b4-110">The Character Map transformation includes an error output, which can be used to direct truncated data to separate output.</span></span> <span data-ttu-id="3e3b4-111">Per altre informazioni, vedere [Gestione degli errori nei dati](../error-handling-in-data.md).</span><span class="sxs-lookup"><span data-stu-id="3e3b4-111">For more information, see [Error Handling in Data](../error-handling-in-data.md).</span></span>  
  
 <span data-ttu-id="3e3b4-112">Questa trasformazione include un input, un output e un output degli errori.</span><span class="sxs-lookup"><span data-stu-id="3e3b4-112">This transformation has one input, one output, and one error output.</span></span>  
  
## <a name="mapping-operations"></a><span data-ttu-id="3e3b4-113">Operazioni di mapping</span><span class="sxs-lookup"><span data-stu-id="3e3b4-113">Mapping Operations</span></span>  
 <span data-ttu-id="3e3b4-114">Nella tabella seguente vengono descritte le operazioni di mapping supportate dalla trasformazione Mappa caratteri.</span><span class="sxs-lookup"><span data-stu-id="3e3b4-114">The following table describes the mapping operations that the Character Map transformation supports.</span></span>  
  
|<span data-ttu-id="3e3b4-115">Operazione</span><span class="sxs-lookup"><span data-stu-id="3e3b4-115">Operation</span></span>|<span data-ttu-id="3e3b4-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3e3b4-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3e3b4-117">Inversione byte</span><span class="sxs-lookup"><span data-stu-id="3e3b4-117">Byte reversal</span></span>|<span data-ttu-id="3e3b4-118">Inverte l'ordine dei byte.</span><span class="sxs-lookup"><span data-stu-id="3e3b4-118">Reverses byte order.</span></span>|  
|<span data-ttu-id="3e3b4-119">Larghezza intera</span><span class="sxs-lookup"><span data-stu-id="3e3b4-119">Full width</span></span>|<span data-ttu-id="3e3b4-120">Esegue il mapping da caratteri a metà larghezza a caratteri a larghezza intera.</span><span class="sxs-lookup"><span data-stu-id="3e3b4-120">Maps half-width characters to full-width characters.</span></span>|  
|<span data-ttu-id="3e3b4-121">Metà larghezza</span><span class="sxs-lookup"><span data-stu-id="3e3b4-121">Half width</span></span>|<span data-ttu-id="3e3b4-122">Esegue il mapping da caratteri a larghezza intera a caratteri a metà larghezza.</span><span class="sxs-lookup"><span data-stu-id="3e3b4-122">Maps full-width characters to half-width characters.</span></span>|  
|<span data-ttu-id="3e3b4-123">Hiragana</span><span class="sxs-lookup"><span data-stu-id="3e3b4-123">Hiragana</span></span>|<span data-ttu-id="3e3b4-124">Esegue il mapping da caratteri Katakana a caratteri Hiragana.</span><span class="sxs-lookup"><span data-stu-id="3e3b4-124">Maps katakana characters to hiragana characters.</span></span>|  
|<span data-ttu-id="3e3b4-125">Katakana</span><span class="sxs-lookup"><span data-stu-id="3e3b4-125">Katakana</span></span>|<span data-ttu-id="3e3b4-126">Esegue il mapping da caratteri Hiragana a caratteri Katakana.</span><span class="sxs-lookup"><span data-stu-id="3e3b4-126">Maps hiragana characters to katakana characters.</span></span>|  
|<span data-ttu-id="3e3b4-127">Conversione da maiuscole a minuscole (e viceversa) basata sulla lingua</span><span class="sxs-lookup"><span data-stu-id="3e3b4-127">Linguistic casing</span></span>|<span data-ttu-id="3e3b4-128">Applica la conversione da maiuscole a minuscole (e viceversa) basata sulla lingua anziché le regole di sistema.</span><span class="sxs-lookup"><span data-stu-id="3e3b4-128">Applies linguistic casing instead of the system rules.</span></span> <span data-ttu-id="3e3b4-129">La conversione da maiuscole a minuscole (e viceversa) basata sulla lingua fa riferimento a una funzionalità disponibile nell'API Win32 per il mapping Unicode semplice tra maiuscole e minuscole per il turco e altre impostazioni locali.</span><span class="sxs-lookup"><span data-stu-id="3e3b4-129">Linguistic casing refers to functionality provided by the Win32 API for Unicode simple case mapping of Turkic and other locales.</span></span>|  
|<span data-ttu-id="3e3b4-130">Lettere minuscole</span><span class="sxs-lookup"><span data-stu-id="3e3b4-130">Lowercase</span></span>|<span data-ttu-id="3e3b4-131">Converte i caratteri in minuscolo.</span><span class="sxs-lookup"><span data-stu-id="3e3b4-131">Converts characters to lowercase.</span></span>|  
|<span data-ttu-id="3e3b4-132">Cinese semplificato</span><span class="sxs-lookup"><span data-stu-id="3e3b4-132">Simplified Chinese</span></span>|<span data-ttu-id="3e3b4-133">Esegue il mapping da caratteri in cinese tradizionale a caratteri in cinese semplificato.</span><span class="sxs-lookup"><span data-stu-id="3e3b4-133">Maps traditional Chinese characters to simplified Chinese characters.</span></span>|  
|<span data-ttu-id="3e3b4-134">Cinese tradizionale</span><span class="sxs-lookup"><span data-stu-id="3e3b4-134">Traditional Chinese</span></span>|<span data-ttu-id="3e3b4-135">Esegue il mapping da caratteri in cinese semplificato a caratteri in cinese tradizionale.</span><span class="sxs-lookup"><span data-stu-id="3e3b4-135">Maps simplified Chinese characters to traditional Chinese characters.</span></span>|  
|<span data-ttu-id="3e3b4-136">Maiuscolo</span><span class="sxs-lookup"><span data-stu-id="3e3b4-136">Uppercase</span></span>|<span data-ttu-id="3e3b4-137">Converte i caratteri in maiuscolo.</span><span class="sxs-lookup"><span data-stu-id="3e3b4-137">Converts characters to uppercase.</span></span>|  
  
## <a name="mutually-exclusive-mapping-operations"></a><span data-ttu-id="3e3b4-138">Operazioni di mapping che si escludono a vicenda</span><span class="sxs-lookup"><span data-stu-id="3e3b4-138">Mutually Exclusive Mapping Operations</span></span>  
 <span data-ttu-id="3e3b4-139">In una stessa trasformazione è possibile eseguire più di un'operazione.</span><span class="sxs-lookup"><span data-stu-id="3e3b4-139">More than one operation can be performed in a transformation.</span></span> <span data-ttu-id="3e3b4-140">Esistono tuttavia operazioni di mapping che si escludono a vicenda.</span><span class="sxs-lookup"><span data-stu-id="3e3b4-140">However, some mapping operations are mutually exclusive.</span></span> <span data-ttu-id="3e3b4-141">Nella tabella seguente sono elencate le restrizioni applicate quando vengono eseguite più operazioni sulla stessa colonna.</span><span class="sxs-lookup"><span data-stu-id="3e3b4-141">The following table lists restrictions that apply when you use multiple operations on the same column.</span></span> <span data-ttu-id="3e3b4-142">Le operazioni nelle colonne Operazione A e Operazione B si escludono a vicenda.</span><span class="sxs-lookup"><span data-stu-id="3e3b4-142">Operations in the columns Operation A and Operation B are mutually exclusive.</span></span>  
  
|<span data-ttu-id="3e3b4-143">Operazione A</span><span class="sxs-lookup"><span data-stu-id="3e3b4-143">Operation A</span></span>|<span data-ttu-id="3e3b4-144">Operazione B</span><span class="sxs-lookup"><span data-stu-id="3e3b4-144">Operation B</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="3e3b4-145">Lettere minuscole</span><span class="sxs-lookup"><span data-stu-id="3e3b4-145">Lowercase</span></span>|<span data-ttu-id="3e3b4-146">Maiuscolo</span><span class="sxs-lookup"><span data-stu-id="3e3b4-146">Uppercase</span></span>|  
|<span data-ttu-id="3e3b4-147">Hiragana</span><span class="sxs-lookup"><span data-stu-id="3e3b4-147">Hiragana</span></span>|<span data-ttu-id="3e3b4-148">Katakana</span><span class="sxs-lookup"><span data-stu-id="3e3b4-148">Katakana</span></span>|  
|<span data-ttu-id="3e3b4-149">Metà larghezza</span><span class="sxs-lookup"><span data-stu-id="3e3b4-149">Half width</span></span>|<span data-ttu-id="3e3b4-150">Larghezza intera</span><span class="sxs-lookup"><span data-stu-id="3e3b4-150">Full width</span></span>|  
|<span data-ttu-id="3e3b4-151">Cinese tradizionale</span><span class="sxs-lookup"><span data-stu-id="3e3b4-151">Traditional Chinese</span></span>|<span data-ttu-id="3e3b4-152">Cinese semplificato</span><span class="sxs-lookup"><span data-stu-id="3e3b4-152">Simplified Chinese</span></span>|  
|<span data-ttu-id="3e3b4-153">Lettere minuscole</span><span class="sxs-lookup"><span data-stu-id="3e3b4-153">Lowercase</span></span>|<span data-ttu-id="3e3b4-154">Hiragana, katakana, metà larghezza, larghezza intera</span><span class="sxs-lookup"><span data-stu-id="3e3b4-154">Hiragana, katakana, half width, full width</span></span>|  
|<span data-ttu-id="3e3b4-155">Maiuscolo</span><span class="sxs-lookup"><span data-stu-id="3e3b4-155">Uppercase</span></span>|<span data-ttu-id="3e3b4-156">Hiragana, katakana, metà larghezza, larghezza intera</span><span class="sxs-lookup"><span data-stu-id="3e3b4-156">Hiragana, katakana, half width, full width</span></span>|  
  
## <a name="configuration-of-the-character-map-transformation"></a><span data-ttu-id="3e3b4-157">Configurazione della trasformazione Mappa caratteri</span><span class="sxs-lookup"><span data-stu-id="3e3b4-157">Configuration of the Character Map Transformation</span></span>  
 <span data-ttu-id="3e3b4-158">Per configurare la trasformazione Mappa caratteri, procedere nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="3e3b4-158">You configure the Character Map transformation in the following ways:</span></span>  
  
-   <span data-ttu-id="3e3b4-159">Specificare le colonne da convertire.</span><span class="sxs-lookup"><span data-stu-id="3e3b4-159">Specify the columns to convert.</span></span>  
  
-   <span data-ttu-id="3e3b4-160">Specificare le operazioni da applicare a ogni colonna.</span><span class="sxs-lookup"><span data-stu-id="3e3b4-160">Specify the operations to apply to each column.</span></span>  
  
 <span data-ttu-id="3e3b4-161">È possibile impostare le proprietà tramite Progettazione [!INCLUDE[ssIS](../../../includes/ssis-md.md)] o a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="3e3b4-161">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="3e3b4-162">Per altre informazioni sulle proprietà che è possibile impostare nella finestra di dialogo **Editor trasformazione Mappa caratteri** , vedere [Editor trasformazione Mappa caratteri](../../character-map-transformation-editor.md).</span><span class="sxs-lookup"><span data-stu-id="3e3b4-162">For more information about the properties that you can set in the **Character Map Transformation Editor** dialog box, see [Character Map Transformation Editor](../../character-map-transformation-editor.md).</span></span>  
  
 <span data-ttu-id="3e3b4-163">Nella finestra di dialogo **Editor avanzato** sono disponibili le proprietà che è possibile impostare a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="3e3b4-163">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="3e3b4-164">Per ulteriori informazioni sulle proprietà che è possibile impostare nella finestra di dialogo **Editor avanzato** o a livello di codice, fare clic su uno degli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="3e3b4-164">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="3e3b4-165">Proprietà comuni</span><span class="sxs-lookup"><span data-stu-id="3e3b4-165">Common Properties</span></span>](../../common-properties.md)  
  
-   [<span data-ttu-id="3e3b4-166">Proprietà personalizzate delle trasformazioni</span><span class="sxs-lookup"><span data-stu-id="3e3b4-166">Transformation Custom Properties</span></span>](transformation-custom-properties.md)  
  
 <span data-ttu-id="3e3b4-167">Per ulteriori informazioni sulle procedure per l'impostazione delle proprietà, fare clic su uno degli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="3e3b4-167">For more information about how to set properties, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="3e3b4-168">Impostazione delle proprietà di un componente del flusso di dati</span><span class="sxs-lookup"><span data-stu-id="3e3b4-168">Set the Properties of a Data Flow Component</span></span>](../set-the-properties-of-a-data-flow-component.md)  
  
-   [<span data-ttu-id="3e3b4-169">Ordinare i dati per le trasformazioni Unione e Merge Join</span><span class="sxs-lookup"><span data-stu-id="3e3b4-169">Sort Data for the Merge and Merge Join Transformations</span></span>](sort-data-for-the-merge-and-merge-join-transformations.md)  
  
  
