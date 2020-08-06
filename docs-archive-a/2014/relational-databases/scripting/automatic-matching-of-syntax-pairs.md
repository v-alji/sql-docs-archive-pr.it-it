---
title: Corrispondenza automatica di coppie della sintassi
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- IntelliSense [SQL Server], delimiter highlighting
- IntelliSense [SQL Server], syntax pair matching
ms.assetid: bfc54cda-bfd6-4545-a5b9-f9db2ae13769
author: rothja
ms.author: jroth
ms.openlocfilehash: d1237eeb9aaec39e3210b00c880c0005ef3d95bd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627168"
---
# <a name="automatic-matching-of-syntax-pairs"></a><span data-ttu-id="be1c1-102">Corrispondenza automatica di coppie della sintassi</span><span class="sxs-lookup"><span data-stu-id="be1c1-102">Automatic Matching of Syntax Pairs</span></span>
  <span data-ttu-id="be1c1-103">La corrispondenza automatica di coppie della sintassi consente di verificare immediatamente se gli elementi della sintassi che devono essere codificati in coppie sono abbinati correttamente.</span><span class="sxs-lookup"><span data-stu-id="be1c1-103">Automatic matching of syntax pairs gives you immediate feedback on whether syntax elements that must be coded in pairs are correctly paired.</span></span> <span data-ttu-id="be1c1-104">Questa corrispondenza è nota come corrispondenza tra delimitatori nell'editor di query del [!INCLUDE[ssDE](../../includes/ssde-md.md)] , corrispondenza tra parentesi graffe nell'editor di query XMLA di Analysis Services e corrispondenza tra parentesi negli editor MDX e DMX.</span><span class="sxs-lookup"><span data-stu-id="be1c1-104">This is known as delimiter matching in the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor, brace matching in the Analysis Services XMLA Query Editor, and parenthesis matching in the MDX and DMX editors.</span></span>  
  
## <a name="database-engine-query-editor-delimiter-matching"></a><span data-ttu-id="be1c1-105">Corrispondenza tra delimitatori nell'editor di query del Motore di database</span><span class="sxs-lookup"><span data-stu-id="be1c1-105">Database Engine Query Editor Delimiter Matching</span></span>  
 <span data-ttu-id="be1c1-106">Nell'editor di query del [!INCLUDE[ssDE](../../includes/ssde-md.md)] viene individuata la corrispondenza tra i delimitatori che identificano i limiti dei blocchi di codice.</span><span class="sxs-lookup"><span data-stu-id="be1c1-106">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor matches the delimiters that identify the boundaries of code blocks.</span></span> <span data-ttu-id="be1c1-107">Ciò avviene in due modi:</span><span class="sxs-lookup"><span data-stu-id="be1c1-107">The matching is done in two ways:</span></span>  
  
-   <span data-ttu-id="be1c1-108">L'editor evidenzia entrambi delimitatori di una coppia quando si finisce di digitare il secondo delimitatore della coppia.</span><span class="sxs-lookup"><span data-stu-id="be1c1-108">The editor highlights both delimiters in a pair when you finish typing the second delimiter in the pair.</span></span>  
  
-   <span data-ttu-id="be1c1-109">Ogni volta che il cursore si trova in uno dei delimitatori di una coppia, è possibile utilizzare il tasto di scelta rapida CTRL+] per passare al delimitatore corrispondente.</span><span class="sxs-lookup"><span data-stu-id="be1c1-109">Anytime the cursor is in one of the delimiters in a pair, you can use the CTRL+] keyboard shortcut to jump to the matching delimiter.</span></span>  
  
### <a name="delimiter-pairs"></a><span data-ttu-id="be1c1-110">Coppie di delimitatori</span><span class="sxs-lookup"><span data-stu-id="be1c1-110">Delimiter Pairs</span></span>  
 <span data-ttu-id="be1c1-111">La corrispondenza tra delimitatori automatica riconosce i seguenti set di delimitatori:</span><span class="sxs-lookup"><span data-stu-id="be1c1-111">Automatic delimiter matching recognizes the following sets of delimiters:</span></span>  
  
