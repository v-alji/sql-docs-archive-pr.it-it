---
title: Editor trasformazione Estrazione termini (scheda Avanzate) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.termextraction.advanced.f1
helpviewer_keywords:
- Term Extraction Transformation Editor
ms.assetid: 87118281-6e3c-499e-bac4-fa4c24bb12c6
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f4be56f8ac2deeab49e43071a07894a466019287
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718468"
---
# <a name="term-extraction-transformation-editor-advanced-tab"></a><span data-ttu-id="94241-102">Editor trasformazione Estrazione termini (Scheda Avanzate)</span><span class="sxs-lookup"><span data-stu-id="94241-102">Term Extraction Transformation Editor (Advanced Tab)</span></span>
  <span data-ttu-id="94241-103">Usare la scheda **Avanzate** della finestra di dialogo **Editor trasformazione Estrazione termini** per specificare le proprietà per l'estrazione, ad esempio la frequenza, la lunghezza e le eventuali parole o frasi da estrarre.</span><span class="sxs-lookup"><span data-stu-id="94241-103">Use the **Advanced** tab of the **Term Extraction Transformation Editor** dialog box to specify properties for the extraction such as frequency, length, and whether to extract words or phrases.</span></span>  
  
 <span data-ttu-id="94241-104">Per ulteriori informazioni sulla trasformazione Estrazione termini, vedere [Term Extraction Transformation](data-flow/transformations/term-extraction-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="94241-104">To learn more about the Term Extraction transformation, see [Term Extraction Transformation](data-flow/transformations/term-extraction-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="94241-105">Opzioni</span><span class="sxs-lookup"><span data-stu-id="94241-105">Options</span></span>  
 <span data-ttu-id="94241-106">**Sostantivo**</span><span class="sxs-lookup"><span data-stu-id="94241-106">**Noun**</span></span>  
 <span data-ttu-id="94241-107">Consente di specificare che la trasformazione estrarrà solo singoli sostantivi.</span><span class="sxs-lookup"><span data-stu-id="94241-107">Specify that the transformation extracts individual nouns only.</span></span>  
  
 <span data-ttu-id="94241-108">**Sintagma nominale**</span><span class="sxs-lookup"><span data-stu-id="94241-108">**Noun phrase**</span></span>  
 <span data-ttu-id="94241-109">Consente di specificare che la trasformazione estrarrà solo sintagmi nominali.</span><span class="sxs-lookup"><span data-stu-id="94241-109">Specify that the transformation extracts noun phrases only.</span></span>  
  
 <span data-ttu-id="94241-110">**Sostantivo e sintagma nominale**</span><span class="sxs-lookup"><span data-stu-id="94241-110">**Noun and noun phrase**</span></span>  
 <span data-ttu-id="94241-111">Consente di specificare che la trasformazione estrarrà sia sostantivi che sintagmi nominali.</span><span class="sxs-lookup"><span data-stu-id="94241-111">Specify that the transformation extracts both nouns and noun phrases.</span></span>  
  
 <span data-ttu-id="94241-112">**Frequenza**</span><span class="sxs-lookup"><span data-stu-id="94241-112">**Frequency**</span></span>  
 <span data-ttu-id="94241-113">Consente di specificare che il punteggio è rappresentato dalla frequenza del termine.</span><span class="sxs-lookup"><span data-stu-id="94241-113">Specify that the score is the frequency of the term.</span></span>  
  
 <span data-ttu-id="94241-114">**TFIDF**</span><span class="sxs-lookup"><span data-stu-id="94241-114">**TFIDF**</span></span>  
 <span data-ttu-id="94241-115">Consente di specificare che il punteggio è rappresentato dal valore TFIDF del termine.</span><span class="sxs-lookup"><span data-stu-id="94241-115">Specify that the score is the TFIDF value of the term.</span></span> <span data-ttu-id="94241-116">Il punteggio TFIDF è il prodotto della frequenza dei termini e della frequenza inversa dei documenti, definito come: TFIDF di un termine T = (frequenza di T) \* log( (numero di righe nell'input) / (numero di righe contenenti T) )</span><span class="sxs-lookup"><span data-stu-id="94241-116">The TFIDF score is the product of Term Frequency and Inverse Document Frequency, defined as: TFIDF of a Term T = (frequency of T) \* log( (#rows in Input) / (#rows having T) )</span></span>  
  
 <span data-ttu-id="94241-117">**Soglia di frequenza**</span><span class="sxs-lookup"><span data-stu-id="94241-117">**Frequency threshold**</span></span>  
 <span data-ttu-id="94241-118">Consente di specificare il numero di volte in cui una parola o una frase deve ricorrere prima che venga estratta.</span><span class="sxs-lookup"><span data-stu-id="94241-118">Specify the number of times a word or phrase must occur before extracting it.</span></span> <span data-ttu-id="94241-119">Il valore predefinito è 2.</span><span class="sxs-lookup"><span data-stu-id="94241-119">The default value is 2.</span></span>  
  
 <span data-ttu-id="94241-120">**Lunghezza massima termine**</span><span class="sxs-lookup"><span data-stu-id="94241-120">**Maximum length of term**</span></span>  
 <span data-ttu-id="94241-121">Consente di specificare la lunghezza massima in parole di una frase.</span><span class="sxs-lookup"><span data-stu-id="94241-121">Specify the maximum length of a phrase in words.</span></span> <span data-ttu-id="94241-122">Questa opzione ha effetto soltanto sui sintagmi nominali.</span><span class="sxs-lookup"><span data-stu-id="94241-122">This option affects noun phrases only.</span></span> <span data-ttu-id="94241-123">Il valore predefinito è 12.</span><span class="sxs-lookup"><span data-stu-id="94241-123">The default value is 12.</span></span>  
  
 <span data-ttu-id="94241-124">**Estrazione con distinzione maiuscole/minuscole**</span><span class="sxs-lookup"><span data-stu-id="94241-124">**Use case-sensitive term extraction**</span></span>  
 <span data-ttu-id="94241-125">Consente di specificare se eseguire l'estrazione rilevando la distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="94241-125">Specify whether to make the extraction case-sensitive.</span></span> <span data-ttu-id="94241-126">Il valore predefinito è `False`.</span><span class="sxs-lookup"><span data-stu-id="94241-126">The default is `False`.</span></span>  
  
 <span data-ttu-id="94241-127">**Configura output errori**</span><span class="sxs-lookup"><span data-stu-id="94241-127">**Configure Error Output**</span></span>  
 <span data-ttu-id="94241-128">Usare la finestra di dialogo [Configura output errori](../../2014/integration-services/configure-error-output.md) per specificare la gestione degli errori per le righe che causano errori.</span><span class="sxs-lookup"><span data-stu-id="94241-128">Use the [Configure Error Output](../../2014/integration-services/configure-error-output.md) dialog box to specify error handling for rows that cause errors.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94241-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="94241-129">See Also</span></span>  
 <span data-ttu-id="94241-130">[Guida di riferimento ai messaggi e agli errori di Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="94241-130">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="94241-131">[Editor trasformazione Estrazione termini &#40;scheda Estrazione termini&#41;](../../2014/integration-services/term-extraction-transformation-editor-term-extraction-tab.md) </span><span class="sxs-lookup"><span data-stu-id="94241-131">[Term Extraction Transformation Editor &#40;Term Extraction Tab&#41;](../../2014/integration-services/term-extraction-transformation-editor-term-extraction-tab.md) </span></span>  
 <span data-ttu-id="94241-132">[Editor trasformazione Estrazione termini &#40;scheda esclusione&#41;](../../2014/integration-services/term-extraction-transformation-editor-exclusion-tab.md) </span><span class="sxs-lookup"><span data-stu-id="94241-132">[Term Extraction Transformation Editor &#40;Exclusion Tab&#41;](../../2014/integration-services/term-extraction-transformation-editor-exclusion-tab.md) </span></span>  
 [<span data-ttu-id="94241-133">Trasformazione Ricerca termini</span><span class="sxs-lookup"><span data-stu-id="94241-133">Term Lookup Transformation</span></span>](data-flow/transformations/lookup-transformation.md)  
  
  
