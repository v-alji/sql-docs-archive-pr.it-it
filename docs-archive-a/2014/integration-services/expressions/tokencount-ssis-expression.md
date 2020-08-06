---
title: TOKENCOUNT (espressione SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 1c0efed1-c2b3-4f20-a3a1-ad91283b7c0a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9068e4958570a0222bc8e1a4c90d34acc5bdf3dc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716444"
---
# <a name="tokencount-ssis-expression"></a><span data-ttu-id="0fcc7-102">TOKENCOUNT (espressione SSIS)</span><span class="sxs-lookup"><span data-stu-id="0fcc7-102">TOKENCOUNT (SSIS Expression)</span></span>
  <span data-ttu-id="0fcc7-103">Restituisce il numero di token in una stringa che contiene token separati dai delimitatori specificati.</span><span class="sxs-lookup"><span data-stu-id="0fcc7-103">Returns the number of tokens in a string that contains tokens separated by the specified delimiters.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0fcc7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0fcc7-104">Syntax</span></span>  
  
```  
TOKENCOUNT(character_expression, delimiter_string)  
```  
  
## <a name="arguments"></a><span data-ttu-id="0fcc7-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="0fcc7-105">Arguments</span></span>  
 <span data-ttu-id="0fcc7-106">*character_expression*</span><span class="sxs-lookup"><span data-stu-id="0fcc7-106">*character_expression*</span></span>  
 <span data-ttu-id="0fcc7-107">Stringa che contiene token separati da delimitatori.</span><span class="sxs-lookup"><span data-stu-id="0fcc7-107">A string that contains tokens separated by delimiters.</span></span>  
  
 <span data-ttu-id="0fcc7-108">*delimiter_string*</span><span class="sxs-lookup"><span data-stu-id="0fcc7-108">*delimiter_string*</span></span>  
 <span data-ttu-id="0fcc7-109">Stringa che contiene caratteri delimitatori.</span><span class="sxs-lookup"><span data-stu-id="0fcc7-109">A string that contains delimiter characters.</span></span> <span data-ttu-id="0fcc7-110">Ad esempio, "; ," contiene i caratteri delimitatori punto e virgola, spazio e virgola.</span><span class="sxs-lookup"><span data-stu-id="0fcc7-110">For example, "; ," contains three delimiter characters semi-colon, a blank space, and a comma.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="0fcc7-111">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="0fcc7-111">Result Types</span></span>  
 <span data-ttu-id="0fcc7-112">DT_I4</span><span class="sxs-lookup"><span data-stu-id="0fcc7-112">DT_I4</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0fcc7-113">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="0fcc7-113">Remarks</span></span>  
 <span data-ttu-id="0fcc7-114">Le osservazioni seguenti riguardano la funzione TOKEN:</span><span class="sxs-lookup"><span data-stu-id="0fcc7-114">The following remarks apply to the TOKEN function:</span></span>  
  
-   <span data-ttu-id="0fcc7-115">La stringa di delimitazione può contenere uno o più caratteri delimitatori.</span><span class="sxs-lookup"><span data-stu-id="0fcc7-115">The delimiter string can contain one or more delimiter characters.</span></span>  
  
-   <span data-ttu-id="0fcc7-116">I delimitatori iniziali vengono ignorati.</span><span class="sxs-lookup"><span data-stu-id="0fcc7-116">Leading delimiters are skipped.</span></span>  
  
-   <span data-ttu-id="0fcc7-117">TOKENCOUNT funziona unicamente con il tipo di dati DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="0fcc7-117">TOKENCOUNT works only with the DT_WSTR data type.</span></span> <span data-ttu-id="0fcc7-118">Se l'argomento *character_expression* è un valore letterale stringa o una colonna di dati con tipo di dati DT_STR, prima di eseguire l'operazione prevista da TOKEN verrà eseguito il cast implicito al tipo di dati DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="0fcc7-118">A *character_expression* argument that is a string literal or a data column with the DT_STR data type is implicitly cast to the DT_WSTR data type before TOKEN performs its operation.</span></span> <span data-ttu-id="0fcc7-119">Per gli altri tipi di dati è necessario il cast esplicito al tipo di dati DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="0fcc7-119">Other data types must be explicitly cast to the DT_WSTR data type.</span></span>  
  
-   <span data-ttu-id="0fcc7-120">TOKENCOUNT restituisce 0 (zero) se character_expression è Null.</span><span class="sxs-lookup"><span data-stu-id="0fcc7-120">TOKENCOUNT returns 0 (zero) if the character_expression is null.</span></span>  
  
-   <span data-ttu-id="0fcc7-121">È possibile utilizzare variabili e colonne come argomenti di questa espressione.</span><span class="sxs-lookup"><span data-stu-id="0fcc7-121">You can use variables and columns as arguments for this expression.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="0fcc7-122">Esempi di espressione</span><span class="sxs-lookup"><span data-stu-id="0fcc7-122">Expression Examples</span></span>  
 <span data-ttu-id="0fcc7-123">Nell'esempio seguente, la funzione TOKENCOUNT restituisce 3 perché la stringa contiene tre token: "01", "12", "2011".</span><span class="sxs-lookup"><span data-stu-id="0fcc7-123">In the following example, the TOKENCOUNT function returns 3 because the string contains three tokens: "01", "12", "2011".</span></span>  
  
```  
TOKENCOUNT("01/12/2011", "/")  
```  
  
 <span data-ttu-id="0fcc7-124">Nell'esempio seguente la funzione TOKENCOUNT restituisce 4 perché la stringa contiene quattro token ("a", "little", "white", "dog").</span><span class="sxs-lookup"><span data-stu-id="0fcc7-124">In the following example, the TOKENCOUNT function returns 4 because there are four tokens ("a", "little", "white", "dog").</span></span>  
  
```  
TOKENCOUNT("a little white dog"," ")  
```  
  
 <span data-ttu-id="0fcc7-125">Nell'esempio seguente la funzione TOKENCOUNT restituisce 1.</span><span class="sxs-lookup"><span data-stu-id="0fcc7-125">In the following example, the TOKENCOUNT function returns 1.</span></span> <span data-ttu-id="0fcc7-126">La funziona cerca i delimitatori nella stringa di input e poiché non ve ne sono, aggiunge l'intera stringa come primo token.</span><span class="sxs-lookup"><span data-stu-id="0fcc7-126">The function parses the input string for delimiters and since there are none in the string, it just adds the entire string as the first token.</span></span>  
  
```  
TOKENCOUNT("a little white dog","|")  
```  
  
 <span data-ttu-id="0fcc7-127">Nell'esempio seguente la funzione TOKENCOUNT restituisce 4.</span><span class="sxs-lookup"><span data-stu-id="0fcc7-127">In the following example, the TOKENCOUNT function returns 4.</span></span> <span data-ttu-id="0fcc7-128">In questo esempio la stringa di delimitazione contiene 5 delimitatori.</span><span class="sxs-lookup"><span data-stu-id="0fcc7-128">The delimiter string in this example contains 5 delimiters.</span></span> <span data-ttu-id="0fcc7-129">La stringa di input contiene 4 token: "a", "little", "white", "dog".</span><span class="sxs-lookup"><span data-stu-id="0fcc7-129">The input string contains 4 tokens: "a", "little", "white", "dog".</span></span>  
  
```  
TOKENCOUNT("a:little|white dog","| ,.:")  
```  
  
 <span data-ttu-id="0fcc7-130">Nell'esempio seguente la funzione TOKENCOUNT restituisce 4.</span><span class="sxs-lookup"><span data-stu-id="0fcc7-130">In the following example, the TOKENCOUNT function returns 4.</span></span> <span data-ttu-id="0fcc7-131">Tutti gli spazi iniziali vengono ignorati.</span><span class="sxs-lookup"><span data-stu-id="0fcc7-131">It ignores all the leading space characters.</span></span>  
  
```  
TOKENCOUNT("        a little white dog", " ")  
```  
  
## <a name="see-also"></a><span data-ttu-id="0fcc7-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0fcc7-132">See Also</span></span>  
 [<span data-ttu-id="0fcc7-133">Funzioni &#40;espressione SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="0fcc7-133">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