|<span data-ttu-id="be1c1-112">Delimitatore iniziale</span><span class="sxs-lookup"><span data-stu-id="be1c1-112">Lead Delimiter</span></span>|<span data-ttu-id="be1c1-113">Delimitatore di chiusura</span><span class="sxs-lookup"><span data-stu-id="be1c1-113">Closing Delimiter</span></span>|  
|--------------------|-----------------------|  
|<span data-ttu-id="be1c1-114">**(**</span><span class="sxs-lookup"><span data-stu-id="be1c1-114">**(**</span></span>|<span data-ttu-id="be1c1-115">**)**</span><span class="sxs-lookup"><span data-stu-id="be1c1-115">**)**</span></span>|  
|<span data-ttu-id="be1c1-116">**BEGIN**</span><span class="sxs-lookup"><span data-stu-id="be1c1-116">**BEGIN**</span></span>|<span data-ttu-id="be1c1-117">**END**</span><span class="sxs-lookup"><span data-stu-id="be1c1-117">**END**</span></span>|  
|<span data-ttu-id="be1c1-118">**BEGIN TRY**</span><span class="sxs-lookup"><span data-stu-id="be1c1-118">**BEGIN TRY**</span></span>|<span data-ttu-id="be1c1-119">**END TRY**</span><span class="sxs-lookup"><span data-stu-id="be1c1-119">**END TRY**</span></span>|  
|<span data-ttu-id="be1c1-120">**BEGIN CATCH**</span><span class="sxs-lookup"><span data-stu-id="be1c1-120">**BEGIN CATCH**</span></span>|<span data-ttu-id="be1c1-121">**END CATCH**</span><span class="sxs-lookup"><span data-stu-id="be1c1-121">**END CATCH**</span></span>|  
  
 <span data-ttu-id="be1c1-122">La corrispondenza tra delimitatori automatica non riconosce i delimitatori per gli identificatori inseriti tra parentesi ([NomeOggetto]) o gli identificatori tra virgolette ("NomeOggetto").</span><span class="sxs-lookup"><span data-stu-id="be1c1-122">Automatic delimiter matching does not recognize the delimiters for bracketed identifiers ([ObjectName]), or quoted identifiers ("ObjectName").</span></span> <span data-ttu-id="be1c1-123">La corrispondenza di coppie non abbina le virgolette singole per i valori letterali stringa ('stringa') perché la codifica dei colori indica già se la stringa è stata delimitata o meno.</span><span class="sxs-lookup"><span data-stu-id="be1c1-123">Pair matching does not match the single quotation delimiters for string literals ('string') because color coding already gives a visual indication of whether the string has been delimited.</span></span>  
  
### <a name="delimiter-highlighting"></a><span data-ttu-id="be1c1-124">Evidenziazione dei delimitatori</span><span class="sxs-lookup"><span data-stu-id="be1c1-124">Delimiter Highlighting</span></span>  
 <span data-ttu-id="be1c1-125">La corrispondenza evidenzia sia l'elemento iniziale che l'elemento di chiusura di una coppia di delimitatori.</span><span class="sxs-lookup"><span data-stu-id="be1c1-125">Matching highlights both the lead and closing element of a pair of delimiters.</span></span> <span data-ttu-id="be1c1-126">In questo modo è possibile identificare visivamente blocchi di codice e verificare eventuali coppie di delimitatori non corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="be1c1-126">This lets you visually identify code blocks and check for mismatched pairs of delimiters.</span></span>  
  
 <span data-ttu-id="be1c1-127">I delimitatori vengono evidenziati quando si digita la lettera finale che completa la coppia.</span><span class="sxs-lookup"><span data-stu-id="be1c1-127">Delimiters are highlighted when you type the final letter that completes the pair.</span></span> <span data-ttu-id="be1c1-128">Per una coppia BEGIN END in cui si digita prima BEGIN e successivamente END, ad esempio, l'evidenziazione viene attivata quando si digita la lettera finale in END.</span><span class="sxs-lookup"><span data-stu-id="be1c1-128">For example, for a BEGIN END pair where you type BEGIN first followed by END, highlighting turns on when you type the final letter in END.</span></span> <span data-ttu-id="be1c1-129">Non è necessario digitare il delimitatore iniziale seguito dal delimitatore di chiusura per attivare l'evidenziazione.</span><span class="sxs-lookup"><span data-stu-id="be1c1-129">You do not have to type the lead delimiter followed by the closing delimiter to turn on highlighting.</span></span> <span data-ttu-id="be1c1-130">Se si digita END come primo delimitatore e successivamente si scorre all'indietro lo script per digitare BEGIN, l'evidenziazione viene attivata quando si digita la lettera finale in BEGIN.</span><span class="sxs-lookup"><span data-stu-id="be1c1-130">If you type END first, then scroll back up the script and type BEGIN, highlighting is turned on when you type the final letter in BEGIN.</span></span> <span data-ttu-id="be1c1-131">Non è necessario che la lettera finale digitata sia la lettera finale del delimitatore.</span><span class="sxs-lookup"><span data-stu-id="be1c1-131">The final letter typed does not have to be the end letter in the delimiter.</span></span> <span data-ttu-id="be1c1-132">Se ad esempio il delimitatore BEGIN viene scritto in modo errato come BEIN, la coppia BEGIN END viene evidenziata quando si inserisce la lettera G finale.</span><span class="sxs-lookup"><span data-stu-id="be1c1-132">For example, you could misspell BEGIN as BEIN, when you insert the final G the BEGIN END pair is highlighted.</span></span>  
  
 <span data-ttu-id="be1c1-133">La coppia di delimitatori rimane evidenziata fino a quando non si sposta il cursore.</span><span class="sxs-lookup"><span data-stu-id="be1c1-133">The delimiter pair remains highlighted until you move the cursor.</span></span> <span data-ttu-id="be1c1-134">L'evidenziazione viene disattivata quando il cursore viene spostato, anche se la nuova posizione del cursore non è diversa rispetto al delimitatore.</span><span class="sxs-lookup"><span data-stu-id="be1c1-134">The highlighting is turned off when the cursor is moved, even if the new cursor position remains in the same delimiter.</span></span> <span data-ttu-id="be1c1-135">È possibile attivare di nuovo l'evidenziazione eliminando e ridigitando qualsiasi lettera in un membro della coppia.</span><span class="sxs-lookup"><span data-stu-id="be1c1-135">You can turn the highlighting back on by deleting and retyping any letter in either member of the pair.</span></span>  
  
