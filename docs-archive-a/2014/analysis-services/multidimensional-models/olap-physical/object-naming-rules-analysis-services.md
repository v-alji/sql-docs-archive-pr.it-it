---
title: Regole di denominazione degli oggetti (Analysis Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- objects [Analysis Services], naming
ms.assetid: b338a60d-4802-4b68-862a-6dc6a3f75e48
author: minewiskan
ms.author: owend
ms.openlocfilehash: 6adfd4b23b6fe9129641271fc3c2381e161119ea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635801"
---
# <a name="object-naming-rules-analysis-services"></a><span data-ttu-id="21bfc-102">Regole di denominazione degli oggetti (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="21bfc-102">Object Naming Rules (Analysis Services)</span></span>
  <span data-ttu-id="21bfc-103">In questo argomento vengono descritte le convenzioni di denominazione dell'oggetto, le parole riservate e i caratteri che non possono essere utilizzati nel nome dell'oggetto, nel codice o nello script in [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="21bfc-103">This topic describes object naming conventions, as well as the reserved words and characters that cannot be used in any object name, in code or script in [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span></span>  
  
##  <a name="naming-conventions"></a><a name="bkmk_Names"></a><span data-ttu-id="21bfc-104">Convenzioni di denominazione</span><span class="sxs-lookup"><span data-stu-id="21bfc-104">Naming Conventions</span></span>  
 <span data-ttu-id="21bfc-105">Ogni oggetto dispone di una proprietà `Name` e `ID` che deve essere univoca nell'ambito della raccolta padre.</span><span class="sxs-lookup"><span data-stu-id="21bfc-105">Every object has a `Name` and `ID` property that must be unique within the scope of the parent collection.</span></span> <span data-ttu-id="21bfc-106">Ad esempio, due dimensioni possono avere lo stesso nome fintanto che ciascuna risiede in un database diverso.</span><span class="sxs-lookup"><span data-stu-id="21bfc-106">For example, two dimensions can have same name as long as each one resides in a different database.</span></span>  
  
 <span data-ttu-id="21bfc-107">Sebbene sia possibile specificarlo manualmente, l'`ID` viene solitamente generato automaticamente quando viene creato l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="21bfc-107">Although you can specify it manually, the `ID` is typically auto-generated when the object is created.</span></span> <span data-ttu-id="21bfc-108">Si consiglia di non modificare mai la proprietà `ID` una volta avviata la compilazione di un modello.</span><span class="sxs-lookup"><span data-stu-id="21bfc-108">You should never change the `ID` once you have begun building a model.</span></span> <span data-ttu-id="21bfc-109">In un modello tutti i riferimenti agli oggetti sono basati sull'`ID`.</span><span class="sxs-lookup"><span data-stu-id="21bfc-109">All object references throughout a model are based on the `ID`.</span></span> <span data-ttu-id="21bfc-110">Pertanto, la modifica dell'`ID` può facilmente causare il danneggiamento del modello.</span><span class="sxs-lookup"><span data-stu-id="21bfc-110">Thus, changing an `ID` can easily result in model corruption.</span></span>  
  
 <span data-ttu-id="21bfc-111">Gli oggetti `DataSource` e `DataSourceView` presentano eccezioni rilevanti alle convenzioni di denominazione.</span><span class="sxs-lookup"><span data-stu-id="21bfc-111">`DataSource` and `DataSourceView` objects have notable exceptions to naming conventions.</span></span> <span data-ttu-id="21bfc-112">L'ID `DataSource` può essere impostato su un punto singolo (.), che non è univoco, come riferimento al database corrente.</span><span class="sxs-lookup"><span data-stu-id="21bfc-112">`DataSource` ID can be set to a single dot (.), which is not unique, as a reference to the current database.</span></span> <span data-ttu-id="21bfc-113">Una seconda eccezione è `DataSourceView`, che aderisce alle convenzioni di denominazione definite per gli oggetti `DataSet` in .NET Framework, dove la proprietà `Name` viene utilizzata come identificatore.</span><span class="sxs-lookup"><span data-stu-id="21bfc-113">A second exception is `DataSourceView`, which adheres to the naming conventions defined for `DataSet` objects in the .NET Framework, where the `Name` is used as the identifier.</span></span>  
  
 <span data-ttu-id="21bfc-114">Le regole seguenti si applicano alle proprietà `Name` e `ID`.</span><span class="sxs-lookup"><span data-stu-id="21bfc-114">The following rules apply to `Name` and `ID` properties.</span></span>  
  
-   <span data-ttu-id="21bfc-115">Per i nomi non viene fatta distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="21bfc-115">Names are case insensitive.</span></span> <span data-ttu-id="21bfc-116">Non è possibile avere un cubo denominato "Sales" e un altro denominato "Sales" nello stesso database.</span><span class="sxs-lookup"><span data-stu-id="21bfc-116">You cannot have a cube named "sales" and another named "Sales" in the same database.</span></span>  
  
-   <span data-ttu-id="21bfc-117">Gli spazi iniziali o finali non sono consentiti nel nome dell'oggetto, sebbene sia possibile incorporare gli spazi all'interno del nome.</span><span class="sxs-lookup"><span data-stu-id="21bfc-117">No leading or trailing spaces allowed in an object name, although you can embed spaces within a name.</span></span> <span data-ttu-id="21bfc-118">Gli spazi iniziali e finali vengono eliminati in modo implicito.</span><span class="sxs-lookup"><span data-stu-id="21bfc-118">Leading and trailing spaces are implicitly trimmed.</span></span> <span data-ttu-id="21bfc-119">Ciò si applica sia alle proprietà `Name` e `ID` di un oggetto.</span><span class="sxs-lookup"><span data-stu-id="21bfc-119">This applies to both the `Name` and `ID` of an object.</span></span>  
  
-   <span data-ttu-id="21bfc-120">Il numero massimo di caratteri consentito è 100.</span><span class="sxs-lookup"><span data-stu-id="21bfc-120">The maximum number of characters is 100.</span></span>  
  
-   <span data-ttu-id="21bfc-121">Non esiste alcun particolare requisito per il primo carattere di un identificatore,</span><span class="sxs-lookup"><span data-stu-id="21bfc-121">There is no special requirement for the first character of an identifier.</span></span> <span data-ttu-id="21bfc-122">che può pertanto essere qualsiasi carattere valido.</span><span class="sxs-lookup"><span data-stu-id="21bfc-122">The first character may be any valid character.</span></span>  
  
##  <a name="reserved-words-and-characters"></a><a name="bkmk_reserved"></a><span data-ttu-id="21bfc-123">Parole riservate e caratteri</span><span class="sxs-lookup"><span data-stu-id="21bfc-123">Reserved Words and Characters</span></span>  
 <span data-ttu-id="21bfc-124">Le parole riservate sono in inglese e si applicano ai nomi di oggetto, non alle didascalie.</span><span class="sxs-lookup"><span data-stu-id="21bfc-124">Reserved words are in English, and apply to object names, not Captions.</span></span> <span data-ttu-id="21bfc-125">Se si utilizza inavvertitamente una parola riservata in un nome di oggetto, si verificherà un errore di convalida.</span><span class="sxs-lookup"><span data-stu-id="21bfc-125">If you inadvertently use a reserved word in an object name, a validation error will occur.</span></span> <span data-ttu-id="21bfc-126">Per i modelli di data mining e multidimensionali, le parole riservate descritte di seguito non possono mai essere utilizzate in alcun nome di oggetto.</span><span class="sxs-lookup"><span data-stu-id="21bfc-126">For multidimensional and data mining models, the reserved words described below cannot be used in any object name, at any time.</span></span>  
  
 <span data-ttu-id="21bfc-127">Per i modelli tabulari dove la compatibilità di database è impostata su 1103, le regole di convalida sono state rese flessibili per alcuni oggetti, non conformi per i requisiti di caratteri estesi e le convenzioni di denominazione di alcune applicazioni client.</span><span class="sxs-lookup"><span data-stu-id="21bfc-127">For tabular models, where the database compatibility is set to 1103, validation rules have been relaxed for certain objects, out of compliance for the extended character requirements and naming conventions of certain client applications.</span></span> <span data-ttu-id="21bfc-128">I database che soddisfano questi criteri sono soggetti a regole di convalida meno restrittive.</span><span class="sxs-lookup"><span data-stu-id="21bfc-128">Databases that meet these criteria are subject to less stringent validation rules.</span></span> <span data-ttu-id="21bfc-129">In questo caso è possibile che un nome di oggetto includa un carattere limitato e superi comunque la convalida.</span><span class="sxs-lookup"><span data-stu-id="21bfc-129">In this case, it's possible for an object name to include a restricted character and still pass validation.</span></span>  
  
 <span data-ttu-id="21bfc-130">**Parole riservate**</span><span class="sxs-lookup"><span data-stu-id="21bfc-130">**Reserved Words**</span></span>  
  
-   <span data-ttu-id="21bfc-131">AUX</span><span class="sxs-lookup"><span data-stu-id="21bfc-131">AUX</span></span>  
  
-   <span data-ttu-id="21bfc-132">CLOCK$</span><span class="sxs-lookup"><span data-stu-id="21bfc-132">CLOCK$</span></span>  
  
-   <span data-ttu-id="21bfc-133">COM1 tramite COM9 (COM1, COM2, COM3 e così via)</span><span class="sxs-lookup"><span data-stu-id="21bfc-133">COM1 through COM9 (COM1, COM2, COM3, and so on)</span></span>  
  
-   <span data-ttu-id="21bfc-134">CON</span><span class="sxs-lookup"><span data-stu-id="21bfc-134">CON</span></span>  
  
-   <span data-ttu-id="21bfc-135">LPT1 tramite LPT9 (LPT1, LPT2, LPT3 e così via)</span><span class="sxs-lookup"><span data-stu-id="21bfc-135">LPT1 through LPT9 (LPT1, LPT2, LPT3, and so on)</span></span>  
  
-   <span data-ttu-id="21bfc-136">NUL</span><span class="sxs-lookup"><span data-stu-id="21bfc-136">NUL</span></span>  
  
-   <span data-ttu-id="21bfc-137">PRN</span><span class="sxs-lookup"><span data-stu-id="21bfc-137">PRN</span></span>  
  
-   <span data-ttu-id="21bfc-138">Non è consentito utilizzare NULL come carattere in una stringa all'interno del frammento XML</span><span class="sxs-lookup"><span data-stu-id="21bfc-138">NULL is not allowed as a character in any string within the XML</span></span>  
  
 <span data-ttu-id="21bfc-139">**Caratteri riservati**</span><span class="sxs-lookup"><span data-stu-id="21bfc-139">**Reserved Characters**</span></span>  
  
 <span data-ttu-id="21bfc-140">Nella tabella seguente sono elencati i caratteri non validi per oggetti specifici.</span><span class="sxs-lookup"><span data-stu-id="21bfc-140">The following table lists invalid characters for specific objects.</span></span>  
  
|<span data-ttu-id="21bfc-141">Oggetto</span><span class="sxs-lookup"><span data-stu-id="21bfc-141">Object</span></span>|<span data-ttu-id="21bfc-142">Caratteri non validi</span><span class="sxs-lookup"><span data-stu-id="21bfc-142">Invalid characters</span></span>|  
|------------|------------------------|  
|`Server`|<span data-ttu-id="21bfc-143">Seguire le convenzioni di denominazione del server Windows quando si denomina un oggetto server.</span><span class="sxs-lookup"><span data-stu-id="21bfc-143">Follow Windows server naming conventions when naming a server object.</span></span> <span data-ttu-id="21bfc-144">Per informazioni dettagliate, vedere [convenzioni di denominazione (Windows)](/windows/desktop/DNS/naming-conventions) .</span><span class="sxs-lookup"><span data-stu-id="21bfc-144">See [Naming Conventions (Windows)](/windows/desktop/DNS/naming-conventions) for details.</span></span>|  
|`DataSource`| `: / \ * \| ? " () [] {} <>` |  
|<span data-ttu-id="21bfc-145">`Level` o `Attribute`</span><span class="sxs-lookup"><span data-stu-id="21bfc-145">`Level` or `Attribute`</span></span>|````. , ; ' ` : / \ * & \| ? " & % $ ! + = [] {} < >````|  
|<span data-ttu-id="21bfc-146">`Dimension` o `Hierarchy`</span><span class="sxs-lookup"><span data-stu-id="21bfc-146">`Dimension` or `Hierarchy`</span></span>|````. , ; ' ` : / \ * \| ? " & % $ ! + = () [] {} <,>````|  
|<span data-ttu-id="21bfc-147">Tutti gli altri oggetti</span><span class="sxs-lookup"><span data-stu-id="21bfc-147">All other objects</span></span>|````. , ; ' ` : / \ * \| ? " & % $ ! + = () [] {} < >````|  
  
 <span data-ttu-id="21bfc-148">**Eccezioni: quando sono consentiti i caratteri riservati**</span><span class="sxs-lookup"><span data-stu-id="21bfc-148">**Exceptions: When Reserved Characters are Allowed**</span></span>  
  
 <span data-ttu-id="21bfc-149">Come è stato notato, i database di un livello di compatibilità e di modalità specifico possono avere nomi di oggetti che includono caratteri riservati.</span><span class="sxs-lookup"><span data-stu-id="21bfc-149">As noted, databases of a specific modality and compatibility level can have object names that include reserved characters.</span></span> <span data-ttu-id="21bfc-150">I nomi di attributi della dimensione, gerarchie, livelli, misuri e oggetti KPI possono includere caratteri riservati, per database tabulari (1103 o un valore superiore) che consentono l'utilizzo di caratteri estesi:</span><span class="sxs-lookup"><span data-stu-id="21bfc-150">Dimension attribute, hierarchy, level, measure and KPI object names can include reserved characters, for tabular databases (1103 or higher) that allow the use of extended characters:</span></span>  
  
|<span data-ttu-id="21bfc-151">Livello di compatibilità del database e modalità del server</span><span class="sxs-lookup"><span data-stu-id="21bfc-151">Server mode and database compatibility level</span></span>|<span data-ttu-id="21bfc-152">Caratteri riservati consentiti?</span><span class="sxs-lookup"><span data-stu-id="21bfc-152">Reserved characters allowed?</span></span>|  
|--------------------------------------------------|----------------------------------|  
|<span data-ttu-id="21bfc-153">MOLAP (tutte le versioni)</span><span class="sxs-lookup"><span data-stu-id="21bfc-153">MOLAP (all versions)</span></span>|<span data-ttu-id="21bfc-154">No</span><span class="sxs-lookup"><span data-stu-id="21bfc-154">No</span></span>|  
|<span data-ttu-id="21bfc-155">Tabulare - 1050</span><span class="sxs-lookup"><span data-stu-id="21bfc-155">Tabular - 1050</span></span>|<span data-ttu-id="21bfc-156">No</span><span class="sxs-lookup"><span data-stu-id="21bfc-156">No</span></span>|  
|<span data-ttu-id="21bfc-157">Tabulare - 1100</span><span class="sxs-lookup"><span data-stu-id="21bfc-157">Tabular - 1100</span></span>|<span data-ttu-id="21bfc-158">No</span><span class="sxs-lookup"><span data-stu-id="21bfc-158">No</span></span>|  
|<span data-ttu-id="21bfc-159">Tabulare-1130 e versioni successive</span><span class="sxs-lookup"><span data-stu-id="21bfc-159">Tabular - 1130 and higher</span></span>|<span data-ttu-id="21bfc-160">Sì</span><span class="sxs-lookup"><span data-stu-id="21bfc-160">Yes</span></span>|  
  
 <span data-ttu-id="21bfc-161">I database possono avere un valore ModelType predefinito.</span><span class="sxs-lookup"><span data-stu-id="21bfc-161">Databases can have a ModelType of default.</span></span> <span data-ttu-id="21bfc-162">Il valore predefinito è equivalente a multidimensionale e quindi non supporta l'utilizzo di caratteri riservati nei nomi delle colonne.</span><span class="sxs-lookup"><span data-stu-id="21bfc-162">Default is equivalent to multidimensional, and thus does not support the use of reserved characters in column names.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21bfc-163">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="21bfc-163">See Also</span></span>  
 <span data-ttu-id="21bfc-164">[Parole riservate MDX](/sql/mdx/mdx-reserved-words) </span><span class="sxs-lookup"><span data-stu-id="21bfc-164">[MDX Reserved Words](/sql/mdx/mdx-reserved-words) </span></span>  
 <span data-ttu-id="21bfc-165">[Traduzioni &#40;Analysis Services&#41;](/analysis-services/translation-support-in-analysis-services) </span><span class="sxs-lookup"><span data-stu-id="21bfc-165">[Translations &#40;Analysis Services&#41;](/analysis-services/translation-support-in-analysis-services) </span></span>  
 [<span data-ttu-id="21bfc-166">XML for Analysis di conformità &#40;XMLA&#41;</span><span class="sxs-lookup"><span data-stu-id="21bfc-166">XML for Analysis Compliance &#40;XMLA&#41;</span></span>](https://docs.microsoft.com/bi-reference/xmla/xml-for-analysis-compliance-xmla)  
  
  
