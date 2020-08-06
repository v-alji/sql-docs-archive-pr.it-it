---
title: Query XPath di esempio (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- examples [SQLXML], XPath
- sample applications [SQLXML]
- sample XPath queries [SQLXML]
- mapping schema [SQLXML], queries
- XPath queries [SQLXML], samples
ms.assetid: 1595c2d4-0e9c-4969-84c8-a793a32df57d
author: rothja
ms.author: jroth
ms.openlocfilehash: 08ed32433e9bed4cc1542d6700ad73dc96f3c2dc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623998"
---
# <a name="sample-xpath-queries-sqlxml-40"></a><span data-ttu-id="c57ef-102">Query XPath di esempio (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="c57ef-102">Sample XPath Queries (SQLXML 4.0)</span></span>
  <span data-ttu-id="c57ef-103">In questa sezione vengono forniti esempi di query XPath per SQLXML 4.0.</span><span class="sxs-lookup"><span data-stu-id="c57ef-103">This section provides examples of XPath queries for SQLXML 4.0.</span></span> <span data-ttu-id="c57ef-104">A scopo illustrativo, queste query XPath di esempio vengono specificate in un modello eseguito utilizzando ADO.</span><span class="sxs-lookup"><span data-stu-id="c57ef-104">For illustration purposes, these example XPath queries are specified in a template executed using ADO.</span></span> <span data-ttu-id="c57ef-105">È pertanto necessario utilizzare un file dello schema di mapping, SampleSchema1.xml, anch'esso fornito in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="c57ef-105">Therefore, you must use a mapping schema file, SampleSchema1.xml, which is also provided in this section.</span></span> <span data-ttu-id="c57ef-106">Salvare questo file nella directory in cui vengono archiviati i modelli.</span><span class="sxs-lookup"><span data-stu-id="c57ef-106">Save this file in the directory where your templates are stored.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c57ef-107">Le query di esempio presentate in questa sezione vengono raggruppate in base al tipo di operazione XPath eseguita dalla query.</span><span class="sxs-lookup"><span data-stu-id="c57ef-107">The sample queries in this section are grouped by the type of XPath operation that is performed by the query.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c57ef-108">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="c57ef-108">In This Section</span></span>  
 [<span data-ttu-id="c57ef-109">Schema XSD con annotazioni di esempio per gli esempi XPath &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="c57ef-109">Sample Annotated XSD Schema for XPath Examples &#40;SQLXML 4.0&#41;</span></span>](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md)  
 <span data-ttu-id="c57ef-110">Utilizzare questo file con gli esempi di query XPath fornito in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="c57ef-110">Use this file with the XPath query examples provided in this section.</span></span>  
  
 [<span data-ttu-id="c57ef-111">Specifica di assi in query XPath &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="c57ef-111">Specifying Axes in XPath Queries &#40;SQLXML 4.0&#41;</span></span>](specifying-axes-in-xpath-queries-sqlxml-4-0.md)  
 <span data-ttu-id="c57ef-112">Viene illustrato come vengono specificati gli assi nelle query XPath.</span><span class="sxs-lookup"><span data-stu-id="c57ef-112">Illustrates how axes are specified in XPath queries.</span></span>  
  
 [<span data-ttu-id="c57ef-113">Specifica di predicati con valori booleani nelle query XPath &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="c57ef-113">Specifying Boolean-Valued Predicates in XPath Queries &#40;SQLXML 4.0&#41;</span></span>](specifying-boolean-valued-predicates-in-xpath-queries-sqlxml-4-0.md)  
 <span data-ttu-id="c57ef-114">Viene illustrato come vengono specificati i predicati con valori booleani nelle query XPath.</span><span class="sxs-lookup"><span data-stu-id="c57ef-114">Illustrates how Boolean-valued predicates are specified in XPath queries.</span></span>  
  
 [<span data-ttu-id="c57ef-115">Specifica di operatori relazionali nelle query XPath &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="c57ef-115">Specifying Relational Operators in XPath Queries &#40;SQLXML 4.0&#41;</span></span>](specifying-relational-operators-in-xpath-queries-sqlxml-4-0.md)  
 <span data-ttu-id="c57ef-116">Viene illustrato come vengono specificati gli operatori relazionali nelle query XPath.</span><span class="sxs-lookup"><span data-stu-id="c57ef-116">Illustrates how relational operators are specified in XPath queries.</span></span>  
  
 [<span data-ttu-id="c57ef-117">Specifica di operatori aritmetici nelle query XPath &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="c57ef-117">Specifying Arithmetic Operators in XPath Queries &#40;SQLXML 4.0&#41;</span></span>](specifying-arithmetic-operators-in-xpath-queries-sqlxml-4-0.md)  
 <span data-ttu-id="c57ef-118">Viene illustrato come vengono specificati gli operatori aritmetici nelle query XPath.</span><span class="sxs-lookup"><span data-stu-id="c57ef-118">Illustrates how arithmetic operators are specified in XPath queries.</span></span>  
  
 [<span data-ttu-id="c57ef-119">Specifica di funzioni di conversione esplicita nelle query XPath &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="c57ef-119">Specifying Explicit Conversion Functions in XPath Queries &#40;SQLXML 4.0&#41;</span></span>](specifying-explicit-conversion-functions-in-xpath-queries-sqlxml-4-0.md)  
 <span data-ttu-id="c57ef-120">Viene illustrato come specificare le funzioni di conversione esplicita nelle query XPath.</span><span class="sxs-lookup"><span data-stu-id="c57ef-120">Illustrates how explicit conversion functions are specified in XPath queries.</span></span>  
  
 [<span data-ttu-id="c57ef-121">Specifica di operatori booleani in query XPath &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="c57ef-121">Specifying Boolean Operators in XPath Queries &#40;SQLXML 4.0&#41;</span></span>](specifying-boolean-operators-in-xpath-queries-sqlxml-4-0.md)  
 <span data-ttu-id="c57ef-122">Viene illustrato come vengono specificati gli operatori booleani nelle query XPath.</span><span class="sxs-lookup"><span data-stu-id="c57ef-122">Illustrates how Boolean operators are specified in XPath queries.</span></span>  
  
 [<span data-ttu-id="c57ef-123">Specifica di funzioni booleane in query XPath &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="c57ef-123">Specifying Boolean Functions in XPath Queries &#40;SQLXML 4.0&#41;</span></span>](specifying-boolean-functions-in-xpath-queries-sqlxml-4-0.md)  
 <span data-ttu-id="c57ef-124">Viene illustrato come vengono specificate le funzioni booleane nelle query XPath.</span><span class="sxs-lookup"><span data-stu-id="c57ef-124">Illustrates how Boolean functions are specified in XPath queries.</span></span>  
  
 [<span data-ttu-id="c57ef-125">Specifica di variabili XPath in query XPath &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="c57ef-125">Specifying XPath Variables in XPath Queries &#40;SQLXML 4.0&#41;</span></span>](specifying-xpath-variables-in-xpath-queries-sqlxml-4-0.md)  
 <span data-ttu-id="c57ef-126">Viene illustrato come vengono specificate le variabili XPath nelle query XPath.</span><span class="sxs-lookup"><span data-stu-id="c57ef-126">Illustrates how XPath variables are specified in XPath queries.</span></span>  
  
  