## <a name="analysis-services-xmla-query-editor-brace-matching"></a><span data-ttu-id="be1c1-136">Corrispondenza tra parentesi graffe nell'editor di query XMLA di Analysis Services</span><span class="sxs-lookup"><span data-stu-id="be1c1-136">Analysis Services XMLA Query Editor Brace Matching</span></span>  
 <span data-ttu-id="be1c1-137">La corrispondenza tra parentesi graffe nell'editor di query XMLA indica se sono stati chiusi elementi evidenziando parentesi graffe di apertura e di chiusura.</span><span class="sxs-lookup"><span data-stu-id="be1c1-137">The XMLA Query Editor brace matching shows if you have closed elements by highlighting opening and closing braces.</span></span> <span data-ttu-id="be1c1-138">È inoltre possibile utilizzare il tasto di scelta rapida CTRL+] per passare da una parentesi a quella corrispondente.</span><span class="sxs-lookup"><span data-stu-id="be1c1-138">You can also use the CTRL+] keyboard shortcut to jump from one brace to the matching brace.</span></span>  
  
 <span data-ttu-id="be1c1-139">Nell'editor di query XMLA la corrispondenza tra parentesi graffe viene eseguita per i termini seguenti:</span><span class="sxs-lookup"><span data-stu-id="be1c1-139">The XMLA Query Editor does brace matching for the following terms:</span></span>  
  
-   <span data-ttu-id="be1c1-140">Tag di inizio e di fine corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="be1c1-140">Matching start and end tags.</span></span>  
  
-   <span data-ttu-id="be1c1-141">Qualsiasi coppia di \<" and "> parentesi angolari "".</span><span class="sxs-lookup"><span data-stu-id="be1c1-141">Any pair of "\<" and ">" angle brackets.</span></span>  
  
-   <span data-ttu-id="be1c1-142">Inizio e fine di commenti.</span><span class="sxs-lookup"><span data-stu-id="be1c1-142">Start and end of comments.</span></span>  
  
-   <span data-ttu-id="be1c1-143">Inizio e fine di istruzioni di elaborazione.</span><span class="sxs-lookup"><span data-stu-id="be1c1-143">Start and end of processing instructions.</span></span>  
  
-   <span data-ttu-id="be1c1-144">Inizio e fine di blocchi CDATA.</span><span class="sxs-lookup"><span data-stu-id="be1c1-144">Start and end of CDATA blocks.</span></span>  
  
-   <span data-ttu-id="be1c1-145">Inizio e fine di dichiarazioni DTD.</span><span class="sxs-lookup"><span data-stu-id="be1c1-145">Start and end of DTD declarations.</span></span>  
  
-   <span data-ttu-id="be1c1-146">Virgolette di apertura e di chiusura sugli attributi.</span><span class="sxs-lookup"><span data-stu-id="be1c1-146">Opening and closing quotes on attributes.</span></span>  
  
## <a name="mdx-and-dmx-editor-parenthesis-matching"></a><span data-ttu-id="be1c1-147">Corrispondenza tra parentesi negli editor DMX e MDX</span><span class="sxs-lookup"><span data-stu-id="be1c1-147">MDX and DMX Editor Parenthesis Matching</span></span>  
 <span data-ttu-id="be1c1-148">Negli editor MDX (Multidimensional Expressions) e DMX (Data Mining Expressions) vengono messe automaticamente in corrispondenza le coppie di parentesi nelle funzioni.</span><span class="sxs-lookup"><span data-stu-id="be1c1-148">The Multi-Dimensional Expressions (MDX) and Data Mining Expressions (DMX) Editors automatically match parenthesis pairs in functions.</span></span>  
  
  
