---
title: Usare la modalità PATH con FOR XML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- PATH FOR XML mode
- characters [SQL Server], XML
- aliases [SQL Server], XML
- FOR XML clause, PATH mode
- FOR XML PATH mode
- column names [SQL Server]
- XPath queries [SQL Server]
ms.assetid: a685a9ad-3d28-4596-aa72-119202df3976
author: rothja
ms.author: jroth
ms.openlocfilehash: ce0cf811f1e610d14a94993b54c51ea079f613e9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629264"
---
# <a name="use-path-mode-with-for-xml"></a><span data-ttu-id="a860a-102">Utilizzare la modalità PATH con FOR XML</span><span class="sxs-lookup"><span data-stu-id="a860a-102">Use PATH Mode with FOR XML</span></span>
  <span data-ttu-id="a860a-103">Come descritto nell'argomento [Costruzione di codice XML tramite la clausola FOR XML](for-xml-sql-server.md), la modalità PATH consente di combinare in modo più semplice elementi e attributi.</span><span class="sxs-lookup"><span data-stu-id="a860a-103">As described in [Constructing XML Using FOR XML](for-xml-sql-server.md), the PATH mode provides a simpler way to mix elements and attributes.</span></span> <span data-ttu-id="a860a-104">e di introdurre nidificazione aggiuntiva per la rappresentazione di proprietà complesse.</span><span class="sxs-lookup"><span data-stu-id="a860a-104">PATH mode is also a simpler way to introduce additional nesting for representing complex properties.</span></span> <span data-ttu-id="a860a-105">È possibile utilizzare query in modalità FOR XML EXPLICIT per la costruzione di questo tipo di strutture XML da un set di righe, ma la modalità PATH costituisce un'alternativa più semplice alla formulazione di query in modalità EXPLICIT, che può essere un'operazione complessa.</span><span class="sxs-lookup"><span data-stu-id="a860a-105">You can use FOR XML EXPLICIT mode queries to construct such XML from a rowset, but the PATH mode provides a simpler alternative to the potentially cumbersome EXPLICIT mode queries.</span></span> <span data-ttu-id="a860a-106">La modalità PATH, insieme alla possibilità di scrivere query FOR XML nidificate e alla direttiva TYPE per restituire istanze di tipo **xml** , consente di formulare più facilmente le query.</span><span class="sxs-lookup"><span data-stu-id="a860a-106">PATH mode, together with the ability to write nested FOR XML queries and the TYPE directive to return **xml** type instances, allows you to write queries with less complexity.</span></span>  
  
 <span data-ttu-id="a860a-107">In modalità PATH i nomi e gli alias di colonna vengono gestiti come espressioni XPath.</span><span class="sxs-lookup"><span data-stu-id="a860a-107">In PATH mode, column names or column aliases are treated as XPath expressions.</span></span> <span data-ttu-id="a860a-108">Queste espressioni indicano il modo in cui viene eseguito il mapping tra i valori e il codice XML.</span><span class="sxs-lookup"><span data-stu-id="a860a-108">These expressions indicate how the values are being mapped to XML.</span></span> <span data-ttu-id="a860a-109">Ogni espressione XPath è un XPath relativo che specifica il tipo dell'elemento, ad esempio attributo, elemento e valore scalare, nonché il nome e la gerarchia del nodo che verrà generato in relazione all'elemento riga.</span><span class="sxs-lookup"><span data-stu-id="a860a-109">Each XPath expression is a relative XPath that provides the item type., such as the attribute, element, and scalar value, and the name and hierarchy of the node that will be generated relative to the row element.</span></span>  
  
 <span data-ttu-id="a860a-110">In questa sezione viene descritto il mapping delle colonne in un set di righe in varie condizioni e vengono forniti alcuni esempi.</span><span class="sxs-lookup"><span data-stu-id="a860a-110">This section describes mapping columns in a rowset under various conditions, and provides examples.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a860a-111">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="a860a-111">In This Section</span></span>  
  
-   [<span data-ttu-id="a860a-112">Colonne senza nome</span><span class="sxs-lookup"><span data-stu-id="a860a-112">Columns without a Name</span></span>](columns-without-a-name.md)  
  
-   [<span data-ttu-id="a860a-113">Colonne provviste di un nome</span><span class="sxs-lookup"><span data-stu-id="a860a-113">Columns with a Name</span></span>](columns-with-a-name.md)  
  
-   [<span data-ttu-id="a860a-114">Colonne con nome specificato come carattere jolly</span><span class="sxs-lookup"><span data-stu-id="a860a-114">Columns with a Name Specified as a Wildcard Character</span></span>](columns-with-a-name-specified-as-a-wildcard-character.md)  
  
-   [<span data-ttu-id="a860a-115">Colonne con il nome di un test di nodo XPath</span><span class="sxs-lookup"><span data-stu-id="a860a-115">Columns with the Name of an XPath Node Test</span></span>](columns-with-the-name-of-an-xpath-node-test.md)  
  
-   [<span data-ttu-id="a860a-116">Nomi di colonna con il percorso specificato come data&#40;&#41;</span><span class="sxs-lookup"><span data-stu-id="a860a-116">Column Names with the Path Specified as data&#40;&#41;</span></span>](column-names-with-the-path-specified-as-data.md)  
  
-   [<span data-ttu-id="a860a-117">Colonne contenenti un valore NULL per impostazione predefinita</span><span class="sxs-lookup"><span data-stu-id="a860a-117">Columns that Contain a Null Value By Default</span></span>](columns-that-contain-a-null-value-by-default.md)  
  
-   [<span data-ttu-id="a860a-118">Supporto dello spazio dei nomi in modalità di PATH</span><span class="sxs-lookup"><span data-stu-id="a860a-118">Namespace Support in PATH Mode</span></span>](namespace-support-in-path-mode.md)  
  
-   [<span data-ttu-id="a860a-119">Esempi: Utilizzo della modalità PATH</span><span class="sxs-lookup"><span data-stu-id="a860a-119">Examples: Using PATH Mode</span></span>](examples-using-path-mode.md)  
  
## <a name="see-also"></a><span data-ttu-id="a860a-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a860a-120">See Also</span></span>  
 <span data-ttu-id="a860a-121">[Aggiungere spazi dei nomi alle query con WITH XMLNAMESPACES](add-namespaces-to-queries-with-with-xmlnamespaces.md) </span><span class="sxs-lookup"><span data-stu-id="a860a-121">[Add Namespaces to Queries with WITH XMLNAMESPACES](add-namespaces-to-queries-with-with-xmlnamespaces.md) </span></span>  
 <span data-ttu-id="a860a-122">[SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a860a-122">[SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql) </span></span>  
 [<span data-ttu-id="a860a-123">FOR XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a860a-123">FOR XML &#40;SQL Server&#41;</span></span>](for-xml-sql-server.md)  
  
  
